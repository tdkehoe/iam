---

copyright:

  years: 2017, 2018

lastupdated: "2018-08-29"

---

{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:screen: .screen}
{:new_window: target="_blank"}

# {{site.data.keyword.Bluemix_notm}} Identity and Access Management
{: #iamoverview}

## 什么是 Cloud IAM？

通过 {{site.data.keyword.Bluemix_notm}} Identity and Access Management (IAM)，您可以在整个 {{site.data.keyword.Bluemix_notm}} 平台上一致、安全地对两个平台服务的用户进行认证并控制对资源的访问权。支持一组 {{site.data.keyword.Bluemix_notm}} 服务使用 Cloud IAM 进行访问控制，这些服务在您的帐户中组织成[资源组](/docs/account/resourcegroups.html)，让用户能够快速、轻松地一次访问多个资源。Cloud IAM 访问策略用于为用户和服务标识分配对帐户中资源的访问权。可以将一组用户和服务标识分组到一个[访问组](/docs/iam/groups.html)中，以轻松向该组内所有实体授予相同级别访问权。

策略通过属性组合来定义访问权的作用域，从而为用户或[服务标识](/docs/iam/serviceid.html#serviceids)分配一个或多个角色。策略可以提供对单个服务下至实例级别的访问权，策略也可以应用于组织成资源组的一组资源。根据分配的[用户角色](/docs/iam/users_roles.html#iamusermanrol)，允许用户或服务标识具有不同级别的访问权，以通过使用 UI 或执行特定类型的 API 调用来完成平台管理任务或访问服务。

![用于控制帐户中访问权的 IAM](images/iam-diagram.svg "如何使用 IAM 在帐户中进行访问权管理")

对于不支持创建 Cloud IAM 策略来管理访问权的服务，可以使用 [Cloud Foundry 访问权](/docs/iam/cfaccess.html#cfaccess)。


## Cloud IAM 提供哪些功能？
{: #features}

<dl>
<dt>用户管理</dt>
<dd>通过统一用户管理，您可以在一个帐户中添加和删除平台和基础架构服务的用户。您可以创建一组称为访问组的用户，以便快速、轻松地一次为多个用户分配访问权。</dd>
<dt>细颗粒度访问控制</dt>
<dd>用户和服务标识的访问权由策略定义。在策略中，可以将用户、服务标识或访问组的访问权作用域分配给资源组中的一组资源，或者分配给单个资源。设置作用域后，可以通过选择访问角色来定义策略主题允许的操作。角色用于定制为策略主题授予的访问权级别，以执行平台管理任务以及访问服务的 UI 或执行 API 调用。</dd>
<dt>用于用户认证的 API 密钥</dt>
<dd>可以为用户创建多个 API 密钥来支持密钥轮换方案，并且同一密钥可用于访问多个服务。平台用户 API 密钥支持使用双因子认证或联合标识的用户通过命令行自动执行认证。</dd>
<dt>服务标识</dt>
<dd>服务标识用于标识服务或应用程序，类似于用户标识对用户进行标识的方式。这些是应用程序可以用于向 {{site.data.keyword.Bluemix_notm}} 服务进行认证的标识。可以为每个服务标识分配策略，以使用服务标识来控制应用程序允许的访问级别，并且可以创建 API 密钥来启用认证。</dd>
</dl>


## 如何使用 Cloud IAM？

您可以通过 Identity and Access UI 或 {{site.data.keyword.Bluemix_notm}} CLI 来访问和使用 Cloud IAM。

要使用 UI 来访问 Cloud IAM，请转至**管理** &gt; **安全性** &gt; **身份和访问权**。

要使用 CLI 来访问 Cloud IAM，请参阅[用于管理 API 密钥和策略的命令](/docs/cli/reference/ibmcloud/cli_api_policy.html#ibmcloud_commands_iam)。
