---
title: Get started with Update Readiness
description: How to set up accounts, permissions, and diagnostic data, enroll devices, and other steps to get Update Readiness started in your organization
ms.prod: w10
ms.mktglfcycl: manage
ms.sitesec: library
author: Jaimeo
ms.localizationpriority: high
ms.author: jaimeo
ms.date: 06/04/2018
---

# Get started with Updated Readiness

This topic explains the steps necessary to configure your environment for Update Readiness. 

Steps are provided in sections that follow the recommended setup process:

1. [Add Update Readiness](#add-update-readiness) to Microsoft Operations Management Suite.
2. [Enroll devices](#enroll-devices-in-update-readiness) so that Update Readiness can monitor them.
3. [Use Update Readiness to discover the current state of devices in your environment](#use-update-readiness-to-monitor-the-current-state) once your devices are enrolled.



## Add Update Readiness

Update Readiness is offered as a solution in the Microsoft Operations Management Suite (OMS), a collection of cloud-based servicing for monitoring and automating your on-premise and cloud environments. For more information about OMS, see [Operations Management Suite overview](https://azure.microsoft.com/en-us/documentation/articles/operations-management-suite-overview/). 

**If you are already using OMS**, you’ll find Update Readiness in the Solutions Gallery. Select the **Update Readiness** tile in the gallery and then click **Add** on the solution's details page. Update Readiness is now visible in your workspace.

**If you are not yet using OMS**, use the following steps to subscribe to Update Readiness:

1.	Go to [Operations Management Suite](https://www.microsoft.com/en-us/cloud-platform/operations-management-suite) on Microsoft.com and click **Sign in**.
   [![Operations Management Suite bar with sign-in button](images/uc-02a.png)](images/uc-02.png)


2.	Sign in to Operations Management Suite (OMS). You can use either a Microsoft Account or a Work or School account to create a workspace. If your company is already using Azure Active Directory (Azure AD), use a Work or School account when you sign in to OMS. Using a Work or School account allows you to use identities from your Azure AD to manage permissions in OMS.
   [![OMS Sign-in dialog box for account name and password](images/uc-03a.png)](images/uc-03.png)


3.	Create a new OMS workspace.

     [![OMS dialog with buttons to create a new OMS workspace or cancel](images/uc-04a.png)](images/uc-04.png)

4.	Enter a name for the workspace, select the workspace region, and provide the email address that you want associated with this workspace. Click **Create**.

    [![OMS Create New Workspace dialog](images/uc-05a.png)](images/uc-05.png)

5.	If your organization already has an Azure subscription, you can link it to your workspace. Note that you may need to request access from your organization’s Azure administrator. If your organization does not have an Azure subscription, create a new one or select the default OMS Azure subscription from the list. If you do not yet have an Azure subscription, follow [this guide](https://blogs.technet.microsoft.com/upgradeanalytics/2016/11/08/linking-operations-management-suite-workspaces-to-microsoft-azure/) to create and link an Azure subscription to an OMS workspace.

    [![OMS dialog to link existing Azure subscription or create a new one](images/uc-06a.png)](images/uc-06.png)

6.	To add Update Readiness to your workspace, go to the Solution Gallery, Select the **Update Readiness** tile and then select **Add** on the solution's detail page.

    [![Windows Analytics details page in Solutions Gallery](images/solution-bundle.png)](images/solution-bundle.png)

7.	Click the **Update Readiness** tile to configure the solution. The **Settings Dashboard** opens. In this example, both Upgrade Readiness and Device Health solutions have been added.

    [![OMS Settings Dashboard showing Device Health and Upgrade Readiness tiles](images/OMS-after-adding-solution.jpg)](images/OMS-after-adding-solution.jpg)



After you have added Update Readiness and devices have a Commercial ID, you will begin receiving data. It will typically take 24-48 hours for the first data to begin appearing. The following section explains how to deploy your Commercial ID to your Windows 10 devices.

>[!NOTE]
>You can unsubscribe from the Update Readiness solution if you no longer want to monitor your organization’s devices. User device data will continue to be shared with Microsoft while the opt-in keys are set on user devices and the proxy allows traffic.

## Enroll devices in Update Readiness

Once you've added Update Readiness to Microsoft Operations Management Suite, you can now start enrolling the devices in your organization.

### Copy your Commercial ID key

Microsoft uses a unique commercial ID to map information from user computers to your OMS workspace. This should be generated for you automatically. Copy your commercial ID key in OMS and then deploy it to user computers. 



1.  On the **Settings** dashboard, navigate to the **Windows Telemetry** panel under **Connected Sources** .

    ![Operations Management Suite Settings dialog showing Connected sources and Windows telemetry selected and the commercial ID location marked by a black box in the lower right.](images/WA-device-enrollment.png)

2. Copy your Commercial ID (which should already be populated). Save this Commercial ID because you will need it later for use in the deployment scripts and policies.

    >**Important**<br> Regenerate a Commercial ID key only if your original ID key can no longer be used. Regenerating a commercial ID key resets the data in your workspace for all solutions that use the ID. Additionally, you’ll need to deploy the new commercial ID key to user computers again.

### Enable data sharing

To enable data sharing, configure your proxy sever to whitelist the following endpoints. You might need to get approval from your security group to do this.

| **Endpoint**  | **Function**  |
|---------------------------------------------------------|-----------|
| `https://v10.events.data.microsoft.com` | Connected User Experience and Diagnostic component endpoint for use with Windows 10, version 1803|
| `https://v10.vortex-win.data.microsoft.com` | Connected User Experience and Diagnostic component endpoint for Windows 10, version 1709 or earlier |
| `https://vortex-win.data.microsoft.com` | Connected User Experience and Diagnostic component endpoint for operating systems older than Windows 10 |
| `https://settings-win.data.microsoft.com` | Enables the compatibility update to send data to Microsoft. 
| `http://adl.windows.com` | Allows the compatibility update to receive the latest compatibility data from Microsoft. |
| `https://watson.telemetry.microsoft.com` | Windows Error Reporting (WER); required for Device Health and Update Compliance AV reports. Not used by Upgrade Readiness. |
| `https://oca.telemetry.microsoft.com`  | Online Crash Analysis; required for Device Health and Update Compliance AV reports. Not used by Upgrade Readiness. |
| `https://nexusrules.officeapps.live.com` | Used to request dynamic diagnostic data events from Office clients. This is useful for drill-down and diagnostics purposes in the Update Readiness portal |
| `https://nexus.officeapps.live.com` | Used by Office clients to send diagnostic data events from Office 14, and Office 15, and versions of Office 16 prior to 16.0.8702.*. Used to collect usage and reliability signals events for Update Readiness. |
| `https://mobile.pipe.aria.microsoft.com/Collector/3.0/` | Used by Office clients to send diagnostic data events from Universal/Modern Office apps and Win32 Office 16 versions later than 16.0.8702.*. Used to collect usage and reliability signals events for Update Readiness. |
| `https://browser.pipe.aria.microsoft.com/Collector/3.0` | Used by Office web clients to send diagnostic data events. This is also used by Office add-ins and other extensions within Office clients. |


>[!NOTE]
>Proxy authentation and SSL inspections are frequent challenges for enterprises. See the following sections for configuration options.

#### Configuring endpoint access with SSL inspection
To ensure privacy and data integrity Windows checks for a Microsoft SSL certificate when communicating with the diagnostic data endpoints. Accordingly SSL interception and inspection is not possible. To use Windows Analytics services you should exclude the above endpoints from SSL inspection.

#### Configuring endpoint access with proxy server authentication
If your organization uses proxy server authentication for outbound traffic, use one or more of the following approaches to ensure that the diagnostic data is not blocked by proxy authentication:

- **Best option: Bypass** Configure your proxy servers to **not** require proxy authentication for  traffic to the diagnostic data endpoints. This is the most comprehensive solution and it works for all versions of Windows 10.
- **User proxy authentication:** Alternatively, you can configure devices to use the logged on user's context for proxy authentication. First, update the devices to Windows 10, version 1703 or later. Then, ensure that users of the devices have proxy permission to reach the diagnostic data endpoints. This requires that the devices have console users with proxy permissions, so you couldn't use this method with headless devices.
- **Device proxy authentication:** Another option--the most complex--is as follows: First, configure a system-level proxy server on the devices. Then, configure these devices to use machine-account-based outbound proxy authentication. Finally, configure proxy servers to allow the machine accounts access to the diagnostic data endpoints. 

### Deploy the compatibility update and related updates

The compatibility update scans your devices and enables application usage tracking. If you don’t already have these updates installed, you can download the applicable version from the Microsoft Update Catalog or deploy it using Windows Server Update Services (WSUS) or your software distribution solution, such as System Center Configuration Manager.

| **Operating System** | **Updates** |
|----------------------|-----------------------------------------------------------------------------|
| Windows 10        | Windows 10 includes the compatibility update, so you will automatically have the latest compatibility update so long as you continue to keep your Windows 10 devices up-to-date with cummulative updates.  |
| Windows 8.1          | [KB 2976978](http://catalog.update.microsoft.com/v7/site/Search.aspx?q=KB2976978)<br>Performs diagnostics on the Windows 8.1 systems that participate in the Windows Customer Experience Improvement Program. These diagnostics help determine whether compatibility issues might be encountered when the latest Windows operating system is installed. <br>For more information about this update, see <https://support.microsoft.com/kb/2976978>|
| Windows 7 SP1        | [KB2952664](http://catalog.update.microsoft.com/v7/site/Search.aspx?q=KB2952664) <br>Performs diagnostics on the Windows 7 SP1 systems that participate in the Windows Customer Experience Improvement Program. These diagnostics help determine whether compatibility issues might be encountered when the latest Windows operating system is installed. <br>For more information about this update, see <https://support.microsoft.com/kb/2952664>|

>[!IMPORTANT] 
>Restart devices after you install the compatibility updates for the first time.

>[!NOTE] 
>We recommend you configure your update management tool to automatically install the latest version of these updates. There is a related optional update, [KB 3150513](https://catalog.update.microsoft.com/v7/site/Search.aspx?q=3150513), which can provide updated configuration and definitions for older compatibiltiy updates. For more information about this optional update, see <https://support.microsoft.com/kb/3150513>.


## Use Update Readiness to monitor the current state

Once your devices are enrolled, you can move on to [START UDR TO SEE WHAT'S WHAT]


## Related topics
