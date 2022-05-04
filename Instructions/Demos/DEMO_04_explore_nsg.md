---
Demo:
    title: 'Azure Network Security Groups (NSGs)'
    module: 'Module 3 Lesson 1: Describe the capabilities of Microsoft security solutions: Describe basic security capabilities in Azure.'
---

# Demo: Azure Network Security Groups (NSGs)

## Demo scenario

In this demo, you will show the functionality of a network security group (NSG) in Azure.  You will do this by first creating a Virtual Machine (VM) without any NSG, as part of the pre-demo setup. You will also create a NSG without any associated interface or subnet.  As part of the demo, you will show the default inbound and outbound rules for the NSG. You will then go through the process of assigning the VM's interface to the NSG.  Once configured you will test the connection to the VM, using the default NSG rules and also rules that you will create.
  
### Pre-demo setup part 1

 Instructors it is recommended that you do this **BEFORE** class time as it can take several minutes to create a VM. In this setup, you will create a Windows 10 virtual machine.

1. Open the **Home – Microsoft Azure** tab on your browser.  If you previously closed the tab, open a browser page and in the address bar, enter portal.azure.com and sign back in.

1. In the search box, in the blue bar on the top of the page next to where it says Microsoft Azure, enter **Virtual machines**, then select **Virtual Machines** from the search results.  

1. From the top left of the page, select **+Add** then select **+Virtual machine**.

