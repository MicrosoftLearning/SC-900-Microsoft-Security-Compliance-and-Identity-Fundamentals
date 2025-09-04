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

Now that you've created an eDiscovery case, you can begin to work with the case.  In this task, you'll create an eDiscovery hold for the case for you created.  Specifically, you'll create a hold for the exchange mailbox belonging to Adele Vance.

1. Open the eDiscovery tab on your browser.

1. From the eDiscovery page, select the case you created in the previous tab, **SC900 Test Case**.

1. From the Home page of the case, select the **Hold** tab then select **+Create**.

1. In the name field, enter **Test hold** then select **Next**.

1. In the Choose locations page, select toggle switch next to **Exchange mailboxes** to set the status to **On**.  

1. Now select **Choose users, groups, or teams**.  In the search box, enter **Adele** then press enter on your keyboard. From the search results select **Adele Vance**, then select **Done**.

1. From the Choose locations page, select **Next**.  For expediency with the lab, no other locations will be included in this hold.

1. The Query conditions page enables you to create a hold for items based on a query that you can create.  You can choose to use the Query builder to create a query or for more advanced users, you can use the KQL editor. For this exercise, you want the hold to preserve all content in the specified location for the specified user, so you will not create a query.

1. Review your settings and select **Submit**, it may take a minute, then select **Done**.  The Test hold should appear on the list.  If you don't immediately see it, select **Refresh**

1. Keep this browser tab open, as you'll use it in the subsequent task.

### Task 4

With a hold in place, you'll create a search query.  Once your search is complete, the eDiscovery supports actions, such as exporting and downloading the results for future investigation.   Note:  Searches associated with an eDiscovery case are not listed on the Content search page in the Microsoft Purview portal. These searches are listed only on the Searches page of the associated eDiscovery case.

1. Open the SC900 Test Case tab on your browser.

1. From the SC900 Test Case page, select  **Searches**.

1. From the Search page, select **+ New Search**.

1. In the Name field, enter **Test Hold – Sales Search**, then select **Next** from the bottom of the page.

1. In the Choose locations page, select **locations on hold** and unselect **Add App Content for On-Premises users**, as your lab environment has no on-premises  users, then select **Next**.

1. The Query conditions page enables you to create a search, based on specific Keywords or Conditions that are satisfied, In the keyword field enter **Sales** select **Next**.

1. Review your settings and select **Submit**, it may take a minute, then select **Done**.  The search should appear on the list.  If you don't immediately see it, select **Refresh**

1. From the Searches window, select the search you created, **Test Hold - Sales Search**.  A window that opens with the Summary tab selected.  Once the search is complete the status will indicate that the search is completed.  You'll see a Search statistics tab (if you don't see the Search statistics tab, the search may still be running and may take a few minutes to complete).  Select the **Search statistics** tab and select the drop-down next to Search content.  You can also view more information for the Condition report and Top locations.  

1. From the bottom of the page, select **Actions**.  Note the available options that include export options (the export options cannot be selected from within the lab platform provided by the authorized lab hoster, but are available in a production environment and are considered part of the workflow). Select **Close**.

1. Sign out and close all open browser windows.

### Review

In this lab, you went through the steps required to get started with eDiscovery, including setting up the role permissions for eDiscovery and creating an eDiscovery case.  With the case, created you went through elements of the eDiscovery workflow by creating an eDiscovery hold and creating a search query.
