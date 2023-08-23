**En date du 12/08/2022**

**L'intérêt de Sentinel dans la stratégie de protection de la donnée**
-

Une fois les connexions établies avec Microsoft 365 Defender, les informations remontées au sein de Microsoft Sentinel permettent d'enquêter sur les alertes, alors rassemblées en incidents et mises en commun avec toutes les autres alertes pouvant être remontées par les autres connexions établies avec Sentinel.

En d'autres termes, les alertes DLP par exemple peuvent enrichir les autres incidents et permettre une plus vaste investigation des menaces détectées au sein du Tenant.

En revanche, les capacités (à ce jour) de Purview au sein de Sentinel sont limitées à la métadonnée. Dans le cas d'une alerte levée par DLP, on a comme information :
- La règle DLP qui a déclenché l'alerte,
- L'utilisateur ayant déclenché l'alerte ainsi que ses éventuels contacts impliqués dans l'incident (adresse mail externe, ...)
- Le nom du / des fichier(s) transmis.

Il n'est pas possible, au sein de Microsoft Sentinel, de procéder à l'ouverture du document sensible et de constater son contenu ainsi que son contexte, ce qu'il est possible de faire dans le Compliance Center et dans une moindre mesure dans le Security Center.

On peut arguer que c'est une information sensible qu'il est bon de laisser à une audience dont c'est strictement le rôle, et que dans un contexte de SIEM unifié, les métadonnées fourniront déjà un très grand nombre d'informations aux analystes SOC, qui pourront si besoin est demander aux Compliance Administrators de procéder à la vérification du contexte et du contenu d'une alerte dans un autre portail. Pourquoi pas, aussi, mettre en place une stratégie d'accès Just In Time même si les rôles de compliance intégrés à Azure AD PIM sont à ce jour très limités.

**Captures d'écran**
- 
Un incident est constitué de plusieurs alertes.
![image.png](/.attachments/image-dfdbd76f-96d8-45f4-9bac-0c2cf4bf0faa.png)

![image.png](/.attachments/image-dacb8326-2337-474a-8ddb-c70835f52875.png)

Les incidents peuvent être décomposés en Entités afin de tracer des liens entre différents incidents.

![image.png](/.attachments/image-1c1eb305-e898-4cf7-b1b1-1e1784a26e1f.png)

En revanche, à ce stade, il n'st pas possible d'investiguer plus en profondeur ces alertes via le portail Sentinel.

![image.png](/.attachments/image-4953e2a1-ecdb-488c-8aaa-45b8b5e87c28.png)

**Doc**
-
https://docs.microsoft.com/en-us/microsoft-365/security/defender/investigate-dlp?view=o365-worldwide