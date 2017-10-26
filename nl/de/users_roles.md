---

copyright:

  years: 2015, 2016

lastupdated: "2017-09-29"

---

{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:screen: .screen}
{:new_window: target="_blank"}

# Benutzerrollen und Berechtigungen
{: #userroles}

Sie können Benutzer auf der Seite **Benutzer** Ihres Kontos innerhalb der {{site.data.keyword.Bluemix_notm}}-Plattform und in den Infrastrukturservices verwalten. Um auf die Seite 'Benutzer' zuzugreifen, klicken Sie im {{site.data.keyword.Bluemix_notm}}-Menü auf **Verwalten** &gt; **Konto** &gt; **Benutzer**. Kontoeigner können alle Operationen zum Verwalten von Benutzern, Berechtigungen, Organisationen und Bereichen ausführen. Cloud Foundry-Organisationsmanager und -Bereichsmanager verfügen außerdem über Zugriff auf die Verwaltungsfunktion für die Berechtigungen von Benutzern, die zu den einzelnen Organisationen und Bereichen hinzugefügt wurden, die von diesen Managern verwaltet werden.
{:shortdesc}

Wenn Sie ein Benutzer sind, der zum Konto einer anderen Person hinzugefügt wurde, und Sie Ihre zugeordneten Rollen und Berechtigungen anzeigen möchten, wechseln Sie zu **Verwalten** &gt; **Sicherheit** &gt; **Identität & Zugriff** &gt; **Benutzer** und klicken Sie auf Ihren Namen.

## Kontorollen
{: #userrolesinfo}

Auf Kontoebene gibt es zwei Rollen, die den Zugriff auf andere Kontoverwaltungsfunktionen ermöglichen:

| Kontorolle | Berechtigungen |
|----------------|---------|
|Eigner | Ein Eigner für das Konto verfügt über Zugriff auf sein Profil, auf Benutzer, die Rechnungsinformationen, die Informationen zu Ausgaben und das Nutzungsdashboard. Auf der Seite 'Benutzer' kann der Eigner neue Benutzer einladen und Rollen anpassen. Der Eigner kann auch Werbeguthaben hinzufügen, das Abrechnungslimit festlegen oder ändern, den Servicezugriff festlegen und Organisationen und Bereiche verwalten. |
|Mitglied | Ein Mitglied hat Zugriff auf sein Profil, die Seite 'Benutzer', auf der die aktiven Benutzer im Konto angezeigt werden, und auf Limits für Kontoguthaben und Abrechnung im {{site.data.keyword.Bluemix_notm}}-Header.  |
{:caption="Tabelle 1. Kontorollen und Berechtigungen" caption-side="top"}

Alle neuen Benutzer werden als Mitglied des Kontos hinzugefügt. Sie können Organisations- und Bereichsrollen für eingeladene Personen zuordnen, um bestimmte Ansichten und Berechtigungen in {{site.data.keyword.Bluemix_notm}} zu aktivieren. Sobald die eingeladenen Personen die Einladung annehmen und an {{site.data.keyword.Bluemix_notm}} teilnehmen, können Sie ihre Rollen auf der Seite 'Benutzer' bearbeiten.

## Cloud Foundry-Rollen
{: #cfroles}

Cloud Foundry-Rollen enthalten die Zugriffsberechtigungen für Organisationen und Bereiche, die im Konto definiert sind. Cloud Foundry-Rollen aktivieren keine Benutzerberechtigungen zum Ausführen von Aktionen im Kontext eines Service. Die folgenden Rollen können auf Organisationsebene hinzugefügt werden:

| Organisationsrolle | Berechtigungen |
|-------------------|-------------|
|Manager | Organisationsmanager können Bereiche innerhalb der Organisation erstellen, anzeigen, bearbeiten oder löschen, die Nutzung und das Kontingent der Organisation anzeigen, Benutzer zur Organisation einladen, steuern, wer Zugriff auf die Organisation und die Rollen in der Organisation hat, und die angepassten Domänen für die Organisation verwalten. |
|Abrechnungsmanager | Abrechnungsmanager können Informationen zur Laufzeit- und Servicenutzung für die Organisation auf der Seite 'Nutzungsdashboard' anzeigen.  |
|Auditor | Organisationsauditoren können Anwendungs- und Serviceinhalte in der Organisation anzeigen. Auditoren können die Benutzer in der Organisation und deren zugeordnete Rollen sowie das Kontingent für die Organisation auch anzeigen. |
{:caption="Tabelle 2. Organisationsrollen und Berechtigungen" caption-side="top"}

Die folgenden Rollen können auf Bereichsebene zugeordnet werden:

| Bereichsrolle | Berechtigungen |
|------------|-------------|
|Manager | Bereichsmanager können vorhandene Benutzer hinzufügen und Rollen innerhalb des Bereichs verwalten. Der Bereichsmanager kann auch die Anzahl der Instanzen, die Servicebindungen und die Nutzung der Ressource für jede Anwendung im Bereich anzeigen. |
|Entwickler | Bereichsentwickler können Anwendungen und Services innerhalb des Bereichs erstellen, löschen und verwalten. Einige der Verwaltungstasks umfassen das Bereitstellen, Starten oder Stoppen von Apps, das Umbenennen oder Löschen von Apps, das Umbenennen eines Bereichs, das Binden oder Aufheben der Bindung eines Service an eine Anwendung, das Anzeigen der Anzahl der Instanzen, Servicebindungen und der Ressourcennutzung für jede Anwendung im Bereich. Darüber hinaus kann der Bereichsentwickler eine interne oder externe URL einer Anwendung im Bereich zuordnen.   |
|Auditor | Bereichsauditoren haben Lesezugriff auf alle Informationen zu Bereichen, beispielsweise auf Informationen zur Anzahl der Instanzen, zu Servicebindungen und zur Ressourcennutzung für jede Anwendung im Bereich. |
{:caption="Tabelle 3. Bereichsrollen und Berechtigungen" caption-side="top"}

**Hinweis:** Benutzer, denen eine Bereichsmanager- oder Bereichsentwicklerrolle zugeordnet wurde, können auf die Umgebungsvariable VCAP_SERVICES zugreifen. Ein Benutzer, dem die Auditorrolle zugeordnet wurde, kann jedoch nicht auf VCAP_SERVICES zugreifen.

## Richtlinien und Rollen für Identity and Access Management
{: #iamusermanpol}

Kontoeignern wird automatisch die Administratorrolle für das Konto für die Identitäts- und Zugriffsverwaltung zugewiesen, mit der Servicerichtlinien zugewiesen und verwaltet werden können. Servicerichtlinien können einzelnen Benutzern oder Service-IDs zugewiesen werden. Die zugewiesene Richtlinie kann den Zugriff für einen gesamten Service oder auf Ebene einzelner Instanzen definieren. 

### Servicerichtlinien

Eine Richtlinie weist einem Benutzer oder einer Service-ID einzelne oder mehrere Rollen für eine Ressourcengruppe zu. Dazu wird eine Kombination von Attributen zur Definition der betreffenden Ressourcengruppe verwendet. Wenn Sie eine Richtlinie einem Benutzer zuweisen, geben Sie zuerst den Service an. Anschließend können Sie eine oder mehrere Rollen auswählen, die zugewiesen werden sollen. Abhängig von dem Service, den Sie auswählen, können zusätzliche Konfigurationsoptionen verfügbar sein.

Sie können Richtlinien zuweisen und verwalten, wenn Sie die entsprechende Rolle haben. In der folgenden Tabelle werden die Richtlinienmanagementtasks und die jeweils erforderliche Rolle aufgeführt.

| Aktion | Erforderliche Rolle |
|----------|---------|
| Richtlinien für ein Konto für alle Services und Instanzen erstellen | Kontoadministrator |
| Richtlinie für einen Service in einem Konto erstellen | Kontoadministrator oder Administrator für den Service im Konto |
| Serviceinstanz erstellen | Kontoadministrator oder Administrator oder Editor für den Service im Konto |
| Richtlinie für eine Serviceinstanz erstellen | Kontoadministrator oder Administrator für den Service im Konto oder Administrator für die Serviceinstanz |
{: caption="Tabelle 4. Verwaltungstasks zum Verwalten von Richtlinien für durch Identität und Zugriff aktivierte Services" caption-side="top"}

### Servicerichtlinienrollen
{: #iamusermanrol}

Rollen sind Sammlungen von Aktionen. Die Aktionen, die diesen Rollen zugeordnet sind, sind je nach Service unterschiedlich. Weitere Informationen darüber, welche Arten von Aktionen jede Rolle ermöglicht, finden Sie in der Dokumentation für den ausgewählten Service.

Neben den Beschreibungen der Rollen, die in der Konsole verfügbar sind, werden in der folgenden Tabelle Beispiele für einige der Tasks aufgeführt, die Benutzer, denen eine Rolle zugewiesen ist, für den {{site.data.keyword.containershort_notm}} ausführen können.  

| Rolle | Beschreibung von Aktionen | Beispielaktionen|
|:-----------------|:-----------------|:-----------------|
| Viewer (Anzeigeberechtigter) | Führt Aktionen aus, die den Status nicht ändern; Aktionen im Lesezugriff. | <ul><li>Cluster auflisten</li><li>Details für einen Cluster anzeigen</li></ul>|
| Editor (Bearbeiter) | Führt Aktionen aus, die den Status ändern und die Unterressourcen erstellen oder löschen. |<ul><li>Service an einen Cluster binden</li><li>Webhook erstellen</li></ul> |
| Operator (Bediener) | Führt Aktionen aus, die zum Konfigurieren und Betreiben von Ressourcen erforderlich sind. | <ul><li>Workerknoten hinzufügen oder entfernen</li><li>Workerknoten neu starten oder erneut laden</li><li>Service an einen Cluster binden</li></ul> |
| Administrator | Führt alle Aktionen aus, einschließlich der Möglichkeit, die Zugriffssteuerung zu verwalten. |<ul><li>Cluster entfernen</li><li>Cluster erstellen</li><li>Benutzerzugriffsrichtlinien aktualisieren</li><li>Alle Aktionen, die ein Anzeigeberechtigter, Bearbeiter und Bediener ausführen kann</li></ul>|
{: caption="Tabelle 5. Beispiele für Benutzerrollen und Aktionen" caption-side="top"}



## Infrastructure-Berechtigungen
{: #infrapermissions}

Sie können bei der Einladung eines Benutzers die folgenden Ausgangsberechtigungen festlegen:

| Festgelegte Berechtigung | Beschreibung von Aktionen |
|---------------------------|------------------------|
|Nur anzeigen | Benutzer mit dieser Berechtigung können Elemente im System nur anzeigen.|
|Basisbenutzer | Benutzer mit dieser Berechtigung können Basisaktionen im System ausführen, wie zum Beispiel Tickets hinzufügen und Geräte verwalten. |
|Superuser | Benutzer mit dieser Berechtigung können alle verfügbaren Aktionen im System ausführen. |
{:caption="Tabelle 6. Infrastructure-Berechtigung" caption-side="top"}

Weitere Berechtigungen können festgelegt werden, nachdem der Benutzer die Einladung akzeptiert hat. Die Ausgangsberechtigung, die zum Zeitpunkt der Einladung festgelegt wird, erteilt keinen Zugriff auf Geräte. Die Zugriffsberechtigungen für Geräte müssen im Steuerungsportal erteilt werden, nachdem der Benutzer die Einladung akzeptiert hat.
