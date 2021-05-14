---
Demo:
    title: 'Getting started with Azure Network Security Groups (NSGs)'
    module: 'Module 3 Lesson 1: Describe the capabilities of Microsoft security solutions: Describe basic security capabilities in Azure.'
---


# Demo: Getting started with Azure Network Security Groups (NSGs).

## Demo scenario
In this Demo, you will show the function of network security groups in Azure.  You will do this by first creating a VM without any network security group (NSG).  Without any NSG to filter traffic, all the ports in the VM are exposed to the public internet.  You will then go through the process of creating an NSG and assigning the VM's interface to that NSG.  Once configured you will test the connection to the VM, using the default NSG rules and also rules that you will create.
  

## Instructions

#### Demo Part 1: SETUP - Instructors it is recommended that you do this BEFORE class time as it can take several minutes to create a VM. In this setp you will create a Windows 10 virtual machine.

1. Open Microsoft Edge.  In the address bar enter **portal.azure.com**.

1. Sign in with your admin credentials.
    1. In the Sign in window enter **admin@WWLxZZZZZZ.onmicrosoft.com** (where ZZZZZZ is your unique tenant ID provided by your lab hosting provider) then select **Next**.   
    1. Enter the admin password which should be provided by your lab hosting provider. Select **Sign in**.
    1. When prompted to stay signed- in, select **Yes**.

1. On the top left corner of the screen, next to where it says Microsoft Azure, select the Show portal menu icon (the three horizontal lines also referred to as hamburger icon) then select **All Services**.  

1. On the main window, under Featured, select Virtual Machines.

1. From the top left of the page, select **+Add** then select **+Virtual machine**.

