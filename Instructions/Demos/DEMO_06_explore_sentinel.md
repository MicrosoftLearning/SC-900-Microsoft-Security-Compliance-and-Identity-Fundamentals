<!---
---
Demo:
    Title: 'Microsoft Sentinel'
    Learning Path/Module/Title: 'Learning Path: Describe the capabilities of Microsoft security solutions; Module 3: Describe the security capabilities of Microsoft Sentinel; Unit 3: Describe how Microsoft Sentinel provides integrated threat management'
---
--->

# Demo: Microsoft Sentinel

This demo maps to the following Learn content:

- Learning Path: Describe the capabilities of Microsoft security solutions
- Module: Describe the security capabilities of Microsoft Sentinel
- Unit: Describe how Microsoft Sentinel provides integrated threat management

## Demo scenario

In this demo, you'll walk through the process of creating a Microsoft Sentinel instance.  You will also set up the permissions to ensure access to the resources that will get deployed to support Microsoft Sentinel.  Once this basic setup is done, you'll walk through the steps for connecting Microsoft Sentinel to your data sources, and select a work book to monitor and visualize your data.  Lastly, you'll show some of the other options available, including the  built-in analytics to get notified of anything suspicious, the automation capability, and more.

### Pre-demo setup:  Create a Microsoft Sentinel instance

1. Open the browser tab, **Home-Microsoft Azure**.  If you previously closed the tab, open a browser page and in the address bar, enter portal.azure.com and sign back in.

1. In the search box, in the blue bar on the top of the page next to where it says Microsoft Azure, enter **Microsoft Sentinel** then select **Microsoft Sentinel** from the search results.

1. From the Microsoft Sentinel page, select **Create Microsoft Sentinel**.

1. From the Add Microsoft Sentinel to a workspace page, select **Create a new workspace**.

1. From the basics tab of the Create Log Analytics workspace, enter the following:
    1. Subscription:  Leave the default.
    1. Resource group: select **Create New**, then enter the name **SC900-Sentinel-RG** then select **OK**.
    1. Name: **SC900-LogAnalytics-workspace**.
    1. Region: **East US** (A different default region may be selected based on your location)
    1. Select **Review + Create** (no tags will be configured).
    1. Verify the information you entered then select **Create**.
    1. It may take a minute or two for the ne workspace to be listed, if you still don't see it, select **Refresh**, then select **Add**.

1. Once the new workspace is added, the Microsoft Sentinel | News & guides page will display, indicating that the Microsoft Sentinel free trial is activated.  Select **OK**.  Note the three steps listed on the Get started page.

1. Keep this page open, as you'll use it in the next task.

### Demo Part 2

With the Microsoft Sentinel instance created, you'll want to make sure that you have the necessary access to the resources that get deployed to support Microsoft Sentinel.  

1. In the search box, in the blue bar on the top of the page next to where it says Microsoft Azure, enter **resource groups** then select **Resource groups** from the search results. Assigning the role at the resource group level will ensure the role will apply to all the resources that are deployed to support Microsoft Sentinel.

1. From the Resource groups page, select the resource group that you created with Microsoft Sentinel, **SC900-Sentinel-RG**.

1. From the SC900-Sentinel-RG page, select **Access control (IAM)** from the left navigation panel.

1. From the Access control page, select **View my access**.  As MOD Administrator, the current role is Service administrator.  This will grant you the necessary permissions but for demo purposes you may want to show the Sentinel specific roles.  Close the MOD Administrator assignments window by selecting the **X** on the top-right corner of the window.

    1. From the Access control page, select **+Add**, then select **Add role assignment**.

    1. The Add role assignment window opens.  In the search box, enter **Microsoft Sentinel** to view the 4 roles associated with Microsoft Sentinel.
    1. From any of the roles listed, select **view** to the view the details of that role.  As a best practice you should assign the least privilege required for the role.  

    1. Close the window by selecting the **X** on the top-right corner of the window.

1. From the access control page, close the window by selecting the **X** on the top-right corner of the window.

### Demo Part 3

In this part of the demo, you'll show the steps for connecting to a data source.  Specifically, you'll connect to the Microsoft Defender for Cloud data connector.

1. In the search box, in the blue bar on the top of the page next to where it says Microsoft Azure, enter **Microsoft Sentinel** then select **Microsoft Sentinel** from the search results.

1. From the Microsoft Sentinel page, select the workspace you created with the instance of Microsoft Sentinel, **SC900-LogAnalytics-workspace**.

1. The first step with Microsoft Sentinel is to be able to collect data. From the left navigation panel select **Data connectors**, listed under configuration.

