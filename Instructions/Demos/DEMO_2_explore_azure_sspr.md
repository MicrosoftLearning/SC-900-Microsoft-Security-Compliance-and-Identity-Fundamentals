---
Demo:
    title: 'Explore Azure AD Authentication with self service password reset'
    module: 'Module 2 Lesson 3: Describe the capabilities of Microsoft Identity and access management solutions: Describe the different authentication methods of Azure AD'
---

# Demo: Explore Azure AD Authentication with self service password reset

## Demo scenario

In this demo, you will walk show the process of enabling self-service password reset.  You will then assume the role of a user to show the process of registering for SSPR.  Lastly, you as the admin, will be able to view audit logs and usage data & insights for SSPR.

## Instructions

#### Demo Part 1: SETUP - INSTRUCTOR DO THIS BEFORE THE CLASS TIME TO SAVE TIME.  In this part of the demo you will add the user to the SSPRSecurityUsers group AND you will reset Adele Vance (or other user's) password.

1. Open Microsoft Edge.

2. In the address bar enter **portal.azure.com** and sign in with your admin credentials.
    1. In the Sign in window enter **admin@WWLxZZZZZZ.onmicrosoft.com** (where ZZZZZZ is your unique tenant ID provided by your lab hosting provider) then select **Next**.
    1. Enter the admin password which should be provided by your lab hosting provider. Select **Sign in**.
    1. When prompted to stay signed- in, select **Yes**.

3. Select **Azure Active Directory**.  

4. From the left navigation panel, select **Groups**.

5. A list of existing groups is displayed.  Select **Load more** from the bottom of the page and scroll down until you find ****SSPRSecurityUsers**, then select it.  It will take you to the configuration option for this group.

6. From the left navigation pane, select **Members**.

7. From the top of the page, select **+ Add members**.  

8. In the Search box, enter **Adele**.  Once the user, **Adele Vance**, appears below the search box, select it then press **Select** from the bottom of the page.

9. Close out of the SSPRSecurityUsers window, selecting the **X** on the top right corner of the screen,

10. Return to the Active Directory page, by selecting **Contoso** from the top left corner of the screen, just above where it says Groups, to return to the Contoso Azure Active Directory page.

11. From the left navigation panel select **Users**.

12. Select **Adele Vance** from the list of users.

13. Select **Reset password** from the top of the page. Since you have not previously signed in as Adele Vance, you will need to reset the password

14. When the password reset window opens, select **Reset Password**.  IMPORTANT, make a note of the new password, as you will need it in a subsequent task, to be able to sign in as the user.

15. Close the password reset window by selecting the **X** at the top right corner of the page.

16. Close the Adele Vance window by selecting the **X** at the top right corner of the page.

17. Close the Users window by selecting the **X** at the top right corner of the page.

18. Keep the  Contoso Overview window open as you will use it in the subsequent task.

#### Demo Part 2: In this part of the demo, will walk through the process of configuring Password reset for users, including configuration of the types of authentication methods to use.

1. Go to the Contoso – Microsoft Azure tab that is open on your browser. If you previously closed the tab, open a browser page and in the address bar, enter portal.azure.com and select Azure Active Directory.  You should be logged in as admin, in the Azure portal, if not, sign back in.

1. From the left navigation pane, select **Password reset**.  

1. The properties for self service password reset are displayed.  Ensure that **Self service reset** is selected for the group which is listed, the SSPRSecurityUsers.  
    1. put your cursor over the information icon next to where it says "select group" and call out that this is where you add users or groups that will be enabled for SSPR. Call out that the user, Adele Vance, for whom you will be showing the process of registering for SSPR is already in this group.  Show how you can add a group Select **SSPRSecurityUsers**. Do not select any additional groups. Close the window by selecting the **X** on the top right of the screen.
    1. Note the light blue information box and call out it out to learners - These settings only apply to end users in your organization. Admins are always enabled for self-service password reset and are required to use two authentication methods to reset their password.

1. From the left navigation panel of Password reset, select **Authentication Methods**.

1. In the Number of methods required to rest, select **1**. Note the information box on the screen.

1. Call out the different methods available to users, including the point that SSPR supports security questions.  **Email** and **Mobile phone (SMS only)** should already be checked; if not, select them.  From the top of the page, select **Save**.  You will see a notification on the top right corner of the screen indicating Password reset policy was saved. 

1. From the left navigation panel of Password reset, select **Registration**.  
    1. Ensure the setting to Require users to register when signing in is set to **Yes**.  Take note of the information box - hover your mouse over it and call it out to the learners.
    1. Leave the Number of days before users are asked to re-confirm their authentication information, to the default of 180.

1. From the left navigation panel of Password reset, select **Notifications**.  

1. Ensure the setting to Notify users on password resets is set to **Yes**.  Leave the setting for Notify all admins when other admins reset their password to No.

1. Note how the Password reset navigation pane also includes options to view audit logs and Usage & insights.

1. **Sign out** from all the browser tabs by clicking on the user icon next to the email address on the top right corner of the screen. Then the close all the browser windows.

#### Demo Part 3:  In this task you, as user Adele Vance, will go through the registration process for self service password reset.  This task requires that you have access to a mobile device where you can receive text messages or a personal email account that you can access.

1. Open Microsoft Edge.

2. In the address bar enter **login.microsoftonline.com**.

