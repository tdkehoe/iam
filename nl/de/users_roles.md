---

copyright:

  years: 2015, 2016
lastupdated: "2017-05-31"

---

{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:screen: .screen}
{:new_window: target="_blank"}

# Benutzerrollen und Berechtigungen
{: #userroles}

Sie können Benutzer über die {{site.data.keyword.Bluemix_notm}}-Plattform- und {{site.data.keyword.Bluemix_notm}}-Infrastrukturservices auf der Seite **Benutzer** für Ihr Konto verwalten. Um auf die Seite 'Benutzer' zuzugreifen, klicken Sie im {{site.data.keyword.Bluemix_notm}}-Menü auf **Verwalten** &gt; **Konto** &gt; **Benutzer**. Kontoeigner führen alle Operationen für Organisationen und Bereiche aus, einschließlich der Verwaltung von Benutzern und deren zugeordneten Rollen. Organisationsmanager und Bereichsmanager verfügen auch über Zugriff zur Verwaltung von Rollen. 
{:shortdesc}

Wenn Sie ein Benutzer sind, der zum Konto einer anderen Person hinzugefügt wurde, und Sie Ihre zugeordneten Rollen und Berechtigungen anzeigen möchten, wechseln Sie zu **Verwalten** &gt; **Sicherheit** &gt; **Identity & Access** &gt; **Benutzer** und klicken Sie auf Ihren Namen.

## Kontorollen
{: #userrolesinfo}

Auf Kontoebene gibt es zwei Rollen, die den Zugriff auf andere Kontoverwaltungsfunktionen ermöglichen:

| Kontorolle | Berechtigungen |
|----------------|---------|
|Eigner | Ein Eigner für das Konto verfügt über Zugriff auf sein Profil, auf Benutzer, die Rechnungsinformationen, die Informationen zu Ausgaben und das Nutzungsdashboard. Auf der Seite 'Benutzer' kann der Eigner neue Benutzer einladen und Rollen anpassen. Der Eigner kann auch Werbeguthaben hinzufügen, das Abrechnungslimit festlegen oder ändern, den Servicezugriff festlegen und Organisationen und Bereiche verwalten. |
|Mitglied | Ein Mitglied hat Zugriff auf sein Profil, die Seite 'Benutzer', auf der die aktiven Benutzer im Konto angezeigt werden, und auf Limits für Kontoguthaben und Abrechnung im {{site.data.keyword.Bluemix_notm}}-Header.   |
{:caption="Tabelle 1. Kontorollen und Berechtigungen" caption-side="top"}

Alle neuen Benutzer werden als Mitglied des Kontos hinzugefügt. Sie können Organisations- und Bereichsrollen für eingeladene Personen zuordnen, um bestimmte Ansichten und Berechtigungen in {{site.data.keyword.Bluemix_notm}} zu aktivieren. Neue Benutzer, die einer Organisation hinzugefügt wurden (lokale oder dedizierte Umgebungen ausgenommen), erhalten standardmäßig die Rolle des Organisationsauditors. Für einen bestimmten Bereich können Sie eingeladenen Personen die Rollen 'Manager', 'Entwickler' oder 'Auditor' zuordnen. Sobald die eingeladenen Personen die Einladung annehmen und an {{site.data.keyword.Bluemix_notm}} teilnehmen, können Sie ihre Rollen auf der Seite 'Benutzer' bearbeiten.

## Cloud Foundry-Rollen
{: #cfroles}

Cloud Foundry-Rollen enthalten die Zugriffsberechtigungen für Organisationen und Bereiche, die im Konto definiert sind. Cloud Foundry-Rollen aktivieren keine Benutzerberechtigungen zum Ausführen von Aktionen im Kontext eines Service. Die folgenden Rollen können auf Organisationsebene hinzugefügt werden:

| Organisationsrolle | Berechtigungen |
|-------------------|-------------|
|Manager | Organisationsmanager können Bereiche innerhalb der Organisation erstellen, anzeigen, bearbeiten oder löschen, die Nutzung und das Kontingent der Organisation anzeigen, Benutzer zur Organisation einladen, steuern, wer Zugriff auf die Organisation und die Rollen in der Organisation hat, und die angepassten Domänen für die Organisation verwalten. |
|Abrechnungsmanager | Abrechnungsmanager können Informationen zur Laufzeit- und Servicenutzung für die Organisation auf der Seite 'Nutzungsdashboard' anzeigen.  |
|Auditor | Organisationsauditoren können Anwendungs- und Serviceinhalte in der Organisation anzeigen. Auditoren können die Benutzer in der Organisation und deren zugeordnete Rollen sowie das Kontingent für die Organisation auch anzeigen. Außer in lokalen oder dedizierten Umgebungen ist diese Rolle standardmäßig allen eingeladenen Personen zugeordnet. |
{:caption="Tabelle 2. Organisationsrollen und Berechtigungen" caption-side="top"}

Die folgenden Rollen können auf Bereichsebene zugeordnet werden:

| Bereichsrolle | Berechtigungen |
|------------|-------------|
|Manager | Bereichsmanager können vorhandene Benutzer hinzufügen und Rollen innerhalb des Bereichs verwalten. Der Bereichsmanager kann auch die Anzahl der Instanzen, die Servicebindungen und die Nutzung der Ressource für jede Anwendung im Bereich anzeigen. |
|Entwickler | Bereichsentwickler können Anwendungen und Services innerhalb des Bereichs erstellen, löschen und verwalten. Einige der Verwaltungstasks umfassen das Bereitstellen, Starten oder Stoppen von Apps, das Umbenennen oder Löschen von Apps, das Umbenennen eines Bereichs, das Binden oder Aufheben der Bindung eines Service an eine Anwendung, das Anzeigen der Anzahl der Instanzen, Servicebindungen und der Ressourcennutzung für jede Anwendung im Bereich. Darüber hinaus kann der Bereichsentwickler eine interne oder externe URL einer Anwendung im Bereich zuordnen.   |
|Auditor | Bereichsauditoren haben Lesezugriff auf alle Informationen zu Bereichen, beispielsweise auf Informationen zur Anzahl der Instanzen, zu Servicebindungen und zur Ressourcennutzung für jede Anwendung im Bereich. |
{:caption="Tabelle 3. Bereichsrollen und Berechtigungen" caption-side="top"}

**Hinweis**: Benutzer, denen eine Bereichsmanager- oder Bereichsentwicklerrolle zugeordnet wurde, können auf die Umgebungsvariable VCAP_SERVICES zugreifen. Ein Benutzer, dem die Auditorrolle zugeordnet wurde, kann jedoch nicht auf VCAP_SERVICES zugreifen.

## Richtlinien und Rollen für Identity and Access Management
{: #iamusermanpol}

Kontoeignern wird automatisch die Administratorrolle für den Kontozugriff für Identity and Access Managemement zugewiesen, mit der Sie Servicerichtlinien zuweisen und verwalten können. Mit dieser Art der Zugriffssteuerung können Richtlinien pro Service oder Serviceinstanz zugewiesen werden, was wiederum die Einrichtung verschiedener Zugriffsebenen für die Verwaltung von Ressourcen und Benutzern im zugewiesenen Kontext ermöglicht.

### Servicerichtlinien

Eine Richtlinie weist einem Benutzer eine oder mehrere Rollen für eine Gruppe von Ressourcen durch eine Kombination von Attributen zur Definition der betreffenden Gruppe von Ressourcen zu. Wenn Sie eine Richtlinie einem Benutzer zuweisen, geben Sie zuerst den Service an. Anschließend können Sie eine oder mehrere Rollen auswählen, die zugewiesen werden sollen. Abhängig von dem Service, den Sie auswählen, können zusätzliche Konfigurationsoptionen verfügbar sein.

Sie können Richtlinien zuweisen und verwalten, wenn Sie die entsprechende Rolle haben. In der folgenden Tabelle werden die Richtlinienmanagementtasks und die jeweils erforderliche Rolle aufgeführt.

| Aktion | Erforderliche Rolle |
|----------|---------|
| Richtlinien für ein Konto für alle Services und Instanzen erstellen | Administrator für den Kontozugriff |
| Richtlinie für einen Service in einem Konto erstellen | Administrator für den Kontozugriff oder Administrator für den Service im Konto |
| Serviceinstanz erstellen | Administrator für den Kontozugriff oder Editor oder der Administrator oder Editor für den Service im Konto |
| Richtlinie für eine Serviceinstanz erstellen | Administrator für den Kontozugriff oder Administrator für das Konto oder Administrator für den Service im Konto oder Administrator für die Serviceinstanz |
{: caption="Tabelle 4. Verwaltungstasks zum Verwalten von Richtlinien für durch Identity and Access aktivierte Services" caption-side="top"}

### Servicerichtlinienrollen
{: #iamusermanrol}

Rollen sind Sammlungen von Aktionen. Die Aktionen, die diesen Rollen zugeordnet sind, sind je nach Service unterschiedlich. Weitere Informationen darüber, welche Arten von Aktionen jede Rolle ermöglicht, finden Sie in der Dokumentation für den ausgewählten Service.

Neben den Beschreibungen der Rollen, die in der Konsole verfügbar sind, werden in der folgenden Tabelle Beispiele für einige der Tasks aufgeführt, die Benutzer, denen eine Rolle zugewiesen ist, je nach ausgewähltem Service ausführen können. 


| Rolle | Beschreibung von Aktionen | Beispielaktionen|
|:-----------------|:-----------------|:-----------------|
| Viewer (Anzeigeberechtigter) | Führt Aktionen aus, die den Status nicht ändern; Aktionen im Lesezugriff. | <ul><li>Geräte auflisten</li><li>Speicherobjekt lesen</li><li>Abfragen ausführen</li><li>Suchen durchführen</li></ul>|
| Editor (Bearbeiter) | Führt Aktionen aus, die den Status ändern und die Unterressourcen erstellen oder löschen. |<ul><li>Virtuelle Maschinen erstellen oder löschen</li><li>Speicher anhängen</li><li>Neu starten</li><li>Starten oder stoppen</li><li>Umbenennen</li></ul> |
| Administrator | Führt alle Aktionen aus, einschließlich der Möglichkeit, die Zugriffssteuerung zu verwalten. |<ul><li>Benutzer einladen</li><li>Virtuelle Maschinen erstellen oder löschen</li><li>Benutzerzugriffsrichtlinien aktualisieren</li><li>Geräte auflisten</li><li>Speicher anhängen</li><li>Neu starten</li><li>Starten oder stoppen</li><li>Umbenennen</li><li>Backup und Restore durchführen</li></ul>|
{: caption="Tabelle 5. Verwaltungstasks zum Verwalten von Richtlinien für durch Identity and Access aktivierte Services" caption-side="top"}

## Infrastructure-Berechtigungen
{: #infrapermissions}

Wenn Sie über die Zugriffsberechtigung zum Zuweisen von Infrastrukturberechtigungen verfügen, können Sie bei der Einladung eines Benutzers die folgenden Berechtigungen zuweisen: 

| Infrastructure-Berechtigung | Beschreibung von Aktionen |
|---------------------------|------------------------|
|Nur anzeigen | Benutzer mit dieser Berechtigung können Elemente im System nur anzeigen.|
|Basisbenutzer | Benutzer mit dieser Berechtigung können Basisaktionen im System ausführen, wie zum Beispiel Tickets hinzufügen und Geräte verwalten. |
|Superuser | Benutzer mit dieser Berechtigung können alle verfügbaren Aktionen im System ausführen. |
{:caption="Tabelle 6. Infrastructure-Berechtigung" caption-side="top"}

Weitere Berechtigungen können festgelegt werden, nachdem der Benutzer die Einladung akzeptiert hat.
