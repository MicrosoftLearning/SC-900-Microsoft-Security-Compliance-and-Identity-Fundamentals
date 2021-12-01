---
Demo:
    title: Microsoft Defender for Cloud'
    module: 'Module 3 Lesson 2: Describe the capabilities of Microsoft security solutions: Describe security management capabilities of Azure'
---

# Demo: Microsoft Defender for Cloud

### Demo scenario

In this demo, you will walk through Microsoft Defender for Cloud and show how Azure Secure Score can be used to improve an organization's security posture.

1. Open the browser tab, **Home-Microsoft Azure**.  If you previously closed the tab, open a browser page and in the address bar, enter portal.azure.com and sign back in.

1. In the search box, in the blue bar on the top of the page next to where it says Microsoft Azure, enter **Microsoft Defender for Cloud** then select **Microsoft Defender for Cloud** from the search results.

1. If this is the first time you enter Microsoft Defender for Cloud with your subscription you may land on the Getting started page and may be prompted to upgrade.  Scroll to the bottom of the page and select **skip**.

1. Notice the information available on the Microsoft Defender for Cloud overview page.  Note: You may see a blue information box on the top of the page indicating that you may be viewing limited information.  Do not select it (it can take up to 15 minutes to process and makes no difference for this demo).

1. Information on the top of the page includes the number of Azure subscriptions, the number of Assessed resources, the number of active recommendations, and any security alerts.  On the main body of the page there are cards representing Secure score, Regulatory compliance, Insights, and more.  

1. From the top of the page, select **Assessed resources**.  (Note that this is equivalent to having selected Inventory from the left navigation panel of the Microsoft Defender for Cloud home page).
    1. This brings you to the **Inventory** page that shows your Azure pass subscription.  Select **Azure Pass – Sponsorship**.
    1. The Resource health page provides a list of recommendations.  From the available list, select **There should be more than one owner assigned to your subscription**.
    1. Select the drop-down arrow next to Remediation steps. Note how detailed remediation steps are provided along with the option to take action.  
    1. Select **Microsoft Defender for Cloud** from the top-left corner of the screen to return to the Microsoft Defender for Cloud overview page.

1. From the top of the page, select **Active recommendations**.  (Note that this is equivalent to having selected Recommendations from the left navigation panel of the Microsoft Defender for Cloud home page).
    1. The recommendations page shows your Secure Score dashboard.
    1. Below the Secure Score dashboard are a list of controls. Each security control represents a security risk that should be mitigated and also includes information on the maximum score associated with that control, the current score, potential score increase, and resource health status.  
    1. Select one of the controls, such as **Enable MFA**.  Select one of the sub-items, such as **MFA should be enabled on accounts with owner permissions on your subscription**.  In the page that opens, you will see a description, Remediation steps, and affected resources. Exit out this page, by selecting the **X** on top-right corner of the screen.
    1. Exit the recommendations page by selecting the **X** on top-right corner of the screen, to return to the overview page.

1. You are back on the Microsoft Defender for Cloud Overview page.  From the main page, select **Secure Score** (this is equivalent to selecting Secure score from the left navigation panel).
    1. This brings you to the Secure Score Dashboard.  In addition it lists any available management groups and subscriptions.  Select your Azure subscription – Azure Pass – Sponsorship.
    1. This brings to the Recommendations page, which was shown earlier.
    1. Exit out the recommendations page, by selecting the **X** on top-right corner of the screen.
    1. Exit out of the Secure Score page by selecting the **X** on top-right corner of the screen, to return to the overview page.

1. You are back on the Microsoft Defender for Cloud Overview page.  From the main page, select **Regulatory compliance**. (Note that this is equivalent to having selected Recommendations from the left navigation panel of the Microsoft Defender for Cloud home page).
    1. The regulatory compliance page provides a list of compliance controls.  Under each control is a set of assessments that are based on the Azure Security Benchmark which provides recommendations on how you can secure your cloud solutions on Azure.
    1. Select **IM. Identity Management** then select **IM-6 Use strong authentication controls**.  The list shows customer responsibility actions that can be taken to improve compliance posture.
    1. Select the **X** on the top-right corner of the screen to close the page and return to the regulatory compliance page.
    1. Select the **X** on the top-right corner of the screen to return to the overview page.

1. Return to the home page of the Azure portal by selecting **Home** on the top-left corner of the page.  Keep this browser tab available, as you will come back to it in a later demo.

## Review

In this demo, you walked through the Microsoft Defender for Cloud and showed how Azure Secure Score can be used to improve an organization's security posture.
