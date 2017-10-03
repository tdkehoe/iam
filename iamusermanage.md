---

copyright:

  years: 2015, 2017

lastupdated: "2017-10-03"

---

{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:screen: .screen}
{:new_window: target="_blank"}

# Managing users and access policies
{: #iamusermanage}

Depending on the access options that you are authorized to manage, you can view and manage users across the account or organization. As an account owner, you can manage users in any of the access options that you administer and to which the user is assigned access in the current account.
{:shortdesc}

## Managing users

To manage users in your account, complete the following steps:

1. From the menu bar, click **Manage** &gt; **Account** &gt; **Users**. The Users window displays a list of users with their email addresses for the currently selected account.
2. Select the user name, or click **Manage user** from the **Actions** menu.
3. Then, depending on what action you need to take, you can choose to remove the user, assign a new policy, or manage the user's existing access.

Review the following sections for additional information about managing each type of access.

If you need to review your assigned access in an account that you have been added to, complete the following steps:

1. From the menu bar, click **Manage** &gt; **Security** &gt; **Identity & Access** &gt; **Users**.
2. Select your name.
3. Review your assigned roles.

If you need additional privileges, you must contact the organization manager or account owner to update the Cloud Foundry role, or contact the administrator for the service or service instance to update the service policy.

For details on the CLI commands that are used to manage accounts, orgs, and spaces, see [Commands for managing accounts, orgs, and roles](/docs/cli/reference/bluemix_cli/bx_cli.html#bx_commands_acctorg).

## Cloud Foundry access
{: #iammancfser}

To manage access to account organizations and spaces, you must be the account owner, organization manager, or space manager:

1. From the menu bar, click **Manage** &gt; **Security** &gt; **Identity & Access** &gt; **Users**.
2. Select the user name that you want to edit roles for.
3. From the **Actions** menu in the Cloud Foundry section, you can:

  * Remove the user from the organization
  * Edit the organization role
  * Edit the space role

You can also add a user to another organization by clicking **Assign Organization**, if you are the manager of an organization that the user is not yet a member of.


## Identity and access-enabled service access policies
{: #iammanidaccser}

To manage service policies or assign new service policies for users, you must be the account access administrator or the assigned administrator for the particular service or service instance. For more information about service policies and roles, see [Identity and access management policies and roles](/docs/iam/users_roles.html#iamusermanpol). For details on the CLI commands that are used to manage policies, see [Commands for managing API keys and policies](/docs/cli/reference/bluemix_cli/bx_cli.html#bx_commands_iam).

### Editing an existing policy

1. From the menu bar, click **Manage** &gt; **Security** &gt; **Identity & Access** &gt; **Users**.
2. Select the user name that you want to assign service policies for.
3. From the row for the policy that you want to edit, select the **Actions** menu, and then click **Edit policy**.
4. Edit the policy.
5. Click **Save policy**.

### Adding a new policy

1. From the menu bar, click **Manage** &gt; **Security** &gt; **Identity & Access** &gt; **Users**.
2. Select the user name that you want to assign service policies for.
3. Select **Assign policies**.
4. Select a service.
5. Select **All current regions** or a specific region, if your are prompted. 
**Note**: Not all services require a region selection.
6. Select **All current service instances** or select a specific service instance.
7. Select a role to define the scope of access for the policy.
8. Optional: Select **Add role** to specify an additional role for the policy.

### Removing a policy

1. From the menu bar, click **Manage** &gt; **Security** &gt; **Identity & Access** &gt; **Users**.
2. Select the user name that you want to assign service policies for.
3. From the row for the policy that you want to remove, select the **Actions** menu, and then click **Remove policy**.
4. Review the user policy details that you are about to remove, and then confirm by clicking **Remove policy**.
  

## Infrastructure services permissions

To assign or update infrastructure permissions, click the **Assign Infrastructure Access** link.

