---
Demo:
    title: 'Explore Azure Active Directory'
    module: 'Module 2 Lesson 2: Describe the capabilities of Microsoft Identity and access management solutions: Explore the services and identity types of Azure AD'
---

# Demo: Explore Azure Active Directory

## Demo scenario

In this demo, you will access Azure Active Directory.  Additionally, you will show how to create a user and configure the different settings.

## Instructions

#### Demo Part 1:  Create a user
1. Open Microsoft Edge.

1. In the address bar enter **portal.microsoft.com** to access the Microsoft 365 admin center.

1. Sign in with your admin credentials. 
    1. In the Sign in window enter **admin@WWLxZZZZZZ.onmicrosoft.com** (where ZZZZZZ is your unique tenant ID provided by your lab hosting provider) then select **Next**.
    1. Enter the admin password which should be provided by your lab hosting provider. Select **Sign in**.
    1. When prompted to stay signed- in, select **Yes**.

1. The Azure portal’s landing page shows Azure services, select **Azure Active Directory**.  

1. From the left navigation pane, select **Users**.  Notice that your tenant is already configured with users.

1. From the top of the page, select **+ New user**.

1. **Create User** should already be selected, if not select that option.

1. Populate the **Identity** fields as follows:
    1. User name: **sara**.
    2. Name field: **Sara Perez**.
    3. First name: **Sara**.
    4. Last name: **Perez**.

1. Populate the **Password** fields as follows:
    1. Select **Let me create the password**.  Note:  use this option if you plan to login as Sara in subsequent step.
    1. Initial password: **Naja8996**. When Sara signs-in for the first time, she will be prompted to change her password.

1. Configure **Groups and roles**.
    1. Next to Groups, select **0 groups selected**.  This displays the available groups.  Notice the list of available groups.
    2. Select **Operations**, you may need to scroll down, then press **Select**. Notice how the text next to groups has been updated to reflect 1 groups selected.  
    3. Next to Roles, select **User**. The list of Directory roles appears.  Scroll down to view the various built-in roles, to view the various roles, but don’t change the user role.  Close out of this window by select the **X** on the top right-hand corner of the page.

1. Configure **Settings**
    1. Block sign in:  **No** (leave the default setting).
    1. Usage location: **United States** (select the drop-down then scroll down to find this option).  Configuring usage location is required for assigning licenses.

1. From the bottom of the page, select the **Create** button.

1. Verify the user appears on the user list (names are listed in alphabetical order).

1. From the user list select the user you just created, **Sara Perez**.  The profile page opens.

1. The left navigation panel shows the various options that can be configured for the user.  Select **Groups**.  Here you can see additional information about the group.  Verify the Operations group is listed (it may take several minutes for the group assignment to show up).  Note:  you will also see the Contoso group, although we only assigned one group when we created the user.  This is a result of a preconfigured policy, in the tenant, that automatically assigns new users to the Contoso group.

1. From the left navigation panel select **Licenses**.  Notice that there are no license assignments found for this user.  

1. To add a license select **+ Assignments** from the top of the main window.

1. Under Select licenses, select **Office 365 E3** and **Windows 10 Enterprise E3** then select the **Save** button on the bottom of the screen. A notification on the top right corner of the screen should show that license assignments succeeded.

1. Select the **X** on the top right of the screen to close the License assignments window.

1. Select the **Refresh icon** at the top of the page to confirm the license assignments.

1. From the left navigational panel select **Authentication methods**

1. call out the description that says, Here, you can set the ​phone numbers and email addresses that users use to perform multi-factor authentication​ and self-service password reset, and reset a user’s password.  Enter a mobile phone for mobile device that you have access to.  You may use this as part of a subsequent demo for SSPR and/or MFA.

1. Select the **X** on the top right corner of the page.  This returns you to the user list.

1. Select the **X** on the top right corner of the page.  This returns you to the main page for the Contoso tenant.

1. You have successfully created and configured a user in Azure Active Directory.

1. Sign out from all the browser tabs by clicking on the user icon next to the email address on the top right corner of the screen. Then the close all the browser windows.

#### Demo Part 2 (Optional):  In this step you will sign in as Sara Perez, for the first time.

1. Open Microsoft Edge.

1. In the address bar enter **login.microsoft.com**.

1. Sign in as **sara@WWLxZZZZZ.onmicrosoft.com**, (where ZZZZZZ is your unique tenant ID provided by your lab hosting provider).

1. Enter the temporary password **Naja8996**.

1. You are now prompted to Update your password. In the Current password field, enter **Naja8996**.

1. In the New password field enter, **SC900-Lab**.  In the Confirm your password field enter SC900-Lab, then select Sign in.  Note: As a best practice, a more secure password should be used. This password is chosen, for expediency and only for the purpose of this lab.

1. You should now be successfully signed-in to Microsoft 365.

1. **Sign out** from all the browser tabs by clicking on the user icon next to the email address on the top right corner of the screen. Then the close all the browser windows.

#### Review
In this demo, you showed the process of creating a new user and the different setting that can be configured, including groups to which the user can be assigned, the availability of roles, and assigning of user licenses.