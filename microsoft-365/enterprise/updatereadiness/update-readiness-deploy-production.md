---
title: Deploy to production with Update Readiness
description: Start and monitor the production deployment
ms.prod: w10
ms.mktglfcycl: manage
ms.sitesec: library
author: Jaimeo
ms.localizationpriority: high
ms.author: jaimeo
ms.date: 08/02/2018
---

# Deploy to production

You can commence the production deployment at any time you are sufficiently confident in the success of the pilot deployment--there is no requirement that all (or any particular number) of devices in the pilot deployment reach the "completed" state prior to doing so.

Update Readiness will have already determined which devices are ready to upgrade with respect to their operating system and device driver versions (based on the parameters you set earlier in the process), but at this point it remains for the administrator to refine the upgrade decision by reviewing additional assets, such as apps, Office apps, and Office add-ins.

Begin by clicking the **Review** button:

[![production plan upgrade view](UDRimages/UDR-prod-plan-review.png)](UDRimages/UDR-prod-plan-review.png)

This opens a view where you can review the state of apps, Office apps, and Office add-ins and use that information to set the upgrade decision for each of those assets.

## Review assets

Use each of the tabs to review the status of apps, Office apps, and Office add-ins. In each tabbed view, you can filter the results to show devices that are on track for upgrade (that is, they have no detected issues), those at risk, devices with mixed results, and those in an undetermined state.

[![production plan assets view](UDRimages/UDR-prod-assets.png)](UDRimages/UDR-prod-assets.png)

As you review each of these specific resources, you set the upgrade decision for it. For example, in the **Apps** tab, if you click a particular app (such as Notepad++ in this image), you can see detailed statistics about its deployment:

[![production app detail view](UDRimages/UDR-app-detail.png)](UDRimages/UDR-app-detail.png)

Based on the data displayed there, you can set an upgrade decision for that particular app. In this example, the administrator has indicated that the Office app Excel 2016 is upgrade-ready.


[![production app set to ready](UDRimages/UDR-app-upgrade-ready.png)](UDRimages/UDR-app-uprade-ready.png)

Repeat this process for all apps, Office apps, and Office add-ins. Once a given device has a positive upgrade decision for *all* assets (drivers and all apps, Office apps, and Office add-ins installed on it), then its state changes to "ready for production." You can see the current count on the main page for the deployment plan by clicking **3. Deploy**:

[![production ready count](UDRimages/UDR-prod-prog.png)](UDRimages/UDR-prod-prog.png)








