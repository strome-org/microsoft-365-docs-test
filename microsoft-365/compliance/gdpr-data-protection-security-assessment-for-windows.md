---
title: Data protection, security, and assessment for Windows
description: Understand how data is protected, secured and assessed for Windows
keywords: Microsoft 365, Microsoft 365 documentation, GDPR, Windows
author: DaniHalfin
audience: microsoft-business
ms.prod: Microsoft-365-enterprise
ms.topic: article
ms.date: 05/24/2018
ms.author: daniha
audience: itpro
ms.collection: GDPR
---
# Data protection, security, and assessment for Windows

## Privacy by design

[Microsoft](https://privacy.microsoft.com/privacystatement) is committed to protecting Windows and Windows users and takes considerable measures to prevent personal data breaches from occurring as a means of maintaining customer trust. All Windows products receive privacy reviews before they are released to market to make certain that personal data is protected and the requirements of the GDPR are met. Windows conducts privacy reviews for all product updates that relate to personal data. Windows privacy reviews make sure that Windows products collect personal data that is adequate, relevant and limited to what is necessary in relation to the purpose for which they are processed.

Microsoft uses Windows diagnostic data to inform decisions and focus efforts to provide the most robust, most valuable platform for your business and enable the people who count on Windows to be as productive as possible. Microsoft adheres to the principle of data minimization and collects only the data needed to provide and improve its products and services. For example, before we allow a new data element to be collected at the non-optional Basic level, the data element must be approved as being required to keep Windows up-to-date and secure. We also aggregate Windows diagnostic data in instances where doing so is compatible with the intended use of the data.  For example, when we receive information about which users or devices are active within a given time period, we aggregate that data to provide the following business metrics:  Daily Active users, Daily active Devices, Monthly Active Users, Monthly Active Devices. If we determine that such information has been inadvertently collected, we delete the data. Additionally, sensitive data is stored in a different folder with more restrictive access permissions. To get access to sensitive data, employees must complete privacy training and demonstrate business justification to access sensitive data.

## Data security

Microsoft internally documents and disseminates its standard operating procedures, which include defined roles and responsibilities to implement the Microsoft Security Policy (MSP), the Microsoft Security Policy Program (MSPP), and [Operational Security Assurance](https://www.microsoft.com/en-us/SDL/OperationalSecurityAssurance) (OSA), which are standard operating procedures reviewed and approved periodically. Some guiding principles of the MSP include defense-in-depth, audit and monitoring, and least-privilege.
Data security for Windows is reviewed by the appropriate security team, and security measures are tested at least annually and evaluated to verify their ongoing effectiveness. Depending on the type of data, we also use authentication and access controls to secure it. For example, sensitive data is stored in a different folder with additional access restrictions.

Microsoft redundantly stores some Windows data in multiple geographical locations for disaster recovery and geographical load-balancing purposes, and periodically opens new data centers to maintain a high level of resiliency and security. Data is transferred according to stringent requirements of the EU-US and Swiss-US [Privacy Shield](https://www.privacyshield.gov/welcome) frameworks, which defines the use and treatment of personal data received from the EU, and access and recourse we must provide to residents of the European Economic Area (EEA) and Switzerland regarding their data. In accordance with Privacy Shield requirements, we transfer data only for limited and specified purposes, and adhere to stringent data security requirements. Windows makes sure that data communicated through Windows services is encrypted during transmission over external networks using Transport Layer Security (TLS). Microsoft’s Privacy Shield commitment is enforceable under US law.

Removable or portable encrypted data storage devices, including external hard drives, tapes, or other types of media, must use software or hardware encryption methods defined by Microsoft Policy. Additionally, decryption keys for these devices are not kept with the media—they must be stored in separate systems or locations. If the media and keys are to be transferred to another individual, location, system, or organization, they are exchanged through separate channels and the agents performing the transfer must be authenticated to prevent social engineering attacks.

BitLocker Drive Encryption must be enabled on all devices that process personal data (except those that maintain persistent, strong physical protection, such as data centers) to help reduce the risk of data compromise if a device is stolen. Microsoft has the following measures in place to secure access to user data:

* Role-based access controls that limit access to those who have a legitimate business purpose for accessing personal data
* Procedures that determine which roles should have access to the data, and periodically verify that only appropriate individuals have access
* Prerequisites for access that are defined and enforced—for example, completion of privacy training prior to access
* Controls that limit physical access to locations where data is stored or accessible

Microsoft maintains logical, administrative, technical, and organizational controls designed to provide a high level of security for the data we collect and process.  Among other measures, we employ dedicated threat management teams that proactively anticipate, prevent, and mitigate malicious access.  Internal security measures such as port scanning, perimeter vulnerability scanning, and intrusion detection allow us to detect and prevent malicious access.

Windows Products Security Policies protects and controls physical media within and outside of controlled areas. A controlled area could be an office building that requires authentication before entry. Secure shipping is required for certain scenarios involving the transportation of assets from one location to another. Secure shipping includes:

* Chain-of-custody tracking and documentation throughout the transportation
* Physical control of assets by accountable personnel at all times
* Tamper-evident seals on packages and containers
 
Microsoft also has systems and processes for incident response and disaster recovery. For more information, see [Windows Breach Notification Under the GDPR](gdpr-breach-Windows.md).

## Audit

Windows features and services that collect personal data must undergo a security review before being put in production or added to released products. Security reviews are handled by Microsoft security professionals.

Once personal data has been collected by Microsoft, the data storage and processing at Microsoft data centers are constantly monitored for potential or emerging threats to data security.

Where internal services claim compliance with standards such as ISO27001, independent external audits help promote compliance. Links to Windows-relevant ISO 27001 audit reports are provided later in this article. Also, Windows products internally audits feature teams at least annually to help promote compliance with internal privacy and security standards.

## Backup and restore

Windows products have limited need to backup Windows diagnostic data. Microsoft will back up online services upon request. This is based on a defined schedule and upon request of the service teams. Data is retained according to the data type identified by the property.

Confidential physical documents are cross-shredded or incinerated when the document is retired. Microsoft buildings have a container where documents can be brought for secure disposal.

## Windows services

Processes are in place to enable all Microsoft production and internal services to follow Microsoft's security and privacy policies. Services undergo regular security risk assessments and audits to identify new risks, and work items or exceptions are created to address or minimize risks.

Windows services handle both customer data and data about customers to provide needed security, privacy, and integrity. This applies to all stages of the data lifecycle (creation, transmission, storage, and retention) and across multiple versions of a service. Processes are in place to enable services to follow Microsoft policies regarding personal data and all applicable government regulations, including rules about handling, storage, access, discovery, and auditing of customer data.

Services are designed for operational security, in addition to following best practices for software security included in the [Security Development Lifecycle](https://www.microsoft.com/sdl/) (SDL). Processes are in place to enable services to follow all policies covering personal data and other business-required policies. This includes compliance, audit, and verification with all applicable government regulations.

## Standards compliance

The Governance, Risk Management, and Compliance (GRC) team promotes compliance in three phases –

* **Plan** — External requirements, management direction, and business objectives are converted to policies, standards, and baselines, which become control objectives and requirements
* **Build** — Control activities are designed and delivered to make certain that software and infrastructure requirements are met by each engineering team
* **Run** —Products Services and infrastructure are operated and monitored to verify that compliance is maintained

Some aspects of Windows products that process personal data are compliant with ISO/IEC 27001:2013 (certificate numbers IS 665452, IS 663486). The ISO/IEC 27001:2013 standard provides a framework to enable accessibility, confidentiality, and integrity of information while staying within legal compliance. 

The following [ISO Reports](https://servicetrust.microsoft.com/ViewPage/MSComplianceGuide) provide evidence of this compliance:

* [Windows – ISO 27001-2013 Certificate for Windows Defender Advanced Threat Protection](https://servicetrust.microsoft.com/ViewPage/MSComplianceGuide?command=Download&downloadType=Document&downloadId=067b981f-1b44-4eec-ad82-9185b6c42e65&docTab=4ce99610-c9c0-11e7-8c2c-f908a777fa4d_ISO_Reports)
* [Windows - ISO 27001 Statement of Applicability for Windows Defender Advanced Threat Protection](https://servicetrust.microsoft.com/ViewPage/MSComplianceGuide?command=Download&downloadType=Document&downloadId=0a78b774-f69e-47bd-97f9-60176c08fd8e&docTab=4ce99610-c9c0-11e7-8c2c-f908a777fa4d_ISO_Reports)
* [Windows - ISO 27001 Audit Assessment Report for Windows Defender Advanced Threat Protection](https://servicetrust.microsoft.com/ViewPage/MSComplianceGuide?command=Download&downloadType=Document&downloadId=834d282a-a0f2-45a3-bc3d-22395145bad2&docTab=4ce99610-c9c0-11e7-8c2c-f908a777fa4d_ISO_Reports)

### Service providers and contracts

Through its contracts with them, Microsoft contractually obligates entities that act as processors of personal data on behalf of Microsoft to follow the requirements of the GDPR.

Microsoft requires third-party suppliers service providers (data processors) who collect, store or process customer, partner or employee personal information on Microsoft’s behalf to be compliant with Microsoft’s Supplier Security and Privacy Assurance Program (MSSPA) as a condition of doing business with Microsoft. Service providers must self-attest annually to compliance with the [MSSPA Data Protection Requirements (DPR)](http://download.microsoft.com/download/A/B/D/ABDDEEC2-EA77-4187-883A-9AE343EB4201/Supplier-Data-Protection-Requirements_en-US.pdf), an agreement that sets out data protection requirements that align with the EU General Data Protection Regulation (GDPR). Microsoft may accept the following alternative compliance attestation or assessment, depending on the nature and sensitivity of the data:

* Third-party auditor assessment plus ISO 27001 Certification

OR

* American Institute of Certified Public Accountants Service Organization Control (SOC 2) Report with security coverage

OR

* National Institute of Standards and Technology (NIST) 800-53 Report

Other partners who process personal data but do not participate in the MSSPA program are subject to separate contracts that require the partners to participate in ensuring compliance with the GDPR. These contracts may include data use restrictions, data handling requirements, audit rights, and other terms as appropriate under the circumstances.

If high-risk or sensitive data is processed by a service provider or other partner, Microsoft may additionally require the service provider or partner to submit to an independent audit of its records and facilities to verify compliance. If a service provider or partner cannot show compliance with the DPR (or similar requirements), Microsoft will stop working with that service provider or vendor.