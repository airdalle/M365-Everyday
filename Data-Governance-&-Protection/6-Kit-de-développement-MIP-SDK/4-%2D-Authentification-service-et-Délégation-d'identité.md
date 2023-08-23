# S'affranchir de la connexion utilisateur en agissant par délégation d'identité
Pour s'affranchir de la connexion utilisateur, et utiliser le SDK via connexion par "service principal" / "application AAD", il y a plusieurs modifications à faire par rapport aux sections précédentes.

**Concernant la configuration de l’enregistrement d’application dans AAD :**
- Il faut rajouter à la partie « Authentification » l’URL suivante : http://localhost, comme dans la capture d’écran suivante 
![image.png](/.attachments/image-036b96e4-fc65-49ab-8a26-ecae8c3ae81f.png)
 
- Concernant les API Autorisées, puisque l’on passe à une authentification par le « Service Principal », il faut rajouter des permissions permettant à l’engine de lire et écrire au nom d’un utilisateur (voir https://learn.microsoft.com/en-us/information-protection/develop/concept-delegation).
Cela se traduit par les autorisations suivantes :
![image.png](/.attachments/image-9be2f908-2224-4a6d-8885-e5739d7e3bbb.png)
A noter que cela donne au programme la possibilité de voir tous les labels du tenant, publiés à l’utilisateur délégué ou non.

- Enfin, pour l’authentification comme service principal, il faut mettre en place une méthode d’authentification : soit un certificat, soit un secret client. Dans le code, on utilise un secret client, et on peut renseigner sa valeur par exempledans le appsettings.json :
 ![image.png](/.attachments/image-89a9fca1-15d2-49e5-acf5-2d43ecfc1150.png)


**Concernant le code du programme :**
- Avant d'instancier le FileEngine, on ajoute l'identité déléguée dans les paramètres du profil. On renseigne l'adresse mail de l'identité déléguée dans une variable (ici `user_identity`) puis on ajoute cette ligne :
![image.png](/.attachments/image-254ae232-de06-420d-8232-27ed7028ee4d.png)

- Il faut modifier les paramètres de protection pour bien utiliser une identité déléguée. On renseigne l'adresse mail de l'identité déléguée dans une variable (ici `user_identity`) et on ajoute cette ligne avant d'appliquer un label :
![image.png](/.attachments/image-5d4b2a8b-6d13-4fc7-ba64-1f0136eb194d.png)

- Une fois que tout ceci est fait, on peut changer la méthode d’authentification dans l’AuthDelegateImplementation : au lieu d’utiliser une PublicClientApplication, on utilise une ConfidentialClientApplication.
![image.png](/.attachments/image-fa6ff2c6-3bfb-4d87-b729-7a5efea077ab.png)
![image.png](/.attachments/image-5d9ee5f8-6fa2-4ee0-8e35-e868fcb2f9b9.png)
 

Ceci implique donc de passer au programme le Client Secret, que l’on n’utilisait pas avant. Pour ce faire, renseigner le appsettings.json fourni dans le code :
![image.png](/.attachments/image-78d65ab3-647d-4de3-a578-f059921f64eb.png)
