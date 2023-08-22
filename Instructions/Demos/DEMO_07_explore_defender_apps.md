<!---
---
Demo:
    Title: Microsoft Defender for Cloud Apps '
    Module: 'Learning Path: Describe the capabilities of Microsoft security solutions; Module 4: Describe the threat protection capabilities of Microsoft 365; Unit 5: Describe Microsoft Defender for Cloud Apps'
---
--->

# Demo: Microsoft Defender for Cloud Apps

This demo maps to the following Learn content:

- Learning Path: Describe the capabilities of Microsoft security solutions
- Module: Describe the threat protection capabilities of Microsoft 365
- Unit: Describe Microsoft Defender for Cloud Apps

## Demo scenario

In this demo, you'll show the capabilities of Microsoft Defender for Cloud Apps.  You'll walk the learner through information available on the Cloud discovery dashboard, the Cloud app catalog, capabilities available to investigate findings with the Activity log and Files, and ways to control impact to your organization through Policies.  Note:  An organization must have a license to use Microsoft Defender for Cloud Apps that is a user-based subscription service.  

### Demo Part 1: Explore Cloud discovery

1. In the address bar, enter **admin.microsoft.com**. Sign in with the admin credentials for the Microsoft 365 tenant provided by your authorized lab hoster (ALH), to access the Microsoft 365 admin center.

1. From the left navigation pane of the Microsoft 365 admin center, select **Show all**.

1. Under Admin centers, select **Security**.  A new browser page opens to the welcome page of the Microsoft 365 Defender portal.  

1. If this is the first time you visit the Microsoft 365 Defender portal, you may get a pop-up window to take a quick tour.

1. From the left navigation panel, select **Cloud apps** to expand the list then select **Cloud Discovery**. This takes you to the Dashboard view.  Speak to the information available on the dashboard. From the dashboard view, you can select different tabs from the top of the page.  Go through each tab on the top of the page.

1. Select **Discovered apps**. The discovered apps window provides a more detailed view of the discovered apps, including risk score, traffic, number of users and more.
    1. From any item on the list, select the **ellipses** in the actions’ column of the table.  Note the various options available, including the ability to tag an app as sanctioned or unsanctioned.  Select the ellipses, again, to close the actions box.
    1. Selecting a specific line item opens a details page for the specific app.  Select an item from the list.  For the selected item, select the **Cloud app usage** tab to see more detailed information, including  **Usage**, **Users, IP**, **Addresses**, and **Alerts**. When you're done exploring the details page, return to discovered apps page, by selecting **Cloud Discovery** from the bread crumb on the top of the page.  If you select Cloud discovery from the left navigation panel, it will take you back to the dashboard view.
    1. From the top of the page, select the **IP addresses** tab.  Here you'll find data including number of transactions, amount of traffic and upload amounts, by IP address.  Note that you can also filter by specific IP address or export the data for further analysis.
    1. From the top of the page, select **Users**.  This is the same type of information provided when you select IP addresses, but instead it's listed for individual users.  Here again, you filter by specific user and export data for further analysis.

1. An important point to call out is that the information provided in the Cloud Discovery page and the related tabs are based on either snap-shot reports from traffic logs you manually upload from your firewalls and proxies or from continuous reports that analyze all logs that are forwarded from your network using Cloud App Security.  To see where this is set up, select **Actions** on the top-right corner of the page.
    1. Select the first option, **Create Cloud Discovery snapshot report** then select **Next**. Here you would fill in the requested details and upload traffic logs to generate and upload a report.  Select **Quit** and if prompted with Are you sure, select **Quit** again.  The data you're seeing for your lab tenant came from a Snapshot report, you can see this information on the top of the Cloud Discovery window.
    1. To see the option for continuous reports, select the **Actions** on the top-right corner of the page and from the drop-down select **Configure automatic upload**.  There are no data sources connected, but this is where you would add a data source. Select **Add a data source** then select the drop-down arrow in the **Select appliance** field to see the types of appliances that you can connect as a data source.  Select **Cancel** to exit.
    1. From the left navigation panel, select **Cloud discovery** to return to Cloud discovery page.

1. With Microsoft 365 Defender for Cloud apps, you can connect to apps directly by setting up app connectors that will provide you with greater visibility and control over your cloud apps. From the top right corner of the screen, select **Actions** then select **Cloud Discovery Settings**.  Note the available settings.
    1. From the left navigation panel of the Cloud apps settings window, select **App connectors** (you may need to scroll down).
    1. The App connectors page is where you would see any app connectors already setup and where you can add an app connector.
    1. You should see Microsoft 365 listed. If it's showing a connection error, go to the vertical ellipses on the right side of the line item, and select **edit settings**.  To reconnect, select **Connect Office 365** on the bottom of the page. The page should now show that Office 365 is connected, select **Done**.  The status will now show with a yellow warning sign, indicating there is no recent status.  It will take some time for status to update as the retroactive scan time period differs per app, and lab tenants may experience longer than normal delays.
    1. To set up a new app connector.  Select **+Connect an app**.  The drop-down list shows a list to choose from.  You may also want to call out that the list includes the option to **Suggest more apps**.  
    1. Optionally, you may want to add the Microsoft Azure connector. From the drop-down list select **Microsoft Azure**.  From the Microsoft Azure pop-up window, select **Connect Microsoft Azure** then select **Done**.  You'll see a connected status (if you don't see it, refresh the browser) and information on scanning users, data, and activities.  

