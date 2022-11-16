<!---
---
Lab:
    Title: 'Explore Azure Network Security Groups (NSGs)'
    Learning Path/Module/Unit: 'Learning Path: Describe the capabilities of Microsoft security solutions; Module 1: Describe the basic security capabilities in Azure; Unit 6: Describe Azure Network Security groups'
---
--->

# Lab: Explore Azure Network Security Groups (NSGs)

This lab maps to the following Learn content:

- Learning Path: Describe the capabilities of Microsoft security solutions
- Module: Describe the basic security capabilities in Azure
- Unit: Describe Azure Network Security groups

## Lab scenario

In this lab, you will explore the function of network security groups in Azure.  You will do this by creating the VM without any network security group (NSG). You will then go through the process of creating an NSG and assigning the VM's interface to that NSG.  Once configured you will observe the default inbound and outbound rules and create new rules.
  
**Estimated Time**: 15-20 minutes

### Task 1

In this task you will create a Windows 10 virtual machine.

1. Open Microsoft Edge.  In the address bar enter **portal.azure.com**.

1. Sign in with your admin credentials.
    1. In the Sign in window enter **admin@WWLxZZZZZZ.onmicrosoft.com** (where ZZZZZZ is your unique tenant ID provided by your lab hosting provider) then select **Next**.

    1. Enter the admin password which should be provided by your lab hosting provider. Select **Sign in**.
    1. When prompted to stay signed- in, select **Yes**.
1. On the top left corner of the screen, next to where it says Microsoft Azure, select the Show portal menu icon (the three horizontal lines also referred to as hamburger icon) then select **All Services**.  
1. On the main window, under Featured, select Virtual Machines.  If  you don't see Virtual machines listed, enter it in the search bar, then select it from the search results.
1. From the top left of the page, select **+Create** then select **Azure Virtual machine**.
1. From the basics tab, fill in the following information (for anything not listed, leave the default settings):
    1. Subscription: verify the default setting to be Azure Pass – Sponsorship.

    1. Resource group:  select **Create new** then in the Name field enter **LabsSC900**, then select **OK**.
    1. Virtual machines name:  enter **SC900-WinVM**.
    1. Region: if the region field is not pre-populated then select the region closest to your location.
    1. Image:  from the drop-down, select **Windows 10 Pro, Version 21H2 – Gen 2**.
    1. Size:  select **see all sizes** from the drop-down and select **B2s**, then press **Select** on the bottom of the page.
    1. Username:  Enter a username of your choice.  Please make a note of it, as you will need it to access the VM.
    1. Password:  Enter a password of your choice.  Please make a note of it, as you will need it to access the VM.
    1. Public inbounds ports:  leave the default, **Allow selected ports**.
    1. Select inbound ports: leave the default, **RDP 3389**.
    1. Licensing:  select **I confirm I have an eligible Windows 10 license with multi-tenant hosting rights**, so that a checkmark appears in the box.
    1. Select **Next: Disks**.
1. You are now in the Disks tab for the VM configuration.  Leave all settings to the default and select **Next: Networking >**.
1. You are now in the Networking tab for the VM configuration.  
    1. NIC network security group: select **None**. Note: the purpose in selecting none at this step is to walk through the steps of creating a network security group from scratch, in the subsequent task.
    1. Public inbound ports:  leave the default value, **Allow selected ports**
    1. Select inbound ports:  leave the default value, **RDP (3389)**
    1. Delete pubic IP and NIC when VM is deleted:  select this so that a blue checkmark appears.
    1. Leave all other items  to the default.  
1. From the bottom of the page, select **Next: Review + Create>** then once the validation has passed, select **create**. It may take several minutes for the VM deployment to complete.
1. Once the VM deployment is complete, select **Go to resource**.
1. You are now in the SC900-WinVM page.
1. From the top of the page, select **Connect** then from the drop-down select **RDP**.
1. Note that the port prerequisite is not met.  In order to satisfy the prerequisite, an inbound network security rule with the destination port 3389, used by RDP, must be configured.  You will do that in the next task, when you create a network security group.
1. Leave this browser tab open.

### Task 2

Create a network security group, assign the network interface of the VM to that NSG, and create a new inbound rule for RDP traffic.

1. Open the SC900-WinVM – Microsoft Azure Tab on your browser.

1. From the top-left corner of the page, next to where it says Microsoft Azure, select the Show portal menu icon (the three horizontal lines also referred to as hamburger icon), then select **All Services**.
1. In the Filter services box next to where it says All services, enter **Network security groups** then from the results, select **Network security groups** (do not select Network security groups classic).
1. From the top of Network security groups page, select **+ Create**.
1. On the Basics tab of the Create network security group page, specify the following settings:
    1. Subscription:  Leave the default value (this is the Azure subscription provided by the authorized lab hoster)

    1. Resource group:  **LabsSC900**
    1. Name:  **NSG-SC900**
    1. Region:  leave the default.
    1. Select **Review + create** then select **Create**.
