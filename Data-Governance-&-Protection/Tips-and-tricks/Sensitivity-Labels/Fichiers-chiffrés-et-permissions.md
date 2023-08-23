[[_TOC_]]

# Abaques générales
>![image.png](/.attachments/image-dbbf6287-955c-4c67-bf98-8bbff798958e.png)

# Types de clés
https://techcommunity.microsoft.com/t5/security-compliance-and-identity/understanding-microsoft-information-protection-encryption-key/ba-p/2214589

# Gestion des flux réseaux - TRES IMPORTANT
https://learn.microsoft.com/en-us/microsoft-365/enterprise/urls-and-ip-address-ranges?view=o365-worldwide

# Azure RMS SuperUser
https://techcommunity.microsoft.com/t5/security-compliance-and-identity/using-azure-pim-for-the-aip-super-user-feature-management/ba-p/1587690
>![image.png](/.attachments/image-bfe4fa91-9a00-4a1e-add8-b090b4b32387.png)

# Azure RMS Logs
>![image.png](/.attachments/image-402c9b37-8035-41cb-b1c0-a4ead1c6d4b9.png)

# Gestion des clés
>![image.png](/.attachments/image-2c8530b3-4911-41a1-b792-eca896c36443.png)

> ![image.png](/.attachments/image-eea5e11a-a89c-4bc0-9365-d3f22b1516d4.png)

## Bring your Own Key

1. Génération des clés via HSM On Prem (mise en place d'un process qu'on nomme "Cérémonie des clés" avec un quorum, etc)
2. Backup de la clé, multiples copies réparties à divers endroits dans le monde, car matériau extrêmement sensible qui PEUT être perdu (impossible de les exporter d'Azure Key Vault)
3. Upload dans Azure Key Vault via "secure HSM to HSM transfer"
4. Autoriser RMS à utiliser la clé, Configurer RMS pour utiliser la clé comme clé active
5. Les données précédement chiffrées via MMK ne seront pas rechiffrées 

> ![image.png](/.attachments/image-8fb0f8f7-8681-40a8-8400-87b50e22d1eb.png)

> ![image.png](/.attachments/image-8c7fb237-b412-437e-a2c2-860239336c1b.png)

> ![image.png](/.attachments/image-b5b8a357-3668-4aa4-9bcf-20269f02d4bd.png)

> ![image.png](/.attachments/image-e85163ae-13cb-4a96-9501-4f9668f04035.png)

# DKE
## Illustrations
> ![image.png](/.attachments/image-35b10cb5-ef75-45bd-a6c3-058bafd8a1b9.png)

> ![image.png](/.attachments/image-cc0827f8-2a11-49bd-b81c-98b009dc0de0.png)
## Solution DoubleKey pour O365
https://duokey.com/products/duokey-for-office-365/

# Azure Key Vault - options possibles
> ![image.png](/.attachments/image-ca3e9af7-d678-482f-b96a-cdd59163a385.png)

# Question Yammer sur gestion des permissions
![image.png](/.attachments/image-5cf23646-e41b-48ba-9c85-2e974abbea3d.png)

# Réponse
## Réponse courte
>The highest privileges wins. The user always receives ONE end user license (EUL) per content per user.
In the end, the RMS service goes through the group memberships in the Publishing License (PL) and looks where the user requesting the member is and takes the rights that the user gets through all the group memberships into ONE EUL.
## Réponse longue
* http://aka.ms/RMSCerts ou https://techcommunity.microsoft.com/t5/security-compliance-and-identity/licenses-and-certificates-and-how-ad-rms-protects-and-consumes/ba-p/247309
> ![image.png](/.attachments/image-24dc6db9-ac12-4c8d-8d2a-aa0d800aaaf6.png)

> ![image.png](/.attachments/image-a39d3677-30f0-49f7-8bd3-1aad94c7e81a.png)

> ![image.png](/.attachments/image-2988befc-6ad2-49e2-b723-69bab8e3071a.png)


