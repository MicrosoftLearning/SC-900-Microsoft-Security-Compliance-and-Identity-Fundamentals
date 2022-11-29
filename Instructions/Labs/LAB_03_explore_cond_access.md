<!---
---
Lab:
    Learning Path: 'Describe the capabilities of Azure Active Directory (Azure AD), part of Microsoft Entra'
    Module: 'Describe the access management capabilities of Azure AD'
    Unit: 'Describe Conditional Access in Azure AD'
---
--->

# Lab: Explore access management in Azure AD with Conditional Access

This lab maps to the following Learn content:

- Learning Path: Describe the capabilities of Azure Active Directory (Azure AD), part of Microsoft Entra
- Module: Describe the access management capabilities of Azure AD
- Unit: Describe Conditional Access in Azure AD

## Lab scenario

In this lab, you will explore conditional access MFA, from the perspective of an admin and a user.  As the admin, will create an policy which will require a user to go through multi-factor authentication when accessing a cloud based Microsoft Azure Management application.  From a user perspective, you will see the impact of the conditional access policy, including the process to register for MFA.

**Estimated Time**: 30 minutes

### Task 1

In this task you, as the admin, will reset the password for the user Debra Berger.  This step is needed so you can initially sign in as the user in subsequent tasks.

1. Open Microsoft Edge.  In the address bar enter **portal.azure.com**.

2. Sign in with your admin credentials.
    1. In the Sign in window enter **admin@WWLxZZZZZZ.onmicrosoft.com** (where ZZZZZZ is your unique tenant ID provided by your lab hosting provider) then select **Next**.
    1. Enter the admin password which should be provided by your lab hosting provider. Select **Sign in**.
    1. When prompted to stay signed- in, select **Yes**.

3. On the top left corner of the screen, next to where it says Microsoft Azure, select the Show portal menu icon (the three horizontal lines also referred to as hamburger icon) then from the left navigation panel, under Favorites, select Azure Active Directory. If it is not listed under favorites, then in the search box, enter Azure Active Directory, then from the results list, select **Azure Active Directory**.

4. From the left navigation panel select **Users**.

5. Select **Debra Berger** from the list of users.

6. Select **Reset password** from the top of the page. Since you have not previously signed in as Debra Berger you don’t know her password and will need to reset the password.

7. When the password reset window opens, select **Reset Password**.  IMPORTANT, make a note of the new password, as you will need it in a subsequent task, to be able to sign in as the user.

8. Close the password reset window by selecting the **X** at the top right corner of the page, then close out of the Debra Berger window by selecting the **X** at the top right corner of the page.

9. Close the Users window by selecting the **X** at the top right corner of the page.

10. You are now back on the **Contoso | Overview** page.  Keep this window open.

### Task 2

In this task you will go through the process of creating a conditional access policy in Azure AD.

1. Open the browser tab, labeled Contoso – Microsoft Azure.   If you previously closed the browser tab, open Microsoft Edge and in the address bar enter portal.azure.com and sign in with your admin credentials, then select Azure Active Directory.  

2. From the left navigation panel, select **Security**.

3. From the left navigation panel, select **Conditional Access**.

4. The Conditional Access Policies screen is displayed. Any existing Conditional Access Policies are listed here. Select **+ New policy**.

5. In the Name field, enter **MFA Test Policy**.

6. Under Users or workload identities, select **0 users or workload identities selected**.

7. You will now see the option to Include or Exclude users or groups.  Make sure **Include** is selected (underlined).

8. Select the option for **Select users and groups** and select **Users and groups**.  The window to Select users and groups opens.  

9. In the Search bar, enter **Debra**.  Select **Debra Berger** from beneath the search bar, then press the **Select** button on the bottom of the page.  Note, a common practice is to assign the policy to users in a group.  For the purpose expediency with this lab, we will assign the policy to a specific user.

10. Under Cloud apps or actions, select **No cloud apps, actions, or authenticated contexts selected**.

11. You will now see the option to Include or Exclude cloud apps or user actions.  Make sure **Cloud apps** is listed in the field labeled Select what this policy applies to.  If not already listed, then select it from the drop-down. Make sure  **Include** is selected (underlined), then select **Select apps**, then underneath where it says Select, select **None**.  The window to Select Cloud apps opens.

