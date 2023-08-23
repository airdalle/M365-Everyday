L'outil "Recherche de contenu" permet d'effectuer des recherches à partir de requêtes sur du contenu "at rest", c'est à dire déjà existant dans l'environnement du client. Il ne permet **pas** de récupérer des informations sur des données "en transit", càd en temps réel (pour cela, il faut utiliser l'outil Data Loss Prevention -> voir la documentation associée).

### Interface utilisateur
![image.png](/.attachments/image-48a8a2af-e1e8-462c-b352-fb2092f2ce90.png)
On voit que l'écran propose deux onglets : **Search** et **Export**
**Search** : c'est là que l'on lance les recherches
**Export** : c'est là que l'on récupère les résultats des recherches que l'on a choisi d'exporter (en format csv)


### Construire des requêtes pour effectuer une recherche
[Documentation Microsoft sur l'outil](https://docs.microsoft.com/en-us/microsoft-365/compliance/content-search?view=o365-worldwide) : pas à pas pour créer une requête
[Documentation indispensable](https://docs.microsoft.com/en-us/microsoft-365/compliance/keyword-queries-and-search-conditions?view=o365-worldwide) pour comprendre comment construire les requêtes 

Attention à bien comprendre à quoi correspondent les différentes propriétés de document et d'email (exemple : propriété _FileName_ et propriété _Title_ à ne pas confondre !)

### Générer des statistiques de recherche et les analyser

Exemple d'écran affiché pour une recherche lancée (et ici terminée/arrivée à expiration, qui devrait donc être relancée pour obtenir des résultats actualisés) : on remarque deux onglets "Récapitulatif" et "Statistiques de recherche"
![image.png](/.attachments/image-4d9a1cdd-d005-4a35-8855-2e326f3a9d82.png)
Si l'on clique sur le bouton "**Exemple de révision**", on aura accès à un aperçu des résultats de recherche. C'est particulièrement utile lorsque l'on souhaite vérifier que la requête ressorte bien les résultats attendus. On voit vite si les résultats récupérés sont accurates ou si la requête génère trop de faux positifs (auquel cas il faudra la reconfigurer). 
Il est important de comprendre que l'outil ne récupère que ce qu'on lui demande de chercher, tout dépend donc de la requête configurée à la base. Il est très souvent nécessaire de procéder par itération jusqu'à obtenir le résultat souhaité. Penser à demander au client d'être présent lorsque l'on passe en revue ces recherches, c'est lui le mieux placé pour savoir si le résultat est satisfaisant au vu des données recherchées.

En cliquant sur le bouton "**Action**", on peut choisir (entre autres) d'exporter les résultats, càd les documents identifiés par l'outil comme correspondants à la requête :
![image.png](/.attachments/image-8384c969-7372-41dd-931e-fc5dae239a89.png)
On retrouvera ces résultats dans l'onglet **Export**.

On peut aussi choisir d'exporter un rapport simple, qui pourra être utilisé pour des statistiques.
![image.png](/.attachments/image-374a6874-833c-47d0-9598-7fd0bc76701f.png)

Exemple de rapport (anonymisé car données client) :
![image.png](/.attachments/image-f7da9f0f-2064-48f8-9943-e75317c56279.png)

Si l'on clique sur l'onglet "**Statistiques de recherche**", on obtient des résultats assez high level sur le nombre de sites concernés et les principaux emplacements (càd les sites présentant le plus de résultats) :
![image.png](/.attachments/image-3232e2c0-f6ee-46d5-9054-d75d14151f7f.png)
Là aussi, il est possible de télécharger le rapport (en format csv)
![image.png](/.attachments/image-b9f23fd3-346e-4271-9ea7-caa18285cce3.png)