[[_TOC_]]

<IMG  src="https://techcommunity.microsoft.com/t5/image/serverpage/image-id/414863i3AC2CF83846ABD5E/image-dimensions/2500?v=v2&amp;px=-1"/>

### Documentation
* Documentation produit 
https://learn.microsoft.com/en-us/microsoft-365/compliance/dlp-learn-about-dlp?view=o365-worldwide
* Training
https://learn.microsoft.com/en-us/training/modules/implement-data-loss-prevention-policies/
### A quoi sert le DLP ?
- Surveiller certains usages des données (partage par email, création, modification...)
- Procurer des conseils aux utilisateurs sur l'utilisation qu'ils en font
- Restreindre l'accès aux données en transit


**Chaque stratégie contient les paramètres suivants :​**

- Le template souhaité (RGPD, PCI DSS, personnalisé…)​ : ce sont les types de données que l'on choisit de soumettre à la stratégie et à ses mécanismes
- Les emplacements concernés​ : SharePoint / Exchange / OneDrive / Teams. Attention, les conditions d'application de la stratégie ne sont pas les mêmes selon l'emplacement concerné ! A bien vérifier et réfléchir lors de la conception de la stratégie et en amont (lors de la phase d'AVV, pour ne pas promettre des choses impossibles au client)
- Les conditions d’application : il s'agit de la définition des données concernées. Dans ce paramètre, on décide de ce qui doit être détecté par la stratégie et comment. Si l'on choisit une stratégie avec un template, ces conditions d'application sont déjà remplies. En résumé, il s'agit de la "requête" utilisée par la stratégie. On peut ajouter des exceptions pour exclure certains types de fichiers ou autres.
- Les actions générées lorsque les conditions sont remplies​ :
Surveiller les actions autour de ces données (création, modification, partage…) avec des rapports d’incidents​
Empêcher le partage des données et restreindre l’accès au contenu​
Chiffrer le contenu (pour Exchange uniquement)​
Procurer des conseils aux utilisateurs​ (exemple ci-dessous)
 ​ ![image.png](/.attachments/image-cac7bce1-91b9-4a93-8d7e-e3ca6a59c24a.png)