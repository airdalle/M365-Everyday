#Créer des Workbooks et gérer le contrôle d'accès

Il est possible, dans certains projets, qu'il soit nécessaire de segmenter le monitoring des alertes DLP.
S'il est toujours nécessaire pour les administrateurs globaux de sécurité d'accéder à toutes les alertes pour pouvoir, notamment, faire des parallèles en cas d'attaque dans différentes BU, il peut être requis par le client de permettre à chaque BU d'une entreprise d'avoir accès à ses propres alertes DLP sans avoir accès aux alertes DLP des autres BU.

Il est possible de réaliser cette division pour une audience technique à l'aide de Microsoft Sentinel. Pour une vue non technique, avec la même interface que le centre de compliance notamment, cela ne sera pas possible. 
De la même manière, les informations retournées ne seront pas aussi exhaustives que dans le centre de compliance, qui lui concentrera toujours, pour les utilisateurs habilités le consulter, l'intégralité des alertes avec l'ensemble des informations qui leur sont attachées.

##Marche à suivre
####1. Connecter les alertes DLP à Sentinel

Voir [cette page](https://lyon-devops.coexya.eu/tfs/Swl-DA/Data%20Gov%20et%20Protection/_wiki/wikis/Data-Gov-et-Protection.wiki?wikiVersion=GBwikiMaster&pagePath=%2FData%20Governance%20%26%20Protection%2FTips%20and%20tricks%2FAudit%20et%20Monitoring%20Activit%C3%A9s%20%26%20Incidents%2FSentinel&pageId=207).

Une fois cette étape passée, les **alertes administrateur** remontées par les stratégies DLP seront loggées dans Defender for Cloud Apps et dans Azure Sentinel.

####2. Diviser les stratégies DLP par audience
 
Dans le cas de figure où l'on veut qu'un responsable d'une audience ne puisse consulter que les alertes DLP de son audience, il faut donc dans Purview segmenter les stratégies selon ces audiences, en multipliant donc le nombre de stratégies.

Ne pas oublier qu'il faut toujours, en production, une stratégie bloquante générale pour protéger les cas de figure qui pourraient se présenter hors des audiences définies. Il faut dans ce cas veiller à ce qu'il n'y ait pas de duplication des alertes.

Attention au nommage des stratégies : c'est sur le nom que va se baser la recherche KQL pour la sélection des alertes qui nous intéressent (exemple : Rule X - BU Y).

####3. Créer un Workbook Sentinel pour chaque audience

Chaque audience doit avoir un Classeur / Workbook qui remontera ses propres alertes.
La sélection des alertes remontées se fait à l'aide d'une requête KQL.

Exemple :
```
SecurityAlert
| summarize arg_max(TimeGenerated, *) by SystemAlertId
| where DisplayName contains "Rule X - BU Y" 
```

![image.png](/.attachments/image-bae4b931-63b1-4b9b-8c07-9197f7868921.png)

Un travail doit être fait sur la mise en forme pour rendre ces informations les plus exploitables possible.

Dans le champ `Entities` on trouve les informations de l'alerte au format JSON. La mise en forme de ces informations peut être un point bloquant puisqu'il s'agit d'une information très technique.
Les informations présentes sont par exemple, dans le cas d'un mail :
- Le nom du mail
- L'expéditeur du mail
- Le destinataire du mail
- Le nom de la pièce jointe

On n'aura pas le contenu et le détail du SIT dans l'alerte. Pour plus d'informations, l'analyste devra faire appel aux administrateurs de sécurité pour qu'ils explorent l'alerte dans Microsoft Purview.

Exemple :
```
[{"$id":"2","Name":"Analyst Research.docx","Type":"file"},
{"$id":"3","Recipient":"samuel.j@orange.fr","InternetMessageId":"SJ1P223MB05305058C331D7270FA69CE2AB809@SJ1P223MB0530.NAMP223.PROD.OUTLOOK.COM","Subject":"Fw: obsidian secret data 4","DeliveryAction":"Unknown","Type":"mailMessage"},
{"$id":"4","Name":"admin","UPNSuffix":"M365x82746099.OnMicrosoft.com","AadUserId":"b03e59a3-1e3b-4781-9f65-428018f9d5fe","IsDomainJoined":true,"Type":"account","UserPrincipalName":"admin@M365x82746099.OnMicrosoft.com","AccountName":"admin"}]
```

####4. Affecter les autorisations correspondantes aux utilisateurs

Une fois les Workbooks pour chaque audience réalisés, il faut, pour chaque classeur, accorder les autorisations suffisantes aux utilisateurs pour qu'ils puissent accéder à leur classeur et pas aux autres.

Il est possible de permettre l'accès en lecture au niveau du classeur via l'interface "Classeurs Azure" / "Azure Workbooks".
![image.png](/.attachments/image-a034e2ac-4845-4c44-b5f3-5762afb6f760.png)

Access Control :
- Sur le workbook : Workbook Reader / Lecteur du workbook

**Note** : C'est curieux mais à l'heure actuelle il est possible pour l'utilisateur de modifier le workbook et donc changer la requête... (WIP)