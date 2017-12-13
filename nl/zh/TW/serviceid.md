---

copyright:

  years: 2017
lastupdated: "2017-11-16"

---

{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:screen: .screen}
{:new_window: target="_blank"}

# 建立及管理服務 ID
{: #serviceids}

服務 ID 會識別與使用者 ID 如何識別使用者類似的服務或應用程式。您建立的服務 ID 可以用來在 {{site.data.keyword.Bluemix_notm}} 外部啟用應用程式，以存取您的 {{site.data.keyword.Bluemix_notm}} 服務。您可以將特定存取原則指派給服務 ID，而服務 ID 限制用於使用特定服務的許可權，或甚至結合用於存取不同服務的許可權。因為服務 ID 未關聯至特定使用者，所以如果使用者離開組織，並已從帳戶中予以刪除，則服務 ID 仍可確保您的應用程式或服務保持啟動並執行。

當您建立服務 ID 時，會建立唯一名稱及說明，方便您在使用者介面中識別及使用服務。在您建立服務 ID 之後，即可建立每一個服務 ID 特有的 API 金鑰，而應用程式可以使用這些金鑰向 {{site.data.keyword.Bluemix_notm}} 服務進行鑑別。若要確定應用程式具有向 {{site.data.keyword.Bluemix_notm}} 服務進行鑑別的適當存取權，請使用指派給所建立之每一個服務 ID 的服務原則。 

與服務 ID 相關聯的存取原則會啟用可在使用該服務 ID 存取特定服務時採取的特定動作。單一服務 ID 可以獲指派多個原則，以定義在存取多個啟用身分及存取的服務，甚至是單一服務的不同實例時所容許的存取層次。例如，您有兩個服務，各有兩個服務實例。例如，您可能針對一個服務的所有可用實例指派 `Viewer` 角色，並針對第二個服務的一個實例僅指派 `Editor` 角色。因此，您可以自訂多個服務的存取權，但使用單一 API 金鑰來鑑別所有服務。


## 建立服務 ID

若要建立服務 ID，請移至**管理** &gt; **安全** &gt; **身分及存取**，然後從側邊畫面中選取**服務 ID**。請遵循可建立服務 ID 之名稱及說明的處理程序。然後，使用**動作**功能表來管理您的服務 ID。您可以從指派原則以及建立 API 金鑰開始。如需使用 API 金鑰的相關資訊，請參閱[管理服務 ID API 金鑰](/docs/iam/serviceid_keys.html#serviceidapikeys)。如需用來管理服務 ID 之 CLI 指令的詳細資料，請參閱[用來管理 API 金鑰及原則的指令](/docs/cli/reference/bluemix_cli/bx_cli.html#bx_commands_iam)。 

## 更新服務 ID

您隨時可以變更名稱及說明，來更新服務 ID。也可以視需要刪除及建立新的 API 金鑰，或更新所指派的存取原則。不過，您對現有服務 ID 進行的任何變更（例如，變更已指派的原則，或刪除目前正在使用的 API 金鑰），可能會導致使用該服務 ID 之應用程式的服務岔斷。


