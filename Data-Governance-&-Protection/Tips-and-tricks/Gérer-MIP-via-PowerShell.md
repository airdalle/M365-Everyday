[[_TOC_]]

# Prérequis
_Using the table below to know which PowerShell Modules you need to install (by running **Install-Module XXX**) and import (**Import-Module XXX**) to configure / troubleshoot Labels:_
><IMG src="https://techcommunity.microsoft.com/t5/image/serverpage/image-id/397406i5BE88AE1DA911D8B/image-dimensions/2500?v=v2&amp;px=-1"/>
_Want to install them “all at once”?_
`Install-Module AipService; Install-Module ExchangeOnlineManagement; Install-Module Microsoft.Online.Sharepoint.PowerShell; Install-Module AzureAd Preview`

# Documentation générale
## Security & Compliance Center PowerShell
https://docs.microsoft.com/en-us/powershell/exchange/scc-powershell?view=exchange-ps
https://docs.microsoft.com/en-us/powershell/module/exchange/?view=exchange-ps#policy-and-compliance

## Connect to Security & Compliance Center PowerShell
https://docs.microsoft.com/en-us/powershell/exchange/connect-to-scc-powershell?view=exchange-ps

# Thématiques
## Data Classification / Sensitive Information Types
- Create : https://learn.microsoft.com/en-us/microsoft-365/compliance/create-a-custom-sensitive-information-type-in-scc-powershell?view=o365-worldwide
- Export & Modify : https://learn.microsoft.com/en-us/microsoft-365/compliance/sit-modify-a-custom-sensitive-information-type-in-powershell?view=o365-worldwide
- Remove : https://learn.microsoft.com/en-us/microsoft-365/compliance/sit-remove-a-custom-sensitive-information-type-in-powershell?view=o365-worldwide

## Retention
- https://docs.microsoft.com/en-us/powershell/module/exchange/?view=exchange-ps#policy-and-compliance-retention

## Sensitivity Labels & Policies
- https://docs.microsoft.com/en-us/powershell/module/exchange/?view=exchange-ps#policy-and-compliance
- https://docs.microsoft.com/en-us/powershell/module/exchange/remove-autosensitivitylabelpolicy?view=exchange-ps
- https://docs.microsoft.com/en-us/powershell/module/exchange/new-labelpolicy?view=exchange-ps

## Content Search
- https://docs.microsoft.com/en-us/powershell/module/exchange/?view=exchange-ps#policy-and-compliance-content-search

## DLP
- https://learn.microsoft.com/en-us/powershell/module/exchange/?view=exchange-ps#policy-and-compliance-dlp

## Information Barriers
- https://docs.microsoft.com/en-us/powershell/module/exchange/new-organizationsegment?view=exchange-ps
- https://docs.microsoft.com/en-us/powershell/module/exchange/remove-informationbarrierpolicy?view=exchange-ps

## EDiscovery
- https://docs.microsoft.com/en-us/powershell/module/exchange/?view=exchange-ps#policy-and-compliance-content-search
