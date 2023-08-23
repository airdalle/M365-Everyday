[[_TOC_]]

Il est possible de bloquer le téléchargement de documents sensibles à partir d'Office 365 sur des postes de travail, en utilisant les fonctionnalités d'Azure AD et Microsoft Defender For Cloud Apps.

## Activer le Conditional Access App Control
Dans AAD, naviguer vers Azure AD Conditional Access :
![image.png](/.attachments/image-c7faf9dd-a723-4cbc-8c3d-13eb0fc1d5c8.png)

Créer une policy nécessite de spécifier :
- Les Utilisateurs concernés,
- Les applications concernées - sélectionner Office 365 dans notre cas,
- Les conditions qui déclencheront le blocage (ces conditions concernent le contexte du téléchargement : l'utilisateur a-t-il un User Risk / un Sign-In Risk trop élevé ? L'appareil est-il onboardé ? L'application est-elle accédée par Navigateur Web ou par Client Desktop ?...)
![image.png](/.attachments/image-9777f476-1f50-4c3c-a579-68a62b2caf48.png)

Une fois ces conditions mises en place, il faut spécifier :
- Les vérifications supplémentaires applicables pour accéder, dans un premier temps, à l'application
![image.png](/.attachments/image-1a8ecfd8-806b-4db5-9f82-3f36c4013c03.png)
- Les contrôles de **session**, qui régissent les actions que l'on va pouvoir faire durant la session. **C'est ce qui nous intéresse dans ce cas de figure.**
![image.png](/.attachments/image-e868a47c-53e0-46aa-be90-0205f39b7e00.png)

Cocher la case "Conditional Access App Control", et choisir si l'on veut :
- Monitorer uniquement
- Bloquer tous les téléchargements venant de l'application
- Spécifier une stratégie custom plus fine (incluant donc les politiques DLP de l'entreprise par exemple).

Une fois ces étapes terminées, il n'est plus nécessaire d'aller dans Azure Active Directory.

## Activer la protection Defender For Cloud Apps

Dans le portail Defender for Cloud Apps, accéder à ce menu :
![image.png](/.attachments/image-fae8f20e-3c83-4432-ad8b-0f00ab16de03.png)

Vous devriez voir, quelques minutes après les étapes précédentes, arriver les applications liées à Office. Si l'option "Onboard with session control" est présente, cliquez dessus et cochez la case "Use the app with session controls".
![image.png](/.attachments/image-2f1ef273-4a47-49ae-8a5c-28a21848e90b.png)
![image.png](/.attachments/image-d1b4ac7c-b2f9-45fc-886d-071a5c6366d5.png)

A partir de maintenant, toute nouvelle session se connectant à Office passera par un Proxy que l'on peut repérer en vérifiant l'adresse dans le navigateur.
![image.png](/.attachments/image-6ca20194-dbc3-4624-b93b-ec8a9dee3ace.png)

Si l'otion "Bloquer tous les téléchargements" a été sélectionnée, il n'y a plus rien à faire : les téléchargements dont la session correspond aux conditions spécifiées dans la section "Activer le Conditional Access App Control" sont tous bloqués.
![image.png](/.attachments/image-6c21f989-7d52-4280-8303-4db5978a6e92.png)

## Activer l'inspection des fichiers et la Prévention de Pertes de Données

Pour bloquer uniquement le téléchargement de contenus sensibles, il faut passer par une policy au sein de Defender for Cloud Apps.

Créez une Session Policy et utilisez le template "Block Download Based on Real-Time content inspection".
Spécifiez dans Activity Source l'application concernée par le blocage (en l'occurence Office 365).
![image.png](/.attachments/image-6b496d19-d21d-4a26-9af5-7792a8d659b7.png)

Voici en bref les options possibles lorsque l'on crée une stratégie de contrôle des téléchargements :
![image.png](/.attachments/image-4ab17a4c-3759-42ce-9bf7-2332f3eebd2d.png)

Exemple avec Data Classification Service :
![image.png](/.attachments/image-010f86ef-855e-4249-ab7e-47cd576d3d79.png)

Les actions pouvant être entreprises sont :
![image.png](/.attachments/image-a198b96f-1710-463e-86de-d9f61145a57b.png)
Appliquer un label peut être intéressant, par exemple pour chiffrer la donnée lors du téléchargement.

Avant de tester, attendez quelques minutes et démarrez une nouvelle session dans Office (déconnexion / reconnexion).

## Documentation

Pour les deux premières sections : [Doc MS](https://learn.microsoft.com/en-us/defender-cloud-apps/proxy-deployment-aad#configure-integration-with-azure-ad)
Pour la troisième section : [Doc MS](https://learn.microsoft.com/en-us/defender-cloud-apps/use-case-proxy-block-session-aad)