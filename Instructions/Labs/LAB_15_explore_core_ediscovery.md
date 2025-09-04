---
lab:
    title: 'Explore eDiscovery'
    module: 'Describe the data compliance solutions of Microsoft Purview'
---

# Lab: Explore eDiscovery

This lab maps to the following Learn content:

- Learning Path: Describe the capabilities of Microsoft Priva and Microsoft Purview
- Module: Describe the data compliance solutions of Microsoft Purview
- Unit:  Describe eDiscovery

## Lab scenario

In this lab you'll go through the steps required for setting up eDiscovery, including setting up role permissions, creating an eDiscovery case, creating an eDiscovery hold and creating a search query.  Note:  Licensing for eDiscovery requires the appropriate organization subscription and per-user licensing. If you aren’t sure which licenses support eDiscovery, visit [Get started with eDiscovery in Microsoft Purview](https://docs.microsoft.com/microsoft-365/compliance/get-started-core-ediscovery?view=o365-worldwide).

**Estimated Time**: 45 minutes

### Task 1

To access eDiscovery or be added as a member of an eDiscovery case, a user must be assigned the appropriate permissions. In this task, you as the global admin, will add specific users as members of the eDiscovery Manager role group.

1. You should be on the home page of the Microsoft Purview portal.  If you previously closed it, open a browser tab and enter **https://purivew.microsoft.com**.

1. From the left navigation pane, select **Settings**, expand **Roles and scopes**, then select **Role groups**.

1. In the search field, on the top, right of the page, enter **eDiscovery** then hit Enter on your keyboard.  Select **eDiscovery Manager**.

1. Select **Edit**. For the purpose of this lab, you'll set yourself as MOD administrator as the eDiscovery Manager and administrator.  In practice, you would designate specific users for specific roles.
    1. The "Manage eDiscovery Manager" page allows you to add users to the role of eDiscovery manager.
    1. Select **Choose users**. Search for and select **MOD Administrator** then press **Select** at the bottom of the page, then select **Next**.
    1. On the "Manage eDiscovery Administrator" page, select **Choose users** . Search for and select **MOD Administrator** then press **Select** at the bottom of the page, then select **Next** and then **Save**.
    1. On the "You successfully updated the role group" page, select **Done**.

1. Return to the Microsoft Purview home page by selecting **Home** from the left navigation panel.

1. Keep this browser tab open, as you'll use it in the next task.

### Task 2

In this task you, as an eDiscovery Administrator (MOD admin is an eDiscovery administrator), will create a case to start using eDiscovery.

1. You should be on the home page of the Microsoft Purview portal.

1. From the left navigation panel, under Solutions, expand **eDiscovery** then select **Cases**.

1. From the Cases page page, select **Create case**.

1. In the New case window, enter a Case name, **SC900 Test Case** then select the **Create**.

1. The case should now appear on the list.

1. As the creator of the case and because you have eDiscovery Administrator privileges, you can begin to work with it.  

1. Keep this browser tab open, as you'll use it in the subsequent task.

### Task 3

With a case created, you can begin to work with the case.  This includes creating a search query to find data and content that is relevant to your case, applying a hold policy, creating a review set, and exporting data. In this task you'll explore some of these options.

1. Open the SC900 Test Case tab on your browser.

1. From the SC900 Test Case page, select  **Create a search**.

1. In the name field, enter **SC900 case search** then select **Create**.

1. Select **Add sources**. Note the filter options and default settings. In the search box, enter **Pradeep** then press enter on your keyboard. From the search results select **Pradeep Gupta**, then select **Save and close**. The Condition builder allows you to build a search query based on specific Keywords or Conditions that are satisfied, In the keyword box, enter **Sales**. From here you can select to **Run the query**.  This may take several minutes.

1. With query results returned in the form of statistics, you can export results.  Select **Export** to vew available options then select **Cancel** (the export options cannot be selected from within the lab platform provided by the authorized lab hoster, but are available in a production environment and are considered part of the workflow).

1. You can add to a review set for further processing.  Select **Add to review set**. Enter a name for the new review set, **`SC900-review-set`**, leave the default settings, then select **Add to review set** .  This can take several minutes to complete.  Now you can review and take action from the review set, including tagging items, querying the review set, running analytics and more.  Explore the various options.

1. You can also create a hold policies to preserve content relevant to your case. Select **Hold policies**, then **New policy**.  Enter a Policy name, **`SC900-hold`**, and select **Create**.  As in the search, you need to add data sources for the hold and you can add keywords and conditions to use in the hold policy, then you can select **Apply hold**.  Actions you can take on a hold policy include retry, turn off a policy, and deleting a hold policy.

1. Sign out and close all open browser windows.

### Review

In this lab, you went through the steps required to get started with eDiscovery, including setting up the role permissions for eDiscovery and creating an eDiscovery case.  With the case, created you explored options available as part of the eDiscovery workflow including an eDiscovery search, a hold policy, add search results to a review set, and exporting results.
