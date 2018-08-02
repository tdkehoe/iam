---

copyright:

  years: 2015, 2018
lastupdated: "2018-08-02"

---

{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:screen: .screen}
{:new_window: target="_blank"}
{:tip: .tip}

# Inviting users and assigning access
{: #iamuserinv}

To invite users and manage outstanding invitations, you must be either an account owner, an organization manager, or you must have infrastructure permissions to add users. You can invite users, cancel invitations, and resend a pending invitation to an invited user. In addition, you can invite a single user or multiple users at once.  
{:shortdesc}

## Inviting users

To invite users or manage user invitations in your account, complete the following steps: 

1. From the menu bar, click **Manage** &gt; **Security** &gt; **Identity and Access**, and then click **Users**. The Users page displays a list of users with their email addresses and status for the currently selected account.
2. Click **Invite users**.
3. Specify the email address of the user. If you are inviting more than one user with a single invitation, they are all assigned the same access.
4. Add one or more of the access options that you manage. You must assign at least one access option. For any additional access options that you don't add and configure, the default value of *no access* is assigned. You might see one or all of the following access options, depending on the options that you are authorized to manage: **Services**, **Cloud Foundry access**, **{{site.data.keyword.Bluemix_notm}} infrastructure access**. For more information, see [Assigning user access](/docs/iam/iamuserinv.html#assignaccess).

If you determine that a user does not need access, you can cancel an invitation for any users that are shown in a **Processing** or **Pending** state in the **Status** column. If an invited user did not receive an invitation, you can resend the invitation to any user in a **Pending** state.

If you want to invite users by using the CLI, see the [ibmcloud account user-invite](/docs/cli/reference/ibmcloud/cli_acct_org_role.html#ibmcloud_account_user_invite) command.
{: tip}

## Assigning user access
{: #assignaccess}

You assign access for users as you invite them by assigning Cloud IAM policies, Cloud Foundry access, and infrastructure permissions. Depending on the access options that you are authorized to manage, you can invite and provide access for users across the account, resource groups, organizations, spaces, service instances, and infrastructure. The following sections describe the three types of access that can be assigned to an invited user.

### Services

You can assign access by creating an initial Cloud IAM access policy when you invite a new user. In this section, you can provide a user access to services in a resource group with access to the resource group or to an individual resource in the account. After the user accepts the invitation, you can assign additional access. See [Managing IAM access](/docs/iam/mngiam.html#iammanidaccser) for details on editing policies to add extra roles, assigning more access, or removing a policy for a user.

**Note**: Depending on which service you select when assigning the policy, you might not see all of fields that are described in the following procedures.

#### Resource group access

You can assign access to all services within a resource group or a single service type in a resource group.

1. From the **Invite users** screen, expand the **Services** section.
2. Select to assign access to resources in a **Resource group**.
3. Choose a resource group.
4. Choose a role for the **Assign access to a resource group** field to enable the user to view the resource group on the dashboard, edit the resource group name, or manage user access to the group. You can select **No access**, if you want the user to have access only to the resource that you specify and not the group that it is organized in.
5. Select a service within the resource group, or select to provide access to all services within the selected group. 
6. Select any combination of roles to assign the wanted access. This access applies only to the resources that you selected for the policy. It does not give access to the actual container that is the resource group.


#### Resource access

You can assign access to a single resource within your account down to the instance.

1. From the **Invite users** screen, expand the **Services** section.
2. Select to assign access to a **Resource**.
3. Select a service.
4. Select **All current regions** or a specific region, if your are prompted. 
5. Select **All current service instances** or select a specific service instance.
6. Depending on the service that you selected, you might see the following fields. If you do not enter values for these fields, the policy is assigned at the service instance level instead of the bucket level. 
    * **Resource type**: Enter **bucket**.
    * **Resource ID**: Enter the name of your bucket.
7. Select any combination of roles to assign the wanted access.

For more specific information about the roles when assigning access, see [IAM access](/docs/iam/users_roles.html#iamusermanrol).

### Cloud Foundry access

When you invite new users, you can choose to add the user to an organization in the account. If you add the user to an organization, you can assign the user an organization role. Then, you choose to give the invited user access to any or all of the spaces in the selected organization with an assigned space role.

1. From the **Invite users** screen, expand the **Cloud Foundry access** section.
2. Select an organization to add the user to.
3. Select an organization role to define the level of access for the selected organization.
4. Optional: Select **Add organization role** to specify an extra role.
5. Select **All current regions** or a specific region.
6. Select **All current spaces** or a specific space.
7. Select a space role to define the level of access for the selected spaces.
8. Optional: Select **Add space role** to specify an extra role.

See [Cloud Foundry roles](/docs/iam/cfaccess.html#cfroles) for more information about the roles.

You can add a Cloud Foundry role by using the [ibmcloud account user-invite](/docs/cli/reference/ibmcloud/cli_acct_org_role.html#ibmcloud_account_user_invite) CLI command, but the UI must be used to assign other access or permissions.
{: tip}

### {{site.data.keyword.BluSoftlayer_notm}} infrastructure access

The permissions assigned are automatically limited to the subset of permissions that you have. For more information about the permissions sets, see [Infrastructure permissions](/docs/iam/infrastructureaccess.html#infrapermission).

1. From the **Invite users** screen, expand the **Infrastructure access** section.
2. Select a permission set to define the scope of access.

Access to devices is granted separately after the user is added by navigating to the **Infrastructure** option in the console.
{: tip}

For information about configuring access for users after they have been added to your account, see [Managing infrastructure access](/docs/iam/mnginfra.html#managing-infrastructure-access).

## Adding VPN-only users

As the account owner of a linked account, you can add a VPN-only user.

1. Click the Menu icon ![Menu icon](../icons/icon_hamburger.svg), and then select **Infrastructure**.
2. Go to **Account** &gt; **Users**.
3. Click **Add VPN Only User**.
4. Enter the personal information details for the user. 
5. Click **Add User**.
6. Set portal permissions for the user.
7. Click **Add Portal Permissions** to save the permissions.
8. Set device access for the user.
9. Click **Update Device Access** to save and assign the access.
