---

copyright:

  years: 2015, 2017

lastupdated: "2017-10-06"

---

{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:screen: .screen}
{:new_window: target="_blank"}

# Benutzer und Zugriffsrichtlinien verwalten
{: #iamusermanage}

Abhängig von den Zugriffsoptionen, zu deren Verwaltung Sie berechtigt sind, können Sie Benutzer aus dem gesamten Konto oder der gesamten Organisation anzeigen und verwalten. Als Kontoeigner können Sie Benutzer in einer beliebigen dieser Zugriffsoptionen, die Sie verwalten und auf die dem Benutzer der Zugriff erteilt ist, im aktuellen Konto verwalten.
{:shortdesc}

## Benutzer verwalten

Um Benutzer in Ihrem Konto zu verwalten, führen Sie die folgenden Schritte aus:

1. Klicken Sie in der Menüleiste auf **Verwalten** &gt; **Konto** &gt; **Benutzer**. Das Fenster 'Benutzer' zeigt eine Liste der Benutzer mit den zugehörigen E-Mail-Adressen für das aktuell ausgewählte Konto an.
2. Wählen Sie den Benutzernamen aus oder klicken Sie im Menü **Aktionen** auf **Benutzer verwalten**.
3. Abhängig von den Aktionen, die Sie ausführen müssen, können Sie den Benutzer entfernen, eine neue Richtlinie zuweisen oder den vorhandenen Zugriff des Benutzers verwalten.

Lesen Sie die folgenden Abschnitte, die weitere Informationen zur Verwaltung der einzelnen Zugriffstypen enthalten.

Wenn Sie Ihren zugewiesenen Zugriff in einem Konto überprüfen müssen, zu dem Sie hinzugefügt wurden, führen Sie die folgenden Schritte aus:

1. Klicken Sie in der Menüleiste auf **Verwalten** &gt; **Sicherheit** &gt; **Identität & Zugriff** &gt; **Benutzer**.
2. Wählen Sie Ihren Namen aus.
3. Überprüfen Sie Ihre zugeordneten Rollen.

Wenn Sie zusätzliche Berechtigungen benötigen, müssen Sie sich an den Organisationsmanager oder den Kontoeigner wenden, um die Cloud Foundry-Rolle zu aktualisieren, oder an den Administrator für den Service oder die Serviceinstanz, der die Servicerichtlinie aktualisiert.

Weitere Details zu den CLI-Befehlen, die zum Verwalten von Accounts, Organisationen und Bereichen verwendet werden, finden Sie unter [Befehle für die Verwaltung von Konten, Organisationen und Rollen](/docs/cli/reference/bluemix_cli/bx_cli.html#bx_commands_acctorg).

## Cloud Foundry-Zugriff
{: #iammancfser}

Um den Zugriff auf Kontoorganisationen und -bereiche zu verwalten, müssen Sie Kontoeigner, Organisationsmanager oder Bereichsmanager sein:

1. Klicken Sie in der Menüleiste auf **Verwalten** &gt; **Sicherheit** &gt; **Identität & Zugriff** &gt; **Benutzer**.
2. Wählen Sie den Benutzernamen aus, für den Sie Rollen bearbeiten möchten.
3. Über das Menü **Aktionen** im Abschnitt zu Cloud Foundry können Sie folgende Aktionen ausführen:

  * Benutzer aus der Organisation entfernen
  * Organisationsrolle bearbeiten
  * Bereichsrolle bearbeiten

Sie können auch einen Benutzer einer anderen Organisation hinzufügen, indem Sie auf **Organisation zuweisen** klicken, wenn Sie der Manager einer Organisation sind, in der der Benutzer noch nicht Mitglied ist.


## Identitäts- und zugriffsaktivierte Servicezugriffsrichtlinien
{: #iammanidaccser}

Um Servicerichtlinie zu verwalten oder neue Servicerichtlinien für Benutzer zuzuweisen, müssen Sie der Administrator für den Kontozugriff oder der zugewiesene Administrator für den entsprechenden Service oder die Serviceinstanz sein. Weitere Informationen zu Servicerichtlinien und Rollen finden Sie im Abschnitt [Richtlinien und Rollen für Identity and Access Management](/docs/iam/users_roles.html#iamusermanpol). Detaillierte Informationen zu den CLI-Befehlen, die zum Verwalten von Richtlinien verwendet werden, finden Sie in [Befehle zur Verwaltung von API-Schlüsseln und Richtlinien](/docs/cli/reference/bluemix_cli/bx_cli.html#bx_commands_iam).

### Vorhandene Richtlinie bearbeiten

1. Klicken Sie in der Menüleiste auf **Verwalten** &gt; **Sicherheit** &gt; **Identität & Zugriff** &gt; **Benutzer**.
2. Wählen Sie den Benutzernamen aus, für den Sie Servicerichtlinien zuweisen möchten.
3. Wählen Sie in der Zeile für die Richtlinie, die bearbeitet werden soll, das Menü **Aktionen** aus und klicken Sie dann auf **Richtlinie bearbeiten**.
4. Bearbeiten Sie die Richtlinie.
5. Klicken Sie auf **Richtlinie speichern**.

### Neue Richtlinie hinzufügen

1. Klicken Sie in der Menüleiste auf **Verwalten** &gt; **Sicherheit** &gt; **Identität & Zugriff** &gt; **Benutzer**.
2. Wählen Sie den Benutzernamen aus, für den Sie Servicerichtlinien zuweisen möchten.
3. Wählen Sie **Richtlinien zuweisen** aus.
4. Wählen Sie einen Service aus.
5. Wählen Sie **Alle aktuellen Regionen** oder eine bestimmte Region aus, wenn Sie vom System dazu aufgefordert werden. 
**Hinweis:** Nicht alle Services erfordern die Auswahl einer Region.
6. Wählen Sie **Alle aktuellen Serviceinstanzen** oder eine bestimmte Serviceinstanz aus.
7. Abhängig vom ausgewählten Service können die folgenden Felder angezeigt werden. Wenn Sie für diese Felder keine Werte eingeben, wird die Richtlinie nicht auf der Bucketebene, sondern auf der Serviceinstanzebene zugewiesen. 
    * **Ressourcentyp**: Geben Sie **Bucket** ein.
    * **Ressource**: Geben Sie den Namen des Buckets ein.
8. Wählen Sie eine Rolle aus, um den Zugriffsbereich für die Richtlinie zu definieren.
9. Optional: Wählen Sie **Rolle hinzufügen** aus, um eine weitere Rolle für die Richtlinie anzugeben.

### Richtlinie entfernen

1. Klicken Sie in der Menüleiste auf **Verwalten** &gt; **Sicherheit** &gt; **Identität & Zugriff** &gt; **Benutzer**.
2. Wählen Sie den Benutzernamen aus, für den Sie Servicerichtlinien zuweisen möchten.
3. Wählen Sie in der Zeile für die Richtlinie, die entfernt werden soll, das Menü **Aktionen** aus und klicken Sie dann auf **Richtlinie entfernen**.
4. Überprüfen Sie die Details zur Benutzerrichtlinie, die entfernt werden soll, und bestätigen Sie dann die Ausführung der Aktion, indem Sie auf **Richtlinie entfernen** klicken.
  

## Berechtigungen für Infrastrukturservices

Zum Erteilen oder Aktualisieren von Infrastrukturberechtigungen klicken Sie auf den Link **Infrastructure-Zugriff zuweisen**.

