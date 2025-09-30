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

### Enable Microsoft 365 audit log and file monitoring

In this setup task, you'll enable the Audit log and file monitoring capabilities in Microsoft 365.

1. Open Microsoft Edge. In the address bar, enter **https://admin.microsoft.com**.

1. Sign in with the admin credentials for the Microsoft 365 tenant provided by your authorized lab hoster (ALH).

1. From the left navigation pane of the Microsoft 365 admin center, select **Show all**.

1. Under Admin centers, select **Security**.  A new browser page opens to the welcome page of Microsoft Defender.  

1. From the left navigation panel of the Microsoft Purview compliance portal, select **Show all**.

1. In the left navigation panel, scroll down and expand **System**.  From the expanded list, select **Audit**.  Note: the audit functionality is also accessible through the Microsoft Purview portal.

1. Once you land on the Audit page, wait 1-2 minutes.  If Auditing is NOT enabled, you'll see a blue bar on the top of the page that says start recording user and admin activity.  Select **Start recording user and admin activity**.  Once auditing is enabled, the blue bar disappears.

1. From the left navigation panel, under System, select **Settings**.

1. From the settings page, select **Cloud apps**.   Scroll down, then under Information Protection select **Files**.

1. If not already enabled, select the box next to where it says **Enable file monitoring** then select **Save**.  

### Configure Compliance administrator role

In this setup task, you'll add yourself, as the MOD administrator, to the Compliance administrator role group.

1. Open a new Microsoft Edge browser tab. In the address bar, enter **https://purview.microsoft.com**. To access the new Microsoft Purview portal, select the box next to where it says, **I agree to the terms of data flow disclosure and Privacy Statements**, then select **Get started**.  
1. From the left navigation panel, select **Settings**.
1. From the navigation panel that opens, select **Roles and scoped** to expand the option, then select **Role groups**.
1. In the search box on the right side of the screen, search on the term **Compliance**.  Select **Compliance Administrator**.
    1. Select **Edit**.
    1. Select **Choose users**.
    1. Search for MOD Administrator, select the box next to **MOD Administrator** then select the **Select** button on the bottom of the page.
    1. Select **Next** then select **Save**, then finally select **Done**.
1. This concludes the setup for the Microsoft 365 tenant, you can close the browser tabs.

## Pre-Demo setup of the Azure Subscription

For this setup you are using the Azure environment which is separate than the Microsoft 365 tenant provided. Logout of the Microsoft 365 Tenant and login using the Azure credentials.

### Azure virtual machine

Check that a VM has already been created. If not, then set it up now. You will use the VM as part of the NSG demo.

1. Open Microsoft Edge.  In the address bar, enter **https://portal.azure.com** and sign in with the Azure credentials provided by the authorized lab hoster (ALH).  This bring you to the Azure services home page.

1. In the blue search box at the top of the page, enter **Virtual Machines** then select **Virtual Machines** from the search results.

1. If a VM is already listed then skip the steps that follow, otherwise you'll need to create one.  Select **Create**, then from the drop-down menu, select **Azure Virtual machine**. Configure the following parameters (if a parameter is not listed, leave the default value).
    1. Resource group: Select **Create new** and enter **LabsSC900**, then select **OK**.
    1. Virtual machine name: enter **SC900-WinVM**.
    1. Availability options: From the drop down, select **No infrastructure redundancy required**.
    1. Security type: from the drop-down, select **Standard**.
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

Check that an NSG has already been created. If the NSG has not been created set it up now, but do not associate any interface to it nor create any rules. Those steps will be done as part of the NSG demo.

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

Set up a Log Analytics workspace and once it is created, create an instance of Microsoft Sentinel and add the Log Analytics workspace to it.

1. Open the Home-Microsoft Azure tab in your browser.

1. In the blue search box on the top of the page, enter **Log Analytics** and select it from the search results.
1. Select **+ Create**.
1. From the basics tab of the Create Log Analytics workspace, enter the following:
    1. Subscription: leave the default, this is the Azure subscription provided by the Authorized Lab Hoster (ALH).
    1. Resource group: select **SC900-Sentinel-RG**. If this resource group is not listed create it by selecting **Create new**, enter **SC900-Sentinel-RG**, then select **OK**.
    1. Name: **SC900-Sentinel-workspace**.
    1. Region: **East US** (A different default region may be selected based on your location)
    1. Select **Review + Create** (no tags will be configured).
    1. Verify the information you entered then select **Create**.
    1. It may take a minute or two for the new workspace to be created.
    1. Once it's created, select **Go to resource** to view information about the workspace.
1. At this point, the instance of Microsoft Sentinel has not yet been created. To create an instance of Sentinel, you need to go to the Microsoft Sentinel page. Use the blue search bar at the top of the page, to search for **Microsoft Sentinel** and select it from the search result.
1. To add the workspace to Microsoft Sentinel, you need to go to the Microsoft Sentinel page. Use the blue search bar at the top of the page, to search for **Microsoft Sentinel**
    1. From the Microsoft Sentinel page, select **+ Create**.
    1. Now you can add the workspace you just created. Select **SC900-Sentinel-workspace**, then select **Add**.  This may take a few minutes, as the free trial of Microsoft Sentinel activates.  Once it is activated, you select **Ok**.

### Review

In this setup, you enabled the audit log capability in your Microsoft 365 tenant and you also created verified that a VM was preconfigured in your Azure environment. You also prepared your Defender for Cloud and Microsoft Sentinel environment.
