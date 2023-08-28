<!---
---
Lab:
    Title: 'Explore Microsoft Sentinel'
    Learning Path/Module/Title: 'Learning Path: Describe the capabilities of Microsoft security solutions; Module 3: Describe the security capabilities of Microsoft Sentinel; Unit 3: Describe how Microsoft Sentinel provides integrated threat management'
---
--->

# Lab: Explore Microsoft Sentinel

This lab maps to the following Learn content:

- Learning Path: Describe the capabilities of Microsoft security solutions
- Module: Describe the security capabilities of Microsoft Sentinel
- Unit: Describe how Microsoft Sentinel provides integrated threat management

## Lab scenario

, you'll walk through the process of creating a Microsoft Sentinel instance.  You'll also set up the permissions to ensure access to the resources that will get deployed to support Microsoft Sentinel.  Once this basic setup is done you'll walk through the steps for connecting Microsoft Sentinel to your data sources, set up a workbook, and do a brief walk-through of some of key capabilities available in Microsoft Sentinel. 

**Estimated Time**: 45-60 minutes

### Task 1

Create a Microsoft Sentinel instance

1. You should be at the home page for Azure services.  If you previously closed the browser, open Microsoft Edge. In the address bar, enter **portal.azure.com**, and sign in with your admin credentials.

1. In the blue search box on the top of the page, enter **Microsoft Sentinel** then select **Microsoft Sentinel** from the search results.

1. From the Microsoft Sentinel page, select **Create Microsoft Sentinel**.

1. From the Add Microsoft Sentinel to a workspace page, select **Create a new workspace**.

1. From the basics tab of the Create Log Analytics workspace, enter the following:
    1. Subscription: leave the default, this is the Azure subscription provided by the Authorized Lab Hoster (ALH).
    1. Resource group: select **SC900-Sentinel-RG**. If this resource group is not listed create it by selecting **Create new**, enter **SC900-Sentinel-RG**, then select **OK**.
    1. Name: **SC900-LogAnalytics-workspace**.
    1. Region: **East US** (A different default region may be selected based on your location)
    1. Select **Review + Create** (no tags will be configured).
    1. Verify the information you entered then select **Create**.
    1. It may take a minute or two for the ne workspace to be listed, if you still don't see it, select **Refresh**, then select **Add**.

1. Once the new workspace is added, the Microsoft Sentinel | News & guides page will display, indicating that the Microsoft Sentinel free trial is activated.  Select **OK**.  Note the three steps listed on the Get started page.

1. Keep this page open, as you'll use it in the next task.

### Task 2

With the Microsoft Sentinel instance created, it is important that users that will have responsibility to support Microsoft Sentinel have the necessary permissions.  This is done by assigning the designated user the required role permissions.  In this task, you'll view the available, built-in Microsoft Sentinel roles.

1. In the blue search box, enter **resource groups** then select **Resource groups** from the search results. 

1. From the Resource groups page, select the resource group that you created with Microsoft Sentinel, **SC900-Sentinel-RG**.  Working at the resource group level will ensure that any role that is selected will apply to all the resources that are part of the Microsoft Sentinel instance that was created in the previous task.

1. From the SC900-Sentinel-RG page, select **Access control (IAM)** from the left navigation panel.

1. From the Access control page, select **View my access**.  For the Azure subscription provided to you by the Authorized Lab Hoster, a role has been defined that will give you access to manage all necessary resources, as shown in the description. It is important, however, to understand the available Sentinel specific roles.  Close the assignments window by selecting the **X** on the top-right corner of the window.

1. From the Access control page, select the **Roles** tab on the top of the page/
    1. In the search box, enter **Microsoft Sentinel** to view the built-in roles associated with Microsoft Sentinel.
    1. From any of the roles listed, select **view** to the view the details of that role.  As a best practice you should assign the least privilege required for the role.  
    1. Close the window by selecting the **X** on the top-right corner of the window.

1. From the access control page, close the window by selecting the **X** on the top-right corner of the window.

1. From the top left corner of the window, just below the blue bar where it says Microsoft Azure, select **Home** to return to the Azure services home page.

1. Keep the Azure tab open on your browser.

### Task 3

The purpose of this task is to walk you through the steps involved in connecting to a data source. Many data connectors are deployed as part of a Microsoft Sentinel solution together with related content like analytics rules, workbooks and playbooks. The Microsoft Sentinel Content hub is the centralized location to discover and manage out-of-the-box (built-in) content. In this step, you'll use the content hub to deploy the Microsoft Defender for Cloud solution for Microsoft Sentinel.  This solution allows you to ingest Security alerts reported in Microsoft Defender for Cloud.

