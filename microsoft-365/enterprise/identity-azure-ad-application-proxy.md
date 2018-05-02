---
title: "Step 16: Provide secure remote access to users"
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 03/01/2018
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection: 
- Ent_O365
- Strat_O365_Enterprise
ms.custom:
description: Understand and configure the use of Azure AD Application Proxy.
---

# Step 16: Provide secure remote access to users

*This step is optional for hybrid environments and applies to both the E3 and E5 versions of Microsoft 365 Enterprise*

![](./media/deploy-foundation-infrastructure/identity_icon-small.png)

In Step 16, you'll provide secure remote access for web-based applications like SharePoint sites, Outlook Web Access servers, or other web-based line of business applications to remote or roaming users. You do this by setting up Azure AD Application Proxy, which replaces traditional virtual private network (VPN) infrastructures and demilitarized zones (DMZ) to provide access to intranet resources. 

Typical solutions to providing access to intranet resource include deploying a virtual private network (VPN) infrastructure or setting up a demilitarized zone (DMZ) with servers that host or provide access to the intranet resource. However, when you have your on-premises user accounts and groups synchronized with Azure AD, you can use Azure AD Application Proxy to provide secure remote access for web-based applications hosted on intranet servers. Web-based applications include SharePoint sites, Outlook Web Access servers, or any other web-based line-of-business applications. 

For more information about Azure AD Application Proxy, including links to configuration information, see [How to provide secure remote access to on-premises apps](https://docs.microsoft.com/azure/active-directory/active-directory-application-proxy-get-started).


As an interim checkpoint, you can see the [exit criteria](identity-exit-criteria.md#crit-identity-step16) for this step.

## Next step

[Identity infrastructure exit criteria](identity-exit-criteria.md)
