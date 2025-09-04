<!---
---
Demo:
    Title: 'Explore the eDiscovery'
    Learning Path/Module/Unit: 'Learning Path: Describe the capabilities of the Microsoft Priva and Microsoft Purview; Module 3: Describe the data compliance solutions of Microsoft Purview; Unit 2:  Describe eDiscovery'
---
--->

# Demo: Explore eDiscovery (Standard)

This demo maps to the following Learn content:

- Learning Path: Describe the capabilities of the Microsoft Priva and Microsoft Purview
- Module: Describe the data compliance solutions of Microsoft Purview
- Unit:  Describe eDiscovery

## Demo scenario

In this demo you'll do a walk-through of the steps required for setting up eDiscovery, including setting up role permissions, creating an eDiscovery case, creating an eDiscovery hold and creating a search query.  NOTE: In the Microsoft Purview portal updates to the user interface are rolling out, gradually. Some lab/demo tenants may not yet show the newest UI, so all lab steps are shown using the Classic eDiscovery UI.

### Demo Part 1

To access eDiscovery or be added as a member of an eDiscovery case, a user must be assigned the appropriate permissions. In this part of the demo, you as the global admin, will walk through the process of adding specific users as members of the eDiscovery Manager role group.

1. Open the browser tab for **Microsoft Purview**. If you previously closed it, open a browser tab and in the address bar, enter **https://purview.microsoft.com** then select **Get started**.  
1. From the left navigation panel, select **Settings**.
1. From the navigation panel that opens, select **Roles and scoped** to expand the option, then select **Role groups**.
1. In the search box on the right side of the screen, search on the term **eDiscovery**.  Select **eDiscovery Manager**.
    1. Select **Edit**.
    1. Select **Choose users**.
    1. Search for MOD Administrator, select the box next to **MOD Administrator** then select the **Select** button on the bottom of the page.
    1. Select **Next** then select **Save**, then finally select **Done**.

1. Keep this browser tab open.

### Demo Part 2

In this part you, as an eDiscovery Administrator (MOD admin is an eDiscovery administrator), will create a case to start using eDiscovery.

1. You should be on the home page of the Microsoft Purview portal.

1. From the left navigation panel, under Solutions, expand **eDiscovery** then select **Cases**.

1. From the Cases page page, select **Create case**.

1. In the New case window, enter a Case name, **SC900 Test Case** then select the **Create**.

1. The case should now appear on the list.

1. As the creator of the case and because you have eDiscovery Administrator privileges, you can begin to work with it.  

1. Keep this browser tab open, as you'll use it in the subsequent task.

### Demo Part 3

With a case created, you can begin to work with the case. This includes creating a search query to find data and content that is relevant to your case, applying a hold policy, creating a review set, and exporting data. In this task you'll explore some of these options. NOTE: It is recommended that you go through creating a search and review set prior to the delivery so the search and review set results are readily available during the demo, as these actions can take several minutes to complete.  

1. Open the SC900 Test Case tab on your browser.

1. From the SC900 Test Case page, select  **Create a search**.

1. In the name field, enter **SC900 case search** then select **Create**.

1. Select **Add sources**. Note the filter options and default settings. In the search box, enter **`Pradeep`** then select **Search**. From the search results select **Pradeep Gupta**, then select **Save and close**. The Condition builder allows you to build a search query based on specific Keywords or Conditions that are satisfied, In the keyword box, enter **Sales**. From here you can select to **Run the query**, From the Choose search results window. For the lab tenant, only the statistics view of the search results is available. Note the options to arrange by top indicators. Select **Run query**.  This may take several minutes.

1. With query results returned in the form of statistics, you can export results.  From the top right of the screen (next to where it says Add to review set), select **Export** to vew available options then select **Cancel**.

1. You can add to a review set for further processing.  Select **Add to review set**. Enter a name for the new review set, **`SC900-review-set`**, leave the default settings, then select **Add to review set**. This can take several minutes to complete. Once the review set results are presented, you can explore the different options, which include Analytics, Query, Actions, Tag files, and Manage.

1. You can also create a hold policies to preserve content relevant to your case. From the Review set window, select the **Hold** tab.  This takes to you the Hold policies window. Select **New policy**.  Enter a Policy name, **`SC900-hold`**, and select **Create**.  As in the search, you need to add data sources for the hold and you can add keywords and conditions to use in the hold policy, then you can select **Apply hold**.  Actions you can take on a hold policy include retry, turn off a policy, and deleting a hold policy.

1. Sign out and close all open browser windows.

### Review

In this demo, you went through the steps required to get started with eDiscovery, including setting up the role permissions for eDiscovery and creating an eDiscovery case.  With the case, created you explored the settings for creating search and exporting results, adding to a review set, and creating a hold.
