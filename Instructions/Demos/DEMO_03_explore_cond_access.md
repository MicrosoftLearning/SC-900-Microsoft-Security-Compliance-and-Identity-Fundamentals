<!---
---
Demo:
    Title: 'Azure AD Conditional Access'
    Learning Path/Module/Unit: 'Learning Path: Describe the capabilities of Microsoft Entra; Module 3: Describe access management capabilities of Microsoft Entra ID; Unit 2: Describe Conditional Access'
---
--->

# Demo: Azure AD Conditional Access

This demo maps to the following Learn content:

- Learning Path: Describe the capabilities of Microsoft Entra
- Module: Describe access management capabilities of Microsoft Entra ID
- Unit: Describe Conditional Access

## Demo scenario

In this demo, you'll walk through the various options available for a conditional access policy.

1. Return to the open browser tab titled "Home-Microsoft Entra admin center."  If you previously closed that browser tab open Microsoft Edge and login to the tenant, per the steps that follow.

    1. In the address bar, enter **admin.microsoft.com** to access the Microsoft 365 admin center.

    1. Sign in with your admin credentials.
        1. In the Sign-in window, enter **admin@WWLxZZZZZZ.onmicrosoft.com** (where ZZZZZZ is your unique tenant ID provided by your lab hosting provider) then select **Next**.
        1. Enter the admin password that should be provided by your lab hosting provider. Select **Sign in**.
        1. When prompted to stay signed- in, select **Yes**.

    1. From the left navigation pane of the Microsoft 365 admin center, select **Show all**.

    1. Under Admin centers, select **Identity** (you may need to scroll down).  A new browser page opens to the overview page of the Microsoft Entra admin center. Here you will see basic information about your Contoso tenant. If you scroll down the main window you will also see information about alerts, my feed, feature highlights, and more.

1. From the left navigation pane, expand **Protection** then select **Conditional Access**.

1. The Conditional access overview page is displayed.  Here you will see tiles showing the Policy summary and general alerts.  From the left navigation panel, select **Policies**.

1. The Conditional Access Policies screen is displayed. Any existing Conditional Access Policies are listed here. To show the settings associated with conditional access, select **+ New policy**.

1. In the **Name** field, you would enter a name for the policy.

1. Note that you have several options under **Assignments**.  Since conditional access policies are like if/then statements, the assignments settings are like the “if” statements.
    1. **Users** - hover your mouse over the information icon next to where it says “Users” and call out that this is where you select the identities in the directory that the policy applies to, including users, groups, and service principals. Select **0 users and groups selected**.  You'll now see the option to Include or Exclude users or groups. Select and call out the settings available for the **Include** tab and then select and speak to the settings available for the **Exclude** tab.
    1. **Target resources** - Select **Target resources**.  Here you control access based on all or specific network access traffic, cloud apps or actions.  Expand the field beneath where it says select what this policy applies to.  Here you can select if the policy applies to cloud apps, user actions, or authentication context.  
        1. Select **Cloud apps** then under the Include tab, select the option **Select apps** then underneath where it says **Select**, select **None**, a window will open to select one or more of the apps for which the policy will apply.
        1. Close out of the Select cloud apps window by selecting the **X** on the top right corner of the window.
        1. As time permits you may choose to go through the other options (user actions and authentication context) to see the configuration options for each.
    1. **Conditions** - hover your mouse over the information icon next to where it says “Conditions” and call out that this sets conditions which define when the policy will apply. For example, 'location. Select **0 conditions selected**. Speak to the different “signals” listed.   Select a few of the options by first selecting the information icon to define what it is and then selecting **Not configured** for the specific item to show the various options.
        1. **User risk** - A user risk represents the probability that a given identity or account is compromised. These risks are calculated offline using Microsoft's internal and external threat intelligence sources.
        1. **Sign-in risk** - A sign-in risk represents the probability that a given authentication request isn't authorized by the identity owner. Examples may include is the sign-in is from an anonymous IP address or atypical travel, etc.
        1. **Device Platform** - Platform the user is signing in from. For example, 'iOS’.
        1. **Location** - Location (determined using IP address range) the user is signing in from
        1. **Client apps** - Software the user is employing to access the cloud app. For example, 'Browser’
        1. **Filter for devices** - When creating Conditional Access policies, administrators can target or exclude specific devices in their environment. Admin can target specific devices using supported operators and properties for device filters and the other available assignment conditions in your Conditional Access policies.

1. **Access Controls** – going back to the analogy that conditional access policies are like if/then statements, the access controls are analogous to the “then” statement.
    1. **Grant** - Hover your mouse over the information icon next to where it says “Grant” for the description.  Select **0 controls selected** to show the different options.  Speak to some of these.  Specifically call out the option to **Require multi-factor authentication**, under Grant Access and how this can be used to provide granular control as to when to require MFA.   Also call out that you can set multiple controls and require all or just one of the selected controls.
    1. **Session** - Hover your mouse over the information icon next to where it says “Session” for the description.  Call out that Session controls enable limited experience within a cloud app.  For example, the user may be able to access the cloud app but will be blocked from downloading any content or printing, as examples.  This is a more complex topic so keep this simple.

1. Once a policy is configured you can enable a policy by selecting **On**, then press the **Create** button to create a policy.

1. Select the **X** on the top right corner of the page to close out of the policy, then select Microsoft Azure on the blue bar at the top of the page to return to the Azure portal home page.

1. Close your open browser tabs as this concludes the demos related to Microsoft Entra.

### Review

In this demo, you walked through the various options available for a conditional access policy.