1. Once the deployment is complete, select **Go to resource**.
1. Notice the default inbound and outbound rules in the NSG.  Although the NSG has been created and there are default rules to filter traffic, no interface has been associated with the NSG.
1. From the left navigation pane on the NSG-SC900 page, under Settings, select **Network interfaces**.
1. Select the **+ Associate**, above search box.
1. On the right side of the page, is an field for selecting the network interface to associate to the NSG. Select the drown-down arrow, then select **sc900-winvmXXX** (the XXX will be specific to the network interface of your VM), then select **ok** on the bottom of the window.
1. Once the interface is associated to the NSG, it will show up on the list.
1. From the left navigation pane, select **Inbound security rules**.
1. The default inbound rules deny all inbound traffic that is not from a Vnet or a Azure load balancer so you need to setup a rule to allow inbound RDP traffic (traffic on port 3389). Recall that you cannot remove the default rules, but you can override them by creating rules with higher priorities.
1. From the top of the page, select **Add**:
1. On the Add inbound security rule window, specify the following settings:
    1. Source:  **Any**

    1. Source port ranges: **\***
    1. Destination:  **Any**
    1. Service:  **RDP**
    1. Action:  **Allow**
    1. Priority:  **300**; Note: rules with lower numbers have higher priority and are processed first.
    1. Name:  you can leave the default name or set to **AllowRDP**
1. Select **Add**
1. Once the rule is provisioned, it will appear on the list of inbound rules (you may need to refresh the screen).
    1. On the newly added rule, you will see a warning sign.  Select the newly added rule.  A window opens that shows the information about the rule. At the bottom of the window you will see the warning sign with the description, "RDP port 3389 is exposed to the Internet. This is only recommended for testing. For production environments, we recommend using a VPN or private connection."  Since we are only testing, leave it as is.  Close the window by selecting the **X** on the top right corner of the window.
1. Now verify that you can connect to the VM using RDP.  Select search field on the top of the page, next to where is says Microsoft Azure, to view the recent services.  Select **Virtual machines**.
1. Select the VM, **SC900-WinVM**.
1. From the top of the page, select **Connect** then from the drop-down select **RDP**.
1. Verify the IP address is set to Public IP address, leave the default port number and select **Download DRP file**.
1. Open the downloaded file and select **Connect**.
1. You will be prompted for your credentials.  Enter the Username and Password you used when you created the VM.
1. A Remote Desktop connection window opens indicating, The identity of the remote computer cannot be verified.  Do you wish to connect anyway?  Select **Yes**.
1. You are now connected to the VM. In this case you were able to connect to the VM because the inbound traffic rule you created allows inbound traffic to the VM via RDP.
1. Keep the VM open, you will use it the next task.

### Task 3

The default outbound rules for NSG allow outbound internet traffic so you will validate that you can connect to the internet.  You will then go through the process of creating a custom outbound rule to block outgoing internet traffic and test that rule.

1. From the VM, select **Edge** to open the browser.  
1. Enter **www.bing.com** in the browser address bar and confirm you are able to connect to the search engine.
1. Close the browser on your VM, and minimize the VM (select the **_** on the top center of the page, next to the IP address), as you will use it in the subsequent steps.
1. Return to the Azure Portal, open the SC900-WinVM – Microsoft Azure Tab on your browser.
1. From the left navigation panel, under Settings, select **Networking**.
1. Select the **Outbound port rules** tab.  You will see the default outbound rules.  Note the default rule "AllowInternetOutBound". This rule allows all outbound internet traffic. You cannot remove the default rule, but you can override it by creating a rule with higher priority. From the right side of the page, select **Add outbound port rule**.
1. On the Add outbound security rule page, specify the following settings:
    1. Source:  **Any**

    1. Source port ranges:  **\***
    1. Destination:  **Service Tag**
    1. Destination service tag:  **Internet**
    1. Service:  **Custom** (leave the default)
    1. Destination port ranges:  * (be sure to put an asterisk in the destination port ranges field)
    1. Protocol: **Any**
    1. Action: **Deny**
    1. Priority:  **4000**
    1. Name:  **DenyInternet**
1. Select **Add**
1. Once the rule is provisioned, it will appear on the list of outbound rules.  Although it appears on the list, it will take a few minutes to take effect (wait a few minutes before continuing with the next steps).  
1. Return to your VM
1. Open the Edge browser in your VM and enter **www.bing.com**. The page should not display.  Note: if you are able to connect to the internet and you verified that all the parameters for the outbound rule were properly set, it is likely because it takes a few minutes for the rule to take effect.  Close the browser, wait a few minutes and try again.
1. Close the remote desktop connection, by selecting the **X** on the top center of the page where the IP address is shown.  A pop-up windows indicates Your remote session will be disconnected. Select **OK**.
1. In this task you successfully configured an outbound rule in your NSG, to block outbound internet traffic.

### Tear-down

VM's are a billed resource and although the cost of running the VMs in this demo are miniscule, it is recommended that you delete the resource group containing the VM and associated resources, at the completion of the course.

1. Open the SC900-WinVM – Microsoft Azure Tab on your browser.

1. From the top-left corner of the page, select **All Services**.
1. In the Filter services box next to where it says All services, enter **Resource groups** then from the results, select **Resource groups**.
1. Select **LabsSC900**.
1. From the top center of the LabsSC900 page, select **Delete resource group**.
1. In the window that opens, enter the resource group name, **LabsSC900**, to confirm deletion the resource group and all its resources, then select **Delete** from the bottom of the page.
1. It may take a few minutes for all the resources and resource group to be deleted.
1. Close all the open browser tabs.

### Review

In this lab you walked through the process of setting up a network security group (NSG), associating that NSG to the network interface of a virtual machine, and adding new rules to the NSG to allow inbound RDP traffic and to block outbound internet traffic.
