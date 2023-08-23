[[_TOC_]]

# Problème rencontré
Pour démarrer l'enrôlement des postes de travail et activer le endpoint DLP, il faut activer cela depuis les paramètres du centre d'administration de MS Purview (https://compliance.microsoft.com/compliancesettings)
Il est possible que cette étape ne se passe pas comme prévu (cf. dernière capture d'écran)
> ![image.png](/.attachments/image-8a6c181d-01a7-4fc9-99be-9310fae1bae5.png)

> ![image.png](/.attachments/image-9e2c3729-686b-4d6b-bf49-e5ef9e338f00.png)

>![image.png](/.attachments/image-1b371ca9-8c18-473e-b8e9-fbc077cf1517.png)

> ![image.png](/.attachments/image-59ba3326-3310-4a97-a493-00ca01a68396.png)

> ![image.png](/.attachments/image-643c5544-c7ff-4e6a-b8da-d26e73c29250.png)

# Solution fournie par Microsoft
- [x] Cette solution a été testée avec succès
1. Avec un compte de type Administrateur global, aller sur Azure Active Directory (https://aad.portal.azure.com/)
2. Créer un groupe de sécurité "PurviewDeviceOnboarding" (par exemple)
3. Ajouter à ce groupe le compte O365 qui sera administrateur global du tenant ET qui sera utilisé pour l'administration de Microsoft Purview
4. Une fois le compte ajouté, assigner un rôle à ce groupe de sécurité : "Compliance Administrator"
>![image.png](/.attachments/image-5a17fd6d-75c3-45ba-8800-4b36a2c16223.png)
5. Attendre 24 à 48h
6. Retourner dans les paramètres du centre d'administration de Microsoft Purview (https://compliance.microsoft.com/compliancesettings)
7. En cliquant sur "Device Onboarding", la page devrait désormais s'afficher comme suit :
> ![image.png](/.attachments/image-9440b6da-d0b6-4d92-bbde-9ec2d9bc3f4b.png)
8. Puis comme suit
> ![image.png](/.attachments/image-59ae86f7-8457-4cd7-a39a-4bff2cdc6f78.png)

