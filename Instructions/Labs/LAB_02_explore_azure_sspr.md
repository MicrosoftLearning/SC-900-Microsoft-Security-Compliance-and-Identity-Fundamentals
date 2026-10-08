---
lab:
  title: Microsoft Entra self-service password reset
  module: Describe the authentication capabilities of Microsoft Entra ID
  description: In this lab, you, as an admin, go through the process of enabling self-service password reset. With SSPR enabled, you'll then assume the role of a user to go through the process of registering for SSPR and also resetting your password. Lastly, you as the admin, learn where to access audit logs and usage & insights data for SSPR.
  duration: 45 minutes
  level: 200
  islab: true
  primarytopics:
    - Microsoft Entra
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

**Estimated Time**: 45 minutes

### Task 1

In this task you, as the admin, will walk through the some of the available configuration settings for SSPR.

1. Open the Microsoft Edge browser. In the address bar, enter **`https://entra.microsoft.com`** and sign in with the Microsoft 365 admin credentials provided by your authorized lab hoster (ALH).
    1. In the Sign-in window, enter **admin@WWLxZZZZZZ.onmicrosoft.com** (where ZZZZZZ is your unique tenant ID provided by your ALH) then select **Next**.
    1. Enter the admin password that should be provided by your lab hosting provider. Select **Sign in**.
    1. Depending on your lab hoster and if this is the first time you are logging in to the tenant, you may be prompted to complete the MFA registration process. If so, follow the prompts on the screen to setup MFA.
    1. Once you're signed-in, you're taken to the Microsoft 365 admin center page.

1. From the left navigation panel, make sure **Entra ID** is expanded, then scroll-down and select **Password reset**.  

1. The properties for self service password reset are displayed. Select the information icon next to where it says **Self services password reset enabled** to view what the description. Ensure that **Selected** is highlighted in blue. Now put your cursor over the information icon next to where it says **Select group** and note that it says, "Defines the group of users who are allowed to reset their own passwords." You must include users in the group, you can’t individually select users. Notice that there is a group already listed - SSPRSecurityGroupUsers (this group was preconfigured as part your Microsoft 365 tenant). Lastly, note the blue information box, "These settings only apply to end users in your organization. Admins are always enabled for self-service password reset and are required to use two authentication methods to reset their password."

1. From the left navigation panel of Password reset, select **Authentication Methods**.

1. In the Number of methods required to reset, select **1**. There is only one method listed, Security questions, but beneath that option is the option to **Use the auth methods policy to manage other authentication methods**.  
    1. Select **auth methods policy** to view the available authentication method policies
    1. Select **X** on the top-right of the page to return to the previous page.

1. From the left navigation panel of Password reset, select **Registration**.  

1. Ensure the setting to Require users to register when signing in is set to **Yes**.  Leave the Number of days before users are asked to reconfirm their authentication information, to the default of **180**.   Take note of the information box on the page.

1. From the left navigation panel of Password reset, select **Notifications**.  

1. Ensure the setting to Notify users on password resets is set to **Yes**.  Leave the setting for Notify all admins when other admins reset their password to **No**.

1. Note how the Password reset navigation pane also includes options to view audit logs and Usage & insights.

1. Close the password reset window by selecting the **X** on the top-right corner of the window. This returns you to hte Microsoft Entra admin center.

1. Keep the Microsoft Entra window open.

### Task 2

In this task you, as the admin, will add the user you created in the previous lab exercise to the SSPR security group.

1. Open the browser tab for the home page of the Microsoft Entra Admin center **`https://entra.microsoft.com`**.

1. From the left navigation panel, under **Entra ID**, select **Groups** and then select **All groups**.

1. A list of existing groups is displayed. In the Search groups field, enter **SSPR**, then from the search results select **SSPRSecurityGroupUsers**.  It will take you to the configuration option for this group.

1. From the left navigation pane, select **Members**.

1. From the top of the page, select **+ Add members**.  

1. In the Search box, enter **Sara Perez**.  Once the user, **Sara Perez**, appears below the search box, select it then press **Select** from the bottom of the page.  You'll be returned to the members page.  Select **Refresh** from the top of the page. You should now see Sara Perez listed as a member in the SSPR security group.

1. Sign out from all the browser tabs by clicking on the user icon next to the email address on the top right corner of the screen. Then the close all the browser windows.

