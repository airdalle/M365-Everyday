[[_TOC_]]

# Source
2019 : https://techcommunity.microsoft.com/t5/security-compliance-and-identity/how-to-prepare-an-azure-information-protection-cloud-exit-plan/ba-p/382631

# Microsoft Managed Key

**![image.png](/.attachments/image-4ff54f45-3914-4450-bc55-804f41428df6.png)**

## Process / Etapes
The following end to end process provides a cloud exit solution for organizations using MMK:

1. Provision the AIP service, configure it as desired and start using it normally.
1. If the need to discontinue using the service is identified, [request the export of the Microsoft Managed Key as part of a TPD file](https://docs.microsoft.com/en-us/azure/information-protection/operations-microsoft-managed-tenant-key#export-your-tenant-key).
1. Install a new AD RMS cluster, with default configurations and register the Service Connection Point in Active Directory, following [our guidance](https://docs.microsoft.com/en-us/previous-versions/windows/it-pro/windows-server-2012-R2-and-2012/hh831364(v=ws.11).
1. [Import the TPD file provided by Microsoft into AD RMS](https://docs.microsoft.com/en-us/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/dd772677%28v%3dws.10%29) either using the AD RMS Management Console or the equivalent PowerShell functionality.
1. Configure clients to use Licensing redirections pointing the AIP URL to the AD RMS cluster URL. You can apply the same settings in the scripts used for a [migration from AD RMS to AIP](https://docs.microsoft.com/en-us/azure/information-protection/migrate-from-ad-rms-phase3), reversing the position of the redirection URLs in the registry.
1. Configure the super user feature in AD RMS, using a suitable AD group that will contain administrators with super user privilege.
1. Use AD RMS normally to consume content protected before the execution of the cloud exit.

# Bring your own key
![image.png](/.attachments/image-7067ee91-e42b-4212-a934-1c5c98b1a185.png)

## Process / Etapes
Voir article en ligne
