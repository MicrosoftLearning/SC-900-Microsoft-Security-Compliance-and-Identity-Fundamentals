<!---
---
Demo:
    Title: 'Azure AD Conditional Access'
    Learning Path/Module/Unit: 'Learning Path: Describe the capabilities of Azure Active Directory (Azure AD), part of Microsoft Entra; Module 3: Describe the access management capabilities of Azure AD; Unit 2: Describe Conditional Access in Azure AD'
---
--->


# Demo: Azure AD Conditional Access

This demo maps to the following Learn content:

- Learning Path: Describe the capabilities of Azure Active Directory (Azure AD), part of Microsoft Entra
- Module: Describe the access management capabilities of Azure AD
- Unit: Describe Conditional Access in Azure AD

## Demo scenario

In this demo you will walk through the various options available for a conditional access policy.

1. Go to the **Contoso – Microsoft Azure** tab that is open on your browser. If you previously closed the tab, open a browser page and in the address bar, enter portal.azure.com and select Azure Active Directory. You should be logged in as admin, in the Azure portal, if not, sign back in.

1. From the left navigation panel, select **Security**.

1. From the left navigation panel, select **Conditional Access**.

1. The Conditional Access Policies screen is displayed. Any existing Conditional Access Policies are listed here. To show the settings associated with conditional access, select **+ New policy**.

1. In the **Name** field, you would simply enter a name for the policy.

1. Note that you have several options under **Assignments**.  Since conditional access policies are like if/then statements, the assignments settings are like the “if” statements.
    1. **Users and groups** - hover your mouse over the information icon next to where it says “Users and groups” and call out that this is where you set the users and groups in the directory that the policy applies to. Select **0 users and groups selected**.  You will now see the option to Include or Exclude users or groups. Select and call out the settings available for the **Include** tab and then select and speak to the settings available for the **Exclude** tab.
    1. **Cloud apps or actions** - hover your mouse over the information icon next to where it says “Cloud apps or actions” and call out that this is where you set the applications used or actions performed by the user, for the conditional access policy.  Select **No cloud apps or actions selected**.
        1. Select the drop-down arrow in the box below where it says **Select what this policy applies to** and note the options.  Leave the default setting – Cloud apps.
        1. Select and call out the settings available for the Include tab. Under the **Include** tab, choose **Select Apps**.  Notice the window that opens where you can select form a list of applications.  Don’t select anything, close out of this window by selecting the **X** on the top-right corner of the window. Go back to choosing **None** to remove the error.
        1. Then select and speak to the settings available for the **Exclude tab**.  Here again you can select specific apps to exclude.
    1. **Conditions** - hover your mouse over the information icon next to where it says “Conditions” and call out that this sets when the policy will apply. Select **0 conditions selected**. Speak to the different “signals” listed.   Select a few of the options by first selecting the information icon to define what it is and then selecting **Not configured** for the specific item to show the various options.
        1. **User risk** - A user risk represents the probability that a given identity or account is compromised. These risks are calculated offline using Microsoft's internal and external threat intelligence sources.
        1. **Sign-in risk** - A sign-in risk represents the probability that a given authentication request isn't authorized by the identity owner. Examples may include is the sign-in is from an anonymous IP address or atypical travel, etc.
        1. **Device Platform** - Platform the user is signing in from. For example, 'iOS’.
        1. **Location** - Location (determined using IP address range) the user is signing in from
        1. **Client apps** - Software the user is employing to access the cloud app. For example, 'Browser’

1. **Access Controls** – going back to the analogy that conditional access policies are like if/then statements, the access controls are analogous to the “then” statement.
    1. **Grant** - Hover your mouse over the information icon next to where it says “Grant” for the description.  Select **0 controls selected** to show the different options.  Speak to some of these.  Specifically call out the option to **Require multi-factor authentication**, under Grant Access and how this can be used to provide very granular control as to when to require MFA.   Also call out that you can set multiple controls and require all or just one of the selected controls.
    1. **Session** - Hover your mouse over the information icon next to where it says “Session” for the description.  Call out that Session controls enable limited experience within a cloud app.  For example, the user may be able to access the cloud app but will be blocked from downloading any content or printing., as examples.  This is a more complex topic so keep this simple.

1. Once a policy is configured you can enable a policy by selecting **On**, then press the **Create** button to create a policy.

1. Select the **X** on the top right corner of the page to close out of the policy, then select Microsoft Azure on the blue bar at the top of the page to return to the Azure Portal home page.

1. Keep this browser page open for the next demo.

### Review

In this demo you walked through the various options available for a conditional access policy.
