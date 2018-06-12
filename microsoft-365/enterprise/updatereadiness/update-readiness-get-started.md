---
title: Get started with Update Readiness
description: How to set up accounts, subscriptions, user access, workspaces
ms.prod: w10
ms.mktglfcycl: manage
ms.sitesec: library
author: Jaimeo
ms.localizationpriority: high
ms.author: jaimeo
ms.date: 06/12/2018
---

# Get started with Updated Readiness

This topic explains the steps necessary to configure your environment for Update Readiness. 

Steps are provided in sections that follow the recommended setup process:


## Entry points to Update Readiness

### From M365 Device Management {most likely for PP}
### From System Center Configuration Manager
### From Azure

In {entry point console}, click {something}, and you will go to the Update Readiness console:

{SCREENSHOT of landing page in UDR}

[![Landing page in UDR](UDRimages/UDR-landing.png)](UDRimages/UDR-landing.png)

## Set up access

**If your account is not already a global administrator**, you'll have to contact someone who is in order to proceed with setup. This dialog will show you who has the necessary permissions; select the administrators you want to contact and then select **Send**. This will send e-mail to them.

[![contact admin dialog](UDRimages/UDR-contact-admin.png)](UDRimages/UDR-contact-admin.png)


**If you are a global administrator**, click **Start** to continue with setup. You'll need to review and accept the license agreement and confirm that you have the appropriate subscription (E3 or {we should list the appropriate subscriptions explicitly}). If you don't have the appropriate subscription, you should leave the setup dialog and obtain the subscription; you can come back to setup later and continue.

### Configure user access

Update Readiness pre-configures two security groups in Azure Active Directory:

- **Workspace Owners**, who can create and manage workspaces. These accounts need owner- or co-owner-level access to an Azure subscription.
- **Workspace Contributors**, who can create and manage deployment plans in this workspace. They do not need any additonal Azure access.

[![config user access dialog](UDRimages/UDR-config-user.png)](UDRimages/UDR-config-user.png)

To add a user to either group, type their name or e-mail address in the **Enter name or email address** section of the appropriate group.

### Prepare your workspace

**If you don't already have an Azure subscription**, a dialog box will offer you the opportunity to obtain one. If you do have an Azure subscription, the portal will display all of your existing workspaces. To use an existing workspace for Update Readiness, just select it.

[![pre-existing workspaces](UDRimages/UDR-existing-workspaces.png)](UDRimages/UDR-existing-workspaces.png)

To create a new workspace, select **+ Create new workspace** and in the dialog that opens, provide a name for the new workspace, use the pull-down menu to select the Azure ID you want to use, select the region, and then click **Create**.

[![create new workspace](UDRimages/UDR-create-new-workspace.png)](UDRimages/UDR-create-new-workspace.png)

The new workspace will appear at the top of the workspace list and is pre-selected; to use the new workspace, select **Set as Workspace**, and then click **Continue** in the **Accept Permissions** dialog that opens.

 ### Complete setup

At this point, you have the option to proceed to [enrolling your devices](update-readiness-enroll-devices.md), or you can go directly to the dashboard and enroll devices later. If you go to the dashboard at this point, you will see something like this:

[![dashboard before enrollment](UDRimages/UDR-dash-not-enrolled.png)](UDRimages/UDR-dash-not-enrolled.png)

If you've come to the dashboard prior to enrolling devices, select **Connected Services** {or is it Connect devices?} to proceed with [enrolling devices](update-readiness-enroll-devices.md).

If your devices are already enrolled, you can start getting familiar with the dashboard:

## Update Readiness dashboard orientation

### Assets

#### Devices
#### Apps
Total apps
Noteworthy apps
#### Office Apps
#### Office Add-ins

### Deployment plans










## Related topics
