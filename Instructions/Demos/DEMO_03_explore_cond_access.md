---
Demo:
    title: 'Explore access management in Azure AD with Conditional'
    module: 'Module 2 Lesson 4: Describe the capabilities of Microsoft Identity and access management solutions: Explore the access management capabilities of Azure AD'
---


# Demo: Explore access management in Azure AD with Conditional

## Instructions

#### Demo Part 1: SETUP - INSTRUCTOR DO THIS BEFORE THE CLASS TIME

1. Open Microsoft Edge.  In the address bar enter **portal.azure.com**.

1. Sign in with your admin credentials.
    1. In the Sign in window enter **admin@WWLxZZZZZZ.onmicrosoft.com** (where ZZZZZZ is your unique tenant ID provided by your lab hosting provider) then select **Next**.
    1. Enter the admin password which should be provided by your lab hosting provider. Select **Sign in**.
    1. When prompted to stay signed- in, select **Yes**.

1. Select **Azure Active Directory**.  

1. From the left navigation panel select **Users**.

1. Select **Debra Berger** from the list of users.

1. Select **Reset password** from the top of the page. Since you have not previously signed in as Debra Berger you don’t know her password and will need to reset the password.

1. When the password reset window opens, select **Reset Password**.  IMPORTANT, make a note of the new password, as you will need it in a subsequent task, to be able to sign in as the user.

1. Close the password reset window by selecting the **X** at the top right corner of the page.

1. Close the Users window by selecting the **X** at the top right corner of the page.

1. Logout as admin by selecting on the user icon on the top right corner of the screen, then selecting **Sign in with a different account**

1. Sign in as Debra Berger to setup a permanent password to save time during the classroom demo and to avoid having to do have to do this at the same time you are showing the MFA registration process.
    1. In the Sign in window enter **DebraB@WWLxZZZZZZ.onmicrosoft.com** (where ZZZZZZ is your unique tenant ID provided by your lab hosting provider) then select **Next**.
    1. Enter the temporary password you noted in the previous step. Select **Sign in**.
    1. Since the password provided when you, as the admin, reset the password is temporary you need to update your password.  Enter the current password, then for the new password and confirm password fields enter **SC900-Lab**.
    1. When prompted to stay signed- in, select **No**

1. Sign out as Debra.

#### Demo Part 1: In this part of the demo you will go through the process of creating a conditional access policy in Azure AD.

1. Open Microsoft Edge.  In the address bar enter **portal.azure.com**.

1. Sign in with your admin credentials.
    1. In the Sign in window enter **admin@WWLxZZZZZZ.onmicrosoft.com** (where ZZZZZZ is your unique tenant ID provided by your lab hosting provider) then select **Next**.
    1. Enter the admin password which should be provided by your lab hosting provider. Select **Sign in**.
    1. When prompted to stay signed- in, select **Yes**.

1. Select **Azure Active Directory**.

1. From the left navigation panel, select **Security**.

1. From the left navigation panel, select **Conditional Access**.

1. The Conditional Access Policies screen is displayed. Any existing Conditional Access Policies are listed here. Select**New policy**.

1. In the Name field, enter **MFA Test Policy**.

1. Under Users and groups, select **0 users and groups selected**.

1. You will now see the option to Include or Exclude users or groups.  Make sure **Include** is selected (underlined).

1. Select the option for **Select users and groups** and select **Users and groups**.  The window to Select users and groups opens.  

1. In the Search bar, enter **Debra**.  Select **Debra Berger** from beneath the search bar, then press the **Select** button on the bottom of the page.  Note to call out, a common practice is to assign the policy to users in a group.  For the purpose expediency with this demo, we will assign the policy to a specific user.  

1. Under Cloud apps or actions, select **No cloud apps or actions selected**.

1. You will now see the option to Include or Exclude cloud apps or user actions.  Make sure **Cloud apps** is highlighted and **Include** is selected (underlined), then select **Select apps**.  The window to Select Cloud apps opens.

