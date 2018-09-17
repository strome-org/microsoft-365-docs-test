---
title: "Summary of Microsoft 365 Enterprise security for the Contoso Corporation"
author: JoeDavies-MSFT
ms.author: josephd
manager: laurawi
ms.date: 09/13/2018
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection: 
- Ent_O365
- Strat_O365_Enterprise
ms.custom:

description: How Contoso is using the security features across Microsoft 365 Enterprise.
---

# Summary of Microsoft 365 Enterprise security for the Contoso Corporation

**Summary:** How Contoso is using the security features across Microsoft 365 Enterprise.

To obtain the sign-off of the deployment of Microsoft 365 Enterprise by the IT security department, a thorough security review was conducted. Here are Contoso's security requirements for the cloud:

- Use the strongest methods of authentication for employee access to cloud resources
- Ensure that PCs and mobile devices connect and access applications in secure ways
- PCs and email are protected from malware
- Permissions on cloud-based digital assets define who can access what and what they can do and are designed for least privilege access
- Sensitive and highly regulated digital assets are labeled, encrypted, and stored in secure locations
- Highly regulated digital assets are protected with permissions
- IT security can monitor security posture from central dashboards and get notified of security events for quick response and mitigation

## Contoso's path to Microsoft 365 security readiness

Contoso used the following steps to ready their security for their deployment of Microsoft 365 Enterprise:

1. Limited administrator accounts for the cloud

   Contoso did an extensive review of the existing Windows Server AD administrator accounts and set up a series of cloud administrator accounts and groups.

2. Performed data classification analysis into three levels

   Contoso performed a careful review and determined the three levels, which was used to determine the Microsoft 365 Enterprise features to protect Contoso's most valuable data.

3. Determined access, retention, and information protection policies for data levels

   Based on the data levels, Contoso determined detailed requirements, which will be used to qualify future IT workloads being moved to the cloud.

In accordance with security best practices and Microsoft 365 Enterprise deployment requirements, Contoso's security administrators and IT department have deployed many security features and capabilities, as described in the following sections.

### Identity & access management 

