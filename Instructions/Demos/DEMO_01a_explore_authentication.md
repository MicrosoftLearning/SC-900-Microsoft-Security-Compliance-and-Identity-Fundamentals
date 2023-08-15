<!---
---
Demo:
    Title: 'Explore Microsoft Entra ID User Settings'
    Learning Path/Module/Unit: 'Learning Path: Describe the capabilities of Microsoft Entra; Module 2: Describe the authentication capabilities of Microsoft Entra ID; Unit 3: Describe authentication methods and Unit 4:  Describe multifactor authentication'
---
--->

# Demo: Authentication methods and MFA

This demo maps to the following Learn content:

- Learning Path: Describe the capabilities of Microsoft Entra.
- Module: Describe the authentication capabilities of Microsoft Entra ID.
- Units: Describe authentication methods and Describe multifactor authentication.

## Demo scenario

In this demo, you'll explore the various settings available for authentication in Microsoft Entra.

1. Open Microsoft Edge.

1. In the address bar, enter **admin.microsoft.com** to access the Microsoft 365 admin center.

1. Sign in with your admin credentials.
    1. In the Sign-in window, enter **admin@WWLxZZZZZZ.onmicrosoft.com** (where ZZZZZZ is your unique tenant ID provided by your lab hosting provider) then select **Next**.
    1. Enter the admin password that should be provided by your lab hosting provider. Select **Sign in**.
    1. When prompted to stay signed- in, select **Yes**.

1. From the left navigation pane of the Microsoft 365 admin center, select **Show all**.

1. Under Admin centers, select **Identity** (you may need to scroll down).  A new browser page opens to the overview page of the Microsoft Entra admin center. Here you will see basic information about your Contoso tenant. If you scroll down the main window you will also see information about alerts, my feed, feature highlights, and more.

1. From the left navigation pane, expand **Protection** then select **Authentication methods**.

1. Selecting authentication methods displays the policies page.  Here you will see the available authentication methods and if they are enabled.  We'll go through a few of these methods:.  
    1. Select **SMS**.  Read the description at the top of the page, "This authentication method delivers a one-time code via SMS to a user's phone, and the user then inputs that code to sign-in. SMS is usable for multi-factor authentication and Self-Service Password Reset; it can also be configured to be used as a first factor."
        1. A point to call out here is that some authentication methods can be used for MFA and/or SSPR.  Some can be used only as a primary form of authentication while others can only be used as a secondary form of authentication.
        1. To configure a particular authentication method, you need to enable it and then target which users and/or groups to include.  You can also select which groups to exclude.
        1. Don't change any settings.  Close out of the SMS settings page by select the **X** on the top right of the page.  
    1. Let's take a look at the voice call settings.  Select **Voice call**, from the description you can see an important difference.  Voice calls is not usable as a first-factor authentication method.
    1. Now select **Microsoft Authenticator**.  This is the flagship authentication methods.  
        1. Here you enable the features and target who to include.  You can do this for all users or groups. Once you have identified which users/groups to include you can identify specific groups to exclude.  
        1. On the **Configure** tab you can select if a specific feature is managed by Microsoft. This setting is a convenient way for an organization to allow Microsoft to enable or disable a feature by default. This can help an organization improve their security posture.
        1. Don't change any settings. Close out of the page, by selecting the **X** on teh top right corner of the page.
 
1. Now let's look at password protection. Select **Password Protection**.  Note the different configuration parameters available.  
    1. Select the information icon next to **Lockout threshold** to view the meaning of this parameter.  Currently it is set to 10, which means that there can be up to 10 failed sign-ins before the account is locked out.  Seems a bit high, so you can set to a different value.
    1. Select the information icon for each of the different parameters and speak to it, briefly.  You'll especially want to call out the custom banned password list.

1. Authentication strengths is a Conditional Access control that allows administrators to specify which combination of authentication methods can be used to access a resource. You'll see this in Conditional access.

1. From the left navigation pane for Authentication methods, select **Activity**.
    1. The **Registration** is shown with a blue underline.  Here  you can view registration activity for different authentication methods.
    1. Select **Usage** to view usage details and note that you can add different filters.

1. In this module you also spoke about multifactor authentication. You will cover more about MFA in the demo on conditional access, but you may want to take a minute to show some basic settings.  From Microsoft Entra admin center navigation panel, select **Multifactor authnentication**
    1. On the **Getting started** page, it shows that the best way to apply it to users is through conditional access, but there are some specific settings you configure here.
    1. Select **Account lockout** and call out the configurable lockout parameters.
    1. Select **Block/unblock users**, call out that here is where an admin can manually block/unblock users.  Note that a blocked user will remain blocked for 90 days unless manually unblocked.
    1. Select **Fraud alert**.  This allows admins to allow users to report fraud if they receive a two-step verification request that they didn't initiate.
    1. Select **Notifications**.  You can configure Microsoft Entra to send email notifications when users report fraud alerts. These notifications are typically sent to identity administrators, because the user's account credentials are likely compromised.

### Review

In this demo, you showed the authentication methods available in Microsoft Entra.  You also shows a few of the configurable parameters associated with multifactor authentication.
