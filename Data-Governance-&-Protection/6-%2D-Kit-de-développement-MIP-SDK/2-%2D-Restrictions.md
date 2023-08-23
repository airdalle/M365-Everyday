# Restrictions liées au Chiffrement

## Comment accéder à un fichier chiffré ?

- Dans le cas d'un fichier Office : on utilise simplement l'application Office correspondante.
Si le fichier est chiffré, le client demandera de s'identifier sur un compte autorisé à lire le fichier.
![image.png](/.attachments/image-e546060b-1652-49d5-ae19-f2c3605438e8.png)

- Dans le cas d'un fichier non Office : le fichier va changer de format selon la table ci-dessous.
Une fois le format changé, il faut utiliser l'AIP Viewer pour l'ouvrir. Il faut, sur le poste, être connecté à un compte autorisé à accéder au contenu.
![image.png](/.attachments/image-bb39d193-da4f-45f3-b149-662c060f1b23.png)
Télécharger l'AIP Viewer : https://www.microsoft.com/en-us/download/details.aspx?id=54536 

## Formats compatibles hors Office
![image.png](/.attachments/image-e5c05feb-8265-4def-b959-53cf2c452399.png)

# Restrictions liées à la Classification

## Cas du content marking
MIP SDK doesn't support direct application of content marking, including header, footer, or watermark, on any files. When writing the label metadata to a file, the File SDK will write the contentBits metadata property to indicate that protection was applied (if configured) and will not write the properties that indicate header, footer, or watermark were applied. When the file is opened in an application that supports content marking, the content marking configuration should be evaluated by the application and written to the file on save.

## Formats compatibles
Si l'application d'un label implique un chiffrement : les formats de fichiers compatibles peuvent être lus sur le tableau ci-dessus.

Autrement, si le label n'implique aucun chiffrement : les formats de fichiers compatibles sont différents :
![image.png](/.attachments/image-ec4e0625-8b9d-4c06-b235-2eec309dee5f.png)
![image.png](/.attachments/image-c13c21ed-4298-47ed-b3ff-b39140808e16.png)

# Documentation
https://learn.microsoft.com/en-us/information-protection/develop/concept-supported-filetypes