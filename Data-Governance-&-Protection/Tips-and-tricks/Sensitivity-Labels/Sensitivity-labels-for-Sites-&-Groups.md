[[_TOC_]]

# Must Read
https://docs.microsoft.com/en-us/microsoft-365/compliance/sensitivity-labels-teams-groups-sites?view=o365-worldwide#how-to-configure-groups-and-site-settings

# About audit event named "Detected document sensitivity mismatch"
## How it appears in audit log
> ![image.png](/.attachments/image-25f32d38-ce98-4188-bd3b-fc4c9aacf534.png)

## PowerShell cmdlet to Disable mail notification
> Set-SpoTenant -BlockSendLabelMismatchEmail $false

Warning : 
> ![image.png](/.attachments/image-fbf29a92-3016-4c9a-8ae2-6f7aad293e31.png)
https://www.yammer.com/askipteam/threads/901212100845568

## Improve / Block notification by another way
> The detected document mismatch event is written to the o365 audit logs by the SharePoint service, so you will find it there alongside 'file opened' etc. 
The BlockSend...Email setting only stops the automated email being sent, it does not stop the event being written to the logs. 
If you want to keep the autoemails enabled but don't want them to reach the end user, you can create an exchange dlp rule that captures it and redirects it, that way you do get a record of how often emails are being sent. 
You can then, if you wanted, use flow and this arriving email to craft a better reply to the end user.  

## Autre article : 
https://office365itpros.com/2022/08/23/document-label-mismatch-audit/