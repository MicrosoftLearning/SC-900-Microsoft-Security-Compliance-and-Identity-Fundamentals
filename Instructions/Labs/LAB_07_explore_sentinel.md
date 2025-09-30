---
lab:
    title: 'Explore Microsoft Sentinel'
    module: 'Describe the security capabilities of Microsoft Sentinel'
---

# Lab: Explore Microsoft Sentinel

This lab maps to the following Learn content:

- Learning Path: Describe the capabilities of Microsoft security solutions
- Module: Describe the security capabilities of Microsoft Sentinel
- Unit: Describe threat detection and mitigation capabilities in Microsoft Sentinel

## Lab scenario

In this lab, you'll walk through the process of creating a Microsoft Sentinel instance.  You'll also set up the permissions to ensure access to the resources that will get deployed to support Microsoft Sentinel.  Once this basic setup is done you'll walk through the steps for connecting Microsoft Sentinel to your data sources, set up a workbook, and do a brief walk-through of some of key capabilities available in Microsoft Sentinel.

**Estimated Time**: 60 minutes

### Task 1

To create an instance of Microsoft Sentinel, you first have to create a Log Analytics workspace, used to store data from Microsoft Sentinel.  Once you have a Log Analytics workspace you can create an instance Microsoft Sentinel and add the log analytics workspace to it.  In this task you run through each of these steps.

1. You should be at the home page for Azure services.  If not, open Microsoft Edge and in the address bar, enter **portal.azure.com**, and sign in with your Azure Portal admin credentials.

1. In the blue search box on the top of the page, enter **Log Analytics** and select it from the search results.
1. Select **+ Create**.
1. From the basics tab of the Create Log Analytics workspace, enter the following:
    1. Subscription: leave the default, this is the Azure subscription provided by the Authorized Lab Hoster (ALH).
    1. Resource group: select **SC900-Sentinel-RG**. If this resource group is not listed create it by selecting **Create new**, enter **SC900-Sentinel-RG**, then select **OK**.
    1. Name: **SC900-Sentinel-workspace**.
    1. Region: **East US** (A different default region may be selected based on your location)
    1. Select **Review + Create** (no tags will be configured).
    1. Verify the information you entered then select **Create**.
    1. It may take a minute or two for the new workspace to be created.
    1. Once it's created, select **Go to resource** to view information about the workspace.
1. At this point, the instance of Microsoft Sentinel has not yet been created. To create an instance of Sentinel, you need to go to the Microsoft Sentinel page. Use the blue search bar at the top of the page, to search for **Microsoft Sentinel** and select it from the search result.
1. To add the workspace to Microsoft Sentinel, you need to go to the Microsoft Sentinel page. Use the blue search bar at the top of the page, to search for **Microsoft Sentinel**
    1. From the Microsoft Sentinel page, select **+ Create**.
    1. Now you can add the workspace you just created. Select **SC900-Sentinel-workspace**, then select **Add**.  This may take a few minutes, as the free trial of Microsoft Sentinel activates.  Once it is activated, you select **Ok**.
1. Keep this page open, as you'll use it in the next task.

### Task 2

With the Microsoft Sentinel instance created and the Log Analytics workspace assigned to it, it's important that users that will have responsibility to support Microsoft Sentinel have the necessary permissions.  This is done by assigning the designated user the required role permissions.  In this task, you'll view the available, built-in Microsoft Sentinel roles.

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

1. From the Azure services home page, select Microsoft Sentinel, then select the instance you created, **SC900-Sentinel-workspace**.

1. From the left navigation panel, expand **Content Management** then select **Content hub**.

1. Take a moment to scroll down to see the long list of available solutions and the options to filter the list.  For this task, your're looking for **Microsoft Defender for Cloud**.  Select it from the list.  In the side window that opens, read the description then select **Install**.  Once the installation is completed, the status column in the main window will show as installed.

1. Once again, select **Microsoft Defender for Cloud** from the list. From the window on the right, select **Manage**.

