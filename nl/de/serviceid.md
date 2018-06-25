---

copyright:

  years: 2017, 2018
  
lastupdated: "2018-06-01"

---

{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:screen: .screen}
{:new_window: target="_blank"}
{:tip: .tip}

# Service-IDs erstellen und verwenden
{: #serviceids}

Eine Service-ID dient (ähnlich wie eine Benutzer-ID, die einen Benutzer identifiziert) zur Identifikation eines Service oder einer Anwendung. Eine von Ihnen erstellte Service-ID kann verwendet werden, um einer Anwendung außerhalb von {{site.data.keyword.Bluemix_notm}} den Zugriff auf Ihre {{site.data.keyword.Bluemix_notm}}-Services zu erteilen. Sie können der Service-ID spezielle Zugriffsrichtlinien zuweisen, die die Berechtigungen zur Verwendung bestimmter Services einschränken, oder auch die Berechtigungen für den Zugriff auf unterschiedliche Services kombinieren. Da Service-IDs nicht an bestimmte Benutzer gebunden sind, bleibt die Service-ID bestehen, wenn der zugehörige Benutzer Ihre Organisation verlässt und sein Konto deshalb gelöscht wird. Auf diese Weise wird sichergestellt, dass Ihre Anwendung oder Ihr Service weiterhin funktionsbereit bleibt.

Bei der Erstellung einer Service-ID werden ein eindeutiger Name und eine eindeutige Beschreibung erstellt, die Sie einfach identifizieren und mit der Sie in der Benutzerschnittstelle problemlos arbeiten können. Nach der Erstellung Ihrer Service-ID können Sie API-Schlüssel speziell für die einzelnen Service-IDs erstellen, die von Ihrer Anwendung benutzt werden können, um die Authentifizierung bei Ihren {{site.data.keyword.Bluemix_notm}}-Services durchzuführen. Um sicherzustellen, dass Ihre Anwendung über die korrekten Zugriffsberechtigungen für die Authentifizierung bei Ihren {{site.data.keyword.Bluemix_notm}}-Services verfügt, können Sie die Zugriffsrichtlinien verwenden, die den von Ihnen erstellten Service-IDs zugewiesen werden. 

Die Zugriffsrichtlinien, die einer Service-ID zugewiesen werden, aktivieren bestimmte Aktionen, die ausgeführt werden können, wenn diese Service-ID für den Zugriff auf einen bestimmten Service verwendet wird. Einer einzelnen Service-ID können mehrere Richtlinien zugewiesen werden, die die Zugriffsebene definieren, die beim Zugriff auf mehrere Services mit aktiviertem Identity and Access Management zulässig ist. Sie verfügen beispielsweise über zwei Services mit jeweils zwei Serviceinstanzen. Sie können nun z. B. allen verfügbaren Instanzen des einen Service die Rolle `Anzeigeberechtigter` und nur einer Instanz des zweiten Service die Rolle `Editor` zuweisen. Auf diese Weise können Sie den Zugriff auf mehrere Services anpassen, jedoch bei allen einen einzigen API-Schlüssel zu Authentifizierungszwecken einsetzen.


## Service-ID erstellen

Zum Erstellen einer Service-ID müssen Sie die Optionen **Verwalten** &gt; **Sicherheit** &gt; **Identität und Zugriff** und anschließend **Service-IDs** auswählen. Befolgen Sie die Vorgehensweise, um einen Namen und eine Beschreibung für Ihre Service-ID zu erstellen. Verwenden Sie dann das Menü **Aktionen**, um Ihre Service-ID zu verwalten. Als erstes können Sie eine Richtlinie zuweisen und API-Schlüssel erstellen. Weitere Informationen zum Arbeiten mit API-Schlüsseln finden Sie in [API-Schlüssel für Service-IDs verwalten](/docs/iam/serviceid_keys.html#serviceidapikeys). 

## Service-ID aktualisieren

Um eine Service-ID zu aktualisieren, können Sie jederzeit ihren Namen und die Beschreibung ändern. Außerdem können Sie API-Schlüssel löschen und neue API-Schlüssel erstellen, wenn dies erforderlich ist, oder die zugewiesenen Zugriffsrichtlinien aktualisieren. Alle von Ihnen an einer vorhandenen Service-ID durchgeführten Änderungen (z. B. das Ändern der zugewiesenen Richtlinien oder das Löschen eines API-Schlüssels, der momentan verwendet wird) können zu Serviceunterbrechungen für Anwendungen führen, die diese Service-ID verwenden.

## Service-ID sperren

Damit eine Situation vermieden werden kann, in der die Service-ID gelöscht und so ein Ausfall oder eine Unterbrechung für die Benutzer des Service verursacht wird, können Sie Service-ID über die Benutzerschnittstelle oder die Befehlszeilenschnittstelle sperren. Das Sperren einer Service-ID verhindert darüber hinaus, dass Zugriffsrichtlinien geändert, gelöscht oder zugewiesen werden und dass API-Schlüssel, die der Service-ID zugewiesen sind, erstellt oder gelöscht werden. Sie können nicht nur eine Service-ID sperren, sondern auch [einzelne API-Schlüssel sperren](/docs/iam/serviceid_keys.html#lockkey), die jeder einzelnen Service-ID in Ihrem Konto zugeordnet sind. 

Gesperrte Service-IDs können nicht gelöscht werden und die Zugriffsrichtlinien können nicht aktualisiert werden. Gesperrte Service-IDs können jedoch aus einer Zugriffsgruppe entfernt werden, zu der sie hinzugefügt wurden. Das bedeutet, dass jeder Zugriff, der einer ID durch ihre Mitgliedschaft in einer Zugriffsgruppe zugeordnet wurde, entfernt wird, wenn die Service-ID aus der Zugriffsgruppe entfernt wird.
{: tip}

### Benutzerzugriff zum Sperren von Service-IDs bereitstellen

Damit ein Benutzer über Zugriff zum Sperren und Entsperren von Service-IDs und API-Schlüsseln verfügt, die Service-IDs zugeordnet sind, müssen sie einer bestimmten Zugriffsrichtlinie zugeordnet sein. Ordnungsgemäßer Zugriff kann über zwei Arten von Zugriffsrichtlinien erteilt werden:

* Zugriff auf alle Service-IDs im Konto
* Zugriff auf eine bestimmte Service-ID im Konto

Wenn Sie Zugriff auf alle Service-IDs in einem Konto zuordnen möchten, definieren Sie eine Zugriffsrichtlinie mit den folgenden Details:

* Bearbeiter- oder Administratorrolle 
* IAM Identity Service

Wenn Sie Zugriff auf eine bestimmte Service-ID in einem Konto zuordnen möchten, definieren Sie eine Zugriffsrichtlinie mit den folgenden Details:

* Bearbeiter- oder Administratorrolle
* IAM Identity Service
* Angeben von `serviceid` im Feld **Ressourcentyp** 
* Angeben der Service-ID im Feld **Ressourcen-ID**

Zum Abrufen der Kennung einer bestimmten Service-ID wechseln Sie zu **Verwalten** > **Sicherheit** > **Identität & Zugriff** und anschließend **Service-IDs**. Wählen Sie die Service-ID aus, zu der Sie die Details anzeigen möchten, und kopieren Sie den ID-Wert.
{: tip}

### Service-ID in Benutzerschnittstelle sperren

Eine gesperrte Service-ID ist durch das Symbol ![Sperrsymbol](images/locked.svg "Gesperrt") gekennzeichnet. 

1. Klicken Sie in der Menüleiste auf **Verwalten** &gt; **Sicherheit** &gt; **Identität und Zugriff** und wählen Sie dann **Service-IDs** aus.
2. Ermitteln Sie die Zeile der Service-ID, die gesperrt werden soll, und wählen Sie dann die Option **Service-ID sperren** im Menü **Aktionen** aus.

Wählen Sie zum Entsperren einer Service-ID die Service-ID, die Sie entsperren möchten, in der Tabelle aus, und wählen Sie **Service-ID entsperren** im Menü **Aktionen** aus. Sie müssen über die erforderliche Zugriffsstufe zum Entsperren einer Service-ID verfügen.
{: tip}

### Service-ID über die Befehlszeilenschnittstelle sperren bzw. entsperren

Verwenden Sie den folgenden Befehl, um eine Service-ID zu sperren:

```
ibmcloud iam service-id-lock (NAME|UUID) [-f, --force]
```

Befehlsoptionen:

<dl>
  <dt>NAME (erforderlich)</dt>
  <dd>Der Name des Service, gegenseitig ausschließend mit UUID</dd>
  <dt>UUID (erforderlich)</dt>
  <dd>Die UUID des Service, gegenseitig ausschließend mit NAME</dd>
  <dt>-f, --force</dt>
  <dd>Sperren ohne Bestätigung</dd>
</dl>

<strong>Beispiele</strong>:

Service-ID `sample-test` ohne Bestätigung sperren

```
ibmcloud iam service-id-lock sample-test -f
```

Service-ID `ServiceId-cb258cb9-8de3-4ac0-9aec-b2b2d27ac976` sperren

```
ibmcloud iam service-id-lock ServiceId-cb258cb9-8de3-4ac0-9aec-b2b2d27ac976
```

Verwenden Sie den folgenden Befehl, um eine Service-ID zu entsperren:

 ```
ibmcloud iam service-id-unlock (NAME|UUID) [-f, --force]
```

Befehlsoptionen:

<dl>
  <dt>NAME (erforderlich)</dt>
  <dd>Der Name des Service, gegenseitig ausschließend mit UUID</dd>
  <dt>UUID (erforderlich)</dt>
  <dd>Die UUID des Service, gegenseitig ausschließend mit NAME</dd>
  <dt>-f, --force</dt>
  <dd>Entsperren ohne Bestätigung</dd>
</dl>

<strong>Beispiele</strong>:

Service-ID 'sample-test' ohne Bestätigung entsperren

```
ibmcloud iam service-id-unlock sample-test -f
```

Service-ID 'ServiceId-cb258cb9-8de3-4ac0-9aec-b2b2d27ac976' entsperren

```
ibmcloud iam service-id-unlock ServiceId-cb258cb9-8de3-4ac0-9aec-b2b2d27ac976
```



## Beispiele für die Verwendung einer Service-ID

Die folgenden Beispiele zeigen, wie eine Service-ID mit den {{site.data.keyword.objectstorageshort}}- und Cloud SQL Query-Services verwendet wird.

- {{site.data.keyword.objectstorageshort}} - [Getting Started](/docs/services/cloud-object-storage/getting-started-cli.html#getting-started-cli-).
- Cloud SQL Query - [Verwendung der SQL Query-REST-API ![Symbol für externen Link](../icons/launch-glyph.svg)](https://www.youtube.com/embed/s6S4AdJItHk?rel=0){: new_window}.

