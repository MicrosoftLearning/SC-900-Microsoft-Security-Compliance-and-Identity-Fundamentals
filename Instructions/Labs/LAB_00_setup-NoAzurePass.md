<!---
---
Lab:
    Title: 'Setup'
---
--->

# Lab: Setup

## Lab scenario

This setup lab consists of enabling the Microsoft Audit Log.

**Estimated Time**: 5-10 minutes

### Setup - Enable Microsoft 365 audit log

In this setup task, you will enable the Audit log capability in Microsoft 365.  Although documentation indicates that audit log is turned on by default, most lab tenants do not have this feature enabled and it can take several hours for this to take effect.  It is beneficial to enable this feature, as Microsoft 365 uses audit logs for user insights and activities identified in policies and analytics insights.

1. Open Microsoft Edge. In the address bar enter **admin.microsoft.com**.

1. Sign in with your admin credentials.
    1. In the Sign in window enter **admin@WWLxZZZZZZ.onmicrosoft.com** (where ZZZZZZ is your unique tenant ID provided by your lab hosting provider) then select **Next**.
    1. Enter the admin password which should be provided by your lab hosting provider. Select **Sign in**.
    1. When prompted to stay signed- in, select **Yes**. This takes you to the Microsoft 365 admin center page.

1. From the left navigation pane of the Microsoft 365 admin center, select **Show all**.

1. Under Admin centers, select **Compliance**.  A new browser page opens to the welcome page of the Microsoft 365 compliance center.  

1. In the left navigation panel, under solutions, select **Audit**.  Note: the audit functionality is also accessible through the Microsoft 365 Defender home page (previously referred to as the Microsoft 365 security center).

1. Verify that the **Search** tab is selected (underlined).

1. Once you land on the Audit page, wait 2-3 minutes.  If Auditing is NOT enabled, you will see a blue bar on the top of the page that says start recording user and admin activity.  Select **Start recording user and admin activity**.  If prompted to confirm the organization setting need to be updated, select **Yes**. Once auditing is enabled, the blue bar disappears.  If the blue bar is not present then auditing is already enabled, and no further action is required.  Another way to check if auditing is enabled is through PowerShell, but that is outside the scope of this course.

1. Return to the home page of the Microsoft 365 compliance center by selecting **Home** from the left navigation panel.

### Review

In this setup you enabled the audit log capability in Microsoft 365.
