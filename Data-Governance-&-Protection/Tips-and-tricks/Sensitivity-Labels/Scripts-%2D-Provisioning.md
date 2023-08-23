[[_TOC_]]

# Connexion
* Console PowerShell
* `Connect-AipService` => Templates RMS
* `Connect-IpPsSession` =>  Security & Compliance PS Module

# Cmdlets principaux
## Créer un label
`New-Label`
## Modifier un label
`Set-Label`
## Lister / Supprimer les sensitivity labels existants
```
Get-Label
Remove-Label
```
## Créer un label policy
`New-LabelPolicy`
## Modifier un label policy
`Set-LabelPolicy`
## Lister / Supprimer les sensitivity labels policy existants
```
Get-LabelPolicy
Remove-LabelPolicy
```
## Lister / Supprimer les auto-labelling policy existants
```
Get-AutoSensitivityLabelPolicy
Remove-AutoSensitivityLabelPolicy
```

# Provisioning simple
## Taxonomie \#1 d'étiquettes
* Non-Professional
* Public
* General
* Confidential
* Secret
### Script PS pour créer les labels
* Non-professional
 `New-Label -DisplayName "Non-professional (PP)" -Name "NonProfessional-Private" -Tooltip "Private / not related with your work or with the company" -AdvancedSettings @{color="#0080FF"}`
* Public
 `New-Label -DisplayName "Public (NBI)" -Name "Public" -Tooltip "Business data that is intended for public consumption" -AdvancedSettings @{color="#80FF00"}` 
* General
`New-Label -DisplayName "General (LBI)" -Name "General" -Tooltip "Business data that is not intended for public consumption" -AdvancedSettings @{color="#FFFF00"}` 
* Confidential
`New-Label -DisplayName "Confidential (MBI)" -Name "Confidential" -Tooltip "Business data that is not intended for sharing with everyone in the company" -AdvancedSettings @{color="#FF8000"}` 
* Secret
`New-Label -DisplayName "Secret (HBI)" -Name "Secret" -Tooltip "Business data that has high impact for the business if shared with unauthorized recipients" -AdvancedSettings @{color="#FF0000"}` 

### Script PS pour créer des versions multilingues des labels 
* Non-Professional
`Set-Label -Identity "NonProfessional-Private" -LocaleSettings '{"localeKey":"DisplayName","Settings":[{"Key":"en-us","Value":"Non-professional (PP)"},{"Key":"fr-fr","Value":"Non professionel - Privé (PP)"},{"Key":"es-es","Value":"No profesional - Privado"}]}','{"localeKey":"tooltip","Settings":[{"Key":"en-us","Value":"Private / not related with your work or with the company"},{"Key":"fr-fr","Value":"Données privées / non liées à votre travail ou à [NomSociété]"},{"Key":"es-es","Value":"Privado / no relacionado con su trabajo o con la empresa"}]}'`
* Public
`Set-Label -Identity "Public" -LocaleSettings '{"localeKey":"DisplayName","Settings":[{"Key":"en-us","Value":"Public (NBI)"},{"Key":"fr-fr","Value":"Public (IBN)"},{"Key":"es-es","Value":"Público"}]}','{"localeKey":"tooltip","Settings":[{"Key":"en-us","Value":"Business data that is intended for public consumption"},{"Key":"fr-fr","Value":"Données de la société destinées à usage public"},{"Key":"es-es","Value":"Sin impacto empresarial"}]}'`
* General
`Set-Label -Identity "General" -LocaleSettings '{"localeKey":"DisplayName","Settings":[{"Key":"en-us","Value":"General (LBI)"},{"Key":"fr-fr","Value":"Général (IBB)"},{"Key":"es-es","Value":"Público "}]}','{"localeKey":"tooltip","Settings":[{"Key":"en-us","Value":"Business data that is intended for public consumption"},{"Key":"fr-fr","Value":"Données de [NomSociété] destinées à usage public"},{"Key":"es-es","Value":"Sin impacto empresarial"}]}'`
* Confidential
`Set-Label -Identity "Confidential" -LocaleSettings '{"localeKey":"DisplayName","Settings":[{"Key":"en-us","Value":"Confidential (MBI)"},{"Key":"fr-fr","Value":"Confidentiel (IBM)"},{"Key":"es-es","Value":"Confidencial"}]}','{"localeKey":"tooltip","Settings":[{"Key":"en-us","Value":"Business data that is not intended for sharing with everyone in the company"},{"Key":"fr-fr","Value":"Données de la société qui ne sont pas destinées à être partagées avec tout le monde de [NomSociété]"},{"Key":"es-es","Value":"Datos empresariales que no están destinados a ser compartidos con todos los miembros de la empresa"}]}'`
* Secret
`Set-Label -Identity "Secret" -LocaleSettings '{"localeKey":"DisplayName","Settings":[{"Key":"en-us","Value":"Secret (HBI)"},{"Key":"fr-fr","Value":"Secret (IBE)"},{"Key":"es-es","Value":"Secreto"}]}','{"localeKey":"tooltip","Settings":[{"Key":"en-us","Value":"Business data that has high impact for the business if shared with unauthorized recipients"},{"Key":"fr-fr","Value":"Données qui ont un impact élevé pour [NomSociété] si elles sont partagées avec des destinataires non autorisés"},{"Key":"es-es","Value":"Datos empresariales que tienen un alto impacto para la empresa si se comparten con destinatarios no autorizados"}]}'`

