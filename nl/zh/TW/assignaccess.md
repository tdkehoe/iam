---

copyright:

  years: 2015, 2017
lastupdated: "2017-05-30"

---

{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:screen: .screen}
{:new_window: target="_blank"}

# 指派使用者存取權
{: #assignaccess}

您可以在邀請使用者時為其指派存取權，並指派 Cloud Foundry 角色、原則及基礎架構許可權。視您獲授權管理的存取選項而定，您可以邀請帳戶、組織、空間及服務實例的使用者，並為其提供存取權。下列各節說明可指派給受邀使用者的三種類型存取權。
{:shortdesc}

## 已啟用身分及存取的服務

當您邀請新的使用者時，可以指派單一服務原則。在使用者接受邀請之後，您就可以新增其他服務原則。

1. 從**邀請使用者**畫面中，展開**已啟用身分及存取的服務**區段。
2. 選取服務。
3. 選取**所有現行地區**或特定地區。
4. 選取**所有現行服務實例**，或選取特定服務實例。
5. 選取角色以定義原則的存取範圍。
6. 選用項目：選取**新增角色**，以指定原則的其他角色。

如需設定服務原則時角色的特定資訊，請參閱[身分及存取管理原則和角色](/docs/iam/users_roles.html#iamusermanpol)。

## Cloud Foundry 存取

當您邀請新的使用者時，可以選擇將使用者新增至帳戶中的組織。如果您將使用者新增至組織，他們預設都會獲授與審核員組織角色。在使用者接受邀請之後，您稍後可以將此角色更新為帳單管理員、組織管理員或無組織角色。此外，您可以選擇將所邀請的使用者存取權授與所選取組織中的任何或所有空間。

1. 從**邀請使用者**畫面中，展開 **Cloud Foundry 存取**區段。
2. 選取要新增使用者的組織。
3. 選取**所有現行地區**或特定地區。
4. 選取**所有現行空間**或特定空間。
5. 選取空間角色，以定義所選取空間的存取層次。
6. 選用項目：選取**新增角色**，以指定其他角色。

如需這些角色的特定相關資訊，請參閱 [Cloud Foundry 角色](/docs/iam/users_roles.html#cfroles)。

**附註**：您可以使用 [bluemix iam account-user-invite](https://console.stage1.bluemix.net/docs/cli/reference/bluemix_cli/bx_cli.html#bluemix_iam_account_user_invite) CLI 指令來新增 Cloud Foundry 角色，但必須使用使用者介面來指派其他存取權或許可權。

## 基礎架構存取

指派的實際許可權自動受限於您所擁有的許可權子集。如需許可權以及使用者可使用每一個許可權來執行之動作的相關資訊，請參閱[基礎架構許可權](/docs/iam/users_roles.html#infrapermissions)。

1. 從**邀請使用者**畫面中，展開**基礎架構存取**區段。 
2. 選取許可權以定義存取範圍。

如需在將使用者新增至您的帳戶之後為其配置存取權的相關資訊，請參閱[管理使用者及存取權](/docs/iam/iamusermanage.html)。
