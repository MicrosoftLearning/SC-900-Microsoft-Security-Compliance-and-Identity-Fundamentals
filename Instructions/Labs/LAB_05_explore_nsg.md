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

In this lab, you'll explore the function of network security groups in Azure.  You'll do this by creating a network security group (NSG) and assigning the NSG to the interface of a pre-existing virtual machine (VM).  Once configured you'll observe the default inbound and outbound rules, create new rules, and test those rules.  In this lab, the VM you'll use with the NSG is created for you, so you'll first view some of the information associated with that VM.
  
**Estimated Time**: 30-45 minutes

### Task 1

In this task, you'll view some of the parameters associated with the VM that that was created for use with this lab.

1. Open Microsoft Edge.  In the address bar, enter **https://portal.azure.com**.

1. Sign in with your admin credentials.
    1. In the Sign-in window, enter the username provided by your lab hosting provider then select **Next**.
    1. Enter the admin password that should be provided by your lab hosting provider. Select **Sign in**.
    1. If prompted to stay signed- in, select **Yes**.

1. On the top of the page, underneath where it says Azure Services, select **Virtual Machines**.  If you don't see it listed, then in the search box, in the blue bar on the top of the page next to where it says Microsoft Azure, enter **Virtual Machines** then select **Virtual Machines** from the search results.

1. From the Virtual machines page, select the VM listed **SC900-WinVM**.

1. You're now in the SC900-WinVM page.  Note some of the basic information about the VM.

1. From the left navigation panel, select **Network Settings**.  The essentials sections of the main window shows the network interface for the VM.  Note how there is nothing listed next to Network security group, as there is not NSG assigned to the interface.

1. Keep this tab open.

### Task 2

In this task, you'll create a network security group, assign the network interface of the VM to that NSG, and create a new inbound rule for RDP traffic.

1. From the open Azure tab, *right-click* on the **Home** link at the top of the page and select **Open link in new tab** to open another page to Azure services.

1. In the blue search bar on the top of the page, enter **Network security groups** and, from the results, select **Network security groups**. Do not select *Network security groups (classic)*.

1. From the center of the page, select the blue button labeled **Create network security group**.  Alternatively, you can select **+ Create** from the top of Network security groups page.

1. On the Basics tab of the Create network security group page, specify the following settings:
    1. Subscription:  Leave the default value (this is the Azure subscription provided by the authorized lab hoster)
    1. Resource group:  **LabsSC900**
    1. Name:  **NSG-SC900**
    1. Region:  leave the default.
    1. Select **Review + create** then select **Create**.

1. Once the deployment is complete, select **Go to resource**.

1. You should be on the overview page for the newly created NSG.  If not, then from the left navigation panel, select **Overview**. On the top of the page underneath where it says Essentials, you'll see some basic information about the NSG you created.  Two points to note are that there are no Custom Security rules and there are no subnets nor network interfaces associated with this NSG.  Although there are no custom security rules, there are default inbound and outbound rules that are included with every NSG, as shown on the page.  Review both the inbound and outbound rules. The default inbound rules deny all inbound traffic that is not from a virtual network or an Azure load balancer.  The outbound rules deny all outbound traffic except traffic between virtual networks and outbound traffic to the Internet.

1. From the left navigation pane on the NSG-SC900 page, under Settings, select **Network interfaces**.
    1. Select **Associate**.
    2. In the field for network interface associations, select the **down-arrow**, select **sc900-winvmXXX**, then select **OK** on the bottom of the window. Once the interface is associated to the NSG, it will show up on the list.  The NSG is now assigned to the network interface of your VM.

1. Switch back to the **SC900-WinWM - Microsoft Azure** tab on the browser.  Refresh the page. Next to where it says Network security group, uou should now see the name of the NSG you just created.  If you still don't see it, wait another minute and then refresh the page again.

1. From the left navigation panel, select **Connect**. From the main window, next to where it shows the port number 3389, select **Check access**. The check access function sends signals (traffic) to the default RDP port 3389 of the VM to check if it is accessible. It may take a minute, but you will see Not accessible.  This is expected, because the DenyAllInBound NSG rule denies all inbound traffic to the VM.

1. Switch back to the **NSG-SC900 - Microsoft Azure** tab on the browser.

1. From the left navigation pane, select **Inbound security rules**. The default inbound rules deny all inbound traffic that is not from a virtual network or an Azure load balancer so you need to set up a rule to allow inbound RDP traffic (traffic on port 3389). Recall that you cannot remove the default rules, but you can override them by creating rules with higher priorities.

1. From the top of the page, select **Add**. On the Add inbound security rule window, specify the following settings:
    1. Source:  **Any**
    1. Source port ranges: **\***
    1. Destination:  **Any**
    1. Service:  **RDP**
    1. Action:  **Allow**
    1. Priority:  **1000**. Rules with lower numbers have higher priority and are processed first.
    1. Name:  Leave the default name or create your own descriptive name.
    1. Note the warning sign at the bottom of the page.  We're using RDP only for testing purposes and to demonstrate the functionality of the NSG.
    1. Select **Add**

