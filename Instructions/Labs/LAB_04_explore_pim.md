<!---
---
Lab:
    Title: 'Explore identity governance in Azure AD with Privileged Identity management. '
    Learning Path/Module/Unit: 'Learning Path: Describe the capabilities of Azure Active Directory (Azure AD), part of Microsoft Entra; Module 4: Describe the identity protection and governance capabilities of Azure AD; Unit 4: Describe the capabilities of Privileged Identity Management'
---
--->

# Lab: Explore identity governance in Azure AD with Privileged Identity management

This lab maps to the following Learn content:

- Learning Path: Describe the capabilities of Azure Active Directory (Azure AD), part of Microsoft Entra
- Module: Describe the identity protection and governance capabilities of Azure AD
- Unit: Describe the capabilities of Privileged Identity Management

## Lab scenario

In this lab, you'll explore some of the basic functionality of Privileged Identity Management (PIM). PIM does require  Microsoft Entra ID P2 licensing.  In this lab, you, as the admin, will configure one of your users, Diego Siciliani, with a Microsoft Entra user administrator role, through Privileged ID management (PIM).   With user admin privileges, Diego will be able to create users and groups manage licenses, and more.  Both the admin and the user, Diego, must be configured for Microsoft Entra ID P2 licensing.

**Estimated Time**: 45-60 minutes

### Task 1

In this task you, as the admin, will reset the password for the user Diego Siciliani. This step is needed so you can initially sign in as the user in subsequent tasks.

