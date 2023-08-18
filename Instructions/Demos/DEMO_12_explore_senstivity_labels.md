<!---
---
Demo:
    Title: 'Sensitivity labels in Microsoft Purview'
    Learning Path/Module/Unit: 'Learning Path: Describe the capabilities of Microsoft compliance; Module 3:Describe information protection, data lifecycle management, and data governance capabilities in Microsoft Purview; Unit 4: Describe sensitivity labels'
---
--->

# Demo: Sensitivity labels in Microsoft Purview

This demo maps to the following Learn content:

- Learning Path: Describe the capabilities of Microsoft compliance
- Module: Describe information protection, data lifecycle management, and data governance capabilities in Microsoft Purview
- Unit: Describe sensitivity labels

## Demo scenario

In this demo, you'll show the capabilities of sensitivity labels.  You'll go through the settings for existing sensitivity labels that have been created and the corresponding policy to publish the label.   Then you'll see how to apply a label and the impact of that label, from the perspective of a user.  **NOTE**: The first time you use Word online with your Microsoft 365 tenant, it can take 15 minutes for the Sensitivity option to appear on the ribbon.  Presenters should run demo part 2 before class to ensure sufficient time for the option to appear.

### Demo Part 1

In this demo, you show the settings for an existing sensitivity label and the corresponding policy to publish the label.

1. Open the browser tab for home page of Microsoft Purview.  If you previously closed it, open a browser tab and enter **https://admin.microsoft.com**. Sign in with the admin credentials for the Microsoft 365 tenant provided by the authorized lab hoster (ALH). From the left navigation pane of the Microsoft 365 admin center, select **Show all** then select **Compliance**.  A new browser page opens to the welcome page of the Microsoft Purview compliance portal.  

1. In the left navigation panel, under solutions, expand **Information protection** then select **Overview**.  The overview page includes information about top sensitivity labels applied to content, top activities detected, locations where sensitivity labels are applied and more.  

1. From the left navigation panel, select the **Labels** tab from the top of the page.

1. Some labels have been preconfigured in your Microsoft 365 lab tenant, for your convenience. Select **Confidential - Finance**.  A window opens that provides information about this label.  Note how this label is set to support both encryption and content marking.  Select the **pencil icon** at the top of the page to view some of the basic configuration settings.
    1. Configuration starts with providing a name and description for your label.  Don’t change anything.  Select **Next** at the bottom of the page.
    1. Note the scope for this label.  The scope is set to Files & emails.  Don’t change anything.  Select **Next** at the bottom of the page.
    1. This next screen is where you can choose protection settings for the labeled items. Note that this label is configured to support encryption and content marking. Don’t change anything.  Select **Next** at the bottom of the page.
        1. The Encryption window shows the configuration for the encryption settings. Review the current settings, but don’t change anything. Notice how the user access to content is set to never expire.  You can also assign permissions to specific users and groups so only they can interact with content that has this label applied.  Under users and groups, the tenant is defined so all users in your tenant can view content that has this label.  The finance team is also listed and they have co-author permissions.  Don’t change any settings.  Select **Next** on the bottom of the page.
        1. On the content markings page, take note of the information box on the top of the page.  Content markings will be applied to documents but only headers and footers will be applied to email messages. In other words, watermarks are not applied to emails.  The content marking associated with this label is a watermark.  Don’t change any settings.  Select **Next** on the bottom of the page.
    1. You are now in the Auto-labeling for files and emails window.  Read the description of auto-labeling on the top of the page and the information box below it.  Also take note that this label is set for auto-labeling for specific conditions. Don’t change any settings.  Select **Next** on the bottom of the page.
    1. This next window defines protection settings for teams, groups, and sites that have this label applied. This is not enabled, select **Next** on the bottom of the page.
    1. This next window is a preview feature to automatically apply this label to schematized data assets in Microsoft Purview Data Map (such as SQL, Synapse, and more) that contain the sensitive info types you choose.  This feature is not enabled. Select **Cancel** at the bottom of the page to exit the label configuration wizard and return to the Information Protection page.

1. From the left navigation panel, select **Label policies**.  It is through label policies that sensitivity labels can be published.  The Microsoft 365 tenant has been configured with some label policies, for your convenience.

