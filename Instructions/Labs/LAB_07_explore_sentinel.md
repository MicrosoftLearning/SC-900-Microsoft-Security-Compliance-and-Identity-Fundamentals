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

In this lab you will walk through the process of creating an Microsoft Sentinel instance.  You will also set up the permissions to ensure access to the resources that will get deployed to support Microsoft Sentinel.  Once this basic setup is done you will walk through the steps for connecting Microsoft Sentinel to your data sources, setup a workbook, and do a brief walk-through of some of key capabilities available in Microsoft Sentinel. 

**Estimated Time**: 45-60 minutes

### Task 1

Create a Microsoft Sentinel instance

1. Open the browser tab, **Home-Microsoft Azure**.  If you previously closed the tab, open a browser page and in the address bar, enter portal.azure.com and sign back in.

1. In the search box, in the blue bar on the top of the page next to where it says Microsoft Azure, enter **Microsoft Sentinel** then select **Microsoft Sentinel** from the search results.

1. From the Microsoft Sentinel page, select **Create Microsoft Sentinel**.

1. From the Add Microsoft Sentinel to a workspace page, select **Create a new workspace**.

1. From the basics tab of the Create Log Analytics workspace, enter the following:
    1. Subscription: In most cases the Azure subscription provided by the Authorized Lab Hoster (ALH) should be pre-populated, by default.  If not, please consult your instructor or learning partner.
    1. Resource group: select **Create New**, then enter the name **SC900-Sentinel-RG** then select **OK**.
    1. Name: **SC900-LogAnalytics-workspace**.
    1. Region: **East US** (A different default region may be selected based on your location)
    1. Select **Next: Tags >**

1. For the Tags, you can leave this blank, then select **Review + Create**.

1. Verify the information you entered then select **Create**.

1. It may take a minute or two for the ne workspace to be listed, if you still don't see it, select **Refresh**, then select **Add**.

1. Once the new workspace is added, the Microsoft Sentinel | News & guides page will display.  Note the three steps listed on the Get started page.

1. Keep this page open, as you will use it in the next task.

### Task 2

With the Microsoft Sentinel instance created, you will want to make sure that you have the necessary access to the resources that get deployed to support Microsoft Sentinel.

1. In the search box, in the blue bar on the top of the page next to where it says Microsoft Azure, enter **resource groups** then select **Resource groups** from the search results. Assigning the role at the resource group level will ensure the role will apply to all the resources that are deployed to support Microsoft Sentinel.

1. From the Resource groups page, select the resource group that you created with Microsoft Sentinel, **SC900-Sentinel-RG**.

1. From the SC900-Sentinel-RG page, select **Access control (IAM)** from the left navigation panel.

1. From the Access control page, select **View my access**.  For the Azure subscription provided to you by the Authorized Lab Hoster, a role has been defined that will give you access to manage all necessary resources, as shown in the description. It is important, however, to understand the available Sentinel specific roles.  Close the assignments window by selecting the **X** on the top-right corner of the window.

    1. From the Access control page, select the **Roles** tab on the top of the page/
    1. In the search box, enter **Microsoft Sentinel** to view the built-in roles associated with Microsoft Sentinel.
    1. From any of the roles listed, select **view** to the view the details of that role.  As a best practice you should assign the least privilege required for the role.  
    1. Close the window by select the **X** on the top-right corner of the window.

1. From the access control page, close the window by select the **X** on the top-right corner of the window.

### Task 3

The purpose of this task is to walk you through the steps involved in setting up a data connector to your instance of Microsoft Sentinel. NOTE: You may not see a connected status for the connector given that Azure lab subscriptions may experience greater than normal delays in connecting to a data source.

1. In the search box, in the blue bar on the top of the page next to where it says Microsoft Azure, enter **Microsoft Sentinel** then select **Microsoft Sentinel** from the search results.

1. From the Microsoft Sentinel page, select the workspace you created with the instance of Microsoft Sentinel, **SC900-LogAnalytics-workspace**.

1. The first step with Microsoft Sentinel is to be able to collect data. From the left navigation panel select **Data connectors**, listed under configuration.

1. From the Data connectors page, scroll down on the main window to view the extensive list of available connectors. In the Search box of the data connectors page, enter **Azure Activity** then from the list select **Azure Activity**.

1. The Azure Activity connector window opens.  Select **Open connector page**.

