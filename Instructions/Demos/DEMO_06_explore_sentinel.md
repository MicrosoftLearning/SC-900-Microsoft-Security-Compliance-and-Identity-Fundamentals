---
Demo:
    title: 'Azure Sentinel'
    module: 'Module 3 Lesson 3: Describe the capabilities of Microsoft security solutions: Describe security capabilities of Azure Sentinel'
---


# Demo: Azure Sentinel 

### Demo scenario
In this demo you will walk through the process of creating an Azure Sentinel instance.  You will also set up the permissions to ensure access to the resources that will get deployed to support Azure Sentinel.  Once this basic setup is done you will walk through the steps for connecting Sentinel to your data sources, using built-in analytics to get notified of anything suspicious, and lastly you will explore the automation capability.  

#### Demo Part 1:  Create an Azure Sentinel instance

1. Open the browser tab, **Home-Microsoft Azure**.  If you previously closed the tab, open a browser page and in the address bar, enter portal.azure.com and sign back in.

1. In the search box, in the blue bar on the top of the page next to where it says Microsoft Azure, enter **sentinel** then select **Azure Sentinel** from the search results.

1. From the Azure Sentinel page, select **Create Azure Sentinel**.

1. From the Add Azure Sentinel to a workspace page, select **Create a new workspace**.

1. From the basics tab of the Create Log Analytics workspace, enter the following:
    1. Subscription:  **Azure Pass – Sponsorship**
    1. Resource group: select **Create New**, then enter the name **SC900-Sentinel-RG** then select **OK**.
    1. Name: **SC900-LogAnalytics-workspace**.
    1. Region: **East US** (leave this default)
    1. Select **Next: Pricing tier >**

1. For the Pricing Tier, leave the default settings: **Pay-as-you-go (per GB 2018)**, then select **Next: Tags >**.

1. For the Tags, you can leave this blank, then select **Review + Create**.

1. Verify the information you entered then select **Create**.

1. It may take a minute or two for the ne workspace to be listed, if you still don't see it, select **Refresh**, then select **Add**.

1. Once the new workspace is added, the Azure Sentinel | News & guides page will display.  Note the three steps listed on the Get started page.

1. Keep this page open, as you will use it in the next task.

#### Demo Part 2:  With the Azure Sentinel instance created, you will want to make sure that you have the necessary access to the resources that get deployed to support Azure Sentinel.  In this task you will go to the access control (IAM) page for the resource group that you created with the instance of Azure Sentinel, view the available roles, and assign yourself (MOD administrator) the required role. Assigning the role at the resource group level will ensure the role will apply to all the resources that are deployed to support Azure Sentinel.

1. In the search box, in the blue bar on the top of the page next to where it says Microsoft Azure, enter **resource groups** then select **Resource groups** from the search results.

1. From the Resource groups page, select the resource group that you created with Azure Sentinel, **SC900-Sentinel-RG**.

1. From the SC900-Sentinel-RG page, select **Access control (IAM)** from the left navigation panel.

1. From the Access control page, select **View my access**.  Note the current role is Service administrator.  Close the MOD Administrator assignments window by selecting the **X** on the top-right corner of the window.

1. From the Access control page, select **+Add**, then select **Add role assignment**.

1. The Add role assignment window opens.  Select the drop-down arrow in the Select a role field to display the available roles. In the select a role search box, enter **sentinel** to view the 4 roles associated with Sentinel. As a best practice you should assign the least privilege required for the role.  For this convenience of this lab, enter **Owner** in the searchbox and select **Owner** from the results. .

1. From the list of users displayed, select **MOD Administrator**.

1. Select **Save** at the bottom of the page.

1. From the access control page, select **View my access** to confirm the role has been added, then close the window by select the **X** on the top-right corner of the window.

#### Demo Part 3:  In this part of the demo you will walk through the process of connecting Azure Sentinel to your data source to begin to collect data.  Note: it can take a bit time to show the connected status of a connector (~30 minutes, depending on the tenant).

1. In the search box, in the blue bar on the top of the page next to where it says Microsoft Azure, enter **sentinel** then select **Azure Sentinel** from the search results.

1. From the Azure Sentinel page, select the workspace you created with the instance of Azure Sentinel, **SC900-LogAnalytics-workspace**.

1. The first step with Azure Sentinel is to be able to collect data. From the left navigation panel select **Data connectors**, listed under configuration.

1. From the Data connectors page, scroll down on the main window to view the extensive list of available connectors. In the Search box of the data connectors page, enter **Azure** then from the list select **Azure Active Directory**.

1. The Azure Active Directory connector window opens.  Select **Open connector page**.

1. From the Azure Active Directory connector page, review the description and note the related content which includes workbooks, queries, and Analytic rules templates.  

1. The instructions tab in the main window, provides the perquisites for Azure Sentinel to integrate with Azure Active Directory.   Under configuration, select **Sign-in logs** then select Apply Changes (multiple connectors can be chosen).  Note: it can take some time before you see the connected status for the connector (~30 minutes or so).  As a reference:
    1. Review permissions in Azure Sentinel:  https://docs.microsoft.com/en-us/azure/sentinel/roles
    1. Connect to Azure Active Directory:  https://docs.microsoft.com/en-us/azure/sentinel/connect-azure-active-directory

