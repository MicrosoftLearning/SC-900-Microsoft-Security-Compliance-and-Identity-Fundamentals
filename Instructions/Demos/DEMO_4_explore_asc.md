---
Demo:
    title: 'Explore Azure Security Center'
    module: 'Module 3 Lesson 2: Describe the capabilities of Microsoft security solutions: Describe security management capabilities of Azure'
---

# Demo: Explore Azure Security Center

## Demo scenario

In this demo, you will walk through the Azure Security Center and show how Azure Secure Score can be used to improve an organization's security posture.

## Instructions

1. Open Microsoft Edge. In the address bar enter **portal.azure.com**.

1. Sign in with your admin credentials.
    1. In the Sign in window enter **admin@WWLxZZZZZZ.onmicrosoft.com** (where ZZZZZZ is your unique tenant ID provided by your lab hosting provider) then select **Next**.
    1. Enter the admin password which should be provided by your lab hosting provider. Select **Sign in**.
    1. When prompted to stay signed- in, select **Yes**.

1. On the top left corner of the screen, next to where it says Microsoft Azure, select the Show portal menu icon (the three horizontal lines also referred to as hamburger icon) then select **All Services**.  

1. In the filter services box, enter **Security Center**, then from the results list, select **Security Center**.

1. Notice the information available on the Security center overview page.  

1. You may see a blue information box on the top of the page indicating that you may be viewing limited information.  Select **click here**.
    1. To ensure that you get tenant wide visibility, assign yourself the necessary role.  Select **Security Admin** then select **Get access** at the bottom of the page.
    1. You will likely see the message; Root management group dos not exist.  Per the description, the system will create the group for you.  It can take up to 15 minutes to complete (but usually happens faster), after which you can repeat the process to get access.  Once the access is granted select **Security Center** on the top-left corner of the page, above where it says Get permissions and then refresh the Security center overview page.

1. Information on the top of the page includes the number of Azure subscriptions, the number of Assessed resources, the number of active recommendations, and any security alerts.  On the main body of the page there are cards representing Secure score, Regulatory compliance, Insights, Azure Defender, and more.  

1. From the top of the page, select **Assessed resources**.  This brings you to the inventory page that shows your Azure pass subscription.  Select **Azure Pass – Sponsorship**.

1. The Resource health page provides a list of recommendations.  From the available list, select **There should be more than one owner assigned to your subscription**.

1. Select the drop-down arrow next to Remediation steps. Note how detailed remediation steps are provided along with the option to take action.  

1. Select **Security Center** from the top-left corner of the screen to return to the Security Center overview page.

1. From the top of the page, select **Active recommendations**.  

1. The recommendations page shows specific actions that can be taken on their potential secure score increase.  Exit the recommendations page by selecting the **X** on top-right corner of the screen.

1. From the main page, select **Regulatory compliance**.

1. The regulatory compliance page provides a list of compliance controls.  Under each control is a set of assessments that are based on the Azure Security Benchmark which provides recommendations on how you can secure your cloud solutions on Azure.

1. Select **IM. Identity Management** then select **IM.4 Use strong authentication controls for all Azure Active Directory based access**.  The list shows customer responsibility actions that can be taken to improve compliance posture.

1. Select the **X** on the top-right corner of the screen to close the page and return to the Security Center Overview page.

## Review

In this demo, you walked through the Azure Security Center and showed how Azure Secure Score can be used to improve an organization's security posture.
