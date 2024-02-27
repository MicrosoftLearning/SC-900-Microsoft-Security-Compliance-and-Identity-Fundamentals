---
lab:
    title: 'Microsoft Entra self-service password reset'
---

<!---
---
Lab:
    Title: 'Explore Azure AD Authentication with self-service password reset'
    Learning Path/Module/Unit: 'Learning Path: Describe the capabilities of Azure Active Directory (Azure AD), part of Microsoft Entra; Module 2: Describe the authentication capabilities of Azure AD; Unit 4: Describe self-service password'
---
--->

# Lab: Microsoft Entra self-service password reset

This lab maps to the following Learn content:

- Learning Path: Describe the capabilities of of Microsoft Entra
- Module: Describe the authentication capabilities of Microsoft Entra ID
- Unit: Describe self-service password reset

## Lab scenario

In this lab, you, as an admin, will walk through the process of adding a user to the SSPR security group, which is already setup in your Microsoft 365 tenant. With SSPR enabled, you'll then assume the role of a user and go through the process of registering for SSPR and also resetting your password.  Lastly, you as the admin, will be able to view audit logs and usage data & insights for SSPR.

**Estimated Time**: 15-20 minutes

### Task 1

In this task you, as the admin, will walk through the some of the available configuration settings for SSPR.

1. Open the Microsoft Edge browser. In the address bar, enter **https://entra.microsoft.com** and sign in with the Microsoft 365 admin credentials provided by your authorized lab hoster (ALH).
    1. In the Sign-in window, enter **admin@WWLxZZZZZZ.onmicrosoft.com** (where ZZZZZZ is your unique tenant ID provided by your ALH) then select **Next**.
    1. Enter the admin password that should be provided by your lab hosting provider. Select **Sign in**.
    1. When prompted to stay signed- in, select **Yes**.

1. From the left navigation pane, expand the option for **Protection**, then select **Password reset**.  

1. The properties for self service password reset are displayed. Select the information icon next to where it says **Self services password reset enabled** to view what the description. Ensure that **Selected** is highlighted in blue. Now put your cursor over the information icon next to where it says **Select group** and note that it says, "Defines the group of users who are allowed to reset their own passwords." You must include users in the group, you can’t individually select users. Notice that there is a group already listed - SSPRSecurityGroupUsers (this group was preconfigured as part your Microsoft 365 tenant). Lastly, note the blue information box, "These settings only apply to end users in your organization. Admins are always enabled for self-service password reset and are required to use two authentication methods to reset their password."

1. From the left navigation panel of Password reset, select **Authentication Methods**.

1. In the Number of methods required to rest, select **1**. Note the information box on the screen.

1. Notice the different methods available to users.  **Email** and **Mobile phone (SMS only)** should already be checked; if not, select them.

1. From the left navigation panel of Password reset, select **Registration**.  

1. Ensure the setting to Require users to register when signing in is set to **Yes**.  Leave the Number of days before users are asked to reconfirm their authentication information, to the default of 180.   Take note of the information box on the page.

1. From the left navigation panel of Password reset, select **Notifications**.  

1. Ensure the setting to Notify users on password resets is set to **Yes**.  Leave the setting for Notify all admins when other admins reset their password to No.

1. Note how the Password reset navigation pane also includes options to view audit logs and Usage & insights.

1. Close the password reset window by selecting the **X** on the top-right corner of the window. This returns you to hte Microsoft Entra admin center.

1. Keep the Microsoft Entra window open.

### Task 2

In this task you, as the admin, will add the user you created in the previous lab exercise to the SSPR security group.

