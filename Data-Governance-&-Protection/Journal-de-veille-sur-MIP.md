[[_TOC_]]

# Annonces du centre de messagerie - Console Administration M365
##Exchange auto-labeling policy now supports replacing manual label and encrypting email received from any organization
MC316412 · Published 20 janv. 2022
**Message Summary**
Exchange auto-labeling policies can protect mail in transit by applying sensitivity labels to mail received from inside or outside the organization that are not manually labeled. Currently, encryption can only be applied to unencrypted mail received from inside the organization. We are now adding the capability to configure policies that can apply encryption to mail received from outside the organization. In addition, policies can be configured to replace a label even if mail already has a manual label applied, provided the label priority on the mail is lower or same.
This message is associated with Microsoft 365 Roadmap ID 85668.

**When this will happen:**
Rollout will begin in mid-February and is expected to be complete by early March.

**How this will affect your organization:**
In order to protect mail with sensitive content as soon as it is introduced to the organization, if an external customer or partner starts a conversation that the receiving organization considers sensitive, auto-labeling can protect the mail with encryption when the mail arrives in the recipient’s mailbox. With this new feature, admins can create policies by designating a Rights Management owner to allow encryption on the receiving mail.

Additionally, to ensure certain sensitive content in mail remains in compliance with organization policies, auto-labeling can enforce classification with a label regardless of whether a user has manually labeled a mail with lower classification. By default, manually labeled mail cannot be overwritten by auto-labeling. With this new feature, admins can create policies that evaluate label applications solely comparing label priority of the existing and new label to be applied.
><IMG src="https://img-prod-cms-rt-microsoft-com.akamaized.net/cms/api/am/imageFileData/RWRtT7?ver=5c4d" alt="Create policies"/>

**What you need to do to prepare:**
To access, go to Microsoft 365 compliance center > Information Protection > Auto-labeling list view. Here, you can create an auto-labeling policy and select a sensitivity label with encryption, then setup the additional policy settings.
><IMG src="https://img-prod-cms-rt-microsoft-com.akamaized.net/cms/api/am/imageFileData/RWRzmD?ver=1529" alt="Information protection"/>

## Automatically configure Teams DLP policies to protect files shared in team messages
**Message Summary**
This new update will enable Teams DLP policies to protect chats in Teams. With this capability, all your existing and new policies will automatically protect files shared in Teams private chats and channel messages.

This message is associated with Microsoft 365 Roadmap ID: 85667.

**When this will happen:**
Rollout will begin in early February and is expected to be complete by late February.

**How this will affect your organization:**
Teams DLP policies can currently be scoped to protect users, Teams team/channels, and security group/distribution lists. With this new feature, we're adding the capability to deploy these Teams DLP policies to automatically protect the content shared as a part of the Teams ‘Team’ and ‘Chats'. This capability can also be disabled if you wish at any time.
><IMG src="https://img-prod-cms-rt-microsoft-com.akamaized.net/cms/api/am/imageFileData/RWRtTl?ver=1a80" alt="Teams DLP policies"/>

When users in a particular Teams team and channel are covered by Teams DLP policy, all the messages (initiated by the user covered under the policy) wil be protected. With this capability, you can apply the same Teams DLP policy rules and actions on the associated SharePoint site that stores documents shared by users within that Team/Channel. This will enable you to manage protection with the same Teams DLP policy rather than requiring the application of distinct policies to SharePoint and OneDrive for Business individually to cover the documents.

Additionally, when users protected as a part of the Teams DLP policy initiate a One-on-One chat, the chat conversation is protected by the Teams DLP policy. With this new capability, you will be able to apply the same Teams DLP policy rules and actions on the associated OneDrive for Business folder that stores any documents shared by a chat participant

Note: If the recipient of a message is covered by the Teams DLP policy, and the sender is not covered under any Teams DLP policy, then there will be no protection applied.

**What you need to do to prepare:**
For access, go to Microsoft 365 compliance center > Data Loss Prevention > Policy page. There will be a banner to show the new feature. You can enable the feature by clicking on the Update policies button in the banner.
><IMG src="https://img-prod-cms-rt-microsoft-com.akamaized.net/cms/api/am/imageFileData/RWRJhR?ver=746e" alt="Update policies button"/>

## Certificate based Authentication for Security and Compliance Center PowerShell
MC316448 21/01/2022
**Message Summary**
With this update, which will improve the security of your tenant, Security & Compliance PowerShell will enable configuration of certificate-based authentication to allow unattended App-only access. 

