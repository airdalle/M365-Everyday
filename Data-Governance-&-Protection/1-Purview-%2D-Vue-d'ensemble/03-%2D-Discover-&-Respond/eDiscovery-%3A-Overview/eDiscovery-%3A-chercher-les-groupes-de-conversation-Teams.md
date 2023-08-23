Il peut être demandé de chercher des groupes de discussion Teams (group chat) via leurs noms. Or, ce n'est pas possible simplement via Content Search, une telle requête demande l'utilisation d'eDiscovery Premium ainsi que quelques informations supplémentaires.

En effet, les messages de group chat ne sont pas stockés dans un site SharePoint ou une boite mail commune qui serait simple à requêter, mais **dans les mailboxes EXO de tous les participants au groupe** (comme pour les channels privés des Teams au passage).

![image.png](/.attachments/image-3228e8fb-ed26-4541-848d-4083c29b5994.png)

Par conséquent, il est nécessaire de créer un case eDiscovery et placer en custodian un utilisateur dont on sait qu'il fait partie du groupe de discussion en question. A noter qu'il n'est pas nécessaire qu'il soit suspecté d'écrire des messages incriminants : sa boîte EXO contiendra **tous les messages émis et reçus durant sa présence dans le groupe en question.**

Cette requête permet de créer une collection de tous les messages Teams directs (1:1, canaux privés et group chats) d'un utilisateur.
![image.png](/.attachments/image-3d2aa573-b874-4fd2-9f3b-b7baa610b72c.png)

A partir de cette collection, créer un Review Set et appliquer un filtre sur le "Subject/Title" avec le nom du group chat.
![image.png](/.attachments/image-533a9127-8265-4119-8fa5-0cee8f6a50a3.png)

Créer un Review Set à partir de cette sélection.

Ressources :
- Workflow classique de case eDiscovery touchant à Microsoft Teams : https://learn.microsoft.com/en-us/microsoft-365/compliance/teams-workflow-in-advanced-ediscovery?view=o365-worldwide
- Ensemble des métadonnées pouvant être utilisées dans eDiscovery en fonction de l'étape du Workflow : https://learn.microsoft.com/en-us/microsoft-365/compliance/document-metadata-fields-in-advanced-ediscovery?view=o365-worldwide