1. Review the Description on the left side of the window. The main window provides detailed instructions, including prerequisites and configuration information. Select **Launch Azure Policy Assignment Wizard** from the bottom of the page.

    1. Select the ellipses next to the **Scope** field, then select the down arrow in the subscription field and select the available subscription.
    1. Press **Select** at the bottom of the page.
    1. Select **Next** to configure the Parameters.  Here you will select the primary log Analytics workspace. Select the down arrow key in the field and select **SC900-LogAnalytics-worksapce**.
    1. Select **Next** to configure remediation.  Here you will select the box next to where it says **Create a remediation task**, so that a checkmark appears in the blue box.  This ensures the policy will be evaluated against existing resources.  
    1. Select **Review + Create**.
    1. Select **Create**

1. You are returned to the Azure Activity connector page.  It will take some time to see a connected status.  Do NOT select the browser refresh.  Return to the Microsoft Sentinel overview page by selecting **Microsoft Sentinel** from the breadcrumb at the top of the page.

1. Keep this page open, as you will use it in the next task.

### Task 4

In this task you will walk through the process of setting up a workbook for Azure Activity, to visualize and monitor your data.  NOTE: You may not see any data in the workbook given that Azure lab subscriptions may experience greater than normal delay in connecting to the data source.

1. From the left navigation panel, select **Workbooks**.

1. In the search box, enter Azure Activity then select **Azure Activity**.

1. From the window that opens on the right side of the screen, review the description then select **Save** from the bottom of the screen then select **OK** to save the workbook to the default location.  Now select **View saved workbook**.

1. The Azure Activity Workbooks page opens.  The workbook data may not show any data as it takes time for the connector to connect and data to be collected, but here is where you can view information about the top 10 active resource groups and view activities over time.  

1. From the top-left corner of the Workbooks page, above where it says Workbooks, select **Microsoft Sentinel | Workbooks** then select **Overview** from the left navigation panel to return to the Overview page.

1. Keep this page open, as you will use it in the next task.

### Task 5

In this task you will walk through some of the options available in Sentinel.

1. From the left navigation panel, select **Hunting**.  From the **queries** tab, which is selected (underlined), select any query from the list.  Once a query is selected, note the information that is provided about that query, including the code for the query, as well as the option to run the query and see results.  Don't select anything.

1. From the left navigation panel, select **MITRE ATT&CK**.  MITRE ATT&CK is a publicly accessible knowledge base of tactics and techniques that are commonly used by attackers. With Microsoft Sentinel you can view the detections already active in your workspace, and those available for you to configure, to understand your organization's security coverage, based on the tactics and techniques from the MITRE ATT&CK® framework.  Select any cell from the matrix and note the information available on the right side of the screen.  

1. From the left navigation panel, select **Community**. Microsoft security analysts constantly create and add new workbooks, playbooks, hunting queries, and more, posting them to the community for you to use in your environment. From the right side of the screen, select **Onboard community content**.  A new tab to the GitHub repository opens where you can download content to enable your scenarios.  Return to the Azure tab in your browser.

1. From the left navigation panel, select **Analytics**.  Select the first item from the list **Advanced Multistage Attack Detection**.  Note the detailed information.  Microsoft Sentinel uses Fusion, a correlation engine based on scalable machine learning algorithms, to automatically detect multistage attacks (also known as advanced persistent threats) by identifying combinations of anomalous behaviors and suspicious activities that are observed at various stages of the kill chain. On the basis of these discoveries, Microsoft Sentinel generates incidents that would otherwise be difficult to catch.

1. From the left navigation panel, select **Automation**.  Here you can create simply automation rules, integrate with existing playbooks, or create new playbooks.  Select **+ Create** then select **Automation rule**.  Note the window that opens on the right side of the screen and the options available to create conditions and actions.  Select **Cancel** from the bottom of the screen.

1. From the left navigation panel, select **Workbooks**. From the Workbooks page, select the **My workbooks** tab, which is above the search box.  The workbook you saved earlier is listed and available for you to view and monitor your data.  Select **Azure Activity** then from the window that opens on the right side of the screen, select **View saved workbook**.  Note:  Some Azure Subscriptions will take some time to initiate collection of data so it may not show any data.  

1. Close the window by select the **X** on the top-right corner of the window.

1. From the top left corner of the window, just below the blue bar, select **Home** to return to the home page of the Azure portal.

1. Close all the open browser tabs.

### Review

In this demo you walked through the steps for connecting Microsoft Sentinel to data sources, you setup a workbook, and walked several options available in Microsoft Sentinel.
