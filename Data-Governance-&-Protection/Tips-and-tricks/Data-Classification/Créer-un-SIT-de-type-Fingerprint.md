Le Sensitive Information Type de type Fingerprint permet de détecter les documents issus, par exemple, d'un template de document donné.
Cependant, cette option n'est pas accessible depuis le Compliance Center, et il faut entrer les commandes suivantes (nécessite le module `ExchangePowerShell` :

```
$UserCredential = Get-Credential

$Session = New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri https://ps.compliance.protection.outlook.com/powershell-liveid/ -Credential $UserCredential -Authentication Basic -AllowRedirection

Import-pssession $session

$FileTemplate = Get-Content "C:\path\to\file" -Encoding byte -ReadCount 0

$FileFingerprint = New-DlpFingerprint -FileData $FileTemplate -Description "Description"

New-DlpSensitiveInformationType -Name "Nom du SIT" -Fingerprints $FileFingerprint -Description "Description user friendly du SIT"
```

**IMPORTANT :**
Ces commandes créent un SIT trouvable parmi tous les autres SIT du tenant.
Cependant, il ne s'utilise pas comme tous les autres SIT : à l'heure actuelle, sa seule utilisation possible est dans **les règles DLP d'Exchange**.
Dans tous les autres cas de figure, les DLP / Content Search / Auto labelling ne sont pas implémentés. La configuration est possible dans le portail mais cela ne donnera aucun résultat.
Source : https://docs.microsoft.com/fr-fr/microsoft-365/compliance/document-fingerprinting?view=o365-worldwide#how-document-fingerprinting-works

Notez aussi que cette feature a des limites problématiques.
![image.png](/.attachments/image-dceb7648-e779-47e3-8d79-67763edbaa4a.png)