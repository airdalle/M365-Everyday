[[_TOC_]]

# Intro
* Question : If
** a document is “sensitivity labeled” and
** goes outside the tenant (local download, hard copy sent by e-mail, etc.), and
** the label configuration enforces no watermarking and no encryption,
* THEN
** how can the destination user know that the document is labeled when opening/viewing it?
* Réponse :  
** Sensitivity label value/name is stored in clear text (not encrypted nor obfuscated) in the technical metadata for files and emails, third-party apps and services can read it and then apply their own protective actions, if required
** => This metadata is then not visible/readable by the end-user
** This metadata can be queried/re-used through custom development using the Microsoft Information Protection SDK

# Documentation minimale
* https://docs.microsoft.com/en-us/microsoft-365/compliance/sensitivity-labels?view=o365-worldwide#what-a-sensitivity-label-is
* https://docs.microsoft.com/en-us/microsoft-365/compliance/sensitivity-labels?view=o365-worldwide#sensitivity-labels-and-the-microsoft-information-protection-sdk
* [Concepts - Label metadata in the MIP SDK | Microsoft Docs](https://docs.microsoft.com/en-us/information-protection/develop/concept-mip-metadata)
* https://techcommunity.microsoft.com/t5/security-compliance-and-identity/upcoming-changes-to-microsoft-information-protection-metadata/ba-p/1904418

# Documentation technique complémentaire
* [2.3 Encryption](https://docs.microsoft.com/en-us/openspecs/office_file_formats/ms-offcrypto/e47faaed-ee58-4309-9033-88b342df5469) <== This section specifies encryption and obfuscation. 
* [2.6 Sensitivity Labels](https://docs.microsoft.com/en-us/openspecs/office_file_formats/ms-offcrypto/e45ba92e-b121-4b51-a153-057a903ed252) <== This section covers details about how and where sensitivity label metadata is stored.