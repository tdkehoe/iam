---

copyright:

  years: 2015, 2018
lastupdated: "2018-10-30"

---

{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:screen: .screen}
{:new_window: target="_blank"}

# Zugriffsrichtlinien für Service-IDs verwalten
{: #serviceidpolicy}

Wenn Sie eine Service-ID erstellen, dann können sie dieser Service-ID Servicerichtlinien zuweisen, um die Zugriffsebene zu steuern, die zulässig ist, wenn sie zur Authentifizierung bei Ihren Services verwendet wird. Sie können diese zugewiesenen Zugriffsrichtlinien jederzeit aktualisieren, indem Sie eine vorhandene Richtlinie ändern, eine Richtlinie löschen oder eine neue Richtlinie zuweisen.

**Hinweis:** Wenn Sie eine vorhandene Richtlinie für eine momentan verwendete Service-ID löschen oder bearbeiten, kann es zu Serviceunterbrechungen kommen.

## Neue Zugriffsberechtigungen zuweisen

Um Zugriffsberechtigungen für alle Ressourcen einer Ressourcengruppe oder für einen einzelnen Service in einer Ressourcengruppe zuzuweisen, müssen Sie die folgenden Schritte ausführen:

1. Klicken Sie in der Menüleiste auf **Verwalten** &gt; **Sicherheit** &gt; **Identität und Zugriff** &gt; **Service-IDs**.
2. Wählen Sie die Service-ID, der Sie eine Servicerichtlinie zuweisen wollen, in der Tabelle aus.
3. Klicken Sie auf **Zugriff zuweisen**.
4. Wählen Sie die Option für die **Zuweisung nach Ressourcengruppe** aus.
5. Wählen Sie eine Ressourcengruppe aus.
6. Wählen Sie eine Rolle für das Feld **Zugriff für eine Ressourcengruppe zuweisen** aus. Diese Option ermöglicht dem Benutzer, die Ressourcengruppe im Dashboard anzuzeigen, den Ressourcengruppennamen zu bearbeiten oder den Benutzerzugriff auf die Gruppe zu verwalten. Sie können **Kein Zugriff** auswählen, wenn der Benutzer ausschließlich Zugriff auf die Ressource erhalten soll, die Sie angeben, nicht jedoch auf die Gruppe, der die Ressource zugewiesen ist.
7. Wählen Sie einen Service in der Ressourcengruppe aus, oder wählen Sie aus, dass der Zugriff auf alle Services in der ausgewählten Gruppe bereitgestellt werden soll.
8. Wählen Sie eine beliebige Zusammenstellung von Rollen aus, um dem Benutzer die gewünschten Zugriffsberechtigungen zuzuweisen. Dieser Zugriff gilt nur für die Ressourcen, die Sie für die Richtlinie ausgewählt haben. Der Zugriff auf den Container selbst, der die Ressourcengruppe darstellt, wird hingegen nicht erteilt.
9. Wählen Sie **Zuweisen** aus.

Führen Sie die folgenden Schritte aus, um die Zugriffsberechtigungen für eine einzelne Ressource im Konto zuzuweisen:

1. Klicken Sie in der Menüleiste auf **Verwalten** &gt; **Sicherheit** &gt; **Identität und Zugriff** &gt; **Service-IDs**.
2. Wählen Sie die Service-ID, der Sie eine Servicerichtlinie zuweisen wollen, in der Tabelle aus.
3. Klicken Sie auf **Zugriff zuweisen**.
4. Wählen Sie die Option für die **Zuweisung nach Ressource** aus.
5. Wählen Sie einen Service aus.
6. Wählen Sie **Alle aktuellen Regionen** oder eine bestimmte Region aus, wenn Sie vom System dazu aufgefordert werden.
7. Wählen Sie **Alle aktuellen Serviceinstanzen** oder eine bestimmte Serviceinstanz aus.
8. Abhängig vom ausgewählten Service können die folgenden Felder angezeigt werden. Wenn Sie für diese Felder keine Werte eingeben, wird die Richtlinie nicht auf der Bucketebene, sondern auf der Serviceinstanzebene zugewiesen.
    * **Ressourcentyp**: Geben Sie **Bucket** ein.
    * **Ressourcen-ID**: Geben Sie den Namen des Buckets ein.
9. Wählen Sie eine beliebige Zusammenstellung von Rollen aus, um dem Benutzer die gewünschten Zugriffsberechtigungen zuzuweisen.
10. Wählen Sie **Zuweisen** aus.

Führen Sie die folgenden Schritte aus, um Zugriff auf einen einzelnen Kontoverwaltungsservice oder alle Kontoverwaltungsservices zu erteilen:

1. Klicken Sie in der Menüleiste auf **Verwalten** &gt; **Sicherheit** &gt; **Identität und Zugriff** &gt; **Service-IDs**.
2. Wählen Sie die Service-ID, der Sie eine Servicerichtlinie zuweisen wollen, in der Tabelle aus.
3. Klicken Sie auf **Zugriff zuweisen**.
4. Wählen Sie diese Option aus, um Zugriff auf **Kontoverwaltungsservices** zu erteilen.
5. Wählen Sie **Alle Kontoverwaltungsservices** oder einen bestimmten Kontoverwaltungsservice aus.
6. Wählen Sie eine beliebige Zusammenstellung von Rollen aus, um die gewünschten Zugriffsberechtigungen zuzuweisen.




## Vorhandene Zugriffsberechtigungen bearbeiten

Gehen Sie wie folgt vor, um eine vorhandene Richtlinie zu bearbeiten:

1. Klicken Sie in der Menüleiste auf **Verwalten** &gt; **Sicherheit** &gt; **Identität und Zugriff** &gt; **Service-IDs**.
2. Wählen Sie die Service-ID, für die eine Servicerichtlinie bearbeitet werden soll, in der Tabelle aus.
3. Ermitteln Sie die Zeile der Richtlinie, die bearbeitet werden soll, und wählen Sie dann die Option **Richtlinie bearbeiten** im Menü **Aktionen** aus.
4. Nehmen Sie die gewünschten Änderungen vor und speichern Sie dann die Richtlinie.

Wenn Sie eine Servicerichtlinie über die Befehlszeilenschnittstelle aktualisieren möchten, können Sie den Befehl [ibmcloud iam service-policy-update](/docs/cli/reference/ibmcloud/cli_api_policy.html#ibmcloud_iam_service_policy_update) verwenden.
```
ibmcloud iam service-policy-update SERVICE_ID POLICY_ID [-v, --version VERSION] {--file JSON_FILE | [-r, --roles ROLE_NAME1,ROLE_NAME2...] [--service-name SERVICE_NAME] [--service-instance SERVICE_INSTANCE] [--region REGION] [--resource-type RESOURCE_TYPE] [--resource RESOURCE] [--resource-group-name RESOURCE_GROUP_NAME] [--resource-group-id RESOURCE_GROUP_ID]} [-f, --force]",
```
{: codeblock}

## Zugriffsberechtigungen entfernen

Gehen Sie wie folgt vor, um eine vorhandene Richtlinie zu entfernen:

1. Klicken Sie in der Menüleiste auf **Verwalten** &gt; **Sicherheit** &gt; **Identität und Zugriff** &gt; **Service-IDs**.
2. Wählen Sie die Service-ID, für die eine Servicerichtlinie gelöscht werden soll, in der Tabelle aus.
3. Ermitteln Sie die Zeile der Richtlinie, die gelöscht werden soll, und wählen Sie dann die Option **Entfernen** im Menü **Aktionen** aus.
4. Überprüfen Sie die Details zur Richtlinie, die entfernt werden soll, und klicken Sie dann auf **Entfernen**, um die Ausführung der Aktion zu bestätigen.

Wenn Sie eine Servicerichtlinie über die Befehlszeilenschnittstelle löschen möchten, können Sie den Befehl [ibmcloud iam service-policy-delete](/docs/cli/reference/ibmcloud/cli_api_policy.html#ibmcloud_iam_service_policy_delete) verwenden.
```
ibmcloud iam service-policy-delete SERVICE_ID POLICY_ID [-f, --force]
```
{: codeblock}
