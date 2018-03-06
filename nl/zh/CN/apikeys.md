---

copyright:

  years: 2015, 2018
lastupdated: "2018-01-26"

---

{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:screen: .screen}
{:new_window: target="_blank"}

# 使用 API 密钥
{: #manapikey}

应用程序编程接口密钥（API 密钥）是传入到应用程序编程接口 (API) 的唯一代码，用于确定调用应用程序或用户。API 密钥用于跟踪和控制 API 的使用情况，例如阻止恶意使用或滥用 API。API 密钥经常充当进行认证的唯一标识和私钥令牌，而且通常有一组特定于其关联身份的访问权。

## 平台 API 密钥

平台 API 密钥是在 Identity and Access Management UI 中创建的，可与以下内容相关联：

* 帐户的用户
* 帐户中创建的服务标识

可以创建和使用链接到您帐户的 API 密钥。联合或非联合用户可以创建要在 CLI 上使用的 API 密钥，或者作为自动化的一部分创建 API 密钥，以便以您的用户身份登录。有关使用与用户身份关联的 API 密钥的更多信息，请参阅[管理用户 API 密钥](userid_keys.html)。

您还可以使用与您创建的服务标识关联的 API 密钥。服务标识用于将 {{site.data.keyword.Bluemix_notm}} 内部或外部的应用程序连接到 {{site.data.keyword.Bluemix_notm}} 服务。有关创建与服务标识关联的 API 密钥的更多信息，请参阅[管理服务标识 API 密钥](serviceid_keys.html)。

## 其他 {{site.data.keyword.Bluemix_notm}} API 密钥

除了平台 API 密钥，在使用 {{site.data.keyword.Bluemix_notm}} 时还可使用其他两种类型的 API 密钥：

* 基础架构 API 密钥
* 特定于服务的 API 密钥

基础架构 API 密钥是在客户门户网站中创建的，与 SoftLayer 帐户用户标识相关联，在访问基础架构服务的 API 时使用。

{{site.data.keyword.Bluemix_notm}} 中的某些服务可能还会为您提供用于与服务进行交互的 API 密钥。例如，如果从仪表板查看 Watson 服务的服务详细信息，您可以在“服务凭证”选项卡上创建仅特定于该服务的凭证（包括 API 密钥和私钥）。

