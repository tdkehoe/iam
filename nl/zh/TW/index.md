---

copyright:

  years: 2017

lastupdated: "2017-11-16"

---

{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:screen: .screen}
{:new_window: target="_blank"}

# {{site.data.keyword.Bluemix_notm}} 身分及存取管理
{: #iamoverview}

## 何謂 Cloud IAM？

「{{site.data.keyword.Bluemix_notm}} 身分及存取管理 (IAM)」可讓您安全地鑑別平台及基礎架構服務的使用者，並跨 {{site.data.keyword.Bluemix_notm}} 平台一致地控制資源的存取。讓一組 {{site.data.keyword.Bluemix_notm}} 服務使用 Cloud IAM 來存取控制，並在帳戶內組織為[資源群組](/docs/admin/resourcegroups.html)，讓使用者可以同時快速並輕鬆地存取多個資源。Cloud IAM 存取原則是用來指派使用者及服務 ID 對帳戶內資源的存取權。

原則會使用用於定義存取範圍的屬性組合，將一個以上的角色指派給使用者或[服務 ID](/docs/iam/serviceid.html#serviceids)。原則可以提供單一服務（直到實例層次）的存取權，也可以套用至一組在資源群組中組織在一起的資源。根據您指派的[使用者角色](/docs/iam/users_roles.html#iamusermanrol)，容許使用者或服務 ID 有不同的存取層次來完成平台管理作業，或使用使用者介面或執行特定類型的 API 呼叫來存取服務。

對於不支援建立 Cloud IAM 原則來管理存取權的服務，您可以使用 [Cloud Foundry 存取](/docs/iam/cfaccess.html#cfaccess)。


## Cloud IAM 提供哪些特性？
{: #features}

<dl>
<dt>使用者管理</dt>
<dd>統一使用者管理可讓您在平台及基礎架構服務的帳戶中新增及刪除使用者。</dd>
<dt>精細存取控制</dt>
<dd>使用者及服務 ID 的存取權是透過原則進行定義。在原則內，可以將存取範圍指派給資源群組中的一組資源或是單一資源。設定範圍之後，您可以藉由選取存取角色來定義原則主題所容許的動作。角色可讓您修改針對原則主體所授與的存取層次來執行平台管理作業，以及存取服務使用者介面或執行 API 呼叫。</dd>
<dt>用於使用者鑑別的 API 金鑰</dt>
<dd>您可以為使用者建立多個 API 金鑰來支援金鑰輪替情境，而且可以使用相同的金鑰來存取多個服務。平台使用者 API 金鑰可讓使用雙因子鑑別或聯合 ID 的使用者從指令行自動進行鑑別。</dd>
<dt>服務 ID</dt> 
<dd>服務 ID 會識別與使用者 ID 如何識別使用者類似的服務或應用程式。應用程式可以使用這些 ID 向 {{site.data.keyword.Bluemix_notm}} 服務進行鑑別。您可以將原則指派給每一個服務 ID，以控制應用程式使用服務 ID 所容許的存取層次，而且可以建立 API 金鑰來啟用鑑別。</dd>
</dl>


## 如何使用 Cloud IAM？

您可以透過「身分及存取使用者介面」或 {{site.data.keyword.Bluemix_notm}} 的 CLI 來存取及使用 Cloud IAM。

若要使用使用者介面來存取 Cloud IAM，請移至**管理** &gt; **安全** &gt; **身分及存取**。

若要使用 CLI 來存取 Cloud IAM，請參閱[用來管理 API 金鑰及原則的指令](/docs/cli/reference/bluemix_cli/bx_cli.html#bx_commands_iam)。
