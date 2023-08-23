[[_TOC_]]
**Ne fonctionne pas sur Exchange à l'heure actuelle.**

# Comment créer une requête Content Search avec un Sensitive Information Type ?
Il est intéressant, dans le centre de Compliance, de chercher les documents liés à un certain type d'information sensible. Pour ce faire, on peut créer des requêtes Content Search 
**Attention :** il faut utiliser le mdoule Content Search et non le module eDiscovery.
Pour ce faire, il faut créer une requête dans un cas d'usage, et régler ainsi

## 1. Attention à bien avoir réglé les permissions avec eDiscovery : 
Votre compte doit être eDiscovery Manager ou eDiscovery Administrator. Si vous ne l'êtes pas, contactez votre administrateur.
![image.png](/.attachments/image-5f0eb8d5-b43b-4a26-aa00-5127c70119d1.png)

## 2. Choisir les localisations qui nous intéressent.
![image.png](/.attachments/image-726e430e-a9a8-48db-ab85-ea179af8fd1b.png)
**Attention :** certaines localisations, notamment Exchange, ne peuvent pas être utilisées pour la recherche via SIT. Cf Microsoft :
`You can't use sensitive information types and the SensitiveType search property to search for sensitive data at-rest in Exchange Online mailboxes. This includes 1:1 chat messages, 1:N group chat messages, and team channel conversations in Microsoft teams because all of this content is stored in mailboxes. However, you can use data loss prevention (DLP) policies to protect sensitive email data in transit.`

## 3.  Remplir les conditions ainsi, dans la fenêtre Keyword et dans le cas d'un SIT builtin
`SensitiveType:"<nom_du_SIT>"` 
**Attention :** Si vous utilisez un SensitiveType custom, indiquer son nom ne fonctionnera pas. Il vous faudra nécessairement indiquer la ligne suivante :
`SensitiveType:<GUID_du_SIT>` (Récupération du GUID via Powershell, voir cmdlet `Get-DlpSensitiveInformationType`)
On peut inclure plusieurs avec "OR", "AND", etc. Exemple :
![image.png](/.attachments/image-07dec35f-c401-41c3-8de9-7dfa7059a10a.png)
Pour plus de détails sur les options de SensitiveType : https://docs.microsoft.com/en-us/microsoft-365/compliance/form-a-query-to-find-sensitive-data-stored-on-sites?view=o365-worldwide

## 4. Construire des requêtes plus complexes

Pour rajouter des filtres aux requêtes, il n'est pas possible d'utiliser les termes "classiques" de KQL.
La liste est disponible ici :
https://learn.microsoft.com/en-us/archive/blogs/quentin/using-search-properties-and-operators-with-ediscovery

Il faut construire la requête exclusivement dans la fenêtre "Keywords" du Content Search et cliquer sur "Keep query" à la sauvegarde.

![image.png](/.attachments/image-5a5516d2-6fd0-420c-aefb-7ec5c9ddf7bd.png)

Exemple de requête :
_SensitiveType:"Credit Card Number" OR SensitiveType:"International Banking Account Number (IBAN)" OR SensitiveType:"EU Debit Card Number" (c:c) Created<2020-04-01_