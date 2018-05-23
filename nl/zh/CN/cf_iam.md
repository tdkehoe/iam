---

copyright:

  years: 2017, 2018

lastupdated: "2018-05-02"

---

{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:screen: .screen}
{:new_window: target="_blank"}
{:tip: .tip}

# 将 Cloud Foundry 服务实例迁移到资源组
{: #accessmodels}

当服务从使用 Cloud Foundry 组织、空间和角色迁移到使用 Cloud Identity and Access Management (IAM) 和资源组时，您的仪表板上会有相应的通知。将服务从 Cloud Foundry 迁出时，系统会提示您将属于组织和空间的现有服务实例迁移到[资源组](/docs/account/resourcegroups.html#rgs)中。 

如果将现有 Cloud Foundry 服务实例迁移到资源组，那么在迁移完成后无法更改您所做的组分配。因此，在迁移之前，必须确保决定如何在帐户中组织资源。因此，在迁移之前，您可能需要创建一个或多个资源组（如果您有付费帐户）。
{: tip}

## 为什么要迁移服务实例？

支持使用 Cloud IAM 的服务有几个优点。例如，能够连接到任何 Cloud Foundry 空间中的应用程序和服务。这意味着，您可以连接来自不同区域的应用程序和服务。此外，由 Cloud IAM 管理的每个实例都属于一个资源组。资源组不是按区域划分的，因此可以将来自不同区域的应用程序和服务供应给同一资源组。也可以使用能够精细到单个实例的细颗粒度访问控制。
 

## 迁移如何工作？

将服务实例从 Cloud Foundry 组织和空间迁移到资源组时，将在资源组中创建新的链接服务实例。Cloud Foundry 组织和空间中的原始实例会变成[别名](/docs/cfapps/connecting_apps.html#what_is_alias)。

您可以在收到通知后迁移服务实例（一次一个）。系统会以两种方式通知您：在仪表板上显示与 Cloud Foundry 服务实例相关联的图标，或者在服务详细信息页面上显示消息，您可以从该消息中直接转至迁移向导来完成整个迁移过程。在迁移之前，请先决定资源的组织方式。然后，可以选择符合要求的服务实例，方法是从仪表板上的**操作**菜单中选择**迁移到资源组**。在此过程中，可选择要将实例迁移到的资源组。成功迁移实例后，可在仪表板的“服务”部分中看到该实例。别名会保留在仪表板的 Cloud Foundry 部分中。 


