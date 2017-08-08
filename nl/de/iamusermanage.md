---

copyright:

  years: 2015, 2017

lastupdated: "2017-05-30"

---

{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:screen: .screen}
{:new_window: target="_blank"}

# Benutzer und Benutzerzugriff verwalten
{: #iamusermanage}

Abhängig von den Zugriffsoptionen, zu deren Verwaltung Sie berechtigt sind, können Sie Benutzer aus dem gesamten Konto oder der gesamten Organisation anzeigen und verwalten. Als Kontoeigner können Sie Benutzer in einer beliebigen dieser Zugriffsoptionen, die Sie verwalten und auf die dem Benutzer der Zugriff erteilt ist, im aktuellen Konto verwalten.
{:shortdesc}

Um Benutzer in Ihrem Konto zu verwalten, führen Sie die folgenden Schritte aus:

1. Klicken Sie in der Menüleiste auf **Verwalten** &gt; **Konto** &gt; **Benutzer**. Das Fenster 'Benutzer' zeigt eine Liste der Benutzer mit den zugehörigen E-Mail-Adressen für das aktuell ausgewählte Konto an. 
2. Wählen Sie den Benutzernamen aus oder klicken Sie im Menü **Aktionen** auf **Benutzer verwalten**. 
3. Je nachdem, welchen Zugriff Sie verwalten, aktualisieren Sie dann den Zugriff für den Benutzer in den Servicerichtlinien oder in den Abschnitten der Cloud Foundry-Rollen oder klicken Sie auf den Link für den Zugriff auf die Seite 'Infrastructure-Zugriff zuweisen'.

Lesen Sie die folgenden Abschnitte, die weitere Informationen zur Verwaltung der einzelnen Zugriffstypen enthalten.

Wenn Sie Ihren zugewiesenen Zugriff in einem Konto überprüfen müssen, zu dem Sie hinzugefügt wurden, führen Sie die folgenden Schritte aus:

1. Klicken Sie in der Menüleiste auf **Verwalten** &gt; **Sicherheit** &gt; **Identity & Access** &gt; **Benutzer**. 
2. Wählen Sie Ihren Namen aus. 
3. Überprüfen Sie Ihre zugeordneten Rollen.

Wenn Sie zusätzliche Berechtigungen benötigen, müssen Sie sich an den Organisationsmanager oder den Kontoeigner wenden, um die Cloud Foundry-Rolle zu aktualisieren, oder an den Administrator für den Service oder die Serviceinstanz, der die Servicerichtlinie aktualisiert.

Weitere Details zu den CLI-Befehlen, die zum Verwalten von Accounts, Organisationen und Bereichen verwendet werden, finden Sie unter [Befehle für die Verwaltung von Konten, Organisationen und Rollen](/docs/cli/reference/bluemix_cli/bx_cli.html#bx_commands_acctorg).

## Cloud Foundry-Zugriff
{: #iammancfser}

Um den Zugriff auf Kontoorganisationen und -bereiche zu verwalten, müssen Sie Kontoeigner, Organisationsmanager oder Bereichsmanager sein:

1. Klicken Sie in der Menüleiste auf **Verwalten** &gt; **Sicherheit** &gt; **Identity & Access** &gt; **Benutzer**. 
2. Wählen Sie den Benutzernamen aus, für den Sie Rollen bearbeiten möchten.
3. Über das Menü **Aktionen** im Abschnitt zu Cloud Foundry können Sie folgende Aktionen ausführen:

  * Benutzer aus der Organisation entfernen
  * Organisationsrolle bearbeiten
  * Bereichsrolle bearbeiten

Sie können auch einen Benutzer einer anderen Organisation hinzufügen, indem Sie auf **Organisation zuweisen** klicken, wenn Sie der Manager einer Organisation sind, in der der Benutzer noch nicht Mitglied ist. 


## Durch Identity and Access aktivierte Services
{: #iammanidaccser}

Um Servicerichtlinie zu verwalten oder neue Servicerichtlinien für Benutzer zuzuweisen, müssen Sie der Administrator für den Kontozugriff oder der zugewiesene Administrator für den entsprechenden Service oder die Serviceinstanz sein.

1. Klicken Sie in der Menüleiste auf **Verwalten** &gt; **Sicherheit** &gt; **Identity & Access** &gt; **Benutzer**. 
2. Wählen Sie den Benutzernamen aus, für den Sie Servicerichtlinien zuweisen möchten.
3. Wählen Sie **Servicerichtlinien zuweisen** aus, um eine neue Servicerichtlinie zu erstellen oder führen Sie über das Menü **Aktionen** im Abschnitt mit den Servicerichtlinie eine der folgenden Aktionen aus:
  
  * Richtlinie bearbeiten
  * Richtlinie entfernen

Weitere Informationen zu Servicerichtlinien und Rollen finden Sie im Abschnitt [Richtlinien und Rollen für Identity and Access Management](/docs/iam/users_roles.html#iamusermanpol).

## Infrastructure-Services

Zum Erteilen oder Aktualisieren von Infrastrukturberechtigungen klicken Sie auf den Link **Infrastructure-Zugriff zuweisen**.
