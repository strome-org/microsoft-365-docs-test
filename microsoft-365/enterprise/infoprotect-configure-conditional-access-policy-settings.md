﻿---
title: "Step 2: Configure conditional access policies"
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 03/02/2018
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection: Ent_O365
ms.custom:
- Strat_O365_Enterprise
description: Understand the role of and configure conditional access policies.
---

# Step 2: Configure conditional access policies

*This step is required and applies to both the E3 and E5 versions of Microsoft 365 Enterprise*

Conditional access policies are settings that specify the conditions under which access for a user or device is granted or denied. For example, you could configure a conditional access policy that permits access for a user under the condition that they use multifactor authentication.

In Step 2, you configure conditional access policies that provide additional security for sign-in and access to information for both user sign-in and for devices. There are two types of settings:

- **Common settings, regardless of workload:** For the details of common identity and device access policies for the baseline, sensitive, and highly regulated security levels, see [Identity and device access policies overview].(identity-device-policies.md) .
- **Workload-specific settings:** For Exchange Online, implement the settings in [Secure email recommended policies](secure-email-recommended-policies.md) for the three levels of security. For SharePoint Online, implement the settings in both [Secure email recommended policies](secure-email-recommended-policies.md) and [Recommended secure document policies](sharepoint-file-access-policies.md). 

>[!Note]
>Although these conditional access settings provide additional security for identity and sign-in, they also affect sign-in for devices and device access that rely on Intune settings implemented in [Phase 5: Mobile device management](mobility-infrastructure.md). For this reason, these conditional access policies are described here, rather than [Phase 2: Identity](identity-infrastructure.md).
>

The result of this step is that you have configured conditional access policies for common settings, Exchange Online, and SharePoint Online for the three levels of security.

As an interim checkpoint, see the exit [exit criteria](infoprotect-exit-criteria.md#crit-infoprotect-step2) corresponding to this step.

## Next step

[Step 3: Configure classification for your environment](infoprotect-configure-classification.md)
