---
title: Device configuration 
description: Learn about the default policies applied to Microsoft Managed Desktop devices.
keywords: Microsoft Managed Desktop, Microsoft 365, service, documentation
ms.service: m365-md
author: jdeckerms
ms.localizationpriority: medium
ms.date: 09/24/2018
---

# Device configuration


<!--This topic is the target for a "Learn more" link in the Enterprise Agreement (aka.ms/dev-config); do not delete.-->

<!-- Device configuration-->

When a new Microsoft Managed Desktop device is being provisioned, we ensure that the right configuration, optimized for Microsoft Managed Desktop, is in place. This includes a set of default policies that are configured as part of the onboarding process. To avoid conflicts, these policies should not be altered. 

Devices will arrive with a signature image, then join the Azure Active Directory domain when the first user logs in. The device will automatically install required policies and applications without any IT intervention needed.

## Why MDM over Group Policy

There are a few reasons to use mobile device management (MDM) instead of Group Policy:

- Security - MDM policies are more secure in the modern world. Group Policy designed to work best with on-premises identity. MDM designed to work best with cloud identity management (Azure Active Directory (Azure AD)).
- Reliability - MDM policies provide more reliable policy deployment. MDM settings overwrite Group Policy Object (GPO) policies. Starting with Windows 10, version 1803, MDM settings will be prioritized over the Group Policy values. This supports customers moving to modern management. 
- Align with Microsoft Managed Desktop vision - Better monitoring on policy deployment. Support ring-based approach to gradually rollout policy changes with capability to pause / resume deployment when necessary.

## Default policies

This table highlights the default polices that are applied to all Microsoft Managed Desktop devices during device provisioning. To avoid conflict, these policies should not be altered. All detected changes not approved by Microsoft Managed Desktop Operations Team to objects managed by Microsoft Managed Desktop will be reverted.

Policy | Description
--- | ---
Security baseline | [Microsoft security baseline](https://docs.microsoft.com/windows/device-security/windows-security-baselines) for MDM is configured for all Microsoft Managed Desktop devices. This baseline is the industry-standard configuration. It is publicly released, well tested, and has been reviewed by Microsoft security experts to keep Microsoft Managed Desktop devices and apps secure in the modern workplace. <br><br>To mitigate threats in the constantly-evolving security threat landscape, the Microsoft security baseline will be updated and deployed to Microsoft Managed Desktop devices with each Windows 10 feature update.<br><br>For more information, see [Security baseline for Windows 10](https://blogs.technet.microsoft.com/secguide/2017/10/18/security-baseline-for-windows-10-fall-creators-update-v1709-final/).
Microsoft Managed Desktop recommended security template | A set of recommended changes to the security baseline that optimize user experience.  These changes are documented in the Security Addendum. Updates to the policy addendum occur on an as needed basis.  
Device compliance | These policies are configured by default for all Microsoft Managed Desktop devices. A device is reported as non-compliant when one of the following security conditions is not met:<br>- BitLocker Device Encryption enabled, to protect data on devices. For more information, see [Overview of BitLocker Device Encryption in Windows 10.](https://docs.microsoft.com/windows/security/information-protection/bitlocker/bitlocker-device-encryption-overview-windows-10)<br>- Secure Boot enabled and enforced, to validate firmware images on devices before they can execute. For more information, see [Secure boot and device encryption overview.](https://docs.microsoft.com/windows-hardware/drivers/bringup/secure-boot-and-device-encryption-overview)<br>- Password required to access Microsoft Managed Desktop devices.
Update deployment | Use Windows Update for Business (WUfB) to perform gradual deployment of software updates. IT admins can’t modify settings for the deployment ring policies. For more information on ring-based deployment, see [How updates are handled](../working-with-managed-desktop/updates.md).
Telemetry | Devices will be set to provide Enhanced diagnostic data to Microsoft under a known commercial identifier. For customers in General Data Protection Regulation (GDPR) regions, end users can reduce the level of diagnostic data that is provided. You can customize this, but there will be a reduction in service. For more information, see [Configure Windows diagnostic data in your organization.](https://docs.microsoft.com/windows/privacy/configure-windows-diagnostic-data-in-your-organization#enhanced-level)

## Advanced policies

 These are the additional policies that can be configured for a more secure/locked-down environment, for highly-regulated industries.

 Policy | Description
 --- | ---
 Advanced capabilities | Windows Information Protection (WIP) & Azure Information Protection (AIP) are used to protect enterprise data, by only allowing access to certain individuals, or a subset of applications/services. For more information, see<br>- [Protect your enterprise data using Windows INformation Protection](https://docs.microsoft.com/windows/threat-protection/windows-information-protection/protect-enterprise-data-using-wip)<br>- [Azure Information Protection client administrator guide](https://docs.microsoft.com/information-protection/rms-client/client-admin-guide)<br>- [Microsoft Managed Desktop Security Addendum](?)






