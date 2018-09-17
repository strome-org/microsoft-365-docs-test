---
title: Create and manage deployment plans in Desktop Analytics
description: How to create a deployment plan in Desktop Analytics
ms.prod: w10
ms.mktglfcycl: manage
ms.sitesec: library
author: jwhit-msft
ms.localizationpriority: medium
ms.author: jwhit
ms.date: 09/17/2018
---

# Create a deployment plan in Desktop Analytics

> [!IMPORTANT]
> This information relates to a pre-released product which may be substantially modified before it's commercially released. Microsoft makes no warranties, express or implied, with respect to the information provided here.

Follow the steps in this article to use Desktop Analytics to create a plan for deploying Windows 10 and Office 365 ProPlus. You can create deployment plans for Windows 10 and Office 365 ProPlus separately or together.

## What is a deployment plan?

Desktop Analytics collects and analyzes device, application, and driver data in your organization. Based on this analysis and your input, you can use the service to create deployment plans for Windows 10 and Office 365 ProPlus. These deployment plans automatically recommend which devices to include in pilots, identify compatibility issues, suggest mitigations, assess the health of the deployment before, during, and after updates, and track the progress of your deployment.


As part of your deployment plan, you: 

 - Define what products and versions you want to deploy (Windows 10, Office 365 ProPlus, or both)
 - Choose what groups of devices you want to deploy to
 - Create readiness rules for the deployment
 - Define the importance of your apps and Office add-ins
 - Choose pilot devices based on automatic recommendations
 - Decide how to fix issues with apps and Office add-ins based on recommendations from Desktop Analytics

After creating a deployment plan, you use the System Center Configuration Manager connector to deploy the products. Once the deployment starts, Desktop Analytics monitors the deployment based on the settings in the plan.

> [!NOTE]
> Information in Desktop Analytics is refreshed daily. Any changes you make, such as assigning importance to an app or choosing a device to include in a pilot, might not be reflected for 24 hours.

## Before you begin

Before creating a deployment plan, make sure you've completed the following steps:

- [Get started with Desktop Analytics](update-readiness-get-started.md)
- [Enroll devices in Desktop Analytics](update-readiness-enroll-devices.md)
- Define the groups of devices you want to deploy to. [[Need new article to link to. In the meantime, captured limited guidance in the note below.]]

