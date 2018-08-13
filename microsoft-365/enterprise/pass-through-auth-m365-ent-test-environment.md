---
title: "Pass-through authentication for your Microsoft 365 test environment"
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 08/13/2018
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection: 
- Ent_O365
- Strat_O365_Enterprise
ms.custom: 
- TLG
- Ent_TLGs
ms.assetid: 
description: "Summary: Configure pass-through authentication for your Microsoft 365 test environment."
---

# Pass-through authentication for your Microsoft 365 test environment

Organizations that want to directly use their on-premises Windows Server Active Directory (AD) infrastructure for authentication to Microsoft cloud-based services and applications can use pass-through authentication. This article describes how you can configure your Microsoft 365 test environment for pass-through authentication, resulting in the following configuration:
  
![The simulated enterprise with pass-through authentication test environment](media/pass-through-auth-m365-ent-test-environment/Phase2.png)
  
There are two phases to setting up this test environment:

1.	Create the Microsoft 365 simulated enterprise test environment with password hash synchronization.
2.	Configure Azure AD Connect on APP1 for pass-through authentication.
    
> [!TIP]
> Click [here](http://aka.ms/catlgstack) for a visual map to all the articles in the One Microsoft Cloud Test Lab Guide stack.
  
## Phase 1: Create the password hash synchronization for your Microsoft 365 test environment

Follow the instructions in [password hash synchronization for Microsoft 365](password-hash-sync-m365-ent-test-environment.md). Here is your resulting configuration.
  
![The simulated enterprise with password hash synchronization test environment](media/pass-through-auth-m365-ent-test-environment/Phase1.png)
  
This configuration consists of: 
  
- Office 365 E5 and EMS E5 trial or permanent subscriptions.
- A simplified organization intranet connected to the Internet, consisting of the DC1, APP1, and CLIENT1 virtual machines on a subnet of an Azure virtual network. Azure AD Connect runs on APP1 to synchronize the TESTLAB Windows Server AD domain to the Azure AD tenant of your Office 365 and EMS E5 subscriptions periodically.

## Phase 2: Configure Azure AD Connect on APP1 for pass-through authentication

In this phase, you configure Azure AD Connect on APP1 to use pass-through authentication, and then verify that it works.

### Configure Azure AD Connect on APP1

1.	From the [Azure portal](https://portal.azure.com), sign in with your global administrator account, and then connect to APP1 with the TESTLAB\User1 account.

2.	From the desktop of APP1, run Azure AD Connect.

3.	On the **Welcome page**, click **Configure**.

4.	On the Additional tasks page, click **Change user sign-in**, and then click **Next**.

5.	On the **Connect to Azure AD** page, type your global administrator account credentials, and then click **Next**.

6.	On the **User sign-in** page, click **Pass-through authentication**, and then click **Next**.

7.	On the **Ready to configure** page, click **Configure**.

8.	On the **Configuration complete** page, click **Exit**.

9.	From the Azure portal, in the left pane, click **Azure Active Directory > Azure AD Connect**. Verify that the **Pass-through authentication** feature appears as **Enabled**.

10.	Click **Pass-through authentication**. The **Pass-through authentication** pane lists the servers where your Authentication Agents are installed. You should see APP1 in the list. Close the **Pass-through authentication** pane.

Next, test the ability to sign in to your Office 365 subscription with the user1@testlab.\<your public domain> user name of the User1 account.

1.	From APP1, sign out of Office 365, and then sign in again, this time specifying a different account.

2.	When prompted for a user name and password, specify **user1@testlab.**\<your public domain> and the User1 password. You should successfully sign in as User1.

Notice that although User1 has domain administrator permissions for the TESTLAB Windows Server AD domain, it is not an Office 365 global administrator. Therefore, you will not see the **Admin** icon as an option.

Here is your resulting configuration:

![The simulated enterprise with pass-through authentication test environment](media/pass-through-auth-m365-ent-test-environment/Phase2.png)
 
This configuration consists of:

- Office 365 E5 and EMS E5 trial or permanent subscriptions with the DNS domain TESTLAB.<your domain name> registered.
- A simplified organization intranet connected to the Internet, consisting of the DC1, APP1, and CLIENT1 virtual machines on a subnet of an Azure virtual network. An Authentication Agent runs on APP1 to handle pass-through authentication requests from the Azure AD tenant of your Office 365 and EMS E5 subscriptions.

## Next step

Explore additional [identity](m365-enterprise-test-lab-guides.md#identity) features and capabilities in your test environment.

## See also

[Microsoft 365 Enterprise Test Lab Guides](m365-enterprise-test-lab-guides.md)

[Deploy Microsoft 365 Enterprise](deploy-microsoft-365-enterprise.md)

[Microsoft 365 Enterprise documentation](https://docs.microsoft.com/microsoft-365-enterprise/)


