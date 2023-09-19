<!---
---
Demo:
    Title: 'Microsoft Entra self-service password reset (SSPR)'
    Learning Path/Module/Unit: 'Learning Path: Describe the capabilities of Microsoft Entra; Module 2: Describe the authentication capabilities of Microsoft Entra ID; Unit 4: Describe self-service password reset'
---
--->

# Demo: Microsoft Entra self-service password reset (SSPR)

This demo maps to the following Learn content:

- Learning Path: Describe the capabilities of of Microsoft Entra
- Module: Describe the authentication capabilities of Microsoft Entra ID
- Unit: Describe self-service password reset

## Demo scenario

In this demo, you'll walk through the various settings associated with enabling self-service password reset.

1. Return to the open browser tab titled "Home-Microsoft Entra admin center."  If you previously closed that browser tab open Microsoft Edge and log in to **[entra.microsoft.com](https://entra.microsoft.com)** with your Microsoft 365 admin credentials.

1. From the left navigation pane, expand **Protection** then select **Password reset**.

1. The properties tab is highlighted.  In the Properties window, notice that SSPR can be enabled for None, Select, or All.
    1. Put your cursor over the information icon next to where it says "Self-services password reset enabled," and call out that you can choose "Selected" to restrict password reset to a limited group of users, vs, selecting for None or all.
    1. Put your cursor over the information icon next to where it says "select group" and call out that this is where you identify the group of users who are allowed to reset their own passwords.   You must include users in the group, you can’t individually select users.  Also, if you change the group, then the group you select replaces the group currently listed.  As such, it's recommended that you add users to the SSPR group.
    1. Note the light blue information box and call out it out to learners - These settings only apply to end users in your organization. Admins are always enabled for self-service password reset and are required to use two authentication methods to reset their password.

1. From the left navigation panel of Password reset, select Authentication Methods.
    1. Put your cursor over the information icon next to where it says "Number of methods required to reset”.  Call out that this sets the number of alternate methods of identification a user in this directory must have to reset their password.   Do no change the setting.
    1. Call out the different “methods available to users”, including the point that SSPR supports security questions. Select Security questions to show the options for using security questions. After you're done speaking about the options go back and select Security questions, to remove the checkmark.

1. From the left navigation panel of Password reset, select Registration.
    1. Hover your mouse over the information icon next to where it says, “Require users to register when signing in”.   Call this out to the users.  
    1. Hover your mouse over the information icon next to where it says, “Number of days before user are asked to reconfirm their authentication information”.   Call this out to the users.  

1. From the left navigation panel of Password reset, select Notifications.  Call out the two settings – hover your mouse over the information icon for the description.

1. Note how the Password reset navigation pane also includes options to view audit logs and Usage & insights.

1. Select the X on the top right corner of the page. This returns you to the main page for the Contoso tenant.

1. Keep this browser page open for the next demo.

### Review

In this demo, you showed the settings associated with self-service password reset.
