La législation impose de filtrer au maximum les contenus personnels lors d'exports de données via les outils de Content Search et d'eDiscovery.
Voici quelques astuces permettant d'effectuer ce filtrage :

- **Preprocessing** dans Content Search, eDiscovery Standard et Premium :
Il est possible d'exclure des collections de données les éléments dont le sujet ou le titre contient certains termes.
![image.png](/.attachments/image-fe08d64c-4e0a-42ef-97d4-a4993c52486a.png)

- **Review** dans eDiscovery Premium :
Comme les Review Set permettent de filtrer via beaucoup plus de métadonnées, il est possible de filtrer par Keyword au sein des contenus ou bien directement dans le path des fichiers par exemple.
![image.png](/.attachments/image-02a5185d-ecd8-4036-9e89-53062bc785ae.png)
Il est possible de tagger les éléments en question afin de les exclure de futurs exports ou de la copie dans un autre review set.

_Note_ : lors du filtrage par le path, attention aux résultats qui seront retournés selon les mots clés utilisés. Utiliser "personal" seul, par exemple, retournera tout ce qui est inclus dans un espace personnel SharePoint (url "<…>-my.sharepoint.com/personal/<…>") ce qui n'inclut donc pas uniquement le contenu de répertoires privés.
![image.png](/.attachments/image-d6cc5e63-729b-4f72-baf6-69a562e1c647.png)