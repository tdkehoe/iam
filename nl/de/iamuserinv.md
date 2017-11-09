---

copyright:

  years: 2015, 2017
lastupdated: "2017-10-06"

---

{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:screen: .screen}
{:new_window: target="_blank"}

# Benutzer einladen und Benutzern Zugriff zuweisen
{: #iamuserinv}

Sie können Benutzer von {{site.data.keyword.Bluemix_notm}}-Services, von Anwendungen und in der gesamten {{site.data.keyword.Bluemix_notm}}-Infrastruktur von einer einzigen Position aus einladen. Zum Einladen von Benutzern und Verwalten ausstehender Benutzer müssen Sie entweder ein Kontoeigner oder ein Organisationsmanager sein oder über die Infrastructure-Berechtigungen zum Hinzufügen von Benutzern verfügen. Sie können Benutzer einladen, Einladungen abbrechen und anstehende Einladungen erneut an eingeladene Benutzer senden. Sie können einen einzelnen Benutzer einladen, wenn Sie denselben Zugriff für alle Mitglieder in einer Gruppe bereitstellen, und Sie können mehrere Benutzer gleichzeitig einladen.  
{:shortdesc}

## Benutzer einladen

Führen Sie die folgenden Schritte aus, um Benutzer einzuladen oder Einladungen in Ihrem Konto zu verwalten: 

1. Klicken Sie in der Menüleiste auf **Verwalten** &gt; **Sicherheit** &gt; **Identität & Zugriff** &gt; **Benutzer**. Das Fenster 'Benutzer' zeigt eine Liste der Benutzer mit den zugehörigen E-Mail-Adressen und dem aktuellen Status des aktuell ausgewählten Kontos an.
2. Klicken Sie auf **Benutzer einladen**.
3. Geben Sie die E-Mail-Adresse oder IBMid des Benutzers an. Wenn Sie mehreren Benutzern denselben Zugriff erteilen, dann können Sie mehrere E-Mail-Adressen oder IBMids eingeben, indem Sie die einzelnen Einträge für die IDs der Benutzer durch Kommas, Leerzeichen oder Zeilenumbrüche voneinander trennen.
4. Fügen Sie eine oder mehrere der von Ihnen verwalteten Zugriffsoptionen hinzu. Sie müssen mindestens eine Zugriffsoption zuweisen und die Einstellungen für den Benutzer in jeder zugewiesenen Zugriffsoption konfigurieren. Für alle weiteren Zugriffsoptionen, die Sie nicht hinzufügen und konfigurieren, wird der Standardwert *Kein Zugriff* zugewiesen. Abhängig von den Zugriffsoptionen, zu deren Verwaltung Sie berechtigt sind, können Ihnen die folgenden Optionen angezeigt werden: **Durch Identität und Zugriff aktivierte Services**, **Cloud Foundry-Zugriff**, **Infrastructure-Zugriff**. Weitere Informationen finden Sie unter [Benutzerzugriff zuweisen](/docs/iam/iamuserinv.html#assignaccess).

Wenn Sie entscheiden, dass ein Benutzer keinen Zugriff benötigt, können Sie eine Einladung für beliebige Benutzer abbrechen, die mit dem Status **Verarbeitung läuft** (Processing) oder **Anstehend** (Pending) in der Spalte **Status** angezeigt werden. Wenn ein eingeladener Benutzer keine Einladung empfangen hat, können Sie die Einladung an jeden Benutzer mit dem Status **Anstehend** erneut senden.

Wenn Sie über die CLI Benutzer einladen möchten, verwenden Sie den Befehl [bluemix iam account-user-invite](/docs/cli/reference/bluemix_cli/bx_cli.html#bluemix_iam_account_user_invite).

## Benutzerzugriff zuweisen
{: #assignaccess}

Bei der Einladung weisen Sie den Benutzern Zugriffsrechte, Cloud Foundry-Rollen und -Richtlinien sowie Infrastrukturberechtigungen zu. Abhängig von den Zugriffsoptionen, zu deren Verwaltung Sie berechtigt sind, können Sie Benutzer aus dem gesamten Konto, der gesamten Organisation, dem gesamten Bereich oder der gesamten Serviceinstanz einladen und mit Zugriffsrechten ausstatten. In den folgenden Abschnitten werden die drei Arten von Zugriff beschrieben, die einem eingeladenen Benutzer zugewiesen werden können.

### Durch Identität und Zugriff aktivierte Services

Sie können eine einzelne Servicerichtlinie zuweisen, wenn Sie einen neuen Benutzer einladen. Sobald der Benutzer die Einladung angenommen hat, können Sie zusätzliche Servicerichtlinien hinzufügen. Detaillierte Informationen zur Bearbeitung von Richtlinien zum Hinzufügen zusätzlicher Rollen und Servicerichtlinien oder zum Entfernen einer Richtlinie für einen Benutzer finden Sie in [Identitäts- und zugriffsaktivierte Servicezugriffsrichtlinien](/docs/iam/iamusermanage.html#iammanidaccser).

**Hinweis:** Abhängig von dem Service, den Sie bei der Zuweisung der Richtlinie ausgewählt haben, werden möglicherweise nicht alle in den folgenden Arbeitsschritten beschriebenen Felder angezeigt.

1. Erweitern Sie in der Anzeige **Benutzer einladen** den Abschnitt **Durch Identität und Zugriff aktivierte Services**.
2. Wählen Sie einen Service aus.
3. Wählen Sie **Alle aktuellen Regionen** oder eine bestimmte Region aus, wenn Sie vom System dazu aufgefordert werden. 
**Hinweis:** Nicht alle Services erfordern die Auswahl einer Region.
4. Wählen Sie **Alle aktuellen Serviceinstanzen** oder eine bestimmte Serviceinstanz aus.
5. Abhängig vom ausgewählten Service können die folgenden Felder angezeigt werden. Wenn Sie für diese Felder keine Werte eingeben, wird die Richtlinie nicht auf der Bucketebene, sondern auf der Serviceinstanzebene zugewiesen. 
    * **Ressourcentyp**: Geben Sie **Bucket** ein.
    * **Ressource**: Geben Sie den Namen des Buckets ein.
6. Wählen Sie eine Rolle aus, um den Zugriffsbereich für die Richtlinie zu definieren.
7. Optional: Wählen Sie **Rolle hinzufügen** aus, um eine weitere Rolle für die Richtlinie anzugeben.


Weitere Informationen zu den Rollen beim Festlegen von Servicerichtlinien finden Sie unter [Richtlinien und Rollen für Identity and Access Management](/docs/iam/users_roles.html#iamusermanpol).

### Cloud Foundry-Zugriff

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

**Hinweis:** Sie können eine Cloud Foundry-Rolle mithilfe der Befehlszeile [bluemix iam account-user-invite](/docs/cli/reference/bluemix_cli/bx_cli.html#bluemix_iam_account_user_invite) hinzufügen, müssen jedoch die Benutzerschnittstelle auch zur Erteilung anderer Zugriffsrechte oder Berechtigungen verwenden.

### Infrastructure-Zugriff

Die tatsächlichen zugewiesenen Berechtigungen werden automatisch auf die Untergruppe von Berechtigungen eingeschränkt, die Sie haben. Weitere Informationen zu den Berechtigungen und welche Aktionen der Benutzer mit jeder dieser Berechtigungen ausführen kann, finden Sie unter [Infrastructure-Berechtigungen](/docs/iam/users_roles.html#infrapermissions).

1. Erweitern Sie in der Anzeige **Benutzer einladen** den Abschnitt **Infrastructure-Zugriff**.
2. Wählen Sie eine Berechtigung aus, um den Zugriffsbereich zu definieren.

Informationen zum Konfigurieren des Zugriffs für Benutzer, nachdem diese zu Ihrem Konto hinzugefügt wurden, finden Sie unter [Benutzer und Benutzerzugriff verwalten](/docs/iam/iamusermanage.html).
