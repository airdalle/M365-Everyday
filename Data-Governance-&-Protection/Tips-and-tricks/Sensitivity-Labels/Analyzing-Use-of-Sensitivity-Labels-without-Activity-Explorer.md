# **Lien :**
https://office365itpros.com/2022/11/15/sensitivity-labels-analysis/ (15/11/2022)

# **Dump :** 
**Understanding Who Does What with Sensitivity Labels**
The Activity explorer is in the Data Classification section of the Microsoft Purview Compliance portal. Its intention is to allow tenant and compliance administrators to [understand how users apply retention and sensitivity labels to files and messages](https://learn.microsoft.com/en-us/microsoft-365/compliance/data-classification-activity-explorer?WT.mc_id=M365-MVP-9501) over the last 30 days. The Activity explorer also surfaces retention label usage and DLP activities, but in this discussion, we focus on analyzing the use of sensitivity labels.

The information presented in the Activity Explorer comes from the unified audit log. Microsoft’s documentation says that extraction “transforms” the audit data. In other words, Activity Explorer extracts the relevant information from the audit event payloads and presents the data in a more accessible form along with a set of filters to cut and dice the data in whatever way you want.

Good as the Activity Explorer UX might be, it’s not a tool to perform any in-depth analysis of audit data relating to sensitivity labels, especially when the volume of events generated daily grows. In this article, I explain how to extract the audit payload information for events relevant to user application of sensitivity labels to documents and messages and answer questions like who applies sensitivity labels and what labels they use.

I’ve been down this path before to [explore the audit events generated for sensitivity labels](https://office365itpros.com/2021/02/16/sensitivity-labels-report-audit/) after Microsoft introduced the feature in early 2021. Time moves on and changes happen, so it was time to write a new script ([available from GitHub](https://github.com/12Knocksinna/Office365itpros/blob/master/AnalyzeSensitivityLabelUsage.PS1)) to demonstrate the principle of analyzing sensitivity label audit records. Feel free to expand its code to meet your needs.

**Fetching Sensitivity Label Data**
Many audit events related to sensitivity labels hold the immutable identifier for the label rather than its display name. To find the set of labels in the tenant, connect to the compliance endpoint with _Connect-IPPSSession_ and run the _Get-Label_ cmdlet. To make it convenient to convert an identifier to the label name, put the results in a hash table.

```
Write-Host "Retrieving sensitivity labels used in the tenant"
$Labels = @{}
[array]$LabelSet = Get-Label | Select-Object ImmutableId, DisplayName
If (!($LabelSet)) { Write-Host "Can't find any sensitivity labels - exiting"; break }
ForEach ($L in $LabelSet) { $Labels.Add([string]$L.ImmutableId, [string]$L.DisplayName) }
```


**Fetching Audit Data**

The next step is to retrieve relevant audit records from the audit log. This code:

- Declares the set of audit operations to fetch.
- Sets start and end dates for the audit log search. Office 365 E3 tenants can go back 90 days while Office 365 E5 tenants can fetch data for the last year.  Depending on the volume of audit events generated in your tenant, you might need to reduce the timespan for the search.
- Calls the Search-UnifiedAuditLog cmdlet to perform the audit log search.
- Removes any DLP events returned by the search. If a DLP policy applies a sensitivity label to an email message, Exchange also logs an MIPLabel event. The script only needs to process one event, so it drops the DLP events.


```
$Operations = ("SensitivityLabelUpdated", "SensitivityLabelApplied", "FileSensitivityLabelApplied", "MIPLabel")
$StartDate = (Get-Date).AddDays(-90)
$EndDate = (Get-Date).AddDays(1)
[Array]$Records = Search-UnifiedAuditLog -StartDate $StartDate -EndDate $EndDate -Formatted -ResultSize 5000 -Operations $Operations
If (!($Records)) { Write-Host "No audit records for sensitivity label application found - exiting" ; break }
$Records = $Records | Where-Object {$_.RecordType -ne "ComplianceDLPExchange"}
```


**Analyzing Audit Data**
Every audit record has a payload in a JSON-formatted property called AuditData. Although some of the important properties for an audit event, such as the user, operation, and timestamp, are available without going near AuditData, to extract details of the action captured in an audit record, the code must convert _AuditData_.

After converting AuditData, a Switch statement processes audit records for the different operations. For instance, here’s what happens for a _SensitivityLabelApplied_ event:

    
```
"SensitivityLabelApplied" {
     $Type = "Label assigned by user"
     $LabelAdded = $Labels[$AuditData.SensitivityLabelEventData.SensitivityLabelId]
     $Application = $AuditData.Application
     $ObjectId = [System.Web.HttpUtility]::UrlDecode($AuditData.ObjectId)
     $Item = $ObjectId.Split('/')[-1]    
     $Site = "https://" + $ObjectId.Split("/")[2] + "/sites/" + $ObjectId.Split("/")[4] + "/"
    }
```

Before writing out details of an audit event, the code checks if the user noted is one of the special SharePoint accounts. In addition to manual user application of a sensitivity label to an Office document or PDF file, the system can assign labels through an auto-label policy or if an administrator [defines a default sensitivity label for a document library](https://office365itpros.com/2022/01/28/default-sensitivity-label-doclib/). To highlight these operations, the code updates the type property for the report.

```
If ($UserId -eq "app@sharepoint") {
     $Type = "Default label applied by document library" 
 } ElseIf ($UserId -eq "SHAREPOINT\system") { 
   $Type = "Label applied by auto-label policy" }
```
 
Assigning sensitivity labels as the default for a document library or through an auto-label policy requires Office 365 E5 or Microsoft 365 Compliance E5 licenses. See [Microsoft’s compliance licensing guidelines](https://learn.microsoft.com/en-us/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance?WT.mc_id=M365-MVP-9501) or the [PDF download specifying Purview features and licensing requirements](https://go.microsoft.com/fwlink/?linkid=2139145).

**Reporting the Data**
After processing each audit record, the code updates a PowerShell list containing the report output. As usual, you can do whatever you want with the data. To answer the questions posed above, I used the Group-Object cmdlet to generate this result:

```
Most commonly used sensitivity labels
-------------------------------------
Name                  Count
----                  -----
Public                  109
Confidential             33
Internal                 15
Eyes Only                 5
Sensitive Stuff           3
Black Matter              3
No Encryption             1
Secret                    1
Market Sensitive          1
```


Given that the Public label is the default for the document library I use to hold blog posts, it’s not surprising that it’s at the top of the list. When reviewing who applied sensitivity labels (Figure 1), it was no surprise that that my account came in on top. I also found non-tenant users listed among those who applied labels. This can happen if the tenant has a mail flow rule that applies sensitivity labels to inbound messages.

**Analyzing the usage of sensitivity labels**
![image.png](/.attachments/image-a9e48a91-8977-4999-bb35-28f38d8681cb.png)
Figure 1: Analyzing the usage of sensitivity labels

**Exporting Activity Explorer Data**
If you’re interested in a more general export of the data used by the Activity Explorer, Microsoft released the Export-ActivityExplorerData cmdlet to general availability in October 2022. It’s not the most elegant cmdlet available in the Exchange Online management module (V3.0 or later), but it might do a job for you. For more information, [Vasil Michev covers the Export-ActivityExplorerData cmdlet on his blog](https://www.michev.info/Blog/Post/4174/fetching-activity-explorer-data-via-the-export-activityexplorerdata-cmdlet).

**No Consistency in Audit Payloads**
It would be nice if Microsoft 365 engineering groups all generated the same kind of content in audit records. The basics of audit records are consistent, but the information inserted into the audit payload varies dramatically across workloads. The lack of consistency means that those who want to interrogate the audit log to extract information (including the Activity Explorer) must jump through hoops to get what they need. That’s a real pity because it makes the audit log a less accessible asset for tenant administrators.