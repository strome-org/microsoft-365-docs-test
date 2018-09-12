---
title: Prerequisites for Microsoft Managed Desktop
description:  
keywords: Microsoft Managed Desktop, Microsoft 365, service, documentation
ms.service: m365-md
author: jdeckerms
ms.localizationpriority: medium
ms.date: 09/24/2018
---

# Prerequisites for Microsoft Managed Desktop

<!--This topic is the target for a "Learn more" link in the Admin Portal (aka.ms/prereq-azure); do not delete.-->
<!--from Prerequisites -->

Success with Microsoft Managed Desktop begins with your infrastructure meeting well-known, documented, and agreed-upon prerequisites, which are outlined in this topic.

Microsoft FastTrack is available to help customers meet these requirements and help you prepare to participate in Modern Workplace as a Service. For more information, see [Microsoft FastTrack](https://fasttrack.microsoft.com/about). 


| Area | Prerequisite details |
| --- | --- |
| Licensing | Microsoft 365 E5 license<br><br>This license includes Office 365 E5, Windows 10 Enterprise E5 & Enterprise Mobility + Security (EMS) E5. For more information, see [Microsoft 365 licensing](https://www.microsoft.com/Licensing/product-licensing/microsoft-365-enterprise.aspx). |
| Connectivity |	All Microsoft Managed Desktop devices need to connect from your organization's internal network to Microsoft service endpoints, including:<ul><li>Windows Update</li><li>Microsoft Store for Business</li><li>Azure Active Directory</li><li>Windows Error Reporting</li><li>Online Crash Analysis</li><li>Connected User Experience and Telemetry</li><li>OneDrive app for Windows 10</li></ul><br>The full list of required IPs and URLs can be found in [Network Configuration](../get-ready/network.md). |
| Azure Active Directory |	Azure Active Directory (Azure AD) is required for Microsoft Managed Desktop. You can:<ul><li>Configure Azure AD as the source of authority for all user accounts</li></ul>or<ul><li>Use Azure AD Connect, version 1.1.654.0, or later to synchronize user accounts must be synchronized from on-premises Active Directory. <p> [Password writeback](https://docs.microsoft.com/azure/active-directory/authentication/howto-sspr-writeback) is required if you use Azure AD Connect.</li></ul> For more information, see [Azure AD Connect](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect). |
| Authentication |	If your organization is synchronizing accounts from an on-premises Active Directory, you must configure one of these in Azure AD Connect:<ul><li>Password Hash Synchronization (recommended)</li><li>Pass-Through Authentication</li><li>Federation with ADFS</li></ul>For more information on Authentication options with Azure AD, see [Azure AD Connect user sign-in options](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect-user-signin). |
| Office 365 |	It is highly recommended that the following services are migrated to the cloud:<ul><li>Email - Migrate to cloud-based mailboxes, Exchange online or be configured with Exchange Online Hybrid with Exchange 2013 or higher, on-premises.</li><li>Files & Folders – Migrate to SharePoint Online/Office 365.</li><li>Skype for Business – Migrate to Skype for Business Online.</li><li>Device management - Microsoft Intune, A cloud-only MDM solution (non-hybrid) is required, which allows IT admins to manage Microsoft Managed Desktop devices using a web console that can be accessed from anywhere in the world. Microsoft Intune is the required MDM solution.</li></ul><br>For more information, see [Microsoft Intune](https://www.microsoft.com/cloud-platform/microsoft-intune). |
| Data back-up and recovery |	Microsoft Managed Desktop requires files to be synced to OneDrive for Business for protection. Any files not synced to OneDrive for Business are not guaranteed by Microsoft Managed Desktop and may be lost during device exchanges, or support calls that require a device reset.  |

[Learn how to meet the prerequisites for Microsoft Managed Desktop enrollment.](../get-ready/index.md)