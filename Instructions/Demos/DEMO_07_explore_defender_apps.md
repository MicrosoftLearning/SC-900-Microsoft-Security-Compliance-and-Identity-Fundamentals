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

In this demo, you will show the capabilities of Microsoft Defender for Cloud Apps.  You will walk the learner through information available on the Cloud discovery dashboard, the Cloud app catalog, capabilities available to investigate findings with the Activity log and Files, and ways to control impact to your organization through Policies.  Note:  An organization must have a license to use Microsoft Defender for Cloud Apps which is a user-based subscription service.  

### Demo Part 1: Explore Cloud discovery

1. Open Microsoft Edge. In the address bar enter **admin.microsoft.com**.  You should already be signed in as the admin.  If not, sign in with your admin credentials.

1. From the left navigation pane of the Microsoft 365 admin center, select **Show all**.  Speak to the point that the different Microsoft 365 admin centers can be accessed from here.

1. Under Admin centers, select **Security**.  A new browser page opens to the welcome page of the Microsoft 365 Defender portal.  

1. If this is the first time you visit the Microsoft 365 Defender portal, you may get a pop-up window to take a quick tour.  Close this.

1. From the left navigation panel, select **Cloud apps** to expand the list then select **Cloud Discovery**. This takes you to the Dashboard view.  Speak to the different tiles available on the dashboard.

1. From the dashboard view, you can select different tabs from the top of the page.  Go through each tab on the top of the page.
    
    1. Select **Discovered apps**. The discovered apps window provides a more detailed view of the discovered apps, including risk score, traffic, number of users and more. 

        1. From any item on the list, select the **ellipses** in the actions’ column of the table.  Note the various options available, including the ability to tag an app as sanctioned or unsanctioned.  Select the ellipses, again, to close the actions box.
        
        1. Selecting a specific line item opens a details page for the specific app.  Select an item from the list.  For the selected item, select the **Cloud app usage** tab to see more detailed information, including  **Usage**, **Users, IP**, **Addresses**, and **Alerts**. When you are done exploring the details page, return to discovered apps page, by selecting **Cloud Discovery** from the bread crumb on the top of the page.  If you select Cloud discovery from the left navigation panel, it will take you back to the dashboard view.
        
    1. From the top of the page, select the **IP addresses** tab.  Here you will find data including number of transactions, amount of traffic and upload amounts, by IP address.  Note that you can also filter by specific IP address or export the data for further analysis.
        
    1. From the top of the page select **Users**.  This is the same type of information provided when you select IP addresses, but instead it is listed for individual users.  Here again, you filter by specific user and export data for further analysis.

1. The information provided in these tabs is based on either snap-shot reports from traffic logs you manually upload from your firewalls and proxies or from continuous reports that analyze all logs that are forwarded from your network using Cloud App Security.  To see where this is setup, select **Actions** on the top-right corner of the page.

    1. Select the first option, **Create Cloud Discovery snapshot report**. Here you would fill in the requested details and upload traffic logs to generate and upload a report.  Select **Quit**.  The data you are seeing for your lab tenant came from a Snapshot report, you can see this information on the top right corner of the screen.

    1. To see the option for continuous reports, select the **Actions** on the top-right corner of the page and from the drop-down select **Configure automatic upload**.  There are no data sources connected, but this is where you would add a data source. Select **Add a data source** then select the drop-down arrow in the **Select appliance** field to see the types of appliances that you can connect as a data source.  Select **Cancel** to exit then select the back-arrow key for the browser to return to Cloud discovery page.

1. Another point to call out is that you can connect to apps directly by setting up app connectors that will provide you with greater visibility and control over your cloud apps. From the top right corner of the screen, select **Actions** then select **Cloud Discovery Settings**.  From the left side of the screen, under Connected apps, select select **App connectors**.  

    1. On the Connected apps page, you should see Office 365 on the list with a connected status.  If Office 365 is showing a connection error, it is most likely because Audit is not turned on.  If audit is enabled, go to the ellipses and edit settings to reconnect.

    1. Select **+ Connect an app** and from the drop-down list select **Microsoft Azure**.  From the Microsoft Azure pop-up window, select **Connect Microsoft Azure**.  You will see a connected status (you may need to refresh the screen) and information on scanning users, data, and activities.  Return to the Cloud Discovery dashboard, by selecting **Cloud Discovery** from the left-most navigation panel.

1. Keep this page open, as you will use it in the next task.

### Demo Part 2 - Explore the Cloud app catalog

1. From the left navigation panel, select **Cloud app catalog**.

1. The Cloud App Catalog gives a full picture of what Cloud Discovery identifies. Cloud Discovery analyzes your traffic logs against the Microsoft Defender for Cloud Apps cloud app catalog of over 25,000 cloud apps. The apps are ranked and scored based on more than 80 risk factors to provide you with ongoing visibility into cloud use, Shadow IT, and the risk Shadow IT poses to your organization.

1. The Cloud app catalog enables you to wisely choose which apps fit your organization's security requirements. Admins can do basic filtering of apps as shown on the top of the page, which include whether the app is sanctioned, unsanctioned, or has no tag , risk score, Compliance risk factor, and security risk factor.  Select **Compliance risk factor** to view the available options.  Note that there is an option to use advanced filters.

1. Admins can also search for apps by category.  For example, in the search category field enter **Social network**, then select social network.  Select **Yammer** to view the a detailed view.  Hovering your mouse over any topics for a given category will show an information icon that you can select to get more information about that topic.
 
1. Keep this page open, as you will use it in the next task.

### Demo Part 3 - Explore the Activity log and Files

1. From the left navigation panel, select **Activity Log**.  Here you get visibility into all the activities from your connected apps.   Since you already had the Office 365 connector connected you should be able to see some data. After you connect Cloud App Security to an app using the App connector, Cloud App Security scans all the activities that happened - the retroactive scan time period differs per app - and then it's updated constantly with new activities.  

1. Notice on the top of the page, the option to add a new policy from the search or to export the data for further analysis.  Select **+ New policy from search**.  Note how you can create a policy based on a template, select a policy severity & category, create filters for the policy, create alerts, and even send the alerts to Power Automate.  Select **Cancel** to exit of the policy creation window.

1. From the left navigation pane, select and explore the **Files** option and note the options to filter data by app, owner, access level, file type, and matched policy. Also, note the option to create a new policy from search and export of the data.

1. Keep this page open, as you will use it in the next task.

### Demo Part 4 - Explore policies

1. From the left navigation panel, select **Policies** then select **Policy management**.  The listed policies provide information on the number of alerts generated by the policy, severity, etc. Selecting any line item provides more detailed information about the policy. Select an item from the list, i.e., **Risky sign-in**.

    1. Note that you can also create a policy. Select **+ Create policy** to view the types of policies you can create.  Select **Activity policy** to view the different options available for creating the policy.  Select **Cancel** to exit out of the configuration window.
    
    1. Note that you can also have the option to export policy information.

1. From the left navigation panel, select **Policy templates**. To create a policy from one the available templates, select the **+** on the left side of the template line item.  View the different configuration options for the policy.  Select **Cancel** to exit out of the page.

1. Close the browser window.

### Review

In this demo, you showed the capabilities of Microsoft Defender for Cloud Apps.  You showed the information available on the Cloud discovery dashboard, the Cloud app catalog, capabilities available to investigate findings with the Activity log and Files, and ways to control impact to your organization through Policies