### Script PS Alternatif - Exemple non personnalisé
```
$Languages = @("fr-fr","it-it","de-de")
$DisplayNames=@("Publique","Publico","Oeffentlich")
$Tooltips = @("Texte Français","Testo italiano","Deutscher text")
$label = "Public"
$DisplayNameLocaleSettings = [PSCustomObject]@{LocaleKey='DisplayName';
Settings=@(
@{key=$Languages[0];Value=$DisplayNames[0];}
@{key=$Languages[1];Value=$DisplayNames[1];}
@{key=$Languages[2];Value=$DisplayNames[2];})}
$TooltipLocaleSettings = [PSCustomObject]@{LocaleKey='Tooltip';
Settings=@(
@{key=$Languages[0];Value=$Tooltips[0];}
@{key=$Languages[1];Value=$Tooltips[1];}
@{key=$Languages[2];Value=$Tooltips[2];})}
Set-Label -Identity $Label -LocaleSettings (ConvertTo-Json $DisplayNameLocaleSettings -Depth 3 -Compress),(ConvertTo-Json $TooltipLocaleSettings -Depth 3 -Compress)
```


## Taxonomie \#2 d'étiquettes
* Personnel-Privé
* Public
* Général
* Confidentiel
* Secret
### Script PS
* Non-professional
 `New-Label -DisplayName "Non professionel - Privé (PP)" -Name "NonProfessionel-Privé" -Tooltip "Données privées / non liées à votre travail ou à l'entreprise" -AdvancedSettings @{color="#0080FF"}`
* Public
 `New-Label -DisplayName "Public (IBN)" -Name "Public" -Tooltip "Données de la société destinées à usage public" -AdvancedSettings @{color="#80FF00"}` 
* General
`New-Label -DisplayName "Général (IBB)" -Name "Général" -Tooltip "Données de la société non destinées à usage public" -AdvancedSettings @{color="#FFFF00"}`
* Confidential
`New-Label -DisplayName "Confidentiel (IBM)" -Name "Confidentiel" -Tooltip "Données de la société qui ne sont pas destinées à être partagées avec tout le monde dans l'entreprise" -AdvancedSettings @{color="#FF8000"}` 
* Secret
`New-Label -DisplayName "Secret (IBE)" -Name "Très confidentiel" -Tooltip "Données de la société qui ont un impact élevé pour l'entreprise si elles sont partagées avec des destinataires non autorisés" -AdvancedSettings @{color="#FF0000"}` 

# Cmdlets pour paramétrage + complexe des labels et label policies
## General
https://learn.microsoft.com/fr-fr/azure/information-protection/rms-client/clientv2-admin-guide-customizations
## Advanced setting reference by feature
https://learn.microsoft.com/en-us/azure/information-protection/rms-client/clientv2-admin-guide-customizations#advanced-setting-reference-by-feature
## Label policy advanced setting reference
https://learn.microsoft.com/en-us/azure/information-protection/rms-client/clientv2-admin-guide-customizations#label-policy-advanced-setting-reference
## Label advanced setting reference
https://learn.microsoft.com/en-us/azure/information-protection/rms-client/clientv2-admin-guide-customizations#label-advanced-setting-reference

