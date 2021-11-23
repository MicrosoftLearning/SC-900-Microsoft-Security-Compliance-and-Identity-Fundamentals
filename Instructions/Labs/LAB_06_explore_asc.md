---
lab:
    title: 'Explore Azure Security Center'
    module: 'Module 3 Lesson 2: Describe the capabilities of Microsoft security solutions: Describe security management capabilities of Azure'
---


# Lab: Explore Azure Security Center 

## Lab scenario
In this lab, you will explore Microsoft Defender for Cloud and learn how Azure Secure Score can be used to improve your organization's security posture.

  

**Estimated Time**: 10-15 minutes

#### Task 1: In this task you will take a brief tour of Microsoft Defender for Cloud.
1.	Open Microsoft Edge. In the address bar enter **portal.azure.com**.

1. Sign in with your admin credentials.
    1. In the Sign in window enter **admin@WWLxZZZZZZ.onmicrosoft.com** (where ZZZZZZ is your unique tenant ID provided by your lab hosting provider) then select **Next**.
    
    1. Enter the admin password which should be provided by your lab hosting provider. Select **Sign in**.
    1. When prompted to stay signed- in, select **Yes**.

1. On the top left corner of the screen, next to where it says Microsoft Azure, select the Show portal menu icon (the three horizontal lines also referred to as hamburger icon) then from the left navigation panel, under Favorites, select **Microsoft Defender for Cloud**.  If it is not listed under favorites, then in the filter services box, enter **Microsoft Defender for Cloud**, then from the results list, select **Microsoft Defender for Cloud**.
1. Notice the information available on the Security center overview page.  
1. You may see a blue information box on the top of the page indicating that you may be viewing limited information.  Select **click here**.
    1. To ensure that you get tenant wide visibility, assign yourself the necessary role.  Select **Security Admin** then select **Get access** at the bottom of the page.
   
    1. You will likely see the message; Root management group dos not exist.  Per the description, the system will create the group for you.  It can take up to 15 minutes to complete (but usually happens faster).  Once the access is granted select **Microsoft Defender for Cloud** on the top-left corner of the page, above where it says Get permissions and then refresh the Microsoft Defender for Cloud overview page.
1. Information on the top of the page includes the number of Azure subscriptions, the number of Assessed resources, the number of active recommendations, and any security alerts.  On the main body of the page there are cards representing Secure score, Regulatory compliance, Insights, Azure Defender, and more.  
1. From the top of the page, select **Assessed resources**.  This brings you to the inventory page that shows your Azure pass subscription.  Select **Azure Pass – Sponsorship**.
1. The Resource health page provides a list of recommendations.  From the available list, select **There should be more than one owner assigned to your subscription**.
1. Select the drop-down arrow next to Remediation steps. Note how detailed remediation steps are provided along with the option to take action.  
1. Select **Microsoft Defender for Cloud** from the top-left corner of the screen to return to the Microsoft Defender for Cloud overview page.
1. From the top of the page, select **Active recommendations**.  
1. The recommendations page shows specific actions that can be taken on their potential secure score increase.  Exit the recommendations page by selecting the **X** on top-right corner of the screen.
1. From the main page, select **Regulatory compliance**.
1. The regulatory compliance page provides a list of compliance controls.  Under each control is a set of assessments that are based on the Azure Security Benchmark which provides recommendations on how you can secure your cloud solutions on Azure.
1. Select **IM. Identity Management** then select **IM-6 Use strong authentication controls**.  The list shows customer responsibility actions that can be taken to improve compliance posture.
1. Select the **X** on the top-right corner of the screen to close the page and return to the Microsoft Defender for Cloud Overview page. 
1. Keep the Microsoft Defender for Cloud overview page open, you will use in the next task.


#### Task 2: In this task you will navigate to Azure Secure score and explore recommendations that can improve your secure score. 

1. From the Microsoft Defender for Cloud overview page, select the **Secure Score** card.

2. Select **Azure Pass – Sponsorship**.  Note your secure score.
3. From the recommendations page, select **Implement security best practices** to expand on the list. Notice that is shows its resource health status as red.
3. Select the item **There should be more than one owner assigned to your subscription**, which shows the resource health status as red. 
4. Underneath where it says **Affected resources**, make sure Unhealthy resources is selected/underlined, then select the listed Azure subscription.
5. From the top of the Access control (IAM) page, select **+ Add** then from the drop down select **Add role assignment**.
    1. From the left side of the page, select **Owner** (this should be the first item listed) so that the row is highlighted in gray, then select **Next** from the bottom of the page.
    2. Next to where it says Members, select **+ Select members**. 
    3. From the Select members window that opens on the right side of the screen, select **Alex Wilber**, then press **Select** on the bottom of the page.  
    4. From the Add role assignment page, verify that Alex Wilber is listed as a member, then select **Next** followed by **Review + assign**.
    5. It can take up to 24 hours for the status to be updated, after which your secure score will also be updated as all the items in the Manage access and permissions group are satisfied.
    6. From the top-left corner of the page, above where is says Azure Pass, select **Microsoft Defender for Cloud** to return the security center overview page.
1. Keep this page open for the subsequent task.


#### Task 3:  Recall that Microsoft Defender for Cloud is offered in two modes: without enhanced security features (free) and with enhanced security features which are available through the Microsoft Defender for Cloud plans. In this task you discover how to enable/disable the various Microsoft Defender for Cloud plans.

1.	From the Microsoft Defender for Cloud overview page, select the **Environment settings** from the left navigation panel.

2. Select the greater-than **>**sign next to where is say Tenant Root Group to exapand it (do not select Tenant Root Group directly as that will direct you to a different page), then select **Azure Pass - Sponsorship**
2.	On the Defender plans page, notice how you can select Enable all or select individual Defender plans. Leave the settings as they are with all plans set to off.
3.	You can now close the browser tab to exit the Azure portal.


#### Review
In this lab, you explored Microsoft Defender for Cloud and learned how Azure Secure Score can be used to improve your organization's security posture.
