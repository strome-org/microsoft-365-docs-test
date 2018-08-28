---
title: Microsoft Managed Desktop operations and monitoring 
description:  
keywords: Microsoft Managed Desktop, Microsoft 365, service, documentation
ms.service: m365-md
author: jdeckerms
ms.localizationpriority: medium
ms.date: 09/24/2018
---

# Microsoft Managed Desktop operations and monitoring

<!-- Operations and monitoring: -->


## Change management

Microsoft and customers will share change management for the Microsoft Managed Desktop service. Responsibilities differ for an online service versus an on-premises server or client. 

### Change process overview

Here’s a summary of how the change process is shared between Microsoft and customers. 

**Before a change**

Microsoft will: | Customers will:
--- | ---
- Notify customers 5 days in advance for changes that require administrator action. For more information, see [change types](#change-types).<br>- For emergency changes, apply a mitigation prior to notifying. | - Read and understand notification email.<br>- Acknowledge and approve, when required.<br>- Manage internal change management processes.

**During a change**

Microsoft will: | Customers will:
--- | ---
- Deploy change for Windows 10 and Office, release security and non-security updates, as needed.<br>- Monitor telemetry and support escalations for any unexpected issues. | - Take action requested by Microsoft, based on timeframes listed in [change types](#change-types).<br>- Create a Support request, if required.

**After a change**

Microsoft will: | Customers will:
--- | ---
- Collect customer feedback to improve rollout of future changes.<br>- Monitor telemetry and support escalations for any unexpected issues. | - Manage internal change management process.<br>- Provide general feedback and specific feedback in the admin feedback tool.<br>- Train users to provide app-specific feedback using the Winbdows Feedback Hub and the Smile button in Office apps. 


### Change types

There are several types of changes that are made to the service on a regular basis. The communication channel for those changes, and the actions that customers are responsible for varies.

The following types of changes can be expected:

Change type | Notification | Customer action
--- | --- | ---
Feature updates and new service components | Email | - Communicate change to users<br>- Act as required by Microsoft<br>- Action must be taken within 48 hours
Security updates, both monthly updates and baseline settings | Email, Security Bulletin, or CVE????? | - Monthly security updates will be deployed using our [update management strategy](updates.md).<br>- Settings to mitigate a threat will be deployed to the entire organization to protect the organization. (THIS DOES NOT APPEAR TO BE A CUSTOMER ACTION)
Quality updates, including hotfixes, service updates, and non-security impacting baseline policy | Email | Will advise when required.
Emergency updates: service, configuration, or software updates requred to mitigate:<br>- Critical security risk<br>- Potential data loss<br>- Access to telemetry data for managing Microsoft Managed Desktop devices | Will advise when required.

## Standard operating procedures

This service is implemented and operated by Microsoft in your environment where you conduct other administrative activities. Microsoft is solely responsible for Microsoft Managed Desktop-specific setup, configuration and operation. 

For on-premises products, your organization takes on all the responsibility for managing operational and configuration activities.

Categories |	Actions
--- | ---
Service accounts |	Microsoft will:<br>- Implement, securely store, and manage the credentials<br>- Communicate unauthorized access or use of these credentials to your Security Operations team<br><br>Customers will:<br>- Open an informational support request with Microsoft Managed Desktop Operations when planning a change that may impact the accounts<br>- Not assign policy, multi-factor authentication, conditional access, or application deployment to the Microsoft Managed Desktop Service Accounts<br>- Not reset the password or use the credentials<br>- Open a Sev C support request to Microsoft Managed Desktop operations if suspicious activity is observed in Intune or Azure audit logs, related to these service accounts
Device Groups |	Microsoft will:<br>- Implement and manage the membership of devices within Microsoft Managed Desktop groups<br>- Use the Microsoft Managed Desktop groups to manage the assignment and release of configuration and updates to devices<br><br>Customers will:<br>- Open an informational support request with Microsoft Managed Desktop Operations when planning a change that may impact the groups<br>- Not modify the membership of any Microsoft Managed Desktop group<br>- Only use the groups to assign the following configurations:<br>    - Corporate certificates for services such as VPN, Windows Hello for Business or email encryption<br>    - Corporate Wi-Fi profile configuration<br>- Where co-management exists, explicitly exclude all Microsoft Managed Desktop groups when deploying the Configuration Manager client
Policies |	Microsoft will:<br>- Implement and manage the Microsoft Managed Desktop policies that govern the configuration state of devices within service<br>- Deploy updates, to policy or Windows, incrementally using Device Groups<br>- Explicitly exclude targeting non-Microsoft Managed Desktop groups<br><br>Customer will:<br>- Open an informational support ticket with Microsoft Managed Desktop Operations when planning a change that may impact the desired configuration state of devices<br>- Not edit or assign Microsoft Managed Desktop policies to devices or users not managed by the Microsoft Managed Desktop service
Windows Defender Advanced Threat Protection	| Microsoft will:<br>- Monitor and investigate devices within the scope of the Microsoft Managed Desktop service<br><br>Customer will:<br>- Open an informational support ticket with Microsoft Managed Desktop Operations when planning a change that may impact the monitoring or investigative capabilities of the Microsoft Managed Desktop Security Operations Center
Microsoft Store for Business |	Microsoft will:<br>- Configure and maintain the Windows Autopilot profile for the Microsoft Managed Desktop service<br><br>Customer will:<br>- Open an informational support ticket with Microsoft Managed Desktop Operations when planning a change that Open might impact the access to the Store or modify the Microsoft Managed Desktop Windows Autopilot profile<br>- Not modify the configuration of the Microsoft Managed Desktop Windows Autopilot profile or add/remove assigned devices
Certificates |	Customer will:<br>- Open an informational support ticket with Microsoft Managed Desktop Operations 60 days prior to any certificate expiring<br>- Update all certificates that are required to configure:<br>    - Certificate profiles<br>    - VPN profiles<br>    - Wi-Fi profiles



