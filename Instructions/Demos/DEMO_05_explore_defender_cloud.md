<!---
---
Demo:
    Title: 'Microsoft Defender for Cloud'
    Learning Path/Module/Unit: 'Learning Path: Describe the capabilities of Microsoft security solutions; Module 2: Describe the security management capabilities of Azure; Unit 3: Describe Microsoft Defender for Cloud'
---
--->

# Demo: Microsoft Defender for Cloud

This demo maps to the following Learn content:

- Learning Path: Describe the capabilities of Microsoft security solutions
- Module: Describe the security management capabilities of Azure
- Unit: Describe Microsoft Defender for Cloud

## Demo scenario

In this demo, you will walk through Microsoft Defender for Cloud and show how it can be used to improve an organization's security posture.  NOTE: the Azure subscription managed by the Authorized Lab Hoster (AH) may limits access and functionality so some steps below may be unavailable or not show any information.

### Demo Task 1

In this demo task you will do a very high-level walk-through of some of the capabilities of Microsoft Defender for Cloud.

1. Open Microsoft Edge. In the address bar enter **portal.azure.com**.
1. Sign in with your admin credentials.
    1. In the Sign in window enter the username provided by your lab hosting provider then select **Next**.
    1. Enter the admin password which should be provided by your lab hosting provider. Select **Sign in**.
    1. When prompted to stay signed- in, select **Yes**.

1. In the blue search bar enter **Microsoft Defender for Cloud**, then from the results list, select **Microsoft Defender for Cloud**.
1. If this is the first time you enter Microsoft Defender for Cloud with your subscription you may land on the Getting started page and may be prompted to upgrade.  Scroll to the bottom of the page and select **Skip**.  You will be taken to the Overview page.
1. From the Overview page of Microsoft Defender for Cloud, notice the information available on the page.  Information on the top of the page includes the number of Azure subscriptions, the number of Assessed resources, the number of active recommendations, and any security alerts.  On the main body of the page there are cards representing Security posture, Regulatory compliance, Insights, and more.  Note: The Microsoft Defender for Cloud default policy initiative, which would normally have to be assigned by the admin, has already been assigned  as part of the Azure subscription setup. The secure score, however, will show as 0% because there can be up to a 24 hour delay for Azure to reflect an initial score.

1. From the top of the page, select **Assessed resources**.  (Note that this is equivalent to having selected Inventory from the left navigation panel of the Microsoft Defender for Cloud home page).
    1. This brings you to the **Inventory** page that lists the current resources. Select the virtual machine resource, **sc900-winwm**. This resource is associated with the virtual machine you used in the previous lab.
    1. The Resource health page for the VM provides a list of recommendations.  From the available list, select any item from the list that shows an **unhealthy** status.
    1. Note the detailed description.  Select the drop-down arrow next to Remediation steps. Note how remediation instructions (or links to instructions) are provided along with the option to take action.  Exit the window without taking any action.
    1. Return to the Microsoft Defender for Cloud overview page, by selecting **Microsoft Defender for Cloud | Overview** from the top of the page, above where it says Resource health.

1. From the left navigation panel, select **Recommendations**.  (Note that this is equivalent to having selected Active recommendations from the top of the Microsoft Defender for Cloud overview page).
    1. Verify,the **All recommendations** tab is selected (underlined).  Note the dashboard view that shows Active recommendations by severity, Resource health, and more.
    1. Note that some items show up as unhealthy resources, as depicted by the red bar on the right of the line item.  From the list, select any unhealthy resource.  In the page that opens, you will see a description, Remediation steps, and affected resources. Exit out this page, by selecting the **X** on top-right corner of the screen.
    1. Exit the recommendations page by selecting the **X** on top-right corner of the screen, to return to the overview page.

1. From the main left navigation panel, select **Regulatory compliance**. The regulatory compliance page provides a list of compliance controls based on the Microsoft cloud security benchmark (verify that Microsoft cloud security benchmark tab is selected/underlined). Under each control domain are a subset of controls and for each control there are one or more assessments. Each assessment provides information including description, remediation, and affected resources.
    1. Let' explore one of the control domains areas. Select (expand) **NS. Network Security**. A list of controls related to network security is displayed.
    1. Select **NS-10. Microsoft Defender for DNS should be enabled**. Note the list of automated assessments (which include automated assessments for AWS) and how each assessment line item provides information including the resource type, failed resources and compliance stations. Select the assessments listed.  Here you see information including a description, Remediation steps, and Affected resources.
    1. Select the **X** on the top-right corner of the screen to close the page.
    1. Select **Overview** from the left navigation panel to  return to the Microsoft Defender for Cloud Overview page.
    1. Keep the Microsoft Defender for Cloud overview page open, you will use in the next task.

### Demo Task 2

Recall that Microsoft Defender for Cloud is offered in two modes: without enhanced security features (free) and with enhanced security features which are available through the Microsoft Defender for Cloud plans. In this task you discover how to enable/disable the various Microsoft Defender for Cloud plans.

1. From the Microsoft Defender for Cloud overview page, select the **Environment settings** from the left navigation panel.
1. Select  the **Expand all** box then select the **MOC Subscription--lodXXXXXXXX** subscription listed next to the yellow key icon.
1. On the Defender plans page, notice how you can select Enable all or select individual Defender plans. 
    1. Verify that CSPM status is set to **On**, if not, set it now.  
    1. Enable the plan for Servers.  Select **On** for the Servers line item, then select **Save** from the top of the page.
1. Close all the open browser tabs.

## Review

In this demo, you walked through the Microsoft Defender for Cloud and showed how Azure Secure Score can be used to improve an organization's security posture.
