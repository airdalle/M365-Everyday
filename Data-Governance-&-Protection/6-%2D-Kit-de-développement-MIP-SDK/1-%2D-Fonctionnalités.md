# Fonctionnalités du MIP SDK
Le MIP SDK exploite trois APIs différentes :

## Protection API
![image.png](/.attachments/image-0b59e2b0-fa15-43a3-b717-263006ad9f90.png)
L'API de Protection concerne **les fonctions de chiffrement** liées aux Etiquettes de Sensibilité.
Elle prend en entrée des buffers / streams d'octets, et retourne des buffers / streams d'octets. 

L'API peut appliquer un chiffrement ou déchiffrer un flux d'octets. Lors de l'utilisations de cette API, cela peut être au développeur de s'assurer que l'utilisateur de son application est en droit de déchiffrer / chiffrer le contenu !

**Cas d'usages :**
- Appliquer un chiffrement à un format office ou non office
- Vérification d'un contenu chiffré en transit
- ...

[Documentation (C++)](https://learn.microsoft.com/en-us/information-protection/develop/concept-handler-file-cpp)

## Policy API
![image.png](/.attachments/image-5daf141e-e033-4fda-8841-0be49498be1c.png)
Cette API concerne les **stratégies des étiquettes de protection**. C'est l'API qu'on utilisera pour lister les labels et connaître les actions à utiliser pour tel ou tel fichier, selon l'utilisateur.
Elle prend en entrée un "Execution State" et sort une liste d'Actions à mettre en oeuvre.

L'API ne contient aucune fonction permettant d'analyser le contenu d'un document.
La mise en place des Actions est à mettre en place par le développeur.

**Cas d'usages :**
- Application étiquetant du contenu
- Lecture et reconnaissance d'étiquettes de sensibilité
- ...

[Documentation (C++)](https://learn.microsoft.com/en-us/information-protection/develop/concept-handler-policy-cpp)

## File API
![image.png](/.attachments/image-857aeaec-d824-45e9-9fe7-94a648c1bbe5.png)

**L'API des fichiers conjugue les deux autres APIs, elle est la combinaison, la somme des deux.**
Elle prend en entrée des fichiers, et rend en sortie des fichiers.

Cette API est celle qu'on utilisera pour appliquer des étiquettes sur des fichiers, par exemple.

**Cas d'usages :**
- Application de génération de documents
- Application de type "Scanner", CASB...

[Documentation (C++)](https://learn.microsoft.com/en-us/information-protection/develop/concept-handler-protection-cpp)