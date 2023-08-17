<!---
---
Pre-Demo Setup:
    Title: 'Demo Setup'
---
--->

## WWL Tenants - Terms of use
If you are being provided with a tenant as a part of an instructor-led training delivery, please note that the tenant is made available for the purpose of supporting the hands-on labs in the instructor-led training.

Tenants should not be shared or used for purposes outside of hands-on labs. The tenant used in this course is a trial tenant and cannot be used or accessed after the class is over and are not eligible for extension.

Tenants must not be converted to a paid subscription. Tenants obtained as a part of this course remain the property of Microsoft Corporation and we reserve the right to obtain access and repossess at any time.

## Pre-Demo Setup of the Microsoft 365 Tenant

### Enable Microsoft 365 audit log

In this setup task, you'll enable the Audit log capability in Microsoft 365.  Although documentation indicates that audit log is turned on by default, most lab tenants don't have this feature enabled, and it can take several hours for this to take effect.  It's beneficial to enable this feature, as Microsoft 365 uses audit logs for user insights and activities identified in policies and analytics insights.

1. Open Microsoft Edge. In the address bar, enter **admin.microsoft.com**.

1. Sign in with your admin credentials.
    1. In the Sign-in window, enter **admin@WWLxZZZZZZ.onmicrosoft.com** (where ZZZZZZ is your unique Microsoft 365 tenant ID provided by your lab hosting provider) then select **Next**.
    1. Enter the admin password that should be provided by your lab hosting provider. Select **Sign in**.
    1. When prompted to stay signed- in, select **Yes**. This takes you to the Microsoft 365 admin center page.

1. From the left navigation pane of the Microsoft 365 admin center, select **Show all**.

1. Under Admin centers, select **Compliance**.  A new browser page opens to the welcome page of the Microsoft Purview compliance portal.  

1. From the left navigation panel of the Microsoft Purview compliance portal, select **Show all**.

1. In the left navigation panel, under solutions, select **Audit**.  Note: the audit functionality is also accessible through the Microsoft 365 Defender home page.

1. Verify that the **Search** tab is selected (underlined).

1. Once you land on the Audit page, wait 2-3 minutes.  If Auditing is NOT enabled, you'll see a blue bar on the top of the page that says start recording user and admin activity.  Select **Start recording user and admin activity**.  Once auditing is enabled, the blue bar disappears.  If the blue bar is not present, then auditing is already enabled, and no further action is required.

1. Return to the home page of the Microsoft Purview compliance portal by selecting **Home** from the left navigation panel.

### Microsoft Defender for Cloud Apps file monitoring

In this setup task, you will enable file monitoring in Microsoft Defender for Cloud Apps.

1. Open the browser tab for the Microsoft 365 admin center.  If you previously closed it, open a new browser tab and in the address bar, enter **admin.microsoft.com** and from the left navigation pane of the Microsoft 365 admin center, select **Show all**.

1. Under Admin centers, select **Security**.  A new browser page opens to the welcome page of the Microsoft 365 Defender portal.  

1. From the left navigation panel, select **Files**, which is listed under Cloud apps.

1. If not already enabled, you'll need to select **Enable file monitoring** and select the box next to where it says **Enable file monitoring** then select **Save**.  

1. From the left-most navigation panel, under cloud apps, select **Files** to return to the files page.  If you successfully enabled file monitoring, you should see the filter options on the top of the page.  It may take some time for files from the pre-configured lab tenant to be displayed.

## Pre-Demo setup of the Azure Cloud Slice Subscription

For this setup you are using the Azure Cloud Slice environment which is separate than the Microsoft 365 tenant provided. Logout of the Microsoft 365 Tenant and login using the Azure Cloud Slice credentials.

### Azure virtual machine

Check that a VM has already been created. If not, then set it up now. You will use the VM as part of the NSG demo.

1. Open Microsoft Edge.  In the address bar, enter **portal.azure.com**.

1. Sign in with the user credentials for the Azure Cloud Slice environment provided by Skillable or your ALH.
    1. In the Sign-in window, enter the username then select **Next**.  
    1. Enter the admin password that should be provided by your lab hosting provider. Select **Sign in**.
    1. If prompted to stay signed- in, select **Yes**.

1. On the top of the page, underneath where it says Azure Services, select **Virtual Machines**.  If you don't see it listed, then in the search box, in the blue bar on the top of the page next to where it says Microsoft Azure, enter **Virtual Machines** then select **Virtual Machines** from the search results.

