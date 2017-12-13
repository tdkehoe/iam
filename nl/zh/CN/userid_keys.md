---

copyright:

  years: 2015, 2017
lastupdated: "2017-11-16"

---

{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:screen: .screen}
{:new_window: target="_blank"}

# 管理用户 API 密钥
{: #userapikey}

联合或非联合用户可以创建要在 CLI 上使用的 API 密钥，或者作为自动化的一部分创建 API 密钥，以便以您的用户身份登录。您可以使用 UI 或 CLI 通过列出密钥、创建密钥、更新密钥或删除密钥来管理 API 密钥。要管理与您的用户身份关联的 {{site.data.keyword.Bluemix_notm}} API 密钥，请转至**管理** &gt; **安全性** &gt; **平台 API 密钥**来查看 API 密钥及其描述和日期的列表。然后，可以在此页面中创建、编辑或删除 API 密钥。要获取可用 CLI 命令的完整列表，请参阅[用于管理 API 密钥和策略的命令](/docs/cli/reference/bluemix_cli/bx_cli.html#bx_commands_iam)。

作为[联合用户](/docs/admin/adminpublic.html#federatedid)，您可以使用 API 密钥，通过 `BLUEMIX_API_KEY` 环境变量来登录。有关使用 API 密钥进行登录的更多信息，请参阅[使用联合标识登录](/docs/iam/login_fedid.html)。

## 创建 API 密钥

作为 {{site.data.keyword.Bluemix_notm}} 用户，您可能希望在启用程序或脚本时使用 API 密钥，而不将密码分发到脚本。使用 API 密钥的优点是用户或组织可以针对不同的程序创建多个 API 密钥，并且如果 API 密钥泄露，可以将其单独删除，而不影响其他 API 密钥，甚至不会影响到用户。

要在 UI 中为您的用户身份创建 API 密钥，请执行以下操作：

1. 转至**管理** &gt; **安全性** &gt; **平台 API 密钥**。
2. 单击**创建 API 密钥**。
3. 为 API 密钥输入名称和描述。
4. 单击**创建 API 密钥**。
5. 然后，单击**显示**以显示 API 密钥，以便复制并保存供日后使用，或者单击**下载 API 密钥**。

**注**：出于安全原因，API 密钥仅在创建时才可复制或下载。如果 API 密钥丢失，必须创建新的 API 密钥。

要使用 CLI 创建 API 密钥，请执行以下操作：

1. 在命令提示符处输入 `bluemix iam api-key-create NAME [-d DESCRIPTION] [-f, --file FILE]`，并指定名称、描述和用于保存密钥的文件。例如：

```
bluemix iam api-key-create MyKey -d "this is my API key" -f key_file
``` 


## 更新 API 密钥

如果要更改 API 密钥的名称或描述，请在 UI 或 CLI 中完成以下步骤。

要编辑 API 密钥，请执行以下操作：

1. 转至**管理** &gt; **安全性** &gt; **平台 API 密钥**。
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

1. 转至**管理** &gt; **安全性** &gt; **平台 API 密钥**。
2. 在表中列出的 API 密钥的**操作**菜单中，单击**删除**。
3. 然后，通过单击**删除密钥**来确认删除操作。

要使用 CLI 删除 API 密钥，请执行以下操作：
1. 在命令提示符处输入 `bluemix iam api-key-delete NAME`，并指定应该删除的密钥的名称。