1. Once the rule is provisioned, it will appear on the list of inbound rules (you may need to refresh the screen).

1. Leave this browser tab open.  

### Task 3

In this task, you'll test the newly created inbound NSG rule to confirm that you can establish a remote desktop (RDP) connection to the VM.  Once inside the VM you'll work to check outbound connectivity to the Internet from the VM.

1. Open the SC900-WinVM – Microsoft Azure Tab on your browser.

1. Select **Connect** from the left navigation panel.

1. Select **check access** (verify the port is set to 3389).  The status should show as "Accessible".

1. Now connect directly to the VM by clicking **Select** in the box that says Native RDP.
   
    1. From the Native RDP window that opens, select **Download RDP file**.
    1. If a download warning appears, select **Keep**, then on the pop-up window that appears, select **Open file**.
    1. A Remote Desktop Connection window opens; select **Connect**.
    1. You'll be prompted for your credentials.  Enter the Username and Password for the VM (refer to the resources tab on the lab instruction panel).
    1. A Remote Desktop connection window opens indicating: *The identity of the remote computer cannot be verified.  Do you want to connect anyway?*  Select **Yes**.

1. You're now connected to the VM. In this case you were able to connect to the VM because the inbound traffic rule you created allows inbound traffic to the VM via RDP.  After a few seconds on the Welcome screen you may see a window to Choose privacy settings for your device, select **Accept**.  If the Networks window appears, select **No**.

1. With the VM in the RDP session up and running, test outbound connectivity to the Internet from the VM.
    1. From the open VM, select **Microsoft Edge** to open the browser.  Since this is the first time you open Microsoft Edge, you may get a pop-up window, select **Start without your data**, then select **Continue without this data**, then select **Confirm and start browsing**.
    1. Enter **www.bing.com** in the browser address bar and confirm you're able to connect to the search engine.
    1. Once you've confirmed that you can access www.bing.com, close the browser window in the VM, but leave the VM up.

1. Minimize the VM by selecting the underscore **_** in the blue tab that shows the VM's IP address. This brings you back to the SC900-WinVM \| Connect page.

1. Keep the browser tab open; you'll use it the next task.

### Task 4

In the previous task you confirmed that you could establish an RDP connection to the VM. Once in the VM you also confirmed that you could establish an outbound connection to the Internet.  The outbound Internet traffic was allowed because the default outbound rules for NSG allow outbound Internet traffic.  In this task, you'll go through the process of creating a custom outbound rule to block outgoing Internet traffic and test that rule.

1. You should be on the SC900-WinVM \| Connect page. From the left navigation panel, select **Networking**. If you previously closed the browser tab, select the blue search bar on the top of the page and select Virtual machines, then select the VM, **SC900-WinVM**, then select **Networking**.

1. Select the **Outbound port rules** tab.  You'll see the default outbound rules.  Note the default rule "AllowInternetOutBound". This rule allows all outbound Internet traffic. You cannot remove the default rule, but you can override it by creating a rule with higher priority. From the right side of the page, select **Add outbound port rule**.

1. On the Add outbound security rule page, specify the following settings:
    1. Source:  **Any**
    1. Source port ranges:  **\***
    1. Destination:  **Service Tag**
    1. Destination service tag:  **Internet**
    1. Service:  **Custom** (leave the default)
    1. Destination port ranges:  **\*** (be sure to put an asterisk in the destination port ranges field)
    1. Protocol: **Any**
    1. Action: **Deny**
    1. Priority:  **1000**
    1. Name:  Leave the default name or create your own descriptive name.
    1. Select **Add**

1. Once the rule is provisioned, it will appear on the list of outbound rules.  Although it appears on the list, it will take a few minutes to take effect (wait a few minutes before continuing with the next steps).  


1. Return to your VM (the RDP icon for the VM should be shown on the task bar on the bottom of the page).

1. Open the Microsoft Edge browser in your VM and enter **www.bing.com**. The page should not display. If you're able to connect to the internet and you verified that all the parameters for the outbound rule were properly set, it's likely because it takes a few minutes for the rule to take effect.  Close the browser, wait a few minutes and try again. Azure subscriptions in the lab environment may experience longer than normal delays.

1. Close the remote desktop connection, by selecting the **X** on the top center of the page where the IP address is shown.  A pop-up window appears indicating Your remote session will be disconnected. Select **OK**.

1. From the top left corner of the window, just below the blue bar where it says Microsoft Azure, select **Home** to return to the Azure services home page.

1. Keep the Azure tab open on your browser.

### Review

In this lab, you walked through the process of setting up a network security group (NSG), associating that NSG to the network interface of a virtual machine, and adding new rules to the NSG to allow inbound RDP traffic and to block outbound Internet traffic.
