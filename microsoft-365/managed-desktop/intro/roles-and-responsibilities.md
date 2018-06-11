---
title: Microsoft 365 Managed Desktop roles and responsibilities
description:  
keywords: Microsoft 365 Managed Desktop, Microsoft 365, service, documentation
ms.service: m365-md
author: jdeckerms
ms.localizationpriority: medium
ms.date: 06/06/2018
---

# Microsoft 365 Managed Desktop roles and responsibilities


<!--This topic is the target for a "Learn more" link in the Admin Portal (aka.ms/admin-access); do not delete.-->

When your organization is enrolled in Microsoft 365 Managed Desktop, what does Microsoft do for you? And what are your organization's responsibilities?

## Microsoft's roles and responsibilities

Below are a few key roles and responsibilities that will be provided to you by Microsoft.

Role or responsibility | Description
--- | ---
Account Manager |  Microsoft will provide an Account Manager as a primary point of contact for all communication. The account manager will reach out to the customer IT team with regular updates on the health of the service. 
Policy management | Microsoft will apply policy according to best practices and consider requests for policy changes. We will also make changes to your tenant as prescribed (link to be added).
App deployment | Microsoft will deploy applications to client devices using Intune. There may be some limitations on which applications will work in a modern environment. For VPN clients, Microsoft will deploy a mutually agreed Windows 10-compatible VPN client only when needed. 
End user support | Microsoft will provide end-user support for devices, Windows, and Office product suite for all enrolled users. 
IT admin support | Microsoft will provide support to your IT department via a Microsoft operations team. This team will field technical troubleshooting, change requests, and incident management. 
Security monitoring | Microsoft will monitor devices using Windows Defender ATP. Should a threat be detected, Microsoft will notify the customer, isolate the device, and rectify the issue remotely. 
Update monitoring and management | Microsoft will actively monitor devices to ensure that the latest quality, feature, and definition updates are installed. We will also manage the deployment of updates in a progressive release pattern, holding as appropriate to minimize business impact. If an issue arises, Microsoft will contact the customer. 
Device procurement | Microsoft will order and drop-ship devices to end-users or the IT distribution point of your choosing. 

## Your roles and responsibilities

Below is an additional set of common roles that are not provided by Microsoft, but are required for a successful deployment. It’s not exhaustive but is typical for most organizations. 

Role or reponsibility | Description
--- | ---
Change management | Microsoft will notify customers, in advance, when changes need to be made to the environment. The customer is required to have resources to review and approve these changes.  
Identity management | Creating user accounts, assigning users to groups, and keeping metadata up to date. 
Office 365 configuration and management | Exchange online administration, including: <br>- Email administration<br>- Mailbox and rule configuration<br>- Exchange on-premises management<br><br> Collaboration tools, SharePoint server administration, domain management, security and information policies set in the Office 365 admin portal (Microsoft will ensure Office applications are deployed to end user devices and kept up-to-date). 
End user support | The customer will provide end-user support for: <br>On site infrastructure - all network and internet connectivity, VPN infrastructure and client configuration, local conference room equipment, printers, proxy server and configuration, firewalls, etc.<br><br> Company-wide cloud resources - Email, SharePoint, collaboration services, and other cloud infrastructure that relates to the company wide technology footprint.<br><br> Line of Business applications - Custom software, 3rd party software, ERP software, design tools, and anything not created by Microsoft. 
Security monitoring and response | In the event a security incident is detected which is outside the scope of Microsoft management, we will require a list of preferred customer contacts based on the severity of the issue. The customer will be responsible for investigating and resolving incidents for devices outside of Microsoft’s management and services and ensuring that the Microsoft Operations Team is informed of any issues that may impact the service. 
Operations support | In the event a non-M365 Managed Desktop operational incident is detected, we will require a list of preferred customer contacts based on the severity of the issue. The customer will be responsible for investigating and resolving incidents for non-M365 Managed Desktop devices and services. and ensuring that the Microsoft Operations Team is informed at all times. 
Network infrastructure, including VPN | Setup, configuration and management (including troubleshooting and debugging) of all networking-related infrastructure and services, including internet connectivity, network controls, proxy configuration and remote connectivity infrastructure.<br><br> By default, M365 Managed Desktop does not specify or require a proxy. However, if one is configured (in hardware or software), there is a collection of URLs that must be allowed by the proxy. <br><br>M365 Managed Desktop does not recommend using multiple proxies. If the customer intends to use both hardware and software proxies, then they must ensure that the sets of devices gated by each proxy are not overlapping with the other proxy. The customer is responsible for troubleshooting any conflicts or incompatibilities due to multiple proxies. 
Printing | Install, maintain and administer printers and print queues. Cloud printing is a recommended solution but is not required. 
Hardware | Devices and accessories not provided by M365 Managed Desktop. M365 Managed Desktop support extends to only the provided device, docking station and included accessories. 
Mobile devices | Support for and management of mobile devices.
Apps | Customers will provide a list of apps that they want to use in their organization (beyond apps included with M365 license). Customers also provide either:<br>- Deployable package (Appx or MSI), or<br>- Installation instructions and executable file<br><br> The customer is responsible for:<br>- App license management: Having the right type and quantity of licenses<br>- App assignment: Assigning apps to Azure AD user groups<br>- App updates: Monitoring app feature and security updates, and letting Microsoft know which updates should be deployed to M365 Managed Desktop devices. 

