---
Lab:
    Title: 'Explore sensitivity labels in Microsoft Purview'
    Learning Path/Module/Unit: 'Learning Path: Describe the capabilities of Microsoft compliance; Module 3: Describe information protection and data lifecycle management in Microsoft Purview; Unit 4: Describe sensitivity labels'
---


# Lab: Explore sensitivity labels in Microsoft Purview

## Lab scenario

In this lab you will explore the capabilities of sensitivity labels.  You will go through the settings for existing sensitivity labels that have been created and the corresponding policy to publish the label.   Then you will see how to apply a label and the impact of that label, from the perspective of a user.

**Estimated Time**: 20-25 minutes

### Task 1

In this task you will gain an understanding of what sensitivity labels can do by going through the settings for an existing sensitivity label that have been created and the corresponding policy to publish the label.

1. Open Microsoft Edge. In the address bar enter **admin.microsoft.com**.

1. Sign in with your admin credentials.
    1. In the Sign in window enter **admin@WWLxZZZZZZ.onmicrosoft.com** (where ZZZZZZ is your unique tenant ID provided by your lab hosting provider) then select **Next**.

    1. Enter the admin password which should be provided by your lab hosting provider. Select **Sign in**.
    1. When prompted to stay signed- in, select **Yes**. This takes you to the Microsoft 365 admin center page.

1. From the left navigation pane of the Microsoft 365 admin center, select **Show all**.

1. Under Admin centers, select **Compliance**.  A new browser page opens to the welcome page of the Microsoft Purview compliance portal.  

1. In the left navigation panel, under solutions, select **Information protection**.

1. Select the **Labels** tab from the top of the page.

1. A yellow information box is displayed that indicates, "Your organization has not turned on the ability to process content in Office online files that have encrypted sensitivity labels applied and are stored in OneDrive and SharePoint..."  Select **Turn on now**.  Once you do this, there can be a delay for the setting to propagate through the system.**
**

1. In the middle of the page, notice how there are labels already created.  Select **Confidential - Finance**.  A window opens that provides information about this label.  Note how this label is set to support both encryption and content marking.  Select Edit Label at the top of the page to view some of the basic configuration settings.

1. Configuration starts with providing a name and description for your label.  Don’t change anything.  Select **Next** at the bottom of the page.

1. Note the scope for this label.  The scope is set to Files & emails to which you can configure Encryption and content marking settings to protect labeled emails and office files.  Don’t change anything.  Select **Next** at the bottom of the page.

1. For the selected scope, Files & emails, you can configure to encrypt and/or mark the content.  Note how the protection settings for files and emails is set for both encryption and marking the content of files.  Review the definition of each.  Don’t change anything.  Select **Next** at the bottom of the page.

1. The Encryption window shows the configuration for the encryption settings.  Don’t change anything.  Review the information box under Configure encryption settings and review the configured settings. Notice how the user access to content is set to never expire.  You can also assign permissions to specific users and groups so only they can interact with content that has this label applied.  Under users and groups, the tenant is defined so all users in your tenant can view content that has this label.  The finance team is also listed and they have co-author permissions.  Don’t change any settings.  Select **Next** on the bottom of the page.

1. On the content markings page, take note of the information box on the top of the page.  Content markings will be applied to documents but only headers and footers will be applied to email messages. In other words, watermarks are not applied to emails.  The content marking associated with this label is a watermark that reads, HIGHLY CONFIDENTIAL.  Don’t change any settings.  Select **Next** on the bottom of the page.

1. You are now in the Auto-labeling for files and emails window.  Read the description of auto-labeling on the top of the page and the information box below it.  Also take note that this label is set for auto-labeling for specific conditions. Don’t change any settings.  Select **Next** on the bottom of the page.

1. This next window defines protection settings for teams, groups, and sites that have this label applied. This is not enabled, select **Next** on the bottom of the page.

1. This next window is a preview feature to automatically apply this label to Azure database columns (such as SQL, Synapse, and more) that contain the sensitive info types you choose.  This features is not enabled. Select **Cancel** at the bottom of the page to exit the label configuration wizard and return to the Information Protection page.

1. From the top of the Information protection page, select **Label policies**.  It is through label policies that sensitivity labels can be published.  

