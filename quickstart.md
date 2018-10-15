---

copyright:

  years: 2017, 2018

lastupdated: "2018-08-21"

---

{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:screen: .screen}
{:new_window: target="_blank"}

# Getting started tutorial
{: #getstarted}

This tutorial is intended to help you get up and running quickly with IBM Cloud Identity and Access Management (IAM) by  inviting users to your account and assigning Cloud IAM access to those users.

This tutorial applies to IAM-managed [resources](/docs/resources/acct_resources.html#resource) only. For services that do not support creating Cloud IAM policies for managing access, you can use [Cloud Foundry access](/docs/iam/cfaccess.html#cfaccess).


## Step 1. Invite users and assign initial access

You can invite one or multiple users and set an initial access policy for the users on the invitation. If you invite multiple users in one invitation, the same access is assigned to each of the users. In the **Access** section of the Invite users page, you only see the sections that you are permitted to assign.

As the account owner, you can assign Cloud IAM roles for users that you invite in the Services section. You can provide access to all resources in a resource group, all resources for a specific service in a resource group, all Identity and Access enabled services in the account, or a single resource in the initial policy that you assign in the invitation:

1. Go to **Manage** &gt; **Security** &gt; **Identity and Access**, and then select **Users**.
2. Click **Invite users**.
3. Specify the email address of the users that you want to invite.
4. In the **Access** section, expand the **Services** option.
5. Choose to assign access to a **Resource** or to resources within a **Resource group**.
6. Depending on your selection, follow the prompts to specify the access to an individual service instance, all Identity and Access enabled services, all resources in a resource group, or to a specific service within the selected resource group. If you selected the resource group option, you can also provide the user with access to view, edit, or manage access to the resource group by selecting a role for access to the resource group.
7. If you have permission, you can also assign Cloud Foundry or infrastructure access on the invitation.
8. Click **Invite users**.

For more information, see [Inviting users and assigning access](/docs/iam/iamuserinv.html#iamuserinv).

## Step 2. Create access groups

To streamline the process of assigning access to users in your account, you can create access groups which are made up of users and service IDs that you select, then you can then easily assign access by defining a single policy for the entire group.

### Set up your groups

To create an access group, complete the following steps:

1. From the menu bar, click **Manage** &gt; **Security** &gt; **Identity and Access**, and then select **Access Groups**.
2. Click **Create**.
3. Enter a name and optional description for your group, and click **Create**.

Next, continue to set up your group by adding users or service IDs:

1. Select the name of the group that you want to add to.
2. Click **Add users**.
3. Select the users that you want to add from the list, and click **Add to group**.
4. To add service IDs to the group, click the **Service IDs** tab and click **Add service ID**.
5. Select the IDs that you want to add from the list, and click **Add to group**.

### Assign access to your groups

After you have created your groups, you can assign access to all entities within the group with a single policy.

1. From the menu bar, click **Manage** &gt; **Security** &gt; **Identity and Access**, and then select **Access Groups**.
2. Select the name of the group that you want to assign access for.
3. Click **Assign access** to set up a policy that assigns access to a single resource in the account or all resources within a resource group.

By organizing resources in resource groups and users in access groups, you can assign a group of users access to a group of resources with a single policy thereby reducing the overall number of policies you need to manage.
{: tip}


## Step 3. Manage access for existing users

After you have invited users, assigned initial access, and created your access groups, you might want to assign additional access or edit the initial access that you assigned to ensure all users and groups in your account have the desired level of access.

### Assigning new access

You can assign access to a user for a resource group or a single resource.

1. From the menu bar, click **Manage** &gt; **Security** &gt; **Identity and Access**, and then select **Users**.
2. Click the name of the user that you want to assign access.
3. Click **Assign access**.
4. Choose how you want to assign access:
    * Select **Assign access within a resource group** to assign access to all resources within a group or to just resources for a specific service within a group. You can also provide the user with access to view, edit, or manage access to the resource group by selecting a role for access to the resource group. Select **No access** if you want the user to only have access to the specified resource and not the group that it is organized in.
    * Select **Assign access to resources** to assign access to all Identity and Access enabled resources across the account, all resources of a specific service across the account, a single instance, or a single resource within a specific service instance.
5. Select any combination of roles to define the scope of access. See [Cloud IAM roles](/docs/iam/users_roles.html#iamusermanrol) for more information.
6. Click **Assign**.


### Editing existing access

You can update existing access by editing the assigned roles for a user.

1. From the menu bar, click **Manage** &gt; **Security** &gt; **Identity and Access**, and then select **Users**.
2. Select the name of the user that you want to edit access for.
3. From the row for the policy that you want to edit, click **Edit policy** from the **Actions** menu.
4. Edit the policy by updating the assigned roles.
5. Click **Save**.

You can remove access from a user by clicking the **Remove** option from the **Actions** menu for the policy that you want to remove.

## Next steps

Learn what else you can do with Cloud IAM by checking out the [Cloud IAM features](/docs/iam/index.html#features) list.