**When this will happen:**
Rollout will begin in mid-February and is expected to be complete by early March.

**How this will affect your organization:**
If your organization is currently using "Basic authentication" for application access, you will need to migrate to certificate-based authentication prior to mid-February.

**What you need to do to prepare:**
To migrate to certificate-based authentication, follow these steps:

- Step 1: [Register the application in Azure AD](https://docs.microsoft.com/powershell/exchange/app-only-auth-powershell-v2?view=exchange-ps#step-1-register-the-application-in-azure-ad)
- Step 2: [Assign API permissions to the application](https://docs.microsoft.com/powershell/exchange/app-only-auth-powershell-v2?view=exchange-ps#step-2-assign-api-permissions-to-the-application)
- Step 3: [Generate a self-signed certificate](https://docs.microsoft.com/powershell/exchange/app-only-auth-powershell-v2?view=exchange-ps#step-3-generate-a-self-signed-certificate)
- Step 4: [Attach the certificate to the Azure AD application](https://docs.microsoft.com/powershell/exchange/app-only-auth-powershell-v2?view=exchange-ps#step-4-attach-the-certificate-to-the-azure-ad-application)
- Step 5: [Assign Azure AD roles to the application](https://docs.microsoft.com/powershell/exchange/app-only-auth-powershell-v2?view=exchange-ps#step-5-assign-azure-ad-roles-to-the-application)

**Learn more:**
- [Connect to Security & Compliance PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-scc-powershell?view=exchange-ps)
- [App-only authentication for unattended scripts in the EXO V2 module](https://docs.microsoft.com/powershell/exchange/app-only-auth-powershell-v2?view=exchange-ps)


## Exchange Transport Rule Report moving to the new Exchange Admin Center (EAC) from the Security and Compliance Center
MC316157
We will be retiring the Exchange Transport Rule (ETR) report from the Security and Compliance Center (SCC).

The report will no longer be available in the security reporting dashboard, beginning early March 2022.
Instead, we recommend the utilization of the replacement for this report, found in the new (MC252053 - July, 2021) modern Exchange Admin Center (EAC), which is where we will continue to invest our development resources.

**Note:** The report will no longer be available in the respective enviroments below starting the end of March 2022 in the security reporting dashboard. The replacement for this report, in the new modern Exchange Admin Center (EAC), is rolling out to WW regions beginning in early January and expect to complete by early February, along with the other mail flow reports and features.

**Key points:**
Timing: Retirement:
WW: Early March
GCC: mid-April
GCC-High: mid-April
**Action:** We recommend you go to the new modern EAC to use the enhanced version of the Exchange Transport Rules report where we will continue to invest our development resources.

## (Updated) Records Management, Information Governance & eDiscovery– Optimized behavior of file versions preserved
https://www.microsoft.com/microsoft-365/roadmap?filters=&featureid=82062
```
To improve performance, any file with multiple versions that is deleted from SharePoint or OneDrive which is
preserved to the Preservation Hold Library (due to its applicable retention label, retention policies or eDiscovery
holds) will now be retained as a single file containing its full version history, rather than each version being
retained as individual files as has been the case until now.

Note: We had previously announced that this feature would begin rollout in the fall of 2021, however we are
postponing this rollout until early 2022. This allows our customers more time to prepare and for us to ensure that
the rollout plan accommodates the end of year activities and minimizes the risk of impact.

This message is associated with Microsoft 365 Roadmap ID 82062.

**When this will happen:**
Rollout will begin in early February (previously early January) and be complete by mid-March (previously mid-February).
```
## Effacer les message pendant la période de rétention
https://admin.microsoft.com/AdminPortal/home#/MessageCenter/:/messages/MC289965?MCLinkSource=DigestMail

```
Pour améliorer la cohérence de l’expérience utilisateur entre OneDrive et SharePoint, le comportement de toute
étiquette de rétention définie sur « conserver les éléments pendant une période spécifique » dans SharePoint changera
pour permettre aux utilisateurs de « supprimer » le document qui sera ensuite conservé dans la bibliothèque de
conservation jusqu’à l’expiration de la période spécifiée.
En réponse à vos excellents commentaires et en offrant plus de flexibilité aux différentes organisations, nous avons
ajouté la possibilité de configurer ce comportement pour votre locataire.
La valeur par défaut sera que ce comportement soit « activé », ce qui permet la suppression comme spécifié
précédemment. Si ce comportement est configuré « désactivé », les utilisateurs ne peuvent pas supprimer ces fichiers
et un message d’erreur s’affiche, comme cela a été le cas dans SharePoint jusqu’à présent.
Ce message est associé à Microsoft 365 Roadmap ID 82063

**Quand cela se produira:**
Le déploiement de ce changement débutera début novembre et se terminera d’ici la fin décembre (auparavant fin
novembre).
```

## Gestion des versions de la Preservation Hold Library
https://admin.microsoft.com/AdminPortal/home#/MessageCenter/:/messages/MC288633?MCLinkSource=DigestMail
```
Quand cela se produira:
Le déploiement débutera début janvier 2022 (auparavant octobre 2021) et sera terminé à la mi-février
(précédemment novembre 2021).

Comment cela affectera votre organisation :
Cette mise à jour modifiera le comportement des fichiers supprimés qui sont configurés pour être conservés et qui ont
plusieurs versions du fichier. Ils seront conservés dans la bibliothèque Preservation Hold en tant que fichier unique
avec toutes les versions dans le cadre de son historique des versions, tout comme elles existent avant d’être
supprimées. Auparavant, chaque version était conservée individuellement dans un fichier distinct.
En outre, cette modification affectera également votre capacité à rechercher ces versions dans eDiscovery. La
recherche ne fonctionnera désormais que sur la dernière version d’un document par défaut plutôt que d’obtenir
plusieurs correspondances pour les versions entre elles, ce qui assure la cohérence des recherches eDiscovery, que le
fichier ait été supprimé ou non.
Si vous avez configuré des retenues basées sur des requêtes dans eDiscovery, la façon dont les fichiers conservés
sont recherchés et conservés sera modifiée, comme indiqué ci-dessus. Si un fichier est supprimé d’une source couverte 
ar une stratégie de conservation basée sur une requête, il ne conservera plus les versions de document spécifiques
qui répondent aux critères de requête et ne conservera la dernière version du document que si elle répond aux
critères de requête lorsque le document est supprimé.
```

# Webinaires 
- 07/12/2021 What’s new with Insider Risk and Communication Compliance
https://mipc.eventbuilder.com/event/52884/occurrence/49647?rauth=853.3277787.3996cecc24d0ec7f1edbae3b4c58c892015414c2af148f21a796251a74fa3e0c
- 15/11/2021 - What’s new with Microsoft Information Protection + Data Loss Prevention
https://mipc.eventbuilder.com/event/52888/occurrence/49651/recording?rauth=853.3220612.05b548ceb2e31feea42dc02f2fad0e82e3fc1050b5854932f66d549edae59985



# Ignite 2021 (Octobre 2021)
## Sessions:
- Keynote: Manage risk and compliance with end-to-end security solutions https://aka.ms/IGNITEBRK241
- Breakout: Is your information protection ready for the hybrid workplace 
 https://myignite.microsoft.com/sessions/e5b197f1-2b5d-4833-93c2-9512431bef99  
- Learn Live: CONLL109 Microsoft Ignite – Prevent Data Loss in Microsoft 365 https://myignite.microsoft.com/sessions/5dc963d4-dd4a-40be-94ab-b5fc8a22210e
 

## Blogs:
- Announcing the Availability of Microsoft Endpoint Data Loss Prevention for macOS https://aka.ms/Ignite2021DLP
- Microsoft Information Protection: Announcing Enhanced Automatic Classification Capabilities! https://techcommunity.microsoft.com/t5/security-compliance-and-identity/microsoft-information-protection-announcing-enhanced-automatic/ba-p/2871144
- Expanding DLP coverage to file type, content types, customized tips, and more! https://techcommunity.microsoft.com/t5/security-compliance-and-identity/announcing-expanded-dlp-coverage-to-new-file-and-content-types/ba-p/2902869
- What’s new in Security and Compliance in SharePoint, OneDrive, and Teams https://techcommunity.microsoft.com/t5/microsoft-sharepoint-blog/what-s-new-in-security-and-compliance-in-sharepoint-onedrive-and/ba-p/2910640#.YYGCKUiYbUU.linkedin
- Default labels and policies for Microsoft Information Protection https://docs.microsoft.com/en-us/microsoft-365/compliance/mip-easy-trials?view=o365-worldwide