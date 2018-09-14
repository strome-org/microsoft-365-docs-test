---
title: Deploy to production with Desktop Analytics
description: Start and monitor the production deployment
ms.prod: w10
ms.mktglfcycl: manage
ms.sitesec: library
author: Jaimeo
ms.localizationpriority: medium
ms.author: jaimeo
ms.date: 09/14/2018
---

[This information relates to a pre-released product which may be substantially modified before it's commercially released. Microsoft makes no warranties, express or implied, with respect to the information provided here.]

# Deploy to production

There are three main parts to accomplishing the deployment of updates to production devices:

1. [Review assets that need an Upgrade Decision](#review-assets-that-need-an-updgrade-decision)
 To make devices ready for production deployment, their assets (apps, Office apps, Office add-ins, and Office macros) must have their Upgrade Decision set to **Ready** or **Ready, remediations required**.
2. [Deploy to devices that are ready](#deploy-to-devices-that-are-ready)
 To accomplish the actual installation of updates to devices that are ready, you use a device management tool such as System Center Configuration Manager (SCCM). Desktop Analytics will provide the list of devices ready for production deployment, as well as reports for monitoring the success of the deployment.
3. [Monitor the health of updated devices](#montor-the-health-of-updated-devices)
 As the update deployment progresses, you can monitor the health of noteworthy assets. If some need attention, you can troubleshoot and fix those issues or, if you decide the issues can't be fixed, you can stop the deployment to the affected devices by setting the Upgrade Decision to **Unable** for them.

> [!NOTE]
> You can commence the production deployment at any time you are sufficiently confident in the success of the pilot deployment--there is no requirement that all (or any particular number) of devices in the pilot deployment reach the "completed" state prior to doing so.

## Review assets that need an Upgrade Decision

The **Prepare production** page guides you through the process of reviewing your assets for production deployment. To get to this page, either select **Prepare production** in the left pane or select the **Review** button on the **Deployment plans** page:

[![production plan upgrade view](UDRimages/UDR-prod-plan-review.png)](UDRimages/UDR-prod-plan-review.png)

This opens a view where you can review the state of apps, Office apps, Office add-ins, and Office macros and use that information to set the upgrade decision for each of those assets.

[![production plan assets view](UDRimages/UDR-prod-assets.png)](UDRimages/UDR-prod-assets.png)

Use each of the tabs to review the status of apps, Office apps, Office add-ins, and Office macros. In each tabbed view, you can filter the results to show devices that are on track for upgrade (that is, they have no detected issues), those at risk, devices with mixed results, and those in an undetermined state.

Select **On track** to quickly filter the view to assets that are likely to be ready for production deployment based on these criteria:

- Risk: our pre-upgrade assessment of known risks for updating devices that have this asset installed {link to an "asset" topic?}
- Health status: our post-upgrade assessment of devices in other deployments and whether they experienced problems after the update was installed. For more information about health, see [Monitor the health of updated devices](#montor-the-health-of-updated-devices).

[![production plan assets view showing "on track"](UDRimages/UDR-prod-assets-ontrack.png)](UDRimages/UDR-prod-assets-ontrack.png)

You can quickly approve these assets for upgrade by selecting the leftmost column header and then selecting **+ Set Upgrade Decision**:

[![production plan assets view showing "on track" and all selected for upgrade](UDRimages/UDR-prod-assets-ontrack-setupgrade.png)](UDRimages/UDR-prod-assets-ontrack-setupgrade.png)

Similarly, you can select **Undetermined** to view assets that could not be classified. These generally are assets that do not have enough coverage for us to perform an analysis of the risk or health status. You might consider adding additional devices with these assets to the pilot or ask pilot users to try these assets to improve the coverage.

### Office macros

For Office macros, what is presented is not the actual macro-enabled files but, instead, advisories related to those files.
 
{Insert Sign-off view for Macros} 

You can explore further by selecting any specific advisory to see additional details, for example, the relevant list of devices affected. You can also export this list for later use, such as to run the Readiness Toolkit on this subgroup for still more detail about reported issues like the names of the files for which the advisories were raised.

{SCREENSHOTS/STEPS FROM RITU}

 There might also be assets in the **At Risk** or **Mixed Results** state that could require additional review from you before you make an upgrade decision for them. Select either of these to obtain additional detailed information. As you review each of these specific resources, you set the upgrade decision for it. For example, in the **Apps** tab, if you click a particular app (such as Notepad++ in this image), you can see detailed statistics about its deployment:

[![production app detail view](UDRimages/UDR-app-detail.png)](UDRimages/UDR-app-detail.png)

Based on the data displayed there, you can set an upgrade decision for that particular app. In this example, the administrator has indicated that the Office app Excel 2016 is ready for upgrade. For more information, see the [Monitor the health of updated devices](#monitor-the-health-of-updated-devices) and {link to an "asset" topic?}.


[![production app set to ready](UDRimages/UDR-app-upgrade-ready.png)](UDRimages/UDR-app-upgrade-ready.png)

Repeat this process for all apps, Office apps, and Office add-ins. Once a given device has a positive upgrade decision for *all* assets (drivers and all apps, Office apps, and Office add-ins installed on it), then its state changes to "ready for production." You can see the current count on the main page for the deployment plan by clicking **3. Deploy**:

[![production ready count](UDRimages/UDR-prod-prog2.png)](UDRimages/UDR-prod-prog2.png)

## Deploy to devices that are ready

{separate export from the export for the pilot?}

Export the list of devices {somehow} to pass over to SCCM manually. Once your deployment implementation tool has started the pilot deployment, you can use Desktop Analytics to monitor the progress and results of the deployment.

### Address deployment alerts

As with the pilot deployment, Desktop Analytics will advise you of any issues that need your attention during the production deployment.

To get details of reported issues click **Review**. The deployment status details page opens, where you can view lists of the devices in these categories:

- Not started
- In progress
- Completed
- Needs attention - devices
- Needs attention - issues

The **Needs attention** categories show the same information, but sorted differently.

Sorted by affected device:

[![devices needing attention sorted by device](UDRimages/UDR-needatten-device.png)](UDRimages/UDR-needatten-device.png)

Sorted by type of issue:

[![devices needing attention sorted by issue](UDRimages/UDR-needatten-issue.png)](UDRimages/UDR-needatten-issue.png)

Click a specific listing in either view to get more details about the detected issue:

[![devices needing attention sorted by issue](UDRimages/UDR-needatten-detail.png)](UDRimages/UDR-needatten-detail.png)

You can start deploying to production at any time you are sufficiently confident in the success of the pilot deployment--there is no requirement that all (or any particular number) of devices in the pilot deployment reach the "completed" state prior to doing so.

## Monitor the health of updated devices

The **Monitor health** page lets you monitor the health of all the noteworthy assets in your deployment plan. Unlike the **Prepare production** page, which focuses on helping you make upgrade decisions for your assets (where the default slicer filters to only those assets that are not yet in the **Ready** state), the **Monitor health** page focuses on showing health issues on any noteworthy asset, even those that are marked **Ready**. If issues are discovered, you can troubleshoot and fix the problem or change the upgrade decision to *Unable* to prevent future upgrades on devices with that asset.

The default slicer applied to this page filters to assets that need attention, which means that we have detected a statistically significant regression to some health metric for that asset (see {somewhere} for details of how this is done). In addition to **Attention needed**, the other possible health status values are as follows:

| **Health status**  | **Meaning**  |
|---------------------------------------------------------|-----------|
| Meeting goals | No regression in behavior detected|
| Insufficient data | No usage data yet available for this asset |

{possibly just include all health statuses and short def of meaning into this table}

You can select the slicer to deselect it, which will show you an unfiltered view: 

[![screenshot provided by marcshep2](UDRimages/marcshep2.png)](UDRimages/marcshep2.png)

>[!NOTE]
>To reduce the number of assets with insufficient data, we monitor the assets on all of your devices that have upgraded to the target Windows or Office version specified in your deployment plan *including devices not included in that specific deployment plan*.

Whether or not a slicer is selected, the default sort order is by number of devices that have had an incident with that particular asset, so you can quickly see which ones are causing the most problems.

Though there is a slicer for assets that need attention, many IT pros want to look at health for all assets, even those with insufficient data for us to make statistical inferences. Here’s one way to do this:
first, consider selecting the **Devices with incidents in last two weeks** column and filter to only those assets that have had incidents on some minimum number of devices to be interesting:

[![screenshot provided by marcshep1](UDRimages/marcshep1.png)](UDRimages/marcshep1.png)

[![screenshot provided by marcshep2](UDRimages/marcshep2.png)](UDRimages/marcshep2.png)
[![screenshot provided by marcshep3](UDRimages/marcshep3.png)](UDRimages/marcshep3.png)

Next, select the **% Devices with incidents in the last 2 weeks** column and switch the sort order to descending:

[![screenshot provided by marcshep4](UDRimages/marcshep4.png)](UDRimages/marcshep4.png)

The resulting view shows the assets that have the highest incident rates (but only assets with a minimum number of incidents):

[![screenshot provided by marcshep5](UDRimages/marcshep5.png)](UDRimages/marcshep5.png)

Finally, select any particular asset to get more details or change the upgrade decision for it:

[![screenshot provided by marcshep6](UDRimages/marcshep6.png)](UDRimages/marcshep6.png)

### Details of health status monitoring

This section explains in detail how health monitoring works.

>[!NOTE]
>Desktop Analytics only collects health data from devices that provide usage data we can use as a denominator. This means that devices running Windows 7 and Windows 10 devices that are not set to share diagnostic data at the Enhanced level are not included. If more than 10% of devices running Windows 10 are set to share diagnostic data at levels other than Enhanced, you will see a warning in the banner area of the **Monitor health** page.

[![screenshot provided by marcshep6](UDRimages/marcshep6.png)](UDRimages/marcshep6.png)

You can see in the flyout of this view a number of things that Desktop Analytics monitors:

- **% Device with crashes** is the number of devices that this particular app has crashed on in the last two weeks divided by the number devices that the app has been used on in the last two weeks. We calculate this for several parameters as follows:
    - **After upgrade** devices are those that have upgraded to the target operating system version specified in the deployment plan. We collect this data for all  ofyour upgraded devices (even those not included in the  deployment plan) in order to reduce the number of assets with insufficient data.
    - **Before upgrade** devices are that are on an operating system version older than {OLDER THAN WHAT?}. This does not include devices running Windows 7. This lets you see whether the crash rate has increased or decreased on the new operating system version.
    - **Commercial avg** lets you see the crash rate across all commercial devices, so you can compare the devices in your organization. The commercial average is calculated across *all* versions of the app, so that if this version shows a crash rate above the commercial average it might be a sign that you are using the wrong version.
- **% Sessions with crashes** is very similar to the above but counts the percentage of sessions with crashes in the last two weeks.

To determine the health status, Desktop Analytics reports “Insufficient data” unless data is available from at least 20 devices. The health status is currently calculated purely based on the session crash rate from these devices (the device crash rate is provided for information only and is not used in the health status calculation).

At the bottom of the page, there are three tabs to help with troubleshooting:

- **Other versions** lets you see alternative versions of this app you might consider deploying. For each version, we show the relative changes to the crash rates within your organization and the commercial average. We also show if the version has a “ready for Windows” signal. If you find a later version of the app with a lower crash rate, it’s a strong signal that an upgrade can help.
- **Top issues** lets you see the most frequent failure IDs by count. A failure ID is a GUID that identifies the stack trace associated with the crash and can be used when you call Microsoft or ISV support to get more information about the issue.
- **Recent crashes** shows recent occurrences of crashes, which you can filter by failure ID and other criteria. You can use this information to troubleshoot the issue by gathering logs or trying fixes on specific devices before on specific devices before trying a broader deployment.

If you find a serious health regression that you are unable to fix, you can change the **Upgrade decision** at the top of the fly-out to *Unable* to prevent future deployment of the update to devices that have this asset installed.

#### Health status for Office apps

This section explains health monitoring specifically for Office apps.

{NEED SCREENSHOT}

You can see in the flyout of this view a number of things that Desktop Analytics monitors:

- **% Device with crashes** is the number of devices that this particular app has crashed on in the last two weeks divided by the number devices that the app has been used on in the last two weeks. We calculate this for several parameters as follows:
    - **After upgrade** devices are those that have upgraded to the target operating system version specified in the deployment plan. We collect this data for all of your upgraded devices (even those not included in the  deployment plan) in order to reduce the number of assets with insufficient data.
    - **Before upgrade** devices are those that are on an operating system version older than {OLDER THAN WHAT?}. This does not include devices running Windows 7. This lets you see whether the crash rate has increased or decreased on the new operating system version.
    - **Commercial avg** lets you see the crash rate across all commercial devices, so you can compare the devices in your organization. The commercial average is calculated across *all* versions of the app, so that if this version shows a crash rate above the commercial average it might be a sign that you are using the wrong version.
- **% Sessions with crashes** is very similar to the above but counts the percentage of sessions with crashes in the last two weeks.

To determine the health status, {RITU} to provide details on algo she wants to disclose}

{This is currently a verbatim repeat of the material immediately preceding--do we need to repeat it?}

#### Health status for Office add-ins

This section explains health monitoring specifically for Office add-ins.

[![screenshot provided by javier carillo 1](UDRimages/javcar1.png)](UDRimages/javcar1.png)

You can see in the flyout of this view a number of things that Desktop Analytics monitors:

- **% Device with incidents** is the number of devices on which the selected add-in had an incident that prevented it from working properly in the last two weeks divided by the number of devices on which the add-in is installed. An incident event for an add-in refers to it failing to load or becoming unresponsive. We calculate this for several parameters as follows:
    - **After upgrade** devices are those that have upgraded to the target Office version specified in the deployment plan.sion. We collect this data for all of your upgraded devices (even those not included in the  deployment plan) in order to reduce the number of assets with insufficient data.
    - **Before upgrade** devices those running any version of Office older than the version that the deployment plan targets. This does not include {include min version of Office} . You can compare this metric to the **After upgrade** to assess the health of the add-in.
    - **Commercial average** shows the incident rate across all commercial devices that use the same version of the add-in on the same version of Office. You can use this to compare against devices in your organization so that if this add-in version is having a higher incident rate than the commercial average, it might be a sign that the problem is not the add-in, but a given configuration in your organization.
- **% Sessions with incidents** is very similar to the above but counts the percentage of sessions with crashes in the last two weeks.


To determine the health status of add-ins, Desktop Analytics reports insufficient data unless we collect data from at least 3 devices for the device incident rate and at least 10 sessions for the session incident rate. For both rates we compare the before and after values to determine  if there is a regression--no regression is considered as meeting goals. Ultimately, the overall health status of the add-in is calculated based on a combination of both device and session incident rates using the following matrix:

|  | **Insufficient data for device crashes**  | **Healthy device crash metrics** | **Regression in device crash metrics** |
|----------------|---------------------|-----------------------|------------------------|
| **Insufficient data for sessions with incidents**| **Insufficient data**| **Meeting goals** | **Insufficient data** |
| **Healthy metrics for sessions with incidents** | **Meeting goals** | **Meeting goals** | **Meeting goals** |
| **Regression in metrics for sessions with incidents** | **Insufficient data** | **Meeting goals** | **Attention needed** |

At the bottom of the page, there are three tabs to help with troubleshooting
- **Recent incidents** shows you the devices on which add-in incidents have occurred recently. This lets you see recent occurrences of incidents and the devices on which they took place. You can use this list to troubleshoot the issue by gathering logs or trying fixes on those specific devices before trying a broader rollout.

#### Health status for Office macros
{placeholder for Javier to elaborate}

Let’s have a closer look at how we monitor the Office macros. Rather than informing you about the files on which macro issues might be occurring (which may be a rather large number), we focus on “macro advisories”. These are related to an Office application (i.e. Word macros, Excel macros, PowerPoint macros) and can be generic or detailed (related to specific functionality in the macro object model). 
Not all advisories 
TODO – add screenshot
As you can see from the fly-out above, there are several things we monitor for each macro advisory:
•	“% Devices with runtime errors”: this is the number of devices on which a runtime error related to the advisory took place in the last 2 weeks over the number of devices on which the advisory is present
To determine the health status, <TODO – Javier to specify what level he wishes to describe the algorithm>
At the bottom of the page, there are three tabs to help with troubleshooting
•	<TDODO>

{Original Macros material to preserve image links, etc.}
### Office macros
{SHOULDN'T THE MACRO STUFF GO UP HERE SINCE WHAT YOU CHOOSE THERE AFFECTS THE UPGRADE DECISION?}
If devices in your environment use Office macros, you can review the usage data and advisories offered by Desktop Analytics in order to further {inform your decisions about which devices to include in the production deployment.}

[![assets macros advisories](UDRimages/UDR-macro-advisory.png)](UDRimages/UDR-macro-advisory.png)

You can explore further by clicking any specific advisory to see additional details, for example, the relevant list of devices affected. You can also export this list for later use, such as to run the Readiness Toolkit on this subgroup for still more detail about reported issues.

>[!TIP]
>If you plan to run the Readiness Toolkit [LINK](https://aka.ms/readinesstoolkit) on this subgroup, it's best to wait until after the pilot deployment is complete to delve into remediating the reported macro issues.

[![assets macros advisory detail](UDRimages/UDR-macro-advisory-detail.png)](UDRimages/UDR-macro-advisory-detail.png)

As you address these deployment issues, the dashboard will continue to show the progress of devices by updating as devices move from **Needs attention** to **Completed**.








{1)	Overview (filtered to just noteworthy assets in the DP, calculate health status based on regression analysis on health signals, monitor all devices in your enterprise on the DP target versions, provide tshooters to solve issues and can toggle upgrade decision to halt upgrades to devices with problem assets).
2)	Needs attention->health status->tshooters (to remediate) or upgrade decision (to halt future rollouts)

[![screenshot provided by marcshep1](UDRimages/marcshep1.png)](UDRimages/marcshep1.png)

3)	Browsing health.

[![screenshot provided by marcshep2](UDRimages/marcshep2.png)](UDRimages/marcshep2.png)
[![screenshot provided by marcshep3](UDRimages/marcshep3.png)](UDRimages/marcshep3.png)
[![screenshot provided by marcshep4](UDRimages/marcshep4.png)](UDRimages/marcshep4.png)
[![screenshot provided by marcshep5](UDRimages/marcshep5.png)](UDRimages/marcshep5.png)
[![screenshot provided by marcshep6](UDRimages/marcshep6.png)](UDRimages/marcshep6.png)

}

| | |
| --- | --- |
| ![done](UDRimages/checklistdone.png) | Learn about Desktop Analytics |
| ![done](UDRimages/checklistdone.png) | Get started with accounts, subscriptions, user access, workspaces: [Get started with Desktop Analytics](update-readiness-get-started.md) |
| ![done](UDRimages/checklistdone.png) | Enroll devices in Desktop Analytics to start the flow of diagnostic data: [Enroll devices in Desktop Analytics](update-readiness-enroll-devices.md)|
| ![done](UDRimages/checklistdone.png) | Additional steps after device enrollment in Desktop Analytics: [Additional steps after device enrollment in Desktop Analytics](update-readiness-additonal-steps.md) |
| ![done](UDRimages/checklistdone.png) | Set up deployment plans -- define global rules and detailed deployment plans for pilot and production: [Define deployment plans with Desktop Analytics](update-readiness-deployment-plans.md) |
| ![done](UDRimages/checklistdone.png) | [Deploy pilot with Desktop Analytics](update-readiness-deploy-pilot.md) |
| ![done](UDRimages/checklistdone.png) | Deploy to production: [Deploy to production with Desktop Analytics](update-readiness-deploy-production.md) (this topic) |
| ![to do](UDRimages/checklistbox.gif) | Monitor status and health of the deployment: [Monitor the health and update status of devices](update-readiness-monitoring.md) |
|                                      |                                                    |
| ![to do](UDRimages/checklistbox.gif)   | Additional information: [Troubleshooting](update-readiness-troubleshooting.md)  |