12. In the search bar, enter **Azure**.  From the search results that appear under the search box, select **Microsoft Azure Management**, then press **Select** at the bottom of the page.  Notice the warning.  

13. Under Conditions, select **0 conditions selected**.  Notice the different options you can configure.  Through the policy, you can control user access based on signals from conditions like risk, device platform, location, client apps, or device state.  For example, you could include a condition for the policy to apply for any location except selected or trusted locations such as your headquarters’ network.  For this policy, do not set any conditions.

14. Now you will set the access controls.  Under Grant, select **0 controls selected**.

15. The Grant window opens.  Ensure **Grant access** is selected and then select **Require multifactor authentication**. Scroll down a bit on teh right window and under the section For multiple controls, leave the default **Require all the selected controls**.  Press **Select** at the bottom of the page.

16. At the bottom of the page, Under Enable policy, select **On**, then select **Create**.

17. After a few seconds, the MFA Pilot policy should appear in the list of conditional access policies (if needed, select **Refresh** at the top of the page).

18. Sign out of Azure and close your browser windows.

### Task 3

In this task you will see the impact of the conditional access policy, from the perspective of the user, Debra Berger. You will start first by signing-in to an application that is not included in the conditional access policy.  Then you will repeat the process for an application that is included in the conditional access policy.  Recall that the policy requires the user to go through MFA when accessing a Microsoft Azure Management application.  To use MFA, the user must first register the authentication method that will be used for MFA, for example a code sent to a mobile device or an authenticator application.

1. Sign in as Debra Burger. 
    1. In the Sign in window enter **DebraB@WWLxZZZZZZ.onmicrosoft.com** (where ZZZZZZ is your unique tenant ID provided by your lab hosting provider) then select **Next**.
    1. Enter the password you noted in the earlier task. Select **Sign in**.
    1. Since the password provided when you, as the admin, reset the password is temporary you need to update your password (this is not part of the MFA policy). Enter the current password, then for the new password enter **SC900-Lab**, then enter **SC900** again to confirm the password.
    1. When prompted to stay signed- in, select **Yes**.  You should be successfully logged in to your Microsoft 365 account. MFA was not required for this application as it is not part of the policy.

1. Now you will attempt to sign in to an application that meets the criteria for MFA. Open a new tab in portal.Microsoft Edge and in the address bar, enter **portal.azure.com**.

1. You will see a window indicating, More information required.  Select **Next**.  Note, this will initiate the MFA registration process, as this is the first time you are accessing the cloud app that that was identified in the conditional access policy.  This registration process is required only once.   An alternative to having the user go through the registration process is to have the admin configure the authentication method to use.

1. In the Keep your account secure window, you have the option to select the method to use for MFA.  Microsoft Authenticator is one option. For expediency in this lab exercise, you will choose a different method.  Select **I want to setup a different method**.  From the Chose a different method pop-up window, select the **drop-down arrow** and select **Phone** then select **Confirm**.

1. In the window that opens, ensure your country is selected then enter mobile phone number you wish to use.  Ensure that **Text me a code** is selected, then press **Next**.  You will receive a text message on your phone with a code that you will need to enter where it says enter code.  Enter the code you received, then press **Next**.  Once confirmed, the screen will display, "SMS verified. You phone was registered successfully".  Select **Next**. then select **Done**.  this completes the one-time registration process.

1. You should now be able to access the Azure portal.  The Azure portal is a Microsoft Azure Management application and therefore requires multi-factor authentication, per the conditional access policy that was created.  
    1. If you get a indicating that your sign-in timed out you, enter the password **SC900-Lab** and select **Sign in**. 
    1. You will see a window that requires you to verify your identity.  Select where it says Text =X XXXXXXX to receive a code on your mobile phone, enter the code and select **Verify**.
    1. If you are prompted to stay signed in, select **No**.

1. Sign out by selecting on the user icon next to the email address on the top right corner of the screen and selecting Sign out. Then the close all the browser windows.

### Review

In this lab you went through the process of setting up a conditional access policy that requires users to go through MFA when they access Microsoft Azure Management cloud application.  Then, as a user you went through the registration process for MFA and saw the impact of the conditional access policy that required you to use MFA when accessing the Azure portal.