1. In this case, Select **Confidential-Finance Policy**.  A window opens that provides information about the policy.  Note the description, this label policy has been set up to serve as the default sensitivity label policy for all users and groups. This policy serves to publish most of the labels that were preconfigured for this Microsoft 365 lab tenant and are listed in the labels tab.  

1. Select **Edit policy** from the top of the window.
    1. Read the description under “Choose sensitivity labels to publish”.  Notice the labels that are listed.  Don’t change any settings.  Select **Next** on the bottom of the page.
    1. The next page is a preview for Assigning admin  units. Select **Next**.
    1. Read the description under “Publish to users and groups”.  Notice this label is available to all users.  Don’t change any settings.  Select **Next** on the bottom of the page.
    1. Review the policy settings.  Select **Next** on the bottom of the page.
    1. Read description under, "Apply a default label to documents." Don’t change any settings.  Select **Next** on the bottom of the page.
    1. Read description under, "Apply a default label to emails." Don’t change any settings.  Select **Next** on the bottom of the page.
    1. Read description under, "Default settings for meetings and calendar events." Don’t change any settings.  Select **Next** on the bottom of the page.
    1. Read description under, "Apply a default label to Power BI content." Don’t change any settings.  Select **Next** on the bottom of the page.
    1. The last configuration option is to name your policy.  Since you're editing the policy, the name field is greyed out.  Select **Next** on the bottom of the page.
    1. Review the policy settings. Since nothing was changed select **Cancel** to return to the Label policies page.

1. From the Information protection page, select Auto-labeling. Review the description. Note that you create auto-labeling policies to automatically apply sensitivity labels to email messages or OneDrive and SharePoint files that contain sensitive info. If there are auto-labeling policies configured, select one and reivew the policy information in the details pane.  

1. From the left navigation panel, select Home to return to the Microsoft Purview compliance portal.

1. Keep this browser tab open.

### Demo Part 2

In this step, you'll show the process of applying a label from the perspective of the user (in this case the user is the admin).  For the purpose of viewing the impact of applying the label, you'll select the Confidential - Finance label because this label applies a watermark.

1. From the Microsoft Purview compliance portal home page, select the **app launcher icon**, next to where it says Contoso Electronics. Select the **Word icon**.  

1. Select **Blank document**, then enter some text on the page.  On the blue bar on the top of the page, select the down-arrow, next to where it says Document - Saved, and in the File Name box enter, **Test-label** then press the **Enter** key on your keyboard.

1. From the top menu bar, select **Sensitivity icon** (the icon to the right of the microphone icon), if you don't immediately see this option, refresh the page. From the drop-down, select **Confidential - Finance**.   NOTE: if you don't immediately see the Sensitivity option, refresh the page, but because this is a lab tenant environment you  may encounter longer than normal delays (10-15 minutes).
1. 
1. From the top menu bar, select **View**, then select **Reading view**.

1. Notice how the document includes the watermark.  

1. Close the Microsoft Word tabs that are open on your browser to exit from Word.

1. Keep the Microsoft Purview browser tab open for the next demo.

### Demo Part 3 (optional)

Recall from the first part of the demo, that the Confidential - Finance label is set up for encryption. Per the permissions that were configured with this label, users in the Contoso tenant have viewer permissions for any document/email with the label applied.  In this section you'll send document you previously created, that includes the Confidential - Finance label, to an email address to which you have access (a personal email address or your Microsoft email) and that is NOT part of the WWLxZZZZ.OnMicrosoft.com domain.  

1. From the Microsoft Purview compliance portal home page, select the **app launcher icon**, next to where it says Contoso Electronics. Select the **Outlook icon**

1. Select **New mail** from the top left corner of the screen.  Enter an email address to which you have access and is not part of the WWLxZZZZ.OnMicrosoft.com domain and enter **Test** in the subject line.

1. From the top ribbon, select the paper clip icon, then from the drop down list, under suggested files, select the document you created in the previous step, **Test-label** to attach it to the email.

1. Press **Send** to sent the email.

1. Check the email to which you sent the document.  Note, the email may be directed to your junk folder.  The email is successfully sent but When you attempt to open the attached word file, which was originally labeled as confidential - Finance, you'll see a notification that you do not have permission to open the document.

1. Close Outlook.

1. Keep the Microsoft Purview browser tab open for the next demo.


### Review

In this demo, you showed the settings that can be configured for sensitivity labels and the settings for policies to publish sensitivity labels. You also showed how to apply a label and the impact of that label, from the perspective of a user.

