[[_TOC_]]
# Source
https://www.infotechtion.com/post/microsoft-information-protection-best-practices

# Bonnes pratiques
1. Ne définir que quelques niveaux de classification de premier niveau
* Moins il y a d'options, plus il sera facile pour les utilisateurs et les machines de choisir la bonne classification de sécurité, par exemple **OUVERT**, **INTERNE**, **RESTREINT**, **CONFIDENTIEL**. 

2. Avoir des sous niveaux uniquement lorsque cela est justifié
* Les modèles de classification de sécurité peuvent avoir des sous-classes, par exemple **CONFIDENTIEL - EXECUTIFS**. Ne les mettez en œuvre que lorsque cela nécessite une protection ou une autorisation distincte, par exemple, uniquement accessible aux cadres.

3. Envisager de lier l'accès aux niveaux de classification de sécurité
* Il peut être plus facile pour les utilisateurs de sélectionner le bon niveau de classification s'ils comprennent qui y aura accès, par exemple **INTERNE** est disponible pour tout le personnel, **RESTREINT** n'est disponible que pour certains employés, **CONFIDENTIEL** n'est disponible que pour des utilisateurs nommés.

4. Veiller à ce que la dénomination ait un sens pour les utilisateurs 
* Veiller à ce que les utilisateurs comprennent vraiment ce que les différentes étiquettes signifient, par exemple **OUVERT** est une information qui peut être partagée à l'extérieur de votre organisation, par opposition à **INTERNE** qui est une information qui peut être largement partagée au sein de votre organisation.

5. Identifier des mots et des phrases clés pour chaque niveau de classification
* Il sera ainsi plus facile pour les utilisateurs et les machines de classifier correctement les informations.

6. Veiller à ce que les utilisateurs ne voient que les niveaux de classification de sécurité pertinents
* Les utilisateurs ne doivent voir que les niveaux de classification de sécurité qui les concernent. Si **OUVERT** signifie qu'il peut être partagé avec tout le monde en dehors de votre organisation, alors seuls certains utilisateurs auront ce mandat. Si **CONFIDENTIEL** est très sensible, seuls les utilisateurs ayant fait l'objet d'une vérification des antécédents appropriée devraient pouvoir utiliser ce niveau.

7. Décider si les utilisateurs doivent classifier toutes les informations, ou seulement les exceptions
* Exiger des utilisateurs qu'ils classifient tous les fichiers améliorera la maturité de l'organisation, mais cela demandera plus de travail aux utilisateurs. Une option consiste à définir des classifications de sécurité par défaut sur les systèmes et les espaces de travail, puis à demander aux utilisateurs de n'agir que lorsque le niveau de classification de sécurité est différent pour chaque fichier. Cette dernière solution est plus difficile à mettre en œuvre, et l'impact est souvent que les informations sensibles ne sont pas classées correctement.

8. Établir des niveaux de protection accrus par niveau de classification
* Commencez par définir comment les informations dont le niveau de classification de sécurité est le plus bas seront protégées, puis quelle sera la protection supplémentaire pour le niveau suivant, et ainsi de suite. 

9. Trouver le bon équilibre entre ouverture et contrôle
* Veillez à ce que le personnel ait accès aux informations pertinentes tout en protégeant les informations sensibles.

10. Définir les cas d'utilisation pour le partage externe des informations sensibles
* Les utilisateurs externes peuvent accéder aux informations protégées lorsque vous le souhaitez.

# Exemple - Cas réel
![image.png](/.attachments/image-204fe038-7e56-4515-b7f0-d02b5b5961ab.png)
![image.png](/.attachments/image-57f8116b-9dff-4166-b9e7-b1bd3ce90b12.png)

