---

copyright:

  years: 2017, 2018

lastupdated: "2018-04-17"

---

{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:screen: .screen}
{:new_window: target="_blank"}
{:tip: .tip}

# 将 Cloud Foundry 服务实例迁移到资源组
{: #accessmodels}

服务从使用 Cloud Foundry 组织、空间和角色迁移到使用 Cloud Identity and Access Management (IAM) 和资源组时，您将在仪表板上收到相应通知。服务迁出 Cloud Foundry 时，会提示您将属于组织和空间的现有服务实例迁移到[资源组](/docs/account/resourcegroups.html#rgs)中。 

如果将现有 Cloud Foundry 服务实例迁移到资源组，那么在迁移完成后无法更改您所做的组分配。因此，在迁移之前，必须确保决定如何在帐户中组织资源。这可能意味着在迁移之前，您需要创建一个或多个资源组（如果您有付费帐户）。
{: tip}

## 为什么要迁移服务实例？

支持使用 Cloud IAM 的服务有若干优点，包括能够连接到任何 Cloud Foundry 空间中的应用程序和服务，这样一来，您可以连接来自不同区域的应用程序和服务。此外，Cloud IAM 管理的每个实例都属于一个资源组，而资源组的作用域不受区域限制，因此您可以将来自不同区域的应用程序和服务供应到同一资源组中。您还可以使用下至单个实例的细颗粒度访问控制。
 

## 迁移如何工作？

将服务实例从 Cloud Foundry 组织和空间迁移到资源组时，将在资源组中创建新的链接服务实例。Cloud Foundry 组织和空间中的原始实例会变成[别名](/docs/cfapps/connecting_apps.html#what_is_alias)。

在仪表板上收到通过与 Cloud Foundry 服务实例关联的图标提供的通知时，可以一次迁移一个服务实例，或者在服务详细信息页面上收到消息，可以直接转至向导以引导您完成整个迁移过程。在迁移之前，请先决定资源的组织方式，然后可以使用仪表板上的**操作**菜单并选择**迁移到资源组**来选择符合要求的服务实例。在此过程中，可选择要将实例迁移到的资源组。成功迁移实例后，您在仪表板的“服务”部分中可看到相关信息。别名会保留在仪表板的 Cloud Foundry 部分中。 


