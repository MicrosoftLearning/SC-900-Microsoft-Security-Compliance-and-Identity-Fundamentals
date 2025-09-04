---
lab:
    title: 'Explore sensitivity labels in Microsoft Purview'
    module: 'Describe the data security solutions of Microsoft Purview'
---

# Lab: Explore sensitivity labels in Microsoft Purview

This lab maps to the following Learn content:

- Learning Path: Describe the capabilities of Microsoft Priva and Microsoft Purview
- Module: Describe the data security solutions of Microsoft Purview
- Unit: Describe sensitivity labels and policies in Microsoft Purview Information Protection

## Lab scenario

In this lab, you'll explore the capabilities of sensitivity labels.  You'll go through the settings for existing sensitivity labels that have been created and the corresponding policy to publish the label.   Then you'll see how to apply a label and the impact of that label, from the perspective of a user.

**Estimated Time**: 45 minutes

### Task 1

In this task, you'll gain an understanding of what sensitivity labels can do by going through the process of creating a new label and creating a policy to publish the label.

1. Open the browser tab for home page of Microsoft Purview.  If you previously closed it, open a browser tab and enter **`https://admin.microsoft.com`**. Sign in with the admin credentials for the Microsoft 365 tenant provided by the authorized lab hoster (ALH).

1. From the left navigation pane of the Microsoft 365 admin center, select **Show all** then select **Microsoft Purview**.  A new browser page opens to the welcome page of the Microsoft Purview portal.

1. In the left navigation panel, select **Solutions** then select **Information protection**.  You are on the overview page. Scroll down to view the information available.

1. From the left navigation panel, select **Sensitivity labels**.
1. You will see a yellow banner indicating that your organization has not turned on the ability to process content in Office online files that have encrypted sensitivity labels applied and are stored in OneDrive and SharePoint.  Select **Turn on now**.

1. Some labels have been preconfigured in your Microsoft 365 lab tenant, for your convenience. Select the label named **Confidential-Finance**.  A window opens that provides information about this label.  Note the settings for this label.  Select **Edit label** If you don't see this option, select the ellipsis.
    1. Configuration starts with providing basic details for the label.  Don’t change anything.  Select **Next** at the bottom of the page.
    1. Review the scope for this label. Don’t change anything.  Select **Next** at the bottom of the page.
    1. This next screen is where you can choose protection settings for the labeled items. This label is configured to support content marking. Don’t change anything.  Select **Next** at the bottom of the page.
        1. On the content markings page, take note of the information box on the top of the page.  Don’t change any settings.  Select **Next** on the bottom of the page.
    1. You are now in the Auto-labeling for files and emails window.  Read the description of auto-labeling on the top of the page and the information box below it.  Also take note that this label is set for auto-labeling for specific conditions. Don’t change any settings.  Select **Next** on the bottom of the page.
    1. This window defines protection settings for groups and sites that have this label applied. This is not enabled, select **Next** on the bottom of the page.
    1. This last windows is where you can review your settings and finish. Select **Cancel** at the bottom of the page to exit the label configuration wizard and return to the Information Protection page.

1. From the left navigation pane, expand **Policies** then select **Label publishing policies**.  It is through label policies that sensitivity labels can be published.  The Microsoft 365 tenant has been configured with some label policies, for your convenience.

