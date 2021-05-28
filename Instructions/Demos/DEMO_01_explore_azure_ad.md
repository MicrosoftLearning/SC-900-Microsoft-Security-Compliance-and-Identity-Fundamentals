---
Demo:
    title: 'Azure Active Directory user settings'
    module: 'Module 2 Lesson 2: Describe the capabilities of Microsoft Identity and access management solutions: Explore the services and identity types of Azure AD'
---

# Demo: Azure Active Directory user settings

### Demo scenario

In this demo, you will access Azure Active Directory and walk through the various settings for an existing user.

1. Go to the **Home – Microsoft Azure** tab that is open on your browser.  If you previously closed the tab, open Microsoft Edge and in the address bar enter portal.azure.com and sign in with the same admin credentials as your Microsoft 365 tenant.

1. The Azure portal’s landing page shows Azure services, select **Azure Active Directory**. If it is not immediately visible, then from the search box next to where it says Microsoft Azure, enter Azure Active Directory.  You may also want to show how to access via the show portal menu icon (the three horizontal lines also referred to as hamburger icon, in the blue bar at the top of the page) to the left of where it says Microsoft Azure.

1. From the left navigation pane, select **Users**. Notice that your tenant is already configured with users.

1. From the list of users, select **Adele Vance**.

1. Notice that on the left navigation panel, **Profile** is selected.  Show/speak to the information shown on the profile page.

1. From the left navigation panel, select **Assigned roles**.  This user does not have any administrative roles assigned.  From the top of the page, select **+ Add assignments**, to the show the types of administrative roles available.  Do not add any, just close out of the page by selecting the **X** on the top right of the page.

1. From the left navigation panel, select **Groups**.  Speak to the fact that this user is a member of several groups.  Here you can speak to the types of groups.  To this user to other groups, you would simply select **+ Add memberships**.  Do not add any new groups, just speak to the point of how easy it is add a user to existing groups. Close out of the groups window by selecting the **X** on the top right corner of the page.

1. From the left navigation panel select **Licenses**. Notice that this user is assigned Microsoft 365 E5 licenses and EMS license.  To add a license, select **+ Assignments** from the top of the main window.  Show the licenses for this user. Do NOT change anything.  Close out of this window by selecting the **X** on the top right corner of the page.

1. From the left navigational panel select **Devices**.  Nothing shows up, but you can say that if this user were to have devices assigned, this is where it would show up.

1. From the left navigation panel, select **Azure role assignments**.  Call out:
    1. This is different than the assigned roles tab shown earlier in that that earlier tab is for role-based access control in Azure Active Directory (emphasize Active Directory).
    1. In this tab, you are able to view role assignments, assigned to users, for Azure resources. For example, if you were to create an Azure Resource Group, and you assign Adele a specific role, such as the owner or contributor for the resource group, you would see that role listed here. This is part of Azure Role Based Access Control (Azure RBAC). That role assignment is managed as part of that specific resource.

1. From the left navigational panel, select **Authentication methods**.  Call out the description that says, “Here, you can set the phone numbers and email addresses that users use to perform multi-factor authentication and self-service password reset and reset a user’s password.” If a user is configured for SSPR or is required to use MFA, and you, as the admin, populate this, then they will already be registered and will not have to go through the registration steps for SSPR or MFA.  It is common that user would self-register vs admin having to do this.

1. From the left navigational panel, select **Sign-ins**.  Here you can see sign-in activity for this user.  You may not see anything for this user, as she has not yet signed-in.

1. Select the **X** on the top right corner of the page. This returns you to the user list.  Before you close out of the user list, you can highlight that MFA is shown at the top of the page.  Select **Multi-Factor Authentication**.  This opens a new browser window.  Here you can bulk select MFA for users.  This is one way to you can enable MFA for users.  We will actually show more about MFA in the context of Conditional access which provides for more granular control of MFA.  Close the browser tab for Multi-factor authentication.

1. Select the **X** on the top right corner of the page. This returns you to the main page for the Contoso tenant.

### Review

In this demo, you showed walked through the settings of an existing user including groups to which the user can be assigned, the availability of roles, and assigning of user licenses.