<!---
---
Demo:
    Title: 'Azure Network Security Groups (NSGs)'
    Learning Path/Module/Unit: 'Learning Path: Describe the capabilities of Microsoft security solutions; Module 1: Describe the basic security capabilities in Azure; Unit 6: Describe Azure Network Security groups'
---
--->

# Demo: Azure Network Security Groups (NSGs)

This demo maps to the following Learn content:

- Learning Path: Describe the capabilities of Microsoft security solutions
- Module: Describe the basic security capabilities in Azure
- Unit: Describe Azure Network Security groups

## Demo scenario

In this demo, you will explore the function of network security groups in Azure. You will show the default inbound and outbound rules, create new rules, and test those rules. Note: The VM you will use with the NSG is already created for you by the authorized lab hoster (ALH).

### Pre-Demo setup

Create a network security group, but do NOT assign the network interface of the preconfigured VM to that NSG.  

1. Open the SC900-WinVM – Microsoft Azure Tab on your browser.

1. In the search box, in the blue bar on the top of the page next to where it says Microsoft Azure, enter **network security group** then select **Network security groups** from the search results.  Do not select Network security groups classic.

1. From the top of Network security groups page, select **+ Create**.

1. On the Basics tab of the Create network security group page, specify the following settings:
    1. Subscription:  leave the default.
    1. Resource group:  **LabsSC900-RG**
    1. Name:  **NSG-SC900**
    1. Region:  leave the default.
    1. Select **Review + create** then select **Create**.

1. Once the deployment is complete, select **Go to resource** and ensure everything is correct.  There should be 3 default inbound,  3 default outbound rules, and no subnets and no interfaces associated with the NSG.  Go back to the **Home** page of the Azure portal.  

### Demo

Walk through the settings for an NSG.  In this case you will do the walk-through for an existing NSG (the one you created it the above setup) that has not yet been assigned to a VM interface. You will then show the process of associating an interface to the NSG and the process for creating inbound and outbound rules.

1. Open the browser tab, **Home-Microsoft Azure**.  If you previously closed the tab, open a browser page and in the address bar, enter portal.azure.com and sign back in.

1. In the search box, in the blue bar on the top of the page next to where it says Microsoft Azure, enter **network security group** then select **Network security groups** from the search results.  Do not select Network security groups classic.

1. From the NSG page, select the NSG you created in the setup, **NSG-SC900**.

1. The **Overview** tab in the left navigation panel is highlighted.  Notice the default inbound and outbound rules in the NSG. Although the NSG has been created and there are default rules to filter traffic, no interface has been associated with the NSG. You can see this in the top right of the page where it says "Associated with: 0 subnets, 0 network interfaces".  For an NSG to do its thing, it has to be assigned to something.  In our case we will assign to the network interface for the VM that was preconfigured.

1. From the left navigation pane on the NSG-SC900 page, under Settings, select **Network interfaces**.

1. Select the **+ Associate**, above search box, then from the the drop-down select **sc900-winvmXXX** (the XXX will be specific to the network interface of your VM) then select **Ok**. As the interface is being associated you will see a notification box in the top right corner of the screen. Once the interface is associated to the NSG, it will show up on the list.

1. Go back to the **Overview** tab.  Note that on the top right of the page you will see "Associated with: 0 subnets, 1 network interfaces" – the interface is now assigned to the NSG. Also, highlight to the learners the default rules. For inbound, only traffic from other Azure virtual networks and Azure load balancer will be allowed. All other inbound traffic to the VM will be denied. Also call out the default outbound rules.  Only outbound traffic to other vnets and outbound internet traffic is allowed.  As part of the demo, it is recommended that you take a minute to show that inbound traffic is denied.
    1. In the search bar, on the top of the page, enter and select **Virtual Machines**.
    1. From the Virtual Machines page, select **SC900-WinVM**.
    1. From the top of the SC900-WinVM page, select **Connect** then select **RDP**.
    1. Note that the port prerequisite is not met.  In order to allow to satisfy the prerequisite, an inbound network security rule with the destination port 3389, used by RDP, must be configured.  

1. Now you will want to create a new rule to allow inbound RDP traffic.  Call out that you cannot delete the existing default rules, you can only create new ones with higher priority. From the left navigation panel, under Settings, select **Networking**.  You are in the networking page of the VM.
1. Verify that the **Inbound port rules** tab is selected (underlined) then select **Add inbound port rule** to create the rule to allow inbound RDP traffic, with the following settings:
    1. Source: **Any**
    1. Source port ranges: **\***
    1. Destination: **Any**
    1. Service: **RDP**
    1. Action: **Allow**
    1. Priority: **300**; Note: rules with lower numbers have higher priority and are processed first. So the priority for this new rule needs to be higher than the priority for the existing rule that denys all inbound traffic.
    1. Name: **AllowRDP**
    1. Select **Add**
    1. Once the rule is provisioned, it will appear on the list of inbound rules.

1. Now select the **Outbound port rules** tab and review the default rules.  Select **Add outbound port rule** from the top of the page and speak to the various settings.  I recommend creating the rule – The settings below create a rule to deny outbound internet traffic:
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

1. Now go back to your VM and test the rules.  From the top of the page, select **SC900-VM**.

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

1. As a general best practice it is beneficial to stop or tear-down the VM to avoid incurring cost, if it is being used only for demo or test purposes. In this case, however, do NOT tear-down the VM, as it will help feed cloud security posture management data when demoing Microsoft Defender for Cloud.  The VM will be torn down when the lab is cancelled.

#### Review

In this demo you showed the information and settings associated an NSG, including the process to associate an interface to the NSG, you showed the default inbound and outbound rules, and finally the steps to create a new rule.
