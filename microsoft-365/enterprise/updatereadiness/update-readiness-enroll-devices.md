---
title: Enroll devices in Update Readiness
description: 
ms.prod: w10
ms.mktglfcycl: manage
ms.sitesec: library
author: Jaimeo
ms.localizationpriority: high
ms.author: jaimeo
ms.date: 06/15/2018
---

# Enroll devices in Updated Readiness

The simplest way to enroll devices is to obtain the Upgrade Readiness [deployment script](https://aka.ms/urscript) and run it. This script is also used to enroll devices in Windows Analytics, but has been extended to also set things appropriately for **Update** Readiness. For details, see the [Upgrade Readiness deployment script](../upgrade/upgrade-readiness-deployment-script.md) topic, which includes a description of the error codes that can be displayed.

>[!NOTE]
>If you are already using Windows Analytics, you can just select the workspace you're using for that from this list and all data and configuration will transfer to Update Readiness.

## Copy your Commercial ID key

Microsoft uses a unique commercial ID to map information from user computers to your Update Readiness workspace. This should be generated for you automatically. Copy your commercial ID key from the Update Readiness dashboard and then deploy it to user computers.


1.  On the dashboard, navigate to the **Your workspace** panel.

    ![Update Readiness Your Workspace section showing Commercial ID as the fourth item](UDRimages/UDR-workspace-commID.png)](UDRimages/UDR-workspace-commID.png)

2. Copy your Commercial ID. Save this Commercial ID because you will need it later for use in the deployment scripts and policies.

    >**Important**<br> Regenerate a Commercial ID key only if your original ID key can no longer be used. Regenerating a commercial ID key resets the data in your workspace for all solutions that use the ID. Additionally, you’ll need to deploy the new commercial ID key to user computers again.

## Enable data sharing

To enable data sharing, configure your proxy sever to whitelist the following endpoints. You might need to get approval from your security group to do this.

| **Endpoint**  | **Function**  |
|---------------------------------------------------------|-----------|
| `https://v10.events.data.microsoft.com` | Connected User Experience and Diagnostic component endpoint for use with Windows 10, version 1803|
| `https://v10.vortex-win.data.microsoft.com` | Connected User Experience and Diagnostic component endpoint for Windows 10, version 1709 or earlier |
| `https://vortex-win.data.microsoft.com` | Connected User Experience and Diagnostic component endpoint for operating systems older than Windows 10 |
| `https://settings-win.data.microsoft.com` | Enables the compatibility update to send data to Microsoft. 
| `http://adl.windows.com` | Allows the compatibility update to receive the latest cofdsmpatibility data from Microsoft. |
| `https://watson.telemetry.microsoft.com` | Windows Error Reporting (WER); required for Device Health and Update Compliance AV reports. Not used by Upgrade Readiness. |
| `https://oca.telemetry.microsoft.com`  | Online Crash Analysis; required for Device Health and Update Compliance AV reports. Not used by Upgrade Readiness. |
| `https://nexusrules.officeapps.live.com` | Used to request dynamic diagnostic data events from Office clients. This is useful for drill-down and diagnostics purposes in the Update Readiness portal |
| `https://nexus.officeapps.live.com` | Used by Office clients to send diagnostic data events from Office 14, and Office 15, and versions of Office 16 prior to 16.0.8702.*. Used to collect usage and reliability signals events for Update Readiness. |
| `https://mobile.pipe.aria.microsoft.com/Collector/3.0/` | Used by Office clients to send diagnostic data events from Universal/Modern Office apps and Win32 Office 16 versions later than 16.0.8702.*. Used to collect usage and reliability signals events for Update Readiness. |
| `https://browser.pipe.aria.microsoft.com/Collector/3.0` | Used by Office web clients to send diagnostic data events. This is also used by Office add-ins and other extensions within Office clients. |


>[!NOTE]
>Proxy authentation and SSL inspections are frequent challenges for enterprises. See the following sections for configuration options.

### Configuring endpoint access with SSL inspection
To ensure privacy and data integrity Windows checks for a Microsoft SSL certificate when communicating with the diagnostic data endpoints. Accordingly SSL interception and inspection is not possible. To use Windows Analytics services you should exclude the above endpoints from SSL inspection.

### Configuring endpoint access with proxy server authentication
If your organization uses proxy server authentication for outbound traffic, use one or more of the following approaches to ensure that the diagnostic data is not blocked by proxy authentication:

