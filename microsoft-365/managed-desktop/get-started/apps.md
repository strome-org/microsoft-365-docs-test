---
title: Preparing apps for Microsoft Managed Desktop 
description:  
keywords: Microsoft Managed Desktop, Microsoft 365, service, documentation
ms.service: m365-md
author: jdeckerms
ms.localizationpriority: medium
ms.date: 09/24/2018
---

# Preparing apps for Microsoft Managed Desktop

<!--This topic is the target for 3 "Learn more" links in the Admin Portal and Enterprise Agreement (aka.ms/app-overview;app-package;app-req); also target for link from Online resources (aka.ms/app-overviewmmd-app-prep) do not delete.-->

<!--Applications: supported/onboard/deployment -->
 
Microsoft and Microsoft Managed Desktop customers have equally critical, yet different responsibilities around applications used with Microsoft Managed Desktop.

## Microsoft responsibilites
**Office 365 apps**
Microsoft will provide full service for the deployment, update, and support of specific Office 365 apps. All users will receive the base set of Office 365 click to run, 64 bit version of applications included in the device’s image so that a user can quickly become productive. The Project and Visio applications in of the Office 365 suite are licensed separately.  Microsoft Managed Desktop will provide deployment groups allowing the IT Administrator to manage licenses and deploy these applications appropriately for their organization. Microsoft will support end users of these applications through the Microsoft Managed Desktop Support channels.