1. Open the browser tab for the home page of the Microsoft Entra Admin center **[entra.microsoft.com](https://entra.microsoft.com)**. If needed, expand **Identity**.

1. From the left navigation panel, under "Identity", expand **Groups** then select **All groups**.

1. A list of existing groups is displayed. In the Search groups field, enter **SSPR**, then from the search results select **SSPRSecurityGroupUsers**.  It will take you to the configuration option for this group.

1. From the left navigation pane, select **Members**.

1. From the top of the page, select **+ Add members**.  

1. In the Search box, enter **Sara Perez**.  Once the user, **Sara Perez**, appears below the search box, select it then press **Select** from the bottom of the page.  You'll be returned to the members page.  Select **Refresh** from the top of the page. You should now see Sara Perez listed as a member in the SSPR security group.

1. Sign out from all the browser tabs by clicking on the user icon next to the email address on the top right corner of the screen. Then the close all the browser windows.

### Task 3

In this task you, as user Sara Perez, will go through the registration process for self service password reset.  This task requires that you have access to a mobile device where you can receive text messages or a personal email account that you can access

1. Open the Microsoft Edge and in the address bar enter **https://login.microsoft.com**.

1. Sign in as Sara Perez.

1. A pop-up displays indicating that More information is required.  This is because as a member of the SSPRSecurityGroupUsers group, the configuration requires its members to register when they sign in.  Select the **Next** button.  Note:  An alternative to having users do the registration, themselves, is for admins to directly configure the authentication methods when they add a user. This requires admins to know and set the ​phone numbers and email addresses that users use to perform self-service password reset, and reset a user’s password.

1. The “Keep your account secure” page opens.  The window that appears is for the Phone authentication method, if you don’t have a mobile device with you that is capable of receiving text messages, skip to the next step.  You're prompted to enter a phone number. Ensure the option **Text me a code** is enabled.   Enter the phone number where you can receive a text code and select the **Next button**.  A new window opens indicating a code was sent to the phone you entered.  Enter the code your received and select **Next**. A window opens indicating Success and showing your Default sign-in method.  Select **Done**.  
    1. Alternatively, you can set up a different method as shown on the bottom left of the window.  If you choose to set up a different method, select **I want to set up a different method**, a pop-up window shows up, asking Which method would you like to use?  From the drop-down, select your preferred method, **Email**, then select the **Confirm** button.  Enter the email you would like to use then select **Next**.  A new window opens indicating a code was sent to the email you entered.  Access the email you entered to obtain the code.  Enter the code your received and select **Next**. A window opens indicating Success and showing your Default sign-in method.  Select **Done**.

1. You can now complete your sign-in. If you see that your sign-in time has expired, just reenter the password.

1. Sign out from all the browser tabs by clicking on the user icon next to the email address on the top right corner of the screen. Then the close all the browser windows.

### Task 4 (Optional)

In this task you, as user Sara Perez, will go through the process of resetting your password

1. Open Microsoft Edge.

1. In the address bar, enter **https://login.microsoftonline.com**.

1. Sign in as Sara Perez, by entering your email **sara@WWLxZZZZ.onmicrosoft.com** (where ZZZZZZ is your unique tenant ID provided by your lab hosting provider)and select the **Next** button. You may, instead, see a Pick an account window open, if so, select the account for Sara Perez.

1. From the Enter password window, select **Forgot my password**.

1. The Get back into your account window opens.   Verify that the email for Sara Perez, sara@WWLxZZZZ.onmicrosoft.com, is shown in the email or username box.  If not, enter it.  

1. In the empty box, enter the characters displayed in image or the words from the audio. Once you've entered them, select **Next**.

1. The screen shows Get back into your account and shows Verification step 1 > choose a new password. Leave the default setting **Text my mobile phone**.  You're prompted to enter your mobile phone number.  Once you've entered it, select the **Text button**.  If during the registration you selected email, the Get back into your account window will that indicate you'll receive an email containing a verification code at your alternate email address.  Select **Email**.

1. Enter the verification code then press **Next**.

1. In the next screen, you're prompted to enter new password and confirm new password.  Enter those now and select the **Finish** button.

1. You'll see a message on the screen that your password has been reset.  Select **click here** to sign in with your new password.

1. From the Pick an account information box, select **sara@WWLxZZZZZZ.onmicrosoft.com**, enter your new password, then select the **Sign in** button.  If you're prompted to Stay signed in. select **No**.

1. You should now be in the Office portal.

1. Sign out by selecting on the user icon next to the email address on the top right corner of the screen and selecting **Sign out**. Then the close all the browser windows

### Task 5 (Optional)

In this task you, as the administrator, will briefly view the Audit logs and the Usage & insights data associated with password reset

1. Open Microsoft Edge.

1. In the address bar, enter **https://entra.microsoft.com** and sign in with the Microsoft 365 admin credentials provided by your authorized lab hoster (ALH).

1. You are in Microsoft Entra admin center.  From the left navigation pane, expand the option for **Protection**, then select **Password reset**.

1. From the left navigation pane, select **Audit logs**.  Notice the information available and the available filters.  Also note that you can download logs.  

1. Select **Download**.  Note that you can format the download as CSV or JSON.  Close the window by selecting the **X** on the top right corner of the screen.

1. From the left navigation pane, select **Usage & insights**.

1. Notice the information available that pertains to Registration.  Note that it may take time to refresh this data, even after you do a refresh, so it may not yet reflect the registration or usage data from the previous task.

1. From the top of the page select **Usage** to view the number of Self-service password resets and account unlocks by method.  Note that it may take time to refresh this data, even after you do a refresh, so it may not yet reflect the usage data from the previous task.

1. Close the open browser tabs.

### Review

In this lab, you, as an admin, went through the process of enabling self-service password reset. With SSPR enabled, you'll then assume the role of a user to go through the process of registering for SSPR and also resetting your password.  Lastly, you as the admin, learn where to access audit logs and usage & insights data for SSPR.
