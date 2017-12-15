---

copyright:

  years: 2015, 2017
lastupdated: "2017-11-16"

---

{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:screen: .screen}
{:new_window: target="_blank"}
{:tip: .tip}

# Benutzer einladen und Benutzern Zugriff zuweisen
{: #iamuserinv}

Zum Einladen von Benutzern und Verwalten ausstehender Benutzer müssen Sie entweder ein Kontoeigner oder ein Organisationsmanager sein oder über die Infrastructure-Berechtigungen zum Hinzufügen von Benutzern verfügen. Sie können Benutzer einladen, Einladungen abbrechen und anstehende Einladungen erneut an eingeladene Benutzer senden. Darüber hinaus können Sie einen einzelnen Benutzer oder mehrere Benutzer gleichzeitig einladen.  
{:shortdesc}

## Benutzer einladen

Führen Sie die folgenden Schritte aus, um Benutzer einzuladen oder Einladungen in Ihrem Konto zu verwalten: 

1. Klicken Sie in der Menüleiste auf **Verwalten** &gt; **Sicherheit** &gt; **Identität und Zugriff** und dann auf **Benutzer**. Die Seite 'Benutzer' enthält eine Liste der Benutzer mit den zugehörigen E-Mail-Adressen und dem aktuellen Status des aktuell ausgewählten Kontos.
2. Klicken Sie auf **Benutzer einladen**.
3. Geben Sie die E-Mail-Adresse des Benutzers an. Wenn Sie mehrere Benutzer mit einer einzigen Einladung einladen, dann wird diesen Benutzern der gleiche Zugriff erteilt.
4. Fügen Sie eine oder mehrere der von Ihnen verwalteten Zugriffsoptionen hinzu. Sie müssen mindestens eine Zugriffsoption zuweisen. Für alle weiteren Zugriffsoptionen, die Sie nicht hinzufügen und konfigurieren, wird der Standardwert *Kein Zugriff* zugewiesen. Abhängig von den Optionen, zu deren Verwaltung Sie berechtigt sind, zeigt das System eine der folgenden Zugriffsoptionen oder alle folgenden Zugriffsoptionen an: **Services**, **Cloud Foundry-Zugriff**, **{{site.data.keyword.Bluemix_notm}}-Infrastructure-Zugriff**. Weitere Informationen zu diesem Thema erhalten Sie in [Benutzerzugriff zuweisen](/docs/iam/iamuserinv.html#assignaccess).

Wenn Sie entscheiden, dass ein Benutzer keinen Zugriff benötigt, können Sie eine Einladung für beliebige Benutzer abbrechen, die mit dem Status **Verarbeitung läuft** (Processing) oder **Anstehend** (Pending) in der Spalte **Status** angezeigt werden. Wenn ein eingeladener Benutzer keine Einladung empfangen hat, können Sie die Einladung an jeden Benutzer mit dem Status **Anstehend** erneut senden.

Wenn Sie Benutzer über die CLI einladen möchten, verwenden Sie den Befehl [bluemix iam account-user-invite](/docs/cli/reference/bluemix_cli/bx_cli.html#bluemix_iam_account_user_invite).
{: tip}

## Benutzerzugriff zuweisen
{: #assignaccess}

Bei der Einladung weisen Sie den Benutzern Zugriffsberechtigungen zu. Dazu führen Sie eine Zuweisung von Cloud IAM-Richtlinien, Cloud Foundry-Zugriffsberechtigungen und Infrastructure-Berechtigungen durch. Abhängig von den Zugriffsoptionen, zu deren Verwaltung Sie berechtigt sind, können Sie Benutzer aus dem gesamten Konto, den Ressourcengruppen, Organisationen, Bereichen, Serviceinstanzen und der Infrastruktur einladen und diesen Benutzern Zugriffsberechtigungen erteilen. In den folgenden Abschnitten werden die drei Arten von Zugriff beschrieben, die einem eingeladenen Benutzer zugewiesen werden können.

### Services

Sie können die Zugriffsberechtigungen erteilen, indem Sie eine Cloud IAM-Ausgangszugriffsrichtlinie erstellen, wenn Sie einen neuen Benutzer einladen. In diesem Abschnitt können Sie einem Benutzer den Zugriff auf die Services in einer Ressourcengruppe mit Zugriff auf die Ressourcengruppe oder eine einzelne Ressource im Konto erteilen. Nachdem der Benutzer die Einladung akzeptiert hat, können Sie weitere Zugriffsberechtigungen zuweisen. Detaillierte Informationen zum Bearbeiten von Richtlinien für das Hinzufügen zusätzlicher Rollen, zum Zuweisen weiterer Zugriffsberechtigungen oder zum Entfernen einer Richtlinie für einen Benutzer finden Sie in [IAM-Zugriff verwalten](/docs/iam/mngiam.html#iammanidaccser).

**Hinweis:** Abhängig von dem Service, den Sie bei der Zuweisung der Richtlinie ausgewählt haben, werden möglicherweise nicht alle in den folgenden Arbeitsschritten beschriebenen Felder angezeigt.

#### Zugriff auf Ressourcengruppen

Sie können Zugriff auf alle Services in einer Ressourcengruppe oder aber auf einen einzelnen Servicetyp in einer Ressourcengruppe erteilen.

1. Erweitern Sie in der Anzeige **Benutzer einladen** den Abschnitt **Services**.
2. Wählen Sie diese Option aus, um den Zugriff auf die Ressourcen in einer **Ressourcengruppe** zuzuweisen.
3. Wählen Sie eine Ressourcengruppe aus.
4. Wählen Sie eine Rolle für das Feld **Zugriff für eine Ressourcengruppe zuweisen** aus, um dem Benutzer die Anzeige der Ressourcengruppe im Dashboard, das Bearbeiten des Ressourcengruppennamens oder das Verwalten des Benutzerzugriffs auf die Gruppe zu ermöglichen. Sie können **Kein Zugriff** auswählen, wenn der Benutzer ausschließlich Zugriff auf die Ressource erhalten soll, die Sie angeben, nicht jedoch auf die Gruppe, in der die Ressource enthalten ist.
5. Wählen Sie einen Service in der Ressourcengruppe aus, oder wählen Sie aus, dass der Zugriff auf alle Services in der ausgewählten Gruppe bereitgestellt werden soll. 
6. Wählen Sie eine beliebige Zusammenstellung von Rollen aus, um die gewünschten Zugriffsberechtigungen zuzuweisen. Dieser Zugriff gilt nur für die Ressourcen, die Sie für die Richtlinie ausgewählt haben. Der Zugriff auf den Container selbst, der die Ressourcengruppe darstellt, wird hingegen nicht erteilt. 


#### Ressourcenzugriff

Sie können Zugriffsberechtigungen für eine einzelne Ressource innerhalb Ihres Kontos bis auf die Instanzebene zuweisen.

1. Erweitern Sie in der Anzeige **Benutzer einladen** den Abschnitt **Services**.
2. Wählen Sie die Option aus, um den Zugriff auf eine **Ressource** zuzuweisen.
3. Wählen Sie einen Service aus.
4. Wählen Sie **Alle aktuellen Regionen** oder eine bestimmte Region aus, wenn Sie vom System dazu aufgefordert werden. 
5. Wählen Sie **Alle aktuellen Serviceinstanzen** oder eine bestimmte Serviceinstanz aus.
6. Abhängig vom ausgewählten Service können die folgenden Felder angezeigt werden. Wenn Sie für diese Felder keine Werte eingeben, wird die Richtlinie nicht auf der Bucketebene, sondern auf der Serviceinstanzebene zugewiesen. 
    * **Ressourcentyp**: Geben Sie **Bucket** ein.
    * **Ressourcen-ID**: Geben Sie den Namen des Buckets ein.
7. Wählen Sie eine beliebige Zusammenstellung von Rollen aus, um die gewünschten Zugriffsberechtigungen zuzuweisen. 

Weiterführende Informationen zu den Rollen bei der Zuweisung von Zugriffsberechtigungen finden Sie im Abschnitt zum [IAM-Zugriff](/docs/iam/users_roles.html#iamusermanrol).

### Cloud Foundry-Zugriff

Wenn Sie neue Benutzer einladen, können Sie den Benutzer zu einer Organisation im Konto hinzuzufügen. Wenn Sie den Benutzer zu einer Organisation hinzufügen, können Sie ihm eine Organisationsrolle zuweisen. Anschließend können Sie dem eingeladenen Benutzer Zugriff auf einen, mehrere oder alle Bereiche in der ausgewählten Organisation mit einer zugewiesenen Bereichsrolle erteilen.

1. Erweitern Sie in der Anzeige **Benutzer einladen** den Abschnitt **Cloud Foundry-Zugriff**.
2. Wählen Sie eine Organisation aus, zu der der Benutzer hinzugefügt werden soll.
3. Wählen Sie eine Organisationsrolle aus, um die Zugriffsebene für die ausgewählte Organisation zu definieren.
4. Optional: Wählen Sie **Organisationsrolle hinzufügen** aus, um eine zusätzliche Rolle anzugeben.
5. Wählen Sie **Alle aktuellen Regionen** oder eine bestimmte Region aus.
6. Wählen Sie **Alle aktuellen Bereiche** oder einen bestimmten Bereich aus.
7. Wählen Sie eine Bereichsrolle aus, um die Zugriffsebene für die ausgewählten Bereiche zu definieren.
8. Optional: Wählen Sie **Bereichsrolle hinzufügen** aus, um eine zusätzliche Rolle anzugeben.

Weiterführende Informationen zu den Rollen finden Sie in [Cloud Foundry-Rollen](/docs/iam/cfaccess.html#cfroles).

Sie können eine Cloud Foundry-Rolle mithilfe des CLI-Befehls [bluemix iam account-user-invite](/docs/cli/reference/bluemix_cli/bx_cli.html#bluemix_iam_account_user_invite) hinzufügen, müssen jedoch die Benutzerschnittstelle auch zur Erteilung anderer Zugriffsrechte oder Berechtigungen verwenden.
{: tip}

### Zugriff auf Infrastruktur für {{site.data.keyword.BluSoftlayer_notm}}

Die zugewiesenen Berechtigungen werden automatisch auf die Untergruppe von Berechtigungen eingeschränkt, die Sie haben. Weitere Informationen zu den Berechtigungssets finden Sie in [Infrastructure-Berechtigungen](/docs/iam/users_roles.html#infrapermissions).

1. Erweitern Sie in der Anzeige **Benutzer einladen** den Abschnitt **Infrastructure-Zugriff**.
2. Wählen Sie ein Berechtigungsset aus, um den Zugriffsbereich zu definieren.

Der Zugriff auf Geräte wird separat erteilt, nachdem der Benutzer hinzugefügt wurde. Dazu navigieren Sie zur Option **Infrastruktur** an der Konsole.
{: tip}

Informationen zum Konfigurieren des Zugriffs für Benutzer, nachdem sie zu Ihrem Konto hinzugefügt wurden, finden Sie in [Infrastructure-Zugriff verwalten](/docs/iam/mnginfra.html#managing-infrastructure-access).

## Reine VPN-Benutzer hinzufügen

Als Kontoeigner eines verknüpften Kontos können Sie reine VPN-Benutzer hinzufügen.

1. Klicken Sie auf das Menüsymbol ![Menüsymbol](../icons/icon_hamburger.svg) und wählen Sie dann **Infrastruktur** aus.
2. Rufen Sie **Konto** &gt; **Benutzer** auf.
3. Klicken Sie auf die Option zum **Hinzufügen reiner VPN-Benutzer**.
4. Geben Sie die personenbezogenen Daten des Benutzers ein. 
5. Klicken Sie auf **Benutzer hinzufügen**.
6. Legen Sie die Portalberechtigungen für den Benutzer fest.
7. Klicken Sie auf die Option zum **Hinzufügen von Portalberechtigungen**, um die Berechtigungen zu speichern.
8. Legen Sie den Gerätezugriff für den Benutzer fest.
9. Klicken Sie auf die Option zum **Aktualisieren des Gerätezugriffs**, um die Daten zu speichern und den Zugriff zuzuweisen.
