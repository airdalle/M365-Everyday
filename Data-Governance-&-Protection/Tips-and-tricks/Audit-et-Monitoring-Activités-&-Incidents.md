[[_TOC_]]

# Activity Explorer
* https://learn.microsoft.com/en-us/microsoft-365/compliance/data-classification-activity-explorer?view=o365-worldwide

# Audit
* https://learn.microsoft.com/en-us/microsoft-365/compliance/audit-solutions-overview?view=o365-worldwide

# Manage DLP Incidents & Alerts in M365 Defender
https://techcommunity.microsoft.com/t5/security-compliance-and-identity/learn-how-to-investigate-microsoft-purview-data-loss-prevention/ba-p/3732758

# API Office 365 Management Activity
* https://learn.microsoft.com/en-us/office/office-365-management-api/office-365-management-activity-api-schema
* Microsoft 365 Compliance audit log activities via O365 Management API - Part 1 ==> https://techcommunity.microsoft.com/t5/security-compliance-and-identity/microsoft-365-compliance-audit-log-activities-via-o365/ba-p/2957171
* Microsoft 365 Compliance audit log activities via O365 Management API - Part 2 ==> https://techcommunity.microsoft.com/t5/security-compliance-and-identity/microsoft-365-compliance-audit-log-activities-via-o365/ba-p/2957297

# Connecteur Sentinel Microsoft Purview Information Protection (MIP)
* https://learn.microsoft.com/en-us/azure/sentinel/connect-microsoft-purview
* https://learn.microsoft.com/en-us/azure/sentinel/microsoft-purview-record-types-activities

# Microsoft Purview Advanced Rich Reports : MPARR
* https://github.com/microsoft/Microsft-Purview-Advanced-Rich-Reports-MPARR-Collector
> ![image.png](/.attachments/image-ac3186e9-62ff-488a-8fac-29245b900770.png)

> ![image.png](/.attachments/image-e3f4476b-b7ac-42bd-b5db-047678ffa8e3.png)

# CAMP Configuration for Microsoft Purview
## Documentation
https://github.com/cammurray/orca
## Prereq & quickstart
* `Install-Module -Name ExchangeOnlineManagement`
* `Install-Module -Name CAMP`
* `Get-CAMPReport`
* Récupérer le rapport : [..]/AppData/Local/Microsoft/CAMP/
## Exemple
> ![image.png](/.attachments/image-bb78c8cd-e1e1-4e98-b944-8151b61bfa3d.png)

# ORCA - Microsoft Defender for Office 365 Recommended Configuration Analyzer Report
## Documentation
https://github.com/cammurray/orca
## Prereq & quickstart
* `Install-Module -Name ExchangeOnlineManagement`
* `Install-Module -Name ORCA`
* `Get-ORCAReport`
* Récupérer le rapport : [..]/AppData/Local/Microsoft/ORCA/
## Exemple
> ![image.png](/.attachments/image-0ecd906d-6df6-4b01-9bc8-93b7f1cddebb.png)

# Azure Data Explorer
## Documentation
https://learn.microsoft.com/en-us/azure/data-explorer/
## URL
https://dataexplorer.azure.com/
## Blogs
* [Unlimited Advanced Hunting for Microsoft 365 Defender with Azure Data Explorer](https://koosg.medium.com/unlimited-advanced-hunting-for-microsoft-365-defender-with-azure-data-explorer-646b08307b75)
> In this article I'd like to demonstrate how you can leverage Azure Data Explorer (ADX) to archive data from Microsoft 356 Defender without having to make use of Microsoft Sentinel in between. Because relaying this data through Sentinel is not preferred by most, due to the added costs that come along with it. Which can be huge in some cases.
![image.png](/.attachments/image-25494c0b-7629-4c09-82c7-adabffa520b8.png)
![image.png](/.attachments/image-cfe9b3fb-6f90-49ed-ab3a-7e66d4432b44.png)