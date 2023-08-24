<!---
---
Demo:
    Title: 'Explore the eDiscovery (Standard) workflow'
    Learning Path/Module/Unit: 'Learning Path: Describe the capabilities of Microsoft compliance; Module 5: Describe the eDiscovery and audit capabilities of Microsoft Purview; Unit 2:  Describe the eDiscovery solutions in Microsoft 365'
---
--->

# Demo: Explore the eDiscovery (Standard) workflow

This demo maps to the following Learn content:

- Learning Path: Describe the capabilities of Microsoft compliance
- Module: Describe the eDiscovery and audit capabilities of Microsoft Purview
- Unit:  Describe the eDiscovery solutions in Microsoft 365

## Demo scenario

In this demo you'll do a walk-through of the steps required for setting up eDiscovery, including setting up role permissions, creating an eDiscovery case, creating an eDiscovery hold and creating a search query.  Note:  Licensing for eDiscovery (Standard) requires the appropriate organization subscription and per-user licensing. If you aren’t sure which licenses support eDiscovery (Standard), visit [Get started with eDiscovery (Standard) in Microsoft Purview](https://docs.microsoft.com/microsoft-365/compliance/get-started-core-ediscovery?view=o365-worldwide).

### Demo Part 1

To access eDiscovery (Standard) or be added as a member of an eDiscovery case, a user must be assigned the appropriate permissions. In this part of the demo, you as the global admin, will walk through the process of adding specific users as members of the eDiscovery Manager role group.

1. Open the browser tab for home page of Microsoft Purview.  If you previously closed it, open a browser tab and enter **https://admin.microsoft.com**. Sign in with the admin credentials for the Microsoft 365 tenant provided by the authorized lab hoster (ALH). From the left navigation pane of the Microsoft 365 admin center, select **Show all** then select **Compliance**.  A new browser page opens to the welcome page of the Microsoft Purview compliance portal.  

1. From the left navigation pane, expand (select the down arrow) **Roles & Scopes** then select **Permissions**.

1. Under Microsoft Purview solutions, select **Roles**.

1. In the search field, enter **eDiscovery** then select the search icon (magnifying glass).  Select **eDiscovery Manager**.  Note the roles in the role group.

1. Select **Edit**.  Notice how there are two subgroups, eDiscovery Manager and eDiscovery Administrator.  
    1. The "Manage eDiscovery Manager" page allows you to add users to the role of eDiscovery manager. For this demo, we'll add members to the eDiscovery Administrator subgroup so select **Next**.
    1. On the "Manage eDiscovery Administrator" page, select **Choose users** . Search for and select **MOD Administrator** and **Megan Bowen** then press **Select** at the bottom of the page, then select **Next** and then **Save**.
    1. On the "You successfully updated the role group" page, select **Done**.

1. Keep this browser tab open.

### Demo Part 2

In this part you, as an eDiscovery Administrator (MOD admin is an eDiscovery administrator), will create a case to start using eDiscovery (Standard).

1. You should still be on the compliance portal roles page. From the left navigation panel, under Solutions, select **eDiscovery** then select **Standard**.

1. From the top of the eDiscovery (Standard) page, select **+ Create a case**.

1. In the New case window, enter a Case name, **SC900 Test Case** then select the **Save** at the bottom of the page.

1. The case should now appear on the list.

1. As the creator of the case and because you have eDiscovery Administrator privileges, you can begin to work with it.  

1. Keep this browser tab open.

### Demo Part 3

Now that you've created an eDiscovery (Standard) case, you can begin to work with the case.  In this part, you'll create an eDiscovery hold for the case for you created.  Specifically, you'll create a hold for the exchange mailbox belonging to Adele Vance.

1. From the eDiscovery (Standard) page, select the case you created - **SC900 Test Case**.

1. From the Home page of the case, select the **Hold** tab then select **+Create**.

1. In the name field, enter **Test hold** then select **Next**.

1. In the Choose locations page, select toggle switch next to **Exchange mailboxes** to set the status to **On**.  

1. Now select **Choose users, groups, or teams**.  In the search box, enter **Adele** then press enter on your keyboard. From the search results select **Adele Vance**, then select **Done**.

1. From the Choose locations page, select **Next**.  For expediency with the demo, no other locations will be included in this hold.

1. The Query conditions page enables you to create a hold, based on specific Keywords or Conditions that are satisfied, select **+ Add condition** to view the available options.  Select **Next**. Without any conditions, the hold will preserve all content in the specified location.

1. Review your settings and select **Submit**, it may take a minute, then select **Done**.  The Test hold should appear on the list.  If you don't immediately see it, select **Refresh**

1. Keep this browser tab open.

### Demo Part 4

With a hold in place, you'll create a search query.  Once your search is complete, the eDiscovery supports actions, such as exporting and downloading the results for future investigation.   Note:  Searches associated with an eDiscovery (Standard) case are not listed on the Content search page in the Microsoft Purview compliance portal. These searches are listed only on the Searches page of the associated eDiscovery (Standard) case.

1. From the SC900 Test Case page, select  **Searches**.

1. From the Search page, select **+ New Search**.

1. In the Name field, enter **Test Hold – Sales Search**, then select **Next** from the bottom of the page.

1. In the Choose locations page, select **locations on hold** and unselect **Add App Content for On-Premises users**, as your lab environment has no on-premises  users, then select **Next**.

1. The Query conditions page enables you to create a search, based on specific Keywords or Conditions that are satisfied, In the keyword field enter **Sales** select **Next**.

1. Review your settings and select **Submit**, it may take a minute, then select **Done**.  The search should appear on the list.  If you don't immediately see it, select **Refresh**

1. From the Searches window, select the search you created, **Test Hold - Sales Search**.  A window that opens with the Summary tab selected.  Once the search is complete the status will indicate that the search is completed.  You'll see a Search statistics tab (if you don't see the Search statistics tab, the search may still be running and may take a few minutes to complete).  Select the **Search statistics** tab and select the down-arrow next to Search content.  You can also view more information for the Condition report and Top locations.  

1. From the bottom of the page, select **Actions**.  Note the available options that include export options. Select **Close**.

1. Close all the open browser tabs.

### Review

In this demo, you went through the steps required to get started with eDiscovery (Standard), including setting up the role permissions for eDiscovery and creating an eDiscovery case.  With the case, created you went through elements of the eDiscovery (Standard) workflow by creating an eDiscovery hold and creating a search query.
