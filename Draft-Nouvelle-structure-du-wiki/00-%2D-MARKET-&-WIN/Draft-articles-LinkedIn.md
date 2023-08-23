[[_TOC_]]

# A1 - Dark Data & Data Discover
## §1
Le terme "Dark data" est utilisé pour décrire les grandes quantités de données non structurées que les organisations génèrent et collectent, mais n'utilisent pas ou ne gouvernent pas efficacement. Ces données peuvent inclure des éléments tels que de vieux e-mails, des fichiers inutilisés, voire des conversations instantanées.

Si les "Dark data" peuvent ne pas représenter un problème au premier abord, elles peuvent en fait représenter un risque important pour les organisations. Elles peuvent contenir des informations sensibles, telles que des données personnelles ou des informations commerciales confidentielles, auxquelles des parties non autorisées pourraient avoir accès, et qui pourraient être utilisées à des fins malveillantes. En outre, les "Dark data" peuvent également exposer les organisations à un risque de non-conformité.
Par exemple, si une organisation est tenue de conserver certaines données pendant une certaine période, mais qu'elle n'a pas connaissance de ces données parce qu'il s'agit de "Dark Data", elle pourrait être en infraction avec la réglementation.

## §2
La découverte des données sous-entend de savoir identifier une donnée, et son éventuelle sensibilité, selon un modèle de données préétabli.

Un processus de découverte des données se déroule selon les étapes suivantes :

1. Définissez les types de contenu sensible que vous recherchez. Il peut s'agir de données personnelles, d'informations commerciales confidentielles ou d'autres types de données sensibles.

2. Utilisez des outils de classification des données : Une fois que vous avez défini les types de contenu sensible que vous recherchez, vous pouvez utiliser des outils de classification des données pour identifier ce contenu dans vos dark data. Ces outils utilisent par exemple des expressions régulières, des dictionnaires de mots-clés, et même des algorithmes d'apprentissage automatique pour classer automatiquement les données en fonction de catégories prédéfinies, et peuvent vous aider à identifier rapidement et efficacement le contenu sensible dans de grands volumes de données.

3. Utilisez un outil d'exploration des données : une fois que vous avez défini les bons modèles pour trouver le contenu sensible, laissez le système rechercher le contenu qui correspond à ces modèles et identifiez où se trouve ce contenu.

4. Utiliser un outil d'étiquetage des données : toujours sur la base des modèles de contenu sensible que vous avez mis en place, exécutez un processus d'étiquetage automatique du contenu. Pour ce faire, vous devez également avoir défini et configuré un ensemble d'étiquettes, en précisant pour chacune d'entre elles le modèle de contenu sensible à identifier.

# A2 - Advanced Data Classification with Trainable classifier
## Qu'est-ce qu'un trainable classifier ?
Un " trainable classifier " est un algorithme de machine learning conçu pour classer automatiquement des données en fonction de catégories prédéfinies. Un "trainable classifier" fonctionne en analysant un ensemble de données d'entrainement qui comprend des exemples de chaque catégorie de classification. En analysant ces données, le système apprend à classer les nouvelles données en fonction des catégories définies.

Les " Trainable classifiers " peuvent être utilisés pour un large éventail d'applications, telles que l'identification des courriers électroniques indésirables, la reconnaissance des images et l'identification des données sensibles dans les dark data. Ils sont généralement plus précis et plus efficaces que la classification manuelle, et peuvent aider les organisations à rapidement et facilement découvrir et gérer des données sensibles.

Dans l'ensemble, un "trainable classifier" est un outil puissant qui permet de classer automatiquement des données et de découvrir des informations qu'il serait difficile, voire impossible, de trouver par des méthodes manuelles. En utilisant des algorithmes d'apprentissage automatique et des données d'entraînement, les "trainable classifiers" peuvent aider les entreprises à améliorer leurs pratiques de gouvernance et de gestion des données, et à libérer la valeur commerciale de leurs données.

## Comment créer un trainable classifier personnalisé ?
Pour créer un "trainable classifier" personnalisé, vous devez d'abord définir les catégories de classification que vous souhaitez couvrir. Par exemple, vous pouvez créer des catégories pour les données personnelles, les informations commerciales confidentielles et les données publiques.

Ensuite, vous devez rassembler des données d'entraînement. Celles-ci seront utilisées pour entraîner le système et lui apprendre à classer correctement les données. Les données d'entraînement doivent comprendre des exemples représentatifs des types de données que vous souhaitez classer.

Une fois que vous avez rassemblé et utilisé les données d'entraînement pour créer le "trainable classifier", vous devez fournir des données de validation pour tester le modèle. Cela permettra d'affiner la précision de la détection du contenu avec le moins de faux positifs et de faux négatifs possible.

Une fois la précision du classificateur validée, vous pouvez le déployer pour classer, ou étiqueter, automatiquement votre contenu. Cela peut vous faire gagner du temps et des ressources par rapport à une classification manuelle, et peut vous aider à identifier rapidement et efficacement les données sensibles dans votre paysage de dark data.

## Comment démarrer au plus simple avec les trainable classifier ?
Microsoft Purview comprend un ensemble de "trainable classifier" intégrés que vous pouvez utiliser pour classer vos données, sans avoir à créer un "trainable classifier" personnalisé.

