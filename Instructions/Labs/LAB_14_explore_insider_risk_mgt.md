---
lab:
  title: Explore insider risk management in Microsoft Purview
  module: Describe the data security solutions of Microsoft Purview
  description: 'This lab maps to the following Learn content:'
  duration: 60 minutes
  level: 300
  islab: true
  primarytopics:
  - Microsoft Purview
---

# Lab: Explore insider risk management in Microsoft Purview

This lab maps to the following Learn content:

- Learning Path: Describe the capabilities of Microsoft Priva and Microsoft Purview
- Module: Describe the data security solutions of Microsoft Purview
- Unit: Describe insider risk management in Microsoft Purview

## Lab scenario

In this lab, you'll walk through the process of setting up an insider risk policy, along with the basic prerequisites to configure and use insider risk management policies.  Note:  this lab will only provide visibility into what is required for setting up Insider risk management and options associated with creating a policy.  This lab does not include a task to trigger the policy, as the number of events that would need to occur to trigger a policy and the time required are outside of the scope of this exercise.

**Estimated Time**: 60 minutes

### Task 1

In this task you explore the different role permissions for Insider Risk Management and verify that specific users have already been included in the Insider Risk Management role group. Ensuring that users have the appropriate role permissions ensures that designated users can access and manage insider risk management features. When adding members to a role group, it may take up to 30 minutes for the role group permissions to apply to users across the organization.

1. Open the browser tab for home page of Microsoft Purview.  If you previously closed it, open a browser tab and enter **https://admin.microsoft.com**. Sign in with the admin credentials for the Microsoft 365 tenant provided by the authorized lab hoster (ALH). 

1. From the left navigation pane of the Microsoft 365 admin center, select **Show all** then select **Microsoft Purview**.  A new browser page opens to the welcome page of the Microsoft Purview portal.  

1. From the left navigation panel, select **Settings**, expand **Roles & scopes** then select **Role groups**.

1. In the search field, on the top right of the page, type **Insider risk** then hit Enter on your keyboard.  Notice the numerous roles that show up.  Each of these has different access levels.  Select **Insider risk management** and review the description.  Scroll down to where it shows members and note that MOD Administrator and Megan Bowen are listed. Close the window by selecting the **X** on the top right of the window..

1. From the left navigation panel, select **Home** to return to the Microsoft Purview portal page.

1. Keep this browser tab open, as you'll come back to it in a subsequent task.

### Task 2

In this task, you'll walk through the settings associated with the Insider Risk Management solution.  Insider risk management settings apply to all insider risk management policies, regardless of the template you choose when creating a policy.

1. You should be on the Microsoft Purview portal home page.

1. Before getting started with setting up a policy, there are some settings that an admin should be familiar with and configure as needed for their organization. From the left navigation pane, select **Settings** then select **Insider Risk Management**.  Here you'll explore some of the available settings.
    1. Select **Privacy**:  for users who perform activities matching your insider risk policies, this setting will determine whether to show their actual names or use anonymized versions to mask their identities.  For the purpose of this walk-through, you can leave the default setting.
    1. Select **Policy indicators**. Once a policy triggering event occurs, activities that map to the selected indicators are used in determining the risk score, for the user. Policy indicators selected here are included the Insider risk policy templates.  Scroll to view all the indicators available and any associated information.  Under **Office indicators**, select **Select all**. The options you select on this screen are included in your policy templates.
    1. Select **Policy timeframes**. The timeframes you choose here go into effect for a user when they trigger a match for an insider risk policy.   The Activation window determines how long policies will actively detect activity for users and is triggered when a user performs the first activity matching a policy. Past activity detection Determines how far back a policy should go to detect user activity and is triggered when a user performs the first activity matching a policy.  Leave the default values.
    1. Select **Intelligent detections**. Review the options here.  Note the domains settings and how they relate to the indicators.
    1. Explore other items listed in the settings and note that many are in preview.

1. From the left navigation pane, select **Solutions**, then select **Insider Risk Management**.

1. Keep this browser tab open, as you'll use it in the next task.

### Task 3

When creating a policy for Insider Risk Management, you have to options: a quick policy or a custom policy. Quick policy settings automatically populate from recommended best practices or on results from the latest analytics scan in your organization.  In this task, you'll walk through the settings for creating a custom policy. The objective is simply to get a sense of the various options and flexibility associated with creating a policy.

1. You should be on the overview page for Insider risk management.  If not already there, select **Solutions** from the left navigation pane, then select **Insider Risk Management** .

1. From the Insider risk management overview page, select the **Policies** tab, select **+ Create policy**, then select **Custom policy**. Configure each of the following policy tabs.

    1. Policy template: Under the Data leaks category, select **Data leaks**.  Read the details associated with this template. Under prerequisites, DLP policy is shown with a checkmark in a green circle to indicate that the prerequisite is satisfied.  There's a DLP policy that was preconfigured for this lab tenant. Select **Next**.
    1. Name and description:  enter a name, **`SC900-InsiderRiskPolicy`**, then select **Next**.
    1. Users and groups:  Review the information box.  Leave the default setting, **Include all users and groups**.  Select **Next**.
    1. Exclude users and groups (optional): Here you can list users and groups to exclude. Don't change anything. Select **Next**.
    1. Content to prioritize: Per the description, Risk scores are increased for any activity that contains priority content, which in turn increases the chance of generating a high severity alert. For simplicity, select **I don't want to prioritize content right now**, then select **Next**.
    1. Triggers: The triggering event determines when a policy will begin to assign risk scores to a user's activity.  You can choose from an existing DLP policy or if the user performs an exfiltration activity. Select **User matches a data loss prevention (DLP) policy** then from the drop-down select **U.S. Financial Data**. Select **Next**.
    1. Indicators: Expand **Office indicators**. Note how the Office indicators area already selected, this is based on the settings from the previous task.  You can deselect some selected indicators or add new ones by selecting Choose indicators. For this exercise, leave the current settings as and select **Next**.
    1. On the Detection options page, leave all the default settings, but read the description associated with the various options and hover over the information icon to get more detailed information on a specific setting.  Select **Next**.
    1. On the page to Decide whether to use default or customer indicator thresholds, leave the default setting **Apply thresholds provided by Microsoft**, then select **Next**.
    1. Finish:  review the settings, select **Submit**.
    1. Review the description of what happens next then select **Done**.

1. You're back on the Policies tab of the Insider risk management page.  The policy you created will be listed.  If you don't see it, select the **Refresh** icon.

1. As an admin, you can immediately start assigning risk scores to users based on activity detected by the policies you selected. This bypasses the requirement that a triggering event (like a DLP policy match) is detected first.  An admin would do this by selecting the empty square next to the policy name to select the policy, then select **Start scoring activity for users**, which is shown above the policy table.  A new window opens that requires the admin to populate the available fields. Leave the fields empty as you won't configure this option, but for more information on why an admin would want to do this, select **Why would I do this??**.  Exit the window by selecting the **X** on the top right of the window.

1. From the left navigation panel, select **Home** to return to the landing page of the Microsoft Purview portal.

1. Keep the browser tab open.

### Review

In this lab, you walked through the process of setting up an insider risk policy, along with the basic prerequisites to configure and use insider risk management policies.
