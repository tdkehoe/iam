---

copyright:

  years: 2017, 2018

lastupdated: "2018-10-30"

---

{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:screen: .screen}
{:new_window: target="_blank"}
{:tip: .tip}

# Managing access to resources
{: #iammanidaccser}

To manage access or assign new access for users by using IAM policies, you must be the account owner, administrator on all services in the account, or the assigned administrator for the particular service or service instance. For more information about access policies and roles, see [IAM access](/docs/iam/users_roles.html).

## Editing existing access

1. From the menu bar, click **Manage** &gt; **Security** &gt; **Identity and Access**, and then select **Users**.
2. Select the name of the user that you want to assign access.
3. From the row for the policy that you want to edit, select the **Actions** menu, and then click **Edit policy**.
4. Edit the policy.
5. Click **Save**.

When editing access for a user or group, you might receive a message about not allowing duplicate policies. If you are editing an existing policy and the changes you make are in conflict with access that is already assigned, you can choose to change the policy you are currently editing to provide different access, or you can go to the existing policy it is in conflict with to review and make changes if needed. You might want to delete the policy you are editing, if a duplicate policy already exists that meets your needs.
{: tip}

To update a user policy by using the CLI, you can use the [ibmcloud iam user-policy-update](/docs/cli/reference/ibmcloud/cli_api_policy.html#ibmcloud_iam_user_policy_update) command.
```
ibmcloud iam user-policy-update USER_NAME POLICY_ID [-v, --version VERSION] {-f, --file JSON_FILE | [--roles ROLE_NAME1,ROLE_NAME2...] [--service-name SERVICE_NAME] [--service-instance SERVICE_INSTANCE] [--region REGION] [--resource-type RESOURCE_TYPE] [--resource RESOURCE] [--resource-group-name RESOURCE_GROUP_NAME] [--resource-group-id RESOURCE_GROUP_ID]}
```
{: codeblock}

### Assigning new access
{: #assignaccess}

You can assign access by using any of the three types of policies: 

* Access to resources within a resource group including the option for just one or all
* Access to resources in the account including including the option for just one type or all types
* Access to account management services including the option for just one or all services

If you want to enable a user full administrator access to complete account management tasks such as inviting and removing users, viewing billing and usage, managing service IDs, managing access groups, managing user access, and access to all account resources, you must create two policies: one on **All Identity and Access enabled services** with the role administrator and one on **All Account Management Services** with the role administrator.
{: tip}

### Access to resources within a resource group 

To assign access to all resources in a resource group or to just one service within a resource group, complete the following steps:

1. From the menu bar, click **Manage** &gt; **Security** &gt; **Identity and Access**, and then select **Users**.
2. From the row for the user that you want to assign access, select the **Actions** menu, and then click **Assign access**.
3. Select to **Assign access within a resource group**.
4. Select a resource group.
5. Choose a role for the **Assign access to a resource group** field to enable the user to view the resource group on their dashboard, edit the resource group name, or manage user access to the group. You can select **No access**, if you want the user to only have access to the resource that you specify and not the group that it is organized in.
6. Select a service within the resource group, or select to provide access to all services within the selected group.
7. Choose any combination of roles to assign the wanted access for the user. This access applies only to the resources that you selected for the policy. It doesn't give access to the actual container that is the resource group.
8. Click **Assign**.

### Access to resources
{: #resourceaccess}

To assign access to an individual resource in the account or access to all resources in the account, complete the following steps: 

1. From the menu bar, click **Manage** &gt; **Security** &gt; **Identity and Access**, and then select **Users**.
2. From the row for the user that you want to assign access, select the **Actions** menu, and then click **Assign access**.
3. Select to **Assign access to resources**.
4. Select a service or select **All Identity and Access enabled services**.
5. Select **All current regions** or a specific region, if your are prompted. 
6. Select **All current service instances** or select a specific service instance.
7. Depending on the service that you selected, you might see the following fields. If you don't enter values for these fields, the policy is assigned at the service instance level instead of the bucket level. 
    * **Resource type**: Enter **bucket**.
    * **Resource ID**: Enter the name of your bucket.
8. Choose any combination of roles to assign the wanted access for the user.
9. Click **Assign**.

You might receive a message that a policy already exists for the details that you've selected. If a policy with the exact details and roles is being created, you're prompted to make changes to the new policy since duplicate policies aren't allowed. If you're creating a policy with the same details but different role assignments as an existing policy, you're prompted to review and update the existing policy with the role assignments that you want to assign.
{: tip}

### Access to account management services 

To assign access to one or all account management services, complete the following steps: 

1. From the menu bar, click **Manage** &gt; **Security** &gt; **Identity and Access**, and then select **Users**.
2. From the row for the user that you want to assign access, select the **Actions** menu, and then click **Assign access**.
3. Select to assign access to **Account Management Services**
4. Select **All Account Management Services** or select a specific account management service.
5. Select any combination of roles to assign the wanted access.


## Removing access

1. From the menu bar, click **Manage** &gt; **Security** &gt; **Identity and Access**, and then select **Users**.
2. Select the user name that you want to remove access for.
3. From the row for the policy that you want to remove, select the **Actions** menu, and then click **Remove**.
4. Review the user policy details that you are about to remove, and then confirm by clicking **Remove**.

To remove a user policy by using the CLI, you can use the [ibmcloud iam user-policy-delete](/docs/cli/reference/ibmcloud/cli_api_policy.html#ibmcloud_iam_user_policy_delete) command.
```
ibmcloud iam user-policy-delete USER_ID POLICY_ID [-f, --force]
```
{: codeblock}

## Reviewing your assigned access

If you need to review your assigned access in an account that you've been added to, complete the following steps:

1. From the menu bar, click **Manage** &gt; **Security** &gt; **Identity and Access**, and then select **Users**.
2. Select your name.
3. Review your assigned access in the **Access policies** section.

If you need more access, you must contact the account owner to update your access or contact the administrator for the service or service instance to update the Cloud IAM access policy.
