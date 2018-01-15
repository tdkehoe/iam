---

copyright:

  years: 2015, 2017
lastupdated: "2017-12-07"

---

{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:screen: .screen}
{:new_window: target="_blank"}

# 管理使用者 API 金鑰
{: #userapikey}

聯合或非聯合使用者可以建立 API 金鑰以在 CLI 上使用，或是在自動化作業之中使用，以您的使用者身分登入。您可以使用使用者介面或 CLI 來管理 API 金鑰，方法是列出金鑰、建立金鑰、更新金鑰，或刪除金鑰。若要管理與您使用者身分相關聯的 {{site.data.keyword.Bluemix_notm}} API 金鑰，請移至**管理** &gt; **安全** &gt; **平台 API 金鑰**，以查看具有說明及日期的 API 金鑰清單。然後，您可以從這個頁面建立、編輯或刪除 API 金鑰。如需可用 CLI 指令的完整清單，請參閱[用來管理 API 金鑰及原則的指令](/docs/cli/reference/bluemix_cli/bx_cli.html#bx_commands_iam)。

身為[聯合使用者](/docs/admin/adminpublic.html#federatedid)，您可以利用 `BLUEMIX_API_KEY` 環境變數來使用 API 金鑰進行登入。如需使用 API 金鑰進行登入的相關資訊，請參閱[使用聯合 ID 登入](/docs/cli/login_federated_id.html#federated_id)。

## 建立 API 金鑰

身為 {{site.data.keyword.Bluemix_notm}} 使用者，在啟用程式或 Script 而不將密碼配送至 Script 時，您可能想要使用 API 金鑰。使用 API 金鑰的好處在於使用者或組織可以為不同的程式建立數個 API 金鑰，而且可以在洩密的情況下獨立刪除，而不會干擾其他 API 金鑰甚至使用者。

若要在使用者介面中建立使用者身分的 API 金鑰，請執行下列動作：

1. 移至**管理** &gt; **安全** &gt; **平台 API 金鑰**。
2. 按一下**建立 API 金鑰**。
3. 輸入 API 金鑰的名稱及說明。
4. 按一下**建立 API 金鑰**。
5. 然後，按一下**顯示**以顯示要複製的 API 金鑰，並儲存它以供之後使用，或按一下**下載 API 金鑰**。

**附註**：基於安全理由，只可在建立時複製或下載 API 金鑰。如果 API 金鑰遺失，您必須建立新的 API 金鑰。

若要使用 CLI 建立 API 金鑰，請執行下列動作：

1. 在命令提示字元中輸入 `bluemix iam api-key-create NAME [-d DESCRIPTION] [-f, --file FILE]`，並指定名稱、說明和儲存金鑰用的檔案。例如：

```
bluemix iam api-key-create MyKey -d "this is my API key" -f key_file
``` 


## 更新 API 金鑰

如果您想要變更 API 金鑰的名稱或說明，請在使用者介面或 CLI 中完成下列步驟。

若要編輯 API 金鑰，請執行下列動作：

1. 移至**管理** &gt; **安全** &gt; **平台 API 金鑰**。
2. 從表格中所列 API 金鑰的**動作**功能表中，按一下**編輯名稱及說明** 
3. 更新 API 金鑰的資訊。
4. 按一下**更新 API 金鑰**。

若要使用 CLI 編輯 API 金鑰，請執行下列動作：

1. 在命令提示字元中輸入 `bluemix iam api-key-update NAME [-n NAME] [-d DESCRIPTION]`，並指定金鑰的舊名稱、新名稱和新說明。例如：

```
bluemix iam api-key-update MyCurrentName -n MyNewName -d "the new description of my key"
```

## 刪除 API 金鑰

如果您使用金鑰旋轉策略，則可能會想要刪除舊的金鑰，並取代為新的金鑰。

若要刪除 API 金鑰，請執行下列動作： 

1. 移至**管理** &gt; **安全** &gt; **平台 API 金鑰**。
2. 從表格中所列 API 金鑰的**動作**功能表中，按一下以**刪除**。
3. 然後，按一下**刪除金鑰**來確認刪除。

若要使用 CLI 刪除 API 金鑰，請執行下列動作：
1. 在命令提示字元中輸入 `bluemix iam api-key-delete NAME`，並指定應該刪除的金鑰名稱。
