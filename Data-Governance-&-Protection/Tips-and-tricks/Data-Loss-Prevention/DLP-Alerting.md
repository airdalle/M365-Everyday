#Alertes et Monitoring

Lors de la mise en place d'une stratégie DLP, plusieurs options sont disponibles pour monitorer les évènements qui contreviendraient à la stratégie.

Les règles de monitoring et de remontées d'alertes 

Dans la définition d'une règle DLP, et pour chaque règle DLP, on peut utiliser les options suivantes :

![image.png](/.attachments/image-b61baffc-233c-46a0-a8b2-231053142774.png)

_A noter que ces réglages pouvant être définis pour chaque règle DLP définie dans une stratégie, il est possible de définir pour chaque règle un niveau d'alerting plus ou moins fort. Un réglage permet de donner un niveau différent de sévérité à chaque alerte selon, par exemple, le nombre d'occurences d'un SIT donné, ou le niveau de confiance en la correspondance relevée par le Purview Engine._

Ces règles s'appliquent de la même manière que la stratégie soit en mode RUN ou en mode TEST. Cela n'a aucune incidence sur le reporting.

#Partie "Alerting"

Dans la première moitié du panneau, on définit la remontée d'alerte dans le **Dashboard DLP**. Cette alerte contient toutes les informations liées à l'alerte et à l'incident, dans un milieu sécurisé et soumis à toutes les restrictions de contrôle d'accès du Centre de Compliance. 
C'est donc une remontée d'informations tout à fait sécuriser, mais cela rend le contrôle d'accès au Centre de Compliance encore plus critique.

Il est possible (et optionnel) d'envoyer une alerte mail à des administrateurs. Cette notification contient un lien vers le Centre de Compliance, il n'y a donc aucune redondance de la donnée sensible. Elle contient cependant quelques informations sensibles, notamment la règle transgressée et l'utilisateur qui l'a provoquée.

![image.png](/.attachments/image-30999a08-0660-445e-bf77-6afff459d040.png)

Enfin, dans cette partie, il est possible d'agréger les alertes et ne les remonter que si une certaine volumétrie est constatée : un certain nombre de transgressions en un temps donné, ou un certain volume de données transféré.

**Note importante** : Dans le cas où l'on veut créer une alerte au delà d'un certain seuil de matches :
- L'alerte est créée à la fin de la fenêtre de temps renseignée, et donne le nombre total de matches 
*Exemple : seuil de 10 matches en 60 minutes, il y a 14 matches, l'alerte sera envoyée au bout des 60 minutes et indiquera 14 matches*
- **Deux matches d'une même policy ayant lieu à la même minute sont considérées comme des doublons** et ne donnent donc pas lieu à deux matches différents pour le déclenchement de l'alerte.
*Exemple : seuil de 10 matches en 60 minutes, il y a 10 matches dont deux dans la même minute, l'alerte n'est pas générée. En revanche, si un 11eme match se produit avant la fin des 60 minutes, une alerte est générée et mentionne **11** matches.*

#Partie "Notifications"

Dans la seconde partie du panneau, il est possible de programmer des notifications mail à différentes personnes : administrateurs, "SiteAdmin", ...
Cette notification peut contenir un nombre croissant d'informations, allant d'informations liées à la règle DLP jusqu'à un résumé très exhaustif de l'alerte en question (dont le SIT).

Ces notifications représentent donc un risque de redondance de l'information sensible. Il faut être très vigilant au sujet de ces notifications qui peuvent donc être un moyen d'exfiltrer ou de concentrer des informations sensibles à des emplacements non prévus.

A noter que cette notification arrive généralement instantanément après l'incident là où l'Alerte prend quelques minutes à être générée.

Une piste pour limiter le risque de ces notifications, si elles sont nécessaires, est de mettre en place une stratégie de rétention auto appliquée qui supprime automatiquement les mails après un temps donné.
A titre d'exemple, voici à quoi ressemble le mail de notification :

![image.png](/.attachments/image-69bd3dd9-ff8e-4e71-98fb-84b122c6eed6.png)