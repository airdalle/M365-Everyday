[[_TOC_]]

# Troubleshooter une DLP Policy (commandes PowerShell)
Les parties **en gras** sont à modifier selon le contexte :

- Get-DlpCompliancePolicy -identity "**D1 Documents in SharePoint**" | fl > c:\temp\**polD1_sword.txt**

- Get-DlpComplianceRule | fl > c:\temp\**polrule_sword.txt**

- Get-DlpSensitiveInformationType | fl > c:\temp\sensitiveinfo_sword.txt

- Get-DlpSensitiveInformationTypeRulePackage | fl > c:\temp\sensitiveinforulepackage_sword.txt

- Get-DlpCompliancePolicy -Identity "**D1 Documents in SharePoint**" -DistributionDetail | Select DistributionStatus > c:\temp\distribD1_sword.txt

La dernière commande permet de vérifier le statut de distribution de la policy.

# DLP Cheat Sheet
- https://www.itpromentor.com/dlp-buffet/
- https://blog.admindroid.com/sharepoint-online-dlp-explained-what-it-is-and-how-it-works/

# Tutoriel - Teams DLP
https://teams-dlp-interactive-guide.azureedge.net/

# Fake Data
www.dlptest.com
https://dlptoolbox.com/