1. Select **Confidential-Finance Policy**.  A window opens that provides information about the policy. Select **Edit policy** from the top of the window.  Here you will walk through the settings without changing anything.
    1. Review the description for “Choose sensitivity labels to publish”.  Notice the label that is listed.  Don’t change any settings.  Select **Next** on the bottom of the page.
    1. Review the description for "Assign admin units". The Admin units are set to the full directory, don't change any settings. Select **Next**.  
    1. Review the description for “Publish to users and groups”.  Notice this label is available to all users.  Don’t change any settings.  Select **Next** on the bottom of the page.
    1. Review the policy settings. Don’t change any settings.  Select **Next** on the bottom of the page.
    1. Review the description for "Apply a default label to documents." Don’t change any settings.  Select **Next** on the bottom of the page.
    1. Review the description for "Apply a default label to emails" and "Inherit label from attachments". Don’t change any settings.  Select **Next** on the bottom of the page.
    1. Review the description for "Apply a default label to meetings and calendar events". Don’t change any settings.  Select **Next** on the bottom of the page.
    1. Review the description for "Apply a default label for Fabric and Power BI content". Don’t change any settings.  Select **Next** on the bottom of the page.
    1. The last configuration option is to name your policy.  Since you're editing the policy, the name field is greyed out.  Select **Next** on the bottom of the page.
    1. Review the policy settings. Select **Cancel** to discard any changes and return to the Label policies page.

1. From the left navigation panel, under Information protection, select **Auto-labeling policies**. Review the description. Note that you create auto-labeling policies to automatically apply sensitivity labels to email messages or OneDrive and SharePoint files that contain sensitive info. No auto-label policies have been preconfigured in our tenant. To create a new auto-label policy, select **Create auto-label policy**.  Here you will walk through the steps to create a new policy.
    1. You start by choosing the information you want this label applied to.  Note the available options.  Select **Medical and health** then select one of the available regulations that will serve as a template.  Select **Next**.
    1. You can name your auto-label policy or use the default name.  Select **Next**.
    1. Next you choose a label to auto-apply.  Select **+ Choose a label**.  Select a label from the list, then select **Add**.
    1. You can assign the admin units to which this policy applies.  Leave the default set to full directory and select **Next**.
    1. Note the available locations where you want to apply the label. Select the box next to **Exchange email** and select **Next**.
    1. You can set up common or advanced rules that define what the content the label is applied to.  Leave the default set to Common rules and select **Next**.
    1. You can define rules for content in all locations.  The label will be applied to content that matches rules defined on this page.  For the template you selected, you should see a line item. Expand it to view the conditions that apply.  Leave all the default settings  and select **Next**.
    1. Additional settings can be configured for email. Leave the defaults and select **Next**.
    1. You can decide to test the policy now or later.  Select **Leave policy turned off** then select **Next**.
    1. Review the settings. For the purpose of this excercise, you can cancel out with out creating the policy. Select **Cancel**.

1. From the left navigation panel, select **Home** to return to the Microsoft Purview portal.

1. Keep this page open, you'll use it in the next task.

### Task 2

In this task, you'll go through the process of applying a sensitivity label to a Microsoft Word document and then view the content marking (watermark) that is generated by the label. NOTE: When using Microsoft Word online, you may experience be a delay before the option to select Sensitivity labels appears on the top ribbon.  It is recommended that you complete all remaining labs and then return back to this task.

1. You should still be on the home page for the Microsoft Purview Portal. 
1. From the Microsoft Purview portal, select the **app launcher icon**, next to where it says Microsoft Purview. Select the **Word icon**.  

1. Under Create new, select **Blank document**, then enter some text on the page.  On the top of the page, next to the Word icon, select where it says **Document** and rename the file to **Test-label** then press **Enter** on your keyboard.

1. On the far right of top menu bar (also referred to as the ribbon) is a down arrow, select it, then select **Classic Ribbon**.  This will make it easier to identity the sensitivity icon. Select **Sensitivity**, located next to the microphone icon. From the drop-down menu, select **Confidential-Finance**.  

1. From the top menu bar, select **View**, then select **Reading view**.

1. Notice how the document includes the watermark-Confidential FINANCIAL DATA..  

1. Close the Microsoft Word tabs that are open on your browser to exit from Word, but keep the the browser tab to the Microsoft Purview home page open.

### Review

In this lab, you'll explore the capabilities of sensitivity labels.  You'll go through the settings for existing sensitivity labels that have already been created and the corresponding policy to publish the label.   Then you'll see how to apply a label.
