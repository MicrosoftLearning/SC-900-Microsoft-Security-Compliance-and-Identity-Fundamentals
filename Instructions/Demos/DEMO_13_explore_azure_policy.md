<!---
---
Demo:
    Title: 'Azure Policy'
    Learning Path/Module/Unit: 'Learning Path: Describe the capabilities of Microsoft compliance; Module 6: Describe the resource governance capabilities in Azure; Unit 2: Describe Azure Policy'
---
--->

# Demo: Azure Policy

This demo maps to the following Learn content:

- Learning Path: Describe the capabilities of Microsoft compliance
- Module: Describe the resource governance capabilities in Azure
- Unit: Describe Azure Policy

## Demo scenario

In this demo you will walk through the process of setting up an Azure policy and the impact of that policy.

### Demo Part 1

Create a policy to require a tag on a resource group (shows steps to create a policy from a template)

1. Open Microsoft Edge. In the address bar enter **portal.azure.com**.  You should already be signed in, if not sign in with your admin credentials.

1. In the search box, in the blue bar on the top of the page next to where it says Microsoft Azure, enter **policy**, then select **Policy** from the search results.

1. You are now in the overview of the Policy page. Notice the information available in the dashboard.

1. Form the left navigation panel, under Authoring, select **Assignments**.  You will notice that there is already a policy assignment, select **ASC Default**.  Review the description field. NOTE: The description field references Azure Security Center which has been rebranded to Microsoft Defender for Cloud.  Return to the Policy Assignments page by selecting the **X** on the top right corner of the page.

1. From the top of the page, select **Assign policy**. The Assign policy wizard opens to the guide the admin in the process of assigning a policy.

1. You start in the Basics tab.
    1. For the Scope, leave the default setting. In this case, the scope of the policy is the Azure subscription provided by the authorized lab hoster (ALH).
    1. For the Policy Definition, select the **ellipses**.  A list of the available policy definitions is provided.  In the search bar enter, **Require a tag**. From the search results, select **Require a tag on resource group** (you may need to scroll down), then press **Select**.  Note: the effect of this policy is to Deny the creation of any new resource group that does not satisfy the requirement.  
    1. Note the default assignment name.  Keep the name as is.
    1. Ensure that Policy enforcement is set to **Enabled**, select **Next**.

1. You are now in the Parameters tab.  In the Tag name field, enter **Environment** then select **Next**.

1. In the Remediation tab, leave the default settings as they are then select **Next**.

1. You are now in the Non-compliance messages tab.  In the non-compliance message field, enter **An environment tag is required**, then select **Next**. Note: this message will appear as the reason for non-compliance for resource groups that were created before the policy assignment and do not have an Environment tag.  

1. Review the policy assignment, then select **Create**.  If you don’t immediately see the policy, select **Refresh**. Note: It may take up to 30 minutes for the policy to take effect, but usually happens much faster.

1. Exit from the Policy assignments page by selecting the **X** on the top right corner of the screen.

1. You are now in the Azure services home page.  Keep this page open, you will need it for the next task.

### Demo Part 2

In this task you will see the impact of the Azure policy assignment, by attempting to create a resource group in Azure that does not have a tag.

1. Open the browser tab, Home – Microsoft Azure.

1. Form the top of the page, underneath where it says Azure Services, select **Resource groups**.

1. From the top left corner of the page, select **+ Create**.

1. From the Basics tab of the Create a resource group, leave the Subscription field as is.

1. In the Resource group field enter, **SC900-Labs**.

1. Leave the Region setting to the default, then select **Next: Tags**.

1. Leave the tag Name and Value field empty.  DO NOT POPULATE, then select **Review + create**.

1. You will see a validate passed (the tag name and value are not required fields in the wizard), then select **Create**.

1. You will see a failure message on the top of the screen, “Failed to create the resource group. Select **View error details**”. The condition that is part of the Azure policy was not satisfied so the resource group creation was blocked, for non-compliance. Note: If you don’t see the failure message and the resource group was created, it is because the policy has not yet taken effect.  Go the Policy page for the policy you created in the previous task and once the policy takes effect you will see that the resource is not compliant.  The details page will include the non-compliance message.

1. The error summary shows the error type, “Resource ‘SC900-Labs’ was disallowed by policy.  Close this window by selecting the **X** on the top left corner of the screen.

1. From the Create a resource group window, select **Previous**.

1. You are back in the Tags page for Create a resource group.  In the Name field enter Environment and in the Value field, enter **SC900-Labs**, then select **Next: Review + Create >**.

1. Verify the tag and select **Create**.

1. In the Name field enter **Environment** and in the Value field, enter **Labs** (this value could be anything, the policy simply requires a tag value), then select **Next: Review + Create >** then select **Create**.

1. You will see the resource group listed.  

1. Call out to the learners that if there had been a resource group created prior to the policy, then that resource group would now show up as non-compliant against this policy assignment and it would need to be remediated, by applying the Environment tag.  There is a pre-existing resources group, ResourceGroup1, that is non-compliant and can be remediated, but the time for the status to update, after remediation, is longer than normal for the lab environment.

### Review

In this demo, you showed the process of setting up an Azure policy and the impact of that policy.
