<!---
---
Lab:
    Title: 'Explore sensitivity labels in Microsoft Purview'
    Learning Path/Module/Unit: 'Learning Path: Describe the capabilities of Microsoft compliance; Module 3: Describe information protection and data lifecycle management in Microsoft Purview; Unit 4: Describe sensitivity labels'
---
--->

# Lab: Explore sensitivity labels in Microsoft Purview

This lab maps to the following Learn content:

- Learning Path: Describe the capabilities of Microsoft compliance
- Module: Describe information protection and data lifecycle management in Microsoft Purview
- Unit: Describe sensitivity labels

## Lab scenario

In this lab, you'll explore the capabilities of sensitivity labels.  You'll go through the settings for existing sensitivity labels that have been created and the corresponding policy to publish the label.   Then you'll see how to apply a label and the impact of that label, from the perspective of a user.

**Estimated Time**: 20-25 minutes

### Task 1

In this task, you'll gain an understanding of what sensitivity labels can do by going through the settings for an existing sensitivity label that have been created and the corresponding policy to publish the label.

1. Open Microsoft Edge. In the address bar, enter **admin.microsoft.com**.

1. Sign in with your admin credentials.
    1. In the Sign-in window, enter **admin@WWLxZZZZZZ.onmicrosoft.com** (where ZZZZZZ is your unique tenant ID provided by your lab hosting provider) then select **Next**.

    1. Enter the admin password that should be provided by your lab hosting provider. Select **Sign in**.
    1. When prompted to stay signed- in, select **Yes**. This takes you to the Microsoft 365 admin center page.

1. From the left navigation pane of the Microsoft 365 admin center, select **Show all**.

1. Under Admin centers, select **Compliance**.  A new browser page opens to the welcome page of the Microsoft Purview compliance portal.  

1. In the left navigation panel, under solutions, expand **Information protection** then select **Overview**.

1. From the overview page, note the yellow information box indicates that your organization has not turned on the ability to process content in Office online files that have encrypted sensitivity labels applied and are stored in OneDrive and SharePoint.  Select **Turn on now**.  Once you do this, there can be a delay for the setting to propagate through the system.  Also review the information available on this overview page.

1. From the left navigation panel, select the **Labels**.

1. Some labels have been preconfigured in your Microsoft 365 lab tenant, for your convenience. Select **Confidential - Finance**.  A window opens that provides information about this label.  Note how this label is set to support both encryption and content marking.  Select **Edit Label** at the top of the page to view some of the basic configuration settings.  As you go through and view the various settings do NOT change anything.
    1. Configuration starts with setting the name and creating a tooltip for your label.  Here you provide a name, description, and a label color.  Don’t change anything.  Select **Next** at the bottom of the page.
    1. Now you define the scope for this label.  The scope is set to **Items**.  Read the description but don’t change anything.  Select **Next** at the bottom of the page.
    1. Now you choose protection settings for labeled items." Included on this page are the options to encrypt and/or mark the content.  Note how the protection settings for files and emails are set for both encryption and marking the content of files.  Review the definition of each.  Don’t change anything.  Select **Next** at the bottom of the page.
    1. The Encryption window shows the configuration for the encryption settings.  Don’t change anything.  Review the information box under Configure encryption settings and review the configured settings. Notice how the user access to content is set to never expire.  You can also assign permissions to specific users and groups so only they can interact with content that has this label applied.  Under users and groups, the tenant is defined so all users in your tenant can view content that has this label.  The finance team is also listed and they have co-author permissions.  Don’t change any settings.  Select **Next** on the bottom of the page.
    1. On the content markings page, take note of the information box on the top of the page.  Content markings will be applied to documents but only headers and footers will be applied to email messages. In other words, watermarks are not applied to emails.  The content marking associated with this label is a watermark that reads, HIGHLY CONFIDENTIAL.  Don’t change any settings.  Select **Next** on the bottom of the page.
    1. You're now in the Auto-labeling for files and emails window.  Read the description of auto-labeling on the top of the page and the information box below it.  Also take note that this label is set for auto-labeling for specific conditions. Don’t change any settings.  Select **Next** on the bottom of the page.
    1. This next window defines protection settings for groups and sites that have this label applied. This is not enabled, select **Next** on the bottom of the page.
    1. This next window is a preview feature for Auto-labeling for schematized data assets. Read the description.  This feature is not enabled. Select **Cancel** at the bottom of the page to exit the label configuration wizard and return to the Labels page.

1. From the left navigation panel, select **Label policies**.  It is through label policies that sensitivity labels can be published.  The Microsoft 365 tenant has been configured with some label policies, for your convenience.

1. In this case, Select **Confidential-Finance Policy**.  A window opens that provides information about the policy.  Note the description, this label policy has been setup to serve as the default sensitivity label policy for all users and groups. This policy serves to publish most of the labels that were preconfigured for this Microsoft 365 lab tenant and are listed in the labels tab.  