### Task 3

In this task, you, as Sara Perez, will register security information for self-service password reset.

1. Open **Microsoft Edge**. In the address bar, enter `https://aka.ms/mysecurityinfo`.

1. Sign in as **Sara Perez** using the password from the previous lab.

1. On the **Security info** page, select **+ Add sign-in method**.

1. In the **Add a sign-in method** window, select **Microsoft Authenticator**.
   
1. Register Microsoft Authenticator as a sign-in method:
    1. On the **Install Microsoft Authenticator** page, if Microsoft Authenticator is already installed on your mobile device, select **Next**. Otherwise, install Microsoft Authenticator from the appropriate app store, and then select **Next**.
    1. On the **Set up your account in app** page, open Microsoft Authenticator on your mobile device, add an account, select **Work or school account**, and then select **Next**.
    1. On the **Scan the QR code** page, use Microsoft Authenticator to scan the QR code displayed on your screen, and then select **Next**.
    1. On the **Let's try it out** page, enter the number displayed on the screen in Microsoft Authenticator to approve the sign-in request.
    1. When the **Authenticator Added** message appears, select **Done**.

1. Confirm that **Microsoft Authenticator** appears as a sign-in method on the **Security info** page.

1. Sign out from all browser tabs by selecting the user icon next to the email address in the upper-right corner of the page, and then close all browser windows.

### Task 4 (Optional)

In this task, you, as Sara Perez, will reset your password using self-service password reset.

1. Open **Microsoft Edge**. In the address bar, enter `https://login.microsoftonline.com`.

1. Sign in as **Sara Perez** by entering **sara@WWLxZZZZZZ.onmicrosoft.com**, where `ZZZZZZ` is your unique tenant ID provided by your lab hosting provider, and then select **Next**. If the **Pick an account** page appears, select Sara Perez's account.

1. On the **Enter password** page, select **Forgot my password**.

1. On the **Get back into your account** page, verify that **sara@WWLxZZZZZZ.onmicrosoft.com** appears in the email or username field. If it doesn't, enter the account, and then select **Next**.

    > **Note:** If prompted for image verification, enter the characters displayed in the image or the words from the audio, and then select **Next**.

1. On the **Get back into your account** page, select **Approve a notification on my authenticator app**, and then select **Send Notification**.

1. Note the number displayed on the screen, and follow the instructions in Microsoft Authenticator on your mobile device to approve the request.

1. When prompted to choose a new password, enter and confirm the new password, and then select **Finish**.

1. When the password reset confirmation appears, select the **click here** link to sign in with your new password.

1. If the **Pick an account** page appears, select **sara@WWLxZZZZZZ.onmicrosoft.com**, enter the new password, and then select **Sign in**. If you're prompted to stay signed in, select **No**.

1. Confirm that you're successfully signed in to Sara's Microsoft account.

1. Sign out by selecting the user icon in the upper-right corner of the page, select **Sign out**, and then close all browser windows.
   
### Task 5 (Optional)

In this task you, as the administrator, will briefly view the Audit logs and the Usage & insights data associated with password reset

1. Open Microsoft Edge.

1. In the address bar, enter **`https://entra.microsoft.com`** and sign in with the Microsoft 365 admin credentials provided by your authorized lab hoster (ALH).

1. On the **Microsoft Entra admin center**, from the left navigation pane, expand the **Entra ID**, then select **Password reset**.

1. From the left navigation pane, select **Audit logs**.  Notice the information available and the available filters.  Also note that you can download logs.  

1. Select **Download**.  Note that you can format the download as CSV or JSON.  Close the window by selecting the **X** on the top right corner of the screen.

1. From the left navigation pane, select **Usage & insights**.

1. Notice the information available that pertains to Registration.  Note that it may take time to refresh this data, even after you do a refresh, so it may not yet reflect the registration or usage data from the previous task.

1. From the top of the page select **Usage** to view the number of Self-service password resets and account unlocks by method.  Note that it may take time to refresh this data, even after you do a refresh, so it may not yet reflect the usage data from the previous task.

1. Close the open browser tabs.

### Review

In this lab, you, as an admin, went through the process of enabling self-service password reset. With SSPR enabled, you'll then assume the role of a user to go through the process of registering for SSPR and also resetting your password.  Lastly, you as the admin, learn where to access audit logs and usage & insights data for SSPR.
