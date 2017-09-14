---

copyright:

  years: 2015, 2017
lastupdated: "2017-08-30"

---

{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:screen: .screen}
{:new_window: target="_blank"}

# 管理 API 密钥
{: #manapikey}

应用程序编程接口密钥（API 密钥）是由调用应用程序编程接口 (API) 的计算机程序传入的代码，用于确定调用程序、其开发者或其 Web 站点用户。API 密钥用于跟踪和控制 API 的使用情况，例如阻止恶意使用或滥用 API（可能如服务方面所定义）。API 密钥经常充当进行认证的唯一标识和密码令牌，而且通常有一组特定于其关联用户的访问权。API 密钥可以基于通用唯一标识 (UUID) 系统来确保它们对每个用户唯一。

联合或非联合用户可以创建要在 CLI 上使用的 API 密钥，或者作为自动化的一部分创建 API 密钥，以便以您的用户名登录。您可以使用 {{site.data.keyword.Bluemix_notm}} UI 或 {{site.data.keyword.Bluemix_notm}} CLI 通过列出密钥、创建密钥、更新密钥或删除密钥来管理 API 密钥。要在 UI 中管理 {{site.data.keyword.Bluemix_notm}} API 密钥，请转至**管理** &gt; **安全性** &gt; **Bluemix API 密钥**来查看 API 密钥及其描述和日期的列表。然后，可以在此页面中创建、编辑或删除 API 密钥。此外，要获取可用 CLI 命令的完整列表，请参阅 [`bluemix iam api-keys`](/docs/cli/reference/bluemix_cli/bx_cli.html#bluemix_iam)。

作为[联合用户](/docs/admin/adminpublic.html#federatedid)，您可以使用 API 密钥，通过 `BLUEMIX_API_KEY` 环境变量来登录。有关使用 API 密钥登录的更多信息，请参阅文档中的 [{{site.data.keyword.Bluemix_notm}} CLI `bluemix login` 命令](/docs/cli/reference/bluemix_cli/bx_cli.html#bluemix_login)和 [cf CLI `cf login` 命令](/docs/cli/reference/cfcommands/index.html#cf_login)。

## 创建 API 密钥

作为 {{site.data.keyword.Bluemix_notm}} 用户，您可能希望在启用程序或脚本时使用 API 密钥，而不将密码分发到脚本。使用 API 密钥的优点是用户或组织可以针对不同的程序创建多个 API 密钥，并且如果 API 密钥泄露，可以将其单独删除，而不影响其他 API 密钥，甚至不会影响到用户。

要在 UI 中创建 API 密钥，请执行以下操作：

1. 转至**管理** &gt; **安全性** &gt; **Bluemix API 密钥**。
2. 单击**创建 API 密钥**。
3. 为 API 密钥输入名称和描述。
4. 单击**创建 API 密钥**。
5. 然后，单击**显示**以显示 API 密钥，以便复制并保存供日后使用，或者单击**下载 API 密钥**。

**注**：API 密钥仅在创建时才可显示或下载。如果 API 密钥丢失，必须创建新的 API 密钥。

要使用 CLI 创建 API 密钥，请执行以下操作：

1. 在命令提示符处输入 `bluemix iam api-key-create NAME [-d DESCRIPTION] [-f, --file FILE]`，并指定名称、描述和用于保存密钥的文件。例如：

```
bluemix iam api-key-create MyKey -d "this is my API key" -f key_file
``` 

使用 CLI 创建 API 密钥后，有多种方式可将密钥用于 bx CLI：

* 使用 `bx login` 命令输入密钥
```
 bx login --apikey <your api key>
```
* 创建 API 密钥文件以用于 `bx login` 命令： 
 ```
 bx login --apkey @apikeyfile
 ```
 `apikeyfile` 会使用 `bx iam api-key-create` 命令上的 `—file` 选项进行创建。
* 要设置环境变量，可以在命令提示符处输入 `BLUEMIX_API_KEY=<your api key>`，然后输入 `bx login`。
* 或者，如果希望避免使用 bx CLI，而仅使用 API 密钥登录到 cf CLI，请输入：
 ```
 cf login -u apikey -p <yourapikey>
 ```
  在此选项中，您使用的用户名是 `apikey`，密码是您的 `apikey`。现在，可以在其他工具（如 Eclipse）或其他位置中使用 `apikey`，以查找仅接受用户名和密码的 `cf login`。
## 编辑 API 密钥

如果要更改 API 密钥的名称或描述，请在 UI 或 CLI 中完成以下步骤。

要编辑 API 密钥，请执行以下操作：

1. 转至**管理** &gt; **安全性** &gt; **Bluemix API 密钥**。
2. 在表中列出的 API 密钥的**操作**菜单中，单击**编辑名称和描述**。 
3. 更新 API 密钥的信息。
4. 单击**更新 API 密钥**。

要使用 CLI 编辑 API 密钥，请执行以下操作：

1. 在命令提示符处输入 `bluemix iam api-key-update NAME [-n NAME] [-d DESCRIPTION]`，并指定密钥的旧名称、新名称和新描述。例如：

```
bluemix iam api-key-update MyCurrentName -n MyNewName -d "the new description of my key"
```

## 删除 API 密钥

如果使用的是密钥轮替策略，那么您可能会希望删除较旧的密钥，而将其替换为新密钥。

要删除 API 密钥，请执行以下操作： 

1. 转至**管理** &gt; **安全性** &gt; **Bluemix API 密钥**。
2. 在表中列出的 API 密钥的**操作**菜单中，单击**删除**。
3. 然后，通过单击**删除密钥**来确认删除操作。

要使用 CLI 删除 API 密钥，请执行以下操作：
1. 在命令提示符处输入 `bluemix iam api-key-delete NAME`，并指定应该删除的密钥的名称。
