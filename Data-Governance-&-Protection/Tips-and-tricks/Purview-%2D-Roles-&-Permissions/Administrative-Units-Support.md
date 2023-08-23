#Administrative Units Support

Depuis peu, et en public Preview, Microsoft Purview supporte l'attribution de rôles Purview à des **Administrative Units** (AU).

Une AU est une division de l'annuaire AAD permettant de scinder une entreprise en plusieurs unités administrées par des profils spécifiques. En d'autre termes, l'administrateur d'une AU peut n'avoir des droits que sur son unité et pas sur les autres.

Cela s'applique donc désormais à Purview : un administrateur de conformité peut désormais n'être relié qu'à certaines AU et donc :
- Ne paramétrer que les stratégies spécifiques à son Unité.
- Ne voir que les alertes / contenus liés à son Unité.

Pour ce faire :
- Se rendre dans l'onglet des permissions de Purview
- Attribuer un utilisateur à un rôle
- Attribuer à cet utilisateur une Administrative Unit
![image.png](/.attachments/image-730c3371-1e5d-4801-a370-b63a5becc805.png)

Pour attribuer une DLP Policy à une AU uniquement, il s'agit de le spécifier dans la configuration de la stratégie :
![image.png](/.attachments/image-539b6f63-ef94-4063-9e08-4deb7b54e515.png)

##Remarque
Cette fonctionnalité n'est pas compatible avec PIM.
A l'heure actuelle, dans AAD, seuls quelques rôles peuvent être assignés à une Administrative Unit. La liste ne contient pas à ce stade les rôles liés au portail Purview.
![image.png](/.attachments/image-6e8b56a2-db64-430a-8e57-efc3e27e0058.png)
La seule option consiste donc à donner une attribution permanente à l'utilisateur via le portail Purview directement.