1. From the Azure services home page, select Microsoft Sentinel, then select the instance you created, **SC900-LogAnalytics-workspace**.

1. From the left navigation panel, select **Content hub**.

1. Take a moment to scroll down to see the long list of available solutions and the options to filter the list.  For this task, your're looking for **Microsoft Defender for Cloud**.  Select it from the list.  In the side window that opens, read the description then select **Install**.  This solution includes one data connector and one analytics rule. It may take a minute to install.  Select **Manage**.

1. Select the box next to where it says Microsoft Defender for Cloud.  A window opens on the right side of the page.  Select **Open connector page**.

1. Note the configuration instructions.  Select the box next to the name of the subscription then select **Connect**.  A pop-op window may appear indicating that only subscriptions you have Security Reader permissions on will start streaming Microsoft Defender for Cloud alerts.  Select **OK**.  The status will move to connected.  The connector is now enabled, although it may take some time for the connector to show up in the data connectors page.  

1. Now view information about the analytics rule.  From the top of the page (in the breadcrumb) select **Microsoft Defender for Cloud**. De-select the box next to where it says Microsoft Defender for Cloud, as you have already configured the connector (it may take some time for the warning icon to disappear). Select the box next to where it says, **Detect CoreBackUp Deletion Activity from related security alerts**. In the window that opens you will see information about the rule and what it does.  
    1. Although the details of the rule logic are beyond the scope of the fundamentals, go through the steps to configure the rule to view the type of information that can be configured as part of the rule. Select **Configuration**.
    1. Select the rule **Detect CoreBackUp Deletion Activity from related security alerts**.
    1. From the window that opens on the right side of the page, select **Create rule**.
    1. Go through each of the configuration pages, then select **Review and create**, then select **Save**.

1. Return to the Sentinel page by selecting **Microsoft Sentinel | Content hub** from the bread-crumb at the top of the page, above where it says Analytics rules.

1. Keep this page open, as you'll use it in the next task.


### Task 4

In this task, you'll walk through some of the options available in Sentinel.

1. From the left navigation panel, select **Hunting**.  From the top of the page, select the **Queries** tab. Read the description of what is a hunting query. Hunting queries can be added through the Content hub. Any queries previously installed would be listed here. Select **Go to content hub**.  The content hub lists content that includes queries either as part of a solution or as a standalone query.  Scroll down to see the available options. Close the Content hub by selecting the **X** on the top-right corner of the window.

1. From the left navigation panel, select **MITRE ATT&CK**.  MITRE ATT&CK is a publicly accessible knowledge base of tactics and techniques that are commonly used by attackers. With Microsoft Sentinel you can view the detections already active in your workspace, and those available for you to configure, to understand your organization's security coverage, based on the tactics and techniques from the MITRE ATT&CK® framework.  Select any cell from the matrix and note the information available on the right side of the screen.  

1. From the left navigation panel, select **Community**. Microsoft security analysts constantly create and add new workbooks, playbooks, hunting queries, and more, posting them to the community for you to use in your environment. From the right side of the screen, select **Onboard community content**.  A new tab to the GitHub repository opens where you can download content to enable your scenarios. Scroll down to the README.md section and review the description. Return to the Azure tab in your browser.

1. From the left navigation panel, select **Analytics**.  There should be two active rules, one that is available by default and the rule you created in the previous task. Select the default rule **Advanced Multistage Attack Detection**.  Note the detailed information.  Microsoft Sentinel uses Fusion, a correlation engine based on scalable machine learning algorithms, to automatically detect multistage attacks (also known as advanced persistent threats) by identifying combinations of anomalous behaviors and suspicious activities that are observed at various stages of the kill chain. On the basis of these discoveries, Microsoft Sentinel generates incidents that would otherwise be difficult to catch.

1. From the left navigation panel, select **Automation**.  Here you can create simple automation rules, integrate with existing playbooks, or create new playbooks.  Select **+ Create** then select **Automation rule**.  Note the window that opens on the right side of the screen and the options available to create conditions and actions.  Select **Cancel** from the bottom of the screen.

1. From the left navigation panel, select **Workbooks**. Read the description of what is a Microsoft Sentinel workbook.  Workbooks can be added through the Content hub.Any workbooks previously installed would be listed here. Select **Go to content hub**.  The content hub lists content that includes workbooks either as part of a solution or as a standalone workbook. Scroll down to see the available options.

1. Close the window by selecting the **X** on the top-right corner of the window.

1. From the top left corner of the window, just below the blue bar, select **Home** to return to the home page of the Azure portal.

1. Close all the open browser tabs.

### Review

In this lV you walked through the steps for connecting Microsoft Sentinel to data sources, you set up a workbook, and walked several options available in Microsoft Sentinel.
