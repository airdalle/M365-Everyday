[[_TOC_]]

# Insider Risk Management & eDiscovery

**Est-ce que les actions de configuration IRM sont dans le journal d'audit ? (Ajout de policy, changer un indicateur…)**
Seuls les "IRM Auditors" ont la capacité de récupérer les logs d'IRM.
L'Audit Log concerne toutes les actions des Policies, Cases, Alertes, Settings, Utilisateurs et "Notice Templates"
Le changement des indicateurs, par exemple, est inclus dans ces logs
 

**Quand est-ce que les cases IRM (et eDiscovery) sont purgés ?**
Les cas IRM peuvent être indiqués "Resolved". Ils sont alors conservés (il s'agit simplement de notifier si le cas est résolu, et en précision, s'il s'agit d'un faux positif ou d'un vrai risque encouru par l'entreprise)
Les cas eDiscovery peuvent être indiqués "Fermés". Ils sont alors conservés, le legal hold éventuellement placé est levé, mais les contenus concernés sont conservés pour une période dite "de grâce" de 30 jours.
Les cas eDiscovery peuvent être supprimés, ce qui supprimera toutes les informations du cases, y compris les requêtes, collections et review sets.

# Forum Sentinel
==> https://techcommunity.microsoft.com/t5/microsoft-sentinel/bd-p/MicrosoftSentinel

# Questions durant webinaire Sentinel
Suresh
1/17/2023 6:43 PM
If I have deployed Microsoft Defender *, Should I still use Sentinel for investigation or use Defender Portal (security.microsoft.com)? When would you recommend to use Sentinel vs Defender Portal for investigation?
Modérateur
1/17/2023 6:44 PM
If you are working on a pure M365D incident, we suggest using both portals. You can start with this page for your initial triage and continue to M365D for a deeper investigation.


Igor (Difenda)
1/17/2023 6:43 PM
It would be great to have a guided CTF kind of event to get people to learn ho to use all these new great features
Modérateur
1/17/2023 6:45 PM
If you want more hands on experience with Sentinel and MDE, you have a great workshop where you can practice some of the new feature and earn a badge: Microsoft Security Immersion Workshop: Into the Breach. https://pulse.microsoft.com/en/microsoft-security-immersion-and-discover-workshops/


Ashfaq
1/17/2023 6:44 PM
I feel that similar incidents should have more clarity about what entity is similar to the current incident - (Same Ip, Same User, Same Process, Same URL) instead of just saying "similar entities"
Modérateur
1/17/2023 6:45 PM
when you hover over notification that it is similar entities, you will be able to see list of similar entities.

Tim Gjerlufsen
1/17/2023 6:50 PM
Are these playbooks shown in the demo available elsewhere??
Modérateur
1/17/2023 6:50 PM
Most are availalbe in the playbook gallery, content hub or in GitHub
https://github.com/Azure/Azure-Sentinel/tree/master/Playbooks