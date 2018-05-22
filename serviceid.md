---

copyright:

  years: 2017, 2018
  
lastupdated: "2018-05-22"

---

{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:screen: .screen}
{:new_window: target="_blank"}
{:tip: .tip}

# Creating and working with service IDs
{: #serviceids}

A service ID identifies a service or application similar to how a user ID identifies a user. A service ID that you create can be used to enable an application outside of {{site.data.keyword.Bluemix_notm}} access to your {{site.data.keyword.Bluemix_notm}} services. You can assign specific access policies to the service ID that restrict permissions for using specific services, or even combine permissions for accessing different services. Since service IDs are not tied to a specific user, if a user happens to leave an organization and is deleted from the account, the service ID remains ensuring that your application or service stays up and running.

When you create a service ID, you create a unique name and description that is easy for you to identify and work with in the UI. Once you have created your service ID, you can create API keys specific to each service ID that your application can use to authenticate with your {{site.data.keyword.Bluemix_notm}} services. To ensure that your application has the appropriate access for authenticating with your {{site.data.keyword.Bluemix_notm}} services, you use access policies assigned to each service ID that you create. 

The access policies that are associated with a service ID enable specific actions that can be taken when that service ID is used to access a specific service. A single service ID can be assigned multiple policies that define the level of access that is allowed when accessing multiple Identity and access-enabled services. For example, you have two services with two service instances each. For example, you might assign the `Viewer` role for all available instances of one service and assign the `Editor` role for only one instance of a second service. This way, you can customize access to multiple services, but use a single API key for authentication to all.


## Creating a service ID

To create a service ID, go to **Manage** &gt; **Security** &gt; **Identity and Access** and then select **Service IDs**. Follow the process to create a name and description for your service ID. Then, use the **Actions** menu to manage your service ID. You can start by assigning a policy and creating API keys. For more information about working with API keys, see [Managing service ID API keys](/docs/iam/serviceid_keys.html#serviceidapikeys). 

## Updating a service ID

You can update a service ID by changing the name and description at any time. You can also delete and create new API keys as needed or update the assigned access policies. However, any changes you make to an existing service ID, such as changing the assigned policies or deleting an API key that is currently being used, might cause service interruptions to applications that use that service ID.

## Locking a service ID

To avoid a situation where your service ID is deleted causing an outage or disruption for the users of your service, you can lock your service ID. Locking a service ID also prevents any policies from being changed, deleted, or assigned. In addition to the ability to lock a service ID, you can [lock individual API keys](/docs/iam/serviceid_keys.html#lockkey) that are associated with each service ID in your account. 

Locked service IDs cannot be deleted and the access policies can't be updated. However, locked service IDs can still be removed from any access group that they are added to. This means that any access that is assigned to the ID by its membership in an access group is removed when the service ID is removed from the access group.
{: tip}

### Providing user access for locking service IDs

In order for a user to have access to lock and unlock service IDs and API keys that are associated with service IDs, they must be assigned a specific access policy. Two types of access policies can grant the proper access:

* Access to all service IDs in the account
* Access to a specific service ID in the account

To assign access to all service IDs in the account, set an access policy with the following details:

* Editor or Administrator role 
* IAM Identity Service

To assign access to a specific service ID in the account, set an access policy with the following details:

* Editor or Administrator role
* IAM Identity Service
* Specify `serviceid` in the **Resource type** field 
* Specify the service ID identifier in the **Resource ID** field

To get the identifier of a specific service ID, go to **Manage** > **Security** > **Identity & Access**, then select **Service IDs**. Select the service ID that you want to view details for, and copy the ID value.
{: tip}

### Locking a service ID from the UI

A locked service ID is indicated by the ![Locked icon](images/locked.svg "Locked") icon.

1. From the menu bar, click **Manage** &gt; **Security** &gt; **Identity and Access** and then select **Service IDs**.
2. Identify the row of the service ID that you want to lock, and select **Lock service ID** from the **Actions** menu.

To unlock a service ID, select the service ID from the table that you want to unlock and select **Unlock service ID** from the **Actions** menu. You must have the appropriate level of access to unlock a service ID.
{: tip}


## Examples of how to use a service ID

The following are examples of how a Service ID is used with the {{site.data.keyword.objectstorageshort}} and Cloud SQL Query services.

- {{site.data.keyword.objectstorageshort}} - [Getting Started](/docs/services/cloud-object-storage/getting-started-cli.html#getting-started-cli-).
- Cloud SQL Query - [How to use the SQL Query REST API ![External link icon](../icons/launch-glyph.svg)](https://www.youtube.com/embed/s6S4AdJItHk?rel=0){: new_window}.