**Line-of-business apps**
Microsoft provides tooling for IT Administrators to manage and deploy their Line of Business applications to end users as a part of the Intune product. Microsoft will support application deployment issues as detailed in [Line-of-business applications](#line-of-business-applications) 

**Deploy with Intune**
Intune will be linked to the **Microsoft Store for Business** during Microsoft Managed Desktop onboarding allowing procured apps to be deployed through Intune. Microsoft will also deploy the web-based version of the Company Portal to end users so that IT Administrators can provide a self-service experience for end users.

**App management**
Microsoft may identify restricted applications which are not suitable for the modern workplace because of their system impact. When such an application is identified Microsoft will notify the customer and that application will need to be removed from the tenant. 

## Customer responsibilities
The Office 365 Suite is core to Microsoft’s productivity offerings and is included in the Microsoft 365 License for all Microsoft Managed Desktop users. While Microsoft deploys, updates, and supports Office Applications to Microsoft Managed Desktop Devices there are still some areas for which the customer is responsible.
- **Assign licenses** - Customers are responsible for  assigning of the appropriate licenses to end users for Office 365. 
- **Add users to security groups** - For customers with users that need Project or Visio the IT administrator must add that user to the appropriate deployment groups. IT administrators are also responsible for managing end of life for that user. 
- **Deploy Office 365 Add Ons** - Customers are responsible for deploying of any plugins to the Office 365 suite which are deemed necessary. 

Since line-of-business (LOB) apps are unique for each customer, customers are responsible for managing all applications within their organization not deployed by Microsoft. This includes:
- Deciding which apps are needed and who needs them
- Assigning apps to those users
- Create and maintain Azure Active Directory (AD) groups for managing app assignments 

Once the core set of LOB apps has been identified the customer will procure, license, package, and test those applications in the Microsoft Managed Desktop environment. The customer must upload and deploy applications to Intune to deploy, update, and decommission their LOB applications. Customers are responsible for managing LOB apps support for their users. 

## Office applications
As part of the Microsoft 365 E5 license, Office 365 Standard Suite (64 Bit) is deployed by Microsoft. 

For details, see [Technologies and devices](../intro/technologies-and-devices.md#technologies) <!--- and the other applications licensed under Office 365 E5 may be deployed by the customer using Intune’s deployment tools.-->

## Line-of-business applications
This table summarizes responsibilities across the different phases for line-of-business (LOB) applications. 

Application work items |	Customer	| Microsoft
--- | --- | ---
**Onboarding apps** |  |
Identify applications needed for targeted user groups	| ![yes](images/checkmark.png)	|
Create and manage Azure AD groups for app deployment | ![yes](images/checkmark.png)	|	
**App Packaging** |  |
Package apps to meet Intune deployment standards |	![yes](images/checkmark.png) |	
Upload apps to Intune |	![yes](images/checkmark.png)	 |
Test apps in Microsoft Managed Desktop environment |	![yes](images/checkmark.png) |	
Test apps with end users	| ![yes](images/checkmark.png) |	
**Deployment** | |
Manage and assign users to applications	 | ![yes](images/checkmark.png)	 |
Intune deployment tools delivers application to remote clients|	|	![yes](images/checkmark.png)
Identify and deploy application updates through Intune | ![yes](images/checkmark.png)	 |
Unistall and remove applications when they have been retired	| ![yes](images/checkmark.png) |	
**Management** | |
Procure and assign licenses |	![yes](images/checkmark.png)	 |
Provide end-user support for line-of-business apps	| ![yes](images/checkmark.png) |
Manage app settings remotely	| ![yes](images/checkmark.png) |

## Application restrictions

It’s important that your applications won’t impact your Microsoft Managed Desktop environment. Microsoft can decide not to deploy applications that include (but are not limited to) any of the areas below.

Applications and drivers like these will often affect the ability of devices to upgrade seamlessly and need to be evaluated to see if they would impact Microsoft Managed Desktop SLAs. Microsoft can decide to remove from the system any application that negatively impacts performance and reliability of Microsoft Managed Desktop devices.

### Prohibited app classes

Certain application types are not permitted on Microsoft Managed Desktop devices because they have been shown to affect the ability to keep Microsoft Managed Desktop devices up to date:
- 3rd party anti-virus, security, or audit software
- Legacy versions of Microsoft software

### Restricted app behaviors

Certain application behaviors can be either be detrimental to user experience or present a security risk to Microsoft Managed Desktop devices. Applications which have the following behaviors are not allowed on Microsoft Managed Desktop devices and Microsoft may prohibit these apps from our systems. 
- Does not spawn long running background processes
- Does not add itself to the startup path in the OS
- Does not install or depend on background services
- Does not call undocumented APIs
- Does not have extension managers 
- Does not add code or memory to important or frequently used code paths in the operating system (can’t hook I/O)

### Driver deployment

Drivers have a unique ability to cause hardware and kernel mode failures on windows device and, consequently, should be monitored to ensure they are not adversely affecting Microsoft Managed Devices devices. 
- Only drivers signed by the Windows Hardware Quality Lab will be deployed to Microsoft Managed Desktop Devices
- Only drivers which are deployed through the Windows Update channel are permitted
- If a driver does not come through the Windows Update channel it must be reviewed and approved by the Microsoft Managed Desktop team before deployment. If approved, it may still be removed from the system if it fails to meet quality measures.
- If authoring drivers in-house ensure that they are developed to the standards outlined at https://aka.ms/udriver

## Resources
While many services are out of scope for Microsoft Managed Desktop operations there are services which Microsoft offers which may help the customer manage their applications.

### Windows Upgrade Readiness
A key part of setting up new Microsoft Managed Devices is understanding which apps are needed to for device users. Windows Upgrade Readiness is a Microsoft tool which helps enterprises understand the application landscape inside their company, and helps themto review key data about those applications:
- **Application usage** - Telemetry data is used to monitor application usage
- **Application compatibility** - Upgrade Readiness looks at each application and sees how broadly it has been deployed on the latest version of Windows 10 and assesses how to identify if it is “Ready for Windows”. This data helps focus testing efforts so on applications which aren’t already broadly adopted.

### Intune application deployment
Application management can be handled through the Microsoft Managed Desktop Admin portal, or through the Intune portal. Intune’s app management portal shows applications deployed for Windows, Android, and iOS. Microsoft Managed Desktop Admin portal limits the view to Windows 10 applications. Both are available through the Azure Portal. 
- [Intune app management basics](https://docs.microsoft.com/intune/app-management)
- [Add a Windows 32 application](https://docs.microsoft.com/intune/lob-apps-windows)
- [Add web applications](https://docs.microsoft.com/intune/web-app)
- [Assign and deploy apps to groups](https://docs.microsoft.com/intune/apps-deploy)

### Application packaging standards
To deploy Windows 32 applications through Intune they must be packaged as either a single .MSI, an .appx, or .MSIX. The most common package type for Intune is currently .MSI.
<!---
Commenting out while updating apps topics
## Supported applications

It’s important that your applications won’t impact your Microsoft Managed Desktop environment. Microsoft can decide not to deploy applications that include (but are not limited to) the following: 

- Non-Microsoft security, encryption, or audit-related applications
- Windows 32 applications which are not compatible with the Microsoft Managed Desktop Code Integrity Policies
- Windows 32 applications dependent on non-Windows Hardware Quality Lab (WHQL) signed drivers
- Windows 32 applications dependent on Windows Hardware Quality Lab (WHQL) signed drivers where drivers demonstrate reliability issues (measured through Windows telemetry)
- Windows 32 applications with auto-updaters turned on
- Drivers which are not WHQL signed
- Legacy versions of Microsoft software

Applications and drivers like these will often affect the ability of devices to upgrade seamlessly and need to be evaluated to see if they would impact Microsoft Managed Desktop SLAs. Microsoft can decide to remove from the system any application that negatively impacts performance and reliability of Microsoft Managed Desktop devices.

## Onboard applications

When planning to onboard apps to your Microsoft Managed Desktop environment, there are a couple of items for customers to plan and be prepared for:

- Identify apps – Decide which applications are important for their environment.
- Create Azure AD security groups – Create and maintain Azure AD security groups for each set of users that will receive applications.
If a customer requests, Microsoft Managed Desktop Operations can configure and provide a Device Guard policy with exemptions for managed installers and signed exceptions. 

## Application deployment process

This is the process for packaging, and deploying applications:

![Analyze, package, upload, target, deploy, test](images/app-deployment.png)
 
### Analyze existing application inventory

Customers need to decide which applications to deploy in their Microsoft Managed Desktop environment. They can use Windows Upgrade Readiness to identify and catalog a list of applications used by their company. This involves deploying a script to existing devices, which catalogs all the applications on any given device. That information is reported through the Windows telemetry pipeline and populates the Upgrade Readiness Report. 

Microsoft recommends deploying only the latest version of an application and replacing or retiring applications that do not meet modern standards.

For more information, see [Manage Windows upgrades with Upgrade Readiness](https://docs.microsoft.com/windows/deployment/upgrade/manage-windows-upgrades-with-upgrade-readiness).

### Package applications

The customer must create a package which complies with Intune deployment standards. The package must be one of these:

- an appx file
- an  appx bundle
- a single file MSI with all install dependencies chained as a part of the install
These applications will be added to the Microsoft Managed Desktop portal as LOB apps  and deployed through Intune. For more information, see Add a Windows line-of-business app to Microsoft Intune. 

Microsoft can provide guidance on packaging applications so that they are deployable through Intune. 

This process can be done by an in-house packaging team or customers can contract separately through Microsoft Consulting Services and other providers to package applications to meet Intune requirements. 

### Upload applications

Customers upload apps through Microsoft Managed Desktop admin portal, and then assign users to groups for app assignment. 

### Deploy applications

Microsoft uses Intune to deploy modern apps to devices based on the groups assigned by the customer.


### User acceptance testing

Customers are responsible for validating the application and approving its use before it is deployed widely.
--> 
