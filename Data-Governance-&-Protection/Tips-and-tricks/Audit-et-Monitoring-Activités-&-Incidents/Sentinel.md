[[_TOC_]]

# En amont - Option 1 : Tirer profit d'Unified Audit Log et Microsoft Defender for Cloud Apps
Il est possible d'afficher, dans Microsoft Defender for Cloud Apps, les alertes DLP de Microsoft Purview, puis de connecter Defender for Cloud Apps à Microsoft Sentinel.
<IMG src="https://s40823.pcdn.co/wp-content/uploads/2022/05/Figure-1-Data-Ingestion-1024x401.png" alt="Monitoring Microsoft Information Protection with Microsoft Sentinel" class="wp-image-56395" width="1024" height="401"/>

Pour ce faire, suivre [ce lien](https://docs.microsoft.com/en-us/defender-cloud-apps/siem-sentinel) puis [ce lien](https://practical365.com/monitoring-microsoft-information-protection-with-microsoft-sentinel/).

Note : le connecteur Microsoft Defender 365 étant à cette heure en préversion, il peut évoluer avec le temps et avoir quelques comportements curieux, notamment à la connexion. La marche à suivre a cependant été réalisée avec succès avant d'écrire ces lignes.

# En amont - Option 2 : Envoyer des logs de stratégie DLP vers Sentinel
Se référer à [la documentation](https://coexya.sharepoint.com/:b:/r/sites/IDS-Microsoft365-InformationProtection/Documents%20partages/R%C3%A9f%C3%A9rences%20projet/Projets/Michelin/Detection%20Rules%20-%202021/Michelin%20-%20O365%20-%20Detection%20Rules%20Recommendations.pdf?csf=1&web=1&e=sIctPA) du projet Michelin

En résumé :
1. Créer le SIT sur lequel la stratégie sera basée (facultatif en fonction du cas d'usage)
1. Créer la stratégie DLP dans compliance.microsoft.com
1. Souscrire à l'API Office 365 Management Activity
1. Créer un flux programmé PowerAutomate pour pousser les logs obtenus vers Log Analytics (nom de la table récupérée : ComplianceDLP_CL)

# En aval : Envoyer des données de Sentinel vers un tableau de bord PowerBI
https://learn.microsoft.com/en-us/azure/sentinel/powerbi

# A suivre...