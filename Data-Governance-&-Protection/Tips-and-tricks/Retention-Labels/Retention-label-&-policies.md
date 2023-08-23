[[_TOC_]]

# Exemples de scénario
## Auto-apply retention labels based on date of received
=> Utile pour appliquer une stratégie de conservation en volume tout en respectant des critères
https://microsoft.github.io/ComplianceCxE/jumpstarts/kql-exchange/

## Appliquer des stratégies globales de rétention selon de manière dynamique
Par exemple, différencier des stratégies globales de rétention selon la localisation géographique de l'utilisateur
https://microsoft.github.io/ComplianceCxE/jumpstarts/adaptive-exchange/

## Backdating retention in M365
> I have migrated a number of documents from a non-SharePoint container into document libraries in SharePoint Online. These libraries have been configured to use document sets with a calendar year complete as a piece of metadata (2000, 2001, 2002, etc.), since we need our retention periods to start from that point. Can I use a retention label to retain for 20 years from the “Calendar Year Complete” metadata column across all migrated libraries automatically? Example: if the document set had a “Calendar Year complete” of 2012, it’s already ten years into its retention (because it’s currently 2022) so I would only want it retained for an additional 10 years in SharePoint Online.

https://joannecklein.com/2022/04/08/back-dating-retention-in-microsoft-365/

## APPLY A RETENTION LABEL ‘X’ DAYS AFTER LAST MODIFIED
> Is it possible to apply a retention label to content 20 days after last modified?”. Their use-case was they initially want to allow end-users to create/edit/delete documents without having any retention label applied. Only after a period of time has elapsed since the document was last modified should a retention label be applied.

https://joannecklein.com/2022/02/08/apply-a-retention-label-x-days-after-last-modified/