1. Open Microsoft Edge.  In the address bar, enter **[entra.microsoft.com](https://entra.microsoft.com)**.

1. Sign in with the Microsoft 365 admin credentials provided by your ALH.
    1. In the Sign-in window, enter **admin@WWLxZZZZZZ.onmicrosoft.com** (where ZZZZZZ is your unique tenant ID provided by your ALH) then select **Next**.
    1. Enter the admin password that should be provided by your lab hosting provider. Select **Sign in**.
    1. When prompted to stay signed- in, select **Yes**.

1. From the left navigation panel, expand **Identity**, expand **Users**, then select **All users**.

1. Select **Diego Siciliani** from the list of users.

1. Select **Reset password** from the top of the page. Since you haven't previously signed in as Diego, you don’t know his password, and will need to reset the password.

1. When the password reset window opens, select **Reset Password**.  IMPORTANT, make a note of the new password, as you'll need it in a subsequent task, to be able to sign in as the user.

1. From the left navigation panel, select **Home** to return the home page for the Microsoft Entra admin center.

1. Keep the browser page open, as you'll need it in the subsequent task.

### Task 2

In this task you, as the admin, will assign Diego an Azure AD role in Privileged Identity Management.

1. Open the browser tab for the home page of the Microsoft Entra admin center.

1. From the left navigation panel, under "Identity", expand **Identity Governance**, then select **Privileged Identity Management**.

1. You are now in the Privileged Identity Management quick start page. Review the information on the Get started page. Select **Manage**.

1. You're now in the Contoso Roles page.  In the search bar, on the top of the page, enter **user**.  From the search results, select **User Administrator**.

1. From the top of the page, select **+ Add assignments**.

1. In the Add assignments page, ensure that **Membership** is underlined.  Here you'll configure the membership settings for the user administrator role in PIM.

1. Leave the Scope type to its default value, Directory.  

1. Under Select members, select **No member selected**. This opens the Select a member window.

1. In the search bar, enter **Diego**.  From the search results, select **Diego Siciliani** then press **Select** on the bottom of the page.  

1. Under Select members, you'll see 1 Member(s) selected and the name and email of the selected member(s), Deigo Siciliani. From the bottom of the Add assignments page, select **Next**.  

1. You're now in the Setting page.  Leave the Assignment type to the default setting, Eligible.

1. If the Permanently eligible box is checked, select **Permanently eligible**, to remove the checkmark.

1. In the Assignment start fields, keep the default date and time, which is today and the current time.

1. In the Assignment end fields, change the date to today’s date (note the default setting is one year from the today, so you need to change the year). For the time, set the time to two hours from the current time. After you have set the time field for the time when the Assignment ends, press the tab key on your keyboard and select **Assign** on the bottom of the page.  

1. This takes you back the Assignments window.  After a few second you should see Diego Siciliani listed in the User Administrator table, along with the details of the assignment. If after a few seconds you still don't see the update, select **Refresh** from the top of the page.

1. From the top of the page, select **Settings**.

1. In the Role setting details for User Administrator, notice the different options.  Note that the setting to “Require justification on activation” is set to yes, and “On activation, require Azure MFA” is also set to yes.  You'll see both of these in the next task when Diego activates the role.  Also note that “Require approval to activate” is set to No.  Leave all the settings to their default values.  Close the page by selecting the **X** on the top right corner of the screen.

1. Sign out by selecting on the user icon next to the email address on the top right corner of the screen and selecting **Sign out**. Then the close all the browser windows.

### Task 3

In this task you, as Diego Siciliani, will sign in to Microsoft Entra admin center, to access the Privileged Identity Management capability of Microsoft Entra to activate your assignment as User administrator.  Once activated you'll make some configuration changes to an existing user. Note: For this task, you'll need access to a mobile device to which you have immediate access and can receive text messages.

1. Open Microsoft Edge.  In the address bar of the browser, enter **Entra.microsoft.com**.

1. Sign in as Diego Siciliani.
    1. In the Sign-in window, enter **DiegoS@WWLxZZZZZZ.onmicrosoft.com** (where ZZZZZZ is your unique tenant ID provided by your lab hosting provider) then select **Next**.
    1. Enter the temporary password that you noted from the previous task and select **Sign in**.  Select **Sign in**.
    1. Since the password you entered was only a temporary password, you need to update now. Enter the current password, enter a new password, then confirm the new password.  Make note of this new password as you will need to complete the task.
    1. When prompted to stay signed- in, select **Yes**.

1. You should be successfully logged in to Microsoft Entra admin center.
1. From the left navigation panel, expand **Identity Governance** then select **Privileged Identity Management**.
1. From the left navigation panel, select **My roles**.  You're now seeing information for your eligible assignments.  You'll see that you, Diego, are assigned the User administrator role.  
1. In the last column of the table, labeled action, select **Activate**.
1. You'll see a warning icon indicating Additional verification required.  Select **Click to continue**.  Recall that the PIM settings for the User administrator role require multi-factor authentication.  Additionally, since Diego’s contact information for use with MFA (authentication methods) was not previously configured, he must register his information, to be able to use MFA.  Although he will have to do MFA anytime he signs in as a user admin, within the assignment period, the MFA registration process is required only once.
1. You're notified that more information is required, select **Next**.
1. Enter your password.
1. From the bottom left of the Microsoft Authenticator window, select **I want to setup a different method**.
1. You're prompted to Choose a different method.  Next to where it says Authenticator app, select the down arrow key.   Select **Phone** and then select **Confirm**.
1. You're prompted to enter a phone number you would like to use. Ensure the country is correct, for your telephone number’s country code.  Enter your phone number, ensure that **Text me a code** is selected, then select **Next**.
1. Enter the 6 digit code you received on your phone and select **Next**.
1. You'll see a notification that your phone was registered successfully. Select **Next**, then select **Done**.
1. You're asked if you want to stay signed in.  Select **Yes**.
1. The Activate User Administrator window appears.  You're required to enter a reason for the activation.  In the box that appears, enter any reason you want (max of 500 characters), then select **Activate**.
1. You'll see the status (3 stages of progress), as the activation is processed.
1. Once the activation is completed you're returned to the My roles | Azure AD roles page, where you'll see a notification stating you have activated a role.  Select **Click here** to view your active roles.  If you notice the end time is different than what was originally configured, select the refresh key on the top of the page (it may take a few minutes to refresh).
1. Return to the home page of the Microsoft Entra admin center by selecting **Home** from the left navigation panel. 
1. As an Azure AD user administrator you can create users and groups, manage licenses, and more. From the left navigation panel, expnad **Identity**, select **Users**, then select **All users**.
1. From the users list, select **Bianca Pisani**.
1. From the left navigation panel, select **Licenses**.
1. Notice how Bianca has no licenses assigned.  From the top of the page, select **+ Assignments**.
1. From the select licenses list, select **Office 365 E3** and **Windows 10 Enterprise E3**.
1. From the bottom of the page, select **Save**.  You'll see a brief notification on the top right of page indicating licenses were successfully assigned.
1. Close out of the updated license assignments page, by selecting the **X** on the top right corner of the page.
1. Sign out by selecting on the user icon next to the email address on the top right corner of the screen and selecting **Sign out**. Then the close all the browser windows.
1. The duration of the user admin role is limited to the time that was configured.
1. Sign out by selecting on the user icon next to the email address on the top right corner of the screen and selecting **Sign out**. Then the close all the browser windows.

### Review

In this lab; you, explored PIM.  You, as the admin, configured Diego with user admin privileges for a specified amount of time.  Then you, as Diego, walked through the process of activating the user admin privileges and configuring user settings.  Recall that PIM requires Azure AD Premium P2 licensing.