3. Sign in as Adele Vance,
    1. In the Sign in window enter **AdedleV@WWLxZZZZZZ.onmicrosoft.com** (where ZZZZZZ is your unique tenant ID provided by your lab hosting provider) then select **Next**.
    1. Enter the password you noted in the earlier task. Select **Sign in**.
    1. When prompted to stay signed- in, select **Yes**

4. Since this is your first sign in as Adele Vance, you will be prompted to reset your password.  Enter your old password.  For your new password enter **SC900-Lab**. Enter **SC-900-Lab** in the confirm password field.  Select **Sign in**.  Note: we are using this password only for the convenience of the demo. As a best practice you would typically enter a more secure password.

5. A pop-up displays indicating that More information is required.  This is because as a member of the SSPRSecurityUsers group, the configuration requires its members to register when they sign in.  Select the **Next** button.  

6. The “Keep your account secure” page opens.  The window that appears is for the Phone authentication method, if you don’t have a mobile device with you that is capable of receiving text messages and prefer to use an email, skip to the next step.  You are prompted to enter a phone number. Ensure the option **Text me a code** is enabled.   Enter the phone number where you can receive a text code and select the **Next button**.  A new window opens indicating a code was just sent to the phone you entered.  Enter the code your received and select **Next**. A window opens indicating Success and showing your Default sign-in method.  Select **Done**.  

7. Skip this step if you were able to configure SSPR with your mobile phone number.  Alternatively, you can setup a different method as shown on the bottom left of the window.  If you choose to setup a different method, select **I want to set up a different method**, a pop-up window shows up, asking Which method would you like to use?  From the drop down, select your preferred method, **Email**, then select the **Confirm** button.  Enter the email you would like to use then select **Next**.  A new window opens indicating a code was just sent to the email you entered.  Access the email you entered to obtain the code.  Enter the code your received and select **Next**. A window opens indicating Success and showing your Default sign-in method.  Select **Done**.

8. You can now complete your sign in.  You should be on the azure portal landing page.  If you see that your sign in time has expired, just reenter the password, SC900-Lab.

9. Sign-out of the Azure portal and close your browser window.

#### Demo Part 4 (Optional): In this part of the demo, as user Adele Vance, will go through the process of resetting your password.

1. Open Microsoft Edge.

2. In the address bar enter login.microsoftonline.com.

3. Sign in as Adele Vance, by entering your email **AdeleV@WWLxZZZZ.onmicrosoft.com** (where ZZZZZZ is your unique tenant ID provided by your lab hosting provider)and select the **Next** button. You may, instead, see a Pick an account window open, if so, select the account for Adele Vance.

4. From the Enter password window, select **Forgot my password**. 

5. The Get back into your account window opens.   Verify that the email for Adele Vance, AdeleV@WWLxZZZZ.onmicrosoft.com, is shown in the email or username box.  If not, enter it.  

6. In the empty box, enter the characters displayed in image or the words from the audio. Once you have entered them, select **Next**.

7. The screen shows Get back into your account and shows Verification step 1 > choose a new password. Leave the default setting **Text my mobile phone**.  You are prompted to enter your mobile phone number.  Once you have entered it, select the **Text button**.  If, during the registration you selected email, the Get back into your account window will indicate You will receive an email containing a verification code at your alternate email address.  Select **Email**. 

8. Enter the verification code then press **Next**.

9. In the next screen you are prompted to enter new password and confirm new password.  Enter those now and select the **Finish** button.

10. You will see a message on the screen that your password has been reset.  Select **click here** to sign in with your new password.

11. From the Pick an account information box, select **AdeleV@WWLxZZZZZZ.onmicrosoft.com**, enter your new password, then select the **Sign in** button.  If you are prompted to Stay signed in. select **No**.

12. You should now be in the Azure portal.

13. Sign out by selecting on the user icon next to the email address on the top right corner of the screen and selecting **Sign out**. Then close all the browser windows

#### Demo Part 5 (Optional):  You will briefly show how to view the Audit logs and the Usage & insights data associated with password reset.

1. Open Microsoft Edge.

2. In the address bar enter **portal.azure.com** 

3. Sign in with your admin credentials.
    1. In the Sign in window enter **admin@WWLxZZZZZZ.onmicrosoft.com** (where ZZZZZZ is your unique tenant ID provided by your lab hosting provider) then select **Next**.
    1. Enter the admin password which should be provided by your lab hosting provider. Select **Sign in**.
    1. When prompted to stay signed- in, select **Yes**.

4. Select **Azure Active Directory**.  

5. From the left navigation pane, select **Password rest**.

6. From the left navigation pane, select **Audit logs**.  Notice the information available and the available filters.  Also note that you can download logs.  

7. Select **Download**.  Note that you can format the download as CSV or JSON.  Close the window by selecting the **X** on the top right corner of the screen.

8. From the left navigation pane, select **Usage & insights**.

9. Notice the information available that pertains to Registration.  Note that it may take time to refresh this data, even after you do a refresh, so it may not yet reflect the registration or usage data from the previous task.

10. From the top of the page select **Usage** to view the number of Self-service password resets and account unlocks by method.  Note that it may take time to refresh this data, even after you do a refresh, so it may not yet reflect the usage data from the previous task.

11. Close the open browser tabs.

#### Review
In this demo, you showed process of enabling self-service password reset. With SSPR enabled, you will assumed the role of a user to show the process of registering for SSPR and also resetting your password.  Lastly, you as the admin, showed where view audit logs and usage & insights data for SSPR.