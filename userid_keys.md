---

copyright:

  years: 2015, 2017
lastupdated: "2017-12-07"

---

{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:screen: .screen}
{:new_window: target="_blank"}

# Managing user API keys
{: #userapikey}

A federated or non-federated user can create an API key to use on the CLI or as part of automation to log in as your user identity. You can use the UI or the CLI to manage your API keys by listing your keys, creating keys, updating keys, or deleting keys. To manage the {{site.data.keyword.Bluemix_notm}} API keys associated with your user identity, go to **Manage** &gt; **Security** &gt; **Platform API keys** to see a list of your API Keys with descriptions and dates. Then, you can create, edit or delete API keys from this page. For a full list of available CLI commands, see [Commands for managing API keys and policies](/docs/cli/reference/bluemix_cli/bx_cli.html#bx_commands_iam).

As a [federated user](/docs/admin/adminpublic.html#federatedid), you can use an API key to login by using the `BLUEMIX_API_KEY` environment variable. For more information about using an API key for logging in, see [Logging in with a federated ID](/docs/cli/login_federated_id.html#federated_id).

## Creating an API key

As a {{site.data.keyword.Bluemix_notm}} user you might want to use an API key when you enable a program or script without distributing your password to the script. A benefit of using an API key can be that a user or organization can create several API Keys for different programs and the API keys can be deleted independently if compromised without interfering with other API keys or even the user.

To create an API key for your user identity in the UI:

1. Go to **Manage** &gt; **Security** &gt; **Platform API keys**.
2. Click **Create API key**.
3. Enter a name and description for your API key.
4. Click **Create API key**.
5. Then, click **Show** to display the API key to copy and save it for later, or click **Download API key**.

**Note**: For security reasons, the API key is only available to be copied or downloaded at the time of creation. If the API key is lost, you must create a new API key.

To create an API key by using the CLI:

1. Enter `bluemix iam api-key-create NAME [-d DESCRIPTION] [-f, --file FILE]` in your command prompt, and specify a name, description, and file for saving your key. For example:

```
bluemix iam api-key-create MyKey -d "this is my API key" -f key_file
``` 


## Updating an API key

If you want to change the name or the description of an API key, complete the following steps in the UI or CLI.

To edit an API key:

1. Go to **Manage** &gt; **Security** &gt; **Platform API keys**.
2. From the **Actions** menu of an API key that is listed in the table, click **Edit the name & description** 
3. Update the information for your API key.
4. Click **Update API key**.

To edit an API key by using the CLI:

1. Enter `bluemix iam api-key-update NAME [-n NAME] [-d DESCRIPTION]` in your command prompt, specifying the old name, new name, and new description for the key. For example:

```
bluemix iam api-key-update MyCurrentName -n MyNewName -d "the new description of my key"
```

## Deleting an API key

If you are using a key rotation strategy, you might want to delete an older key and replace it with a new key.

To delete an API key: 

1. Go to **Manage** &gt; **Security** &gt; **Platform API keys**.
2. From the **Actions** menu of an API key that is listed in the table, click to **Delete**.
3. Then, confirm the deletion by clicking **Delete key**.

To delete an API key by using the CLI:
1. Enter `bluemix iam api-key-delete NAME` in your command prompt, specifying the name of your key that should be deleted.
