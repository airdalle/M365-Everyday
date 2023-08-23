Le Workflow d'eDiscovery Premium passe par différentes étapes essentielles résumées dans l'illustration suivante :

![image.png](/.attachments/image-ff0f3794-5228-4b2e-baa9-ec44ad2b84a9.png)

1. Un évènement déclenche le processus d'eDiscovery : lettre de mission, plainte, processus automatisé...

2. Les eDiscovery Managers créent le case et assignent aux personnes légitimes les permissions sur ce case.

3. eDiscovery Premium s'appuie sur les données de "dépositaires", dits **custodians**. Les Custodians sont les utilisateurs dont les données vont être étudiées dans le cadre du processus d'eDiscovery.
Selon les situations, il est possible de placer les données de ces custodians "**on hold**", de manière assez granulaire (on peut assurer la rétention de la boîte exchange de tel custodian, tandis qu'on assurera la rétention des données OneDrive d'un autre utilisateur).
Il est possible d'ajouter des données "non custodian", des sites SharePoint par exemple, qui peuvent également servir de sources de données à placer on hold, ou bien des données hors M365.
Enfin, eDiscovery Premium fournit des fonctionnalités permettant de **communiquer avec les utilisateurs** pour leur informer, comme peut le vouloir la loi selon la législation en vigueur chez le client, de la mise sous rétention de leurs données, de l'investigation, diverses notifications...
![image.png](/.attachments/image-89b848f3-10a9-4aae-a6eb-97bd708258fa.png)

4. Une fois les sources de données définies, il faut créer une **collection de données** en exécutant une recherche Content Search. Plusieurs mécanismes permettent de prétraiter la donnée afin de faciliter son traitement dans la partie suivante. Une fois la collection de données jugée satisfaisante, on crée un **review set** intégrant toutes les données de cette collection.
![image.png](/.attachments/image-8d78ab67-266c-4f55-8b63-9f71c04c1fb3.png)
![image.png](/.attachments/image-5c660cbf-0360-4377-9e46-d632741fea0b.png)

5. La plus grande partie du traitement, ainsi que la vraie valeur ajoutée d'eDiscovery Premium par rapport à eDiscovery Standard, se trouve dans le traitement au sein des review set. Plusieurs opérations y sont rendues possible :
**L'analyse des données du Review Set** mettra à profit toutes les capacités Machine Learning d'eDiscovery Premium pour accélérer le processus de review du set.
![image.png](/.attachments/image-41c552c0-d013-4c55-b9fd-fa96d1f63f8c.png)
Il est possible de **review plusieurs doublons à la fois**, en focalisant l'attention du reviewer sur les différences entre copies; de **trouver les "thèmes"** qui permettent d'indiquer l'intention sous-jacente du document (le ton, ...)...
Il est aussi possible de **tag les documents** via un système de checkboxes, ce qui facilitera le filtrage des documents durant cette étape.
![image.png](/.attachments/image-baeab7ff-d555-4908-bccf-9b49011ec350.png)
Le processus peut passer par **plusieurs review sets consécutifs** : le premier filtrage peut enrichir un deuxième review set, etc. A la fin du traitement, on aura les données requises, nécessaires et suffisantes et l'on pourra passer à l'export.

6. **L'export des données** peut être fait de plusieurs manières : téléchargement, dépôt dans un répertoire M365...

Ressources :
- **Lien très important :** ensemble des métadonnées pouvant être requêtées aux différentes étapes du workflow de eDiscovery Premium : https://learn.microsoft.com/en-us/microsoft-365/compliance/document-metadata-fields-in-advanced-ediscovery?view=o365-worldwide
- https://learn.microsoft.com/en-us/microsoft-365/compliance/near-duplicate-detection-in-advanced-ediscovery?view=o365-worldwide
- https://learn.microsoft.com/en-us/microsoft-365/compliance/themes-in-advanced-ediscovery?view=o365-worldwide
- https://learn.microsoft.com/en-us/microsoft-365/compliance/tagging-documents?view=o365-worldwide