1. If a VM is already listed then skip the steps that follow, otherwise you'll need to create one.  Select **Create**, then from the drop-down menu, select **Azure Virtual machine**. Configure the following parameters (if a parameter is not listed, leave the default value).
    1. Resource group: Select **Create new** and enter **LabsSC900**, then select **OK**.
    1. Virtual machine name: enter **SC900-WinVM**.
    1. Availability options: From the drop down, select **No infrastructure redundancy required**.
    1. Image: From the drop down select **Windows 11 Pro, version 22H2 - x64 Gen2** (or any Windows 10 or Window 11 image listed).
    1. Size: select **See all sizes** and select **Standard_B1s** then select **Select** at the bottom of the page.
    1. Username: enter **SC900-VM-User**
    1. Password:  enter a password and write it down, you will need it later!!!!
    1. Confirm password: re-enter the password.
    1. Public inbound ports: **None**.
    1. Licensing: select where it says, "I confirm I have an eligible Windows 10/11 license with multi-tenant hosting rights."  A checkmark should appear.
    1. Select **Next: Disks**
    1. OS disk type: from the drop-down, select **Standard SSD**.
    1. Select **Next: Networking**
    1. NIC network security group: select **None**.  You will create an NSG as part of the demo, so don't do it here!
    1. Delete public IP and NIC when VM is deleted:  select the box so a checkmark appears.
    1. Select **Review + create**, then when validation passes, select **Create**.
    1. Once the VM deployment is complete, select **Home** from the top of the page.

1. Keep the Azure browser tab open to continue with the pre-demo setup.

### Network security group

Here you will create a network security group but will not associate any interface to it nor create any rules. Those steps will be done as part of the NSG demo.

1. In the blue search bar on the top of the page, enter **Network security groups** groups. From the results, select **Network security groups** (do not select Network security groups classic).

1. Select **Create network security group**. On the Basics tab of the Create network security group page, specify the following settings:
    1. Subscription:  Leave the default value (this is the Azure subscription provided by the authorized lab hoster)
    1. Resource group:  **LabsSC900**
    1. Name:  **NSG-SC900**
    1. Region:  leave the default.
    1. Select **Review + create** then select **Create**.
    1. Once the deployment is complete (this happens very quickly), select **Go to resource**.

### Microsoft Defender for Cloud

The objective here is simply to access Microsoft Defender to Cloud for the first time. This is important because it can take up to 24 hours for Defender for Cloud to reflect an initial secure score.  

1. Open the Home-Microsoft Azure tab in your browser.

1. In the blue search bar enter **Microsoft Defender for Cloud**, then from the results list, select **Microsoft Defender for Cloud**.

1. If this is the first time you enter Microsoft Defender for Cloud with your subscription, you may land on the Getting started page, and may be prompted to upgrade.  Scroll to the bottom of the page and select **Skip**.  You'll be taken to the Overview page.

1. All subscriptions have foundational CSPM enabled by default, which provides a secure score, but it can take up to 24 hours for Defender for Cloud to reflect an initial secure score.

1. Select **Home** from the top of the page.

1. Keep the browser tab open to continue with the pre-demo setup.

### Microsoft Sentinel

Here you will create an instance of Microsoft Sentinel that you will use as part of the walk-through demo on Microsoft Sentinel.

1. Open the Home-Microsoft Azure tab in your browser.

1. In the search box, in the blue bar on the top of the page next to where it says Microsoft Azure, enter **Microsoft Sentinel** then select **Microsoft Sentinel** from the search results.

1. From the Microsoft Sentinel page, select **Create Microsoft Sentinel**.

1. From the Add Microsoft Sentinel to a workspace page, select **Create a new workspace**.

1. From the basics tab of the Create Log Analytics workspace, enter the following:
    1. Subscription:  Leave the default.
    1. Resource group: select **Create New**, then enter the name **SC900-Sentinel-RG** then select **OK**.
    1. Name: **SC900-LogAnalytics-workspace**.
    1. Region: **East US** (A different default region may be selected based on your location).
    1. Select **Review + Create** (no tags will be configured).
    1. Verify the information you entered then select **Create**.
    1. It may take a minute or two for the ne workspace to be listed, if you still don't see it, select **Refresh**, then select **Add**.

1. Once the new workspace is added, the Microsoft Sentinel | News & guides page will display, indicating that the Microsoft Sentinel free trial is activated.  Select **OK**.

### Review

In this setup, you enabled the audit log capability in your Microsoft 365 tenant and you also created verified that a VM was preconfigured in your Azure Cloud Slice environment. You also prepared your Defender for Cloud and Microsoft Sentinel environment.
