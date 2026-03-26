---
lab:
  title: Explore sensitivity labels in Microsoft Purview
  module: Describe the data security solutions of Microsoft Purview
  description: In this lab, you'll explore the capabilities of sensitivity labels. You'll go through the settings for existing sensitivity labels that have been created and the corresponding policy to publish the label. Then you apply a label and validate the label has been applied, from the perspective of a user.
  duration: 45 minutes
  level: 200
  islab: true
  primarytopics:
    - Microsoft Purview
---

# Lab: Explore sensitivity labels in Microsoft Purview

This lab maps to the following Learn content:

- Learning Path: Describe the capabilities of Microsoft Priva and Microsoft Purview
- Module: Describe the data security solutions of Microsoft Purview
- Unit: Describe sensitivity labels and policies in Microsoft Purview Information Protection

## Lab scenario

In this lab, you'll explore the capabilities of sensitivity labels.  You'll go through the settings for existing sensitivity labels that have been created and the corresponding policy to publish the label. Then you'll see how to apply a label and the impact of that label, from the perspective of a user.

**Estimated Time**: 45 minutes

### Task 1

In this task, you'll gain an understanding of what sensitivity labels can do by going through the process of creating a new label and creating a policy to publish the label.

1. Open the browser tab for home page of Microsoft Purview.  If you previously closed it, open a browser tab and enter **`https://admin.microsoft.com`**. Sign in with the admin credentials for the Microsoft 365 tenant provided by the authorized lab hoster (ALH).

1. From the left navigation pane of the Microsoft 365 admin center, select **Show all** then select **Microsoft Purview**.  A new browser page opens to the welcome page of the Microsoft Purview portal.

1. In the left navigation panel, select **Solutions** then select **Information protection**.  You are on the overview page. Scroll down to view the information available.

1. From the left navigation panel, select **Sensitivity labels**.

1. You may see a yellow banner indicating that your organization has not turned on the ability to process content in Office online files that have encrypted sensitivity labels applied and are stored in OneDrive and SharePoint. If the banner is displayed, review the message and Select **Turn on now**. If no banner is shown, continue to the next step.

1. Some labels have been preconfigured in your Microsoft 365 lab tenant, for your convenience. Select the label named **Highly Confidential**. A window opens that provides information about this label.  Note the settings for this label.  Select **Edit label** If you don't see this option, select the ellipsis.
    1. Configuration starts with providing basic details for the label.  Don’t change anything.  Select **Next** at the bottom of the page.
    1. Review the scope for this label. Don’t change anything.  Select **Next** at the bottom of the page.
    1. This next screen is where you can choose protection settings for the labeled items. This label controls who can access and view labeled items and also applies content marking.  Select **Next** to view the details.
        1. Access control: Review the settings, but don't change anything.  Select **Next**.
        1. Content marking: Note that the label applies a footer.  then select **Next**.
        1. Auto-labeling for files and emails: Read the description of auto-labeling on the top of the page and the information box below it.  Also take note that this label is set for auto-labeling when credit card numbers are detected. Don’t change any settings.  Select **Next** on the bottom of the page.
    1. Define protection settings for groups and sites: Review the options for protection settings and auto apply settings.  Nothing has been configured in this window.  Don't change anything. Select **Next** on the bottom of the page.
    1. Review your settings and finish: Review your settings.  Since nothing has been changed, select **Cancel**.

