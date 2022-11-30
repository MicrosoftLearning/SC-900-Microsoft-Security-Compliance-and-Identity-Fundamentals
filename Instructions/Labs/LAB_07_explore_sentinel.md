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

1. Open Microsoft Edge. In the address bar enter **portal.azure.com**.
1. Sign in with your admin credentials.
    1. In the Sign in window enter the username provided by your lab hosting provider then select **Next**.
    1. Enter the admin password which should be provided by your lab hosting provider. Select **Sign in**.
    1. When prompted to stay signed- in, select **Yes**.

1. In the blue search box on the top of the page, enter **Microsoft Sentinel** then select **Microsoft Sentinel** from the search results.

1. From the Microsoft Sentinel page, select **Create Microsoft Sentinel**.

1. From the Add Microsoft Sentinel to a workspace page, select **Create a new workspace**.

1. From the basics tab of the Create Log Analytics workspace, enter the following:
    1. Subscription: In most cases the Azure subscription provided by the Authorized Lab Hoster (ALH) should be pre-populated, by default.  If not, please consult your instructor or learning partner.
    1. Resource group: select **Create New**, then enter the name **SC900-Sentinel-RG** then select **OK**.
    1. Name: **SC900-LogAnalytics-workspace**.
    1. Region: **East US** (A different default region may be selected based on your location)
    1. Select **Review + Create** (no tags will be configured).

1. Verify the information you entered then select **Create**.

1. It may take a minute or two for the ne workspace to be listed, if you still don't see it, select **Refresh**, then select **Add**.

1. Once the new workspace is added, the Microsoft Sentinel | News & guides page will display, indicating that the Microsoft Sentinel free trial is activated.  Select **OK**.  Note the three steps listed on the Get started page.

1. Keep this page open, as you will use it in the next task.

### Task 2

With the Microsoft Sentinel instance created, it is important that users that will have responsibility to support Microsoft Sentinel have the necessary permissions.  This is done by assigning the designated user the required role permissions.  In this task, you will view the available, built-in Microsoft Sentinel roles.

1. In the blue search box, enter **resource groups** then select **Resource groups** from the search results. 

1. From the Resource groups page, select the resource group that you created with Microsoft Sentinel, **SC900-Sentinel-RG**.  Working at the resource group level will ensure that any role that is selected will apply to all the resources that are part of the Microsoft Sentinel instance that was created in the previous task.

1. From the SC900-Sentinel-RG page, select **Access control (IAM)** from the left navigation panel.

1. From the Access control page, select **View my access**.  For the Azure subscription provided to you by the Authorized Lab Hoster, a role has been defined that will give you access to manage all necessary resources, as shown in the description. It is important, however, to understand the available Sentinel specific roles.  Close the assignments window by selecting the **X** on the top-right corner of the window.

    1. From the Access control page, select the **Roles** tab on the top of the page/
    1. In the search box, enter **Microsoft Sentinel** to view the built-in roles associated with Microsoft Sentinel.
    1. From any of the roles listed, select **view** to the view the details of that role.  As a best practice you should assign the least privilege required for the role.  
    1. Close the window by select the **X** on the top-right corner of the window.

1. From the access control page, close the window by select the **X** on the top-right corner of the window.

### Task 3

The purpose of this task is to walk you through the steps involved in setting up a data connector to your instance of Microsoft Sentinel and selecting a built-in workbook templates to allow you to quickly gain insights across your data as soon as you connect a data source. NOTE: Azure lab subscriptions may experience greater than normal delays in connecting to a data source and/or visualizing data.

1. In the search box, in the blue bar on the top of the page next to where it says Microsoft Azure, enter **Microsoft Sentinel** then select **Microsoft Sentinel** from the search results.

1. From the Microsoft Sentinel page, select the workspace you created with the instance of Microsoft Sentinel, **SC900-LogAnalytics-workspace**.

1. The first step with Microsoft Sentinel is to be able to collect data. From the left navigation panel select **Data connectors**, listed under configuration.

1. From the Data connectors page, scroll down on the main window to view the extensive list of available connectors. In the Search box of the data connectors page, enter **Microsoft Defender for Cloud** then from the list select **Microsoft Defender for Cloud**.

