---

copyright:

  years: 2017, 2018

lastupdated: "2017-11-16"

---

{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:screen: .screen}
{:new_window: target="_blank"}

# IAM 及 Cloud Foundry 存取模型
{: #accessmodels}

目前，並非所有 {{site.data.keyword.Bluemix_notm}} 服務都支援使用 Cloud IAM 存取管理。未啟用 Cloud IAM 的服務會繼續根據 Cloud Foundry 組織及空間中的使用者角色，來判定使用者是否有權存取資源。您可以使用 {{site.data.keyword.Bluemix_notm}}「身分及存取」使用者介面，來管理使用 Cloud IAM 或 Cloud Foundry 存取管理系統的服務存取權。


## 切換至 Cloud IAM 的 Cloud Foundry 服務
{: #cftoiam}

如果您目前是使用 Cloud Foundry 服務來開始支援使用 Cloud IAM 存取管理，則會收到一則通知，指出您現在可以對所建立的新服務實例充分運用 IAM 的存取控制。

服務開始啟用 Cloud IAM 時，您可以預期下列事項：

* 對於帳戶中已使用 Cloud Foundry 存取管理的現有實例，透過將使用者指派給具有 Cloud Foundry 角色的組織及空間，您可以繼續使用那些實例，而不需要進行任何變更。
* 若要建立新的實例，您可以將每一個實例指派給帳戶中的資源群組，然後，如果您是資源群組的管理者，則可以使用 Cloud IAM 來管理對該實例的存取權，以及其所屬資源群組的存取權。

支援使用 Cloud IAM 的服務有幾個優點，包括在任何 Cloud Foundry 空間中連接至應用程式及服務的能力，這容許您從不同的地區連接應用程式及服務。此外，Cloud IAM 所管理的每一個實例都屬於一個資源群組，而資源群組不是依地區限定範圍，因此您可以將不同地區的應用程式及服務佈建給相同的資源群組。您也可以使用往下至個別實例的精細存取控制。
