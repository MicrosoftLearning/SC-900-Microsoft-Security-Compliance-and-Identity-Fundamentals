<!---
---
Lab:
    Title: 'Explore insider risk management in Microsoft Purview'
    Learning Path/Module/Unit: 'Learning Path: Describe the capabilities of Microsoft compliance; Module 4: Describe the insider risk capabilities in Microsoft Purview; Unit 2: Describe insider risk management'
---
--->

# Lab: Explore insider risk management in Microsoft Purview

This lab maps to the following Learn content:

- Learning Path: Describe the capabilities of Microsoft compliance
- Module: Describe the insider risk capabilities in Microsoft Purview
- Unit: Describe insider risk management

## Lab scenario

In this lab, you'll walk through the process of setting up an insider risk policy, along with the basic prerequisites to configure and use insider risk management policies.  Note:  this lab will only provide visibility into what is required for setting up Insider risk management and options associated with creating a policy.  This lab does not include a task to trigger the policy, as the number of events that would need to occur to trigger a policy and the time required are outside of the scope of this exercise.

**Estimated Time**: 45-60 minutes

### Task 1

In this task you, as the global administrator, will enable permissions for Insider Risk Management.  Specifically, you'll add users to the Insider Risk Management role group to ensure that designated users can access and manage insider risk management features.  It may take up to 30 minutes for the role group permissions to apply to users across the organization.

1. Open the browser tab for home page of Microsoft Purview.  If you previously closed it, open a browser tab and enter **https://admin.microsoft.com**. Sign in with the admin credentials for the Microsoft 365 tenant provided by the authorized lab hoster (ALH). From the left navigation pane of the Microsoft 365 admin center, select **Show all** then select **Compliance**.  A new browser page opens to the welcome page of the Microsoft Purview compliance portal.  

1. From the left navigation panel, expand **Roles & scopes** then select **Permissions**.

1. Under Microsoft Purview solutions, select **Roles**.

1. In the search field, enter **Insider risk** then select the search icon (magnifying glass).  Notice the numerous roles that show up.  Each of these has different access levels.  Select **Insider risk management** and review the description.  Scroll down to where it shows members and note that MOD Administrator and Megan Bowen are listed. Close the window by selectin the **X** on the top right of the window..

1. From the left navigation panel, select **Home** to return to the Microsoft Purview compliance portal page.

1. Keep this browser tab open, as you'll come back to it in a subsequent task.

### Task 2 (SKIP if you did the setup lab task to enable the audit log)

Insider risk management uses Microsoft 365 audit logs for user insights and activities identified in policies and analytics insights. In this task, you'll enable the Audit log search capability. Note:  It may take several hours after you turn on audit log search before you can return results when you search the audit log.  Although it can take several hours before you can search the audit log, it will not impact the ability to complete other tasks in this lab.

1. Select the browser tab labeled, **Home-Microsoft 365 compliance**.  If you previously closed this browser tab, open Microsoft Edge, and in the address bar enter **compliance.microsoft.com** and sign in with your admin credentials.

1. In the left navigation panel, under solutions, select **Audit**.

1. Verify that the **New Search** tab is selected (underlined).

1. Once you land on the Audit page, wait 2-3 minutes.  If Auditing is NOT enabled, you'll see a blue bar on the top of the page that says start recording user and admin activity.  Select **Start recording user and admin activity**.  Once auditing is enabled, the blue bar disappears.  If the blue bar is not present, then auditing is already enabled, and no further action is required.

1. Return to the home page of the Microsoft Purview compliance portal by selecting **Home** from the left navigation panel.

1. Keep this browser tab open, as you'll use it in the next task.

### Task 3

In this task, you'll walk through the settings associated with the Insider Risk Management solution.  Insider risk management settings apply to all insider risk management policies, regardless of the template you choose when creating a policy.

1. You should be on the Microsoft Purview compliance portal home page. If not, Open the browser tab **Home - Microsoft 365 compliance**.

1. From the left navigation panel under Solutions, select **Insider risk management**.