If you've connected Desktop Analytics to System Center Configuration Manager, you can select your Configuration Manager groups. If you don't use Configuration Manager or if you want to create a new query-based group, click **Create your group in OMS** when choosing target groups. If you create a query-based group, make sure that the query is not based on a computer value that changes as part of the deployment. For more information on how to create groups, see [Computer groups in Log Analytics log searches](https://docs.microsoft.com/en-us/azure/log-analytics/log-analytics-computer-groups). 
 

## Step 1: Create a deployment plan

You can create a single deployment plan to cover all your devices or multiple deployment plans to cover different groups of devices and different versions of Windows and Office. 

![Create a deployment plan](UDRimages/UDR-plans-createplan.png)

1. On the dashboard, click **Deployment Plans**.
2. In the **Deployment Plans** pane, click **Create**.
3. In **Create deployment plan**, type a name for the plan.
4. Choose which products and versions to deploy. We recommend creating deployment plans for Office and Windows together and using the most recent versions.
5. Choose the groups you want to deploy to. 
6. Define any readiness rules you want for your deployment plan. As part of your readiness rules, you can specify the following:
 - Whether your devices automatically receive drivers from Windows Update. If devices receive the driver updates from Windows Update, then any driver issues identified as part of readiness assessment are automatically marked as **Ready**.
 - Low install count threshold for your Windows apps. If an app is installed on a higher percentage of computers than this threshold, the deployment plan will mark the app as Noteworthy, which means you can decide how important it is to test during the pilot phase.
 - Update Office 365 ProPlus from 32-bit to 64-bit on devices that have a 64-bit version of Windows. Default setting is **Yes**.
 - When updating from an older version of Office, leave older Office apps, even if those apps don't exist in the newer version of Office. Default setting is **No**. 
 - Low install count threshold for your Office add-ins. If an add-in is installed on a higher percentage of computers than this threshold, the deployment plan will mark the add-in as Noteworthy, which means you can decide how important it is to test during the pilot phase.
7. Choose the completion date by which Windows and Office should be fully deployed to all the specified devices.
8. Click **Create**. The new plan will appear in the list of deployment plans.

## Step 2: Set the importance of your apps and Office add-ins

As part of the deployment plan, you set the importance of the apps and Office add-ins that are installed on the devices you're deploying to. This setting helps determine which devices are included in the pilot phase of the deployment. 

Any app or add-in that's installed on less than 2% of the devices targeted in the deployment plan is marked Low Install Count. (Two percent is the default setting; you can adjust the threshold in the readiness settings from 0 to 10%.) Low install count apps and add-ins are automatically marked as **Ready to upgrade**.  

For the remaining apps and add-ins, you can choose **Critical**, **Important**, or **Not important**. If you mark an app or add-in as critical or important, Desktop Analytics will include some devices with that app or add-in in the pilot deployment. (Making an app or add-in critical means more instances of it will be included in the pilot.) If you mark an app or add-in as Not Important, Desktop Analytics automatically sets it to **Ready to upgrade**.

![Set importance](UDRimages/UDR-plans-importance.png)

To change the importance level of an app or add-in:

1.  On the dashboard, click **Identify importance**.
2. On the apps tab, click **Not Reviewed** to view the apps that need your input. 
3.  Select the apps you want to change, click **Edit**, and then choose **Critical**, **Important**, or **Not Important** from the **Importance** list. Note that you can select multiple apps to edit at the same time. 
 
    > [!NOTE]
    > When assigning importance levels, you can also choose the Upgrade decision.   
4.  Click **Save**.
5. Click the **Office Add-ins** tab, and update the importance of the add-ins.

## Step 3: Choose pilot devices

After you've defined the importance of the apps and Office add-ins, Desktop Analytics combines that information with the global pilot settings to create a recommendation for which devices should be part of the pilot deployment. The recommended pilot deployment includes devices with different hardware configurations and one or more instances of all the critical and important apps. (If an app is marked critical, the service recommends more devices with that app in the pilot.)

In this step, you review, edit, and approve the pilot recommendations. By the end of this step, you'll have approved a set of devices for the pilot deployment.

![Choose pilot devices](UDRimages/UDR-plans-identifypilot.png)

1. On the dashboard, click Identify pilot.
2. In the Identify pilot pane, review the recommended devices for the pilot. 
3. Select seach device and click **Add to pilot** or, if you disagree with the recommendation, **Replace**.

For details on how the recommendations are made, click the information icon in the top right corner of the **Identify Pilot** pane.



| | |
| --- | --- |
| ![done](UDRimages/checklistdone.png) | Learn about Desktop Analytics |
| ![done](UDRimages/checklistdone.png) | Get started with accounts, subscriptions, user access, workspaces: [Get started with Desktop Analytics](update-readiness-get-started.md) |
| ![done](UDRimages/checklistdone.png) | Enroll devices in Desktop Analytics to start the flow of diagnostic data: [Enroll devices in Desktop Analytics](update-readiness-enroll-devices.md)|
| ![done](UDRimages/checklistdone.png) | Additional steps after device enrollment in Desktop Analytics: [Additional steps after device enrollment in Desktop Analytics](update-readiness-additonal-steps.md) |
| ![done](UDRimages/checklistdone.png)  | Set up deployment plans -- define detailed deployment plans for pilot and production: [Define deployment plans with Desktop Analytics](update-readiness-deployment-plans.md) (this topic) |
| ![to do](UDRimages/checklistbox.gif) | [Deploy pilot with Desktop Analytics](update-readiness-deploy-pilot.md) |
| ![to do](UDRimages/checklistbox.gif) | Deploy to production: [Deploy to production with Desktop Analytics](update-readiness-deploy-production.md) |
| ![to do](UDRimages/checklistbox.gif) | Monitor status and health of the deployment: [Monitor the health and update status of devices](update-readiness-monitoring.md) |
|                                      |                                                    |
| ![to do](UDRimages/checklistbox.gif)   | Additional information: [Troubleshooting](update-readiness-troubleshooting.md)  |

