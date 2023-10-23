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
    1. On the overview page, you may see a yellow information box indicating that your organization has not turned on the ability to process content in Office online files that have encrypted sensitivity labels applied and are stored in OneDrive and SharePoint.  Select **Turn on now**.  Once you do this, there can be a delay for the setting to propagate through the system.

1. From the left navigation panel, select **Labels**.

1. Some labels have been preconfigured in your Microsoft 365 lab tenant, for your convenience. Select the label named **Confidential-Finance**.  A window opens that provides information about this label.  Note the settings for this label.  Select the **pencil icon** at the top of the page to view some of the basic configuration settings. If you don't see the pencil icon, select the ellipsis.
    1. Configuration starts with providing a name and description for your label.  Don’t change anything.  Select **Next** at the bottom of the page.
    1. Review the scope for this label. Don’t change anything.  Select **Next** at the bottom of the page.
    1. This next screen is where you can choose protection settings for the labeled items. This label is configured to support content marking. Don’t change anything.  Select **Next** at the bottom of the page.
        1. On the content markings page, take note of the information box on the top of the page.  Don’t change any settings.  Select **Next** on the bottom of the page.
    1. You are now in the Auto-labeling for files and emails window.  Read the description of auto-labeling on the top of the page and the information box below it.  Also take note that this label is set for auto-labeling for specific conditions. Don’t change any settings.  Select **Next** on the bottom of the page.
    1. This window defines protection settings for teams, groups, and sites that have this label applied. This is not enabled, select **Next** on the bottom of the page.
    1. This window is a preview feature to automatically apply this label to schematized data assets in Microsoft Purview Data Map (such as SQL, Synapse, and more) that contain the sensitive info types you choose.  This feature is not enabled. Select **Cancel** at the bottom of the page to exit the label configuration wizard and return to the Information Protection page.

1. From the left navigation panel, select **Label policies**.  It is through label policies that sensitivity labels can be published.  The Microsoft 365 tenant has been configured with some label policies, for your convenience.

1. Select **Confidential-Finance Policy**.  A window opens that provides information about the policy. 

1. Select **Edit policy** from the top of the window.  Here you will walk through the settings without changing anything.
    1. Review the description for “Choose sensitivity labels to publish”.  Notice the label that is listed.  Don’t change any settings.  Select **Next** on the bottom of the page.
    1. Review the description for "Assign admin units". The Admin units are set to the full directory, don't change any settings. Select **Next**.  
    1. Review the description for “Publish to users and groups”.  Notice this label is available to all users.  Don’t change any settings.  Select **Next** on the bottom of the page.
    1. Review the policy settings. Don’t change any settings.  Select **Next** on the bottom of the page.
    1. Review the description for "Apply a default label to documents." Don’t change any settings.  Select **Next** on the bottom of the page.
    1. Review the description for "Apply a default label to emails" and "Inherit label from attachments". Don’t change any settings.  Select **Next** on the bottom of the page.
    1. Review the description for "Apply a default label to meetings and calendar events". Don’t change any settings.  Select **Next** on the bottom of the page.
    1. Review the description for "Apply a default label to Power BI content". Don’t change any settings.  Select **Next** on the bottom of the page.
    1. The last configuration option is to name your policy.  Since you're editing the policy, the name field is greyed out.  Select **Next** on the bottom of the page.
    1. Review the policy settings. Select **Cancel** to discard any changes and return to the Label policies page.

1. From the Information protection page, select Auto-labeling. Review the description. Note that you create auto-labeling policies to automatically apply sensitivity labels to email messages or OneDrive and SharePoint files that contain sensitive info. If there are auto-labeling policies configured, select one and review the policy information in the details pane.  If no policy is listed, you may choose to walk-through the steps to create one, if time permits.

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

### Review

In this demo, you showed the settings that can be configured for sensitivity labels and the settings for policies to publish sensitivity labels. You also showed how to apply a label.