1. The Microsoft Defender for Cloud connector window opens. Review the description then Select **Open connector page**.

1. From the Microsoft Defender for Cloud connector page, review the Description on the left side of the window.

1. The instructions tab in the main window, provides the perquisites.  Review the instructions and configuration information.
    1. From the configuration section, select the empty box next to the listed subscription, **MOC Subscription--lodXXXXXXXX** so that a checkmark appears then select **Connect** (the connect option is shown above the search box).  A Connect window will appear, select **OK**.  in the status column, next to the subscription you should see that status update to Connected.  Don't worry if you don't see connected status in the window on the left side of the page, do NOT refresh the browser.
    1. Scroll down on the page and select **Enable** to create incidents automatically from all alerts generated in the connected service.
    1. Now select the **Next steps** tab on the top of the page, to view recommended workbooks, for this data connector.  Microsoft Sentinel comes with built-in workbook templates to allow you to quickly gain insights across your data as soon as you connect a data source.
    1. Select **ASC Compliance and Protection** (Note: ASC or Azure Security Center is now called Microsoft Defender for Cloud).  This opens the workbooks page.  On the right side of the screen, review the description then select **Save** from the bottom of the screen then select **OK** to save the workbook to the default location.  Now select **View saved workbook**.
    1. From the top-left corner of the Workbooks page, above where it says Workbooks, select **Microsoft Sentinel**. This returns you to the Overview page. You should now see the number 1 above where it says connected, to indicate one active connector (you may need to select refresh).

1. Keep this page open, as you will use it in the next task.

### Task 4

In this task you will walk through some of the options available in Sentinel.

1. From the left navigation panel, select **Hunting**.  From the **queries** tab, which is selected (underlined), select any query from the list.  Once a query is selected, note the information that is provided about that query, including the code for the query, as well as the option to run the query and see results.  Don't select anything.

1. From the left navigation panel, select **MITRE ATT&CK**.  MITRE ATT&CK is a publicly accessible knowledge base of tactics and techniques that are commonly used by attackers. With Microsoft Sentinel you can view the detections already active in your workspace, and those available for you to configure, to understand your organization's security coverage, based on the tactics and techniques from the MITRE ATT&CK® framework.  Select any cell from the matrix and note the information available on the right side of the screen.  

1. From the left navigation panel, select **Community**. Microsoft security analysts constantly create and add new workbooks, playbooks, hunting queries, and more, posting them to the community for you to use in your environment. From the right side of the screen, select **Onboard community content**.  A new tab to the GitHub repository opens where you can download content to enable your scenarios. Scroll down to the README.md section and review the description. Return to the Azure tab in your browser.

1. From the left navigation panel, select **Analytics**.  Select the first item from the list **Advanced Multistage Attack Detection**.  Note the detailed information.  Microsoft Sentinel uses Fusion, a correlation engine based on scalable machine learning algorithms, to automatically detect multistage attacks (also known as advanced persistent threats) by identifying combinations of anomalous behaviors and suspicious activities that are observed at various stages of the kill chain. On the basis of these discoveries, Microsoft Sentinel generates incidents that would otherwise be difficult to catch.

1. From the left navigation panel, select **Automation**.  Here you can create simple automation rules, integrate with existing playbooks, or create new playbooks.  Select **+ Create** then select **Automation rule**.  Note the window that opens on the right side of the screen and the options available to create conditions and actions.  Select **Cancel** from the bottom of the screen.

1. From the left navigation panel, select **Workbooks**. From the Workbooks page, select the **My workbooks** tab, which is above the search box.  The workbook you saved earlier is listed and available for you to view and monitor your data.  Select **ASC Compliance and Protection** then from the window that opens on the right side of the screen, select **View saved workbook**.  NOTE: Azure lab subscriptions may experience greater than normal delays in collecting data that can be visualized in the workbook.

1. Close the window by select the **X** on the top-right corner of the window.

1. From the top left corner of the window, just below the blue bar, select **Home** to return to the home page of the Azure portal.

1. Close all the open browser tabs.

### Review

In this demo you walked through the steps for connecting Microsoft Sentinel to data sources, you setup a workbook, and walked several options available in Microsoft Sentinel.
