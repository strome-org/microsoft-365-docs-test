---
title: "Azure AD Seamless Single Sign-on for your Microsoft 365 test environment"
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 08/21/2018
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection: 
- Ent_O365
- Strat_O365_Enterprise
ms.custom: 
- TLGS
- Ent_TLGs
ms.assetid: 
description: "Summary: Configure and test Azure AD Seamless Single Sign-on for your Microsoft 365 test environment."
---

# Azure AD Seamless Single Sign-on for your Microsoft 365 test environment

Azure AD Seamless Single Sign-On (SSO) automatically signs in users when they are on their PCs or devices that are connected to their organization network. Azure AD Seamless SSO provides users with easy access to cloud-based applications without needing any additional on-premises components.

This article describes how you can configure your Microsoft 365 test environment for Azure AD Seamless SSO, resulting in the following:
  
![The simulated enterprise with pass-through authentication test environment](media/pass-through-auth-m365-ent-test-environment/Phase2.png)
  
There are two phases to setting up this test environment:

1.	Create the Microsoft 365 simulated enterprise test environment with password hash synchronization.
2.	Configure Azure AD Connect on APP1 for Azure AD Seamless SSO.
    
![Test Lab Guides for the Microsoft cloud](media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png) 
    
> [!TIP]
> Click [here](https://aka.ms/m365etlgstack) for a visual map to all the articles in the Microsoft 365 Enterprise Test Lab Guide stack.
  
## Phase 1: Create the password hash synchronization for your Microsoft 365 test environment

Follow the instructions in [password hash synchronization for Microsoft 365](password-hash-sync-m365-ent-test-environment.md). Here is your resulting configuration.
  
![The simulated enterprise with password hash synchronization test environment](media/pass-through-auth-m365-ent-test-environment/Phase1.png)
  
This configuration consists of: 
  
- Office 365 E5 and EMS E5 trial or permanent subscriptions.
- A simplified organization intranet connected to the Internet, consisting of the DC1, APP1, and CLIENT1 virtual machines on a subnet of an Azure virtual network. Azure AD Connect runs on APP1 to synchronize the TESTLAB Windows Server AD domain to the Azure AD tenant of your Office 365 and EMS E5 subscriptions periodically.

## Phase 2: Configure Azure AD Connect on APP1 for Azure AD Seamless SSO

In this phase, you configure Azure AD Connect on APP1 for Azure AD Seamless SSO, and then verify that it works.

### Configure Azure AD Connect on APP1

1. From the [Azure portal](https://portal.azure.com), sign in with your global administrator account, and then connect to APP1 with the TESTLAB\User1 account.

2. From the desktop of APP1, run Azure AD Connect.

3. On the **Welcome page**, click **Configure**.

4. On the Additional tasks page, click **Change user sign-in**, and then click **Next**.

5. On the **Connect to Azure AD** page, type your global administrator account credentials, and then click **Next**.

6. On the **User sign-in** page, select **Enable single sign-on**, and then click **Next**.

7. On the **Enable single sign-on** page, click **Enter credentials**.

8. In the **Windows Security** dialog box, type **user1** and the password of the user1 account, and then click **OK**. Click **Next**.

9. On the **Ready to Configure** page, click **Configure**.

10. On the **Configuration complete** page, click **Exit**.

11. From the Azure portal, in the left pane, click **Azure Active Directory > Azure AD Connect**. Verify that the **Seamless single sign-on** feature appears as **Enabled**.

Next, test the ability to sign in to your Office 365 subscription with the user1@testlab.\<your public domain> user name of the User1 account.

1. From Internet Explorer on APP1, click the settings icon, and then click **Internet Options**.
 
2. In **Internet Options**, click the **Security** tab.

3. Click **Local intranet**, and then click **Sites**.

4. In **Local intranet**, click **Advanced**.

5. In **Add this website to the zone**, type <span>https://autologon.microsoftazuread-sso.com</span>, click **Add > Close > OK > OK**.

6. Sign out of Office 365, and then sign in again, this time specifying a different account.

7.	When prompted to sign in, specify **user1@testlab.**\<your public domain> name, and then click **Next**. You should successfully sign in as User1 without being prompted for a password. This proves that Seamless SSO is working.

Notice that although User1 has domain administrator permissions for the TESTLAB Windows Server AD domain, it is not an Office 365 global administrator. Therefore, you will not see the **Admin** icon as an option.

Here is your resulting configuration:

![The simulated enterprise with pass-through authentication test environment](media/pass-through-auth-m365-ent-test-environment/Phase2.png)
 
This configuration consists of:

- Office 365 E5 and EMS E5 trial or permanent subscriptions with the DNS domain TESTLAB.\<your domain name> registered.
- A simplified organization intranet connected to the Internet, consisting of the DC1, APP1, and CLIENT1 virtual machines on a subnet of an Azure virtual network. Azure AD Connect runs on APP1 to synchronize the list of accounts and groups from the Azure AD tenant of your Office 365 and EMS E5 subscriptions to the TESTLAB Windows Server AD domain.

See the [Simplify user sign-in](identity-single-sign-on.md) step in the Identity phase for information and links to configure Azure AD Seamless SSO in production.

## Next step

Explore additional [identity](m365-enterprise-test-lab-guides.md#identity) features and capabilities in your test environment.

## See also

[Microsoft 365 Enterprise Test Lab Guides](m365-enterprise-test-lab-guides.md)

[Deploy Microsoft 365 Enterprise](deploy-microsoft-365-enterprise.md)

[Microsoft 365 Enterprise documentation](https://docs.microsoft.com/microsoft-365-enterprise/)


