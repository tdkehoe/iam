---

copyright:

  years: 2018

lastupdated: "2018-11-30"

---

{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:screen: .screen}
{:new_window: target="_blank"}
{:tip: .tip}

# 除去用户
{: #remove}

从帐户中除去用户后，该用户即无法再登录到控制台，无法切换到您的帐户（如果他们仍然属于其他帐户），也无法访问帐户资源。
{:shortdesc}

只有帐户所有者或具有以下访问权的用户可以从帐户中除去用户：

* 具有分配了对用户管理帐户管理服务的管理员角色的 IAM 策略，并且是 Cloud Foundry 组织管理者（如果用户属于 Cloud Foundry 组织）。
* 如果您的帐户中具有经典基础架构，那么用户必须具有分配了对用户管理帐户管理服务的管理员角色的 IAM 策略，必须是 Cloud Foundry 组织管理者（如果该用户属于 Cloud Foundry 组织），并且必须是经典基础架构用户层次结构中分配了“管理用户”经典基础架构许可权的用户的祖代。

要从帐户除去用户，请完成以下步骤：

1. 在菜单栏中，单击**管理** &gt; **访问权 (IAM)**，然后选择**用户**。
2. 在要除去的用户所在的行中，从**操作** ![“操作列表”图标](../icons/action-menu-icon.svg) 菜单中，选择**除去用户**。