- Dedicated global administrator accounts with MFA and PIM

  Rather than assign the global admin role to everyday user accounts, Contoso created three, dedicated global administrator accounts with very strong passwords and protected them with multi-factor authentication (MFA) and Azure AD Privileged Identity Management (PIM). 

  Signing in with a global administrator account is only done for specific administrative tasks, the passwords are only known to designated staff, and can only be used within the time configured with Azure AD PIM. 

  Contoso's security administrators have assigned lesser admin roles to accounts that are appropriate to that IT person's job function and responsibility.

  For more information, see [About Office 365 admin roles](https://support.office.com/article/about-office-365-admin-roles-da585eea-f576-4f55-a1e0-87090b6aaa9d).

- MFA for all user accounts

  MFA adds an additional layer of protection to the sign-in process by requiring users to acknowledge a phone call, text message, or an app notification on their smart phone after correctly entering their password. With MFA, Azure AD user accounts are protected against unauthorized sign-in even if an account password is compromised.

   - To protect against a compromise of the Microsoft 365 subscription, Contoso requires MFA on all global administrator accounts.
   - To protect against phishing attacks, in which an attacker compromises the credentials of a trusted person in the organization and sends malicious emails, Contoso enabled MFA on all user accounts, including manager and executive staff. 

- Safer device and application access with conditional access policies

  Contoso is using [conditional access policies](microsoft-365-policies-configurations.md) for identity, devices, Exchange Online, and SharePoint Online. Identity conditional access policies include requiring password changes for high-risk users and blocking clients from using apps that don’t support modern authentication. Device conditional policies include the definition of approved apps and requiring compliant PCs and mobile devices. Exchange Online conditional access policies include blocking ActiveSync clients and setting up Office 365 message encryption. SharePoint Online conditional access policies include additional protection for sensitive and highly regulated sites.

- Windows Hello for Business

  Contoso has deployed and requires [Windows Hello for Business](https://docs.microsoft.com/windows/security/identity-protection/hello-for-business/hello-identity-verification) to eventually eliminate the need for passwords with strong two-factor authentication on PCs and mobile devices running Windows 10 Enterprise.

- Windows Defender Credential Guard

  To block targeted attacks and malware running in the operating system with administrative privileges, Contoso has enabled [Windows Defender Credential Guard](https://docs.microsoft.com/windows/security/identity-protection/credential-guard/credential-guard) through Windows Server AD group policy.

### Threat protection

- Protection from malware with Windows Defender Antivirus

  Contoso is using [Windows Defender Antivirus](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-antivirus/windows-defender-antivirus-in-windows-10) for malware protection and anti-malware management for PCs and devices running Windows 10 Enterprise.

- Secure email flow and mailbox audit logging with Office 365 Advanced Threat Protection 

  Contoso is using Exchange Online Protection and [Office 365 Advanced Threat Protection (ATP)](https://docs.microsoft.com/office365/securitycompliance/office-365-atp) to protect against unknown malware, viruses, and malicious URLs transmitted through emails. 

  Contoso has also enabled mailbox audit logging to determine who has logged into user mailboxes, sent messages, and other activities performed by the mailbox owner, a delegated user, or an administrator.

- Attack monitoring and prevention with Office 365 Threat Intelligence

  Contoso uses [Office 365 Threat Intelligence](https://docs.microsoft.com/office365/securitycompliance/office-365-ti) to protect their Office 365 users by making it easy to identify and address attacks, and to prevent future attacks.

- Protection from sophisticated attacks with Advanced Threat Analytics

  Contoso is using [Advanced Threat Analytics (ATA)](https://docs.microsoft.com/advanced-threat-analytics/what-is-ata) to protect itself from advanced targeted attacks.  ATA automatically analyzes, learns, and identifies normal and abnormal entity (user, devices, and resources) behavior. 

### Information protection

- Protect sensitive and highly regulated digital assets with Azure Information Protection

  Contoso determined three levels of data protection and deployed [Azure Information Protection](https://docs.microsoft.com/azure/information-protection/what-is-information-protection) labels that users apply to digital assets. For its trade secrets and other intellectual property, Contoso uses Azure Information Protection sub-labels in a scoped policy for highly regulated data that encrypts content and restricts access to specific security groups.

- Prevent intranet data leaks with Office 365 Data Loss Prevention

  Contoso has configured [Data Loss Prevention](https://docs.microsoft.com/office365/securitycompliance/data-loss-prevention-policies) policies for Exchange Online, SharePoint Online, and OneDrive for Business to prevent users from accidentally or intentionally sharing sensitive data.

- Prevent device data leaks Windows Information Protection

  Contoso is using [Windows Information Protection (WIP)](https://docs.microsoft.com/windows/security/information-protection/windows-information-protection/protect-enterprise-data-using-wip) to protect against data leakage through Internet-based apps and services and enterprise apps and data on enterprise-owned devices and personal devices that employees bring to work.

- Cloud monitoring with Microsoft Cloud App Security

  Contoso is using [Microsoft Cloud App Security](https://docs.microsoft.com/cloud-app-security/what-is-cloud-app-security) to map their cloud environment, monitor its usage, and detect security events and incidents. 

- Office 365 security monitoring with Office 365 Cloud App Security

  Contoso security administrators set up alerts with [Office 365 Cloud App Security (CAS)](https://docs.microsoft.com/office365/securitycompliance/office-365-cas-overview) to be notified of unusual or risky user activity, such as downloading large amounts of data from SharePoint Online or OneDrive for Business, multiple failed sign-in attempts, or sign-ins from unknown or dangerous IP addresses.

- Device management with Microsoft Intune

  As part of the Enterprise Management + Security (EMS) suite, Contoso uses [Microsoft Intune](https://docs.microsoft.com/intune/introduction-intune) to enroll, manage, and configure access to mobile devices and the apps that run on them. Device-based conditional access policies also require approved apps and compliant PCs and mobile devices.

### Security management

- Central security dashboard for IT with Azure Security Center

  Contoso uses the [Azure Security Center](https://docs.microsoft.com/intune/introduction-intune) for a unified view of security and threat protection, to manage security policies across its workloads, and to respond to cyberattacks.

- Central security dashboard for users with Windows Defender Security Center

  Contoso has deployed the [Windows Defender Security Center app](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-security-center/windows-defender-security-center) to its PCs and devices running Windows 10 Enterprise so that users can see their security posture at a glance and take action.


## Next step

[Deploy](deploy-microsoft-365-enterprise.md) Microsoft 365 Enterprise in your organization.

