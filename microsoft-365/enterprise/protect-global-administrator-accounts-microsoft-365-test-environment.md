---
title: "Protect global administrator accounts in your Microsoft 365 Enterprise test environment"
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 08/21/2018
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection: Ent_O365
ms.custom: 
- TLG
- Ent_TLGs
description: "Use these steps to protect global administrator accounts in your Microsoft 365 Enterprise test environment."
---

# Protect global administrator accounts in your Microsoft 365 Enterprise test environment

You can prevent digital attacks on your organization by ensuring that your administrator accounts are as secure as possible. This article describes how to use Office 365 Cloud App Security and Azure AD conditional access policies to protect global administrator accounts.

There are two phases to protecting global administrator accounts in your Microsoft 365 Enterprise test environment:

1.	Create the Microsoft 365 Enterprise test environment.
2.	Protect your dedicated global administrator account.

![Test Lab Guides for the Microsoft cloud](media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png) 
    
> [!TIP]
> Click [here](https://aka.ms/m365etlgstack) for a visual map to all the articles in the Microsoft 365 Enterprise Test Lab Guide stack.
  

## Phase 1: Build out your Microsoft 365 Enterprise test environment

If you just want to test global administrator account protection in a lightweight way with the minimum requirements, follow the instructions in [Lightweight base configuration](lightweight-base-configuration-microsoft-365-enterprise.md).
  
If you want to test global administrator account protection in a simulated enterprise, follow the instructions in [Pass-through authentication](pass-through-auth-m365-ent-test-environment.md).
  
> [!NOTE]
> Testing global administrator account protection does not require the simulated enterprise test environment, which includes a simulated intranet connected to the Internet and directory synchronization for a Windows Server AD forest. It is provided here as an option so that you can test global administrator account protection and experiment with it in an environment that represents a typical organization. 
  
## Phase 2: Configure Cloud App Security and conditional access policies

First, create an Office 365 Cloud App Security policy to monitor global administrator account activity and send alerts to the email address of your global administrator account. 

1. Sign in to the Office 365 portal at [http://portal.office.com](http://portal.office.com) using your global administrator account.
2. Click the **Admin** tile. On the **Office Admin center** tab, click **Admin centers > Security & Compliance**.
3. In the left navigation pane, click **Alerts > Manage advanced alerts**.
4. On the **Manage advanced alerts** page, click **Turn on Office 365 Cloud App Security**, and then click **Go to Office 365 Cloud App Security**.
5. On the new **Dashboard** tab, click **Control > Policies**.
6. On the **Policy** page, click **Create policy**, and then click **Activity policy**.
7. In **Policy name**, type **Administrative activity**.
8. In **Policy severity**, click **High**.
9. In **Category**, click **Privileged accounts**.
10. In **Create filters for the policy**, in **Activities matching all of the following**, click **Administrative activity**.
11. In **Alerts**, click **Send alert as email**. In **To**, type the email address of your global administrator account.
12. At the bottom of the page, click **Create**.
13. Close the **Dashboard** tab.
    
Next, create a new user account as a dedicated global administrator.

1. On the **Office Admin center** tab, under **Active users**, click **Add a user**.
2. On the **New user** page, type **DedicatedAdmin** in **First name**, **Display name**, and **Username**.
3. Click **Password**, click **Let me create the password**, and then type a strong password. Record the password for this new account in a secure location.
4. Clear **Make this user change their password when they first sign in**.
5. Click **Roles**, and then click **Global administrator**.
6. Click **Product licenses**, and then turn the **Enterprise Mobility + Security E5** and **Office 365 Enterprise E5 licenses** on.
7. Click **Add**.
8. On the **User was added page**, clear **Send password in email**, and then click **Close**.

Next, create a new group named GlobalAdmins and add the DedicatedAdmin account to it.

1. On the **Office Admin center** tab, click the groups icon in the left navigation, and then click **Groups**.
2. Click **Add a group**.
3. On the **New Group** page, type **GlobalAdmins**.
4. Click **Select owner** click your global administrator account, and then click **Add > Close**.
5. In the list of groups, click the **GlobalAdmins** group.
6. On the **GlobalAdmins** page, click **Edit for Member**, and then click **Add members**.
7. In the list, click the **DedicatedAdmin** account, and then click **Save > Close > Close > Admin center**.

Next, create conditional access policies to require multifactor authentication for global administrator accounts and to deny authentication if the sign-in risk is medium or high.

This first policy requires that all global administrator accounts use MFA.

1. In a new tab of your browser, go to [https://portal.azure.com](https://portal.azure.com).
2. Click **Azure Active Directory > Conditional access**.
3. On the **Conditional access – Policies** blade, click **Baseline policy: Require MFA for admins (preview)**.
4. On the **Baseline policies…** blade, click **Use policy immediately > Save**.

This second policy blocks access to global administrator account authentication when the sign-in risk is medium or high.

1. On the **Conditional access – Policies** blade, click **New policy**.
2. On the **New** blade, type **Global administrators** in **Name**.
3. In the **Assignments** section, click **Users and groups**.
4. On the **Include** tab of the **Users and groups** blade, click **Select users and groups > Users and groups > Select**.
5. On the **Select** blade, click the **GlobalAdmins > Select > Done**.
6. In the **Assignments** section, click **Conditions**.
7. On the **Conditions** blade, click **Sign-in risk**, click **Yes** for **Configure**, click **High** and **Medium**, and then click **Select** and **Done**.
8. In the **Access controls** section of the **New** blade, click **Grant**.
9. On the **Grant** blade, click **Block access**, and then click **Select**.
10. On the **New** blade, click **On** for **Enable policy**, and then click **Create**.
11. Close the **Azure portal** and **Office Admin center** tabs.

To test the first policy, sign out and sign in with the DedicatedAdmin account. You should be prompted to configure MFA on the user account. This demonstrates that the first policy is being applied.

See the [Protect global administrator accounts](identity-designate-protect-admin-accounts.md) step in the Identity phase for information and links to protect your global administrator accounts in production.

## Next step

Explore additional [identity](m365-enterprise-test-lab-guides.md#identity) features and capabilities in your test environment.

## See also

[Phase 2: Identity](identity-infrastructure.md)

[Microsoft 365 Enterprise Test Lab Guides](m365-enterprise-test-lab-guides.md)

[Microsoft 365 Enterprise deployment](deploy-microsoft-365-enterprise.md)

[Microsoft 365 Enterprise documentation](https://docs.microsoft.com/microsoft-365-enterprise/)
