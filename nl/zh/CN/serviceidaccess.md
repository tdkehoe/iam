---

copyright:

  years: 2015, 2018
lastupdated: "2018-10-30"

---

{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:screen: .screen}
{:new_window: target="_blank"}

# 管理服务标识访问策略
{: #serviceidpolicy}

创建服务标识时，可以为该服务标识分配服务策略，以控制允许用于向服务进行认证的访问级别。您可以随时通过更改现有策略，删除策略或指定新策略来更新这些已分配的访问策略。

**注**：如果删除或编辑当前正在使用的服务标识的现有策略，那么可能会导致服务中断。

## 分配新访问权

要分配对资源组中所有资源的访问权，或分配仅对资源组中一项服务的访问权，请完成以下步骤：

1. 在菜单栏中，单击**管理** &gt; **安全性** &gt; **身份和访问权** &gt; **服务标识**。
2. 从表中选择要为其分配服务策略的服务标识。
3. 单击**分配访问权**。
4. 选择**按资源组分配**。
5. 选择资源组。
6. 为**分配对资源组的访问权**字段选择角色。此选项支持用户在自己的仪表板上查看资源组，编辑资源组名称或管理用户对资源组的访问权。如果希望用户只能访问您指定的资源，而不是将资源所分配到的组，那么可以选择**无访问权**。
7. 选择资源组中的服务，或选择提供对所选组中所有服务的访问权。
8. 选择任意角色组合来为用户分配所需的访问权。此访问权仅适用于为策略选择的资源。它并不授予对实际容器（即资源组）的访问权。
9. 选择**分配**。

要分配对帐户中单个资源的访问权，请完成以下步骤：

1. 在菜单栏中，单击**管理** &gt; **安全性** &gt; **身份和访问权** &gt; **服务标识**。
2. 从表中选择要为其分配服务策略的服务标识。
3. 单击**分配访问权**。
4. 选择**按资源分配**。
5. 选择服务。
6. 选择**所有当前区域**或特定区域（如果系统提示选择）。
7. 选择**所有当前服务实例**或选择特定服务实例。
8. 根据所选择的服务，可能会看到以下字段。如果您未输入这些字段的值，那么会在服务实例级别而非存储区级别来分配策略。
    * **资源类型**：输入**存储区**。
    * **资源标识**：输入存储区的名称。
9. 选择任意角色组合来为用户分配所需的访问权。
10. 选择**分配**。

要分配对单个帐户管理服务或所有帐户管理服务的访问权，请完成以下步骤：

1. 在菜单栏中，单击**管理** &gt; **安全性** &gt; **身份和访问权** &gt; **服务标识**。
2. 从表中选择要为其分配服务策略的服务标识。
3. 单击**分配访问权**。
4. 选择分配对**帐户管理服务**的访问权。
5. 选择**所有帐户管理服务**，或选择特定的帐户管理服务。
6. 选择任意角色组合来分配所需的访问权。




## 编辑现有访问权

要编辑现有策略，请执行以下操作：

1. 在菜单栏中，单击**管理** &gt; **安全性** &gt; **身份和访问权** &gt; **服务标识**。
2. 从表中选择要编辑其服务策略的服务标识。
3. 确定要编辑的策略所在的行，然后从**操作**菜单中选择**编辑策略**。
4. 进行更改，然后保存策略。

要使用 CLI 更新服务策略，可以使用 [ibmcloud iam service-policy-update](/docs/cli/reference/ibmcloud/cli_api_policy.html#ibmcloud_iam_service_policy_update) 命令。
```
ibmcloud iam service-policy-update SERVICE_ID POLICY_ID [-v, --version VERSION] {--file JSON_FILE | [-r, --roles ROLE_NAME1,ROLE_NAME2...] [--service-name SERVICE_NAME] [--service-instance SERVICE_INSTANCE] [--region REGION] [--resource-type RESOURCE_TYPE] [--resource RESOURCE] [--resource-group-name RESOURCE_GROUP_NAME] [--resource-group-id RESOURCE_GROUP_ID]} [-f, --force]",
```
{: codeblock}

## 除去访问权

要除去现有策略，请执行以下操作：

1. 在菜单栏中，单击**管理** &gt; **安全性** &gt; **身份和访问权** &gt; **服务标识**。
2. 从表中选择要删除其服务策略的服务标识。
3. 确定要删除的策略所在的行，然后从**操作**菜单中选择**除去**。
4. 复查即将要除去的策略的详细信息，然后通过单击**除去**进行确认。

要使用 CLI 删除服务策略，可以使用 [ibmcloud iam service-policy-delete](/docs/cli/reference/ibmcloud/cli_api_policy.html#ibmcloud_iam_service_policy_delete) 命令。
```
ibmcloud iam service-policy-delete SERVICE_ID POLICY_ID [-f, --force]
```
{: codeblock}
