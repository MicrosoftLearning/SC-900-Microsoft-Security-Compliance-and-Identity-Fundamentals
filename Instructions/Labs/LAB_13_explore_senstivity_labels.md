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

1. Open the browser tab for home page of Microsoft Purview.  If you previously closed it, open a browser tab and enter **https://admin.microsoft.com**. Sign in with the admin credentials for the Microsoft 365 tenant provided by the authorized lab hoster (ALH). From the left navigation pane of the Microsoft 365 admin center, select **Show all** then select **Compliance**.  A new browser page opens to the welcome page of the Microsoft Purview compliance portal.   

1. In the left navigation panel, under solutions, expand **Information protection** then select **Overview**. Note the warning at the top of the page and scroll down to view the information available.

1. From the left navigation panel, select **Labels**.
   1. On the labels page, you may see a yellow information box indicating that your organization has not turned on the ability to process content in Office online files that have encrypted sensitivity labels applied and are stored in OneDrive and SharePoint.  Select **Turn on now**.  Once you do this, there can be a delay for the setting to propagate through the system and there are additional steps that must be completed to protect Teams, SharePoint sites, and Microsoft 365 Groups.

1. Some labels have been preconfigured in your Microsoft 365 lab tenant, for your convenience. Expand **Highly Confidential** and select **All Employees**.  A window opens that provides information about this label.  Note how this label is set to support both encryption and content marking.  Select the **pencil icon** at the top of the page to view some of the basic configuration settings.
    1. Configuration starts with providing a name and description for your label.  Don’t change anything.  Select **Next** at the bottom of the page.
    1. Note the scope for this label.  The scope is set to Files & Emails.  Don’t change anything.  Select **Next** at the bottom of the page.
    1. This next screen is where you can choose protection settings for the labeled items. Note that this label is configured to support encryption and content marking. Don’t change anything.  Select **Next** at the bottom of the page.
        1. The Encryption window shows the configuration for the encryption settings. Review the current settings, but don’t change anything. Notice how the user access to content is set to never expire and always allow offline access.  You can also assign permissions to specific users and groups so only they can interact with content that has this label applied.  Under users and groups, the tenant is defined so all users in your tenant can view content that has this label.  Don’t change any settings.  Select **Next** on the bottom of the page.
        1. On the content markings page, take note of the information box on the top of the page.  Content markings will be applied to documents but only headers and footers will be applied to email messages. In other words, watermarks are not applied to emails.  The content marking associated with this label is a footer.  Don’t change any settings.  Select **Next** on the bottom of the page.
    1. You are now in the Auto-labeling for files and emails window.  Read the description of auto-labeling on the top of the page and the information box below it.  Also take note that this label is set for auto-labeling for specific conditions. Don’t change any settings.  Select **Next** on the bottom of the page.
    1. This next window defines protection settings for teams, groups, and sites that have this label applied. This is not enabled, select **Next** on the bottom of the page.
    1. This next window is a preview feature to automatically apply this label to schematized data assets in Microsoft Purview Data Map (such as SQL, Synapse, and more) that contain the sensitive info types you choose.  This feature is not enabled. Select **Cancel** at the bottom of the page to exit the label configuration wizard and return to the Information Protection page.

1. From the left navigation panel, select **Label policies**.  It is through label policies that sensitivity labels can be published.  The Microsoft 365 tenant has been configured with some label policies, for your convenience.

1. In this case, select **Global sensitivity label policy**.  A window opens that provides information about the policy.  Note the description, this label policy has been setup to serve as the default sensitivity label policy for all users and groups. This policy serves to publish most of the labels that were preconfigured for this Microsoft 365 lab tenant and are listed in the labels tab.  

