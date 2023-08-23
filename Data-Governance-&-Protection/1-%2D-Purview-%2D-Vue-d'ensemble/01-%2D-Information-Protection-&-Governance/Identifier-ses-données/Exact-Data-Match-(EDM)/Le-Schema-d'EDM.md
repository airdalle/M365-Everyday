#Schema d'EDM
Une fois que les données sont bien formalisées et que les types de données primaires ont été choisis, il faut créer le schéma.
Il s'agit d'un fichier .xml qui contient toutes les informations nécessaires et complémentaires à la source de données.

##Utilisation de l'utilitaire de création des schémas EDM
Il est possible de générer / modifier ce schéma avec l'utilitaire du Compliance center. Cela n'empêche pas ensuite de le modifier à la main.
![image.png](/.attachments/image-46eec0e4-c0ab-405f-9084-f9526359e33f.png)

L'utilitaire permet notamment de rentrer chacun des champs de la source de données.
![image.png](/.attachments/image-7b75c6b9-d98e-4297-b24a-5c1299e8e0dc.png)

##Utilisation de powershell pour importer / exporter les schémas EDM
Le schéma n'étant rien de plus qu'un fichier XML, il est possible de l'exporter pour le travailler sur son poste.

*Exportation du schéma avec Powershell :*
```
$Schema = Get-DlpEdmSchema -Identity "[your EDM Schema name]"
Set-Content -Path ".\Schemafile.xml" -Value $Schema.EdmSchemaXML
```

*Créer un schéma en important le fichier .xml avec Powershell :*
```
New-DlpEdmSchema -FileData ([System.IO.File]::ReadAllBytes('.\\edm.xml')) -Confirm:$true
```

*Construction du schéma :*

Voir la documentation.

**Documentation**
- Documentation générale sur la page : https://docs.microsoft.com/en-us/microsoft-365/compliance/sit-get-started-exact-data-match-create-schema?view=o365-worldwide#create-the-schema-for-exact-data-match-based-sensitive-information-types
- Se connecter au centre de compliance avec Powershell : https://docs.microsoft.com/en-us/powershell/exchange/connect-to-scc-powershell?view=exchange-ps