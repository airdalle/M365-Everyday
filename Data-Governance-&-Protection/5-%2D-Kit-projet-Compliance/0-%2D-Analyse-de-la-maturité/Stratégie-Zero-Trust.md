[[_TOC_]]

# Informations et contenus sur la stratégie Zero Trust
* **Landing Page** : https://aka.ms/zt-links (https://github.com/jplesage/articles/blob/main/zt-links.md)
> ![image.png](/.attachments/image-5373cc12-7a25-4ec1-998e-753ccb25e8c6.png)
* **Initialisation d'un projet Zero Trust :**
        - Initier un projet Zero Trust - partie 1 (Généralités) : https://www.youtube.com/watch?v=miLTgmHUIDk
        - Initier un projet Zero Trust - partie 2 (Détail sur l'accompagnement des entreprises) : https://youtu.be/ofkja2kslpI

# Questionnaire de maturité Zero Trust
## Description générale
* **Lien**: https://aka.ms/Zero-Trust-Maturity-Questionnaire  (https://www.microsoft.com/fr-fr/download/details.aspx?id=103935)
> ![image.png](/.attachments/image-f13a6a94-2e40-4af7-abdc-f55a99041039.png)
* Format : Fichier Excel
* Contenu : 6 piliers, une dizaine de questions par piliers
* Résumé des éléments importants :
1. Identité : Des questions sur comment l'entreprise sécurise ses comptes, sur l'état de son intégration Cloud.
Les aspects les plus avancés se trouvent à la fin du questionnaire :
	- Présence d'un SIEM pour monitorer les menaces sur la sécurité des identités ? (Microsoft Sentinel)
	- Mise en place d'une gouvernance des accès et des identités ? (PIM + Package d'accès + Révisions d'accès, Identity Governance...)

2. Appareil : Fait état des dispositions prises par l'entreprise pour sécuriser les appareils : Stratégies de groupe et de mise à jour, VPN et EDR
	- Nécessité d'enroll les ordinateurs ? Utilisation d'un EDR ? (AAD Devices + Defender for Endpoint)
	- Nécessité d'enroll les appareils portables ? MDM pour contrôle total, MAM pour BYOD ? (AAD Devices + Endpoint Manager)
	- Critères liés à l'appareil dans les stratégies d'accès conditionnel ? (AAD)

3. Applications : Teste la connaissance des applications utilisées au sein de l'entreprise ainsi que de la protection des secrets d'authentification
	- Y a-t-il un moyen de connaître les applications Cloud utilisées par les collaborateurs ? (Defender for Cloud Apps)
	- Cette connaissance est-elle utilisée dans les stratégies d'accès conditionnel ? (AAD)
	- Une stratégie sur le partage des secrets d'authentification est-elle déployée ? (Azure Key Vault)

4. Infrastructure : Questions sur le monitoring des ressources On Prem et Cloud.
	- Protection d'Active Directory et des ressources On Prem ? (Defender for Identity, Defender for Cloud + Sentinel)
	- Protection des ressources Azure ? (Defender for Cloud + Sentinel)
	- Quels accès pour les utilisateurs sur chaque ressources ? Rôles Owners, Co-Author, Contributor, Reader ? (AAD, PIM)

5. Données : Teste la Compliance avec des questions sur la classification, le labeling, le DLP.
	- Des labels et une classification efficace ont-ils été mis en place ? (MIP in O365 Defender)
	- Le DLP a-t-il été mis en place sur les applications Cloud comme Office 365 ? Sur les Terminaux ? (MIP in 0365 Defender, Defender for Endpoint)
	- Toutes les données ont-elles été bien classées ? Un Chiffrement a-t-il été mis en place ? (MIP, AIP)
	- Présence de process en cas de demandes DSR sur les données personnelles ? Vérification du niveau de compliance ? (Compliance Manager, Priva)

6. Réseau : S'assure de la segmentation des réseaux Cloud et On Prem ainsi que l'accessibilité des ressources via le réseau de l'entreprise
	- Ressources Cloud segmentées avec la sécurité Azure ? (Azure Virtual Networks, Azure Private Links, Azure Bastion...)
	- Ressources On Prem segmentées ?
	- Chiffrage des connexions Wifi ? Accès possible à toutes les ressources sans utiliser de VPN via connexion WiFi ?


## Retours d'expérience sur l'utilisation du questionnaire
[ToDo]




