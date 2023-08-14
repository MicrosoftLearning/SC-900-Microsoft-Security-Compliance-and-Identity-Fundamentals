<!---
---
Lab:
    Title: 'Explore Microsoft Entra ID User Settings'
    Learning Path/Module/Unit: 'Learning Path: Describe the capabilities of Microsoft Entra; Module 1: Describe the function and identity types of Microsoft Entra ID; Unit 3: Describe the Microsoft Entra identity types'
---
--->

# Lab: Explore Azure Active Directory

This lab maps to the following Learn content:

- Learning Path: Describe the capabilities of Microsoft Entra.
- Module: Describe the function and identity types of Microsoft Entra ID.
- Unit: Describe the types of identities.

## Lab scenario

In this lab, you'll access Microsoft Entra ID (previously referred to as Azure Active Directory).  Additionally, you'll create a user and configure the different settings, including adding licenses.  

**Estimated Time**: 10-15 minutes

### Task 1

As a subscriber to Microsoft 365 you're already using Microsoft Entra ID (previously referred to as Azure AD).  In this task, you’ll learn how to create a new user in Microsoft Entra ID and explore some of services that can be managed at the user level.

1. From the Microsoft Edge browser, select the tab labeled Home - Microsoft 365 admin center.

1. If you previously closed that browser tab, then follow the steps below:
    1. in the address bar, enter **admin.microsoft.com** and sign in with your admin credentials as follows:
    1. In the Sign-in window, enter **admin@WWLxZZZZZZ.onmicrosoft.com** (where ZZZZZZ is your unique tenant ID provided by your lab hosting provider) then select **Next**.
    1. Enter the admin password that should be provided by your lab hosting provider. Select **Sign in**.
    1. When prompted to stay signed- in, select **Yes**.

1. From the left navigation pane of the Microsoft 365 admin center, select **Show all**.

1. Under Admin centers, select **Identity** (you may need to scroll down).  A new browser page opens to the overview page of the Microsoft Entra admin center. Here you will see basic information about your Contoso tenant. If you scroll down the main window you will also see information about alerts, my feed, feature highlights, and more.

1. From the left navigation pane, expand **Users** then select **All users**. Notice that your tenant is already configured with users.

1. From the top of the page, select **+ New user** then from the drop-down box, select **Create new user**.

1. You are now in the **basics** tab of the create new user page. Populate the fields as follows:
    1. User principal name: **sara**.

    1. Mail nickname: leave the default, which is set to derive from user principal name.

    1. Display name: **Sara Perez**.

    1. Password: uncheck the box that says auto-generate password and enter a temporary password that adheres to the password requirements and make note of it, as you will need it to complete the subsequent task.

    1. Account enabled:  Leave the checkmark to ensure the account is enabled.

    1. At the bottom of the page, select **Next: Properties**.

1. Here you will configure a few of the fields in the **Properties** tab.

    1. First name: Sara

    1. Last name: Perez

    1. User types:  Leave the default to **Member**, but note that from the drop-down you have the option to select guest.

    1. Usage location: Choose the country/region where you are located.  Note that to get to the usage location field, you will need to scroll down on the page as it is the last field on the page.

    1. Select **Next: Assignments**.

1. You are now on the **Assignments** tab where you add a group assignment and view the available options for adding a role.

    1. Select **Add group**.

    1. The window that opens shows all the available groups.  

    1. Next to Groups, select **0 groups selected**.  This displays the available groups.  Notice the list of available groups.  From the list, select **Operations**.  From the bottom of the page, select the **Select** button.  It may take a few seconds but you should see the operations group showup on the assignments page.

    1. From the top of the page, select **Add role**.  A window opens that shows all the available directory roles.  View the available options, but don't add any new roles.  Close this page by selecting the **X** on the top right corner of the directory roles page.
    1. From the bottom of the page, select **Review + create**. A summary of the settings will be displayed.  From the bottom of the page, select **Create**.

1. You are returned to the users page.  After a few seconds, Sara Perez will be listed.  You may need to select the **refresh** icon on the top of the page.

1. From the user list, select the user you created, **Sara Perez**.  The **Overview** page opens.

1. The left navigation panel shows the various options that can be configured for the user. View the available options.

1. From the left navigation panel, select **Licenses**.  Notice that there are no license assignments found for this user.  NOTE:  Licenses can only be assigned if a usage location was configured. If you did not set the usage location, go back to that step in the previous task.

    1. To add a license select **+ Assignments** from the top of the main window.

    1. Under Select licenses, select **Office 365 E3** and **Windows 10/11 Enterprise E3** then select the **Save** button on the bottom of the screen. A notification on the top right corner of the screen should show that license assignments succeeded.

    1. Select the **X** on the top right of the screen to close the License assignments window.

    1. Select the **Refresh icon** at the top of the page to confirm the license assignments.

1. Return to the Microsoft Entra admin center by selecting **Home** from the left navigation panel or from the top-left of the screen (the bread-crumb), above where it says Sara Perez | Licenses.

1. You have successfully created and configured a user in Microsoft Entra ID.

1. Sign out of all the open browser tabs. Sign out by selecting the user icon next to the email address on the top right corner of the screen then selecting **Sign out**. Close all the browser windows.

### Task 2

In this task, you'll sign in as Sara Perez, for the first time.

1. Open Microsoft Edge.

2. In the address bar, enter **login.microsoft.com**.

3. Sign in as **sara@WWLxZZZZZ.onmicrosoft.com**, (where ZZZZZZ is your unique tenant ID provided by your lab hosting provider).

4. Enter the temporary password you set in the previous task.

5. You are now prompted to Update your password. In the Current password field, enter the temporary password from the previous task.

6. In the New password field, enter a new password, confirm the password, then select **Sign in**.  

7. You should now be successfully signed-in to Microsoft 365.

8. Sign out by selecting the icon on the top right corner of the Microsoft 365 window that is shown as a circle with the letters SP (next to the question mark icon), then selecting **Sign out**, then close the browser.

### Review

In this lab, you started your initial exploration of Azure AD. Since subscribers to Microsoft 365 are automatically using Azure AD, you found that you access Azure AD features and services through either the Microsoft 365 admin portal or through the Azure portal.  Whichever approach you prefer to get to the same place.  You also walked through the process of creating a new user and the different setting that can be configured, including groups to which the user can be assigned, the availability of roles, and assigning of user licenses.
