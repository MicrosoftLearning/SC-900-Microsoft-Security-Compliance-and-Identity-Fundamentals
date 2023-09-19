<!---
---
Lab:
    Title: 'Explore Microsoft Defender for Cloud Apps '
    Module: 'Learning Path: Describe the capabilities of Microsoft security solutions; Module 4: Describe the threat protection capabilities of Microsoft 365; Unit 5: Describe Microsoft Defender for Cloud Apps'
---
--->

# Lab: Explore Microsoft Defender for Cloud Apps

This lab maps to the following Learn content:

- Learning Path: Describe the capabilities of Microsoft security solutions
- Module: Describe the threat protection capabilities of Microsoft 365
- Unit: Describe Microsoft Defender for Cloud Apps

## Lab scenario

In this lab, you'll explore the capabilities of Microsoft Defender for Cloud Apps.  You'll walk through the information available on the Cloud Discovery dashboard, the Cloud app catalog, capabilities available to investigate findings, and ways to control impact to your organization through policies. Note:  An organization must have a license to use Microsoft Defender for Cloud Apps that is a user-based subscription service.

**Estimated Time**: 15-20 minutes

### Task 1 - Explore Cloud discovery

Explore Cloud Discovery.

1. Open Microsoft Edge. In the address bar, enter **admin.microsoft.com**.

1. Sign in with your admin credentials for the Microsoft 365 tenant.
    1. In the Sign in window, enter **admin@WWLxZZZZZZ.onmicrosoft.com** (where ZZZZZZ is your unique tenant ID provided by your lab hosting provider) then select **Next**.
    1. Enter the admin password that should be provided by your lab hosting provider. Select **Sign in**.
    1. When prompted to stay signed- in, select **Yes**. This takes you to the Microsoft 365 admin center page.

1. From the left navigation pane of the Microsoft 365 admin center, select **Show all**.

1. Under Admin centers, select **Security**.  A new browser page opens to the welcome page of the Microsoft 365 Defender portal.  

1. If this is the first time you visit the Microsoft 365 Defender portal, you may get a pop-up window to take a quick tour.  Close this.

1. From the left navigation panel, select **Cloud apps** to expand the list then select **Cloud Discovery**. This takes you to the Dashboard view.  Note the information available on the dashboard. From the dashboard view, you can select different tabs from the top of the page.  

1. Select **Discovered apps**. The discovered apps window provides a more detailed view of the discovered apps, including risk score, traffic, number of users and more.
    1. From any item on the list, select the **ellipses** in the actions’ column of the table.  Note the various options available, including the ability to tag an app as sanctioned or unsanctioned.  Select the **ellipses**, again, to close the actions box.
    1. Selecting a specific line item opens a details page for the specific app.  Select an item from the list and review the information available on the overview page.  For the selected item, select the **Cloud app usage** tab to see more detailed information, including  **Usage**, **Users, IP**, **Addresses**, and **Alerts**. When you're done exploring the details page, return to discovered apps page, by selecting **Cloud Discovery** from the bread crumb on the top of the page.  If you select Cloud discovery from the left navigation panel, it will take you back to the dashboard view.
    1. From the top of the page, select the **IP addresses** tab.  Here you'll find data including number of transactions, amount of traffic and upload amounts, by IP address.  Note that you can also filter by specific IP address or export the data for further analysis.
    1. From the top of the page select **Users**.  This is the same type of information provided when you select IP addresses, but instead it's listed for individual users.  Here again, you filter by specific user and export data for further analysis.

1. The information provided in the Cloud Discovery page and the related tabs are based on either snap-shot reports from traffic logs you manually upload from your firewalls and proxies or from continuous reports that analyze all logs that are forwarded from your network using Cloud App Security.  To see where this is set up, select **Actions** on the top-right corner of the page.
    1. Select the first option, **Create Cloud Discovery snapshot report** then select **Next**. Here you would fill in the requested details and upload traffic logs to generate and upload a report.  Select **Quit** and if prompted with Are you sure, select **Quit** again.  The data you're seeing for your lab tenant came from a Snapshot report, you can see this information on the top of the Cloud Discovery window.
    1. To see the option for continuous reports, select the **Actions** on the top-right corner of the page and from the drop-down select **Configure automatic upload**.  There are no data sources connected, but this is where you would add a data source. Select **Add a data source** then select the drop-down arrow in the **Select appliance** field to see the types of appliances that you can connect as a data source.  Select **Cancel** to exit,
    1. From the left navigation panel, select **Cloud discovery** to return to Cloud discovery page.

