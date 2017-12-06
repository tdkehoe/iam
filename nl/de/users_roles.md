---

copyright:

  years: 2015, 2016

lastupdated: "2017-10-06"

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

Kontoeignern wird automatisch die Administratorrolle für das Konto für die Identitäts- und Zugriffsverwaltung (IAM) zugewiesen, mit der Servicerichtlinien zugewiesen und verwaltet werden können. Servicerichtlinien können einzelnen Benutzern oder Service-IDs zugewiesen werden. Die zugewiesene Richtlinie kann den Zugriff für einen gesamten Service oder auf Ebene einzelner Instanzen definieren.

### Servicerichtlinien

Eine Richtlinie weist einem Benutzer oder einer Service-ID einzelne oder mehrere Rollen für eine Ressourcengruppe zu. Dazu wird eine Kombination von Attributen zur Definition der betreffenden Ressourcengruppe verwendet. Wenn Sie eine Richtlinie zuweisen, geben Sie zuerst den Service an. Anschließend können Sie eine oder mehrere Rollen auswählen, die zugewiesen werden sollen. Abhängig von dem Service, den Sie auswählen, können zusätzliche Konfigurationsoptionen verfügbar sein.

Sie können Richtlinien zuweisen und verwalten, wenn Sie die entsprechende Rolle haben. In der folgenden Tabelle werden die Richtlinienmanagementtasks und die jeweils erforderliche Rolle aufgeführt.

| Aktion | Erforderliche Rolle |
|----------|---------|
| Richtlinien für ein Konto für alle Services und Instanzen erstellen | Kontoadministrator |
| Richtlinie für einen Service in einem Konto erstellen | Kontoadministrator oder Administrator für den Service im Konto |
| Serviceinstanz erstellen | Kontoadministrator oder Administrator oder Editor für den Service im Konto |
| Richtlinie für eine Serviceinstanz erstellen | Kontoadministrator oder Administrator für den Service im Konto oder Administrator für die Serviceinstanz |
{: caption="Tabelle 4. Verwaltungstasks zum Verwalten von Richtlinien für durch IAM aktivierte Services" caption-side="top"}

