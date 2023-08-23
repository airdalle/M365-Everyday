## Groupes de rôles importants

De plus en plus de groupes de rôles sont disponibles et administrables via Azure Active Directory (et donc par extension Privilege Identity Management qui permet de gérer des attributions de rôles plus sécurisées).

Liste non exhaustive et simplifiée de rôles importants liés à Microsoft Purview :
- Security Reader : vision du portail de compliance sans possibilité d'entrer dans le détail de la configuration des différentes stratégies. A noter que ce rôle donne aussi cette vision (limitée) dans les autres portails d'administration de la sécurité Microsoft.
- Compliance Data Administrator : Accès aux fonctions de configuration des fonctionnalités Purview, hormis l'eDiscovery, la Data Investigation et la Communication Compliance.
- Compliance Administrator : Accès à toutes les fonctions de configuration des fonctionnalités Purview. Toutefois, tout comme le Compliance Data Administrator, ce rôle ne permet pas d'utiliser le Content Explorer : un administrateur ayant ces rôles obtiendra des informations minimales dans les alertes et les logs liés aux stratégies DLP.
- Content Explorer Content Viewer (non inclus dans ADD) : Ce rôle permet d'accéder au Content Explorer et donc à investiguer les données directes des alertes ainsi que leur contexte. A associer au Compliance Administrator pour avoir "les pleins pouvoirs" en quelque sorte.

**Il existe aussi des rôles intégrés directement au portail Purview**, c'est à dire qu'ils sont gérés via le portail mais pas via AAD. Cela permet une gestion plus granulaire des rôles, mais attention toutefois puisque **ces rôles peuvent ne pas être en conformité avec la stratégie globale de gestion des identités et des rôles du client** (accès via Privilege Identity Management par exemple).
A adapter donc en fonction du client.

Plus d'informations :
- Overview exhaustive des rôles : https://learn.microsoft.com/en-us/microsoft-365/security/office-365-security/permissions-in-the-security-and-compliance-center?view=o365-worldwide
- Permissions pour accéder au Content Explorer : https://learn.microsoft.com/en-us/microsoft-365/compliance/data-classification-content-explorer?view=o365-worldwide#required-permissions-to-access-items-in-content-explorer 



## Correspondance Role / Capabilities

![image.png](/.attachments/image-3805c55d-44de-4abd-9ac3-9329f383b0dc.png)