[[_TOC_]]

# Client-side versus Service-Side
## Blog Joanne C Klein
https://joannecklein.com/2021/02/15/client-side-versus-service-side-sensitivity-auto-labeling-why-you-should-care/amp/

## Documentation Microsoft
https://docs.microsoft.com/en-us/microsoft-365/compliance/apply-sensitivity-label-automatically?view=o365-worldwide
> ![image.png](/.attachments/image-93375b78-b716-4f51-9306-5ea3dc425d20.png)

# Comportements/limites observés
## Labeling conditionné à un contenu en entête ou pied de page
- Si on veut faire du client side autolabeling sur la base de contenu à repérer dans un entête ou pied de page, le client side autolabeling ne fonctionnera pas si on utilise office online (UI web donc). Il faut obligatoirement utiliser le client Office pour Windows pour que l'autolabeling se déclenche
- le service side autolabeling fonctionne bien sur le repérage de contenu au sein d'un entête ou pied de page

# Service-Side Auto-labeling Playbook
https://microsoft.github.io/ComplianceCxE/playbooks/service-side-auto-labeling/

# Labeling inheritance between e-mail and attachment
* ![image.png](/.attachments/image-3be14747-209d-4514-a14d-0723793eca98.png)
* ![image.png](/.attachments/image-3a8ec041-d4c6-4384-9054-5364b0575366.png)

# Autolabeling via MDCA
* https://docs.microsoft.com/en-us/defender-cloud-apps/azip-integration#automatically-label-files

# Container Labeling
## Exemple de taxonomie
[Sensitivity Labeling - Taxonomie](/Data-Governance-&-Protection/Tips-and-tricks/Sensitivity-Labels/Sensitivity-Labeling-%2D-Taxonomie)

## Tips 1
* ![image.png](/.attachments/image-6c0d1f02-1930-4f2d-ad7f-02e388210b4c.png)
* [![image.png](/.attachments/image-5cc7057a-30e6-46af-ab60-b9f4a5d0c130.png)](https://practical365.com/monitor-changes-sensitivity-labels-container-management/)
## Tips 2
* ![image.png](/.attachments/image-45afd867-21d1-45cf-a0cf-35ab1848e06d.png)
* [![image.png](/.attachments/image-a7d6c79f-8a21-4f50-87b8-20b9e276ba3c.png)](https://alberthoitingh.com/2021/04/23/check-for-label-changes-on-container-level/)

## Warning !
* [![image.png](/.attachments/image-02a81666-40ef-4969-9e67-82739cae3f59.png)](https://docs.microsoft.com/en-us/azure/active-directory/enterprise-users/groups-assign-sensitivity-labels#enable-sensitivity-label-support-in-powershell)
* ![image.png](/.attachments/image-3a0ec54e-49fc-49a4-b251-e07b0689da7c.png)


