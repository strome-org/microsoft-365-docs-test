---
title: Enroll devices in Desktop Analytics
description: 
ms.prod: w10
ms.mktglfcycl: manage
ms.sitesec: library
author: Jaimeo
ms.localizationpriority: medium
ms.author: jaimeo
ms.date: 09/14/2018
---

# Enroll devices in Desktop Analytics

Desktop Analytics has no agents that require installation, so device enrollment is simply a matter of configuring settings on the devices you want Desktop Analytics to monitor. You can do this by using a deployment script, Group Policy, or Mobile Device Management (MDM) policy. These settings control which Desktop Analytics instance the device should send its data to as well as a number of other configuration options.


>[!NOTE]
>If you are already using Windows Analytics, you can just select the workspace you're using for that from the displayed list and all of those devices will show up in your Desktop Analytics workspace automatically (without the need to enroll them). However, if you chose to configure a different workspace, you will have to first split your entries into devices that are monitored by Windows Analytics and devices that are monitored by Desktop Analytics; then you must follow the enrollment steps for those devices you want Desktop Analytics to monitor.

## Copy your Commercial ID key

Microsoft uses a unique commercial ID to map information from user computers to your Desktop Analytics workspace. This should be generated for you automatically. Copy your commercial ID key from the Desktop Analytics dashboard and then deploy it to user computers.


1.  On the dashboard, navigate to the **Your workspace** panel.

{NEED REAL SCREENSHOT W/O HAND}
    ![Desktop Analytics Your Workspace section showing Commercial ID as the fourth item](UDRimages/UDR-workspace-commID.png)](UDRimages/UDR-workspace-commID.png)

2. Copy your Commercial ID. Save this Commercial ID because you will need it later for use in the deployment scripts and policies.

    >**Important**<br> Regenerate the Commercial ID only if you can no longer use the current one. If you regenerate the commercial ID, you must deploy the new ID to your devices in order to continue to monitor them, which might result in data loss during the transition.

## Enable data sharing

To enable data sharing, configure your proxy sever to whitelist the following endpoints. You might need to get approval from your security group to do this.

| **Endpoint**  | **Function**  |
|---------------------------------------------------------|-----------|
| `https://v10.events.data.microsoft.com` | Connected User Experience and Diagnostic component endpoint for use with Windows 10, version 1803|
| `https://v10.vortex-win.data.microsoft.com` | Connected User Experience and Diagnostic component endpoint for Windows 10, version 1709 or earlier |
| `https://vortex-win.data.microsoft.com` | Connected User Experience and Diagnostic component endpoint for operating systems older than Windows 10 |
| `https://settings-win.data.microsoft.com` | Enables the compatibility update to send data to Microsoft. 
| `http://adl.windows.com` | Allows the compatibility update to receive the latest compatibility data from Microsoft. |
| `https://watson.telemetry.microsoft.com` | Windows Error Reporting (WER); required for Device Health and Update Compliance AV reports. Not used by Desktop Analytics. |
| `https://oca.telemetry.microsoft.com`  | Online Crash Analysis; required for Device Health and Update Compliance AV reports. Not used by Desktop Analytics. |
| `https://login.live.com` | Windows Error Reporting (WER); required in order to obtain a unique device ID. **Note:** WER does *not* use login.live.com to access Microsoft Account consumer services such as Xbox Live. WER uses an anti-spoofing API at that address to enhance the integrity of error reports. |
| `https://nexusrules.officeapps.live.com` | Used to request dynamic diagnostic data events from Office clients. This is useful for drill-down and diagnostics purposes in the Desktop Analytics portal |
| `https://nexus.officeapps.live.com` | Used by Office clients to send diagnostic data events from Office 14, and Office 15, and versions of Office 16 prior to 16.0.8702.*. Used to collect usage and reliability signals events for Desktop Analytics. |
| `https://mobile.pipe.aria.microsoft.com/Collector/3.0/` | Used by Office clients to send diagnostic data events from Universal/Modern Office apps and Win32 Office 16 versions later than 16.0.8702.*. Used to collect usage and reliability signals events for Desktop Analytics. |
| `https://browser.pipe.aria.microsoft.com/Collector/3.0` | Used by Office web clients to send diagnostic data events. This is also used by Office add-ins and other extensions within Office clients. |


>[!NOTE]
>Proxy authentication and SSL inspections are frequent challenges for enterprises. See the following sections for configuration options.

### Configuring endpoint access with SSL inspection
To ensure privacy and data integrity Windows checks for a Microsoft SSL certificate when communicating with the diagnostic data endpoints. Accordingly, SSL interception and inspection is not possible. To use Desktop Analytics you should exclude the above endpoints from SSL inspection.

