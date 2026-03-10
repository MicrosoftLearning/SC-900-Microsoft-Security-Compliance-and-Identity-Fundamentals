---
lab:
  title: Lab setup
  module: Setup your Microsoft 365 lab tenant (not associated with a Learn module)
  description: If you are being provided with a tenant as a part of an instructor-led
    training delivery, please note that the tenant is made available for the purpose
    of supporting the hands-on labs in the instructor-led training.
  duration: 15 minutes
  level: 100
  islab: true
---

# Lab: Setup of the Microsoft 365 tenant

## WWL Tenants - Terms of use
If you are being provided with a tenant as a part of an instructor-led training delivery, please note that the tenant is made available for the purpose of supporting the hands-on labs in the instructor-led training.

Tenants should not be shared or used for purposes outside of hands-on labs. The tenant used in this course is a trial tenant and cannot be used or accessed after the class is over and are not eligible for extension.

Tenants must not be converted to a paid subscription. Tenants obtained as a part of this course remain the property of Microsoft Corporation and we reserve the right to obtain access and repossess at any time.

## Lab scenario

This setup lab consists of enabling the Microsoft Audit Log and file monitoring capabilities in the Microsoft 365 tenant.

**Estimated Time**: 10-15 minutes

### Setup - Enable Microsoft 365 audit log and file monitoring

In this setup task, you will enable the Audit log and file monitoring capabilities in Microsoft 365.  

1. Open Microsoft Edge. In the address bar, enter **`https://admin.microsoft.com`**.

1. Sign in with the admin credentials for the Microsoft 365 tenant provided by your authorized lab hoster (ALH).

1. From the left navigation pane of the Microsoft 365 admin center, select **Show all**.

1. Under Admin centers, select **Security**.  A new browser page opens to the welcome page of Microsoft Defender.

1. In the left navigation panel, scroll down and expand **System**.  From the expanded list, select **Audit**.  Note: the audit functionality is also accessible through the Microsoft Purview portal.

1. Once you land on the Audit page, wait 1-2 minutes.  If Auditing is NOT enabled, you'll see a blue bar on the top of the page that says start recording user and admin activity.  Select **Start recording user and admin activity**.  Once auditing is enabled, the blue bar disappears.

1. From the left navigation panel, under System, select **Settings**.

1. From the settings page, select **Cloud apps**.   Scroll down, then under **Information Protection** select **Files**.

1. If not already enabled, select the box next to where it says **Enable file monitoring** then select **Save**.  

1. This concludes the lab setup on the Microsoft 365 tenant.
1. You can close the browser tab, "Cloud Apps-Microsoft Defender", but keep the "Microsoft 365 admin center" tab open, for the next exercise.

### Review

In this setup, you enabled the audit log and file monitoring capabilities in Microsoft 365.
