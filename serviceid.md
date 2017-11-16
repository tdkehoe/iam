---

copyright:

  years: 2017
lastupdated: "2017-11-16"

---

{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:screen: .screen}
{:new_window: target="_blank"}

# Creating and managing service IDs
{: #serviceids}

A service ID identifies a service or application similar to how a user ID identifies a user. A service ID that you create can be used to enable an application outside of {{site.data.keyword.Bluemix_notm}} access to your {{site.data.keyword.Bluemix_notm}} services. You can assign specific access policies to the service ID that restrict permissions for using specific services, or even combine permissions for accessing different services. Since service IDs are not tied to a specific user, if a user happens to leave an organization and is deleted from the account, the service ID remains ensuring that your application or service stays up and running.

When you create a service ID, you create a unique name and description that is easy for you to identify and work with in the UI. Once you have created your service ID, you can create API keys specific to each service ID that your application can use to authenticate with your {{site.data.keyword.Bluemix_notm}} services. To ensure that your application has the appropriate access for authenticating with your {{site.data.keyword.Bluemix_notm}} services, you use service policies assigned to each service ID that you create. 

The access policies associated with a service ID enable specific actions that can be taken when that service ID is used to access a specific service. A single service ID can have multiple policies assigned that define the level of access allowed when accessing multiple Identity and access-enabled services, and even different instances of a single service. For example, you have two services with two service instances each. For example, you might assign the `Viewer` role for all available instances of one service and assign the `Editor` role for only one instance of a second service. This way you can customize access to multiple services, but use a single API key for authentication to all.


## Creating a service ID

To create a service ID, go to **Manage** &gt; **Security** &gt; **Identity and Access** and then select **Service IDs** from the side panel. Follow the process to create a name and description for your service ID. Then, use the **Actions** menu to manage your service ID. You can start by assigning a policy and creating API keys. For more information about working with API keys, see [Managing service ID API keys](/docs/iam/serviceid_keys.html#serviceidapikeys). For details on the CLI commands that are used to manage a service ID, see [Commands for managing API keys and policies](/docs/cli/reference/bluemix_cli/bx_cli.html#bx_commands_iam). 

## Updating a service ID

You can update a service ID by changing the name and description at any time. You can also delete and create new API keys as needed or update the assigned access policies. However, any changes you make to an existing service ID, such as changing the assigned policies or deleting an API key that is currently being used, might cause service interruptions to applications using that service ID.


