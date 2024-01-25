<!---
---
Demo:
    Title: 'Microsoft Sentinel'
    Learning Path/Module/Title: 'Learning Path: Describe the capabilities of Microsoft security solutions; Module 3: Describe the security capabilities of Microsoft Sentinel; Unit 3: Describe threat detection and mitigation capabilities in Microsoft Sentinel'
---
--->

# Demo: Microsoft Sentinel

This demo maps to the following Learn content:

- Learning Path: Describe the capabilities of Microsoft security solutions
- Module: Describe the security capabilities of Microsoft Sentinel
- Unit: Describe threat detection and mitigation capabilities in Microsoft Sentinel

## Demo scenario

In this demo, you'll walk through the some of the options available with Microsoft Sentinel, including using the content hub to find packaged solutions that you can deploy.  But first, you'll walk through the process of setting up role-based access control permissions for users who would need to access your Microsoft Sentinel resources.

### Demo part 1

An instance of Microsoft Sentinel should have already been created as part of the pre-demo setup. Verify that it was created.

1. Open the browser tab, **Home-Microsoft Azure**.  If you previously closed the tab, open a browser page and in the address bar, enter **https://portal.azure.com**. Sign in with the Azure credentials provided by the authorized lab hoster (ALH).  This bring you to the Azure services home page.

1. In the search box, in the blue bar on the top of the page next to where it says Microsoft Azure, enter **Microsoft Sentinel** then select **Microsoft Sentinel** from the search results.  

1. On the Microsoft Sentinel page, you should see your instance of Sentinel listed and select it.  If it's not listed, create it now.
    1. From the Microsoft Sentinel page, select **Create Microsoft Sentinel**.

    1. From the Add Microsoft Sentinel to a workspace page, select **Create a new workspace**. From the basics tab of the Create Log Analytics workspace, enter the following:
        1. Subscription:  Leave the default.
        1. Resource group: select **Create New**, then enter the name **SC900-Sentinel-RG** then select **OK**.
        1. Name: **SC900-LogAnalytics-workspace**.
        1. Region: **East US** (A different default region may be selected based on your location)
        1. Select **Review + Create** (no tags will be configured).
        1. Verify the information you entered then select **Create**.
        1. It may take a minute or two for the ne workspace to be listed, if you still don't see it, select **Refresh**, then select **Add**.
        1. Once the new workspace is added, the Microsoft Sentinel | News & guides page will display, indicating that the Microsoft Sentinel free trial is activated.  Select **OK**.

1. Keep this page open, as you'll use it in a subsequent task.

### Demo Part 2

As with all Azure resources, you want to ensure that users have the proper permissions to access your Microsoft Sentinel resources. Here you will show the steps to assign a role and the available roles for use with Microsoft Sentinel.  

1. In the search box, in the blue bar on the top of the page next to where it says Microsoft Azure, enter **resource groups** then select **Resource groups** from the search results. Assigning the role at the resource group level will ensure the role will apply to all the resources that are deployed to support Microsoft Sentinel.

1. From the Resource groups page, select the resource group that you created with Microsoft Sentinel, **SC900-Sentinel-RG**.

1. From the SC900-Sentinel-RG page, select **Access control (IAM)** from the left navigation panel.

1. From the Access control page, select **View my access**.  If you are using the Skillable Cloud Slice subscription, the role assignment is set to LOD Owner, which is a custom role assignment configured for this Cloud Slice subscription and it will grant you the necessary permissions. For demo purposes, however, it's good to show the Sentinel specific roles.  Close the assignments window by selecting the **X** on the top-right corner of the window.

    1. From the Access control page, select **+Add**, then select **Add role assignment**.

    1. The Add role assignment window opens.  In the search box, enter **Microsoft Sentinel** to view the roles associated with Microsoft Sentinel.
    1. From any of the roles listed, select **view** to the view the details of that role.  As a best practice you should assign the least privilege required for the role.  

    1. Close the window by selecting the **X** on the top-right corner of the window.

1. From the access control page, close the window by selecting the **X** on the top-right corner of the window.

### Demo Part 3

In this part of the demo, you'll show the steps for connecting to a data source. Many data connectors are deployed as part of a Microsoft Sentinel solution together with related content like analytics rules, workbooks and playbooks. The Microsoft Sentinel Content hub is the centralized location to discover and manage out-of-the-box (built-in) content. In this step, you'll use the content hub to deploy the Microsoft Defender for Cloud solution for Microsoft Sentinel.  This solution allows you to ingest Security alerts reported in Microsoft Defender for Cloud.

