---
title: Desktop Analytics and privacy
description: How Desktop Analytics uses data
keywords: Desktop Analytics, oms, privacy, data, diagnostic, operations management suite, prerequisites, requirements, updates, upgrades, log analytics, health, FAQ, problems, troubleshooting, error
ms.prod: w10
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: deploy
author: jaimeo
ms.author: jaimeo
ms.date: 08/25/2018
ms.localizationpriority: medium
---

[This information relates to a pre-released product which may be substantially modified before it's commercially released. Microsoft makes no warranties, express or implied, with respect to the information provided here.]

{RIGHT NOW THIS IS A BLIND CUT/PASTE OUT OF THE WA PRIVACY TOPIC--A PLACEHOLDER FOR US TO UPDATE FOR DA USE.}

# Desktop Analytics and privacy

Desktop Analytics is fully committed to privacy, centering on these tenets:

- **Transparency:** We fully document the Desktop Analytics diagnostic events (see the links for additional information) so you can review them with your company’s security and compliance teams. The Diagnostic Data Viewer lets you see diagnostic data sent from a given device (see [Diagnostic Data Viewer Overview](https://docs.microsoft.com/windows/configuration/diagnostic-data-viewer-overview) for details).
- **Control:** You ultimately control the level of diagnostic data you wish to share. In Windows 10 1709 we added a new policy to Limit enhanced diagnostic data to the minimum required by Desktop Analytics
- **Security:** Your data is protected with strong security and encryption
- **Trust:** Desktop Analytics supports the Microsoft Online Service Terms

The following illustration shows how diagnostic data flows from individual devices through the Diagnostic Data Service, Azure Log Analytics storage, and to your Log Analytics workspace:

[![Diagram illustrating flow of diagnostic data from devices](UDRimages/WA-data-flow-v1.png)](images/WA-data-flow-v1.png)

The data flow sequence is as follows:

1.	Diagnostic data is sent from devices to the Microsoft Diagnostic Data Management service, which is hosted in the US.
2.	An IT administrator creates an Azure Log Analytics workspace. The administrator chooses the location, copies the Commercial ID (which identifies that workspace), and then pushes Commercial ID to devices they want to monitor. This is the mechanism that specifies which devices appear in which workspaces.
3.	Each day Microsoft produces a "snapshot" of IT-focused insights for each workspace in the Diagnostic Data Management service.
4.	These snapshots are copied to transient storage which is used only by Desktop Analytics (also hosted in US data centers) where they are segregated by Commercial ID.
5.	The snapshots are then copied to the appropriate Azure Log Analytics workspace.
6.	If the IT administrator is using the Upgrade Readiness solution, user input from the IT administrator (specifically, the target operating system release and the importance and upgrade readiness per app) is stored in the Desktop Analytics Azure Storage. (Upgrade Readiness is the only Desktop Analytics solution that takes such user input.)


See these topics for additional background information about related privacy issues:

- [Windows 10 and the GDPR for IT Decision Makers](https://docs.microsoft.com/windows/privacy/gdpr-it-guidance)
- [Configure Windows diagnostic data in your organization](https://docs.microsoft.com/windows/configuration/configure-windows-diagnostic-data-in-your-organization)
- [Windows 7, Windows 8, and Windows 8.1 Appraiser Telemetry Events, and Fields](https://go.microsoft.com/fwlink/?LinkID=822965) (link downloads a PDF file)
- [Windows 10, version 1703 basic level Windows diagnostic events and fields](https://docs.microsoft.com/windows/configuration/basic-level-windows-diagnostic-events-and-fields-1703)
- [Windows 10, version 1709 enhanced diagnostic data events and fields used by Desktop Analytics](https://docs.microsoft.com/windows/configuration/enhanced-diagnostic-data-windows-analytics-events-and-fields)
- [Diagnostic Data Viewer Overview](https://docs.microsoft.com/windows/configuration/diagnostic-data-viewer-overview)
- [Licensing Terms and Documentation](https://www.microsoftvolumelicensing.com/DocumentSearch.aspx?Mode=3&DocumentTypeId=31)
- [Learn about security and privacy at Microsoft datacenters](https://www.microsoft.com/datacenters)
- [Confidence in the trusted cloud](https://azure.microsoft.com/support/trust-center/)
- [Trust Center](https://www.microsoft.com/trustcenter)

### Can Desktop Analytics be used without a direct client connection to the Microsoft Data Management Service?
No, the entire service is powered by Windows diagnostic data, which requires that devices have this direct connectivity.

### Can I choose the data center location?
Yes for Azure Log Analytics, but no for the Microsoft Data Management Service (which is hosted in the US).
