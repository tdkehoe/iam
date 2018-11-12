---

copyright:

  years: 2015, 2018
lastupdated: "2018-10-30"

---

{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:screen: .screen}
{:new_window: target="_blank"}

# 管理服務 ID 存取原則
{: #serviceidpolicy}

當您建立服務 ID 時，可以指派該服務 ID 的服務原則，以控制使用它向服務進行鑑別時所容許的存取層次。您隨時可以變更現有原則、刪除原則或指派新原則，來更新這些已指派存取原則。

**附註**：如果您刪除或編輯目前所使用服務 ID 的現有原則，則可能會導致服務岔斷。

## 指派新存取權

若要指派資源群組中所有資源的存取權，或只指派資源群組內一項服務的存取權，請完成下列步驟：

1. 從功能表列中，按一下**管理** &gt; **安全** &gt; **身分及存取** &gt; **服務 ID**。
2. 從表格中，選取您要指派服務原則的服務 ID。
3. 按一下**指派存取權**。
4. 選取以**依資源群組指派**。
5. 選取資源群組。
6. 選擇**指派資源群組存取權**欄位的角色。這個選項讓使用者在其儀表板上檢視資源群組、編輯資源群組名稱，或管理使用者對群組的存取權。如果您要使用者只能存取您指定的資源，而非其指派的群組，則可以選取**不可存取**。
7. 選取資源群組內的服務，或選取以提供所選取群組內所有服務的存取權。
8. 選擇任何角色組合，以指派使用者想要的存取權。此存取權僅適用於您為原則選取的資源。它未提供對本身為資源群組之實際容器的存取權。
9. 選取**指派**。

若要指派帳戶中個別資源的存取權，請完成下列步驟：

1. 從功能表列中，按一下**管理** &gt; **安全** &gt; **身分及存取** &gt; **服務 ID**。
2. 從表格中，選取您要指派服務原則的服務 ID。
3. 按一下**指派存取權**。
4. 選取以**依資源指派**。
5. 選取服務。
6. 當系統提示您時，請選取**所有現行地區**或特定地區。

7. 選取**所有現行服務實例**，或選取特定服務實例。
8. 視您選取的服務而定，可能會看到下列欄位。如果您不輸入這些欄位的值，原則會在服務實例層次指派，而非儲存區層次。
    * **資源類型**：輸入 **bucket**。
    * **資源 ID**：輸入您的儲存區名稱。
9. 選擇任何角色組合，以指派使用者所需的存取權。
10. 選取**指派**。

若要指派對個別帳戶管理服務或所有帳戶管理服務的存取權，請完成下列步驟：

1. 從功能表列中，按一下**管理** &gt; **安全** &gt; **身分及存取** &gt; **服務 ID**。
2. 從表格中，選取您要指派服務原則的服務 ID。
3. 按一下**指派存取權**。
4. 選取以指派對**帳戶管理服務**的存取權。
5. 選取**所有帳戶管理服務**，或選取特定的帳戶管理服務。
6. 選取任何角色組合，以指派想要的存取權。




## 編輯現有存取權

若要編輯現有原則，請執行下列動作：

1. 從功能表列中，按一下**管理** &gt; **安全** &gt; **身分及存取** &gt; **服務 ID**。
2. 從表格中，選取您要編輯服務原則的服務 ID。
3. 識別您要編輯的原則列，然後從**動作**功能表中選取**編輯原則**。
4. 進行變更，然後儲存原則。

若要使用 CLI 更新服務原則，您可以使用 [ibmcloud iam service-policy-update](/docs/cli/reference/ibmcloud/cli_api_policy.html#ibmcloud_iam_service_policy_update) 指令。
```
ibmcloud iam service-policy-update SERVICE_ID POLICY_ID [-v, --version VERSION] {--file JSON_FILE | [-r, --roles ROLE_NAME1,ROLE_NAME2...] [--service-name SERVICE_NAME] [--service-instance SERVICE_INSTANCE] [--region REGION] [--resource-type RESOURCE_TYPE] [--resource RESOURCE] [--resource-group-name RESOURCE_GROUP_NAME] [--resource-group-id RESOURCE_GROUP_ID]} [-f, --force]",
```
{: codeblock}

## 移除存取權

若要移除現有原則，請執行下列動作

1. 從功能表列中，按一下**管理** &gt; **安全** &gt; **身分及存取** &gt; **服務 ID**。
2. 從表格中，選取您要刪除服務原則的服務 ID。
3. 識別您要刪除的原則列，然後從**動作**功能表中選取**移除**。
4. 檢閱您即將移除之原則的詳細資料，然後按一下**移除**進行確認。

若要使用 CLI 刪除服務原則，您可以使用 [ibmcloud iam service-policy-delete](/docs/cli/reference/ibmcloud/cli_api_policy.html#ibmcloud_iam_service_policy_delete) 指令。
```
ibmcloud iam service-policy-delete SERVICE_ID POLICY_ID [-f, --force]
```
{: codeblock}