1. Open the browser tab for Microsoft Sentinel.

1. From the left navigation panel, select **Content hub**.

1. Take a moment to scroll down to see the long list of available solutions and the options to filter the list.  For this task, your're looking for **Microsoft Defender for Cloud**.  Select it from the list.  In the side window that opens, read the description then select **Install**.  Once the installation is completed, the status column in the main window will show as installed.

1. On the right side of the the Microsoft Defender for Cloud page is the description and notes associated with the solution from Content Hub and what is included as part of this solution.  On the main window are the components of the solution.  In this case there are two data connectors and one data rule. The orange triangle indicates that some configuration is needed. Select the box next to where it says **Subscription-based Microsoft Defender for Cloud (Legacy)**.  A window opens on the right side of the page.  Select **Open connector page**.

1. Note the configuration instructions.  Select the box next to the name of the subscription then select **Connect**.  The status will move to connected.  The connector is now enabled, although it may take some time for the connector to show up in the data connectors page.  

1. Now view information about the analytics rule.  From the top of the page (in the breadcrumb) select **Microsoft Defender for Cloud**. De-select the box next to where it says Microsoft Defender for Cloud, as you have already configured the connector (it may take some time for the warning icon to disappear). Select the box next to where it says, **Detect CoreBackUp Deletion Activity from related security alerts**.  This brings up the Analytics Rules page.  Again, select the **Detect CoreBackUp Deletion Activity from related security alerts** rule. A window that opens on the right, that provides information about the rule and what it does.  Select **Create rule**.  
    1. Although the details of the rule logic are beyond the scope of the fundamentals, go through each tab in the rule creation to view the type of information that can be configured
    1. When you reach the Review + create tab, select **Save**.

1. Return to the Sentinel page by selecting **Microsoft Sentinel | Content hub** from the bread-crump at the top of the page, above where it says Analytics rules.

1. Call out that by using the content hub, a solution can be easily and quickly deployed.

1. Keep this page open, as you'll use it in the next task.

### Demo Part 4

In this part of the demo, you'll show some of the options available in Sentinel.

1. From the left navigation panel, select **Hunting**.  From the top of the page, select the **queries** tab. Read the description of what is a hunting query. Hunting queries can be added through the Content hub. Any queries previously installed would be listed here. Select **Go to content hub**.  The content hub lists content that includes queries either as part of a solution or as a standalone query.  Scroll down to see the available options.

1. From the left navigation panel, select **MITRE ATT&CK**.  MITRE ATT&CK is a publicly accessible knowledge base of tactics and techniques that are commonly used by attackers. With Microsoft Sentinel you can view the detections already active in your workspace, and those available for you to configure, to understand your organization's security coverage, based on the tactics and techniques from the MITRE ATT&CK® framework.  Select any cell from the matrix and note the information available on the right side of the screen.  

1. From the left navigation panel, select **Community**. The community page includes Cybersecurity insights and updates from Microsoft Research, a link to a list of Microsoft Sentinel Blogs, a link to Microsoft Sentinel Forums, links the the latest editions to the Microsoft Sentinel Hub, and more. Explore this at will.

1. From the left navigation panel, select **Analytics**.  There should be two active rules, one that is available by default and the rule you created in the previous task. Select the default rule **Advanced Multistage Attack Detection**.  Note the detailed information.  Microsoft Sentinel uses Fusion, a correlation engine based on scalable machine learning algorithms, to automatically detect multistage attacks (also known as advanced persistent threats) by identifying combinations of anomalous behaviors and suspicious activities that are observed at various stages of the kill chain. On the basis of these discoveries, Microsoft Sentinel generates incidents that would otherwise be difficult to catch.

1. From the left navigation panel, select **Automation**.  Here you can create simple automation rules, integrate with existing playbooks, or create new playbooks.  Select **+ Create** then select **Automation rule**.  Note the window that opens on the right side of the screen and the options available to create conditions and actions.  Select **Cancel** from the bottom of the screen.

1. From the left navigation panel, select **Workbooks**. Read the description of the Microsoft Sentinel workbook.  Workbooks can be added through the Content hub.Any workbooks previously installed would be listed here. Select **Go to content hub**.  The content hub lists content that includes workbooks either as part of a solution or as a standalone workbook. Scroll down to see the available options.

1. Close the window by selecting the **X** on the top-right corner of the window.

1. From the top left corner of the window, just below the blue bar, select **Home** to return to the home page of the Azure portal.  

### Review

In this demo you walked through the steps for connecting Microsoft Sentinel to data sources, you set up a workbook, and walked several options available in Microsoft Sentinel.
