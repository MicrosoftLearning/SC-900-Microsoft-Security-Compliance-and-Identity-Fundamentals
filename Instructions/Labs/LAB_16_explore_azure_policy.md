<!---
---
Lab:
    Title: 'Explore Azure Policy'
    Learning Path/Module/Unit: 'Learning Path: Describe the capabilities of Microsoft compliance; Module 6: Describe the resource governance capabilities in Azure; Unit 2: Describe Azure Policy'
---
--->

# Lab: Explore Azure Policy

This lab maps to the following Learn content:

- Learning Path: Describe the capabilities of Microsoft compliance
- Module: Describe the resource governance capabilities in Azure
- Unit: Describe Azure Policy

## Lab scenario

Azure Policy helps to enforce organizational standards and to assess compliance at-scale. Azure Policy evaluates resources in Azure by comparing the properties of those resources to business rules. In this lab, you will  create a policy and see the impact of that policy.  You will also explore by compliance and remediation information available on the policy page.

**Estimated Time**: 20-25 minutes



### Task 1

In this task you will create a basic policy assignment to require a tag on a resource groups.
1.  Open Microsoft Edge. In the address bar enter **portal.azure.com**.

1. Sign in with your admin credentials.
    1. In the Sign in window enter **admin@WWLxZZZZZZ.onmicrosoft.com** (where ZZZZZZ is your unique tenant ID provided by your lab hosting provider) then select **Next**.

    1. Enter the admin password which should be provided by your lab hosting provider. Select **Sign in**.
    1. When prompted to stay signed- in, select **Yes**.

1. You are now in the Azure Portal.  In the search box, in the blue bar on the top of the page next to where it says Microsoft Azure, enter **policy**, then select **Policy** from the search results. This opens the Policy home page which provides a dashboard view.  The scope for the Dashboard view is the Azure subscription provided by the authorized lab hoster.  Since this is assumed to be a new instance of an Azure subscription for which there is not yet any policy defined or assigned, it is likely that you will not see any information in the Dashboard view.

1. Form the left navigation panel, under Authoring, select **Assignments**.

1. From the top of the page, select **Assign policy**.

1. The Assign policy wizard opens to  guide the admin in the process of assigning a policy.  Next to the Policy definition field, select the **ellipses**.  A list of the available policy definitions is provided.  

1. In the search bar enter, **Require a tag**.

1. From the search results, select **Require a tag on resource group** (you may need to scroll down), then press **Select**.  Note: the effect of this policy is to Deny the creation of any new resource group that does not satisfy the requirement.  

1. Note the default assignment name.  Keep the name as is and from the bottom of the page, select **Next**.

1. In the Tag name field, enter **Environment** then select **Next**.

1. Leave the default remediation settings as they are then select **Next**.

1. In the non-compliance message, enter **An environment tag is required**, then select **Next**. Note: this message will appear as the reason for non-compliance for resource groups that were created before the policy assignment and do not have an Environment tag.  For resource groups created after the policy was created, the creating of the resource group will be denied if there is no environment tag.

1. Review the policy assignment, then select Create.  If you don’t immediately see the policy, select **Refresh**. Note: It may take up to 30 minutes for the policy to take effect, but usually happens faster.

1. Exit from the Policy assignments page by selecting the **X** on the top right corner of the screen.

1. You are now in the Azure services home page.  Keep this page open, you will need it for the next task.

### Task 2

In this task you will see the impact of the Azure policy assignment, by attempting to create a resource group in Azure that does not have a tag.

1. Open the browser tab, Home – Microsoft Azure.

1. Form the top of the page, underneath where it says Azure Services, select **Resource groups**.

1. From the top left corner of the page, select **+ Create**.

1. From the Basics tab of the Create a resource group, leave the Subscription field as is.

1. In the Resource group field enter, **SC900-Labs**.

1. Leave the Region setting to the default, then select **Next: Tags**.

1. Leave the tag Name and Value field empty.  DO NOT POPULATE, then select **Review + create**.

1. You will see the validation failed and a failure icon (an x in a red circle) next to the tags tab. From the top of the page, select the **Tags** tab.  Note the error message in red text, regarding Policy enforcement. The condition that is part of the Azure policy was not satisfied so the resource group validation and creation is blocked, for non-compliance.  Note: If you don’t see the failure message and the resource group was created, it is because the policy has not yet taken effect. Go the Policy page for the policy you created in the previous task and once the policy takes effect you will see that the resource is not compliant. The details page will include the non-compliance message.

1. In the Name field enter Environment and in the Value field, enter **SC900-Labs**, then select **Next: Review + Create >** then select **Create**.

1. You will see the resource group listed.  

1. Select **Home** from the breadcrumb on the top of the page to return to the Azure home page. 

1. Keep the browser tab open you ill need it for the next task. 

### Task 3

Briefly explore the Azure policy page.

1. From the Azure home page, select **policy**. This opens the Policy home page which provides a dashboard view.  The scope for the Dashboard view is the Azure subscription provided by the authorized lab hoster.  

1. You should see the policy you created earlier, select it.

1. On the top of the page, under Essentials, you can see the name, description, and other essential information. 

1. From the left navigation panel, select **Compliance**.  As with the overview page, here you can view the compliance state of the listed policies and/or initiatives. 

1. From the left navigation panel, select **Remediation**.  This page provides a list of policies that have non-compliant resources.  By selecting on a policy on the remediation page, you can trigger the creation of a task to remediate the policy.  

1. Keep this browser tab (Policy – Microsoft Azure) open for the next task.

### Review

In this lab, you went through the Azure policy landing page. After the initial exploration of the Azure policy page, you went through the process of creating a policy and you were able to see the impact of that policy.
