---

copyright:

  years: 2015, 2018
lastupdated: "2018-05-02"

---

{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:screen: .screen}
{:new_window: target="_blank"}

# 分配用户访问权
{: #assignaccess}

在邀请用户时，您将为用户分配访问权，即分配 Cloud Foundry 角色、策略和基础架构许可权。根据您有权管理的访问权选项，可以邀请整个帐户、组织、空间和服务实例中的用户并为其提供访问权。以下各部分描述了可以分配给被邀请用户的三种类型访问权。
{:shortdesc}

## 启用了身份和访问权的服务

邀请新用户时，可以分配单个服务策略。在用户接受邀请后，可以添加其他服务策略。

1. 在**邀请用户**屏幕中，展开**启用了身份和访问权的服务**部分。
2. 选择服务。
3. 选择**所有当前区域**或特定区域。
4. 选择**所有当前服务实例**或选择特定服务实例。
5. 选择用于定义策略的访问权作用域的角色。
6. （可选）可以选择**添加角色**，为策略指定其他角色。

有关设置服务策略时角色的更多信息，请参阅 [Identity and Access Management 策略和角色](/docs/iam/users_roles.html#iamusermanpol)。

## Cloud Foundry 访问权

当您邀请新用户时，您可以选择将用户添加到帐户中的组织。如果您向组织添加用户，那么可以向该用户分配组织角色。然后，选择通过分配的空间角色为受邀的用户提供所选组织中任何或所有空间的访问权。

1. 在**邀请用户**屏幕中，展开 **Cloud Foundry 访问权**部分。
2. 选择要将用户添加到的组织。
3. 选择组织角色，以定义所选组织的访问权级别。
4. 可选：选择**添加角色**以指定其他角色。
5. 选择**所有当前区域**或特定区域。
6. 选择**所有当前空间**或特定空间。
7. 选择空间角色，以定义所选空间的访问权级别。
8. （可选）可以选择**添加角色**，为策略指定其他角色。

有关这些角色的更多信息，请参阅 [Cloud Foundry 角色](/docs/iam/users_roles.html#cfroles)。

**注**：您可以使用 [bluemix iam account-user-invite](/docs/cli/reference/bluemix_cli/bx_cli.html#bluemix_iam_account_user_invite) CLI 命令来添加 Cloud Foundry 角色，但必须使用 UI 来分配其他访问权或许可权。

## 基础架构访问权

所分配的实际许可权会自动限制为您所拥有的许可权的子集。有关这些许可权以及每个许可权允许用户完成哪些操作的更多信息，请参阅[基础架构许可权](/docs/iam/users_roles.html#infrapermissions)。

1. 在**邀请用户**屏幕中，展开**基础架构访问权**部分。
2. 选择用于定义访问权作用域的许可权。

有关将用户添加到帐户后为用户配置访问权的信息，请参阅[管理用户和访问权](/docs/iam/iamusermanage.html)。
