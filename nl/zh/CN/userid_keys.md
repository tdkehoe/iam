---

copyright:

  years: 2015, 2018
lastupdated: "2018-06-06"

---

{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:screen: .screen}
{:new_window: target="_blank"}

# 管理用户 API 密钥
{: #userapikey}

联合或非联合用户可以创建要在 CLI 上使用的 API 密钥，或者作为自动化的一部分创建 API 密钥，以便以您的用户身份登录。您可以使用 UI 或 CLI 通过列出密钥、创建密钥、更新密钥或删除密钥来管理 API 密钥。要管理与您的用户身份关联的 {{site.data.keyword.Bluemix_notm}} API 密钥，请转至**管理** &gt; **安全性** &gt; **平台 API 密钥**来查看 API 密钥及其描述和日期的列表。然后，可以创建、编辑或删除 API 密钥。此外，要获取可用 CLI 命令的完整列表，请参阅 [`ibmcloud iam api-keys`](/docs/cli/reference/ibmcloud/cli_api_policy.html#ibmcloud_iam_api_keys)。

作为[联合用户](/docs/account/adminpublic.html#federatedid)，您可以使用 API 密钥，通过 `BLUEMIX_API_KEY` 环境变量来登录。有关使用 API 密钥进行登录的更多信息，请参阅[使用联合标识登录](/docs/cli/login_federated_id.html#federated_id)。

## 创建 API 密钥

作为 {{site.data.keyword.Bluemix_notm}} 用户，您可能希望在启用程序或脚本时使用 API 密钥，而不将密码分发到脚本。使用 API 密钥的优点是用户或组织可以针对不同的程序创建多个 API 密钥，并且如果 API 密钥泄露，可以将其单独删除，而不影响其他 API 密钥，甚至不会影响到用户。您最多可以创建 20 个 API 密钥。

要在 UI 中为您的用户身份创建 API 密钥，请完成以下步骤：

1. 转至**管理** &gt; **安全性** &gt; **平台 API 密钥**。
2. 单击**创建 API 密钥**。
3. 为 API 密钥输入名称和描述。
4. 单击**创建 API 密钥**。
5. 然后，单击**显示**以显示 API 密钥，以便复制并保存供日后使用，或者单击**下载 API 密钥**。

**注**：出于安全原因，API 密钥仅在创建时才可复制或下载。如果 API 密钥丢失，必须创建新的 API 密钥。

要使用 CLI 创建 API 密钥，请使用以下命令：

1. 在命令提示符处输入 `ibmcloud iam api-key-create NAME [-d DESCRIPTION] [-f, --file FILE]`，并指定名称、描述和用于保存密钥的文件。请参阅以下示例：

```
ibmcloud iam api-key-create MyKey -d "this is my API key" --file key_file
``` 


## 更新 API 密钥

如果要更改 API 密钥的名称或描述，请在 UI 或 CLI 中完成以下步骤。

要编辑 API 密钥，请完成以下步骤：

1. 转至**管理** &gt; **安全性** &gt; **平台 API 密钥**。
2. 在表中列出的 API 密钥的**操作**菜单中，单击**编辑名称和描述**。 
3. 更新 API 密钥的信息。
4. 单击**更新 API 密钥**。

要使用 CLI 编辑 API 密钥，请输入以下命令：

1. 在命令提示符处输入 `ibmcloud iam api-key-update NAME [-n NAME] [-d DESCRIPTION]`，并指定密钥的旧名称、新名称和新描述。例如：

```
ibmcloud iam api-key-update MyCurrentName -n MyNewName -d "the new description of my key"
```

## 锁定 API 密钥

对于表示您用户身份的平台 API 密钥，可以通过锁定 API 密钥来防止将其删除。锁定的 API 密钥由 ![“已锁定”图标](images/locked.svg "已锁定") 图标指示。可以使用 UI 或 CLI 来锁定和解锁 API 密钥。

### 在 UI 中锁定和解锁 API 密钥

1. 在菜单栏中，单击**管理** &gt; **安全性** &gt; **身份和访问权**，然后选择**平台 API 密钥**。
2. 确定要锁定的 API 密钥所在的行，然后从**操作**菜单中选择**锁定 API 密钥**。

您可以随时解锁 API 密钥以更新、删除或添加访问策略，也可以从帐户中除去 API 密钥。选择表中要解锁的 API 密钥，然后从**操作**菜单中选择**解锁 API 密钥**。
{: tip}

### 使用 CLI 锁定和解锁 API 密钥

要锁定平台 API 密钥，请使用以下命令：

```
ibmcloud iam api-key-lock (NAME|UUID) [-f, --force]
```

<strong>先决条件</strong>：端点和登录

<strong>命令选项</strong>：
<dl>
<dt>NAME（必需）</dt>
<dd>要锁定的 API 密钥的名称，与 UUID 互斥。</dd>
<dt>UUID（必填）</dt>
<dd>要锁定的 API 密钥的 UUID，与 NAME 互斥。</dd>
<dt>-f, --force</dt>
<dd>强制锁定而不确认。</dd>
</dl>

<strong>示例</strong>：

锁定 API 密钥 `test-api-key`

```
ibmcloud iam api-key-lock test-api-key
```

要解锁平台 API 密钥，请运行以下命令：

```
ibmcloud iam api-key-unlock (NAME|UUID) [-f, --force]
```

<strong>先决条件</strong>：端点和登录

<strong>命令选项</strong>：
<dl>
<dt>NAME（必需）</dt>
<dd>要解锁的 API 密钥的名称，与 UUID 互斥。</dd>
<dt>UUID（必填）</dt>
<dd>要解锁的 API 密钥的 UUID，与 NAME 互斥。</dd>
<dt>-f, --force</dt>
<dd>强制解锁而不确认。</dd>
</dl>

<strong>示例</strong>：

解锁 API 密钥 `test-api-key`

```
ibmcloud iam api-key-unlock test-api-key
```


## 删除 API 密钥

如果使用的是密钥轮替策略，那么您可能会希望删除较旧的密钥，而将其替换为新密钥。

要删除 API 密钥，请完成以下步骤： 

1. 转至**管理** &gt; **安全性** &gt; **平台 API 密钥**。
2. 在表中列出的 API 密钥的**操作**菜单中，单击**删除**。
3. 然后，通过单击**删除密钥**来确认删除操作。

要使用 CLI 删除 API 密钥，请执行以下操作：
1. 在命令提示符处输入 `ibmcloud iam api-key-delete NAME`，并指定要删除的密钥的名称。
