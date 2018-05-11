---

copyright:

  years: 2015, 2018
lastupdated: "2018-02-26"

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
6. Wählen Sie eine Rolle für das Feld **Zugriff für eine Ressourcengruppe zuweisen** aus, um dem Benutzer die Anzeige der Ressourcengruppe im Dashboard, das Bearbeiten des Ressourcengruppennamens oder das Verwalten des Benutzerzugriffs auf die Gruppe zu ermöglichen. Sie können **Kein Zugriff** auswählen, wenn der Benutzer ausschließlich Zugriff auf die Ressource erhalten soll, die Sie angeben, nicht jedoch auf die Gruppe, der die Ressource zugewiesen ist.
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



## Vorhandene Zugriffsberechtigungen bearbeiten

Gehen Sie wie folgt vor, um eine vorhandene Richtlinie zu bearbeiten:

1. Klicken Sie in der Menüleiste auf **Verwalten** &gt; **Sicherheit** &gt; **Identität und Zugriff** &gt; **Service-IDs**.
2. Wählen Sie die Service-ID, für die eine Servicerichtlinie bearbeitet werden soll, in der Tabelle aus.
3. Ermitteln Sie die Zeile der Richtlinie, die bearbeitet werden soll, und wählen Sie dann die Option **Richtlinie bearbeiten** im Menü **Aktionen** aus.
4. Nehmen Sie die gewünschten Änderungen vor und speichern Sie dann die Richtlinie.

## Zugriffsberechtigungen entfernen

Gehen Sie wie folgt vor, um eine vorhandene Richtlinie zu entfernen:

1. Klicken Sie in der Menüleiste auf **Verwalten** &gt; **Sicherheit** &gt; **Identität und Zugriff** &gt; **Service-IDs**.
2. Wählen Sie die Service-ID, für die eine Servicerichtlinie gelöscht werden soll, in der Tabelle aus.
3. Ermitteln Sie die Zeile der Richtlinie, die gelöscht werden soll, und wählen Sie dann die Option **Entfernen** im Menü **Aktionen** aus.
4. Überprüfen Sie die Details zur Richtlinie, die entfernt werden soll, und klicken Sie dann auf **Entfernen**, um die Ausführung der Aktion zu bestätigen.
