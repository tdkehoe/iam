---

copyright:

  years: 2015, 2017

lastupdated: "2017-11-16"

---

{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:screen: .screen}
{:tip: .tip}
{:new_window: target="_blank"}

# IAM access
{: #userroles}

All services that are organized into a resource group in your account are managed by using {{site.data.keyword.Bluemix_notm}} Identity and Access Management (IAM). Account owners are automatically assigned the account administrator role for Cloud IAM. As the account administrator you can assign and manage access for users, create resource groups, provision service instances, and all other tasks that can be delegated by assigning the Cloud IAM roles. You provide access for users and service IDs by creating policies that set a target for the user or service ID to access and a role which defines what type of access is allowed.


## What are Cloud IAM policies and who can assign them?
{: #iamusermanpol}

You can provide access for users and service IDs by creating policies that set a target for the user or service ID to access and a role that defines what type of access is allowed. A policy grants a user or service ID one or multiple roles to a set of resources by using a combination of attributes to define the applicable set of resources. When you assign a policy, you first choose from setting the policy for a resource group or an individual resource. Then, depending on your initial selection, you can select a service within a resource group or a single instance for the selected resource. More configuration options might be available, depending on the service you select. Finally, you can select a role, or roles, to assign. 

You can assign and manage policies if you have the proper role. The following table shows policy management tasks and the role that is required for each.

| Action | Required role |
|----------|---------|
| Create a policy in an account for all services and instances | Account owner or administrator on all services in the account | 
| Create a policy on a service in an account | Account owner or administrator on the service in the account |
| Create a policy on a service instance | Account owner, administrator on the service in the account, administrator on all services in the relevant resource group, or administrator on the service instance |
| Create a policy to manage a resource group | Account owner or administrator to a resource group |
{: caption="Table 1. Users allowed to create access policies" caption-side="top"} 


## Cloud IAM roles
{: #iamusermanrol}

With Cloud IAM, you can manage and define access for users and resources in your account. If the service you use can be managed by using IAM, there are two types of roles that can be assigned: platform management roles and service access roles.

<dl>
<dt>Platform management roles</dt> 
<dd>Platform management roles cover a range of actions, including the ability to create instances, manage service IDs, manage users and permissions, and create resource groups. The most common platform roles are administrator, editor, operator, viewer. </dd>
<dt>Service access roles</dt>
<dd>Service access roles define a user or service’s ability to perform actions on a service instance such as accessing the UI or performing API calls. There are three possible roles: manager, writer, and reader. </dd>
</dl> 

You might not see all of the roles listed as options when you assign policies in the UI because only the roles available for the service that you have selected in the policy are displayed. For specific information on what roles are enabled and what actions each access role allows for each service, refer to the documentation for that service.
{: tip}

By using a combination of these roles in a single access policy, you can provide fine-grained access for users and service IDs by assigning access on any of the following:

* All resources within the account
* All resources within all services that belong to an individual resource group as well as the ability to manage the resource group
* All resources within a single service in a resource group as well as the ability to manage the resource group
* All resources within a single service across the account, regardless of the resource group they are assigned to
* Resources in an individual instance
* A single resource type within an instance, for example, a bucket in a {{site.data.keyword.objectstorageshort}} instance

To enable another user full access to the account for the purposes of managing user access and managing all account resources including the ability to create resource groups, set up a policy that gives the user access to all resources in the account by selecting **All Identity and Access enabled services** with the **Administrator** role assigned. 
{: tip}

### Platform management roles

Platform management roles enable users to be assigned varying levels of permission for performing platform actions within the account. In addition to the descriptions of the roles provided in the console, the following tables provide examples for some of the platform management actions that users assigned each role can do. You can refer to the documentation for each service to understand how the roles apply to users within the context of the service that is being used.

| Platform management role  | Actions a user can perform on services in the account | Actions for service IDs | Actions for access to resource groups | Action on resources within resource groups |
|:-----------------|:--------------|:---------------|:----------------|:-----------------|
| Viewer | View instances, aliases, bindings, and credentials | View IDs and API keys | View resource group | View only specified instances in the resource group |
| Operator |  View instances and manage aliases, bindings, and credentials | Not applicable | Not applicable | Not applicable |
| Editor |  Create, delete, edit, and view instances. Manage aliases, bindings, and credentials | Create and delete IDs and API keys | View and edit name of resource group | Create, delete, edit, suspend, resume, view, and bind only specified instances in the resource group |
| Administrator |  All management actions for services | Create and delete IDs and API keys, assign policies to IDs | View, edit, and manage access for the resource group | All management actions for the specified instances in the resource group |
{: caption="Table 2. Example platform management roles and actions" caption-side="top"}

Some services might map specific actions to the platform management roles that are related to the management of the service rather than to the access of the service. As an example, see the following table detailing the {{site.data.keyword.containershort_notm}} service actions that are mapped to these roles.


| Platform management role | Description of actions | Example actions for {{site.data.keyword.containershort_notm}} |
|:-----------------|:-----------------|:-----------------|
| Viewer | Can view service instances, but can't modify them  | <ul><li>List clusters</li><li>View details for a cluster</li></ul>|
| Editor | Perform all platform actions except for managing the account and assigning access policies |<ul><li>Bind a service to a cluster</li><li>Create a webhook</li></ul> |
| Operator | Perform platform actions required to configure and operate service instances, such as viewing a service's dashboard. | <ul><li>Add or remove worker nodes</li><li>Reboot or reload worker nodes</li><li>Bind a service to a cluster</li></ul> |
| Administrator | Performs all platform actions based on the resource this role is being assigned, including assigning access policies to other users. |<ul><li>Remove a cluster</li><li>Create a cluster</li><li>Update user access policies</li><li>All actions a viewer, editor, and operator can perform</li></ul>|
{: caption="Table 3. Example platform management roles and actions for {{site.data.keyword.containershort_notm}} service" caption-side="top"}


### Service access roles

Service access roles enable users to be assigned different levels of permission for calling the service's API and accessing the UI for the service. The following table provides example actions that can be taken depending on the assigned roles based on using the {{site.data.keyword.objectstorageshort}} service.

**Note**: The actions that can be taken for each assigned role vary based on the service that you selected for the policy.

| Service access role | Description of actions | Example actions for {{site.data.keyword.objectstorageshort}} service |
|:-----------------|:-----------------|:-----------------|
|  Reader | Perform read-only actions within a service such as viewing service-specific resources | List and download objects |
| Writer | Writers have permissions beyond the reader role, including creating and editing service-specific resources. | Create and destroy buckets and objects |
| Manager | Managers have permissions beyond the writer role to complete privileged actions as defined by the service. In addition, you can create and edit service-specific resources. | Manage all aspects of data storage, create and destroy buckets and objects |
{: caption="Table 4. Example service access user roles and actions" caption-side="top"}


