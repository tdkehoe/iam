---

copyright:

  years: 2017, 2018

lastupdated: "2017-11-16"

---

{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:screen: .screen}
{:new_window: target="_blank"}

# IAM 和 Cloud Foundry 访问模型
{: #accessmodels}

目前，并非所有 {{site.data.keyword.Bluemix_notm}} 服务都支持使用 Cloud IAM 访问权管理。未启用 Cloud IAM 的服务将继续依赖于用户在 Cloud Foundry 组织和空间中的角色来确定用户是否有权访问资源。可以使用 {{site.data.keyword.Bluemix_notm}} Identity and Access UI 来为使用 Cloud IAM 或 Cloud Foundry 访问管理系统的服务管理访问权。


## 切换到 Cloud IAM 的 Cloud Foundry 服务
{: #cftoiam}

如果当前使用的是 Cloud Foundry 服务且该服务已开始支持使用 Cloud IAM 访问权管理，那么您将收到通知称现在可以将 IAM 的访问控制用于创建的新服务实例。

服务开始启用 Cloud IAM 后，预期以下情况成立：

* 对于帐户中的现有实例，如果它们已通过将用户分配给具有 Cloud Foundry 角色的组织和空间来使用 Cloud Foundry 访问管理，那么可以继续使用这些实例，无需进行任何更改。
* 要创建新实例，可将每个实例分配给帐户中的一个资源组，然后可以使用 Cloud IAM 来管理对该实例及其所属资源组（如果您是该资源组的管理员）的访问权。

支持使用 Cloud IAM 的服务有若干优点，包括能够连接到任何 Cloud Foundry 空间中的应用程序和服务，这样一来，您可以连接来自不同区域的应用程序和服务。此外，Cloud IAM 管理的每个实例都属于一个资源组，而资源组的作用域不受区域限制，因此您可以将来自不同区域的应用程序和服务供应到同一资源组中。您还可以使用下至单个实例的细颗粒度访问控制。