1. From the basics tab, fill in the following information (for anything not listed, leave the default settings):
    1. **Subscription**: verify the default setting to be Azure Pass – Sponsorship.
    1. **Resource group**: select **Create new** then in the Name field enter **LabsSC900-RG**, then select **OK**.
    1. **Virtual machines name**:  enter **SC900-WinVM**.
    1. **Region**:  leave the default.
    1. **Availability options**: be sure to select **No infrastructure redundancy required**.  NOTE: it is very important that availability options be set to No infrastructure redundancy required, otherwise the demo will not work as intended.  Having an availability option requires an NSG and we are intentionally creating the VM without an NSG.
    1. **Image**:  from the drop-down, select **Windows 10 Pro, Version 20H2 – Gen 1**.
    1. **Size**:  select **see all sizes** from the drop-down and select **B2s**, then press **Select** on the bottom of the page.
    1. **Username**:  Enter a username of your choice.  Please make a note of it, as you will need it to access the VM.
    1. **Password**:  Enter a password of your choice.  Please make a note of it, as you will need it to access the VM.
    1. **Public inbounds ports**:  you can leave the defaults setting (Doesn't matter what you select here as the network settings will override what you do here).
    1. **Licensing**:  select **I confirm I have an eligible Windows 10 license with multi-tenant hosting rights**, so that a check-mark appears in the box.
    1. Select **Next: Disks**.

1. You are now in the Disks tab for the VM configuration.  Leave all settings to the default and select **Next: Networking >**.

1. You are now in the Networking tab for the VM configuration.  Fill in the following information (for anything not listed, leave the default settings):
    1. NIC network security group:  select **None**.  Note: By selecting none you are ensuring that the NIC does not have an NSG.  In a subsequent step in the demo you will create a NSG and assign the VM NIC to the NSG you create.
    1. Since other settings for the VM will be kept as their default, go ahead and select Next: **Review + Create>**.

1. Review the configuration for your VM.  A few points to note: This VM has a public IP address and no NIC network security group.  From a security perspective this leaves the VM exposed.  We will address this in a subsequent task. Select **Create**.  It may take several minutes for the VM deployment to complete.

1. Note the name of the network interface, **sc900-winvmXXX** (the XXX will be specific to the network interface of your VM).

1. Once the VM deployment is complete, select **Go to resource**.  You are now in the SC900-WinVM page.  Note the public IP address.

1. From the left navigation panel, select **Networking** and note the network interface **sc900-winvmXXX** (the XXX will be specific to the network interface of your VM).  There should be no inbound our outbound rules associated with the interface.  

1. From the top of the page, select **Connect** as it is important to verify that you can connect to the VM.
    1. From the top of the page, make sure that **RDP** is selected (underlined).
    1. Verify the IP address is set to Public IP address, leave the default port number and select **Download DRP file**.
    1. **Open** the downloaded file and in the window that appears, select **Connect**.
    1. A window opens that will prompt you for your credentials. If the default window requests a PIN, select **More choices**, then select **Use a different account**.   You will be prompted for your credentials.  Enter the Username and Password you used when you created the VM.
    1. A Remote Desktop connection window opens indicating, The identity of the remote computer cannot be verified.  Do you wish to connect anyway?  Select **Yes**.
    1. You are now connected to the Windows VM you just created. Complete the Windows setup. Although you connected to the VM via RDP and a commonly used RDP Port, this VM has all ports open and there is nothing that is filtering traffic.  Close the remote desktop connection, by selecting the **X** on the top center of the page where the IP address is shown.  A pop-up windows indicates Your remote session will be disconnected. Select **OK**.

1. You are now back in the SC900-WinVM page in the Azure portal.  Leave this browser tab open for the next task.

### Pre-Demo setup part 2

Create a network security group, but do NOT assign the network interface of the VM to that NSG.  

1. Open the SC900-WinVM – Microsoft Azure Tab on your browser.

1. In the search box, in the blue bar on the top of the page next to where it says Microsoft Azure, enter **network security group** then select **Network security groups** from the search results.  Do not select Network security groups classic.

1. From the top of Network security groups page, select **+ Create**.

1. On the Basics tab of the Create network security group page, specify the following settings:
    1. Subscription:  Azure Pass – Sponsorship
    1. Resource group:  **LabsSC900-RG**
    1. Name:  **NSG-SC900**
    1. Region:  leave the default **(US) East US**
    1. Select **Review + create** then select **Create**.

1. Once the deployment is complete, select **Go to resource** and ensure everything is correct.  There should be 3 default inbound,  3 default outbound rules, and no subnets and no interfaces associated with the NSG.  Go back to the **Home** page of the Azure portal.  

### Demo

Walk through the settings for an NSG.  In this case you will do the walk-through for an existing NSG (the one you created it the above setup) that has not yet been assigned to a VM interface. You will then show the process of associating an interface to the NSG and the process for creating inbound and outbound rules.

1. Open the browser tab, **Home-Microsoft Azure**.  If you previously closed the tab, open a browser page and in the address bar, enter portal.azure.com and sign back in.

1. In the search box, in the blue bar on the top of the page next to where it says Microsoft Azure, enter **network security group** then select **Network security groups** from the search results.  Do not select Network security groups classic.

1. From the NSG page, select the NSG you created in the setup, **NSG-SC900**.

1. The **Overview** tab in the left navigation panel is highlighted.  Notice the default inbound and outbound rules in the NSG. Although the NSG has been created and there are default rules to filter traffic, no interface has been associated with the NSG. You can see this in the top right of the page where it says "Associated with: 0 subnets, 0 network interfaces".  For an NSG to do its thing, it has to be assigned to something.  In our case we will assign to the network interface for the VM that was previously created.

1. From the left navigation pane on the NSG-SC900 page, under Settings, select **Network interfaces**.

1. Select the **+ Associate**, above search box, then from the the drop-down select **sc900-winvmXXX** (the XXX will be specific to the network interface of your VM) then select **Ok**. As the interface is being associated you will see a notification box in the top right corner of the screen. Once the interface is associated to the NSG, it will show up on the list.

1. Go back to the **Overview** tab.  Note that on the top right of the page you will see "Associated with: 0 subnets, 1 network interfaces" – the interface is now assigned to the NSG. Also, highlight to the learners the default rules. For inbound, only traffic from other Azure virtual networks and Azure load balancer will be allowed. All other inbound traffic to the VM will be denied. Also call out the default outbound rules.  Only outbound traffic to other vnets and outbound internet traffic is allowed.  As part of the demo, it is recommended that you take a minute to show that inbound traffic is denied.
    1. In the search bar, on the top of the page, enter and select **Virtual Machines**.
    1. From the Virtual Machines page, select **SC900-WinVM**.
    1. From the top of the SC900-WinVM page, select **Connect** then select **RDP**.
    1. Verify the IP address is set to Public IP address, leave the default port number and select **Download DRP file**.
    1. **Open** the downloaded file and select **Connect**.
    1. After a few seconds of trying to connect, you will see the failure message, indicating that the remote Desktop can’t connect to the remote computer. Select **OK**.

1. Now that you showed the impact of the NSG default inbound rules, you will want to create a new rule to allow inbound RDP traffic.  Call out that you cannot delete the existing default rules, you can only create new ones with higher priority.
    1. From the left navigation panel, under Settings, select **Networking**.  You are in the networking page of the VM and although you can create an inbound rule and outbound rule from here, go back to the NSG page, after all the demo is about NSG.  **Select NSG-SC900**, it is the link in the middle of the window.

1. You are now in the NSG overview page.  Note the information about the NSG. From the left navigation panel of the NSG page, under settings, select **Inbound security rules**, then select **+ Add** from the top of the page. On the Add inbound security rule page, speak to the various settings. It is recommended that you actually create the rule to allow inbound RDP traffic, with the following settings:
    1. Source: **Any**
    1. Source port ranges: **\***
    1. Destination: **Any**
    1. Service: **RDP**
    1. Action: **Allow**
    1. Priority: **300**; Note: rules with lower numbers have higher priority and are processed first. So the priority for this new rule needs to be higher than the priority for the existing rule that denys all inbound traffic.
    1. Name: **AllowRDP**
    1. Select **Add**
    1. Once the rule is provisioned, it will appear on the list of inbound rules.

1. Now checkout the out **Outbound security rules**.  Select **+ Add** from the top of the page and speak to the various settings.  I recommend creating the rule – The settings below create a rule to deny outbound internet traffic:
    1. Source: **Any**
    1. Source port ranges: **\***
    1. Destination: **Service Tag**
    1. Destination service tag: **Internet**
    1. Service: **Custom** (leave the default)
    1. Destination port ranges: **\*** (be sure to put an asterisk in the destination port ranges field).
    1. Protocol: **Any**
    1. Action: **Deny**
    1. Priority: **4000** (the point to call out is that the priority needs to be higher than priority for the existing rule that allows internet outbound traffic)
    1. Name: **DenyInternet**
    1. Select **Add**
    1. Once the rule is provisioned, it will appear on the list of outbound rules.

1. Now go back to your VM and test the rules.  From the top of the page, select **SC900-VM**, above where it says outbound security rules.

1. Test the inbound rule by verifying that you can connect to the VM using RDP.
    1. Select **Connect** from the left navigation panel.
    1. Verify the IP address is set to Public IP address, leave the default port number and select **Download DRP file**.
    1. **Open** the downloaded file and select **Connect**.
    1. You will be prompted for your credentials. Enter the Username and Password you used when you created the VM.  If the window prompting for your credentials requests a PIN, select  **More choices**, then select **Use a different account**.
    1. A Remote Desktop connection window opens indicating, The identity of the remote computer cannot be verified. Do you wish to connect anyway? Select **Yes**.
    1. You are now connected to the VM. highlight to the learner that in this case you were able to connect to the VM because the inbound traffic rule you created allows inbound traffic to the VM via RDP.

1. Now test the outbound NSG rule
    1. Open the Edge browser in the VM.
    1. Enter **www.bing.com**. The page should not display. Note: if you are able to connect to the internet and you verified that all the parameters for the outbound rule were properly set, it is likely because it takes a few minutes for the rule to take effect. Wait a few minutes and try again.

1. Close the remote desktop connection, by selecting the **X** on the top center of the page where the IP address is shown. A pop-up windows indicates Your remote session will be disconnected. Select **Ok**.

1. Return to the Home page of the Azure portal, by selecting **Microsoft Azure** on the blue bar on the top of the page.

### Tear-down

**IMPORTANT**: In this task you will delete the resource group and all the resources it contains.   This is important to avoid additional charges.

1. Open the SC900-WinVM – Microsoft Azure Tab on your browser.

1. From the top-left corner of the page, select **All Services**.

1. In the Filter services box next to where it says All services, enter **Resource groups** then from the results, select **Resource groups**.

1. Select **LabsSC900-RG**.

1. From the top center of the LabsSC900-RG page, select **Delete resource group**.

1. In the window that opens, enter the resource group name, **LabsSC900-RG**, to confirm deletion the resource group and all its resources, then select **Delete** from the bottom of the page.

1. It may take a few minutes for all the resources and resource group to be deleted.

#### Review

In this demo you showed the information and settings associated an NSG, including the process to associate an interface to the NSG, you showed the default inbound and outbound rules, and finally the steps to create a new rule.
