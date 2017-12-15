---

copyright:

  years: 2017

lastupdated: "2017-11-16"

---

{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:screen: .screen}
{:new_window: target="_blank"}
{:tip: .tip}

# IAM-Zugriff verwalten
{: #iammanidaccser}

Um den Zugriff zu verwalten oder Benutzern neue Zugriffsberechtigungen zuzuweisen, müssen Sie der Kontoeigner, der Administrator für alle Services im Konto oder der zugewiesene Administrator für den entsprechenden Service oder die entsprechende Serviceinstanz sein. Weitere Informationen zu den Zugriffsrichtlinien und Rollen finden Sie im Abschnitt zum [IAM-Zugriff](/docs/iam/users_roles.html). 

## Vorhandene Zugriffsberechtigungen bearbeiten

1. Klicken Sie in der Menüleiste auf **Verwalten** &gt; **Sicherheit** &gt; **Identität und Zugriff** und wählen Sie dann **Benutzer** aus.
2. Wählen Sie den Namen des Benutzers aus, dem Sie Zugriffsberechtigungen zuweisen möchten.
3. Wählen Sie in der Zeile für die Richtlinie, die bearbeitet werden soll, das Menü **Aktionen** aus und klicken Sie dann auf **Richtlinie bearbeiten**.
4. Bearbeiten Sie die Richtlinie.
5. Klicken Sie auf **Speichern**.

## Neue Zugriffsberechtigungen zuweisen
{: #assignaccess}

### Zugriff auf Ressourcen in einer Ressourcengruppe 

Um Zugriffsberechtigungen für alle Ressourcen einer Ressourcengruppe oder für einen einzelnen Service in einer Ressourcengruppe zuzuweisen, müssen Sie die folgenden Schritte ausführen:

1. Klicken Sie in der Menüleiste auf **Verwalten** &gt; **Sicherheit** &gt; **Identität und Zugriff** und wählen Sie dann **Benutzer** aus.
2. Wählen Sie in der Zeile für den Benutzer, dem Sie Zugriffsberechtigungen zuweisen wollen, das Menü **Aktionen** aus und klicken Sie dann auf **Zugriff zuweisen**.
3. Wählen Sie die Option **Zugriff in einer Ressourcengruppe zuweisen** aus.
4. Wählen Sie eine Ressourcengruppe aus.
5. Wählen Sie eine Rolle für das Feld **Zugriff für eine Ressourcengruppe zuweisen** aus, um dem Benutzer die Anzeige der Ressourcengruppe im Dashboard, das Bearbeiten des Ressourcengruppennamens oder das Verwalten des Benutzerzugriffs auf die Gruppe zu ermöglichen. Sie können **Kein Zugriff** auswählen, wenn der Benutzer ausschließlich Zugriff auf die Ressource erhalten soll, die Sie angeben, nicht jedoch auf die Gruppe, in der die Ressource enthalten ist.
6. Wählen Sie einen Service in der Ressourcengruppe aus, oder wählen Sie aus, dass der Zugriff auf alle Services in der ausgewählten Gruppe bereitgestellt werden soll.
7. Wählen Sie eine beliebige Zusammenstellung von Rollen aus, um dem Benutzer die gewünschten Zugriffsberechtigungen zuzuweisen. Dieser Zugriff gilt nur für die Ressourcen, die Sie für die Richtlinie ausgewählt haben. Der Zugriff auf den Container selbst, der die Ressourcengruppe darstellt, wird hingegen nicht erteilt. 
8. Klicken Sie auf **Zuweisen**.

### Zugriff auf Ressourcen
{: #resourceaccess}

Führen Sie die folgenden Schritte aus, um Zugriffsberechtigungen für eine einzelne Ressource im Konto oder für alle Ressourcen im Konto zuzuweisen: 

1. Klicken Sie in der Menüleiste auf **Verwalten** &gt; **Sicherheit** &gt; **Identität und Zugriff** und wählen Sie dann **Benutzer** aus.
2. Wählen Sie in der Zeile für den Benutzer, dem Sie Zugriffsberechtigungen zuweisen wollen, das Menü **Aktionen** aus und klicken Sie dann auf **Zugriff zuweisen**.
3. Wählen Sie die Option **Zugriff auf Ressourcen zuweisen** aus.
4. Wählen Sie einen Service oder die Option **Alle durch Identity and Access aktivierten Services** aus.
5. Wählen Sie **Alle aktuellen Regionen** oder eine bestimmte Region aus, wenn Sie vom System dazu aufgefordert werden. 
6. Wählen Sie **Alle aktuellen Serviceinstanzen** oder eine bestimmte Serviceinstanz aus.
7. Abhängig vom ausgewählten Service können die folgenden Felder angezeigt werden. Wenn Sie für diese Felder keine Werte eingeben, wird die Richtlinie nicht auf der Bucketebene, sondern auf der Serviceinstanzebene zugewiesen. 
    * **Ressourcentyp**: Geben Sie **Bucket** ein.
    * **Ressourcen-ID**: Geben Sie den Namen des Buckets ein.
8. Wählen Sie eine beliebige Zusammenstellung von Rollen aus, um dem Benutzer die gewünschten Zugriffsberechtigungen zuzuweisen.
9. Klicken Sie auf **Zuweisen**.

Um einem Benutzer Zugriffsberechtigungen für alle Kontoressourcen und die Berechtigung zum Verwalten des Benutzerzugriffs, zum Erstellen von Ressourcengruppen und zum Ausführen aller anderen IAM-Management-Tasks zu erteilen, wählen Sie die Option **Alle durch Identity and Access aktivierten Services** für diese Richtlinie aus und weisen Sie dabei die Rolle **Administrator** zu.
{: tip}


## Zugriffsberechtigungen entfernen

1. Klicken Sie in der Menüleiste auf **Verwalten** &gt; **Sicherheit** &gt; **Identität und Zugriff** und wählen Sie dann **Benutzer** aus.
2. Wählen Sie den Benutzernamen aus, dessen Zugriffsberechtigungen entfernt werden sollen.
3. Wählen Sie in der Zeile für die Richtlinie, die entfernt werden soll, das Menü **Aktionen** aus und klicken Sie dann auf **Entfernen**.
4. Überprüfen Sie die Details zur Benutzerrichtlinie, die entfernt werden soll, und bestätigen Sie dann die Ausführung der Aktion, indem Sie auf **Entfernen** klicken.

## Zugewiesene Zugriffsberechtigungen überprüfen

Wenn Sie Ihre zugewiesenen Zugriffsberechtigungen in einem Konto überprüfen müssen, zu dem Sie hinzugefügt wurden, führen Sie die folgenden Schritte aus:

1. Klicken Sie in der Menüleiste auf **Verwalten** &gt; **Sicherheit** &gt; **Identität und Zugriff** und wählen Sie dann **Benutzer** aus.
2. Wählen Sie Ihren Namen aus.
3. Überprüfen Sie Ihre zugewiesenen Zugriffsberechtigungen im Abschnitt **Zugriffsrichtlinien**.

Wenn Sie weiterführende Zugriffsberechtigungen benötigen, müssen Sie sich an den Kontoeigner wenden, um Ihre Zugriffsberechtigungen aktualisieren zu lassen. Alternativ hierzu können Sie sich auch an den zuständigen Administrator für den Service oder die Serviceinstanz wenden, um die Cloud IAM-Zugriffsrichtlinie aktualisieren zu lassen.