1. From the Data connectors page, scroll down on the main window to view the extensive list of available connectors. In the Search box of the data connectors page, enter **Microsoft Defender for Cloud** then from the list select **Microsoft Defender for Cloud**.

1. The Microsoft Defender for Cloud connector window opens. Review the description then Select **Open connector page**.

1. From the Microsoft Defender for Cloud connector page, review the Description on the left side of the window.

1. The instructions tab in the main window, provides the perquisites.  Review the instructions and configuration information.
    The instructions tab in the main window, provides the perquisites.  Review the instructions and configuration information.
    1. From the configuration section, select the empty box next to the listed subscription, **MOC Subscription--lodXXXXXXXX** so that a checkmark appears in a blue box, then select **Connect** (the connect option is shown above the search box).  A Connect window will appear, select **OK**.  in the status column, next to the subscription you should see that status update to Connected.  Don't worry if you don't see connected status in the window on the left side of the page, do NOT refresh the browser.
    1. Scroll down on the page and select **Enable** to create incidents automatically from all alerts generated in the connected service.
    1. Now select the **Next steps** tab on the top of the page, to view recommended workbooks, for this data connector.  Microsoft Sentinel comes with built-in workbook templates to allow you to quickly gain insights across your data as soon as you connect a data source.
    1. Select **ASC Compliance and Protection** (Note: ASC or Azure Security Center is now called Microsoft Defender for Cloud).  This opens the workbooks page.  On the right side of the screen, review the description then select **Save** from the bottom of the screen then select **OK** to save the workbook to the default location.  Now select **View saved workbook**.  
    1. In the workspace field, select **SC900-LogAnalytics-workspace**.
    1. From the top of the workbook page, select **Auto refresh: Off**, then select **5 minutes** and select **Apply**.
    1. From the top of the workbook page, select the **Save icon**.
    1. From the top-left corner of the Workbooks page, above where it says Workbooks, select **Microsoft Sentinel**. This returns you to the Overview page. You should now see the number 1 above where it says connected, to indicate one active connector (you may need to select refresh).

1. Keep this page open, as you'll use it in the next task.

### Demo Part 4

In this part of the demo, you'll show some of the options available in Sentinel.

1. From the left navigation panel, select **Hunting**.  From the **queries** tab, which is selected (underlined), select any query from the list.  Once a query is selected, note the information that provided about that query, including the code for the query, and the option to run the query and see results.  Don't select anything.

1. From the left navigation panel, select **MITRE ATT&CK**.  MITRE ATT&CK is a publicly accessible knowledge base of tactics and techniques that are commonly used by attackers. With Microsoft Sentinel you can view the detections already active in your workspace, and those available for you to configure, to understand your organization's security coverage, based on the tactics and techniques from the MITRE ATT&CK® framework.  Select any cell from the matrix and note the information available on the right side of the screen.  

1. From the left navigation panel, select **Community**. Microsoft security analysts constantly create and add new workbooks, playbooks, hunting queries, and more, posting them to the community for you to use in your environment. You can download sample content from the private community GitHub repository to create custom workbooks, hunting queries, notebooks, and playbooks for Microsoft Sentinel.  Select **Onboard community content**.  A new tab to the GitHub repository opens where you can download content to enable your scenarios.  Return to the Azure tab in your browser.

1. From the left navigation panel, select **Analytics**.  Select the first item from the list **Advanced Multistage Attack Detection**.  Note the detailed information.  Microsoft Sentinel uses Fusion, a correlation engine based on scalable machine learning algorithms, to automatically detect multistage attacks (also known as advanced persistent threats) by identifying combinations of anomalous behaviors and suspicious activities that are observed at various stages of the kill chain. On the basis of these discoveries, Microsoft Sentinel generates incidents that would otherwise be difficult to catch.

1. From the left navigation panel, select **Automation**.  Here you can create simply automation rules, integrate with existing playbooks, or create new playbooks.  Select **+ Create** then select **Automation rule**.  Note the window that opens on the right side of the screen and the options available to create conditions and actions.  Select **Cancel** from the bottom of the screen.

1. From the left navigation panel, select **Workbooks**. From the Workbooks page, select the **My workbooks** tab, which is above the search box.  The workbook you saved earlier is listed and available for you to view and monitor your data.   NOTE: There isn't any real activity happening in the Azure subscription to reflect in the workbook and Azure lab subscriptions may experience greater than normal delays in collecting data that can be visualized in the workbook.

1. Close the window by selecting the **X** on the top-right corner of the window.

1. From the top left corner of the window, just below the blue bar, select **Home** to return to the home page of the Azure portal.  

### Review

In this demo you walked through the steps for connecting Microsoft Sentinel to data sources, you set up a workbook, and walked several options available in Microsoft Sentinel.
