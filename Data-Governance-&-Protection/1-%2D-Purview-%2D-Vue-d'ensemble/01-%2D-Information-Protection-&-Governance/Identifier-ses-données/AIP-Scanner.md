_Note : La fonctionnalité de l'AIP Scanner est en cours d'évolution à l'heure actuelle par Microsoft. La feature sera prochainement renommée Microsoft Purview Information Protection Scanner, et l'implémentation du portail au sein du portail Purview est encore en cours._

# Azure Information Protection Scanner
Pour découvrir et labeliser des documents sur :
- Disque Windows
- Disque réseau
- SharePoint On Premise

Il est possible d'utiliser le scanner, qui parcourra ces différents emplacements pour remonter ces informations au portail Purview.

![image.png](/.attachments/image-efef8d8d-edf7-4f1c-999f-622b90aad814.png)

Le portail est accessible via Purview :

![image.png](/.attachments/image-23e8f308-a413-46bf-a464-0ad2092c9fe6.png)

## Installation du Scanner

Les conditions matérielles et logicielles à l'installation sont les suivantes :
- 4 core processors
- 8 GB RAM
- 10-GB free space
- OS :
Windows Server 2019 64 bits OR
Windows Server 2016 64 bits OR
Windows Server 2012 R2 64 bits

- Accès à Internet
- Support des NFS Shares si pertinent

L'installation passe par les étapes suivantes :
- Intallation d'un serveur SQL (SQL Express fait l'affaire, disponible sur le site de MS) 
- Installation d'Office iFilters et du client Azure Information Protection (disponibles sur le site de MS)
- Installation du module Powershell "AIPService" (`Install-Module AIPService`)

Il est possible, si tout a été correctement installé, de vérifier la présence du service "Azure Information Protection Scanner" dans les services de la machine.
![image.png](/.attachments/image-b6148e49-c971-4815-ac17-e4dccd6ac344.png)

Pour une installation dans un contexte différent (pas d'accès à Internet par exemple), se référer aux différents scénarios de la documentation :

https://learn.microsoft.com/en-us/azure/information-protection/deploy-aip-scanner-prereqs#restriction-the-scanner-server-cannot-have-internet-connectivity

Traditionnellement, le scanner doit être installé sur une machine physique ou virtuelle intégrée dans le réseau On Premise. **La machine doit être reliée à l'Active Directory local** (ou à un Azure Active Directory Domain Service dans le cas d'une VM Azure), et **utiliser un compte de service AD lui même synchronisé dans l'AAD du Tenant** du portail Purview.

Attention à bien donner les accès suivants au compte de service dans l'AAD :
- Compliance Administrator
- Accès à la connexion de la machine / VM

## Configuration Tenant et Scanner
Dans le portail, on crée un Cluster (= scanner) et on lui assigne des "jobs" qui sont les différentes analyses de contenu que l'on va pouvoir exécuter (en prenant en compte les policy DLP, en choisissant un labeling par défaut...)

Premièrement, on crée donc ce **Cluster** en précisant un nom qui permet d'identifier la machine sur laquelle on a installé le scanner.

![image.png](/.attachments/image-1e79ae23-3134-4ebc-bcd4-c79455beab88.png)

On crée ensuite un **Job**, voir [la page correspondante de ce wiki](https://lyon-devops.coexya.eu/tfs/Swl-DA/Data%20Gov%20et%20Protection/_wiki/wikis/Data-Gov-et-Protection.wiki?wikiVersion=GBwikiMaster&pagePath=%2FData%20Governance%20%26%20Protection%2F1%20%252D%20Capacit%C3%A9s%20MIP%20%252D%20Vue%20d%27ensemble%2F01%20%252D%20Information%20Protection%20%26%20Governance%2FIdentifier%20ses%20donn%C3%A9es%2FAIP%20Scanner%20%252D%20Discover%20and%20label%20files%20on%20premise%2FAIP%20Scanner%20%252D%20Configuration%20Jobs&pageId=304) pour plus d'informations.

Une fois ces tâches faites, le portail Purview est configuré pour traiter la donnée, il faut désormais **connecter la machine via une inscription d'application dans Azure Active Directory**.
Le workflow à suivre dans son intégralité (notamment le réglage des permissions) peut être retrouvé à ce lien :
https://learn.microsoft.com/en-us/azure/information-protection/rms-client/clientv2-admin-guide-powershell#create-and-configure-azure-ad-applications-for-set-aipauthentication

Enfin, à partir de la machine, on requête un token à l'aide de ces commandes :
```
$pscreds = Get-Credential <Domain>\<Service account name> (i.e CONTOSO\scanner)
Set-AIPAuthentication -AppId <Application app ID> -AppSecret <Application secret> -DelegatedUser <Service account email adress> -TenantId <Tenant Id> -OnBehalfOf $pscreds
```

Si tout s'est bien déroulé suite à cela, après un certain temps, un **Node** est apparu dans le portail de Purview :

![image.png](/.attachments/image-362ac219-4b99-4ca2-9e8f-34a52162c3c9.png)

Il doit notamment être possible de lancer des scans sur la page des Jobs en sélectionnant le job précédemment créé et en cliquant sur "Scan Now"

## Scan et Analyse
- Todo

## Troubleshooting Installation
Dans Powershell, les commandes suivantes permettront d'avoir une idée d'où peut se situer un problème d'installation :
```
$scanner_account_creds= Get-Credential <Domain>\<Service account name> (i.e CONTOSO\scanner)
Start-AIPScannerDiagnostics -onbehalf $scanner_account_creds
```

En fonction de ce qui est retourné, se référer à cette page :
https://learn.microsoft.com/en-us/azure/information-protection/deploy-aip-scanner-tsg