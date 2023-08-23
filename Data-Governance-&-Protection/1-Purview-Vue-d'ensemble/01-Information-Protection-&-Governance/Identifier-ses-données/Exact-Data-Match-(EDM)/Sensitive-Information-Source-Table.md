#Définition des données source
L'EDM vise à détecter des données précises dans les documents. Il faut donc fournir en amont ces données pour créer le SIT.

_Note : Ce qui est comparé côté Microsoft, **ce sont les empreintes des valeurs**, et non pas les valeurs directement. De fait, on peut utiliser des données extrêmement sensibles, cela ne sortira jamais et Microsoft ne pourra jamais en avoir connaissance au niveau du moteur de comparaison EDM._

## Structure des données
Les données sources doivent être fournies sous la forme d'un fichier .csv, .tsv ou un format .txt séparant les différentes colonnes (fields) par des caractères | (pipes).
Ces données doivent suivre les contraintes suivantes :
- Pas plus de 100 millions de lignes de données sensibles,
- Pas plus de 32 colonnes par source de données,
- Pas plus de 5 colonnes marquées comme "searchable",
- La première ligne contient les noms des colonnes (par ex : firstname, lastname, birthdate...),
- Il est recommandé d'utiliser le format .tsv ou d'encadrer les valeurs contenant des virgules : en effet, en .csv, une valeur avec une virgule serait parsée comme deux valeurs différentes.

## Les Champs primaires (Primary Elements)
Pour repérer les données sensibles dans l'abondance de données disponibles, Microsoft demande de choisir des "Primary Elements". Il s'agit de champs qui peuvent être **cherchés à l'aide d'un pattern**, comme une regex par exemple.
Ces champs doivent être taggés dans le schéma comme "**Searchable**", c'est à dire qu'ils peuvent être utilisés pour identifier le Primary Element.

Il s'agit d'une "limitation" (nécessaire) de ce SIT. On ne peut pas chercher simplement une liste de valeurs, au vu du nombre de valeurs et de documents à analyser. Il faut donc avoir en support de l'EDM une des données qui puisse être trouvée par un pattern d'analyse plus classique.

_Exemple : Si on a des colonnes "Nom, date de naissance, account number, numéro de sécurité sociale", alors le primary element le plus naturel serait de choisir le numéro de sécurité sociale ou le numéro de compte._

Il s'agit d'un choix crucial à faire en amont de la création d'un EDM.

Pour des raisons de performance, **ce pattern ne doit pas être trop vague** (un mot, une adresse mail, un numéro de téléphone... Tout ceci est beaucoup trop commun dans les données et va retourner bien trop de correspondances), et au contraire être **aussi restrictif et précis que possible**.

La meilleure solution serait de choisir comme Primary Element **une donnée classifiable par un SIT bien configuré**, avec des Additional Evidences et un pattern suffisamment précis. Les SIT Built-in sont très bons pour cela. Ce SIT peut aussi être basé sur un dictionnaire de mots clés.

S'il n'est pas possible de restreindre le pattern ou d'exiger des additional evidences, alors on peut se rabattre sur une autre solutions : **augmenter le nombre de matches nécessaires** dans une certaine proximité. 
_Par exemple, on choisir comme Primary Element un account number qui est un nombre à 5 chiffres. On ne veut pas mettre d'additional evidences. Dans ce cas, on précise que l'on ne veut un match que si il y a x occurences de ce pattern avec une proximité de y caractères._

**Documentation**
- **https://docs.microsoft.com/en-us/microsoft-365/compliance/sit-get-started-exact-data-match-export-data?view=o365-worldwide#export-source-data-for-exact-data-match-based-sensitive-information-type**