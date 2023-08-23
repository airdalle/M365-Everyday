[[_TOC_]]

# Vue d'ensemble
Source : https://www.infotechtion.com/post/microsoft-information-protection-best-practices
![image.png](/.attachments/image-64eb9177-3199-44ec-ac3b-129eec4550f8.png)

# Vérifier le licensing du client pour valider les types de stratégies qui lui sont disponibles
* En résumé : https://m365maps.com/Microsoft%20365%20Enterprise%20-%20Venn.htm
* https://go.microsoft.com/fwlink/?linkid=2139145
* [Data Loss Prevention for Teams](https://docs.microsoft.com/en-us/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance#information-protection-data-loss-prevention-for-teams)
* [Data loss prevention for Exchange Online, SharePoint Online, and OneDrive for Business](https://docs.microsoft.com/en-us/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance#information-protection-data-loss-prevention-for-exchange-online-sharepoint-online-and-onedrive-for-business)

# Architecture des stratégies DLP
* Ne pas mélanger les workloads (locations) au sein d'une policy, car cela limite les conditions ou exceptions configurables (Par exemple, les conditions spécifiques à Exchange Online ne sont proposées que si la policy ne couvre QUE Exchange Online)
==> quand SPO + EXO sont sélectionnés : 
> ![image.png](/.attachments/image-afcb1663-0e21-40ca-b8c3-831b819478f5.png)
==> quand EXO est sélectionné seul : 
> ![image.png](/.attachments/image-ab5e4638-07de-424d-85e0-3235edbc7b9c.png)

# Planification et délais
* Une stratégie DLP (Endpoint ou Cloud) prend au moins 2h à être déployée sur tous les devices ou utilisateurs.

# Priorisation des tâches de DLP
C'est assez connu, le DLP Engine peut prendre du temps à scanner l'intégralité du Tenant pour attribuer les bons labels et restreindre les documents au bon niveau de sécurité.
* Il est nécessaire de bien prioriser les tâches. Les DLP Policies sont ordonnancées par un "Ordre" sur le portail de Compliance. La Policy d'Ordre 0 sera exécutée avant l'ordre 1, etc, etc. Les stratégies les plus sensibles doivent donc être remontées en haut de la liste.
* Il peut être intéressant d'activer le mode "Sensitive by Default" sur le tenant SPO. Cela consiste à dire que tant que le DLP Engine n'est pas passé, le contenu est considéré comme sensitive et ne peut pas être partagé. Cela s'active avec cette ligne de commande : `Set-SPOTenant -MarkNewFilesSensitiveByDefault BlockExternalSharing `
Source : https://docs.microsoft.com/fr-fr/sharepoint/sensitive-by-default