1. From the left navigation pane, expand **Policies** then select **Label publishing policies**.  It is through label policies that sensitivity labels can be published.  The Microsoft 365 tenant has been configured with some label policies, for your convenience. Select **Highly Confidential Policy**.  A window opens that provides information about the policy. Select **Edit policy** from the top of the window.  Here you will walk through the settings without changing anything.
    1. Choose sensitivity labels to publish:  Notice the labels listed.  Don’t change any settings.  Select **Next** on the bottom of the page.
    1. Assign admin units: The Admin units are set to the full directory, don't change any settings. Select **Next**.  
    1. Publish to users and groups:  Notice this label is available to all users.  Don’t change any settings.  Select **Next** on the bottom of the page.
    1. Policy settings: Note the available options. Don’t change any settings.  Select **Next** on the bottom of the page.
    1. Default settings for documents: Don’t change any settings.  Select **Next** on the bottom of the page.
    1. Default settings for emails: Review the options and note that emails can inherit a label from an attachment with higher priority, if configured to so. Select **Next**.
    1. Default settings for meetings and calendar events: Review the options and note the option to  apply inheritance between Teasm meeting and artifacts. Don’t change any settings.  Select **Next**.
    1. Default settings for Fabric and Power BI content: Don’t change any settings.  Select **Next**.
    1. Name your policy: Since you're editing the policy, the name field is greyed out.  Select **Next**.
    1. Review and finish: Since nothing was changed, select **Cancel**.

1. From the left navigation panel, under Information protection, select **Auto-labeling policies**. Review the description. Note that you create auto-labeling policies to automatically apply sensitivity labels to email messages or OneDrive and SharePoint files that contain sensitive info. No auto-label policies have been preconfigured in our tenant. To create a new auto-label policy, select **Create auto-label policy**.  Here you will walk through the steps involved in creating a new policy.
    1. You start by choosing the information you want this label applied to.  Note the available options.  Select **Medical and health** then select one of the available regulations that will serve as a template.  Select **Next**.
    1. You can name your auto-label policy or use the default name.  Select **Next**.
    1. Next you choose a label to auto-apply.  Select **+ Choose a label**.  Select a label from the list, then select **Add**.
    1. You can assign the admin units to which this policy applies.  Leave the default set to full directory and select **Next**.
    1. Choose locations where you want to apply the label.  Review the information provide and  the available locations you can select. For this exercise, select the box next to **Exchange email** then select **Next**.
    1. You can set up common or advanced rules that define what the content the label is applied to.  Leave the default set to Common rules and select **Next**.
    1. You can define rules for content in all locations.  The label will be applied to content that matches rules defined on this page.  For the template you selected, you should see a line item. Expand it to view the conditions that apply.  Leave all the default settings  and select **Next**.
    1. Additional settings can be configured for email. Leave the defaults and select **Next**.
    1. You can decide to test the policy now or later.  Select **Leave policy turned off** then select **Next**.
    1. Review the settings. For the purpose of this exercise, you can cancel out with out creating the policy. Select **Cancel**.

1. From the left navigation panel, select **Home** to return to the Microsoft Purview portal.

1. Keep this page open, you'll use it in the next task.

### Task 2

In this task, you'll go through the process of applying a sensitivity label to a Microsoft Word document and then view the content marking (footer) that is generated by the label. 

   >**Note**: When using Microsoft Word online, you may experience be a delay before the option to select Sensitivity labels appears on the top ribbon.  It is recommended that you complete all remaining labs and then return back to this task.

1. You should still be on the home page for the Microsoft Purview Portal. 
1. From the Microsoft Purview portal, select the **app launcher icon**, next to where it says Microsoft Purview. Select the **Word icon**.  

1. Select **Create blank document**, then enter some text on the page.  On the top of the page, next to the Word icon, select where it says **Document** and rename the file to **Test-label** then press **Enter** on your keyboard.

1. On the far right of top menu bar (also referred to as the ribbon) is a down arrow, select it, then select **Classic Ribbon**.  This will make it easier to identity the sensitivity icon. Select **Sensitivity**, located next to the microphone icon. From the drop-down menu, select **Highly Confidential**.  

1. From the top menu bar, select **View**, then select **Reading view**.

1. Notice how the document includes the footer, "Classified as Highly Confidential".  

1. Close the Microsoft Word and Microsoft Purview tabs that are open on your browser to exit from those applications.

### Review

In this lab, you explored the capabilities of sensitivity labels.  You explored the settings for an existing sensitivity label and the corresponding policy to publish the label.  You applied the label and since the label included content markings, you were able to see that marking in the document to which you applied the label.
