---
lab:
    title: 'Explore Microsoft Cloud App Security '
    module: 'Module 3 Lesson 4: Describe the capabilities of Microsoft security solutions: Describe threat protection with Microsoft 365 Defender'
---


# Lab: Explore Microsoft Cloud App Security

## Lab scenario
In this lab, you will explore the capabilities of Microsoft Cloud App Security.  You will walk through the information available on the Cloud Discovery dashboard as well as capabilities available to investigate findings and control impact to your organization through policies.  Note:  An organization must have a license to use Microsoft Cloud App Security which is a user-based subscription service. 

**Estimated Time**: 00 minutes

#### Task 1: Explore Cloud Discovery.

1.	Open Microsoft Edge. In the address bar enter **admin.microsoft.com**.

1. Sign in with your admin credentials.
    1. In the Sign in window enter **admin@WWLxZZZZZZ.onmicrosoft.com** (where ZZZZZZ is your unique tenant ID provided by your lab hosting provider) then select **Next**.
    1. Enter the admin password which should be provided by your lab hosting provider. Select **Sign in**.
    1. When prompted to stay signed- in, select **Yes**. This takes you to the Microsoft 365 admin center page.

1. From the left navigation pane of the Microsoft 365 admin center, select **Show all**.

1. Under Admin centers, select **Security**.  A new browser page opens to the welcome page of the Microsoft 365 Defender portal.  

1. From the bottom of the left navigation panel of the Microsoft 365 Defender page, select **More resources**.

1. On the **Microsoft Cloud App Security** card, select **Open**.  A new browser page opens to the Cloud App Security Dashboard.  Note the information cards that are available.  It is possible you may not see any information on the cards, as this is a preconfigured lab tenant environment that has not been actively used.  

1. From the left navigation panel, select **Discover** then from the drop-down select **Cloud Discovery dashboard**.  The dashboard includes and overview of discovered apps, app categories, risk levels, and more.  
    1. From the top of the Cloud Discovery page, select the **Discovered apps** tab.  The discovered apps window provides a more detailed view of the discovered apps, including risk score, traffic, number of users and more.
        1. From any item on the list, select the **ellipses** in the actions’ column of the table.  Note the various options available, including the ability to tag an app as sanctioned or unsanctioned.  Select the ellipses, again, to close the actions box.
        1. Selecting a specific line item opens a details page for the specific app.  Select an item from the list.  For the selected item go through each tab on the top of the details page:  **Usage**, **Info, IP**, **Addresses**, **Users**, and **Alerts**. When you are done exploring the details page, return to discovered apps, by selecting **Discovered apps** from the left navigation panel.
    1. From the top of the page, select the **IP addresses** tab (this is equivalent to selecting IP addresses from the left navigation pane).  Here you will find data including number of transactions, amount of traffic and upload amounts, by IP addresses.  Note that you can also filter by specific IP address or export the data for further analysis.
    1. From the top of the page (or the left navigation pane) select **Users**.  This is the same type of information provided when you select IP addresses, but instead it is listed for individual users.  Here again, you filter by specific user and export data for further analysis.

1. The information provided in these tabs is based on either snap-shot reports from traffic logs you manually upload from your firewalls and proxies or from continuous reports that analyze all logs that are forwarded from your network using Cloud App Security.  To see where this is setup, select the **ellipses** on the top-right corner of the page.
    1. Select the first option, **Create Cloud Discovery snapshot report**. Here you would fill in the requested details and upload traffic logs to generate and upload a report.  Select **Cancel**.  The data you are seeing for your lab tenant came from a Snapshot report, you can see this information on the top right corner of the screen.
    1. To see the option for continuous reports, select the **ellipses** on the top-right corner of the page and from the drop-down select **Configure automatic upload**.  There are no data sources connected, but this is where you would add a data source. Select the **Select Appliance** drop-down arrow to see the types of appliances that you can connect as a data source.  Select **Cancel** to exit.

1. Another point to call out is that you can connect to apps directly by setting up app connectors that will provide you with greater visibility and control over your cloud apps. From the top left corner of the screen, select the **Settings cog icon** and from the drop-down list, select **App connectors**.  
    1. On the Connected apps page, you should see Office 365 on the list with a connected status.  If Office 365 is showing a connection error, it is most likely because Audit is not turned on.
    1. Select **+Connect an app** and from the drop-down list select **Microsoft Azure**.  From the Microsoft Azure pop-up window, select **Connect Microsoft Azure**.  You will see a connected status and information on scanning users, data, and activities.  Select the **Close button**.

1. Keep this page open, as you will use it in the next task.

#### Task 2: Explore ways in which you can investigate the recorded activities.

1. From the left navigation panel, under Investigate, select **Activity Log**.  Here you get you visibility into all the activities from your connected apps.   Since you already had the Office 365 connector connected you should be able to see some data. After you connect Cloud App Security to an app using the App connector, Cloud App Security scans all the activities that happened - the retroactive scan time period differs per app - and then it's updated constantly with new activities.  

1. Select an item to display more detailed information. Notice on the top of the page, the option to add a new policy from the search or to export the data for further analysis.  Select **+New policy from search**.  Note how you can create a policy based on a template, select a policy severity & category, create filters for the policy, create alerts, and even send the alerts to Power Automate.  Select **Cancel** to exit of the policy creation window.

1. From the left navigation pane, select and explore the **Files** option and note the options to filter data, create a file policy, and export of the data.  Select and explore the **user and accounts** option.  Note the options to filter data and export of the data.

1. From the left navigation panel, select Security configuration. This page provides you with security configuration assessments for your Azure, Amazon Web Services (AWS), and Google Cloud Platform (GCP) accounts.

1. Keep this page open, as you will use it in the next task.


#### Task 3: In this task you will explore the policies and alerts pages in Microsoft Cloud app security.

1. From the left navigation panel, under where it says Control, select **Policies**.  The listed policies provide information on the number of alerts generated by the policy, severity, etc. Selecting any line item provides more detailed information about the policy. Select an item from the list, i.e., **Risky sign-in**.  

1. From the left navigation panel, select **Alerts**.  If you have any alerts listed, select an item from the alerts list. Review the information provided.  From the top-right side of the window, select **Close alert**, to view options for closing the alert.  

1. Close the browser window.

#### Review
In this lab, you explored the capabilities of Microsoft Cloud App Security.  You walked through the information available on the Cloud Discovery dashboard as well as capabilities available to investigate findings and control the impact to your organization through policies.