1. Select **Edit policy** from the top of the window.
    1. Read the description under “Choose sensitivity labels to publish”.  Notice the labels that are listed.  Don’t change any settings.  Select **Next** on the bottom of the page.
    1. Review the description for "Assign admin units". The Admin units are set to the full directory, don't change any settings. Select **Next**.  
    1. Review the description for “Publish to users and groups”.  Notice this label is available to all users.  Don’t change any settings.  Select **Next** on the bottom of the page.
    1. Review the policy settings. Select **Require users to apply a label to their emails and documents** and review the description provided. Select **Next** on the bottom of the page.
    1. Read description under "Apply a default label to documents." Don’t change any settings.  Select **Next** on the bottom of the page.
    1. Read description under "Apply a default label to emails" and "Inherit label from attachments". Don’t change any settings.  Select **Next** on the bottom of the page.
    1. Read description under "Apply a default label to meetings and calendar events". Don’t change any settings.  Select **Next** on the bottom of the page.
    1. Read description under "Apply a default label to Power BI content". Don’t change any settings.  Select **Next** on the bottom of the page.
    1. The last configuration option is to name your policy.  Since you're editing the policy, the name field is greyed out.  Select **Next** on the bottom of the page.
    1. Review the policy settings. Select **Cancel** to discard any changes and return to the Label policies page.

1. From the Information protection page, select Auto-labeling. Review the description. Note that you create auto-labeling policies to automatically apply sensitivity labels to email messages or OneDrive and SharePoint files that contain sensitive info. No auto-label policies have been preconfigured in our tenant. To create a new auto-label policy, select **Create auto-label policy**.  Here you will walk through the steps to create a new policy.
    1. You start by choosing the information you want this label applied to.  Note the available options.  Select **Medical and health** then select one of the available templates.  Select **Next**.
    1. You can name your auto-label policy or use the default name.  Select **Next**.
    1. You can assign the admin units to which this policy applies.  Leave the default set to full directory and select **Next**.
    1. Note the available locations where you want to apply the label.  Leave the defaults and select **Next**.
    1. You can set up common or advanced rules that define what hte content the label is applied to.  Leave the default set to Common rules and select **Next**.
    1. You can define rules for content in all locations.  The label will be applied to content that matches rules defined on this page.  For the template you selected, you should see a line item. Expand it to view the conditions that apply.  Leave all the default settings  and select **Next**.
    1. Choose a label to auto-apply by selecting **Choose a label**.  Choose a label then select **Add**.
    1. Additional settings can be configured for email. Leave the defaults and select **Next**.
    1. You can decide to test the policy now or later.  Select **Leave policy turned off** then select **Next**.
    1. Review the settings and select **Create policy** then select **Done**.

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

Recall from the first part of the demo, that the Confidential - Finance label is set up for encryption. Per the permissions that were configured with this label, users in the Contoso tenant have viewer permissions for any document/email with the label applied.  In this section you'll send document you previously created, that includes the Confidential - Finance label, to an email address to which you have access (a personal email address or your Microsoft email) and that is NOT part of the WWLxZZZZ.OnMicrosoft.com domain.  

1. From the Microsoft Purview compliance portal home page, select the **app launcher icon**, next to where it says Contoso Electronics. Select the **Outlook icon**.

1. Select **New mail** from the top left corner of the screen.  Enter an email address to which you have access and is not part of the WWLxZZZZ.OnMicrosoft.com domain and enter **Test** in the subject line.

1. Select **Attach** (the paperclip icon).

1. Select **OneDrive**.

1. Make sure the **Recent** tab on the left navigation panel is selected.  From the list that shows up, select the document you created and to which you applied the label **Test-label**. Select **Next** and select **Attach as a copy**.  Press **Send**.

1. Check the email to which you sent the document.  Note, the email may be directed to your junk folder.  The email is successfully sent but When you attempt to open the attached word file, which was originally labeled as confidential - Finance, you'll see a notification that you do not have permission to open the document.

1. Close Outlook, but keep the the browser tab to the Microsoft Purview home page open.

### Review

In this lab, you'll explore the capabilities of sensitivity labels.  You'll go through the settings for existing sensitivity labels that have already been created and the corresponding policy to publish the label.   Then you'll see how to apply a label and the impact of that label, from the perspective of a user.
