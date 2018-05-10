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

# 將 Cloud Foundry 服務實例移轉至資源群組
{: #accessmodels}

當服務從使用 Cloud Foundry 組織、空間及角色，改為使用 Cloud Identity and Access Management (IAM) 和資源群組時，您的儀表板上會收到通知。當服務離開 Cloud Foundry 時，系統會提示您將屬於組織及空間的現有服務實例，移轉至[資源群組](/docs/account/resourcegroups.html#rgs)。 

當您將現有的 Cloud Foundry 服務實例移轉至資源群組時，移轉定案之後便無法變更您進行的群組指派。因此，您必須在移轉之前，確定您要如何組織帳戶中資源的決策。這可能表示您需要在移轉之前建立一個以上的資源群組，如果您有付費帳戶的話。
{: tip}

## 為何要移轉服務實例？

支援使用 Cloud IAM 的服務有幾個優點，包括在任何 Cloud Foundry 空間中連接至應用程式及服務的能力，這容許您從不同的地區連接應用程式及服務。此外，Cloud IAM 所管理的每一個實例都屬於一個資源群組，而資源群組不是依地區限定範圍，因此您可以將不同地區的應用程式及服務佈建給相同的資源群組。您也可以使用往下至個別實例的精細存取控制。
 

## 移轉如何運作？

將服務實例從 Cloud Foundry 組織及空間移轉至資源群組會在資源群組中建立一個新的鏈結服務實例。Cloud Foundry 組織及空間中的原始實例會變成[別名](/docs/cfapps/connecting_apps.html#what_is_alias)。

當您在儀表板上收到與 Cloud Foundry 服務實例相關聯圖示的通知，或是服務詳細資料頁面上訊息的通知時，您可以一次移轉一個服務實例；服務詳細資料頁面可直接帶您使用引導您完成處理程序的精靈。在您移轉之前，請先決定您要如何組織資源，然後便可以使用儀表板上的**動作**功能表來選擇有資格的服務實例，然後選取**移轉至資源群組**。在過程中，您會選取要將實例移轉至的資源群組。順利移轉實例之後，您會看到它反映在儀表板的「服務」區段中。該別名會保留在儀表板的 Cloud Foundry 區段中。 


