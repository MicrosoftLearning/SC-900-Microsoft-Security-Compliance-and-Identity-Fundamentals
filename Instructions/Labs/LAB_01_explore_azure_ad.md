<!---
---
Lab:
    Title: 'Explore Azure Active Directory'
    Learning Path/Module/Unit: 'Learning Path: Describe the capabilities of Azure Active Directory (Azure AD), part of Microsoft Entra; Module 1: Describe the basic services and identity types of Azure AD; Unit 4: Describe the Azure AD identity types'
---
--->

# Lab: Explore Azure Active Directory

This lab maps to the following Learn content:

- Learning Path: Describe the capabilities of Azure Active Directory (Azure AD), part of Microsoft Entra
- Module: Describe the basic services and identity types of Azure AD
- Unit: Describe the Azure AD identity types

## Lab scenario

In this lab, you'll access Azure Active Directory.  Additionally, you'll create a user and configure the different settings, including adding licenses.  

**Estimated Time**: 10-15 minutes

### Task 1

As a subscriber to Microsoft 365 you're already using Azure AD.  In this task, you'll walk through accessing Azure AD through the Microsoft 365 Admin portal and through the Azure portal.

1. From the Microsoft Edge browser, select the tab labeled Home - Microsoft 365 admin center.

1. If you previously closed that browser tab, then follow the steps below:
    1. in the address bar, enter **https://admin.microsoft.com** and sign in with your admin credentials as follows:
    1. In the Sign-in window, enter **admin@WWLxZZZZZZ.onmicrosoft.com** (where ZZZZZZ is your unique tenant ID provided by your lab hosting provider) then select **Next**.
    1. Enter the admin password that should be provided by your lab hosting provider. Select **Sign in**.
    1. When prompted to stay signed- in, select **Yes**.
    1. From the left navigation pane of the Microsoft 365 admin center, select **Show all**.

1. Under Admin centers, select **Identity** (you may need to scroll down).  A new browser page opens to the Overview page of the Microsoft Entra ID (Azure AD) in the Microsoft Entra admin center. From the overview, you'll see several tabs, including the Organization’ overview (tenant name: Contoso, the tenant ID and the Primary domain name), Monitoring, Recommendations, Tutorials, and more.

1. From the left navigation pane, under Identity select **Show more**.  The navigation panel now lists all the services that are available in Microsoft Entra ID (Azure AD).

1. Now open a new browser window and in the address bar, enter **https://portal.azure.com**.  Since you're already signed in as admin@WWLxZZZZZZ.onmicrosoft.com and you originally used those same credentials to redeem your Azure pass, you should be logged in as admin when you access the Azure portal.  You can verify this by checking the email on the top-right corner of the page and hovering your mouse over the user icon.

1. The Azure portal’s landing page shows Azure services, including Azure Active Directory, VMs, storage accounts, databases, and much more.  Select **More Services**, then select **Azure Active Directory**. If you don't immediately see it, you can enter Azure Active Directory on the blue search bar and select it from there.  

1. You're now seeing the Azure Active Directory for your Microsoft 365 Contoso tenant.    Whichever approach you use to access Azure Active Directory services (the Microsoft 365 admin portal or the Azure portal) you end up in the same place – the Contoso Azure Active Directory where you can administer all the Azure AD services.

1. Keep this browser page open for the next task.

### Task 2

In this task, you’ll learn how to create a new user in Azure Active Directory and explore some of services that can be managed at the user level.

1. Go to the Contoso – Microsoft Azure tab that is open on your browser. If you previously closed the tab, open a browser page and in the address bar, enter https://portal.azure.com and select **Azure Active Directory**.  You should be logged in as admin in the Azure portal; if not, sign back in.

1. From the left navigation pane, select **Users**.  Notice that your tenant is already configured with users.

1. From the top of the page, select **+ New user** then from the drop-down box, select **Create new user**.

1. **Create new user** should already be selected, if not select that option.

1. Populate the **Identity** fields as follows:

    1. User principal name: **sara**.

    1. Display name: **Sara Perez**.

