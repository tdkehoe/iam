---

copyright:

  years: 2015, 2018
lastupdated: "2018-01-26"

---

{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:screen: .screen}
{:new_window: target="_blank"}

# 使用 API 金鑰
{: #manapikey}

應用程式設計介面金鑰（API 金鑰）是傳入應用程式設計介面 (API) 的唯一代碼，可識別呼叫端應用程式或使用者。API 金鑰用來追蹤及控制 API 的使用方式，例如，防止惡意使用或濫用 API。API 金鑰通常作為進行鑑別的唯一 ID 及密碼記號，而且一般具有其相關聯身分特有的一組存取權。

## 平台 API 金鑰

平台API 金鑰是在「身分及存取管理使用者介面」中建立，並且可以與下列項目相關聯：

* 帳戶的使用者
* 帳戶中建立的服務 ID

您可以建立及使用鏈結至您帳戶的 API 金鑰。聯合或非聯合使用者可以建立 API 金鑰以在 CLI 上使用，或是在自動化作業之中使用，以您的使用者身分登入。如需使用與您使用者身分相關聯的 API 金鑰的相關資訊，請參閱[管理使用者 API 金鑰](userid_keys.html)。

您也可以使用與所建立服務 ID 相關聯的 API 金鑰。服務 ID 是用來將 {{site.data.keyword.Bluemix_notm}} 內部或外部的應用程式連接至 {{site.data.keyword.Bluemix_notm}} 服務。如需建立與服務 ID 相關聯的 API 金鑰的相關資訊，請參閱[管理服務 ID API 金鑰](serviceid_keys.html)。

## 其他 {{site.data.keyword.Bluemix_notm}} API 金鑰

除了您的平台 API 金鑰之外，使用 {{site.data.keyword.Bluemix_notm}} 時還有一些您可能使用的其他 API 金鑰類型：

* 基礎架構 API 金鑰
* 服務特有的 API 金鑰

基礎架構 API 金鑰是在客戶入口網站中建立，並且與您的 SoftLayer 帳戶使用者 ID 相關聯，在存取基礎架構服務的 API 時會用到。

{{site.data.keyword.Bluemix_notm}} 中的某些服務，可能也會提供 API 金鑰，供您用來與服務進行互動。例如，如果您從儀表板中檢視 Watson 服務的服務詳細資料，則您可以在「服務認證」標籤上建立包括 API 金鑰及密碼的認證，而此認證僅專屬於這個服務。

