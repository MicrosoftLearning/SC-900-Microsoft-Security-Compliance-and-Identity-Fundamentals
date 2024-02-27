---
lab:
    title: 'Explore Microsoft Defender for Cloud'
---

<!---
---
Lab:
    Title: 'Explore Microsoft Defender for Cloud'
    Learning Path/Module/Unit: 'Learning Path: Describe the capabilities of Microsoft security solutions; Module 2: Describe the security management capabilities of Azure; Unit 3: Describe cloud security posture management'
---
--->

# Lab: Explore Microsoft Defender for Cloud

This lab maps to the following Learn content:

- Learning Path: Describe the capabilities of Microsoft security solutions
- Module: Describe the security management capabilities of Azure
- Unit: Describe cloud security posture management

## Lab scenario

In this lab, you'll explore Microsoft Defender for Cloud.  NOTE: the Azure subscription provided by the Authorized Lab Hoster (ALH) limits access and may experience longer than normal delays.

**Estimated Time**: 30 minutes

### Task 1

In this task, you'll do a high-level walk-through of some of the capabilities of Microsoft Defender for Cloud

1. You should be the home page for Azure services.  If you previously closed the browser, ppen Microsoft Edge. In the address bar, enter **portal.azure.com**, and sign in with your admin credentials.

1. In the blue search bar enter **Microsoft Defender for Cloud**, then from the results list, select **Microsoft Defender for Cloud**.

1. If this is the first time you enter Microsoft Defender for Cloud with your subscription you may land on the Getting started page, and may be prompted to upgrade.  Scroll to the bottom of the page and select **Remind me later** (or **Skip**).  You'll be taken to the Overview page.

1. From the Overview page of Microsoft Defender for Cloud, notice the information available on the page (if you see 0 assessed resources and active recommendations, refresh the browser page, it may take a few minutes).  Information on the top of the page includes the number of Azure subscriptions, the number of Assessed resources, the number of active recommendations, and any security alerts.  On the main body of the page, there are cards representing Security posture, Regulatory compliance, Insights, and more.  Note: The Microsoft Defender for Cloud default policy initiative, which would normally have to be assigned by the admin, has already been assigned as part of the Azure subscription setup. The secure score, however, will show as 0% because there can be up to a 24 hour delay for Azure to reflect an initial score.

1. From the top of the page, select **Assessed resources**. 
    1. This brings you to the **Inventory** page that lists the current resources. Select the virtual machine resource, **sc900-winwm**. This resource is associated with the virtual machine you used in the previous lab.
    1. The Resource health page for the VM provides a list of recommendations.  From the available list, select any item from the list that shows an **unhealthy** status.
    1. Note the detailed description.  Select the drop-down arrow next to Remediation steps. Note how remediation instructions (or links to instructions) are provided along with the option to take action.  Exit the window without taking any action.
    1. Return to the Microsoft Defender for Cloud overview page, by selecting **Microsoft Defender for Cloud | Overview** from the top of the page, above where it says Resource health.

1. From the left navigation panel, select **Recommendations**.  
    1. Verify,the **All recommendations** tab is selected (underlined).  Note the dashboard view that shows Active recommendations by severity, Resource health, and more.
    1. From the list, select an item.  In the page that opens, you'll see a description and additional information that may include remediation steps, affected resources, and more. Exit out this page, by selecting the **X** on top-right corner of the screen.

1. From the main left navigation panel, select **Regulatory compliance**.  **NOTE**: If you see that there is no subscription to calculate compliance for, its because there may be up to a 24 hour delay for information to appear. Move to Task 2.  If you do see information then proceed with the steps that follow.
    1. The regulatory compliance page provides a list of compliance controls based on the Microsoft cloud security benchmark (verify that Microsoft cloud security benchmark tab is selected/underlined). Under each control domain is a subset of controls and for each control there are one or more assessments. Each assessment provides information including description, remediation, and affected resources.
    1. Let's explore one of the control domains areas. Select (expand) **NS. Network Security**. A list of controls related to network security is displayed.
    1. Select **NS-10. Ensure Domain Name System (DNS) security**. Note the list of automated assessments (which include automated assessments for AWS) and how each assessment line item provides information including the resource type, failed resources and compliance stations. Select the assessments listed.  Here you see information including a description, Remediation steps, and Affected resources.
    1. Select the **X** on the top-right corner of the screen to close the page.
    1. Select **Overview** from the left navigation panel to  return to the Microsoft Defender for Cloud Overview page.
    1. Keep the Microsoft Defender for Cloud overview page open, you'll use in the next task.

### Task 2

Recall that Microsoft Defender for Cloud is offered in two modes: without enhanced security features (free) and with enhanced security features that are available through the Microsoft Defender for Cloud plans. In this task, you discover how to enable/disable the various Microsoft Defender for Cloud plans.

1. From the Microsoft Defender for Cloud overview page, select the **Environment settings** from the left navigation panel.
1. Select  the **Expand all** box then select the **MOC Subscription--lodXXXXXXXX** subscription listed next to the yellow key icon.
1. On the Defender plans page, notice how you can select Enable all or select individual Defender plans. 
    1. Verify that CSPM status is set to **On**, if not, set it now.  
    1. Enable the plan for Servers.  Select **On** for the Servers line item, then select **Save** from the top of the page.
1. From the top left corner of the window, just below the blue bar where it says Microsoft Azure, select **Home** to return to the Azure services home page.
1. Keep the Azure tab open on your browser.

### Review

In this lab, you explored Microsoft Defender for Cloud.
