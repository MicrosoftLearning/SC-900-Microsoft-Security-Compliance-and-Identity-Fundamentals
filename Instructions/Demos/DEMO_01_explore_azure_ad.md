<!---
---
Demo:
    Title: 'Explore Azure AD User Settings'
    Learning Path/Module/Unit: 'Learning Path: Describe the capabilities of Azure Active Directory (Azure AD), part of Microsoft Entra; Module 1: Describe the basic services and identity types of Azure AD; Unit 4: Describe the Azure AD identity types'
---
--->

# Demo: Azure AD user settings

This demo maps to the following Learn content:

- Learning Path: Describe the capabilities of Azure Active Directory (Azure AD), part of Microsoft Entra
- Module: Describe the basic services and identity types of Azure AD
- Unit: Describe the Azure AD identity types

## Demo scenario

In this demo, you'll access Azure Active Directory and walk through the various settings for an existing user.  NOTE to presenter:  This demo accesses Azure AD through the Microsoft 365 tenant. An alternative option to show learners is to access Azure AD through the Azure portal. The intent in going through the Microsoft 365 portal is to show that Microsoft 365 includes access to Azure AD.

1. Open Microsoft Edge.

1. In the address bar, enter **admin.microsoft.com** to access the Microsoft 365 admin center.

1. Sign in with your admin credentials.
    1. In the Sign-in window, enter **admin@WWLxZZZZZZ.onmicrosoft.com** (where ZZZZZZ is your unique tenant ID provided by your lab hosting provider) then select **Next**.
    1. Enter the admin password that should be provided by your lab hosting provider. Select **Sign in**.
    1. When prompted to stay signed- in, select **Yes**.

1. From the left navigation pane of the Microsoft 365 admin center, select **Show all**.

1. Under Admin centers, select **Azure Active Directory** (you may need to scroll down).  A new browser page opens to the My Dashboard page of the Azure Active Directory admin center. From the dashboard’s main windows, you'll see several tiles, including the Organization’ Identity tile (Contoso, the tenant and the Azure AD edition), a tile for users and groups, and more.

1. From the left navigation pane, select **Users**. Notice that your tenant is already configured with users.

1. From the list of users, select **Adele Vance**.

1. Notice that on the left navigation panel, **Profile** is selected.  Show/speak to the information shown on the profile page.

1. From the left navigation panel, select **Assigned roles**.  This user doesn't have any administrative roles assigned.  From the top of the page, select **+ Add assignments**, to the show the types of administrative roles available.  Do not add any, just close out of the page by selecting the **X** on the top right of the page.

1. From the left navigation panel, select **Groups**.  Speak to the fact that this user is a member of several groups.  Here you can speak to the types of groups.  To add this user to other groups, you would select **+ Add memberships**.  Do not add any new groups, just speak to the point of how easy it is to add a user to existing groups. Close out of the groups window by selecting the **X** on the top right corner of the page.

1. From the left navigation panel, select **Licenses**. Notice that this user is assigned Microsoft 365 E5 licenses and EMS license.  To add a license, select **+ Assignments** from the top of the main window.  Show the licenses for this user. Do NOT change anything.  Close out of this window by selecting the **X** on the top right corner of the page.

1. From the left navigational panel, select **Devices**.  Nothing shows up, but you can say that if this user were to have devices assigned, this is where it would show up.

1. From the left navigation panel, select **Azure role assignments**.  Call out:
    1. This is different than the assigned roles tab shown earlier in that that earlier tab is for role-based access control in Azure Active Directory (emphasize Active Directory).
    1. In this tab, you're able to view role assignments, assigned to users, for Azure resources. For example, if you were to create an Azure Resource Group, and you assign Adele a specific role, such as the owner or contributor for the resource group, you would see that role listed here. This is part of Azure Role Based Access Control (Azure RBAC). That role assignment is managed as part of that specific resource.

1. From the left navigational panel, select **Authentication methods**.  Call out the description that says, “Here, you can set the phone numbers and email addresses that users use to perform multi-factor authentication and self-service password reset and reset a user’s password.” If a user is configured for SSPR or is required to use MFA, and you, as the admin, populate this, then they'll already be registered and will not have to go through the registration steps for SSPR or MFA.  It's common that a user would self-register vs an admin having to do this.

1. From the left navigational panel, select **Sign-ins**.  Here you can see sign-in activity for this user.  You may not see anything for this user, as she has not yet signed-in.

1. Select the **X** on the top right corner of the page. This returns you to the user list.  Before you close out of the user list, you can highlight that MFA is shown at the top of the page.  Select **Multi-Factor Authentication**.  This opens a new browser window.  Here you can bulk select MFA for users.  This is one way to you can enable MFA for users.  We'll show more about MFA in the context of Conditional access and how it provides for more granular control of MFA.  Close the browser tab for Multi-factor authentication.

1. Select the **X** on the top right corner of the page. This returns you to the main page for the Contoso tenant.

### Review

In this demo, you showed the settings of an existing user including groups to which the user can be assigned, the availability of roles, and assigning of user licenses.
