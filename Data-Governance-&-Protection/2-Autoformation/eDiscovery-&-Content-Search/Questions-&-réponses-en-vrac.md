[[_TOC_]]
# **Quelle est la différence entre Content Search et eDiscovery ?**
Content Search et eDiscovery utilisent le même moteur de recherche pour chercher, dans les contenus Office 365, des mots clés, SIT, etc.
En revanche, ils ne répondent pas à la même exigence. eDiscovery est un outil plus complet, contenant des fonctionnalités comme des litigation holds, qui est utile pour remplir les exigences de "eDiscovery", un procédé juridique précis lorsque l'on veut prouver que l'on a ou n'a pas tel document à un tribunal (Discover and Respond).

Ce sont des exigences juridiques assez précises et complexes à maîtriser. Dans l'écrasante majorité des cas, on se contentera de Content Search et on ne touchera pas à eDiscovery.
Plus d'informations à [03 - Discover & Respond](https://lyon-devops.coexya.eu/tfs/Ids-TAndC/Base%20de%20connaissance%20G%C3%A9n%C3%A9rale/_wiki/wikis/Base-de-connaissance-G%C3%A9n%C3%A9rale.wiki?pagePath=%2FSommaire%2FCompliance%20et%20S%C3%A9curit%C3%A9%2F1%20%252D%20Capacit%C3%A9s%20MIP%20%252D%20Vue%20d'ensemble%2F03%20%252D%20Discover%20%26%20Respond&wikiVersion=GBwikiMaster&pageId=195).

# **Comment créer une requête Content Search pour chercher des Sensitive Information Type dans le contenu O365 ?**
Voir [Créer requête eDiscovery avec SIT](https://lyon-devops.coexya.eu/tfs/Ids-TAndC/Base%20de%20connaissance%20G%C3%A9n%C3%A9rale/_wiki/wikis/Base-de-connaissance-G%C3%A9n%C3%A9rale.wiki?pagePath=%2FSommaire%2FCompliance%20et%20S%C3%A9curit%C3%A9%2FTips%20and%20tricks%2FContent%20Search%20avec%20SIT&wikiVersion=GBwikiMaster&pageId=306).

# **A quel niveau de granularité sommes-nous capables de distribuer les rôles d’investigation dans eDiscovery Premium ?**
Aujourd'hui, il est possible de définir un "staff" différent par case, ainsi, inclure des personnes sur un seul case si leur aide est requise.
Toutefois, ces personnes auront accès à l'ensemble des collections, review sets et communications liées à ce case. Ainsi, par exemple, dans le cas d'un déontologue qu'on voudrait n'impliquer que sur certains review sets, le principe du moindre privilège ne peut être respecté.

Il est prévu qu'une distribution plus granulaire des rôles entre en Preview au moment où ces lignes sont écrites (janvier 2023) : _“A feature for reviewer capabilities for guest users”_.
Plus d'infos à suivre donc.

# **Si des procédures de rétention ou de suppressions de contenu sont activées, vont-elles supprimer les données pendant l’enquête ?**
« Custodians » et « sources non custodians » peuvent être placées « on litigation hold » et rien ne sera supprimé. 

_"A litigation hold can manually be placed on a user's mailbox so that nothing is deleted by anyone or any automated process (such as a retention policy)"_

# **Comment optimiser l’exportation des résultats afin d’accélerer le processus d’exploitation et de production de rapport ?**
Plusieurs formats d'exports sont disponibles au sein d'eDiscovery Premium.
![image.png](/.attachments/image-c5d7f171-76ad-445c-9daf-459ea714b45d.png)
- "Report Only" ne concerne qu'une liste des données au format .csv
- "Loose files and PSTs" va fournir des archives Exchange au format .pst. Les pièces jointes sont dans ce dossier.
- "Condensed Directory Structure" fournit les messages au format .msg avec les pièces jointes directement dans les messages : plus facile pour la visualisation des données. Sous cette forme, il est possible d'upload automatiquement ces données à un compte de stockage Azure.
![image.png](/.attachments/image-a42210fa-c092-4e43-bf17-05c9ee0fffea.png)
![image.png](/.attachments/image-9597d9b6-0c01-4b64-9b88-c329cdeba519.png)

# **Comment chercher un fichier dont on ne connaît pas l’auteur / expéditeur ?**
Dans eDiscovery Premium, les Cases prennent comme source de données des Custodians (ou des sources non custodianes que l'on déclare comme des sites SharePoint).
Ainsi, ce n'est pas l'outil à utiliser pour ce genre de requête, on se penchera plutôt sur Content Search ou eDiscovery Standard s'il y a une nécessité d'appliquer un Litigation Hold sur le résultat.