1. While on the Cloud apps settings page, it's worth spending a few minutes also exploring some of the other Cloud Discovery settings.  
    1. Select **Conditional Access App Control apps** and note the description, "The Conditional Access App Control adds real-time monitoring and control capabilities for your apps."
    1. Select Microsoft Information Protection, speak to the available settings.
    1. Explore others at will. Call out the level of integration and flexibility.

1. Return to the Cloud Discovery dashboard, by selecting **Cloud Discovery** from the left-most navigation panel.

1. Keep this page open, as you'll use it in the next part.

### Demo Part 2 - Explore the Cloud app catalog

In this part of the demo, you'll show the capabilities of the Cloud app catalog. Cloud Discovery analyzes your traffic logs against the Microsoft Defender for Cloud Apps cloud app catalog of over 31,000 cloud apps. The apps are ranked and scored based on more than 80 risk factors to provide you with ongoing visibility into cloud use, Shadow IT, and the risk Shadow IT poses to your organization.  

1. From the left navigation panel, select **Cloud app catalog**.

1. The Cloud app catalog enables you to choose apps that fit your organization's security requirements. Admins can do basic filtering of apps as shown on the top of the page, which includes whether the app is sanctioned, unsanctioned, or has no tag, risk score, Compliance risk factor, and security risk factor.  For example, filtering by compliance risk factor lets you search for a specific standards, certification, and compliance that the app may comply with. Examples include HIPAA, ISO 27001, SOC 2, and PCI-DSS. Select **Compliance risk factor** to view the available options.  You can further filter by risk score, by moving the sliders on the risk score on the top of the page. If you moved the slide, be sure to set it so the range is set at 0 to 10.

1. Admins can also search for apps by category.  For example, in the search for category field enter **Social network**, then select **Social network**.  Select any item from the list for a detailed view.  Hovering your mouse over any topics for a given category will show an information icon that you can select to get more information about that topic.

1. Keep this page open, as you'll use it in the next task.

### Demo Part 3 - Explore the Activity log and Files

Explore ways in which you can investigate the recorded activities with the activity log and files.

1. From the left navigation panel, select **Activity Log**. Here you get visibility into all the activities from your connected apps. You may not see any data listed as it can take several hours to perform retroactive scans once audit is enabled and lab tenants may experience longer than normal delays. Note the available filter options and the option to create new a policy from search.

1. To provide data protection, Microsoft Defender for Cloud Apps gives you visibility into all the files from your connected apps, for example all the files stored in SharePoint and Salesforce. From the left navigation pane, select and explore the **Files** option.
    1. The ability to scan files must be enabled as part of the Information protection settings of Microsoft 365 Cloud apps.  Select **Enable file monitoring** and select the box next to where it says **Enable file monitoring** then select **Save**.  
    1. Return to files by selecting **Files**, listed under cloud apps, from the left navigation panel. You may not see anything listed because it can take several days before you can see your files but its worth calling out that once files are listed you can filter data by app, owner, access level, file type, and matched policy. Also, you create a new policy from search and export of the data.

1. Keep this page open, as you'll use it in the next task.

### Demo Part 4 - Explore policies

In this part, you'll show the options available for policies in Microsoft Defender for Cloud Apps.

1. From the left navigation panel, select **Policies**.
    1. Select **Policy management**.  The listed policies provide information on the number of alerts generated by the policy, severity, etc. Selecting any line item provides more detailed information about the policy. Select an item from the list, to view detailed information about the policy.  Speak to some of the options then select **Cancel**.
    2. Note that you can also create a policy. Select **+ Create policy** to view the types of policies you can create.  Select **Activity policy** to view the different options available for creating the policy.  Select **Cancel** to exit out of the configuration window.
    3. Note that you can also have the option to export policy information.

1. From the left navigation panel, select **Policy templates**. To create a policy from one the available templates, select the **+** on the right side of the template line item.  View the different configuration options for the policy.  Select **Cancel** to exit out of the page.

1. From the left navigation panel, select **Home** to return to the home page for Microsoft 365 Defender.

1. Keep the browser tab open if you plan to continue with the next demo.

### Review

In this demo, you showed the capabilities of Microsoft Defender for Cloud Apps.  You showed the information available on the Cloud discovery dashboard, the Cloud app catalog, capabilities available to investigate findings with the Activity log and Files, and ways to control impact to your organization through Policies
