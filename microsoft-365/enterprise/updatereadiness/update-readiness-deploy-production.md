---
title: Deploy to production with Update Readiness
description: Start and monitor the production deployment
ms.prod: w10
ms.mktglfcycl: manage
ms.sitesec: library
author: Jaimeo
ms.localizationpriority: medium
ms.author: jaimeo
ms.date: 08/22/2018
---

[This information relates to a pre-released product which may be substantially modified before it's commercially released. Microsoft makes no warranties, express or implied, with respect to the information provided here.]

# Deploy to production

There are three main parts to accomplishing the deployment of updates to production devices:

1. [Review assets that need an Upgrade Decision](#review-assets-that-need-an-updgrade-decision)
 To make devices ready for production deployment, their assets (apps, Office apps, Office add-ins, and Office macros) must have their Upgrade Decision set to **Ready** or **Ready with remediations**.
2. [Deploy to devices that are ready](#deploy-to-devices-that-are-ready)
 To accomplish the actual installation of updates to devices that are ready, you use a device management tool such as System Center Configuration Manager (SCCM). Update Readiness will provide the list of devices ready for production deployment, as well as reports for monitoring the success of the deployment.
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

You can explore further by clicking any specific advisory to see additional details, for example, the relevant list of devices affected. You can also export this list for later use, such as to run the Readiness Toolkit on this subgroup for still more detail about reported issues like the names of the files for which the advisories were raised.

{SCREENSHOTS/STEPS FROM RITU}

 There might also be assets in the **At Risk** or **Mixed Results** state that could require additional review from you before you make an upgrade decision for them. Select either of these to obtain additional detailed information. As you review each of these specific resources, you set the upgrade decision for it. For example, in the **Apps** tab, if you click a particular app (such as Notepad++ in this image), you can see detailed statistics about its deployment:

[![production app detail view](UDRimages/UDR-app-detail.png)](UDRimages/UDR-app-detail.png)

Based on the data displayed there, you can set an upgrade decision for that particular app. In this example, the administrator has indicated that the Office app Excel 2016 is ready for upgrade. For more information, see the [Monitor the health of updated devices](#monitor-the-health-of-updated-devices) and {link to an "asset" topic?}.


[![production app set to ready](UDRimages/UDR-app-upgrade-ready.png)](UDRimages/UDR-app-upgrade-ready.png)

Repeat this process for all apps, Office apps, and Office add-ins. Once a given device has a positive upgrade decision for *all* assets (drivers and all apps, Office apps, and Office add-ins installed on it), then its state changes to "ready for production." You can see the current count on the main page for the deployment plan by clicking **3. Deploy**:

[![production ready count](UDRimages/UDR-prod-prog2.png)](UDRimages/UDR-prod-prog2.png)

## Deploy to devices that are ready

{separate export from the export for the pilot?}

Export the list of devices {somehow} to pass over to SCCM manually. Once your deployment implementation tool has started the pilot deployment, you can use Update Readiness to monitor the progress and results of the deployment.

### Address deployment alerts

As with the pilot deployment, Update Readiness will advise you of any issues that need your attention during the production deployment.

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

### Office macros
{SHOULDN'T THE MACRO STUFF GO UP HERE SINCE WHAT YOU CHOOSE THERE AFFECTS THE UPGRADE DECISION?}
If devices in your environment use Office macros, you can review the usage data and advisories offered by Update Readiness in order to further {inform your decisions about which devices to include in the production deployment.}

[![assets macros advisories](UDRimages/UDR-macro-advisory.png)](UDRimages/UDR-macro-advisory.png)

You can explore further by clicking any specific advisory to see additional details, for example, the relevant list of devices affected. You can also export this list for later use, such as to run the Readiness Toolkit on this subgroup for still more detail about reported issues.

>[!TIP]
>If you plan to run the Readiness Toolkit [LINK](https://aka.ms/readinesstoolkit) on this subgroup, it's best to wait until after the pilot deployment is complete to delve into remediating the reported macro issues.

[![assets macros advisory detail](UDRimages/UDR-macro-advisory-detail.png)](UDRimages/UDR-macro-advisory-detail.png)

As you address these deployment issues, the dashboard will continue to show the progress of devices by updating as devices move from **Needs attention** to **Completed**.

You can commence the production deployment at any time you are sufficiently confident in the success of the pilot deployment--there is no requirement that all (or any particular number) of devices in the pilot deployment reach the "completed" state prior to doing so.

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
>To reduce the number of assets with insufficient data, we monitor the asset on all of your devices that have upgraded to the target Windows or Office version specified in your deployment plan *including devices not included in that specific deployment plan*.

Whether or not a slicer is selected, the default sort order is by number of devices that have had an incident with that particular asset, so you can quickly see which ones are causing the most problems.

Though there is a slicer for assets that need attention, many IT pros want to look at health for all assets, even those with insufficient data for us to make statistical inferences. Here’s one way to do this:
first, consider selecting the **Devices with incidents in last two weeks** column and filter to only those assets that have had incidents on some minimum number of devices to be interesting:
















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