1. Select **Confidential-Finance Policy**.  A window opens that provides information about the policy.  This policy serves to publish the Confidential-Finance Policy labels and protects data that contains financial data for Contoso.  Also note how this policy is published to all.  

1. Select **Edit** policy from the top of the window.

1. Read the description under “Choose sensitivity labels to publish”.  Notice the label that is listed.  Don’t change any settings.  Select **Next** on the bottom of the page.

1. Read the description under “Publish to users and groups”.  Notice the this label is available to all users.  Don’t change any settings.  Select **Next** on the bottom of the page.

1. Review the policy settings.  Don’t change any settings.  Select **Next** on the bottom of the page.
    1. Read description under, "the Apply a default label to documents."  Notice there is no default label. Don’t change any settings.  Select **Next** on the bottom of the page.
    1. Read description under, "the Apply a default label to emails."  Select the drop down arrow in the input box, to view the available options. Don’t change any settings.  Select **Next** on the bottom of the page.
    1. Read description under, "the Apply a default label to Power BI content."  Notice there is no default label. Don’t change any settings.  Select **Next** on the bottom of the page.

1. The last configuration option is to name your policy.  Don’t change any settings.  Select **Cancel** on the bottom of the page to exit the policy configuration and return to the Information protection page.

1. From the Information protection page, select Auto-labeling.  Note there is no auto-labeling policy configured.  Don’t change any settings.  If you are wondering why there is no policy here, given that the label configuration is set to auto-labeling for files and emails, go back to the steps where you walked through the label configuration settings and review the description and information boxes associated Auto-labeling for files and emails.  Hint:  In the auto labeling tab for the sensitivity lab, it says.  "To automatically apply this label to files that are already saved (in SharePoint and OneDrive) or emails that are already processed by Exchange, you must create an auto-labeling policy."

1. From the left navigation panel, select Home to return to the Microsoft Purview compliance portal.

1. Keep this page open, you will use it in the next task.

### Task 2

In this task, you will go through the process of applying a label from the perspective of the user (in this case the user is the admin) and view the content marking that is generated by the label.

1. From the Microsoft 365 compliance center home page, select the **app launcher icon**, next to where it says Contoso Electronics. **right click on the Word icon** and select **Open in new tab**.  

1. Select **+ New blank document**, then enter some text on the page.  On the blue bar on the top of the page, select the down-arrow, next to where it says DocumentXX - Saved, and in the File Name box enter, **Test-label**.

1. From the top menu bar, select **Sensitivity**, if you don't immediately see this option, refresh the page. From the drop down select **Confidential - Finance**.  NOTE:  The Sensitivity option may take up to 15 minutes to show up.

1. From the top menu bar, select **View**, then select **Reading view**.

1. Notice how the document includes the watermark.  

1. Close the Microsoft Word tabs that are open on your browser to exit from Word.

### Task 3 (optional)

In addition to content marking, the label protection setting was set for encryption. Per the permissions that were configured with this label, members of the finance group can co-author documents with this label applied and users in the Contoso tenant can view.  In this task you will send this document to an email address to which you have access (ie., a personal email address) and that is NOT part of the WWLxZZZZ.OnMicrosoft.com domain and see what happens when you try to open the attachment.

1. From the Microsoft Purview compliance portal home page, select the **app launcher icon**, next to where it says Contoso Electronics. **right click on the Outlook icon** and select **Open in new tab**.

1. Select **New message** from the top left corner of the screen.  Enter an email address to which you have access and is not part of the WWLxZZZZ.OnMicrosoft.com domain and enter **Test** in the subject line.

1. Select **Attach**.

1. Select **Browse cloud locations**.

1. From the list that shows up, select the document you created and to which you applied the label **Test-label**. Select **Next** and select **Attach as a copy**.  Press **Send**.

1. Using the web browser on your lab VM, login to the email account to which you sent the document.  Note, the email may be directed to your junk folder.  When you attempt to open the attached word file you will see a notification that you do not have permission to open the document.

1. Close all the open browser tabs.

### Review

In this lab you will explore the capabilities of sensitivity labels.  You will go through the settings for existing sensitivity labels that had already been created and the corresponding policy to publish the label.   Then you will see how to apply a label and the impact of that label, from the perspective of a user.
