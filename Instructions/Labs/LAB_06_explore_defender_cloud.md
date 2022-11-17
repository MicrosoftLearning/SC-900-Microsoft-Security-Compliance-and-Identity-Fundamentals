<!---
---
Lab:
    Title: 'Explore Microsoft Defender for Cloud'
    Learning Path/Module/Unit: 'Learning Path: Describe the capabilities of Microsoft security solutions; Module 2: Describe the security management capabilities of Azure; Unit 3: Describe Microsoft Defender for Cloud'
---
--->

# Lab: Explore Microsoft Defender for Cloud

This lab maps to the following Learn content:

- Learning Path: Describe the capabilities of Microsoft security solutions
- Module: Describe the security management capabilities of Azure
- Unit: Describe Microsoft Defender for Cloud

## Lab scenario

In this lab, you will explore Microsoft Defender for Cloud.  NOTE: This demo walk-through assumes the presenter has admin-level permissions to the Azure subscription through an Azure pass.  An Azure subscription, such as a Cloudslice Subscription, managed by the Authorized Lab Hoster limits access and functionality so some steps below may unavailable or not show any information.

**Estimated Time**: 30 minutes

### Setup

In this task you will do some basic setup of Microsoft Defender for Cloud, to get the subscription ready and to enable and assign a default policy.

1. Open Microsoft Edge. In the address bar enter **portal.azure.com**.

1. Sign in with your admin credentials.
1. Sign in with your admin credentials.
    1. In the Sign in window enter the username provided by your lab hosting provider then select **Next**.

    1. Enter the admin password which should be provided by your lab hosting provider. Select **Sign in**.
    1. When prompted to stay signed- in, select **Yes**.

1. On the search bar next to where it says Microsoft Azure, on the top of the page, enter **Microsoft Defender for Cloud**, then from the results list, select **Microsoft Defender for Cloud**.

1. If this is the first time you enter Microsoft Defender for Cloud with your subscription you may land on the Getting started page and may be prompted to upgrade.  Scroll to the bottom of the page and select **skip**.  You will be taken to the Overview page.
    1. On the top of the page, you will see a light blue information box that indicates, "Getting things ready for your subscription. This may take a few minutes..."
    1. Once the subscription is ready, a new information box may appear that says, "One subscription doesn't have the default policy assigned. To review the the list of subscriptions, open the Security Policy page."  Select the right arrow at the end of sentence or select **Environment settings** from the left navigation pane.
        1. You are now in the Environment settings page. Select **Expand all** then select the subscription listed next to the yellow key icon.
        1. From the left navigation pane, select **Security policy**.
        1. From them main page, under where it says Default initiative, select **Assign policy**.
        1. From the bottom of the page, select **Review + create**.
        1. From the bottom of the page, select **Create**.  This assigns the Azure Security Benchmark as a default policy initiative.  Refresh the screen (it may up to 30 minutes for the policy to take effect).
        1. Exit the environment settings page by selecting the **X** on the page.  
        1. From the Azure services page select **Microsoft Defender for Cloud** to return to the overview page.

### Task 1

In this task, you will do a very high-level walk-through of some of the capabilities of Microsoft Defender for Cloud

1. From the Overview page of Microsoft Defender for Cloud, notice the information available on the page.  Information on the top of the page includes the number of Azure subscriptions, the number of Assessed resources, the number of active recommendations, and any security alerts.  On the main body of the page there are cards representing Secure score, Regulatory compliance, Insights, and more.

1. From the top of the page, select **Assessed resources**.  (Note that this is equivalent to having selected Inventory from the left navigation panel of the Microsoft Defender for Cloud home page).
    1. This brings you to the **Inventory** page that lists the current resources. Select the virtual machine resource, **sc900-winwm**. This resource is associated with the virtual machine you created in the previous lab.  If you skipped that lab go back on execute that lab, as this lab and the Microsoft Sentinel lab will depend on it.
    1. The Resource health page for the VM provides a list of recommendations.  From the available list, select any item from the list that shows an **unhealthy** status.
    1. Select the drop-down arrow next to Remediation steps. Note how remediation steps are provided along with the option to take action.  Exit the window without taking any action.
    1. Return to the Microsoft Defender for Cloud overview page, by selecting **Microsoft Defender for Cloud | Overview** from the top of the page, above where it says Resource health.

1. From the left navigation panel, select **Recommendations**.  (Note that this is equivalent to having selected Active recommendations from the top of the Microsoft Defender for Cloud overview page).
    1. Verify,the **All recommendations** tab is selected (underlined).
    1. Select one of the line items that shows up as an unhealthy resources, as depicted by the red bar on the right of the line item.  In the page that opens, you will see a description, Remediation steps, and affected resources. Exit out this page, by selecting the **X** on top-right corner of the screen.
    1. Exit the recommendations page by selecting the **X** on top-right corner of the screen, to return to the overview page.

1. From the main left navigation panel, select **Regulatory compliance**. The regulatory compliance page provides a list of compliance controls based on the Microsoft cloud security benchmark (verify that Microsoft cloud security benchmark tab is selected/underlined). Under each control domain are a subset of controls and for each control there are one or more assessments. Each assessment provides information including description, remediation, and affected resources.
    1. Let' explore one of the control domains areas. Select (expand) **NS. Network Security**. A list of controls related to network security is displayed.
    1. Select one of the controls listed for Network Security. Selecting **NS-1. Establish network segmentation boundaries** provides a list of automated assessments.  Select any one of the assessments listed.  Here you see information including a description, Remediation steps, and Affected resources.
    1. Select the **X** on the top-right corner of the screen to close the page.
    1. Select **Overview** from the left navigation panel to  return to the Microsoft Defender for Cloud Overview page.
    1. Keep the Microsoft Defender for Cloud overview page open, you will use in the next task.

### Task 2

Recall that Microsoft Defender for Cloud is offered in two modes: without enhanced security features (free) and with enhanced security features which are available through the Microsoft Defender for Cloud plans. In this task you discover how to enable/disable the various Microsoft Defender for Cloud plans.

1. From the Microsoft Defender for Cloud overview page, select the **Environment settings** from the left navigation panel.
1. Select  the **Expand all** box then select the subscription listed next to the yellow key icon.
1. On the Defender plans page, notice how you can select Enable all or select individual Defender plans. Leave the settings as they are.
1. Close all the open browser tabs.

### Review

In this lab, you explored Microsoft Defender for Cloud.
