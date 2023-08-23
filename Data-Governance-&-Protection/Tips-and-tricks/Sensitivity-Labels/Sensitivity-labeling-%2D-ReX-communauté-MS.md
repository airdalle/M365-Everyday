[[_TOC_]]

# Modification de la structure des sensitivity labels et impacts pour les utilisateurs
## Enoncé du problème
https://www.yammer.com/askipteam/threads/1732888691105792
![image.png](/.attachments/image-62b91bdb-2bcb-4622-8dd4-ebe34192c684.png)
## Réponse
>All files which are already labeled with the parent label "Office Use Only" remains this label.
If you create afterwards a child label "General-unencrypted (Default label)" and define also this one as the "default label" this will change nothing to the already label files with "Office Use Only".
In other words: A default label will NOT overwrite / overrule here.

>And btw.: If you create afterwards child labels and publish the parent label AND child labels to the user, they are not able anymore to select the parent label and must choose one of the child labels going forward :-). But if you deploy *just* the parent label *without' the child labels, then the user can apply the parent label but NOT if you deploy beside the parent ALSO the child label ;-).

# La Policy ne se déploie pas sur des utilisateurs ajoutés à posteriori à la policy
## Enoncé du problème
> ![image.png](/.attachments/image-54a8b021-cfc5-4c64-8c8c-6bf5ebd1bb4c.png)
## Opérations de diagnostic à mener
1. 
> Please verify whether the RMS template is in the "Published" status:
>>Install-Module AIPService
Get-AipServiceTemplate
Get-AipServiceTemplate -TemplateId <...> | FL *
Set-AipServiceTemplateProperty -TemplateID <...> -Status Published

2. 
> use the 'Unified Labeling Support Tool' to initiate a full reset for the affected user:
>> https://aka.ms/UnifiedLabelingSupportTool
>>> Using RESET with the tool was not meant to be used as solution. It's for testing purposes only; for one user. Then as next step a RECORD PROBLEM could be done to see where the bootstrap process fails. For this kind of analyzes, a support ticket would be needed
> If reset does not help, I recommend to open a support ticket.

>> That's not a feasible solution when you have thousands of users onboarded and they are all getting the same error.   Could it be related to a known issue?

3. 
> I may have found the issue by looking at the template properties using 
>>Get-AipServiceTemplate -TemplateId <guid> | fl *

> The ScopedIdentities value is not updating with the additional users/groups that are added.
It as noted above, is still showing the original users and not the users added 2 days ago in my case.
Is there anyway to force a refresh of the AIP policy/template for an existing label


# Les fichiers de type .MSG chiffrés avec AIP ne sont plus lisibles/consultables
## Enoncé du problème
> ![image.png](/.attachments/image-aac965ac-8609-4de9-8bf2-63d5e0452c38.png)
## Diagnostic
> ![image.png](/.attachments/image-db5593c7-1f1f-42dc-8047-3e9cfdfeafa9.png)

