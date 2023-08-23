#Hash et upload des données

##Guide
Suivre ces procédures :
- Créer un groupe de sécurité dans le tenant, nommé **EDM_DataUploaders**. Ajouter les users.
- Récupérer l'agent d'upload EDM correspondant :

    Commercial + GCC - most commercial customers should use this (https://go.microsoft.com/fwlink/?linkid=2088639)
    GCC-High - This is specifically for high security government cloud subscribers (https://go.microsoft.com/fwlink/?linkid=2137521)
    DoD - this is specifically for United States Department of Defense cloud customers (https://go.microsoft.com/fwlink/?linkid=2137807)

- Si le hash et l'upload ont lieu sur deux machines différentes : https://docs.microsoft.com/en-us/microsoft-365/compliance/sit-get-started-exact-data-match-hash-upload?view=o365-worldwide#separate-hash-and-upload (Conseillé)
- Si le hash et l'upload ont lieu sur la même machine : https://docs.microsoft.com/en-us/microsoft-365/compliance/sit-get-started-exact-data-match-hash-upload?view=o365-worldwide#hash-and-upload-from-one-computer

- Ensuite, il est possible de créer l'EDM SIT en suivant les instructions de cette page :  https://docs.microsoft.com/en-us/microsoft-365/compliance/sit-get-started-exact-data-match-create-rule-package?view=o365-worldwide
Note : le SIT est une entité différente du schéma et de la collection de données sensibles.
On peut imaginer avoir plusieurs SIT, avec différents patterns, pour un même schéma, par exemple.

## Bonnes pratiques
1. Au vu de la sensibilité des données pouvant être traitées, **il conseillé de ne pas exposer à Internet la machine qui s'occupe du traitement des données sources de l'EDM.** Le hash va nécessiter de les stocker sur la machine, et puisque l'EDM est susceptible d'être mis à jour de manière dynamique, cette machine pourrait être souvent sollicitée.
Ainsi, il convient d'effectuer l'action de hash sur une machine isolée, qui n'est pas en capacité de se connecter à Internet et donc au centre de Compliance, et d'effectuer l'Upload sur une autre machine après avoir récupéré les empreintes.

2. Avant de lancer l'opération de hash, il est important de vérifier les éventuelles erreurs de formatage du fichier (présence de caractères spéciaux notamment virgules, ...)
```EdmUploadAgent.exe /ValidateData /DataFile [data file] /Schema [schema file]```