1. Select **Edit** policy from the top of the window.
    1. Read the description under “Choose sensitivity labels to publish”.  Notice the labels that are listed.  Don’t change any settings.  Select **Next** on the bottom of the page.
    1. The next page is a preview for Assigning admin units, review the description for admin units. The admin units is set to the full directory, don't change any settings. Select **Next**.  
    1. Read the description under “Publish to users and groups”.  Notice this label is available to all users.  Don’t change any settings.  Select **Next** on the bottom of the page.
    1. Review the policy settings.  Select **Next** on the bottom of the page.
    1. Read description under, "Apply a default label to documents." Don’t change any settings.  Select **Next** on the bottom of the page.
    1. Read description under, "Apply a default label to emails." Don’t change any settings.  Select **Next** on the bottom of the page.
    1. Read description under, "Default settings for meetings and calendar events." Don’t change any settings.  Select **Next** on the bottom of the page.
    1. Read description under, "Apply a default label to Power BI content." Don’t change any settings.  Select **Next** on the bottom of the page.
    1. The last configuration option is to name your policy.  Since you're editing the policy, the name field is greyed out.  Select **Next** on the bottom of the page.
    1. Review the policy settings. Since nothing was changed select **Cancel** to return to the Label policies page.

1. From the left navigation panel, select Auto-labeling.  Note there's no auto-labeling policy configured.  Don’t change any settings.  If you're wondering why there's no policy here, given that the label configuration is set to auto-labeling for files and emails, go back to the steps where you walked through the label configuration settings and review the description and information boxes associated Auto-labeling for files and emails.  Hint:  In the auto labeling tab for the sensitivity lab, it says.  "To automatically apply this label to files that are already saved (in SharePoint and OneDrive) or emails that are already processed by Exchange, you must create an auto-labeling policy."

1. From the left navigation panel, select Home to return to the Microsoft Purview compliance portal.

1. Keep this page open, you'll use it in the next task.

### Task 2

In this task, you'll go through the process of applying a sensitivity label to a Microsoft Word document and then view the content marking (watermark) that is generated by the label. NOTE: When using Microsoft Word online, you may experience be a delay before the option to select Sensitivity labels appears on the top ribbon.  It is recommended that you complete all remaining labs and then return back to this task.

1. From the Microsoft Purview compliance portal home page, select the **app launcher icon**, next to where it says Contoso Electronics. Select the **Word icon**.  

1. Under Create new, select **Blank document**, then enter some text on the page.  On the top of the page, select the down-arrow, next to where it says Document - Saved, and in the File Name box enter, **Test-label** then press **Enter** on your keyboard.

1. From the top menu bar, select **Sensitivity icon**, the icon to the right of the microphone icon (depending on your screen size, you may need to select the ellipses then select sensitivity). From the drop-down, select **Confidential - Finance**.  NOTE: When using Microsoft Word online, you may experience be a delay before the option to select Sensitivity labels appears on the top ribbon.  It is recommended that you complete all remaining labs and then return back to this task.

1. From the top menu bar, select **View**, then select **Reading view**.

1. Notice how the document includes the watermark.  

1. Close the Microsoft Word tabs that are open on your browser to exit from Word.

### Task 3 (optional)

Recall from the first part of the demo, that the Confidential - Finance label is set up for encryption. Per the permissions that were configured with this label, users in the Contoso tenant have viewer permissions for any document/email with the label applied.  In this section you'll send document you previously created, that includes the Confidential - Finance label, to an email address to which you have access (ie., a personal email address or your Microsoft email) and that is NOT part of the WWLxZZZZ.OnMicrosoft.com domain.  

1. From the Microsoft Purview compliance portal home page, select the **app launcher icon**, next to where it says Contoso Electronics. Select the **Outlook icon**.

1. Select **New mail** from the top left corner of the screen.  Enter an email address to which you have access and is not part of the WWLxZZZZ.OnMicrosoft.com domain and enter **Test** in the subject line.

1. Select **Attach** (the paperclip icon).

1. Select **OneDrive**.

1. Make sure the **Recent** tab on the left navigation panel is selected.  From the list that shows up, select the document you created and to which you applied the label **Test-label**. Select **Next** and select **Attach as a copy**.  Press **Send**.

1. Check the email to which you sent the document.  Note, the email may be directed to your junk folder.  The email is successfully sent but When you attempt to open the attached word file, which was originally labeled as confidential - Finance, you'll see a notification that you do not have permission to open the document.

1. Close the open browser tabs.

### Review

In this lab, you'll explore the capabilities of sensitivity labels.  You'll go through the settings for existing sensitivity labels that had already been created and the corresponding policy to publish the label.   Then you'll see how to apply a label and the impact of that label, from the perspective of a user.
