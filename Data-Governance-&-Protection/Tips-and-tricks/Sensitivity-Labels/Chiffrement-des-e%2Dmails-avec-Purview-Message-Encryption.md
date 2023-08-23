[[_TOC_]]


# Documentation générale
https://learn.microsoft.com/en-us/microsoft-365/compliance/ome?view=o365-worldwide#how-message-encryption-works

# Comparaison entre OME et MPME
The behavioral differences and different types of recipients are described in the following table.

|  |**Currently OME mail flows**  | **Deprecated OME mail flows** |
|--|--|--|
|**Mail body branding**  | “Office 365 Message Encryption"	 | “Microsoft Purview Message Encryption" |
| **Internal M365 recipients experience**	 | Any client will contain an html attachment, open the attachment to open mail in OME portal.	 | Supported Outlook client with inline experience with a message.rpmsg. Any unsupported client will show notification mail with URL link to open mail in Outlook on the Web. (This is also true for users on Exchange on-premises mailbox." |
| **External M365 recipients experience**	 | Any client will contain an html attachment, open the attachment to open mail in OME portal.	 | Any client will show notification mail with URL link to open mail in Microsoft Purview encrypted message portal; there is no attachment in mail. Mail flow rules can be modified to provide same behavior as internal recipients above.** |
| **(External) Non-M365 recipients experience**| Any client will contain an html attachment, open the attachment to open mail in OME portal. After mail is opened in the portal, mail and attachment can be viewed. All attachments are downloaded without encryption | Any client will show notification mail with URL link to open mail in Microsoft Purview encrypted message portal; there is no attachment in mail. After mail is opened in the portal, mail and attachment can be viewed. Office documents are downloaded with encryption if no changes are made by admins.*|

>*The encrypted attachments provide extra security by protecting the stored file at rest. Applications that can open Office documents may not be compatible with RMS protected Office documents. Admins can provide the same behavior as OME by enabling a global configuration to download Encrypt-only attachments without encryption: Set-IrmConfiguration – DecryptAttachmentForEncryptOnly $true

>**By modifying existing the mail flow rules to apply Purview Message Encryption protection, external M365 recipients will receive encrypted mail containing a message.rpmsg attachment and supported Outlook clients can provide show the mail content directly in the application.

# Gestion des flux réseaux - TRES IMPORTANT
https://learn.microsoft.com/en-us/microsoft-365/enterprise/urls-and-ip-address-ranges?view=o365-worldwide