### Configuring endpoint access with proxy server authentication
If your organization uses proxy server authentication for outbound traffic, use one or more of the following approaches to ensure that the diagnostic data is not blocked by proxy authentication:

- **Best option: Bypass** Configure your proxy servers to **not** require proxy authentication for traffic to the diagnostic data endpoints. This is the most comprehensive solution and it works for all versions of Windows 10.
- **User proxy authentication:** Alternatively, you can configure devices to use the logged-on user's context for proxy authentication. First, update the devices to Windows 10, version 1703 or later. Then, ensure that users of the devices have proxy permission to reach the diagnostic data endpoints. This requires that the devices have console users with proxy permissions, so you couldn't use this method with headless devices.
- **Device proxy authentication:** Another option--the most complex--is as follows: First, configure a system-level proxy server on the devices. Then, configure these devices to use machine-account-based outbound proxy authentication. Finally, configure proxy servers to allow the machine accounts access to the diagnostic data endpoints. 

## Deploy the compatibility update and related updates

The compatibility update scans your devices and enables application usage tracking. If you don’t already have these updates installed, you can download the applicable version from the Microsoft Update Catalog or deploy it using Windows Server Update Services (WSUS) or your software distribution solution, such as System Center Configuration Manager.

{NEED LINK TO OPTIONAL UPDATE THAT LOWERS LATENCY (AND DESCRIPTION) FROM ZANE SZAFRANIEC, PRABHU PADHI, OR DAVID MEBANE}

