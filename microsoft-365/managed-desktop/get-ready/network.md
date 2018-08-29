---
title: Network configuration for Microsoft Managed Desktop 
description:  
keywords: Microsoft Managed Desktop, Microsoft 365, service, documentation
ms.service: m365-md
author: jdeckerms
ms.localizationpriority: medium
ms.date: 09/24/2018
---

#  Network configuration for Microsoft Managed Desktop

<!--Proxy config -->


## Proxy configuration

Microsoft Managed Desktop is a cloud-managed service. There is a set of endpoints that the Microsoft Managed Desktop services needs to be able to reach. Most customers will set up a proxy or firewall to only allow network traffic from specific domains for security reason. This section lists the endpoints that need to be allowed. 

### Proxy requirement

The proxy or firewall must support TLS 1.2. Otherwise, you may have to disable protocol detection.

### Endpoints allowed

These URLs needs to be in the allowed list so that mWaaS devices can communicate with Microsoft Services.

Microsoft service  | URLs required on allow list | Documentation source
--- | --- | ---
Windows Update for Business (WUfB) | update.microsoft.com<br>\*.update.microsoft.com<br>download.windowsupdate.com<br>\*.download.windowsupdate.com<br>download.microsoft.com<br>\*.download.microsoft.com<br>windowsupdate.com<br>\*.windowsupdate.com<br>ntservicepack.microsoft.com<br>wustat.windows.com<br>login.live.com <br>mp.microsoft.com<br>\*.mp.microsoft.com | [Windows Update for Business firewall and proxy requirements](https://support.microsoft.com/help/3084568/can-t-download-updates-from-windows-update-from-behind-a-firewall-or-p)
Delivery Optimization | \*.do.dsp.mp.microsoft.com<br>\*.dl.delivery.mp.microsoft.com <br>\*.emdl.ws.microsoft.com<br>\*.download.windowsupdate.com <br>\*.windowsupdate.com   | [Windows Update proxy requirements](https://support.microsoft.com/help/3175743/proxy-requirements-for-windows-update)
Microsoft Store for Business | login.live.com <br>account.live.com <br>clientconfig.passport.net <br>wustat.windows.com <br>\*.windowsupdate.com <br>\*.wns.windows.com <br>\*.hotmail.com <br>\*.outlook.com <br>\*.microsoft.com <br>\*.msftncsi.com/ncsi.txt   | [Microsoft Store allow list](https://support.microsoft.com/help/2778122/using-authenticated-proxy-servers-together-with-windows-8)
Office 365 | \*.office365.com<br>\*.office.com<br>\*.office.net<br>\*.live.com<br>\*.portal.cloudappsecurity.com<br>\*.portal.cloudappsecurity.com<br>\*.us.portal.cloudappsecurity.com<br>\*.eu.portal.cloudappsecurity.com<br>\*.us2.portal.cloudappsecurity.com<br><tenant>.onmicrosoft.com<br>account.office.net<br>agent.office.net<br>apc.delve.office.com<br>aus.delve.office.com<br>can.delve.office.com<br>delve.office.com<br>eur.delve.office.com<br>gbr.delve.office.com<br>home.office.com<br>ind.delve.office.com<br>jpn.delve.office.com<br>kor.delve.office.com<br>lam.delve.office.com<br>nam.delve.office.com<br>portal.office.com<br>outlook.office365.com<br>suite.office.net<br>webshell.suite.office.com<br>www.office.com<br>\*.aria.microsoft.com<br>browser.pipe.aria.microsoft.com<br>mobile.pipe.aria.microsoft.com<br>portal.microsoftonline.com<br>clientlog.portal.office.com<br>nexus.officeapps.live.com<br>nexusrules.officeapps.live.com<br>amp.azure.net<br>\*.o365weve.com<br>auth.gfx.ms<br>appsforoffice.microsoft.com<br>assets.onestore.ms<br>az826701.vo.msecnd.net<br>c.microsoft.com<br>c1.microsoft.com<br>client.hip.live.com<br>contentstorage.osi.office.net<br>dgps.support.microsoft.com<br>docs.microsoft.com<br>groupsapi-<br>rod.outlookgroups.ms<br>groupsapi2-prod.outlookgroups.ms<br>groupsapi3-prod.outlookgroups.ms<br>groupsapi4-prod.outlookgroups.ms<br>msdn.microsoft.com<br>platform.linkedin.com<br>products.office.com<br>prod.msocdn.com<br>r1.res.office365.com<br>r4.res.office365.com<br>res.delve.office.com<br>shellprod.msocdn.com<br>support.content.office.net<br>support.microsoft.com<br>support.office.com<br>technet.microsoft.com<br>templates.office.com<br>video.osi.office.net<br>videocontent.osi.office.net<br>videoplayercdn.osi.office.net<br>\*.manage.office.com<br>\*.protection.office.com<br>manage.office.com<br>Protection.office.com<br>diagnostics.office.com | [Office 365 URL and IP address ranges](https://docs.microsoft.com/office365/enterprise/urls-and-ip-address-ranges)
Azure Active Directory | api.login.microsoftonline.com<br>api.passwordreset.microsoftonline.com<br>autologon.microsoftazuread-sso.com<br>becws.microsoftonline.com<br>clientconfig.microsoftonline-p.net <br>companymanager.microsoftonline.com <br>device.login.microsoftonline.com <br>hip.microsoftonline-p.net <br>hipservice.microsoftonline.com <br>login.microsoft.com<br>login.microsoftonline.com <br>logincert.microsoftonline.com <br>loginex.microsoftonline.com<br>login-us.microsoftonline.com <br>login.microsoftonline-p.com <br>login.windows.net <br>nexus.microsoftonline-p.com <br>passwordreset.microsoftonline.com <br>provisioningapi.microsoftonline.com<br>stamp2.login.microsoftonline.com<br>\*.msappproxy.net<br>ccs.login.microsoftonline.com<br>ccs-sdf.login.microsoftonline.com<br>accounts.accesscontrol.windows.net<br>secure.aadcdn.microsoftonline-p.com<br>\*.phonefactor.net<br>account.activedirectory.windowsazure.com<br>secure.aadcdn.microsoftonline-p.com<br>graph.microsoft.com | [Hybrid identity required ports and protocols](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect-ports) and [Active Directory and Active Directory Domain Services Port Requirements](https://aka.ms/AA26ygm) 
Microsoft Intune | login.microsoftonline.com<br>portal.manage.microsoft.com<br>m.manage.microsoft.com<br>sts.manage.microsoft.com<br>Manage.microsoft.com <br>i.manage.microsoft.com <br>r.manage.microsoft.com <br>a.manage.microsoft.com <br>p.manage.microsoft.com <br>EnterpriseEnrollment.manage.microsoft.com <br>EnterpriseEnrollment-s.manage.microsoft.com<br>portal.fei.msua01.manage.microsoft.com<br>m.fei.msua01.manage.microsoft.com<br>fei.msua01.manage.microsoft.com<br>portal.fei.msua01.manage.microsoft.com <br>m.fei.msua01.manage.microsoft.com<br>fei.msua02.manage.microsoft.com<br>portal.fei.msua02.manage.microsoft.com<br>m.fei.msua02.manage.microsoft.com<br>fei.msua02.manage.microsoft.com<br>portal.fei.msua02.manage.microsoft.com<br>m.fei.msua02.manage.microsoft.com<br>fei.msua04.manage.microsoft.com<br>portal.fei.msua04.manage.microsoft.com <br>m.fei.msua04.manage.microsoft.com<br>fei.msua04.manage.microsoft.com<br>portal.fei.msua04.manage.microsoft.com <br>m.fei.msua04.manage.microsoft.com<br>fei.msua05.manage.microsoft.com <br>portal.fei.msua05.manage.microsoft.com <br>m.fei.msua05.manage.microsoft.com<br>fei.msua05.manage.microsoft.com <br>portal.fei.msua05.manage.microsoft.com <br>m.fei.msua05.manage.microsoft.com<br>fei.amsua0502.manage.microsoft.com <br>portal.fei.amsua0502.manage.microsoft.com <br>m.fei.amsua0502.manage.microsoft.com<br>fei.amsua0502.manage.microsoft.com <br>portal.fei.amsua0502.manage.microsoft.com <br>m.fei.amsua0502.manage.microsoft.com<br>fei.msua06.manage.microsoft.com <br>portal.fei.msua06.manage.microsoft.com <br>m.fei.msua06.manage.microsoft.com<br>fei.msua06.manage.microsoft.com <br>portal.fei.msua06.manage.microsoft.com <br>m.fei.msua06.manage.microsoft.com<br>fei.amsua0602.manage.microsoft.com <br>portal.fei.amsua0602.manage.microsoft.com <br>m.fei.amsua0602.manage.microsoft.com<br>fei.amsua0602.manage.microsoft.com <br>portal.fei.amsua0602.manage.microsoft.com <br>m.fei.amsua0602.manage.microsoft.com<br>fei.msub01.manage.microsoft.com <br>portal.fei.msub01.manage.microsoft.com <br>m.fei.msub01.manage.microsoft.com<br>fei.msub01.manage.microsoft.com <br>portal.fei.msub01.manage.microsoft.com <br>m.fei.msub01.manage.microsoft.com<br>fei.amsub0102.manage.microsoft.com <br>portal.fei.amsub0102.manage.microsoft.com <br>m.fei.amsub0102.manage.microsoft.com<br>fei.amsub0102.manage.microsoft.com <br>portal.fei.amsub0102.manage.microsoft.com <br>m.fei.amsub0102.manage.microsoft.com<br>fei.msub02.manage.microsoft.com <br>portal.fei.msub02.manage.microsoft.com <br>m.fei.msub02.manage.microsoft.com<br>fei.msub02.manage.microsoft.com <br>portal.fei.msub02.manage.microsoft.com <br>m.fei.msub02.manage.microsoft.com<br>fei.msub03.manage.microsoft.com <br>portal.fei.msub03.manage.microsoft.com <br>m.fei.msub03.manage.microsoft.com<br>fei.msub03.manage.microsoft.com <br>portal.fei.msub03.manage.microsoft.com <br>m.fei.msub03.manage.microsoft.com<br>fei.msub05.manage.microsoft.com <br>portal.fei.msub05.manage.microsoft.com <br>m.fei.msub05.manage.microsoft.com<br>fei.msub05.manage.microsoft.com <br>portal.fei.msub05.manage.microsoft.com <br>m.fei.msub05.manage.microsoft.com<br>fei.msuc01.manage.microsoft.com <br>portal.fei.msuc01.manage.microsoft.com <br>m.fei.msuc01.manage.microsoft.com<br>fei.msuc01.manage.microsoft.com <br>portal.fei.msuc01.manage.microsoft.com <br>m.fei.msuc01.manage.microsoft.com<br>fei.msuc02.manage.microsoft.com <br>portal.fei.msuc02.manage.microsoft.com <br>m.fei.msuc02.manage.microsoft.com<br>fei.msuc02.manage.microsoft.com <br>portal.fei.msuc02.manage.microsoft.com <br>m.fei.msuc02.manage.microsoft.com<br>fei.msuc03.manage.microsoft.com <br>portal.fei.msuc03.manage.microsoft.com <br>m.fei.msuc03.manage.microsoft.com<br>fei.msuc03.manage.microsoft.com <br>portal.fei.msuc03.manage.microsoft.com <br>m.fei.msuc03.manage.microsoft.com<br>fei.msuc05.manage.microsoft.com <br>portal.fei.msuc05.manage.microsoft.com <br>m.fei.msuc05.manage.microsoft.com<br>fei.msuc05.manage.microsoft.com <br>portal.fei.msuc05.manage.microsoft.com <br>m.fei.msuc05.manage.microsoft.com<br>fef.msua01.manage.microsoft.com<br>fef.msua02.manage.microsoft.com<br>fef.msua04.manage.microsoft.com<br>fef.msua05.manage.microsoft.com<br>fef.msua06.manage.microsoft.com<br>fef.msua07.manage.microsoft.com<br>fef.msub01.manage.microsoft.com<br>fef.msub02.manage.microsoft.com<br>fef.msub03.manage.microsoft.com<br>fef.msub05.manage.microsoft.com<br>fef.msuc01.manage.microsoft.com<br>fef.msuc02.manage.microsoft.com<br>fef.msuc03.manage.microsoft.com<br>fef.msuc05.manage.microsoft.com |  [Intune network configuration requirements]( https://docs.microsoft.com/intune/network-bandwidth-use)