1. From the basics tab, fill in the following information (for anything not listed, leave the default settings):
    1. Subscription: verify the default setting to be Azure Pass – Sponsorship.
    1. Resource group:  select **Create new** then in the Name field enter **LabsSC900**, then select **OK**.
    1. Virtual machines name:  enter **SC900-WinVM**.
    1. Image:  from the drop-down, select **Windows 10 Pro, Version 20H2 – Gen 1**.
    1. Size:  select **see all sizes** from the drop-down and select **B2s**, then press **Select** on the bottom of the page.
    1. Username:  enter **AzureUser**.
    1. Password:  enter **SC900AzureLabs**.
    1. Public inbounds ports:  you can leave the defaults setting (Doen't matter what you select here as the network settings will override what you do here).
    1. Licensing:  select **I confirm I have an eligible Windows 10 license with multi-tenant hosting rights**, so that a check-mark appears in the box.
    1. Select **Next: Disks**.

1. You are now in the Disks tab for the VM configuration.  Leave all settings to the default and select **Next: Networking >**.

1. You are now in the Networking tab for the VM configuration.  Fill in the following information (for anything not listed, leave the default settings):
    1. NIC network security group:  select **None**.  Note: By selecting none you are ensuring that the NIC does not have an NSG.  In a subsequent step in the demo you will create a NSG and assign the VM NIC to the NSG you create.
    1. Select **Next:  Management >**.

1. You are now in the Management tab for the VM configuration.  Leave all settings to the default and select **Next: Advanced>**.

1. You are now in the Advanced tab for the VM configuration.  Leave all settings to the default and select **Next: Tags>**.

1. You are now in the Tags tab for the VM configuration.  Leave all settings to the default and select **Next: Review + Create>**.

1. Review the configuration for your VM.  A few points to note: This VM has a public IP address and no NIC network security group.  From a security perspective this leaves the VM exposed.  We will address this in a subsequent task. Select Create.  It may take several minutes for the VM deployment to complete.

1. Note the name of the network interface, **sc900-winvmXXX** (the XXX will be specific to the network interface of your VM).

1. Once the VM deployment is complete, select **Go to resource**.  You are now in the SC900-WinVM page.  Note the public IP address.

1. From the top of the page, select **Connect** then from the drop-down select **RDP**.

1. Verify the IP address is set to Public IP address, leave the default port number and select **Download DRP file**.

1. Open the downloaded file and select **Connect**.

1. You will be prompted for your credentials.  For Username, enter **AzureUser**.  For the Password, enter **SC900AzureLabs**.

1. A Remote Desktop connection window opens indicating, The identity of the remote computer cannot be verified.  Do you wish to connect anyway?  Select **Yes**.

1. You are now connected to the Windows VM you just created. Complete the Windows setup. Although you connected to the VM via RDP and a commonly used RDP Port, this VM has all ports open and there is nothing that is filtering traffic.  Close the remote desktop connection, by selecting the **X** on the top center of the page where the IP address is shown.  A pop-up windows indicates Your remote session will be disconnected. Select **OK**.

1. You are now back in the SC900-WinVM page in the Azure portal.  Leave this browser tab open for the next task.

#### Demo Part 2:  Create a network security group and assign the network interface of the VM to that NSG.

1. Open the SC900-WinVM – Microsoft Azure Tab on your browser.

1. From the top-left corner of the page, next to where it says Microsoft Azure, select the Show portal menu icon (the three horizontal lines also referred to as hamburger icon), then select **All Services**.

1. In the Filter services box next to where it says All services, enter **Network security groups** then from the results, select **Network security groups** (do not select Network security groups classic).

1. From the top of Network security groups page, select **+ Create**.

1. On the Basics tab of the Create network security group page, specify the following settings:
    1. Subscription:  Azure Pass – Sponsorship
    1. Resource group:  **LabsSC900**
    1. Name:  **NSG-SC900**
    1. Region:  leave the default **(US) East US**
    1. Select **Review + create** then select **Create**.

1. Once the deployment is complete, select **Go to resource**.

1. Notice the default inbound and outbound rules in the NSG.  Although the NSG has been created and there are default rules to filter traffic, no interface has been associated with the NSG.  You can see this in the top right of the page where it says "Associated with:  0 subnets, 0 network interfaces".  As such, the VM is still vulnerable with all its ports exposed to the public internet.

1. From the left navigation pane on the NSG-SC900 page, under Settings, select **Network interfaces**.

1. Select the **+ Associate**, above search box.

1. From the associate network interface page, select **sc900-winvmXXX** (the XXX will be specific to the network interface of your VM), then select **Ok**.  As the interface is being associated you will see a notification box in the top right corner of the screen.  Once the interface is associated to the NSG, it will show up on the list.  

1. From the left navigation panel select **Overview**.  You are in the overview page of the NSG you created. On the top right of the page you will see "Associated with:  0 subnets, 1 network interfaces".  Also, highlight to the learners the default rules.  For inbound, only traffic from other Azure virtual networks and Azure load balancer will be allowed.  All other inbound traffic to the VM will be denied.  The next step is to test that.

1. From the top-left corner of the page, select **All services**, then under where is says featured, select **Virtual Machines**.

1. From the Virtual Machines page, select **SC900-WinVM**.

1. From the top of the **SC900-WinVM** page, select **Connect** then select **RDP**.

1. Verify the IP address is set to Public IP address, leave the default port number and select **Download DRP file**.

1. **Open** the downloaded file and select **Connect**.

1. After a few seconds of trying to connect, you will see the failure message, indicating that the remote Desktop can’t connect to the remote computer.  Select **OK**.

#### Demo Part 3: in this part of the demo, you will show how to create a NSG rule to allow inbound traffic using RDP on port 3389 and you will test that rule by showing that you can connect to the VM.

1. Open the SC900-WinVM – Microsoft Azure Tab on your browser.

1. From the left navigation panel, under Settings, select **Networking**.

1. With the Inbound port rules tab selected, you see the default inbound rules. You cannot remove the default rules, but you can override them by creating rules with higher priorities. From the right side of the page, select **Add inbound port rule**:

1. On the Add inbound security rule page, specify the following settings:
    1. Source:  **Any**
    1. Source port ranges: *
    1. Destination:  **Any**
    1. Service:  **RDP**
    1. Action:  **Allow**
    1. Priority:  **300**; Note: rules with lower numbers have higher priority and are processed first.
    1. Name:  **AllowRDP**

1. Select **Add**

1. Once the rule is provisioned, it will appear on the list of inbound rules.

1. Now verify that you can connect to the VM using RDP.  Select **Connect** from the left navigation panel.

1. Verify the IP address is set to Public IP address, leave the default port number and select **Download DRP file**. 

1. **Open** the downloaded file and select **Connect**. 

1. You will be prompted for your credentials.  For Username, enter **AzureUser**.  For the Password, enter **SC900AzureLabs**. 

1. A Remote Desktop connection window opens indicating, The identity of the remote computer cannot be verified.  Do you wish to connect anyway?  Select **Yes**.

1. You are now connected to the VM.  highlight to the learner that in this case you were able to connect to the VM because the inbound traffic rule you created allows inbound traffic to the VM via RDP.

1. Keep the VM and open, you will use in the next step of the demo, which focused on outbound traffic.


#### Demo Part 4:  In this part of the demo, you will show outbound traffic on the VM.  The default outbound rules for NSG allow outbound internet traffic so you will show that you can connect to the internet.  You will then show the process to create a custom outbound rule to block outgoing internet traffic and test that rule.

1. From the VM, select **Edge** to open the browser.  

1. Enter **https://www.bing.com** in the browser address bar and confirm you are able to connect to the search engine. Highlight to the learners that the default outbound rules of the NSG includes a rule to allow outbound internet traffic.

1. Close the edge browser on your VM, but keep the VM open.  

1. Return to the Azure portal, Open the SC900-WinVM – Microsoft Azure Tab on your browser.

1. From the left navigation panel, under Settings, select **Networking**.

1. Select the **Outbound port rules** tab.  You will see the default outbound rules. Highlight to the learner the default rule "AllowInternetOutBound". You cannot remove the default rules, but you can override them by creating rules with higher priorities.  In this next step you will create a rule to deny outbound internet traffic. From the right side of the page, select **Add outbound port rule**.

1. On the Add outbound security rule page, specify the following settings:
    1. Source:  **Any**  
    1. Source port ranges:  *
    1. Destination:  **Service Tag**
    1. Destination service tag:  **Internet**
    1. Service:  **Custom** (leave the default)
    1. Destination port ranges:  * (be sure to put an asterisk in the destination port ranges field).
    1. Protocol: **Any**
    1. Action: **Deny**
    1. Priority:  **4000**
    1. Name:  **DenyInternet**

1. Select **Add**

1. Once the rule is provisioned, it will appear on the list of outbound rules.  Wait a few minutes before continuing to give time for the rule to fully take effect.

1. Return to your VM.

1. Open the Edge browser in your VM and enter **https://www.bing.com**.  The page should not display.  Note: if you are able to connect to the internet and you verified that all the parameters for the outbound rule were properly set, it is likely because it takes a few minutes for the rule to take effect.  Wait a few minutes and try again.

1. Close the remote desktop connection, by selecting the **X** on the top center of the page where the IP address is shown.  A pop-up windows indicates Your remote session will be disconnected. Select **OK**.

1. In this task you successfully configured an outbound rule in your NSG, to block outbound internet traffic.

#### Demo Part 5:  IMPORTANT: In this task you will delete the resource group and all the resources it contains.   This is important to avoid additional charges.

1. Open the SC900-WinVM – Microsoft Azure Tab on your browser.

1. From the top-left corner of the page, select **All Services**.

1. In the Filter services box next to where it says All services, enter **Resource groups** then from the results, select **Resource groups**.

1. Select **LabsSC900**.

1. From the top center of the LabsSC900 page, select **Delete resource group**.

1. In the window that opens, enter the resource group name, **LabsSC900**, to confirm deletion the resource group and all its resources, then select **Delete** from the bottom of the page.

1. It may take a few minutes for all the resources and resource group to be deleted.

#### Review

In this demo you showed the process of creating an NSG and assigning that NSG to a VM interface.  You then shows the impact of the default NSG rules and you shows the process to create new inbound and outbound rules and the impact of those rules.
