---

copyright:

  years: 2015, 2018

lastupdated: "2018-06-07"

---

{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:screen: .screen}
{:tip: .tip}
{:new_window: target="_blank"}

# IAM-Zugriff
{: #userroles}

Alle Services, die in einer Ressourcengruppe in Ihrem Konto zusammengefasst sind, werden mithilfe von {{site.data.keyword.Bluemix_notm}} Identity and Access Management (IAM) verwaltet. Kontoeignern wird automatisch die Kontoadministratorrolle für Cloud IAM zugewiesen. Als Kontoadministrator können Sie Benutzern Zugriffsberechtigungen zuweisen und diese Zugriffsberechtigungen verwalten, Ressourcengruppen erstellen und Serviceinstanzen bereitstellen, indem Sie die entsprechenden Cloud IAM-Rollen zweisen. Sie können Zugriffsberechtigungen für Benutzer und Service-IDs bereitstellen, indem Sie Richtlinien erstellen, die ein Ziel für den Benutzer oder die Service-ID festlegen, auf das zugegriffen werden soll, und außerdem eine Rolle, in der definiert ist, welcher Zugriffstyp zulässig ist.


## Was sind Cloud IAM-Richtlinien und wer kann sie zuweisen?
{: #iamusermanpol}

Eine Richtlinie weist einem Benutzer oder einer Service-ID einzelne oder mehrere Rollen für eine Gruppe von Ressourcen zu, um im Kontext der angegebenen Zielressourcen bestimmte Aktion zu ermöglichen. Wenn Sie eine Richtlinie zuweisen, geben Sie zuerst an, ob eine Richtlinie für eine Ressourcengruppe oder eine einzelne Ressource definiert werden soll. Anschließend können Sie abhängig von der zuerst getroffenen Auswahl einen Service in einer Ressourcengruppe oder eine einzelne Instanz für die ausgewählte Ressource auswählen. Abhängig von dem Service, den Sie auswählen, können weitere Konfigurationsoptionen verfügbar sein. Abschließend können Sie einzelne oder mehrere Rollen auswählen, die zugewiesen werden sollen. 

Sie können Richtlinien zuweisen und verwalten, wenn Sie die entsprechende Rolle haben. In der folgenden Tabelle werden die Richtlinienmanagementtasks und die jeweils erforderliche Rolle aufgeführt.

| Aktion | Erforderliche Rolle |
|----------|---------|
| Richtlinie für ein Konto für alle Services und Instanzen erstellen | Kontoeigner oder Administrator für alle Services im Konto | 
| Richtlinie für einen Service in einem Konto erstellen | Kontoeigner oder Administrator für den Service im Konto |
| Richtlinie für eine Serviceinstanz erstellen | Kontoeigner, Administrator für den Service im Konto, Administrator für alle Services in der relevanten Ressourcengruppe oder Administrator für die Serviceinstanz |
| Richtlinie zum Verwalten einer Ressourcengruppe erstellen | Kontoeigner oder Administrator für eine Ressourcengruppe |
{: caption="Tabelle 1. Benutzer, die Zugriffsrichtlinien erstellen dürfen" caption-side="top"} 


## Cloud IAM-Rollen
{: #iamusermanrol}

Mit Cloud IAM können Sie die Zugriffsberechtigungen für Benutzer und Ressourcen in Ihrem Konto verwalten und definieren. Es können zwei Typen von Rollen zugewiesen werden: Plattformmanagement- und Servicezugriffsrollen.

<dl>
<dt>Plattformmanagementrollen</dt> 
<dd>Plattformmanagementrollen decken einen Bereich von Aktionen ab. Hierzu gehört z. B. die Möglichkeit zum Erstellen von Instanzen, zum Verwalten von Service-IDs, Benutzern und Berechtigungen sowie zum Erstellen von Ressourcengruppen. Die am häufigsten verwendeten Plattformrollen sind 'Administrator', 'Editor', 'Operator' und 'Anzeigeberechtigter'. </dd>
<dt>Servicezugriffsrollen</dt>
<dd>Servicezugriffsrollen definieren die Möglichkeit eines Benutzers oder eines Service, bestimmte Aktionen für eine Serviceinstanz auszuführen. Hierzu zählen z. B. der Zugriff auf die Benutzerschnittstelle oder das Ausführen von API-Aufrufen. Es gibt drei mögliche Rollen: Manager, Schreibberechtigter (Writer) und Leseberechtigter (Reader). </dd>
</dl> 

Möglicherweise werden nicht alle als Optionen aufgeführten Rollen angezeigt, wenn Sie Richtlinien in der Benutzerschnittstelle zuweisen, da nur die Rollen angezeigt werden, die für den von Ihnen ausgewählten Service verfügbar sind. Spezifische Informationen zu den aktivierten Rollen und zu den Aktionen, die die einzelnen Zugriffsrollen für den jeweiligen Service ermöglichen, sind in der Dokumentation zum betreffenden Service beschrieben.
{: tip}

Durch Verwendung einer Zusammenstellung dieser Rollen in einer einzigen Zugriffsrichtlinie können Sie differenzierte Zugriffsberechtigungen für Benutzer und Service-IDs bereitstellen, indem Sie den Zugriff auf die folgenden Komponenten zuweisen:

* Alle Ressourcen im Konto
* Alle Ressourcen in allen Services, die zu einer einzelnen Ressourcengruppe gehören, sowie die Möglichkeit, die Ressourcengruppe zu verwalten.
* Alle Ressourcen in einem einzelnen Service in einer Ressourcengruppe sowie die Möglichkeit, die Ressourcengruppe zu verwalten.
* Alle Ressourcen in einem einzelnen Service innerhalb des gesamten Kontos unabhängig von der Ressourcengruppe, der sie zugewiesen sind.
* Ressourcen in einer einzelnen Instanz.
* Ein einzelner Ressourcentyp in einer Instanz, z. B. ein Bucket in einer {{site.data.keyword.objectstorageshort}}-Instanz.

Um einem weiteren Benutzer den uneingeschränkten Zugriff auf das Konto zu erteilen, um den Benutzerzugriff und alle Kontoressourcen (einschließlich der Möglichkeit zum Erstellen von Ressourcengruppen) zu verwalten, müssen Sie eine Richtlinie einrichten, die dem Benutzer den Zugriff auf alle Ressourcen im Konto ermöglicht. Wählen Sie hierzu die Option **Alle Services mit aktiviertem Identity and Access Management** aus und weisen Sie dabei die Rolle **Administrator** zu. 
{: tip}

### Plattformmanagementrollen

Mit Plattformmanagementrollen können Benutzern unterschiedliche Berechtigungsstufen für die Durchführung von Plattformaktionen im Konto zugewiesen werden. In den folgenden Tabellen werden Beispiele für einige der Plattformmanagementaktionen aufgeführt, die Benutzer durchführen können, denen die entsprechende Rolle zugewiesen wurde. In der Dokumentation zu den verschiedenen Services finden Sie Informationen dazu, wie die Rollen für Benutzer im Kontext des momentan verwendeten Service angewendet werden.

| Zugriffsrichtlinie - Details  | Aktionen, die ein Benutzer für Services im Konto durchführen kann | Aktionen für Service-IDs | Aktionen für Zugriff auf Ressourcengruppen | Aktion für Ressourcen in Ressourcengruppen | Aktionen für die Verwaltung von Zugriffsgruppen |
|:-----------------|:--------------|:---------------|:----------------|:-----------------|:--------------|
| Zugriff zuweisen für | Einen oder alle IAM-fähigen Services | IAM Identity Service | Ausgewählte Ressourcengruppe | Ausgewählten Service in einer Ressourcengruppe | IAM-Zugriffsgruppen |
| Anzeigeberechtigten-Rolle | Instanzen, Aliasnamen, Bindungen und Berechtigungsnachweise anzeigen | IDs und API-Schlüssel anzeigen | Ressourcengruppe anzeigen | Nur angegebene Instanzen in der Ressourcengruppe anzeigen | Zugriffsgruppen und Mitglieder anzeigen |
| Operatorrolle |  Instanzen anzeigen und Aliasnamen, Bindungen und Berechtigungsnachweise verwalten | Nicht zutreffend | Nicht zutreffend | Nicht zutreffend | Nicht zutreffend |
| Bearbeiterrolle |  Instanzen erstellen, löschen, bearbeiten und anzeigen. Aliasnamen, Bindungen und Berechtigungsnachweise verwalten | IDs und API-Schlüssel erstellen und löschen | Name der Ressourcengruppe anzeigen und bearbeiten | Nur angegebene Instanzen in der Ressourcengruppe erstellen, löschen, bearbeiten, aussetzen, wiederaufnehmen, anzeigen und binden | Zugriffsgruppen in dem Konto anzeigen, erstellen, löschen und bearbeiten |
| Administratorrolle |  Alle Verwaltungsaktionen für Services | IDs und API-Schlüssel erstellen und löschen, Richtlinien zu IDs zuweisen | Zugriff für die Ressourcengruppe anzeigen, bearbeiten und verwalten | Alle Verwaltungsaktionen für die angegebenen Instanzen in der Ressourcengruppe | Zugriff für das Arbeiten mit Zugriffsgruppen anzeigen, erstellen, löschen, bearbeiten und verwalten |
{: caption="Tabelle 2. Beispiele für Plattformmanagementrollen und Aktionen" caption-side="top"}
{: #platformrolestable}

Einige Services ordnen möglicherweise bestimmte Aktionen den Plattformmanagementrollen zu, die nicht zum Servicezugriff, sondern zur Serviceverwaltung gehören. Beispiele hierfür sind in der folgenden Tabelle mit Details zu den {{site.data.keyword.containershort_notm}}-Serviceaktionen aufgeführt, die diesen Rollen zugeordnet sind.


| Plattformmanagementrolle | Beschreibung von Aktionen | Beispielaktionen für {{site.data.keyword.containershort_notm}} |
|:-----------------|:-----------------|:-----------------|
| Viewer (Anzeigeberechtigter) | Serviceinstanzen anzeigen, nicht jedoch ändern  | <ul><li>Cluster auflisten</li><li>Details für einen Cluster anzeigen</li></ul>|
| Editor (Bearbeiter) | Alle Plattformaktionen ausführen mit Ausnahme der Kontoverwaltung und der Zuweisung von Zugriffsrichtlinien |<ul><li>Service an einen Cluster binden</li><li>Webhook erstellen</li></ul> |
| Operator (Bediener) | Plattformaktionen ausführen, die für die Konfiguration und den Betrieb von Serviceinstanzen erforderlich sind, z. B. Anzeigen eines Service-Dashboards | <ul><li>Workerknoten hinzufügen oder entfernen</li><li>Workerknoten neu starten oder erneut laden</li><li>Service an einen Cluster binden</li></ul> |
| Administrator | Alle Plattformaktionen auf der Basis der Ressource ausführen, der diese Rolle zugewiesen wird, einschließlich der Zuweisung von Zugriffsrichtlinien zu anderen Benutzern |<ul><li>Cluster entfernen</li><li>Cluster erstellen</li><li>Benutzerzugriffsrichtlinien aktualisieren</li><li>Alle Aktionen, die ein Anzeigeberechtigter, Bearbeiter und Bediener ausführen kann</li></ul>|
{: caption="Tabelle 3. Beispiele für Plattformmanagementrollen und Aktionen für {{site.data.keyword.containershort_notm}}-Service" caption-side="top"}


### Servicezugriffsrollen

Mit Servicezugriffsrollen können Benutzern unterschiedliche Berechtigungsstufen für das Aufrufen der Service-APIs und den Zugriff auf die Benutzerschnittstelle des Service zugewiesen werden. Die folgende Tabelle enthält Beispiele für Aktionen, die abhängig von den zugewiesenen Rollen auf Basis der Verwendung des {{site.data.keyword.objectstorageshort}}-Service ausgeführt werden können.

**Hinweis**: Die Aktionen, die für die jeweilige zugewiesene Rolle ausgeführt werden können, variieren abhängig vom Service, der für die Richtlinie ausgewählt wurde.

| Servicezugriffsrolle | Beschreibung von Aktionen | Beispielaktionen für den {{site.data.keyword.objectstorageshort}}-Service |
|:-----------------|:-----------------|:-----------------|
|  Reader (Leseberechtigter) | Aktionen mit Lesezugriff innerhalb eines Service durchführen, z. B. servicespezifische Ressourcen anzeigen | Objekte auflisten und herunterladen |
| Writer (Schreibberechtigter) | Schreibberechtigte verfügen über Berechtigungen, die über die Rolle der Leseberechtigten hinausgehen, z. B. servicespezifische Ressourcen erstellen und bearbeiten. | Buckets und Objekte erstellen und löschen |
| Manager | Manager verfügen über Berechtigungen, die über die Rolle der Schreibberechtigten hinausgehen, und können Aktionen durchführen, für die vom Service definierte spezielle Berechtigungen erforderlich sind. Darüber hinaus können servicespezifische Ressourcen erstellt und bearbeitet werden. | Alle Aspekte der Datenspeicherung verwalten, Buckets und Objekte erstellen und löschen |
{: caption="Tabelle 4. Beispiele für Servicezugriffsbenutzerrollen und Aktionen" caption-side="top"}

