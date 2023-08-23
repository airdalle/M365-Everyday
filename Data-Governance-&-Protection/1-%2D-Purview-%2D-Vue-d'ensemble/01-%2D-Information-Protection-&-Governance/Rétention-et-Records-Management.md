Préciser où se configurent les étiquettes avec paramètre de record.

### [Etiquettes et stratégies de rétention](https://docs.microsoft.com/en-us/microsoft-365/compliance/retention?view=o365-worldwide)

Les étiquettes et stratégies de rétention permettent de gérer le cycle de vie des documents stockés dans Office 365.

Les **étiquettes** permettent d'attribuer des paramètres à un ou plusieurs documents :
- Effet de la rétention
- Déclencheur de la rétention 
- Durée de la rétention
- Issue de la rétention


. Elles se configurent dans la fonctionnalité "Gouvernance des informations" :
![image.png](/.attachments/image-0caa7a53-8260-48e3-8c64-a4c42f7cec9c.png)
Pour pouvoir être associées à un document ou un email par les utilisateurs, les étiquettes de rétention doivent être publiées sur le(s) site(s) ou boite(s) mail souhaités dans une stratégie de publication :
![image.png](/.attachments/image-6e59695f-6ca7-4946-8b4e-9e0f097b987e.png)
Les [**stratégies de rétention**](https://docs.microsoft.com/en-us/microsoft-365/compliance/create-retention-policies?view=o365-worldwide) quant à elles s'appliquent sur un ou plusieurs workloads (SharePoint/OD, Exchange, Canaux d'équipe, conversations Teams) de manière complètement automatique. Elles sont utiles par exemple pour appliquer une suppression automatisée des emails ou des messages dans Teams au bout d'un certain temps, afin d'éviter un surstockage d'informations (pour des raisons de conformité, d'écologie, etc...)
![image.png](/.attachments/image-2429759d-cf1a-46fa-b01a-b865f6f6c526.png)

**Application des étiquettes de rétention** 

Une fois publiées via une stratégie, les étiquettes de rétention peuvent être appliquées [automatiquement](https://docs.microsoft.com/en-us/microsoft-365/compliance/apply-retention-labels-automatically?view=o365-worldwide) ou manuellement sur les documents. 
L'application automatique peut se faire sur les conditions suivantes :
![image.png](/.attachments/image-4caaecae-000b-4549-b1c1-f937495aa4df.png)

Un document ou un email ne peut avoir qu'une étiquette de rétention. Si un document est soumis à plusieurs règles de rétention (une stratégie + une étiquette, par exemple), alors un ensemble de règles dites "[règles de précédence](https://docs.microsoft.com/en-us/microsoft-365/compliance/retention?view=o365-worldwide#the-principles-of-retention-or-what-takes-precedence)" s'applique :
<IMG src="https://docs.microsoft.com/en-us/microsoft-365/media/principles-of-retention.png?view=o365-worldwide" alt="Diagram of the principles of retention."/>

 
**Complémentarité Stratégies / Etiquettes :**
Il est possible d'utiliser les stratégies et les étiquettes de conservation de façon complémentaire. 

Exemple : 
- Création d'une stratégie de rétention avec suppression automatique des contenus cinq ans après leur dernière modification pour l'ensemble des OneDrive de l'entreprise. 
- Création d'une étiquette de rétention permettant de retenir le contenu pour 20 ans à date de sa création, publication de cette étiquette sur l'ensemble des OneDrive. Les utilisateurs pourront ainsi appliquer manuellement cette étiquette à des documents spécifiques qu'ils estiment devoir être conservés plus longtemps que 5 ans.

### [Records Management](https://docs.microsoft.com/en-us/microsoft-365/compliance/records-management?view=o365-worldwide)



 Attention, il s'agit d'une **solution ME5** donc des coûts supplémentaires peuvent s'appliquer en fonction du nvieau de licence du client.
Cette solution complète la solution "Gouvernance des informations" en ajoutant les fonctionnalités suivantes :
- Import ou création directe d’un plan de gestion des fichiers (« File plan »)
- Les étiquettes de rétention peuvent bénéficier d’un paramètre supplémentaire « marquer les items en tant que records » : 
- Lorsque l’étiquette est appliquée sur un document, celui-ci ne peut plus être ni supprimé ni modifié
- Le statut de record peut être déverrouillé et permettre la modification de l’item
- Les modifications effectuées sont tracées et mises à disposition de l’admin du site dans une bibliothèque dédiée.
- Possibilité de demander une revue du document à la fin de la période de rétention (« Disposition Review »)
- Possibilité de faire démarrer une période de rétention à partir d’un événement non planifié
- Les étiquettes de rétention peuvent également être appliquées au niveau d'une bibliothèque ou d'un dossier

