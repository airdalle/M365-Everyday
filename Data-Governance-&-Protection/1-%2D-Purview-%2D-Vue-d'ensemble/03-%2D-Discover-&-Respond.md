[[_TOC_]]

# eDiscovery

##Overview - eDiscovery dans Microsoft Purview

La recherche de données via Microsoft Purview est possible à différents niveaux de licence.

- **Content Search** permet d'effectuer des requêtes sur le contenu Exchange, SharePoint, OneDrive et Teams en utilisant le langage de requête KQL (Kusto Query Language), en cherchant dans le contenu des mots-clé ou des informations sensibles ou dans un certain nombre de champs de métadonnées.
Ce Wiki contient plusieurs articles permettant de créer ces requêtes.

- **eDiscovery Standard** (anciennement Core eDiscovery) est une solution de gestion de dossiers (cases) et de rétention de données (hold) basée sur Content Search. Cette solution ne permet pas plus de possibilités en terme de recherche de contenus, mais permet d'organiser ses recherches de contenus en *Cases* et de placer les données *on hold* c'est à dire qu'elles ne pourront pas être supprimées par qui que ce soit durant l'enquête.

- **eDiscovery Premium** (anciennement Advanced eDiscovery) est une solution de gestion de dossiers, de rétention de données et de recherche de contenus plus aboutie et complète que Content Search. L'usage de l'outil passe par différentes étapes d'un workflow complexe.

## Réalisations clients
Nous n'avons jamais implémenté de process d'eDiscovery chez un client, néanmoins pour plus d'informations sur le sujet on peut se référer à :

- [La proposition](https://teams.microsoft.com/l/file/BF9B5D2E-18D3-4CD7-BDF7-905D667EA60E?tenantId=6adf23d8-eabe-44c8-b68a-0b8fb7aacef9&fileType=pdf&objectUrl=https%3A%2F%2Fswordoffice.sharepoint.com%2Fsites%2Fug-fr-swl-tc%2FDocuments%20partages%2FOffice%20365%20Security%20and%20Compliance%2FCompliance%20AVV%2FeDiscovery%20-%20EPIQ%2FMichelin-SWORD%20SOW050521.pdf&baseUrl=https%3A%2F%2Fswordoffice.sharepoint.com%2Fsites%2Fug-fr-swl-tc&serviceName=teams&threadId=19:a60383fd3dfa469dac69875dca734c6c@thread.skype&groupId=7bf71975-d393-4e19-9378-1ab2b4400f74) faite par Epiq à Michelin
- La documentation Microsoft sur le sujet : 
[Core eDiscovery](https://docs.microsoft.com/en-us/microsoft-365/compliance/get-started-core-ediscovery?view=o365-worldwide)
[Advanced eDiscovery](https://docs.microsoft.com/en-us/microsoft-365/compliance/overview-ediscovery-20?view=o365-worldwide)
- Pour une meilleure compréhension du process d'eDiscovery, se référer au modèle suivant :
<IMG src="https://docs.microsoft.com/en-us/microsoft-365/media/edrmv1.png?view=o365-worldwide" alt="The Electronic Discovery Reference Model (EDRM)."/>

A noter que les procédures d'eDiscovery sont très peu implémentées en France, elles sont d'actualité pour les US (et donc d'intérêt pour les clients officiant dans ce pays).

## Articles de blogs
- https://joannecklein.com/2020/01/09/5-key-questions-an-office-365-ediscovery-team-must-answer/
- https://techcommunity.microsoft.com/t5/yammer-blog/ediscovery-and-native-mode-for-yammer-now-available/ba-p/1121476
- https://joannecklein.com/2019/12/02/ediscovery-for-microsoft-teams-standard-private-channels/amp/
- https://joannecklein.com/2019/10/07/office-365-architecture-for-ediscovery-infographic/amp/

## Vidéos
- Parcours des capacités eDiscovery Standard & Premium avec un focus sur Teams : https://www.youtube.com/watch?v=hjpxIl8Keuk
- Présentation de features d'analyse avancées d'eDiscovery Premium : https://www.youtube.com/watch?v=3enEgQiAr_0