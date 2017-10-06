---

copyright:

  years: 2015, 2016

lastupdated: "2017-10-06"

---

{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:screen: .screen}
{:new_window: target="_blank"}

# User roles and permissions
{: #userroles}

You can manage users across the {{site.data.keyword.Bluemix_notm}} platform and Infrastructure services from the **Users** page for your account. To access the Users page, from the {{site.data.keyword.Bluemix_notm}} menu, click **Manage** &gt; **Account** &gt; **Users**. Account owners can perform all operations for managing users, permissions, organizations, and spaces. Cloud Foundry organization managers and space managers also have access to manage permissions for users added to each organization and space that they manage.
{:shortdesc}

If you are a user added to another person's account, and you want to view your assigned roles and permissions, go to **Manage** &gt; **Security** &gt; **Identity & Access** &gt; **Users**, and click on your name.

## Account roles
{: #userrolesinfo}

At the account level, there are two roles that enable access to different account management features:

| Account role | Permissions |
|----------------|---------|
|Owner | An owner for the account has access to their profile, users, billing information, spending notifications, and usage dashboard. From the Users page, the owner can invite new users and adjust roles. The owner can also add promotional credits, set or change the billing limit, set service access, and manage organizations and spaces. |
|Member | A member has access to their profile, the Users page displaying the active users in the account, and account credits and billing limits in the {{site.data.keyword.Bluemix_notm}} header.  |
{:caption="Table 1. Account roles and permissions" caption-side="top"}

All new users are added as a member of the account. You can assign organization and space roles to invitees to enable specific views and permissions in {{site.data.keyword.Bluemix_notm}}. Once your invitees accept the invitation and join {{site.data.keyword.Bluemix_notm}}, you can edit their roles on the Users page.

## Cloud Foundry roles
{: #cfroles}

Cloud Foundry roles include the access permissions for organizations and spaces defined within the account. Cloud Foundry roles do not enable user permissions for completing actions within the context of a service. The following roles can be assigned at the organization level:

| Organization role | Permissions |
|-------------------|-------------|
|Manager | Organization managers can create, view, edit, or delete spaces within the organization, view the organization's usage and quota, invite users to the organization, manage who has access to the organization and their roles in the organization, and manage custom domains for the organization. |
|Billing manager | Billing managers can view runtime and service usage information for the organization on the Usage Dashboard page.  |
|Auditor | Organization auditors can view application and service content in the organization. Auditors can also view the users in the organization and their assigned roles, and the quota for the organization. |
{:caption="Table 2. Organization roles and permissions" caption-side="top"}

The following roles can be assigned at the space level:

| Space role | Permissions |
|------------|-------------|
|Manager | Space managers can add existing users and manage roles within the space. The space manager can also view the number of instances, service bindings, and resource use for each application in the space. |
|Developer | Space developers can create, delete, and manage applications and services within the space. Some of the managing tasks include deploying apps, starting or stopping apps, renaming an app, deleting an app, renaming a space, binding or unbinding a service to an application, view the number or instances, service bindings, and resource use for each application in the space. In addition, the space developer can associate an internal or external URL with an application in the space.   |
|Auditor | Space auditors have read-only access to all information about the space, such as information about the number of instances, service bindings, and resource use for each application in the space. |
{:caption="Table 3. Space roles and permissions" caption-side="top"}

**Note**: Users that are assigned the manager or developer space role can access the VCAP_SERVICES environment variable. However, a user that is assigned the auditor role can't access VCAP_SERVICES.

## Identity and access management policies and roles
{: #iamusermanpol}

Account owners are automatically assigned the account administrator role for Identity and access management (IAM) which enables you to assign and manage service policies. Service policies can be assigned to individual users or to service IDs, and the assigned policy can define access for an entire service or at the individual instance level.

### Service policies

A policy assigns a user or service ID one or multiple roles to a set of resources by using a combination of attributes to define the applicable set of resources. When you assign a policy, you first specify the service. Then, you can select a role, or roles, to assign. Additional configuration options might be available, depending on the service you select.

You can assign and manage policies if you have the proper role. The following table shows policy management tasks and the role required for each.

| Action | Required role |
|----------|---------|
| Create policies on an account for all services and instances | Account administrator |
| Create a policy on a service in an account | Account administrator or administrator on the service in the account |
| Create a service instance | Account administrator or the administrator or editor on the service in the account |
| Create a policy on a service instance | Account administrator or administrator on the service in the account or administrator on the service instance |
{: caption="Table 4. Administrative tasks for managing IAM-enabled services policies" caption-side="top"}

### Service policy roles
{: #iamusermanrol}

IAM allows you to manage and define access for users and resources in your account. If the service you use can be managed using IAM for user access control, then there are two types of roles that allow different actions within your account: platform management and service access roles.

<dl>
<dt>Platform management roles</dt>
<dd>Roles available for all services that can be managed using IAM for user access control, which include administrator, editor, operator, viewer, and billing administrator. These roles are mapped to user actions that can be performed on {{site.data.keyword.Bluemix_notm}} resources at the platform level. For example, some of these actions are the ability to create instances, connect instances to an application, manage service IDs, manage users and permissions, and manage billing and quotas for the account. </dd>
<dt>Service access roles</dt>
<dd>These roles are service-specific. The manager, writer, and reader roles define the user’s ability to use the service and perform service APIs calls. Because each service defines the actions a user with a given role can perform, it is possible that a service might not use all of the available roles described in this documentation. </dd>
</dl>

**Note**: You might not see all of the roles listed as options when assigning policies in the UI because only the roles applicable to the service that you have selected in the policy are displayed. For specific information on what roles are enabled and what actions each access role allows for each service, refer to the documentation for that service.


#### Platform management roles

Platform management roles enable users to be assigned varying levels of permission for performing platform actions. In addition to the descriptions of the roles provided in the console, the following tables provide examples for some of the platform management actions that users assigned each role might be able to do.

| Platform management role  | Actions a user can perform on services in the account | Actions for service IDs |
|:-----------------|:--------------|:---------------|
| Viewer | View instances | View IDs and API keys |
| Operator |  View and bind service instances | Not applicable |
| Editor |  Create, delete, edit, suspend, resume, view, bind service instances | Delete IDs and create and delete API keys |
| Administrator |  All management actions for services | Create and delete IDs and API keys, assign policies to IDs |
{: caption="Table 5. Example platform management roles and actions" caption-side="top"}

Some services might map specific actions to the platform management roles that are related to the management of the service rather than to the access of the service. As an example, see the following table detailing the {{site.data.keyword.containershort_notm}} service actions that are mapped to these roles.


| Platform management role | Description of actions | Example actions for {{site.data.keyword.containershort_notm}} service |
|:-----------------|:-----------------|:-----------------|
| Viewer | Can view service instances, but can't modify them  | <ul><li>List clusters</li><li>View details for a cluster</li></ul>|
| Editor | Perform all platform actions except for managing the account and assigning access policies |<ul><li>Bind a service to a cluster</li><li>Create a webhook</li></ul> |
| Operator | Perform platform actions required to configure and operate service instances, such as viewing a service's dashboard. | <ul><li>Add or remove worker nodes</li><li>Reboot or reload worker nodes</li><li>Bind a service to a cluster</li></ul> |
| Administrator | Performs all platform actions based on the resource this role is being assigned, including assigning access policies to other users. |<ul><li>Remove a cluster</li><li>Create a cluster</li><li>Update user access policies</li><li>All actions a viewer, editor, and operator can perform</li></ul>|
{: caption="Table 6. Example platform management roles and actions" caption-side="top"}


#### Service access roles

Service access roles enable users to be assigned different levels of permission for calling the service's API. The following table provides example actions that can be taken depending on the assigned service access roles based on using the {{site.data.keyword.objectstorageshort}} service.

**Note**: The actions that can be taken for each assigned role vary based on the service that you selected for the policy.

| Service access role | Description of actions | Example actions for {{site.data.keyword.objectstorageshort}} service |
|:-----------------|:-----------------|:-----------------|
|  Reader | Perform read-only actions within a service such as viewing service-specific resources | List and download objects |
| Writer | Writers have permissions beyond the reader role, including creating and editing service-specific resources. | Create and destroy buckets and objects |
| Manager | Managers have permissions beyond the writer role to complete privileged actions as defined by the service. In addition, you can create and edit service-specific resources. | Manage all aspects of data storage, create and destroy buckets and objects |
{: caption="Table 7. Example service access user roles and actions" caption-side="top"}


## Infrastructure permissions
{: #infrapermissions}

You can set the following initial permissions when you invite a user:

| Permission set | Description of actions |
|---------------------------|------------------------|
|View Only | Users with this permission can only view items within the system.|
|Basic User | Users with this permission can perform basic actions within the system, such as adding a ticket and managing devices. |
|Super User | Users with this permission can perform all actions available in the system. |
{:caption="Table 8. Infrastructure permissions" caption-side="top"}

Additional permissions can be set after the user has accepted the invite. The initial permission set at invite time does not grant access to devices, so you must grant device access in the Control Portal after the user has accepted the invite.