1. From the Next steps tab, note the list of recommended workbooks.   Under recommended workbooks, select **Azure Sign-in logs** (additional workbooks can be chosen).

1. From the workbooks page and with the templates tab selected (underlined), select **Azure Sign-in logs**.

1. From the Azure AD Sign-in logs window that opens, review the description, and select **View template**.  Exit out of the template, by selecting the **X** on the top-right corner of the screen.  Select **Save** from the bottom of the page, then select **OK** to save the workbook to the default location.

1. From the top-left corner of the Workbooks page, above where it says Workbooks, select **Azure Sentinel**. This returns you to the Azure Sentinel Data Connectors page.

1. The top of the Data connectors page should display 1 connected, to reflect that you are now connected to Azure Active Directory.

1. From the left navigation panel, select **Workbooks**.

1. From the Workbooks page, select the **My workbooks** tab, which is above the search box.  The workbook you just saved is listed and available for you to view and monitor your data.  Subsequent logins will be reflected in the workbook, so you may choose to show this.

1. Keep this page open, as you will use it in the next task.

#### Demo Part 4 (Optional):  In this part of the demo you will walk through the process of using a built-in analytics rule template to create a rule to get notified when something suspicious occurs.

1. From the left navigation panel, select **Analytics**.

1. The Analytics page will show active rules (Advanced multistage attack detection is enabled by default) and will also provide access to Rule templates.  Select the **Rule templates** tab.  Notice the list of available templates and the different ways to filter the list.  Using built-in analytics alerts within the Azure Sentinel workspace, you’ll get notified when anything suspicious occurs.

1. In the Search bar, enter **Azure Portal**.  Select **Failed login attempts to Azure Portal**.  

1. From the window that opens, read the description and review the information associated with the template.  Select **Create rule** on the bottom of the page.
    1. From the Analytics rule wizard, review the information, then select **Next: Set rule logic >**.
    1. The Set rule logic page, is where you define the logic for your new analytics rule. The template already provides some logic and predefined settings.  Scroll through the page to see the available settings.  Leave the defaults. Select **Next: Incident settings (preview)>**.
    1. With Incident settings, Azure Sentinel alerts can be grouped together into an Incident that should be looked into. You can set whether the alerts that are triggered by this analytics rule should generate incidents.  Leave the default settings and select **Next: Automated response >**.
    1. In the Automated response tab, note how you can add a playbook to automate the response.  Similarly, you can create an incident automation rule.  Select **+ Add** new under incident automation.  A window to create a new automation rule opens.  Any automation rule you create on this page is triggered by the analytics rule you are c   Note that you can add conditions and set actions for the rule.   Select **Cancel** to exit out of the window.
    1. Select **Next: Review>** to review all the details associated with the rule and based on the chosen template. At this point, you can choose to create the rule, by selecting **Create** or exit without creating the rule by selecting **X** on the top-right corner of the page.

1. Keep this page open, as you will use it in the next task.

#### Demo Step 5 (Optional):  In the previous step you created an analytics rule to be alerted of suspicious activities.  Embedded in that wizard is the option to automate the response to an incident based on the specific rule.  But you can also create automation rules by going directly to the automation configuration option.

1. From the left navigation panel, select **Automation**.  

1. Select **+ Create**. From the drop-down note how you can select either to add a new playbook or add a new rule.  Select **Add new rule**.  
    1. A window to create a new automation rule opens.  Note that you can add conditions and set actions for the rule.  The only distinction is that the first condition is to associate the analytics rule(s) to which you want to apply this automation rule.  This is was greyed out in the previous task because the automation was being configured for the specific rule.  Select **Cancel** to exit out the Create new automation rule window.

1. Keep this page open, as you will use it in the next task.

#### Step 6: TEAR DOWN - Instructor do this step after class. Delete Azure Sentinel Resource group.  Azure Sentinel is billed based on the volume of data ingested for analysis in Azure Sentinel. Although the amount of data ingested as a result of this lab is minimal, it is recommended that you delete the Azure Sentinel resource group when you are done exploring the features of capabilities of Azure Sentinel.

1. From the Azure Sentinel page, on the top-left corner of the page, above where is says Azure Sentinel, select **All Services**.

1. In the filter services box, enter resource groups, then from the list provided select **Resource groups**.

1. From the Resource groups page, select the resource group that you created with Azure Sentinel, **SC900-Sentinel-RG**.

1. From the top center of the page, select **Delete resource group**.  Review the warning.  Enter the resource group name, **SC900-Sentinel-RG**, then select **Delete** from teh bottom of the page.  It will take several minutes to delete the resource group.

1. Once you have verified the resource group was deleted, close the browser page. 

#### Review

In this demo you showed the process of creating an Azure Sentinel instance.  You showed how to set up the permissions to ensure access to the resources associated with your instance of Azure Sentinel.  With the Azure Sentinel instance created, you walked through the steps for connecting Sentinel to data sources, how to use built-in analytics rules to get notified of anything suspicious, and lastly you explored the automation capability. You concluded the demo by deleting the resource group associated with the instance of Azure Sentinel that you created.