1. Before getting started with setting up a policy, there are some settings that an admin should be familiar with and configure to as needed for their organization. From the Insider Risk Management page, select the **setting cog icon** on the top-right corner of the Insider risk management window to access Insider Risk settings.  
    1. Verify you are in the **Privacy** tab:  for users who perform activities matching your insider risk policies, this setting will determine whether to show their actual names or use anonymized versions to mask their identities.  For the purpose of this walk-through, you can leave the default setting.
    1. Select the **Policy indicators** tab. Once a policy triggering event occurs, activities that map to the selected indicators are used in determining the risk score, for the user. Policy indicators selected here are included the Insider risk policy templates.  Scroll to view all the indicators available and any associated information. Under **Office indicators**, select **Select all**, then select **Save** at the bottom of the page (you'll need to scroll down).
    1. Select the **Policy timeframes** tab. The timeframes you choose here go into effect for a user when they trigger a match for an insider risk policy.   The Activation window determines how long policies will actively detect activity for users and is triggered when a user performs the first activity matching a policy. Past activity detection Determines how far back a policy should go to detect user activity and is triggered when a user performs the first activity matching a policy.  Leave the default values.
    1. Select the **Intelligent detections** tab. Review the options here.  Note the domains settings and how they relate to the indicators.
    1. Explore other items listed in the settings and note that many are in preview.

1. To return to the Insider risk management overview, select **Insider risk management** from the top-left corner of the page, above where it says Settings.

1. Keep this browser tab open, as you'll use it in the next task.

### Task 4

In this task, you'll walk through the settings for creating a policy.  The objective is simply to get a sense of the various options and flexibility associated with creating a policy.

1. You should be on the Insider risk management page.  If not already there, open the browser tab labeled, **Insider risk management - Microsoft 365 compliance**.

1. From the Insider risk management overview page, select the **Policies** tab then select **+ Create policy**.  Configure each of the following policy tabs.

    1. Policy template: Under the Data leaks category, select **Data leaks**.  Read the details associated with this template. Under prerequisites, DLP policy is shown with a checkmark in a green circle to indicate that the prerequisite is satisfied.  There's a DLP policy that was preconfigured for this lab tenant. Select **Next**. 
    1. Name and description:  enter a name, **SC900-InsiderRiskPolicy**, then select **Next**.
    1. Users and groups:  Review the information box.  Leave the default setting, **Include all users and groups**.  Select **Next**.
    1. Content to prioritize: Per the description, Risk scores are increased for any activity that contains priority content, which in turn increases the chance of generating a high severity alert. For simplicity, select **I don't want to prioritize content right now**, then select **Next**.
    1. Decide whether to score only activity with priority content:  Leave the default setting **Get alerts for all activity**, then select **Next**.
    1. Triggers: The triggering event determines when a policy will begin to assign risk scores to a user's activity.  You can choose from an existing DLP policy or if the user performs an exfiltration activity. Select **User matches a data loss prevention (DLP) policy** then from the drop-down select **U.S. Financial Data**. Select **Next**.
    1. Indicators: Note that all the office indicators you selected in the previous task are selected (you can see this be selecting the down arrow key next to Office indicators), then select **Next**.
    1. On the Detection options page, leave all the default settings, but read the description associated with the various options and hover over the information icon to get more detailed information on a specific setting.  Select **Next**.
    1. On the page to Decide whether to use default or customer indicator thresholds, leave the default setting **Default thresholds**, then select **Next**.
    1. Finish:  review the settings, select **Submit**.
    1. Review the description of what happens next then select **Done**.

1. You're back on the Policies tab of the Insider risk management page.  The policy you created will be listed.  If you don't see it, select the **Refresh** icon.

1. As an admin, you can immediately start assigning risk scores to users based on activity detected by the policies you selected. This bypasses the requirement that a triggering event (like a DLP policy match) is detected first.  An admin would do this by selecting the empty square next to the policy name to select the policy, then select **Start scoring activity for users**, which is shown above the policy table.  A new window opens that requires the admin to populate the available fields. Leave the fields empty as you won't configure this option, but for more information on why an admin would want to do this, select **Why would I do this??**.  Exit the window by selecting the **X** on the top right of the window.

1. From the left navigation panel, select **Home** to return to the landing page of the Microsoft Purview compliance portal.

1. Keep the browser tab open.

### Review

In this lab, you walked through the process of setting up an insider risk policy, along with the basic prerequisites to configure and use insider risk management policies.
