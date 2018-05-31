---

copyright:

  years: 2015, 2018
lastupdated: "2018-05-31"

---

{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:screen: .screen}
{:new_window: target="_blank"}

# Managing service ID API keys
{: #serviceidapikeys}

Service IDs are created to enable access to your {{site.data.keyword.Bluemix_notm}} services by applications hosted both inside and outside of {{site.data.keyword.Bluemix_notm}}. API keys are used by an application to authenticate as a particular service ID and be granted the access associated with that service ID.

Once you create a service ID, you can start creating API keys and assigning service policies. Each policy specifies the level of access that is allowed when the API key is used to authenticate with your services. For more information about creating a service ID and assigning policies, see [Creating and managing service IDs](/docs/iam/serviceid.html#serviceids). For details on the CLI commands that are used to manage service ID API keys, see [Commands for managing API keys and policies](/docs/cli/reference/bluemix_cli/bx_cli.html#bx_commands_iam).

Each API key that is associated with a service ID inherits the policy that has been assigned to the service ID. For example, if you want one application to be able to simply view resources within a service, then you need to use an API key associated with a service ID that has a policy assigned with the `Viewer` role. And, if you want another application to be able to have full access within a service, then you need to use an API key associated with a second service ID that has a policy assigned with the `Administrator` role.

For more information, see [Examples of how to use a service ID](/docs/iam/serviceid.html#examples-of-how-to-use-a-service-id).

## Creating an API key for a service ID

Create an API key to associate with a service ID.

1. Go to **Manage** &gt; **Security** &gt; **Identity and Access** &gt; **Service IDs**.
2. If you don't have a service ID created already, create the service ID.
3. From the **Actions** menu, go to the **Manage service ID** option.
4. Click **Create** in the API keys section.
5. Add a name and description to easily identify the API key.
6. Click **Create**.
7. Save your API key by copying or downloading it to secure location.

**Note**: For security reasons, the API key is only available to be copied or downloaded at the time of creation. If the API key is lost, you must create a new API key.

## Updating an API key for a service ID

You can update an API key by editing the name or description used to identify the key in the UI.

1. Go to **Manage** &gt; **Security** &gt; **Identity and Access** &gt; **Service IDs**.
2. If you don't have a service ID created already, create the service ID.
3. From the **Actions** menu, go to the **Manage service ID** option.
4. From the **Actions** menu in the API keys section, go to the **Edit name & description** option.

## Locking a service ID's API key
{: #lockkey}

For API keys that represent the identity of the service ID, you can prevent policies from being changed and the API key from being deleted by locking it. A locked API key is indicated by the ![Locked icon](images/locked.svg "Locked") icon in the UI.

1. From the menu bar, click **Manage** &gt; **Security** &gt; **Identity and Access**, and then select **Service IDs**.
2. Identify the row of the service ID that you want to select an API key for, and select the name of the service ID.
3. Select **API keys**.
4. Hover on the row of the API key that you want to lock, and click the **Actions** menu to open a list of options.
5. Click **Lock API key**.

You can unlock your API key at any time to update, delete, or add an access policy, or to remove the API key.
{: tip}

### Locking or unlocking a service ID API key with the CLI

To lock a service ID API key, use the following command:

```
ibmcloud iam service-api-key-lock (APIKEY_NAME|APIKEY_UUID) (SERVICE_ID_NAME|SERVICE_ID_UUID) [-f, --force]
```

<strong>Prerequisites</strong>: Endpoint, Login, Target

<strong>Command Options</strong>:
<dl>
  <dt>APIKEY_NAME (required)</dt>
  <dd>Name of the API key, exclusive with APIKEY_UUID</dd>
  <dt>APIKEY_UUID (required)</dt>
  <dd>UUID of the API key, exclusive with APIKEY_NAME</dd>
  <dt>SERVICE_ID_NAME (required)</dt>
  <dd>Name of the service ID, exclusive with SERVICE_ID_UUID</dd>
  <dt>SERVICE_ID_UUID (required)</dt>
  <dd>UUID of the service ID, exclusive with SERVICE_ID_NAME</dd>
  <dt>-f, --force</dt>
  <dd>Lock without confirmation</dd>
</dl>

<strong>Examples</strong>:

Lock service API key `sample-key` of service ID `sample-service`:

```
ibmcloud iam service-api-key-lock sample-key sample-service
```

To unlock a service ID API key, use the following command:

```
ibmcloud iam service-api-key-unlock (APIKEY_NAME|APIKEY_UUID) (SERVICE_ID_NAME|SERVICE_ID_UUID) [-f, --force]
```


## Deleting an API key for a service ID

You can delete an API key that is associated with a service ID. However, deleting an API key that is currently in use by an application will remove the ability for that application to authenticate with your services.

1. Go to **Manage** &gt; **Security** &gt; **Identity and Access** &gt; **Service IDs**.
2. If you don't have a service ID created already, create the service ID.
3. From the **Actions** menu, go to the **Manage service ID** option.
4. From the **Actions** menu in the API keys section, go to the **Delete key** option.
