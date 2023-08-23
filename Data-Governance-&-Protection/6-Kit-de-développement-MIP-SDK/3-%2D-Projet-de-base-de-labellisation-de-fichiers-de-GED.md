# Projet de base
Dans le cadre du projet de PoC pour le groupe La Française, un prototype d'application d'étiquetage a été créé.
Le projet est développé en C#.

Il est accessible via ce lien : 
http://lyovgitlabins.coexya.lan/sjacquier/mip_sdk_scanner

Prenez garde à lire le Readme avant de tenter de lancer le programme.

## Composants du code
Le Programme utilise multiples composants :

### Authentification
Il est nécessaire d'authentifier un utilisateur du tenant autorisé à utiliser le label que l'on va vouloir appliquer.
On instancie un objet : AuthDelegateImplementation, avec les informations de l'application enregistrée dans l'AAD.
![image.png](/.attachments/image-f672c85b-ab11-42f1-b00d-24b269ccafe5.png)
Cet objet doit implémenter une fonction AcquireToken :
![image.png](/.attachments/image-b5cb313b-0449-4112-8a1f-c66186c7d43d.png)
Avec cet objet, l'application obtiendra les Tokens nécessaires pour authentifier les requêtes et permettre la labellisation, le chiffrement, etc.
![image.png](/.attachments/image-96708633-1ac3-4a73-8626-4d7a5e944e96.png)

### Helper d'étiquetage
Avant d'appeler le Helper implémentant les fonctions d'étiquetage, on doit instancier un FileEngine (en effet, on utilise le File API. A noter que chaque API du SDK a son propre engine : PolicyEngine et ProtectionEngine existent et s'instancient chacun d'une manière différente à voir dans la documentation)

![image.png](/.attachments/image-d2993147-ac0f-4617-b705-eb39bae8a65a.png)

Les actions d'étiquetage développées sont actuellement au nombre de deux :

- Récupération des étiquettes
![image.png](/.attachments/image-6f6f6e19-8fcd-4928-895d-e33b5de819ad.png)
- Application d'une étiquette
![image.png](/.attachments/image-6634efc6-d80e-4794-9619-3e0b17be0106.png)

**Important** : dans ce projet, on profite de la labellisation pour appliquer des métadonnées étendues custom au fichier, selon le type de fichier que l'on étiquette.
Il s'agit des lignes "labelingOptions.ExtendedProperties", qui donc appliquent ces métadonnées.
Pour plus d'informations sur ce point précis, [Cliquez ici](https://learn.microsoft.com/en-us/information-protection/develop/concept-mip-metadata#extending-metadata-with-custom-attributes).

### Helper SQL
Cette partie n'est pas liée au SDK en soi, mais liée au cas d'usage du projet.
Dans cette application, on labellise les fichiers qui sont recensés dans une base de données, SSI leur "SensitiveMode" est à 1.
Ce comportement réplique le cas d'une GED associée à une base de données descriptives des fichiers contenus dans la GED.

Dans le Readme, vous trouverez la table à inclure dans la base de données à connecter au programme si vous souhaitez conserver cette feature.
Auquel cas, il faudra aussi inclure la ConnectionString de votre base dans le fichier App.Config de l'application.