1. In the search bar, enter **Azure**.  From the search results that appear under the search box, select **Microsoft Azure Management**, then press **Select** at the bottom of the page.  Notice the warning.  

1. Under Conditions, select **0 conditions selected**.  Notice the different options you can configure.  Through the policy, you can control user access based on signals from conditions like risk, device platform, location, client apps, or device state.  For example, you could include a condition for the policy to apply for any location except selected or trusted locations such as your headquarters’ network.  For this policy, do not set any conditions.

1. Now you will set the access controls.  Under Grant, select **0 controls selected**.

1. The Grant window opens.  Ensure **Grant access** is selected and then select **Require multi-factor authentication**.  Under the section For multiple controls, leave the default **Require all the selected controls**.  Press **Select** at the bottom of the page.

1. AT the bottom of the page, Under Enable policy, select **On**, then press the **Create button**.

1. After a few seconds, the MFA Pilot policy should appear in the list of conditional access policies (if needed, select **Refresh** at the top of the page).

1. Sign out of Azure and close your browser windows.

#### Demo Step 3: In this part of the demo you will show the impact of the conditional access policy, from the perspective of the user, Debra Berger. You will first start by signing-in to an application that is not part of the conditional access policy then you sign in to an application that is included in the conditional access policy.  Recall that the policy requires the user to go through MFA when accessing a Microsoft Azure Management application, so this demo will also show the MFA registration process (you will need to have a mobile device to which you have access).

1. Open Microsoft Edge.  In the address bar of the browser, enter **https://login.microsoftonline.com/**.

1. Sign in as Debra Burger,
    1. In the Sign in window enter **DebraB@WWLxZZZZZZ.onmicrosoft.com** (where ZZZZZZ is your unique tenant ID provided by your lab hosting provider) then select **Next**.
    1. Enter the password **SC900-Lab**. Select **Sign in**..
    1. When prompted to stay signed- in, select **No**

1. You should be successfully logged in to your Microsoft 365 account.  MFA was not required for this application as it is not part of the policy.

1. Now you will attempt to access to an application that meets the criteria for MFA.  Open Microsoft Edge and in the address bar, enter https://portal.azure.com.

1. You will see a window indicating, More information required.  Select **Next**.  Note, this will initiate the MFA registration process, as this is the first time you are accessing the cloud app that that was identified in the conditional access policy.  This registration process is required only once.   An alternative to having the user go through the registration process is to have the admin configure the authentication method to use.

1. In the Keep your account secure window, you have the option to select the method to use for MFA.  Microsoft Authenticator is one option. For expediency in this lab exercise, you will choose a different method.  Select **I want to setup a different method**.  From the Chose a different method pop-up window, select the **drop-down arrow** and select **Phone** then select **Confirm**.

1. In the window that opens, ensure your country is selected then enter mobile phone number you wish to use and select, ensure that **Text me a code** is selected, then press **Next**.  The screen will display, "SMS verified. You phone was registered successfully".  Select **Next**. then select **Done**.  this completes the one-time registration process.

1. You will likely get a message indicating that your sign-in timed out.  Just enter the password **SC900-Lab** and select **Sign in**.

1. You will see a window prompting you to enter the code that was sent to your phone.  Enter the code and select **Next**.  This is the experience that you, as Gerhart, will experience anytime you access a Microsoft Azure Management cloud application, such as the Azure Portal, per the MFA policy.

1. You will see a window prompting you to enter the code that was sent to your phone.  Enter the code and select the **Verify** button.  When prompted to stay signed in, select **No**.

1. You should now be able to access the Azure portal.  The Azure portal is a Microsoft Azure Management application and therefore requires multi-factor authentication, per the conditional access policy that was created.  

1. Sign out by selecting on the user icon next to the email address on the top right corner of the screen and selecting Sign out. Then the close all the browser windows.

#### Review
In this demo you walked through the process of setting up a conditional access policy that requires users to go through MFA when they access Microsoft Azure Management cloud application.  Then, as a user you went through the registration process for MFA and saw the impact of the conditional access policy that required you to use MFA when accessing the Azure portal.