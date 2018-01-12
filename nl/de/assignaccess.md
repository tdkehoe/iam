---

copyright:

  years: 2015, 2017
lastupdated: "2017-07-26"

---

{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:screen: .screen}
{:new_window: target="_blank"}

# Benutzerzugriff zuweisen
{: #assignaccess}

Bei der Einladung weisen Sie den Benutzern Zugriffsberechtigungen, Cloud Foundry-Rollen und -Richtlinien sowie Infrastructure-Berechtigungen zu. Abhängig von den Zugriffsoptionen, zu deren Verwaltung Sie berechtigt sind, können Sie Benutzer aus dem gesamten Konto, der gesamten Organisation, dem gesamten Bereich oder der gesamten Serviceinstanz einladen und mit Zugriffsberechtigungen ausstatten. In den folgenden Abschnitten werden die drei Arten von Zugriff beschrieben, die einem eingeladenen Benutzer zugeordnet werden können.
{:shortdesc}

## Services mit aktiviertem Identity and Access Management

Sie können eine einzelne Servicerichtlinie zuordnen, wenn Sie einen neuen Benutzer einladen. Sobald der Benutzer die Einladung angenommen hat, können Sie zusätzliche Servicerichtlinien hinzufügen.

1. Erweitern Sie in der Anzeige **Benutzer einladen** den Abschnitt **Services mit aktiviertem Identity and Access Management**.
2. Wählen Sie einen Service aus.
3. Wählen Sie **Alle aktuellen Regionen** oder eine bestimmte Region aus.
4. Wählen Sie **Alle aktuellen Serviceinstanzen** oder eine bestimmte Serviceinstanz aus.
5. Wählen Sie eine Rolle aus, um den Zugriffsbereich für die Richtlinie zu definieren.
6. Optional: Wählen Sie **Rolle hinzufügen** aus, um eine weitere Rolle für die Richtlinie anzugeben.

Weitere Informationen zu den Rollen beim Festlegen von Servicerichtlinien finden Sie unter [Richtlinien und Rollen für Identity and Access Management](/docs/iam/users_roles.html#iamusermanpol).

## Cloud Foundry-Zugriff

Wenn Sie neue Benutzer einladen, können Sie den Benutzer zu einer Organisation im Konto hinzuzufügen. Wenn Sie den Benutzer zu einer Organisation hinzufügen, können Sie ihm eine Organisationsrolle zuweisen. Anschließend können Sie dem eingeladenen Benutzer Zugriff auf einen, mehrere oder alle Bereiche in der ausgewählten Organisation mit einer zugewiesenen Bereichsrolle erteilen.

1. Erweitern Sie in der Anzeige **Benutzer einladen** den Abschnitt **Cloud Foundry-Zugriff**.
2. Wählen Sie eine Organisation aus, zu der der Benutzer hinzugefügt werden soll.
3. Wählen Sie eine Organisationsrolle aus, um die Zugriffsebene für die ausgewählten Organisationen zu definieren.
4. Optional: Wählen Sie **Rolle hinzufügen** aus, um eine zusätzliche Rolle anzugeben.
5. Wählen Sie **Alle aktuellen Regionen** oder eine bestimmte Region aus.
6. Wählen Sie **Alle aktuellen Bereiche** oder einen bestimmten Bereich aus.
7. Wählen Sie eine Bereichsrolle aus, um die Zugriffsebene für die ausgewählten Bereiche zu definieren.
8. Optional: Wählen Sie **Rolle hinzufügen** aus, um eine zusätzliche Rolle anzugeben.

Nähere Informationen zu diesen Rollen finden Sie in [Cloud Foundry-Rollen](/docs/iam/users_roles.html#cfroles).

**Hinweis**: Sie können eine Cloud Foundry-Rolle mithilfe der Befehlszeile [bluemix iam account-user-invite](/docs/cli/reference/bluemix_cli/bx_cli.html#bluemix_iam_account_user_invite) hinzufügen, müssen jedoch die Benutzerschnittstelle auch zur Erteilung anderer Zugriffsrechte oder Berechtigungen verwenden.

## Infrastructure-Zugriff

Die tatsächlichen zugewiesenen Berechtigungen werden automatisch auf die Untergruppe von Berechtigungen eingeschränkt, die Sie haben. Weitere Informationen zu den Berechtigungen und welche Aktionen der Benutzer mit jeder dieser Berechtigungen ausführen kann, finden Sie unter [Infrastructure-Berechtigungen](/docs/iam/users_roles.html#infrapermissions).

1. Erweitern Sie in der Anzeige **Benutzer einladen** den Abschnitt **Infrastructure-Zugriff**.
2. Wählen Sie eine Berechtigung aus, um den Zugriffsbereich zu definieren.

Informationen zum Konfigurieren des Zugriffs für Benutzer, nachdem diese zu Ihrem Konto hinzugefügt wurden, finden Sie unter [Benutzer und Benutzerzugriff verwalten](/docs/iam/iamusermanage.html).
