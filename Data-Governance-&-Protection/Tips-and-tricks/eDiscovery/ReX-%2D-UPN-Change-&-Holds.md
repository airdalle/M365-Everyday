[[_TOC_]]

# Qu'est-ce qu'un UPN Change ?
* https://learn.microsoft.com/en-us/sharepoint/upn-changes#types-of-upn-changes

# Quels impacts sur un espace OneDrive ?
* https://learn.microsoft.com/en-us/sharepoint/upn-changes#onedrive-url
  * l'espace OneDrive voit son URL changer, pour refléter le nouveau nom d'utilisateur et/ou le domaine

# Quels impacts pour un case eDiscovery ? (en date du 20/04/2023)
* L'emplacement (URL) OneDrive visé par le case n'est plus couvert par le case après changement d'UPN => il faut ré-ajouter manuellement l'espace OneDrive au case
* Si l'espace OneDrive est sous Hold au moment de l'UPN change, le Hold n'est pas impacté

* S'il s'agit d'un case eDiscovery Premium
  * Le custodian, placé sous hold ou non, n'est pas mis à jour avec les impacts suivants : 
    * la messagerie e-mail reste configurée dans le case
    * l'espace OneDrive n'est plus configuré dans le case
  * Il faut effectuer les modifications suivantes sur le case
    * Placer sous "temporary hold" le nouvel espace OneDrive et messagerie e-mail de l'utilisateur via l'ajout d'un "non custodial data" ou via l'onglet "Hold"
    * Faire un release sur le custodian
    * Réajouter le custodian en le sélectionnant via le nouvel UPN
    * Attendre une journée
    * Retirer le "temporary hold"




 