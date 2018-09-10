---
title: Get started with Desktop Analytics
description: How to set up accounts, subscriptions, user access, workspaces
ms.prod: w10
ms.mktglfcycl: manage
ms.sitesec: library
author: Jaimeo
ms.localizationpriority: medium
ms.author: jaimeo
ms.date: 09/10/2018
---

[This information relates to a pre-released product which may be substantially modified before it's commercially released. Microsoft makes no warranties, express or implied, with respect to the information provided here.]

# Get started with Updated Readiness

This topic explains the steps necessary to configure your environment for Desktop Analytics. 

Steps are provided in sections that follow the recommended setup process:


## Entry points to Desktop Analytics
{Which of these are functional currently?}

### From M365 Device Management {most likely for PP}
### From System Center Configuration Manager
### From Azure

In {entry point console}, click {something}, and you will go to the Desktop Analytics console:


[![Landing page in UDR](UDRimages/UDR-landing.png)](UDRimages/UDR-landing.png)

## Set up users and workspace

**If your account is not already a global administrator**, you'll have to contact someone who is in order to proceed with setup. This dialog will show you who has the necessary permissions; select the administrators you want to contact and then select **Send**. This will send e-mail to them.

[![contact admin dialog](UDRimages/UDR-contact-admin.png)](UDRimages/UDR-contact-admin.png)


**If you are a global administrator**, click **Start** to continue with setup. You'll need to review and accept the license agreement and confirm that you have the appropriate subscription (E3 or {we should list the appropriate subscriptions explicitly}). If you don't have the appropriate subscription, you should leave the setup dialog and obtain the subscription; you can come back to setup later and continue.

### Configure user access

Desktop Analytics pre-configures two security groups in Azure Active Directory:

- **Workspace Owners**, who can create and manage workspaces. These accounts need owner- or co-owner-level access to an Azure subscription.
- **Workspace Contributors**, who can create and manage deployment plans in this workspace. They do not need any additonal Azure access.

[![config user access dialog](UDRimages/UDR-config-user.png)](UDRimages/UDR-config-user.png)

To add a user to either group, type their name or e-mail address in the **Enter name or email address** section of the appropriate group.

### Prepare your workspace

**If you don't already have an Azure subscription**, a dialog box will offer you the opportunity to obtain one. If you do have an Azure subscription, the portal will display all of your existing workspaces. To use an existing workspace for Desktop Analytics, just select it.

[![pre-existing workspaces](UDRimages/UDR-existing-workspaces.png)](UDRimages/UDR-existing-workspaces.png)

>[!NOTE]
>If you are already using Windows Analytics, you can just select the workspace you're using for that from this list and all data and configuration will transfer to Desktop Analytics.

To create a new workspace, select **+ Create new workspace** and in the dialog that opens, provide a name for the new workspace, use the pull-down menu to select the Azure ID you want to use, select the region, and then click **Create**.

[![create new workspace](UDRimages/UDR-create-new-workspace.png)](UDRimages/UDR-create-new-workspace.png)

The new workspace will appear at the top of the workspace list and is pre-selected; to use the new workspace, select **Set as Workspace**, and then click **Continue** in the **Accept Permissions** dialog that opens.

### Provision the reverse datapump {maybe we can come up w/ a friendlier term for this}

You will need someone with global administrator permissions to complete these steps.

1. Give a security principal in your Azure Active Directory (AAD) tenant access to the MALogAnalyticsReader application 
the admin consent for the reserveDataPump app:  {I would clean up this sentence but I'm not totally sure what it's trying to say} {also, the provided link in the OneNote just takes me to Microsoft.com--so I guess there's some piece of UI we are trying to show here?}
2. Log into the Azure Portal (http://portal.azure.com) with your AAD acount. If you are presented with a dialog asking permission, approve it.
3. Search Azure resources for a resource of **type=LogAnalytics** which has the same name as the OMS workspace you created. In this example, the workspace is "MA-Smoke-EUS".
4. Click the workspace name to see the details, and then select **Access control (IAM)**.
5. Select **+ Add** and then select **Role = 'Log Analytics Reader'**. Enter *MALogAnalyticsReader* in the **Select** box
6. When this user is found, select it, and then select **Save** near the bottom of the panel.

[![create new workspace](UDRimages/IAM_Workspace.png)](UDRimages/IAM_Workspace.png)

[![create new workspace](UDRimages/IAM_Workspace_Role.png)](UDRimages/IAM_Workspace_Role.png)

[![create new workspace](UDRimages/IAM_Workspace_MALogAnalyticsReader.png)](UDRimages/IAM_Workspace_MALogAnalyticsReader.png)


### Complete setup

At this point, you have the option to proceed to [enrolling your devices](update-readiness-enroll-devices.md), or you can go directly to the dashboard and enroll devices later. If you go to the dashboard at this point, you will see something like this:

[![dashboard before enrollment](UDRimages/UDR-dash-not-enrolled.png)](UDRimages/UDR-dash-not-enrolled.png)

If you've come to the dashboard prior to enrolling devices, select **Connected Services** {or is it Connect devices?} to proceed with [enrolling devices](update-readiness-enroll-devices.md).

If your devices are already enrolled, you can start getting familiar with the dashboard:

## Review assets

Once device enrollment is complete, you should review carefully the inventory of reported devices and other assets to determine if any are missing or are reporting unexpected data. Your devices, drivers, apps, Office apps, Office add-ins, and Office macros are visible as items under **Assets**:

[![assets view](UDRimages/UDR-main-assets.png)](UDRimages/UDR-main-assets.png)

### Devices

Key information about all devices in your organization that are enrolled. You can sort on any column or filter for particular values.


### Apps

Similarly, the Apps tab shows all installed apps detected on your Windows devices.

[![assets apps view](UDRimages/UDR-assets-apps2.png)](UDRimages/UDR-assets-apps2.png)

"Noteworthy" apps are those that are installed on more than 2% of enrolled devices. You can change the threshold of "noteworthy" by {doing something}. You can also set the *Importance* of apps by categorizing them into these categories:

- Critical
- Important
- Ignore
- Not reviewed

To set the importance of an app, click it to get its detailed view, and then use the **Importance** pull-down menu to choose a value. You can also assign an owner, as in this example from Office add-ins:

[![assets add-ins detail](UDRimages/UDR-app-detail2.png)](UDRimages/UDR-app-detail2.png)

### Office apps

Office apps (such as Microsoft Word or Excel) are displayed similarly, though there is no categorization or "noteworthy" count. You set the importance and owner for the Office app the same way as with other apps or add-ins.

### Office add-ins

Office add-ins (for example, an e-mail scanner or iCloud add-in) are displayed similarly, including the "noteworthy" count and the means to categorize importance as with apps. You can view details of any add-in by clicking it.

### Office macros

This section shows whether reporting devices have accessed any files recently that are capable of including macros. (For a detailed list of these file types, see [File formats supported in the 2007 Office system (corrected)](https://blogs.technet.microsoft.com/office_resource_kit/2009/04/04/file-formats-supported-in-the-2007-office-system-corrected/) at the Office IT Pro blog.)

[![assets macros detail](UDRimages/UDR-assets-macros.png)](UDRimages/UDR-assets-macros.png)

>[!NOTE]
>If you have run the Readiness Toolkit [LINK](https://aka.ms/readinesstoolkit) on any devices in your environment, additional data from those devices will be displayed here as well. However, there is no need to obtain or run the Readiness Toolkit to use any aspect of Desktop Analytics.

## View the current state of your environment

{SUPERCEDED by "global-monitoring" topic--should we link to that here or just delete this section in this topic?}

{not sure if this is really part of the flow prior to setting the deployment plan or if it's better in "ongoing monitoring"--or both?}

Knowing the current status of updates in your environment will be helpful as you formulate a deployment plan once devices are enrolled.

### Security updates

To review the current status of security updates, select **Security updates** in the **Monitor** section of Desktop Analytics:

[![security update status view](UDRimages/UDR-security-status.png)](UDRimages/UDR-security-status.png)

This view summarizes security updates for devices that are running Windows or Office (scoped to devices with Click-To-Run installation of Office) {what does this mean?}. The total number of devices considered for both Windows and Office is shown to the left of the bar chart. Devices in the bar chart are categorized as follows:

| **Label**  | **Definition**  |
|---------------------------------------------------------|-----------|
| Latest | Devices are running the latest security update per release version and release channel.|
| Latest-1 | Devices are running a security update one release older than the latest available update on that channel and a build that is not the most current. |
| Older | Devices are running a security update older than Latest -1. |
| Not measured | Devices which Desktop Analytics has not assessed. For Windows, this includes devices running Windows 7 or Windows 8.1. For Office, this includes devices with Office 365 ProPlus that are in Insider channels {what is the minimum version?}, perpetual versions of Office that use a Windows installer (for example, Office 2016, Office 2013, and Office 2010), and Office 365 ProPlus devices that have not returned sufficient data to assess the security status. | 

Select **Windows 10** or **Office 365 ProPlus** to see more details for each of those entities. You can also select **Security updates** in the **Monitor** section of Desktop Analytics. For more details about monitoring, see [Monitor the health and update status of devices](update-readiness-monitoring.md).

### Feature updates

To review the current status of feature updates, select **Feature updates** in the **Monitor** section of Desktop Analytics:

[![feature update status view](UDRimages/UDR-feature-update.png)](UDRimages/UDR-feature-update.png)

This view summarizes feature updates for devices that are running Windows or Office (scoped to devices with Click-To-Run installation of Office) {what does this mean?}. The total number of devices considered for both Windows and Office is shown to the left of the bar chart. Devices in the bar chart are categorized as follows:

| **Label**  | **Definition**  |
|---------------------------------------------------------|-----------|
| In service | Devices are running the latest feature update per release version and release channel.|
| Near end of service | Devices are running a feature update that is within 90 days of reaching end of service. |
| End of service | Devices are running a feature update which is past the end of service date. For details about end of service dates, see {xlink into relevant section of UDR_monitoring}|
| Not measured | Devices which Desktop Analytics has not assessed. For Windows, this includes devices running Windows 7 or Windows 8.1. For Office, this includes devices with Office 365 ProPlus that are in Insider channels {what is the minimum version?}, perpetual versions of Office that use a Windows installer (for example, Office 2016, Office 2013, and Office 2010), and Office 365 ProPlus devices that have not returned sufficient data to assess the security status. | 

Select **Windows 10** or **Office 365 ProPlus** to see more details for each of those entities. You can also select **Security updates** in the **Monitor** section of Desktop Analytics. For more details about monitoring, see [Monitor the health and update status of devices](update-readiness-monitoring.md).



| | |
| --- | --- |
| ![done](UDRimages/checklistdone.png) | Learn about Update Readiness |
| ![done](UDRimages/checklistdone.png) | Get started with accounts, subscriptions, user access, workspaces: [Get started with Update Readiness](update-readiness-get-started.md) |
| ![to do](UDRimages/checklistbox.gif) | Enroll devices in Desktop Analytics to start the flow of diagnostic data: [Enroll devices in Update Readiness](update-readiness-enroll-devices.md)|
| ![to do](UDRimages/checklistbox.gif)| Set up deployment plans -- define global rules and detailed deployment plans for pilot and production: [Define deployment plans with Update Readiness](update-readiness-deployment-plans.md) |
| ![to do](UDRimages/checklistbox.gif) | [Deploy pilot with Update Readiness](update-readiness-deploy-pilot.md) (this topic) |
| ![to do](UDRimages/checklistbox.gif) | Deploy to production: [Deploy to production with Update Readiness](update-readiness-deploy-production.md) |
| ![to do](UDRimages/checklistbox.gif) | Monitor status and health of the deployment: [Monitor the health and update status of devices](update-readiness-monitoring.md) |




## Related topics