### Servicerichtlinienrollen
{: #iamusermanrol}

IAM ermöglicht das Verwalten und Definieren des Zugriffs für Benutzer und Ressourcen in Ihrem Konto. Wenn der verwendete Service mit der IAM-Benutzerzugriffssteuerung verwaltet werden kann, stehen zwei Arten von Rollen zur Verfügung, die verschiedene Aktionen in Ihrem Konto ermöglichen: Plattformmanagement- und Servicezugriffsrollen.

<dl>
<dt>Plattformmanagementrollen</dt>
<dd>Für alle Services verfügbare Rollen, die mit der IAM-Benutzerzugriffssteuerung verwaltet werden können. Hierzu gehören Administrator, Editor (Bearbeiter), Operator (Bediener), Viewer (Anzeigeberechtigter) und Abrechnungsadministrator. Diese Rollen werden Benutzeraktionen zugeordnet, die für {{site.data.keyword.Bluemix_notm}}-Ressourcen auf Plattformebene durchgeführt werden können. Zu diesen Aktionen gehören beispielsweise das Erstellen von Instanzen, das Verbinden von Instanzen mit einer Anwendung, das Verwalten von Service-IDs, das Verwalten von Benutzern und Berechtigungen und das Verwalten der Rechnungsstellung und der Kontingente für das Konto. </dd>
<dt>Servicezugriffsrollen</dt>
<dd>Diese Rollen sind servicespezifisch. Die Rollen des Managers, des Schreibberechtigten und des Leseberechtigten definieren die Möglichkeiten des Benutzers, den Service zu verwenden und Service-API-Aufrufe auszuführen. Da jeder Service die Aktionen definiert, die ein Benutzer mit einer bestimmten Rolle durchführen kann, ist es möglich, dass ein Service nicht alle verfügbaren Rollen, die in der vorliegenden Dokumentation beschrieben sind, nutzt. </dd>
</dl>

**Hinweis**: Möglicherweise werden nicht alle als Optionen aufgeführte Rollen angezeigt, wenn Sie Richtlinien in der Benutzerschnittstelle zuweisen, da nur die Rollen, die für den in der Richtlinie ausgewählten Service zutreffen, angezeigt werden. Spezifische Informationen zu den aktivierten Rollen und zu den Aktionen, die die einzelnen Zugriffsrollen für den jeweiligen Service ermöglichen, sind in der Dokumentation zum betreffenden Service beschrieben.


#### Plattformmanagementrollen

Mit Plattformmanagementrollen können Benutzern unterschiedliche Berechtigungsstufen für die Durchführung von Plattformaktionen zugewiesen werden. Neben den Beschreibungen der Rollen, die in der Konsole verfügbar sind, werden in den folgenden Tabellen Beispiele für einige der Plattformmanagementaktionen aufgeführt, die Benutzer durchführen können, denen die entsprechende Rolle zugewiesen wurde.

| Plattformmanagementrolle  | Aktionen, die ein Benutzer für Services im Konto durchführen kann | Aktionen für Service-IDs |
|:-----------------|:--------------|:---------------|
| Viewer (Anzeigeberechtigter) | Instanzen anzeigen | IDs und API-Schlüssel anzeigen |
| Operator (Bediener) |  Serviceinstanzen anzeigen und binden | Nicht zutreffend |
| Editor (Bearbeiter) |  Serviceinstanzen erstellen, löschen, bearbeiten, aussetzen, wiederaufnehmen, anzeigen und binden | IDs löschen und API-Schlüssel erstellen und löschen |
| Administrator |  Alle Verwaltungsaktionen für Services | IDs und API-Schlüssel erstellen und löschen, Richtlinien zu IDs zuweisen |
{: caption="Tabelle 5. Beispiele für Plattformmanagementrollen und Aktionen" caption-side="top"}

Einige Services ordnen möglicherweise bestimmte Aktionen den Plattformmanagementrollen zu, die nicht zum Servicezugriff, sondern zur Serviceverwaltung gehören. Beispiele hierfür sind in der folgenden Tabelle mit Details zu den {{site.data.keyword.containershort_notm}}-Serviceaktionen aufgeführt, die diesen Rollen zugeordnet sind.


| Plattformmanagementrolle | Beschreibung von Aktionen | Beispielaktionen für den {{site.data.keyword.containershort_notm}}-Service |
|:-----------------|:-----------------|:-----------------|
| Viewer (Anzeigeberechtigter) | Serviceinstanzen anzeigen, nicht jedoch ändern  | <ul><li>Cluster auflisten</li><li>Details für einen Cluster anzeigen</li></ul>|
| Editor (Bearbeiter) | Alle Plattformaktionen ausführen mit Ausnahme der Kontoverwaltung und der Zuweisung von Zugriffsrichtlinien |<ul><li>Service an einen Cluster binden</li><li>Webhook erstellen</li></ul> |
| Operator (Bediener) | Plattformaktionen ausführen, die für die Konfiguration und den Betrieb von Serviceinstanzen erforderlich sind, z. B. Anzeigen eines Service-Dashboards | <ul><li>Workerknoten hinzufügen oder entfernen</li><li>Workerknoten neu starten oder erneut laden</li><li>Service an einen Cluster binden</li></ul> |
| Administrator | Alle Plattformaktionen auf der Basis der Ressource ausführen, der diese Rolle zugewiesen wird, einschließlich der Zuweisung von Zugriffsrichtlinien zu anderen Benutzern |<ul><li>Cluster entfernen</li><li>Cluster erstellen</li><li>Benutzerzugriffsrichtlinien aktualisieren</li><li>Alle Aktionen, die ein Anzeigeberechtigter, Bearbeiter und Bediener ausführen kann</li></ul>|
{: caption="Tabelle 6. Beispiele für Plattformmanagementrollen und Aktionen" caption-side="top"}


#### Servicezugriffsrollen

Mit Servicezugriffsrollen können Benutzern unterschiedliche Berechtigungsstufen für das Aufrufen der Service-APIs zugewiesen werden. Die folgenden Tabelle enthält Beispiele für Aktionen, die abhängig von den zugewiesenen Servicezugriffsrollen auf der Basis der Verwendung des {{site.data.keyword.objectstorageshort}}-Service ausgeführt werden können.

**Hinweis**: Die Aktionen, die für die jeweilige zugewiesene Rolle ausgeführt werden können, variieren abhängig vom Service, der für die Richtlinie ausgewählt wurde.

| Servicezugriffsrolle | Beschreibung von Aktionen | Beispielaktionen für den {{site.data.keyword.objectstorageshort}}-Service |
|:-----------------|:-----------------|:-----------------|
|  Reader (Leseberechtigter) | Aktionen mit Lesezugriff innerhalb eines Service durchführen, z. B. servicespezifische Ressourcen anzeigen | Objekte auflisten und herunterladen |
| Writer (Schreibberechtigter) | Schreibberechtigte verfügen über Berechtigungen, die über die Rolle der Leseberechtigten hinausgehen, z. B. servicespezifische Ressourcen erstellen und bearbeiten. | Buckets und Objekte erstellen und löschen |
| Manager | Manager verfügen über Berechtigungen, die über die Rolle der Schreibberechtigten hinausgehen, und können Aktionen durchführen, für die vom Service definierte spezielle Berechtigungen erforderlich sind. Darüber hinaus können servicespezifische Ressourcen erstellt und bearbeitet werden. | Alle Aspekte der Datenspeicherung verwalten, Buckets und Objekte erstellen und löschen |
{: caption="Tabelle 7. Beispiele für Servicezugriffsrollen und Aktionen" caption-side="top"}


## Infrastructure-Berechtigungen
{: #infrapermissions}

Sie können bei der Einladung eines Benutzers die folgenden Ausgangsberechtigungen festlegen:

| Festgelegte Berechtigung | Beschreibung von Aktionen |
|---------------------------|------------------------|
|Nur anzeigen | Benutzer mit dieser Berechtigung können Elemente im System nur anzeigen.|
|Basisbenutzer | Benutzer mit dieser Berechtigung können Basisaktionen im System ausführen, wie zum Beispiel Tickets hinzufügen und Geräte verwalten. |
|Superuser | Benutzer mit dieser Berechtigung können alle verfügbaren Aktionen im System ausführen. |
{:caption="Tabelle 8. Infrastructure-Berechtigungen" caption-side="top"}

Weitere Berechtigungen können festgelegt werden, nachdem der Benutzer die Einladung akzeptiert hat. Die Ausgangsberechtigung, die zum Zeitpunkt der Einladung festgelegt wird, erteilt keinen Zugriff auf Geräte. Die Zugriffsberechtigungen für Geräte müssen im Steuerungsportal erteilt werden, nachdem der Benutzer die Einladung akzeptiert hat.