| **Operating System** | **Updates** |
|----------------------|-----------------------------------------------------------------------------|
| Windows 10        | Windows 10 includes the compatibility update, so you will automatically have the latest compatibility update so long as you continue to keep your Windows 10 devices up-to-date with cumulative updates.  |
| Windows 8.1          | [KB 2976978](http://catalog.update.microsoft.com/v7/site/Search.aspx?q=KB2976978)<br>Performs diagnostics on the Windows 8.1 systems that participate in the Windows Customer Experience Improvement Program. These diagnostics help determine whether compatibility issues might be encountered when the latest Windows operating system is installed. <br>For more information about this update, see <https://support.microsoft.com/kb/2976978>|
| Windows 7 SP1        | [KB2952664](http://catalog.update.microsoft.com/v7/site/Search.aspx?q=KB2952664) <br>Performs diagnostics on the Windows 7 SP1 systems that participate in the Windows Customer Experience Improvement Program. These diagnostics help determine whether compatibility issues might be encountered when the latest Windows operating system is installed. <br>For more information about this update, see <https://support.microsoft.com/kb/2952664>|

>[!NOTE] 
>These updates are incremented regularly, though the associated KB number will not change. So you should confirm that you always have the latest version of the update.

>[!IMPORTANT] 
>Restart devices after you install the compatibility updates for the first time.

>[!NOTE] 
>We recommend you configure your update management tool to automatically install the latest version of these updates. There is a related optional update, [KB 3150513](https://catalog.update.microsoft.com/v7/site/Search.aspx?q=3150513), which can provide updated configuration and definitions for older compatibility updates. For more information about this optional update, see <https://support.microsoft.com/kb/3150513>.

## Set diagnostic data levels

You can set the diagnostic data level used by monitored devices either with the Desktop Analytics deployment script or by policy (by using Group Policy or Mobile Device Management).

The basic functionality of Desktop Analytics will work at the Basic diagnostic data level, however you won't get usage or health data for your updated devices without enabling the Enhanced level. This means you won't get information about health regressions on updated devices. So it is best to enable the Enhanced diagnostic data level, at least on devices running Windows 10, version 1709 (or later) where the Enhanced diagnostic data setting can be paired with "limited enhanced" data level (see [Windows 10 enhanced diagnostic data events and fields used by Windows Analytics](https://docs.microsoft.com/windows/privacy/enhanced-diagnostic-data-windows-analytics-events-and-fields)). For more information, see [Windows Analytics and privacy](https://docs.microsoft.com/windows/deployment/update/windows-analytics-privacy).
{DO WE NEED TO ADDRESS PRIVACY ISSUES IN SOME WAY ANALOGOUS TO THE WA PRIVACY TOPIC?}

## Enroll a few pilot devices

If you have never used Windows Analytics before and are completely new to this technology, we recommend manually running this script on a few representative devices initially to verify things are properly configured and that the device can connect to the diagnostic data endpoints. Make sure to run the pilot version of the script, which will provide extra diagnostics.

See the [Desktop Analytics deployment script NEED LINK](???) topic for information about obtaining and running the script, and for a description of the error codes that can be displayed. See ["Understanding connectivity scenarios and the deployment script"](https://blogs.technet.microsoft.com/upgradeanalytics/2017/03/10/understanding-connectivity-scenarios-and-the-deployment-script/) on the Windows Analytics blog for a summary of setting the ClientProxy for the script, which will enable the script properly check for diagnostic data endpoint connectivity.

After data is sent from devices to Microsoft, it generally takes 48-56 hours for the data to populate in Desktop Analytics. The compatibility update takes several minutes to run. If the update does not get a chance to finish running or if the computers are inaccessible (turned off or sleeping for example), data will take longer to populate in Desktop Analytics. For this reason, you can expect most of your devices to be populated in Desktop Analytics in about 1-2 weeks after deploying the update and configuration to user computers.

## Viewing newly enrolled devices

While it takes some time to gather full data on devices you have enrolled in Desktop Analytics, there is a way to quickly see new devices that have successfully sent partial data to Microsoft less than an hour after running the deployment script. This is particularly useful to verify that endpoints are correctly configured while you wait for the full amount of data to populate.

To see the list of devices that have newly become associated with your organization’s Commercial ID, head to the Connected Services page in Desktop Analytics and navigate to the {SECTION}. This will open a flyout showing new devices seen in the last 24 hours. You can adjust the filter to see new devices as far back as 7 days.

{NEED SCREENSHOT}

### Enrolling devices at scale with the deployment script

The deployment script is the only recommended option for configuring Windows 7 devices because the required settings are not configurable via policy. You can also use the deployment script to configure Windows 10 devices (although many customers choose to use policy instead for reasons described in the next section).

Use a software distribution system such as System Center Configuration Manager to distribute the Desktop Analytics deployment script at scale. For more information, see [NEEDLINK TO NEW Desktop Analytics SCRIPT](https://blogs.technet.microsoft.com/upgradeanalytics/2016/09/20/new-version-of-the-upgrade-analytics-deployment-script-available/) on the Desktop Analytics blog. For information on how to deploy PowerShell scripts by using Microsoft Intune, see [Manage PowerShell scripts in Intune for Windows 10 devices](https://docs.microsoft.com/intune/intune-management-extension).

### Enrolling Windows 10 devices at scale by using policy

Many customers choose to configure Windows 10 devices using policy, since policies can be centrally managed, are automatically removed when the device leaves the management scope, don't require enabling Windows PowerShell on client devices to manage the associated security configurations, and are much easier to accomplish with mobile device management tools such as Intune.

 All policies described in this section also have *preference* registry key equivalents that can be set by using the deployment script. Policy settings override preference settings if both are set.


These Group Policy objects are under Microsoft\Windows\DataCollection:

| Policy   | Value  |
|-----------------------|------------------|
| CommercialId | In order for your devices to show up in Desktop Analytics, they must be configured with your organization’s Commercial ID. |
| AllowTelemetry  |	1 (Basic), 2 (Enhanced) or 3 (Full) diagnostic data. Desktop Analytics will work with basic diagnostic data, but more features are available when you use the Enhanced level (for example, Device Health requires Enhanced diagnostic data and Desktop Analytics only collects app usage and site discovery data on Windows 10 devices with Enhanced diagnostic data). For more information, see [Configure Windows diagnostic data in your organization](https://docs.microsoft.com/windows/configuration/configure-windows-diagnostic-data-in-your-organization). |
| LimitEnhancedDiagnosticDataWindowsAnalytics |	Only applies when AllowTelemetry=2. Limits the Enhanced diagnostic data events sent to Microsoft to just those needed by Desktop Analytics. For more information, see [Windows 10, version 1709 enhanced diagnostic data events and fields used by Windows Analytics](https://docs.microsoft.com/windows/configuration/enhanced-diagnostic-data-windows-analytics-events-and-fields).|
| AllowDeviceNameInTelemetry |	In Windows 10, version 1803, a separate opt-in is required to enable devices to continue to send the device name. |

You can set these values by using Group Policy (in Computer Configuration > Administrative Templates > Windows Components > Data Collection and Preview Builds). You can also configure devices by using a mobile device management tool such as Intune.

#### To set diagnostic data by using Intune
1. On the main menu bar in Intune, go to manage **Device Configuration**.
2.	Select **Create profile** at the top of the pane. 
3.	Select the Platform **Windows 10 and later** and the Type **Device Restrictions**. 
4.	Select the settings category **Reporting and Telemetry**. 
5.	Select your preferred diagnostic data setting from the drop-down menu labeled **Share usage data**. 
6.	Select **OK** to create the profile. 
7.	To set this diagnostic data level on devices, assign them to the profile.

#### To set the Commercial ID by using Intune
1.	On the main menu bar in Intune, go to manage **Device Configuration**. 
2.	Select **Create profile** at the top of the pane. 
3.	Select the Platform **Windows 10 and later** and the Type **Custom**. 
4.	Select **ADD** to add a custom OMA-URI setting. 
5.	Set the field **OMA-URI** to *./Vendor/MSFT/DMClient/Provider/ProviderID/CommercialID*
6.	From the **Data Type** drop-down menu, select the value **String**. 
7.	In the **value** field enter your Commercial ID value.  
8.	Select **OK** to create the profile. 
9.	To configure the Commercial ID on devices, assign them to the profile.  

You cannot currently set the device name opt-in {can we explain better what this is?} on devices running Windows 10, version 1803 by using Mobile Device Management. Instead, set this by using a Windows PowerShell script {can we provide the script?}. To run a PowerShell script on devices by using Intune, follow these steps:

1.	On the main menu bar, go to manage **Device Configuration**. 
2.	Under **Manage**, select **PowerShell scripts**. 
3.	Select the **add** button at the top of the page. 
4.	Select a PowerShell script to upload. 
5.	Select **Configure**, and then choose to run the script with the user’s credentials on the device (Yes), or system context (No). {is this quoting UI?}  
6.	Choose whether the script must be signed by a trusted publisher (Yes), or if there is no requirement for the script to be signed (No). 
7.	To send the script to devices, assign them to the PowerShell policy.  

{TODO: Document just the part of the script that sets device name opt-in. Here’s the code:}

```powershell
$deviceNameOptInPath = "HKLM:\SOFTWARE\Policies\Microsoft\Windows\DataCollection"

# Create preference key if it doesn’t exist
$testdeviceNameOptInPath = Test-Path -Path $deviceNameOptInPath
If ($testdeviceNameOptInPath -eq $false) {
New-Item -Path $deviceNameOptInPath -ItemType Key}

# Set value to 1 if it’s not already set
if ((Get-ItemProperty -Path $deviceNameOptInPath -Name AllowDeviceNameInTelemetry -ErrorAction SilentlyContinue) -eq $null) {
New-ItemProperty -Path $deviceNameOptInPath -Name AllowDeviceNameInTelemetry -PropertyType DWord -Value 1}
else {
$existingValue = (Get-ItemProperty -Path $deviceNameOptInPath -Name AllowDeviceNameInTelemetry).AllowDeviceNameInTelemetry
            if($existingValue -ne 1) {
Set-ItemProperty -Path $deviceNameOptInPath -Name AllowDeviceNameInTelemetry  -Val}
}
``` 
 ## Troubleshooting
If you encounter difficulty with enrolling devices in Desktop Analytics, check [Desktop Analytics troubleshooting](update-readiness-troubleshooting.md) for suggestions.

| | |
| --- | --- |
| ![done](UDRimages/checklistdone.png) | Learn about Desktop Analytics (this topic) |
| ![done](UDRimages/checklistdone.png) | Get started with accounts, subscriptions, user access, workspaces: [Get started with Desktop Analytics](update-readiness-get-started.md) |
| ![done](UDRimages/checklistdone.png) | Enroll devices in Desktop Analytics to start the flow of diagnostic data: [Enroll devices in Desktop Analytics](update-readiness-enroll-devices.md)|
| ![to do](UDRimages/checklistbox.gif) | Additional steps after device enrollment in Desktop Analytics: [Additional steps after device enrollment in Desktop Analytics](update-readiness-additonal-steps.md) |
| ![to do](UDRimages/checklistbox.gif) | Set up deployment plans -- define global rules and detailed deployment plans for pilot and production: [Define deployment plans with Desktop Analytics](update-readiness-deployment-plans.md) |
| ![to do](UDRimages/checklistbox.gif) | [Deploy pilot with Desktop Analytics](update-readiness-deploy-pilot.md) |
| ![to do](UDRimages/checklistbox.gif) | Deploy to production: [Deploy to production with Desktop Analytics](update-readiness-deploy-production.md) |
| ![to do](UDRimages/checklistbox.gif) | Monitor status and health of the deployment: [Monitor the health and update status of devices](update-readiness-monitoring.md) |
|                                      |                                                    |
| ![to do](UDRimages/checklistbox.gif)   | Additional information: [Troubleshooting](update-readiness-troubleshooting.md)  |
