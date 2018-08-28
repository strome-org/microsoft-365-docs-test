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


<!--This topic is the target for 3 "Learn more" links in the Admin Portal and Enterprise Agreement (aka.ms/app-overview;app-package;app-req); do not delete.-->

<!--Applications: supported/onboard/deployment -->

Microsoft and the customer’s IT team will have different responsibilities around applications in the modern workplace. 

Microsoft will install, update, and provision line-of-business applications (LOB apps) that are licensed or owned by the customer, and that have been vetted and packaged appropriately by the customer (for example, apps meet the latest packaging requirements described in this document). 

Application work items |	Customer	| Microsoft
--- | --- | ---
**Onboarding apps** |  |
App inventory	| ![yes](images/checkmark.png)	|
User management	| ![yes](images/checkmark.png)	|
Code integrity policy |	|	![yes](images/checkmark.png)
**App Packaging** |  |
Packaging and security |	![yes](images/checkmark.png) |	
App ingestion |	![yes](images/checkmark.png)	 |
System install testing |	![yes](images/checkmark.png) |	
User acceptance testing	| ![yes](images/checkmark.png) |	
**Deployment** | |
User allocation	 | ![yes](images/checkmark.png)	 |
Distribution |	|	![yes](images/checkmark.png)
Updates	| ![yes](images/checkmark.png)	 |
Decommissioning	| ![yes](images/checkmark.png) |	
**Management** | |
App license management |	![yes](images/checkmark.png)	 |
Monitoring	| ![yes](images/checkmark.png) |	![yes](images/checkmark.png)
Support	| ![yes](images/checkmark.png) |	Microsoft apps
App settings management	| ![yes](images/checkmark.png) |	

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
