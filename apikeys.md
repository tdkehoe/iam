---

copyright:

  years: 2015, 2017
lastupdated: "2017-07-27"

---

{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:screen: .screen}
{:new_window: target="_blank"}

# Managing API keys
{: #manapikey}

An application programming interface key (API key) is a code that is passed in by computer programs that call an application programming interface (API) to identify the calling program, its developer, or its user to the website. API keys are used to track and control how the API is being used, for example to prevent malicious use or abuse of the API (as defined perhaps by terms of service). The API key often acts as both a unique identifier and a secret token for authentication, and generally has a set of access rights specific to the user associated with it. API keys can be based on the universally unique identifier (UUID) system to ensure they are unique to each user.

A federated or non-federated user can create an API key to use on the CLI or as part of automation to log in as your user name. You can use the {{site.data.keyword.Bluemix_notm}} UI or the {{site.data.keyword.Bluemix_notm}} CLI to manage your API keys by listing your keys, creating keys, updating keys, or deleting keys. To manage your {{site.data.keyword.Bluemix_notm}} API keys in the UI, go to **Manage** &gt; **Security** &gt; **Bluemix API keys** to see a list of your API Keys with descriptions and dates. Then, you can create, edit or delete API keys from this page. And, for a full list of available CLI commands, see [`bluemix iam api-keys`](/docs/cli/reference/bluemix_cli/bx_cli.html#bluemix_iam).

As a [federated user](/docs/admin/adminpublic.html#federatedid), you can use an API key to login by using the `BLUEMIX_API_KEY` environment variable. For more information about using an API key for logging in, see the documentation for the [{{site.data.keyword.Bluemix_notm}} CLI `bluemix login` command](/docs/cli/reference/bluemix_cli/bx_cli.html#bluemix_login) and the [cf CLI `cf login` command](/docs/cli/reference/cfcommands/index.html#cf_login).

## Creating an API key

As a {{site.data.keyword.Bluemix_notm}} user you might want to use an API key when you enable a program or script without distributing your password to the script. A benefit of using an API key can be that a user or organization can create several API Keys for different programs and the API keys can be deleted independently if compromised without interfering with other API keys or even the user.

To create an API key in the UI:

1. Go to **Manage** &gt; **Security** &gt; **Bluemix API keys**.
2. Click **Create API key**.
3. Enter a name and description for your API key.
4. Click **Create API key**.
5. Then, click **Show** to display the API key to copy and save it for later, or click **Download API key**.

**Note**: The API key is only available to show or download at the time of creation. If the API key is lost, you must create a new API key.

To create an API key by using the CLI:

1. Enter `bluemix iam api-key-create NAME [-d DESCRIPTION] [-f, --file FILE]` in your command prompt, and specify a name, description, and file for saving your key. For example:

```
bluemix iam api-key-create MyKey -d "this is my API key" -f key_file
``` 

After an API key is created by using the CLI, there are a few ways that you can use the key with the bx CLI:

* Enter it with the `bx login` command
```
 bx login —apikey <your api key>
```
* Create an API key file to use with the `bx login` command: 
 ```
 bx login —apkey @apikeyfile
 ```
 The `apikeyfile` is created by using the `—file` option on the `bx iam api-key-create` command.
* In your command prompt, you can set the environment variable by entering `BLUEMIX_API_KEY=<your api key>` and then entering `bx login`.
* Or, if you want to avoid the bx CLI and just log in to the cf CLI by using your API key, enter:
 ```
 cf login -u apikey -p <yourapikey>
 ```
  In this option, you use the user name of `apikey` and the password is your `apikey`. Now, you can use `apikey` in other tools like Eclipse or other places looking for `cf login` that accepts only user name and password.

## Editing an API key

If you want to change the name or the description of an API key, complete the following steps in the UI or CLI.

To edit an API key:

1. Go to **Manage** &gt; **Security** &gt; **Bluemix API keys**.
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

1. Go to **Manage** &gt; **Security** &gt; **Bluemix API keys**.
2. From the **Actions** menu of an API key that is listed in the table, click to **Delete**.
3. Then, confirm the deletion by clicking **Delete key**.

To delete an API key by using the CLI:
1. Enter `bluemix iam api-key-delete NAME` in your command prompt, specifying the name of your key that should be deleted.
