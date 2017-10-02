---

copyright:

  years: 2015, 2017
lastupdated: "2017-09-29"

---

{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:screen: .screen}
{:new_window: target="_blank"}

# Inviting users and assigning access
{: #iamuserinv}

You can invite users across {{site.data.keyword.Bluemix_notm}} services, applications, and {{site.data.keyword.Bluemix_notm}} infrastructure from a single location. To invite users and manage outstanding invitations, you must be either an account owner, an organization manager, or you must have infrastructure permissions to add users. You can invite users, cancel invitations, and resend a pending invitation to an invited user. You can invite a single user or, if you are providing the same access for all members in a group of users, you can invite multiple users at once.  
{:shortdesc}

## Inviting users

To invite users or manage user invitations in your account, complete the following steps: 

1. From the menu bar, click **Manage** &gt; **Security** &gt; **Identity & Access** &gt; **Users**. The Users window displays a list of users with their email addresses and current status in the currently selected account.
2. Click **Invite users**.
3. Specify the email address or IBMid of the user. If you are providing multiple users the same access, enter multiple email addresses or IBMids by separating the user ID entries with commas, spaces, or line breaks.
4. Add one or more of the access options that you manage. You must assign at least one access option and configure the settings for the user in each access option that you assign. For any additional access options that you don't add and configure, the default value of *no access* is assigned. You might see one or all of the following access options, depending on the options that you are authorized to manage: **Identity and access enabled services**, **Cloud Foundry access**, **Infrastructure access**. See [Assigning user access](/docs/iam/iamuserinv.html#assignaccess) for more information.

If you determine that a user does not need access, you can cancel an invitation for any users that are shown in a **Processing** or **Pending** state in the **Status** column. If an invited user did not receive an invitation, you can resend the invitation to any user in a **Pending** state.

If you want to invite users using the CLI, see the [bluemix iam account-user-invite](/docs/cli/reference/bluemix_cli/bx_cli.html#bluemix_iam_account_user_invite) command.

## Assigning user access
{: #assignaccess}

You assign access for users as you invite them, assigning Cloud Foundry roles, policies, and infrastructure permissions. Depending on the access options that you are authorized to manage, you can invite and provide access for users across the account, organization, space, and service instances. The following sections describe the three types of access that can be assigned to an invited user.

### Identity and access enabled services

You can assign a single service policy when you invite a new user. Once the user has accepted the invitation, you can add additional service policies. See [Identity and access-enabled service access policies](/docs/iam/iamusermanage.html#iammanidaccser) for details on editing policies to add additional roles, adding additional service policies, or removing a policy for a user.

**Note**: Depending on which service you select when assigning the policy, you might not see all of fields described in the following procedure.

1. From the **Invite users** screen, expand the **Identity and Access enabled services** section.
2. Select a service.
3. Select **All current regions** or a specific region, if your are prompted. 
**Note**: Not all services require a region selection.
4. Select **All current service instances** or select a specific service instance.
5. Select a role to define the scope of access for the policy.
6. Optional: Select **Add role** to specify an additional role for the policy.

See [Identity and access management policies and roles](/docs/iam/users_roles.html#iamusermanpol) for more specific information about the roles when setting service policies.

### Cloud Foundry access

When you invite new users, you can choose to add the user to an organization in the account. If you add the user to an organization, you can assign the user an organization role. Then, you choose to give the invited user access to any or all of the spaces in the selected organization with an assigned space role.

1. From the **Invite users** screen, expand the **Cloud Foundry access** section.
2. Select an organization to add the user to.
3. Select an organization role to define the level of access to the selected organization.
4. Optional: Select **Add role** to specify an additional role.
5. Select **All current regions** or a specific region.
6. Select **All current spaces** or a specific space.
7. Select a space role to define the level of access to the selected spaces.
8. Optional: Select **Add role** to specify an additional role.

See [Cloud Foundry roles](/docs/iam/users_roles.html#cfroles) for more specific information about these roles.

**Note**: You can add a Cloud Foundry role using the [bluemix iam account-user-invite](/docs/cli/reference/bluemix_cli/bx_cli.html#bluemix_iam_account_user_invite) CLI command, but the UI must be used to assign other access or permissions.

### Infrastructure access

The actual permissions assigned are automatically limited to the subset of permissions that you have. For more information about the permissions and what actions the user can perform with each, see [Infrastructure permissions](/docs/iam/users_roles.html#infrapermissions).

1. From the **Invite users** screen, expand the **Infrastructure access** section.
2. Select a permission to define the scope of access.

For information about configuring access for users after they have been added to your account, see [Managing users and access](/docs/iam/iamusermanage.html).