1. You can connect to apps directly by setting up app connectors that will provide you with greater visibility and control over your cloud apps. From the top-right corner of the screen, select **Actions** then select **Cloud Discovery Settings**.  From the left side of the screen, under Connected apps, select **App connectors**.  

    1. On the Connected apps page, select **Office 365** from the list to view the detailed information available and then select the vertical ellipses on the right side of the screen and select **View App connector settings** to return to the App connectors page. If Office 365 is showing a connection error, it's most likely because Audit is not turned on.  If audit is enabled, go to the vertical ellipses on the right side of the line item, and select **Edit settings**.  To reconnect, select **Connect Office 365** on the bottom of the page. The page should now show that Office 365 is connected. Select **Done**.  The status will now show with a yellow warning sign, indicating there is no recent status.  It will take some time for status to update as the retroactive scan time period differs per app, and lab tenants may experience longer than normal delays.

    1. Now you'll set up a new app connector. Select **+Connect an app** and from the drop-down list select **Microsoft Azure**.  From the Microsoft Azure pop-up window, select **Connect Microsoft Azure** then select **Done**.  You'll see a connected status (if you don't see it, refresh the browser). Select **Microsoft Azure** to view the detailed information on scanning users, data, and activities.  Return to the Cloud Discovery dashboard by selecting **Cloud Discovery** under Cloud Apps from the left-most navigation panel.

1. Keep this page open, as you'll use it in the next task.

### Task 2 - Explore the Cloud app catalog

Cloud Discovery analyzes your traffic logs against the Microsoft Defender for Cloud Apps cloud app catalog of over 31,000 cloud apps. The apps are ranked and scored based on more than 80 risk factors to provide you with ongoing visibility into cloud use, Shadow IT, and the risk Shadow IT poses to your organization.  In this task, you'll explore the capabilities of the Cloud app catalog.

1. From the left navigation panel, select **Cloud app catalog**.

1. The Cloud app catalog enables you to choose apps that fit your organization's security requirements. Admins can do basic filtering of apps as shown on the top of the page, which includes whether the app is sanctioned, unsanctioned, or has no tag, risk score, Compliance risk factor, and security risk factor.  For example, filtering by compliance risk factor lets you search for a specific standards, certification, and compliance that the app may comply with. Examples include HIPAA, ISO 27001, SOC 2, and PCI-DSS. Select **Compliance risk factor** to view the available options.  You can further filter by risk score, by moving the sliders on the risk score on the top of the page. If you moved the slide, be sure to set it so the range is set at 0 to 10.

1. Admins can also search for apps by category.  For example, in the search for category field enter **Social network**, then select **Social network**.  Select any item from the list for a detailed view.  Hovering your mouse over any topics for a given category will show an information icon that you can select to get more information about that topic.

1. Keep this page open, as you'll use it in the next task.

### Task 3 - Explore the Activity log and Files

Explore ways in which you can investigate the recorded activities with the activity log and files.

1. From the left navigation panel, select **Activity Log**. Here you get visibility into all the activities from your connected apps. You may not see any data listed as it can take several hours to perform retroactive scans once audit is enabled and lab tenants may experience longer than normal delays. Note the available filter options and the option to create new a policy from search.

1. To provide data protection, Microsoft Defender for Cloud Apps gives you visibility into all the files from your connected apps, for example all the files stored in SharePoint and Salesforce. From the left navigation pane, select and explore the **Files** option.
    1. The ability to scan files must be enabled as part of the Information protection settings of Microsoft 365 Cloud apps.  Select **Enable file monitoring** and select the box next to where it says **Enable file monitoring** then select **Save**.  
    1. Return to files by selecting **Files**, listed under cloud apps, from the left navigation panel. As noted, it can take several days for files to display, once file monitoring is enabled it's worth noting that once files are listed you can filter data by app, owner, access level, file type, and matched policy. Also, you create a new policy from search and export of the data.

1. Keep this page open, as you'll use it in the next task.

### Task 4 - Explore Policies

In this task, you'll explore the policies in Microsoft Defender for Cloud Apps.

1. From the left navigation panel, select **Policies** then select **Policy management**.  The listed policies provide information on the number of alerts generated by the policy, severity, etc. Selecting any line item provides more detailed information about the policy.
    1. Note that you can also create a policy. Select **+ Create policy** to view the types of policies you can create.  Select **Activity policy** to view the different options available for creating the policy.  Select **Cancel** to exit out of the configuration window.
    1. Note that you can also have the option to export policy information.

1. From the left navigation panel, select **Policy templates**. To create a policy from one the available templates, select the **+** on the right side of a template line item.  View the different configuration options for the policy.  Select **Cancel** to exit out of the page.

1. Close the browser window.

### Review

In this lab, you explored the capabilities of Microsoft Defender for Cloud Apps.  You walked through information available on the Cloud Discovery dashboard, the Cloud app catalog, capabilities available to investigate findings, and ways to control impact to your organization through policies.
