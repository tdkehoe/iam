---

copyright:

  years: 2017, 2018

lastupdated: "2018-08-02"

---

{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:screen: .screen}
{:new_window: target="_blank"}
{:tip: .tip}

# Managing IAM access
{: #iammanidaccser}

To manage access or assign new access for users, you must be the account owner, administrator on all services in the account, or the assigned administrator for the particular service or service instance. For more information about access policies and roles, see [IAM access](/docs/iam/users_roles.html).

## Editing existing access

1. From the menu bar, click **Manage** &gt; **Security** &gt; **Identity and Access**, and then select **Users**.
2. Select the name of the user that you want to assign access.
3. From the row for the policy that you want to edit, select the **Actions** menu, and then click **Edit policy**.
4. Edit the policy.
5. Click **Save**.

To update a user policy using the CLI, you can use the [ibmcloud iam user-policy-update](/docs/cli/reference/ibmcloud/cli_api_policy.html#ibmcloud_iam_user_policy_update) command.
```
ibmcloud iam user-policy-update USER_NAME POLICY_ID [-v, --version VERSION] {-f, --file JSON_FILE | [--roles ROLE_NAME1,ROLE_NAME2...] [--service-name SERVICE_NAME] [--service-instance SERVICE_INSTANCE] [--region REGION] [--resource-type RESOURCE_TYPE] [--resource RESOURCE] [--resource-group-name RESOURCE_GROUP_NAME] [--resource-group-id RESOURCE_GROUP_ID]}
```
{: codeblock}

## Assigning new access
{: #assignaccess}

To enable a user access to all account resources with the ability to manage user access, create resource groups, and complete all other IAM management tasks, select the **All Identity and Access enabled services** option for this policy with the **Administrator** role assigned.
{: tip}

### Access to resources within a resource group 

To assign access to all resources in a resource group or to just one service within a resource group, complete the following steps:

1. From the menu bar, click **Manage** &gt; **Security** &gt; **Identity and Access**, and then select **Users**.
2. From the row for the user that you want to assign access, select the **Actions** menu, and then click **Assign access**.
3. Select to **Assign access within a resource group**.
4. Select a resource group.
5. Choose a role for the **Assign access to a resource group** field to enable the user to view the resource group on their dashboard, edit the resource group name, or manage user access to the group. You can select **No access**, if you want the user to only have access to the resource that you specify and not the group that it is organized in.
6. Select a service within the resource group, or select to provide access to all services within the selected group.
7. Choose any combination of roles to assign the wanted access for the user. This access applies only to the resources that you selected for the policy. It does not give access to the actual container that is the resource group.
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
7. Depending on the service that you selected, you might see the following fields. If you do not enter values for these fields, the policy is assigned at the service instance level instead of the bucket level. 
    * **Resource type**: Enter **bucket**.
    * **Resource ID**: Enter the name of your bucket.
8. Choose any combination of roles to assign the wanted access for the user.
9. Click **Assign**.


## Removing access

1. From the menu bar, click **Manage** &gt; **Security** &gt; **Identity and Access**, and then select **Users**.
2. Select the user name that you want to remove access for.
3. From the row for the policy that you want to remove, select the **Actions** menu, and then click **Remove**.
4. Review the user policy details that you are about to remove, and then confirm by clicking **Remove**.

To remove a user policy using the CLI, you can use the [ibmcloud iam user-policy-delete](/docs/cli/reference/ibmcloud/cli_api_policy.html#ibmcloud_iam_user_policy_delete) command.
```
ibmcloud iam user-policy-delete USER_ID POLICY_ID [-f, --force]
```
{: codeblock}

## Reviewing your assigned access

If you need to review your assigned access in an account that you have been added to, complete the following steps:

1. From the menu bar, click **Manage** &gt; **Security** &gt; **Identity and Access**, and then select **Users**.
2. Select your name.
3. Review your assigned access in the **Access policies** section.

If you need more access, you must contact the account owner to update your access or contact the administrator for the service or service instance to update the Cloud IAM access policy.
