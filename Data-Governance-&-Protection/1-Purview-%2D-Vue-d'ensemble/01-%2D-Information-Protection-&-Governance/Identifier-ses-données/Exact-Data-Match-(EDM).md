#EDM

Les Exact Data Match sont un type de SIT qui utilisent des valeurs exactes (ou presque exactes) au lieu de patterns ou de liste de mots clés.
Cette fonctionnalité résulte en un nombre réduit de faux positifs et peut être mise à jour dynamiquement plus facilement que les autres types de SIT classiques (jusqu'à une fois par jour).
Pour créer un SIT de type EDM, il faut fournir :
- Les données dans une base de données.
- Un schéma, un fichier .xml contenant plusieurs informations.

L'EDM est pertinent pour les cas de figure où **il y a de très nombreuses valeurs (au delà du million) de données sensibles**. Autrement, d'autres types de SIT seraient à privilégier.
Il serait aussi pertinent dans le cas où il faut **limiter le nombre de faux positifs de données très risquées**, dont le stockage en clair dans le centre de compliance poserait des inquiétudes en terme de sécurité (numéros de cartes bleues par exemple). En effet, l'EDM fonctionne en comparant des empreintes et non pas des données en clair - qui ne sont donc jamais transmises à MS. C'est un autre cas où l'EDM est pertinent.
_Exemple : Bloquer tous les numéros de carte bleue créerait des faux positifs si un employé effectue un achat. Il convient de ne bloquer que les numéros de carte bleue des clients, par exemple._

**Quelques limitations à relever :**
- Il n'est possible de créer que 10 schémas EDM différents dans un tenant.
- Chaque EDM doit se baser sur un "primary element", qui se base sur un pattern de SIT classique comme une regex par exemple, auxquels s'ajoutent d'éventuels "supporting elements". 

Plus d'informations et de détails dans les sous pages de ce wiki.

_Schéma du Workflow de la création et du déploiement d'un EDM SIT_
<IMG src="https://docs.microsoft.com/en-us/microsoft-365/media/swimlane_edm_process.png?view=o365-worldwide" alt="exact data match workflow phases"/>

**Documentation :**

- https://docs.microsoft.com/en-us/microsoft-365/compliance/sit-learn-about-exact-data-match-based-sits?view=o365-worldwide#learn-about-exact-data-match-based-sensitive-information-types

- https://docs.microsoft.com/en-us/microsoft-365/compliance/sit-get-started-exact-data-match-based-sits-overview?view=o365-worldwide