1. Populate the **Password** fields as follows:

    1. Deselect **Auto-generate password**.

    1. Initial password: Enter a temporary password that adheres to the password requirements and make note of it, as you will need it to complete the subsequent task. When Sara signs-in for the first time, she'll be prompted to change her password.
  
1. Account enabled:  **Selected** (leave the default setting).

1. At the bottom of the page, select **Next: Properties >**.

1. On the Properties tab, populate the **Identity** fields as follows:

    1. First name: **Sara**.

    1. Last name: **Perez**.
  
    1. User type: **Member** (leave the default setting).

1. Scroll down and populate the **Settings** fields as follows:

    1. Usage location: select the drop-down then select **United States** (scroll down to find this option) or the country in which you're located.  Configuring usage location is required for assigning licenses.

1. At the bottom of the page, select **Next: Assignments >**.

1. On the Assignments tab, select **+ Add group**.  This displays the available groups.  Notice the list of available groups.

    1. Search for and select **Operations**, you may need to scroll down, then press **Select**. Notice the assignment table has been updated to reflect 1 group assigned.  

1. On the Assignments tab, select **+ Add role**. This displays the available Directory roles.  Scroll down to view the various built-in roles. View the various roles, but don’t assign any.  Close out of this window by select the **X** at the top right-hand corner of the page.

1. From the bottom of the page, select the **Review + create** button and then **Create**.

1. Verify the user appears in the user list (names are listed in alphabetical order). **Note:** You may need to use the **Refresh icon** in the command bar at the top of the page.

1. From the user list, select the user you created, **Sara Perez**.  The profile page opens.

1. The left navigation panel shows the various options that can be configured for the user.  Select **Groups**.  Here you can see additional information about the group.  Verify the Operations group is listed (it may take several minutes for the group assignment to show up).  **Note:**  You may also see the Contoso group, although we only assigned one group when we created the user.  This is a result of a preconfigured policy in the tenant that automatically assigns new users to the Org-wide Contoso group.

1. From the left navigation panel, select **Licenses**.  Notice that there are no license assignments found for this user.  

1. To add a license select **+ Assignments** from the command bar at the top of the main window.

1. Under Select licenses, select **Office 365 E3** and **Windows 10/11 Enterprise E3** then select the **Save** button at the bottom of the screen. A notification at the top right corner of the screen should show that license assignments succeeded.

1. Select the **X** at the top right corner of the screen to close the License assignments window.

1. Select the **Refresh icon** in the command bar at the top of the page to confirm the license assignments.

1. Return to the Contoso Overview Azure Active directory page, by selecting **Contoso | Users** at the top-left of the screen (the bread-crumb), above where it says Sara Perez | Licenses.

1. You have successfully created and configured a user in Azure Active Directory.

1. Sign out of all the open browser tabs.  In the Azure portal, sign out by selecting the user icon next to the email address at the top right corner of the screen then selecting **Sign out**.  In Microsoft 365 sign out by selecting the icon at the top right corner of the Microsoft 365 window that is shown as a circle with the letters SP (next to the question mark icon), then selecting **Sign out**.  Close all the browser windows.

### Task 3

In this task, you'll sign in as Sara Perez, for the first time.

1. Open Microsoft Edge.

2. In the address bar, enter **https://login.microsoft.com**.

3. Sign in as **sara@WWLxZZZZZ.onmicrosoft.com**, (where ZZZZZZ is your unique tenant ID provided by your lab hosting provider).

4. Enter the temporary password you set in the previous task.

5. You are now prompted to Update your password. In the Current password field, enter the temporary password from the previous task.

6. In the New password field, enter a new password, confirm the password, then select **Sign in**.  

7. You should now be successfully signed-in to Microsoft 365.

8. Sign out by selecting the icon on the top right corner of the Microsoft 365 window that is shown as a circle with the letters SP (next to the question mark icon), then selecting **Sign out**, then close the browser.

### Review

In this lab, you started your initial exploration of Azure AD. Since subscribers to Microsoft 365 are automatically using Azure AD, you found that you access Azure AD features and services through either the Microsoft 365 admin portal or through the Azure portal.  Whichever approach you prefer to get to the same place.  You also walked through the process of creating a new user and the different setting that can be configured, including groups to which the user can be assigned, the availability of roles, and assigning of user licenses.
