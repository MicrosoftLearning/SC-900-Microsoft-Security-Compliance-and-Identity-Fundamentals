<!---
---
Demo:
    Title: 'Sensitivity labels in Microsoft Purview'
    Learning Path/Module/Unit: 'Learning Path: Describe the capabilities of the Microsoft Priva and Microsoft Purview; Module 2:Describe the data security solutions of Microsoft Purview; Unit 4: Describe sensitivity labels and policies in Microsoft Purview Information Protection'
---
--->

# Demo: Sensitivity labels in Microsoft Purview

This demo maps to the following Learn content:

- Learning Path: Describe the capabilities of the Microsoft Priva and Microsoft Purview
- Module: Describe the data security solutions of Microsoft Purview
- Unit: Describe sensitivity labels and policies in Microsoft Purview Information Protection

## Demo scenario

In this demo you'll show the capabilities of sensitivity labels.  You'll go through the settings for existing sensitivity labels that have been created and the corresponding policy to publish the label.   Then you'll see how to apply a label and the impact of that label, from the perspective of a user.

**NOTE**: The first time you use Word online with your Microsoft 365 tenant, it can take up to 15 minutes for the Sensitivity icon to appear on the ribbon. It's recommended that presenters open Word online (as shown in demo part 3) prior to starting the full demo to ensure sufficient time for the option to appear.

### Demo part 1 (optional)

If this is the first instance where you demo a Microsoft Purview solutions, it is recommended that you spend a couple of minutes introducing the Microsoft Purview portal, before getting into Sensitivity labels.

1. Open a Microsoft Edge and in the address bar, enter **https://purview.microsoft.com**, login with the credentials provided by the authorized lab hoster, then select **Get started**.  

1. Before getting into Sensitivity labels, take a few moments to explore the Microsoft Purview portal.

1. Select the tile **View all solutions** to see the grouping for the Microsoft Purview solutions.

1. From the left navigation panel you'll see options for Solutions, Learn, Settings, and recently selected solutions.
    1. **Solutions**. This opens a new panel with all the solutions and related portals.
    1. **Learn** to view links to docs, videos, and blogs.
    1. **Settings**. Explore these options at will. From here you can configure roles and scopes, data connector, and all solution settings.

1. Return to the home page by selecting **Home** from the left navigation panel.

### Demo Part 2

In this demo, you show the settings for an existing sensitivity label and the corresponding policy to publish the label.

1. You should be on the landing page of the  Microsoft Purview portal.  If not, open a browser tab in Microsoft Edge and enter, **`https://puriview.microsoft.com`** and login with the credentials provided by the authorized lab hoster.

1. From the landing page of the new Microsoft Purview portal, select the **View all solutions** tile, then select the **Information Protection** tile. Alternatively, you select **Solutions** from the left navigation panel, then select **Information Protection**.

1. You'll land on the overview page. From the left navigation panel, select **Sensitivity labels**. If you see a yellow banner indicating that your organization has not turned on the ability to process content in Office online files that have encrypted sensitivity labels applied and are stored in OneDrive and SharePoint.  Select **Turn on now**

1. Some labels have been preconfigured in your Microsoft 365 lab tenant, for your convenience. Expand the label named **Highly Confidential**, then select **All Employees**.  A window opens that provides information about this label.  Note the settings for this label.  Select **Edit label** If you don't see this option, select the ellipsis.
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
    1. Default settings for meetings and calendar events: Review the options and note the option to apply inheritance between Team meeting and artifacts. Don’t change any settings.  Select **Next**.
    1. Default settings for Fabric and Power BI content: Don’t change any settings.  Select **Next**.
    1. Name your policy: Since you're editing the policy, the name field is greyed out.  Select **Next**.
    1. Review and finish: Since nothing was changed, select **Cancel**.

1. From the left navigation panel, under Information protection, select Auto-labeling. Review the description. Note that you create auto-labeling policies to automatically apply sensitivity labels to email messages or OneDrive and SharePoint files that contain sensitive info. If there are auto-labeling policies configured, select one and review the policy information in the details pane.  If no policy is listed, you may choose to walk-through the steps to create one, if time permits.

1. From the left navigation panel, select Home to return to the Microsoft Purview  portal.

1. Keep this browser tab open.

### Demo Part 3

In this step, you'll go through the process of applying a sensitivity label to a Microsoft Word document and then view the content marking (footer) that is generated by the label. NOTE: When using Microsoft Word online, you may experience be a delay before the option to select Sensitivity labels appears on the top ribbon.  It is recommended that you complete all remaining labs and then return back to this task.

1. You should still be on the home page for the Microsoft Purview Portal. 
1. From the Microsoft Purview portal, select the **app launcher icon**, next to where it says Microsoft Purview. Select the **Word icon**.  

1. Under Create new, select **Blank document**, then enter some text on the page.  On the top of the page, next to the Word icon, select where it says **Document** and rename the file to **Test-label** then press **Enter** on your keyboard.

1. On the far right of top menu bar (also referred to as the ribbon) is a down arrow, select it, then select **Classic Ribbon**.  This will make it easier to identity the sensitivity icon. Select **Sensitivity**, located next to the microphone icon. From the drop-down menu, select **Highly Confidential** then select **All Employees**.  

1. From the top menu bar, select **View**, then select **Reading view**.

1. Notice how the document includes the footer, "Classified as Highly Confidential".  

1. Close the Microsoft Word tabs that are open on your browser to exit from Word, but keep the the browser tab to the Microsoft Purview home page open.

### Review

In this demo, you showed the settings that can be configured for sensitivity labels and the settings for policies to publish sensitivity labels. You also showed how to apply a label.