- **Best option: Bypass** Configure your proxy servers to **not** require proxy authentication for traffic to the diagnostic data endpoints. This is the most comprehensive solution and it works for all versions of Windows 10.
- **User proxy authentication:** Alternatively, you can configure devices to use the logged on user's context for proxy authentication. First, update the devices to Windows 10, version 1703 or later. Then, ensure that users of the devices have proxy permission to reach the diagnostic data endpoints. This requires that the devices have console users with proxy permissions, so you couldn't use this method with headless devices.
- **Device proxy authentication:** Another option--the most complex--is as follows: First, configure a system-level proxy server on the devices. Then, configure these devices to use machine-account-based outbound proxy authentication. Finally, configure proxy servers to allow the machine accounts access to the diagnostic data endpoints. 

## Deploy the compatibility update and related updates

The compatibility update scans your devices and enables application usage tracking. If you don’t already have these updates installed, you can download the applicable version from the Microsoft Update Catalog or deploy it using Windows Server Update Services (WSUS) or your software distribution solution, such as System Center Configuration Manager.

| **Operating System** | **Updates** |
|----------------------|-----------------------------------------------------------------------------|
| Windows 10        | Windows 10 includes the compatibility update, so you will automatically have the latest compatibility update so long as you continue to keep your Windows 10 devices up-to-date with cummulative updates.  |
| Windows 8.1          | [KB 2976978](http://catalog.update.microsoft.com/v7/site/Search.aspx?q=KB2976978)<br>Performs diagnostics on the Windows 8.1 systems that participate in the Windows Customer Experience Improvement Program. These diagnostics help determine whether compatibility issues might be encountered when the latest Windows operating system is installed. <br>For more information about this update, see <https://support.microsoft.com/kb/2976978>|
| Windows 7 SP1        | [KB2952664](http://catalog.update.microsoft.com/v7/site/Search.aspx?q=KB2952664) <br>Performs diagnostics on the Windows 7 SP1 systems that participate in the Windows Customer Experience Improvement Program. These diagnostics help determine whether compatibility issues might be encountered when the latest Windows operating system is installed. <br>For more information about this update, see <https://support.microsoft.com/kb/2952664>|

>[!NOTE] 
>These updates are incremented regularly, though the associated KB number will not change. So you should confirm that you always have the latest version of the update.

>[!IMPORTANT] 
>Restart devices after you install the compatibility updates for the first time.

>[!NOTE] 
>We recommend you configure your update management tool to automatically install the latest version of these updates. There is a related optional update, [KB 3150513](https://catalog.update.microsoft.com/v7/site/Search.aspx?q=3150513), which can provide updated configuration and definitions for older compatibiltiy updates. For more information about this optional update, see <https://support.microsoft.com/kb/3150513>.

## Set diagnostic data levels

You can set the diagnostic data level used by monitored devices either with the Update Readiness deployment script or by policy (by using Group Policy or Mobile Device Management).

The basic functionality of Update Readiness will work at the Basic diagnostic data level, however you won't get usage or health data for your updated devices without enabling the Enhanced level. This means you won't get information about health regressions on updated devices. So it is best to enable the Enhanced diagnostic data level, at least on devices running Windows 10, version 1709 (or later) where the Enhanced diagnostic data setting can be paired with "limited enhanced" data level (see [Windows 10 enhanced diagnostic data events and fields used by Windows Analytics](https://docs.microsoft.com/windows/privacy/enhanced-diagnostic-data-windows-analytics-events-and-fields). For more information, see [Windows Analytics and privacy](https://docs.microsoft.com/windows/deployment/update/windows-analytics-privacy).

## Enroll a few pilot devices

If you have never used Windows Analytics before and are completely new to this technology, we recommend manually running this script on a few representative devices initially to verify things are properly configured and the device can connect to the diagnostic data endpoints. Make sure to run the pilot version of the script, which will provide extra diagnostics.

See the [Upgrade Readiness deployment script](../upgrade/upgrade-readiness-deployment-script.md) topic for information about obtaining and running the script, and for a description of the error codes that can be displayed. See ["Understanding connectivity scenarios and the deployment script"](https://blogs.technet.microsoft.com/upgradeanalytics/2017/03/10/understanding-connectivity-scenarios-and-the-deployment-script/) on the Windows Analytics blog for a summary of setting the ClientProxy for the script, which will enable the script properly check for diagnostic data endpoint connectivity.

After data is sent from devices to Microsoft, it generally takes 48-56 hours for the data to populate in Update Readiness. The compatibility update takes several minutes to run. If the update does not get a chance to finish running or if the computers are inaccessible (turned off or sleeping for example), data will take longer to populate in Update Readiness. For this reason, you can expect most of your devices to be populated in Update Readiness in about 1-2 weeks after deploying the update and configuration to user computers. As described in the Windows Analytics blog post ["You can now check on the status of your computers within hours of running the deployment script"](https://blogs.technet.microsoft.com/upgradeanalytics/2017/05/12/wheres-my-data/), you can verify that devices have successfully connected to the service within a few hours. Most of those devices should start to show up in the Update Readiness console within a few days.

### Distribute the deployment script at scale

Use a software distribution system such as System Center Configuration Manager to distribute the Upgrade Readiness deployment script at scale. For more information, see [New version of the Upgrade Analytics Deployment Script available](https://blogs.technet.microsoft.com/upgradeanalytics/2016/09/20/new-version-of-the-upgrade-analytics-deployment-script-available/) on the Upgrade Readiness blog. For information on how to deploy PowerShell scripts by using Windows Intune, see [Manage PowerShell scripts in Intune for Windows 10 devices](https://docs.microsoft.com/intune/intune-management-extension).

### Distributing policies at scale
There are a number of policies that can be centrally managed to control Update Readiness device configuration. All of these policies have *preference* registry key equivalents that can be set by using the deployment script. Policy settings override preference settings if both are set.
>[!NOTE]
>You can only set the diagnostic data level to Enhanced by using policy. For example, this is necessary for device health data to work.

These policies are under Microsoft\Windows\DataCollection:

| Policy   | Value  |
|-----------------------|------------------|
| CommercialId | In order for your devices to show up in Update Readiness, they must be configured with your organization’s Commercial ID. |
| AllowTelemetry (in Windows 10) |	1 (Basic), 2 (Enhanced) or 3 (Full) diagnostic data. Update Readiness will work with basic diagnostic data, but more features are available when you use the Enhanced level (for example, Device Health requires Enhanced diagnostic data and Upgrade Readiness only collects app usage and site discovery data on Windows 10 devices with Enhanced diagnostic data). For more information, see [Configure Windows diagnostic data in your organization](https://docs.microsoft.com/windows/configuration/configure-windows-diagnostic-data-in-your-organization). |
| LimitEnhancedDiagnosticDataWindowsAnalytics (in Windows 10) |	Only applies when AllowTelemetry=2. Limits the Enhanced diagnostic data events sent to Microsoft to just those needed by Update Readiness. For more information, see [Windows 10, version 1709 enhanced diagnostic data events and fields used by Windows Analytics](https://docs.microsoft.com/windows/configuration/enhanced-diagnostic-data-windows-analytics-events-and-fields).|
| AllowDeviceNameInTelemetry (in Windows 10) |	In Windows 10, version 1803, a separate opt-in is required to enable devices to continue to send the device name. |
| CommercialDataOptIn (in Windows 7 and Windows 8) |	1 is required for Upgrade Readiness, which is the only solution that runs on Windows 7 or Windows 8. |

You can set these values by using Group Policy (in Computer Configuration > Administrative Templates > Windows Components > Data Collection and Preview Builds) or by using Mobile Device Management (in Provider/ProviderID/CommercialID). For more information about deployment using MDM, see the [DMClient CSP](https://docs.microsoft.com/windows/client-management/mdm/dmclient-csp) topic in MDM documentation.

The corresponding preference registry values are available in **HKLM\Software\Microsoft\Windows\CurrentVersion\Policies\DataCollection** and can be configured by the deployment script. If a given setting is configured by both preference registry settings and policy, the policy values will override.

### Distribution at scale without using the deployment script

We recommend using the deployment script to configure devices. However if this is not an option, you can still manage settings by policy as described in the previous section. However, if you don't run the deployment script, you won't benefit from its error checking, and you might have to wait a long time (possibly weeks) before devices send the initial full inventory scan.

Note that it is possible to intiate a full inventory scan on a device by calling these commands:
- CompatTelRunner.exe -m:generaltel.dll -f:DoCensusRun
- CompatTelRunner.exe -m:appraiser.dll -f:DoScheduledTelemetryRun ent

For details on how to run these and how to check results, see the deployment script.