1. On the right side of the the Microsoft Defender for Cloud page is the description and notes associated with the solution from Content Hub and what is included as part of this solution.  On the main window are the components of the solution.  In this case there are two data connectors and one data rule. The orange triangle indicates that some configuration is needed. Select the box next to where it says **Subscription-based Microsoft Defender for Cloud (Legacy)**.  A window opens on the right side of the page.  Select **Open connector page**.

1. Note the configuration instructions.  Select the box next to the name of the subscription then select **Connect**.  A pop-op window may appear indicating that only subscriptions you have Security Reader permissions on will start streaming Microsoft Defender for Cloud alerts.  Select **OK**.  The status will move to connected.  The connector is now enabled, although it may take some time for the connector to show up in the data connectors page.  

1. Now view information about the analytics rule.  From the top of the page (in the breadcrumb) select **Microsoft Defender for Cloud**. De-select the box next to where it says Microsoft Defender for Cloud, as you have already configured the connector (it may take some time for the warning icon to disappear). Select the box next to where it says, **Detect CoreBackUp Deletion Activity from related security alerts**.  This brings up the Analytics Rules page.  Again, select the **Detect CoreBackUp Deletion Activity from related security alerts** rule. A window that opens on the right, that provides information about the rule and what it does.  Select **Create rule**.  
    1. Although the details of the rule logic are beyond the scope of the fundamentals, go through each tab in the rule creation to view the type of information that can be configured
    1. When you reach the Review + create tab, select **Save**.

1. Return to the Sentinel page by selecting **Microsoft Sentinel | Content hub** from the bread-crumb at the top of the page, above where it says Analytics rules.

1. Keep this page open, as you'll use it in the next task.


### Task 4

In this task, you'll walk through some of the options available in Sentinel.

1. From the left navigation panel, expand **Threat management** and explore the options listed in threat management.
    1. Select **Incidents**.  Although no incidents are found, review the **What is it?** section.
    1. Select **Hunting** then review the information provided in the **Hunts (Preview)** tab.
    1. Select **Notebooks** and review the the **What is it?** section.
    1. Select **Threat intelligence** and review the information on the page.
    1. Select **MITRE ATT&CK**.  MITRE ATT&CK is a publicly accessible knowledge base of tactics and techniques that are commonly used by attackers. With Microsoft Sentinel you can view the detections already active in your workspace, and those available for you to configure, to understand your organization's security coverage, based on the tactics and techniques from the MITRE ATT&CK® framework.  Select any cell from the matrix and note the information available on the right side of the screen. **Note**: You may need to select the "**<<**" at the far-right side of the window to see the information panel.

1. From the left navigation panel, expand **Content Management**, then select **Community**. The community page includes Cybersecurity insights and updates from Microsoft Research, a link to a list of Microsoft Sentinel Blogs, a link to Microsoft Sentinel Forums, links the the latest editions to the Microsoft Sentinel Hub, and more. Explore this at will.


1. From the left navigation panel, expand **Configuration** and explore the options listed:
    1. select **Analytics**.  There should be two active rules, one that is available by default and the rule you created in the previous task. Select the default rule **Advanced Multistage Attack Detection**.  Review the detailed information. **Note**: You may need to select the "**<<**" at the far-right side of the window to see the information panel.
    1. From the left navigation panel, select **Automation**.  Here you can create simple automation rules, integrate with existing playbooks, or create new playbooks.  Select **+ Create** then select **Automation rule**.  Note the window that opens on the right side of the screen and the options available to create conditions and actions.  Select **Cancel** from the bottom of the screen.

1. Close the window by selecting the **X** on the top-right corner of the window.

1. From the top left corner of the window, in the blue banner, select **Microsoft Azure** to return to the home page of the Azure portal.

1. Sign out and close all the open browser tabs.

### Review

In this lab you walked through the steps for connecting Microsoft Sentinel to data sources, you set up a workbook, and walked several options available in Microsoft Sentinel.
