
# Documentation MS
https://learn.microsoft.com/en-us/information-protection/develop/concept-fips-compliance

# Conversation Yammer sur le sujet
https://www.yammer.com/askipteam/#/threads/show?threadId=1969311701680128
>I need to clarify the SDK docs. I realized it's muddy after re-reading.
MIP File SDK uses ECB mode for Office file types. All other file types are CBC (Pfile, PDF, etc.)
MIP Protection SDK uses CBC mode by default. Apps can switch to ECB mode. 
MSIPC defaults to CBC, apps can switch to ECB mode. 
>![image.png](/.attachments/image-f5162233-72e0-4295-9bcf-6f0378b57f4d.png)

>The SDK that OME (or any service) uses isn't relevant in this case. They have the option to use the legacy crypto modes for both MIP SDK and MSIPC (RMS SDK 2.1). The service-side OME components use MSIPC but will move to MIP at some point soon. That work is independent from work to move to CBC. 
>![image.png](/.attachments/image-5879557e-7ce0-4780-a59b-154eac6db855.png)

# Article externe sur Office Message Encryption (OME/MPME)
* https://office365itpros.com/2022/10/17/office-365-message-encryption-ecb/
* https://labs.withsecure.com/advisories/microsoft-office-365-message-encryption-insecure-mode-of-operation
