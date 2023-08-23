### Guide de configuration des Jobs dans le portail Purview:
Le **Job** doit être paramétré de sorte à :

- Préciser le label par défaut attribué aux fichiers si nécessaire
- Préciser l'application de règles DLP pendant le scan (voir ci après)
- Autres options à retrouver ci dessous :

![image.png](/.attachments/image-69578de5-5f77-4297-a7d6-da82a5c18297.png)

L'application de Policies DLP permettra au scanner d'identifier les fichiers dont le partage sur un disque réseau constitue une violation des stratégies DLP en place, ainsi que de mettre en place des actions de remédiation :
`When your DLP rules are enabled, the scanner may reduce file access to data owners only, or reduce exposure to network-wide groups, such as Everyone, Authenticated Users, or Domain Users.`
Voir : https://learn.microsoft.com/en-us/azure/information-protection/deploy-aip-scanner-configure-install?tabs=azure-portal-only#use-a-dlp-policy

Les **Repositories** quant à eux représentent les différents lieux à scanner. Il peut s'agir :
- D'un répertoire réseau, à renseigner ainsi : \\Server\Folder.
- D'une librairie SharePoint : http://sharepoint.contoso.com/Shared%20Documents/Folder.
- D'un répertoire local : C:\Folder
- D'un path UNC : \\Server\Folder
![image.png](/.attachments/image-a9212c6f-ead5-49f9-abbc-84192dd1427f.png)

