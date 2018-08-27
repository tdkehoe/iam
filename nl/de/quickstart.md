---

copyright:

  years: 2017, 2018

lastupdated: "2018-08-21"

---

{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:screen: .screen}
{:new_window: target="_blank"}

# Lernprogramm 'Einführung'
{: #getstarted}

Dieses Lernprogramm soll Sie dabei unterstützen, sich schnell mit IBM Cloud Identity and Access Management (IAM) vertraut zu machen. Dazu werden Benutzer zu Ihrem Konto eingeladen und Sie werden diesen Benutzern Cloud IAM-Zugriffsberechtigungen zuweisen.

Dieses Lernprogramm bezieht sich ausschließlich auf [Ressourcen](/docs/resources/acct_resources.html#resource), die mit IAM verwaltet werden. Für Services, die die Erstellung von Cloud IAM-Richtlinien zur Verwaltung des Zugriffs nicht unterstützen, können Sie den [Cloud Foundry-Zugriff](/docs/iam/cfaccess.html#cfaccess) verwenden.


## Schritt 1. Benutzer einladen und Anfangszugriffsberechtigungen zuweisen

Sie können einzelne oder auch mehrere Benutzer einladen und die Richtlinie für die Anfangszugriffsberechtigungen der eingeladenen Benutzer festlegen. Wenn Sie in einer einzigen Einladung mehrere Benutzer einladen, dann werden diesen Benutzern die gleichen Zugriffsberechtigungen zugewiesen. Im Abschnitt **Zugriff** der Seite 'Benutzer einladen' werden nur die Abschnitte angezeigt, zu deren Zuweisung sie berechtigt sind.

Als Kontoeigner können Sie den von Ihnen eingeladenen Benutzern im Abschnitt 'Services' Cloud IAM-Rollen zuweisen. Sie können dabei den Zugriff auf alle Ressourcen einer Ressourcengruppe, alle Ressourcen für einen bestimmten Service in einer Ressourcengruppe, alle Services mit aktiviertem Identity and Access Management im Konto oder für eine einzelne Ressource in der Anfangsrichtlinie bereitstellen, die Sie in der Einladung zuweisen wollen:

1. Rufen Sie **Verwalten** &gt; **Sicherheit** &gt; **Identität und Zugriff** auf und wählen Sie dann **Benutzer** aus.
2. Klicken Sie auf **Benutzer einladen**.
3. Geben Sie die E-Mail-Adresse der Benutzer an, die eingeladen werden sollen.
4. Erweitern Sie im Abschnitt **Zugriff** die Ansicht der Option **Services**.
5. Wählen Sie aus, dass einer **Ressource** oder bestimmten Ressourcen einer **Ressourcengruppe** Zugriff erteilt werden soll.
6. Abhängig von der getroffenen Auswahl müssen Sie dann den Eingabeaufforderungen folgen, um den Zugriff auf eine bestimmte Serviceinstanz, alle Services mit aktiviertem Identity and Access Management, alle Ressourcen einer Ressourcengruppe oder auf einen bestimmten Service in der ausgewählten Ressourcengruppe anzugeben. Wenn Sie die Option für die Ressourcengruppe ausgewählt haben, dann können Sie dem Benutzer auch die Zugriffsberechtigungen zum Anzeigen, Bearbeiten oder Verwalten des Zugriffs auf die Ressourcengruppe erteilen, indem Sie eine Rolle für den Zugriff auf die Ressourcengruppe auswählen.
7. Wenn Sie über die erforderlichen Berechtigungen verfügen, dann können Sie in der Einladung auch den Cloud Foundry-Zugriff oder den Infrastructure-Zugriff erteilen.
8. Klicken Sie auf **Benutzer einladen**.

Weitere Informationen finden Sie in [Benutzer einladen und Benutzern Zugriff zuweisen](/docs/iam/iamuserinv.html#iamuserinv).

## Schritt 2. Zugriffsgruppen erstellen

Um die Zuweisung von Zugriff für Benutzer in Ihrem Konto zu optimieren, können Sie Zugriffsgruppen erstellen, die aus von Ihnen ausgewählten Benutzern und Service-IDs bestehen. Anschließend können Sie den Zugriff ohne großen Aufwand zuweisen, indem Sie eine einzige Richtlinie für die gesamte Gruppe definieren.

### Ihre Gruppen einrichten

Führen Sie die folgenden Schritte aus, um eine Zugriffsgruppe zu erstellen:

1. Klicken Sie in der Menüleiste auf **Verwalten** &gt; **Sicherheit** &gt; **Identität und Zugriff** und wählen Sie dann **Zugriffsgruppen** aus.
2. Klicken Sie auf **Erstellen**.
3. Geben Sie einen Namen und eine optionale Beschreibung für Ihre Gruppe ein und klicken Sie auf **Erstellen**.

Fahren Sie danach mit der Einrichtung Ihrer Gruppe fort, indem Sie Benutzer oder Service-IDs hinzufügen:

1. Wählen Sie den Namen der Gruppe aus, zu der Sie diese hinzufügen wollen.
2. Klicken Sie auf **Benutzer hinzufügen**.
3. Wählen Sie die Benutzer, die Sie hinzufügen möchten, in der Liste aus und klicken Sie auf **Zu Gruppe hinzufügen**.
4. Wenn Sie Service-IDs zu der Gruppe hinzufügen wollen, klicken Sie auf **Service-IDs** und anschließend auf **Service-ID hinzufügen**.
5. Wählen Sie die IDs, die Sie hinzufügen möchten, in der Liste aus und klicken Sie auf **Zu Gruppe hinzufügen**.

### Zugriff auf Ihre Gruppen zuweisen

Nachdem Sie Ihre Gruppen erstellt haben, können Sie mit einer einzigen Richtlinie allen Entitäten in der Gruppe den Zugriff zuweisen.

1. Klicken Sie in der Menüleiste auf **Verwalten** &gt; **Sicherheit** &gt; **Identität und Zugriff** und wählen Sie dann **Zugriffsgruppen** aus.
2. Wählen Sie den Namen der Gruppe aus, für die Sie Zugriff zuweisen wollen.
3. Klicken Sie auf **Zugriff zuweisen**, um eine Richtlinie einzurichten, die den Zugriff auf eine einzelne Ressource im Konto oder auf alle Ressourcen in einer Ressourcengruppe zuweist.

Durch die Organisation von Ressourcen in Ressourcengruppen und Benutzer in Zugriffsgruppen können Sie einer Gruppe von Benutzern mit einer einzigen Richtlinie den Zugriff auf eine Gruppe von Ressourcen zuweisen. Dies verringert die Gesamtzahl der Richtlinien, die Sie verwalten müssen.
{: tip}


## Schritt 3. Zugriff für vorhandene Benutzer verwalten

Nachdem Sie Benutzer eingeladen, den Erstzugriff zugewiesen und Ihre Zugriffsgruppen erstellt haben, können Sie weiterführenden Zugriff zuweisen oder die Anfangszugriffsberechtigungen bearbeiten, die Sie zugewiesen haben. Auf diese Weise können Sie sicherstellen, dass alle Benutzer und Gruppen in Ihrem Konto die gewünschte Zugriffsebene erhalten.

### Neue Zugriffsberechtigungen zuweisen

Sie können einem Benutzer Zugriffsberechtigungen für eine Ressourcengruppe oder für eine einzelne Ressource zuweisen.

1. Klicken Sie in der Menüleiste auf **Verwalten** &gt; **Sicherheit** &gt; **Identität und Zugriff** und wählen Sie dann **Benutzer** aus.
2. Klicken Sie auf den Namen des Benutzers, dem Sie Zugriffsberechtigungen zuweisen möchten.
3. Klicken Sie auf **Zugriff zuweisen**.
4. Wählen Sie aus, wie der Zugriff zugewiesen werden soll:
    * Wählen Sie **Zugriff in einer Ressourcengruppe zuweisen** aus, um den Zugriff auf alle Ressourcen in einer Gruppe oder nur auf die Ressourcen für einen bestimmten Service in einer Gruppe zuzuweisen. Sie können dem Benutzer auch die Zugriffsberechtigungen zum Anzeigen, Bearbeiten oder Verwalten des Zugriffs auf die Ressourcengruppe erteilen, indem Sie eine Rolle für den Zugriff auf die Ressourcengruppe auswählen. Wählen Sie **Kein Zugriff** aus, wenn der Benutzer lediglich Zugriff auf die angegebene Ressource und nicht auf die Gruppe erhalten soll, in der sich die Ressource befindet.
    * Wählen Sie **Zugriff auf Ressourcen zuweisen** aus, um den Zugriff auf alle Ressourcen mit aktiviertem Identity and Access Management innerhalb des Kontos, alle Ressourcen eines bestimmten Service innerhalb des Kontos, auf eine einzelne Instanz oder eine einzelne Ressource innerhalb einer bestimmten Serviceinstanz zuzuweisen.
5. Wählen Sie eine beliebige Zusammenstellung von Rollen aus, um den Geltungsbereich der Zugriffsberechtigungen zu definieren. Weitere Informationen zu diesem Thema finden Sie im Abschnitt zu den [Cloud IAM-Rollen](/docs/iam/users_roles.html#iamusermanrol).
6. Klicken Sie auf **Zuweisen**.


### Vorhandene Zugriffsberechtigungen bearbeiten

Sie können die vorhandenen Zugriffsberechtigungen aktualisieren, indem Sie die zugewiesenen Rollen für einen Benutzer bearbeiten.

1. Klicken Sie in der Menüleiste auf **Verwalten** &gt; **Sicherheit** &gt; **Identität und Zugriff** und wählen Sie dann **Benutzer** aus.
2. Wählen Sie den Namen des Benutzers aus, dessen Zugriffsberechtigungen bearbeitet werden sollen.
3. Klicken Sie in der Zeile für die Richtlinie, die Sie bearbeiten wollen, im Menü **Aktionen** auf **Richtlinie bearbeiten**.
4. Bearbeiten Sie die Richtlinie, indem Sie die zugewiesenen Rollen aktualisieren.
5. Klicken Sie auf **Speichern**.

Sie können die Zugriffsberechtigungen eines Benutzers entfernen, indem Sie für die Richtlinie, die entfernt werden soll, im Menü **Aktionen** auf die Option **Entfernen** klicken.

## Nächste Schritte

Hier erfahren Sie, welche weiterführenden Schritte Sie mit Cloud IAM ausführen können, indem Sie die Informationen in der Liste der [Cloud IAM-Funktionen](/docs/iam/index.html#features) lesen.
