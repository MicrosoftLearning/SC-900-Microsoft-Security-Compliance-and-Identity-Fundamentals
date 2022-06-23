---
lab:
    title: 'Explore Microsoft Defender for Cloud'
    module: 'Module 3 Lesson 2: Describe the capabilities of Microsoft security solutions: Describe security management capabilities of Azure'
---

# Lab: Explore Microsoft Defender for Cloud

## Lab scenario

In this lab, you will explore Microsoft Defender for Cloud and learn how Azure Secure Score can be used to improve your organization's security posture.  NOTE: This demo walk-through assumes the presenter has admin-level permissions to the Azure subscription through an Azure pass.  An Azure subscription, such as a Cloudslice Subscription, managed by the Authorized Lab Hoster limits access and functionality so some steps below may unavailable or not show any information.

**Estimated Time**: 30 minutes

### Setup

In this task you will do some basic setup of Microsoft Defender for Cloud, to get the subscription ready and to enable and assign a default policy.

1. Open Microsoft Edge. In the address bar enter **portal.azure.com**.

1. Sign in with your admin credentials.
    1. In the Sign in window enter **admin@WWLxZZZZZZ.onmicrosoft.com** (where ZZZZZZ is your unique tenant ID provided by your lab hosting provider) then select **Next**.
    1. Enter the admin password which should be provided by your lab hosting provider. Select **Sign in**.
    1. When prompted to stay signed- in, select **Yes**.

1. On the top left corner of the screen, next to where it says Microsoft Azure, select the Show portal menu icon (the three horizontal lines also referred to as hamburger icon) then from the left navigation panel, under Favorites, select **Microsoft Defender for Cloud**.  If it is not listed under favorites, then in the search box, enter **Microsoft Defender for Cloud**, then from the results list, select **Microsoft Defender for Cloud**.

1. If this is the first time you enter Microsoft Defender for Cloud with your subscription you may land on the Getting started page and may be prompted to upgrade.  Scroll to the bottom of the page and select **skip**.  You will be taken to the Overview page.
    1. On the top of the page, you will see a light blue information box that indicates, "Getting things ready for your subscription. This may take a few minutes..."
    1. Once the subscription is ready, a new information box may appear that says, "One subscription doesn't have the default policy assigned. To review the the list of subscriptions, open the Security Policy page."  Select the right arrow at the end of sentence or select **Environment settings** from the left navigation pane.
        1. You are now in the Environment settings page. Select **Azure pass - Sponsorship**.  Note:  If your Azure environment is based on an Azure subscription managed by the Authorized Lab Hoster, instead of an Azure Pass, you will see it referenced. Expand the option by selecting the greater than sign until you can no longer expand the options and you see the subscription.
        1. From the left navigation pane, select **Security policy**.
        1. From them main page, under where it says Default initiative, select **Assign policy**.
        1. From the bottom of the page, select **Review + create**.
        1. From the bottom of the page, select **Create**.  This assigns the Azure Security Benchmark as a default policy initiative.  Refresh the screen (it may take a couple of minutes to take effect).
        1. Exit the environment settings page by selecting the **X** on the page.  
        1. From the Azure services page select **Microsoft Defender for Cloud** to return to the overview page.

### Task 1

In this task, you will do a very high-level walk-through of some of the capabilities of Microsoft Defender for Cloud

1. From the Overview page of Microsoft Defender for Cloud, notice the information available on the page.  Information on the top of the page includes the number of Azure subscriptions, the number of Assessed resources, the number of active recommendations, and any security alerts.  On the main body of the page there are cards representing Secure score, Regulatory compliance, Insights, and more.

1. From the top of the page, select **Assessed resources**.  (Note that this is equivalent to having selected Inventory from the left navigation panel of the Microsoft Defender for Cloud home page).
    1. This brings you to the **Inventory** page that shows your Azure pass subscription.  Select **Azure Pass – Sponsorship**.
    1. The Resource health page provides a list of recommendations.  From the available list, select **There should be more than one owner assigned to your subscription**.
    1. Select the drop-down arrow next to Remediation steps. Note how detailed remediation steps are provided along with the option to take action.  
    1. Select **Microsoft Defender for Cloud** from the top-left corner of the screen to return to the Microsoft Defender for Cloud overview page.

1. From the top of the page, select **Active recommendations**.  (Note that this is equivalent to having selected Recommendations from the left navigation panel of the Microsoft Defender for Cloud home page).
    1. The recommendations page shows your Secure Score dashboard.
    1. Below the Secure Score dashboard are a list of controls. Each security control represents a security risk that should be mitigated and also includes information on the maximum score associated with that control, the current score, potential score increase, and resource health status.  
    1. Select one of the controls, such as **Implement security best practices**.  Select one of the sub-items, such as **There should be more than one owner assigned to your subscription**.  In the page that opens, you will see a description, Remediation steps, and affected resources. Exit out this page, by selecting the **X** on top-right corner of the screen.
    1. Exit the recommendations page by selecting the **X** on top-right corner of the screen, to return to the overview page.

1. From the main page, select **Regulatory compliance**. The regulatory compliance page provides a list of compliance controls.  Under each control is a set of assessments that are based on the Azure Security Benchmark which provides recommendations on how you can secure your cloud solutions on Azure.
    1. Select **IM. Identity Management** then select **IM-6 Use strong authentication controls**.  The list shows customer responsibility actions that can be taken to improve compliance posture.
    1. Select the **X** on the top-right corner of the screen to close the page and return to the Microsoft Defender for Cloud Overview page.
    1. Keep the Microsoft Defender for Cloud overview page open, you will use in the next task.

### Task 2

Recall that Microsoft Defender for Cloud is offered in two modes: without enhanced security features (free) and with enhanced security features which are available through the Microsoft Defender for Cloud plans. In this task you discover how to enable/disable the various Microsoft Defender for Cloud plans.

1. From the Microsoft Defender for Cloud overview page, select the **Environment settings** from the left navigation panel.
1. Select the greater-than **>**sign next to where is say Tenant Root Group to expand it (do not select Tenant Root Group directly as that will direct you to a different page), then select **Azure Pass - Sponsorship**
1. On the Defender plans page, notice how you can select Enable all or select individual Defender plans. Leave the settings as they are with all plans set to off.
1. Close all the open browser tabs.

### Review

In this lab, you explored Microsoft Defender for Cloud and learned how Azure Secure Score can be used to improve your organization's security posture.
