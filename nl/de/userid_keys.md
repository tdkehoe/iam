---

copyright:

  years: 2015, 2018
lastupdated: "2018-06-06"

---

{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:screen: .screen}
{:new_window: target="_blank"}

# API-Schlüssel für Benutzer verwalten
{: #userapikey}

Ein eingebundener oder nicht eingebundener Benutzer kann einen API-Schlüssel erstellen, der in der Befehlszeilenschnittstelle (CLI = Command-Line Interface) oder im Rahmen der automatisierten Anmeldung als Benutzeridentität verwendet wird. Sie können die Benutzerschnittstelle oder die Befehlszeilenschnittstelle verwenden, um Ihre API-Schlüssel zu verwalten, indem Sie Schlüssel auflisten, erstellen, aktualisieren oder löschen. Zum Verwalten der {{site.data.keyword.Bluemix_notm}}-API-Schlüssel, die Ihrer Benutzeridentität zugeordnet sind, rufen Sie **Verwalten** &gt; **Sicherheit** &gt; **Plattform-API-Schlüssel** auf, um eine Liste Ihrer API-Schlüssel mit Beschreibungen und Datumsangaben anzuzeigen. Sie können dann API-Schlüssel erstellen, bearbeiten oder löschen. Eine vollständige Liste der verfügbaren CLI-Befehle finden Sie im Abschnitt [`ibmcloud iam api-keys`](/docs/cli/reference/bluemix_cli/bx_cli.html#ibmcloud_iam).

Als [eingebundener Benutzer](/docs/account/adminpublic.html#federatedid) können Sie einen API-Schlüssel für die Anmeldung nutzen, indem Sie die Umgebungsvariable `BLUEMIX_API_KEY` verwenden. Weitere Informationen zur Verwendung eines API-Schlüssels für die Anmeldung finden Sie in [Mit eingebundener ID anmelden](/docs/cli/login_federated_id.html#federated_id).

## API-Schlüssel erstellen

Als {{site.data.keyword.Bluemix_notm}}-Benutzer können Sie einen API-Schlüssel verwenden, wenn Sie ein Programm oder Script aktivieren, ohne Ihr Kennwort an das Script weiterzugeben. Ein Vorteil bei der Verwendung eines API-Schlüssels kann sein, dass ein Benutzer oder eine Organisation mehrere API-Schlüssel für verschiedene Programme erstellen kann und die API-Schlüssel können einzeln gelöscht werden, wenn diese kompromittiert wurden, ohne dass sich dies auf andere API-Schlüssel oder gar den Benutzer auswirkt. Sie können bis zu 20 API-Schlüssel erstellen.

Führen Sie die folgenden Schritte aus, um einen API-Schlüssel für Ihre Benutzeridentität in der Benutzerschnittstelle zu erstellen:

1. Rufen Sie **Verwalten** &gt; **Sicherheit** &gt; **Plattform-API-Schlüssel** auf.
2. Klicken Sie auf **API-Schlüssel erstellen**.
3. Geben Sie einen Namen und eine Beschreibung für den API-Schlüssel ein.
4. Klicken Sie auf **API-Schlüssel erstellen**.
5. Klicken Sie anschließend auf **Anzeigen**, um den API-Schlüssel anzuzeigen, um ihn zu kopieren und für eine spätere Verwendung zu speichern, oder klicken Sie auf **API-Schlüssel herunterladen**.

**Hinweis:** Aus Sicherheitsgründen kann der API-Schlüssel nur zum Zeitpunkt seiner Erstellung kopiert oder heruntergeladen werden. Wenn der API-Schlüssel verloren geht, müssen Sie einen neuen API-Schlüssel erstellen.

Verwenden Sie den folgenden Befehl, um einen API-Schlüssel über die Befehlszeilenschnittstelle zu erstellen:

1. Geben Sie `ibmcloud iam api-key-create NAME [-d DESCRIPTION] [-f, --file FILE]` in der Eingabeaufforderung ein und geben Sie einen Namen, eine Beschreibung und eine Datei zum Speichern des Schlüssels ein. Beispiel:

```
ibmcloud iam api-key-create MyKey -d "this is my API key" --file key_file
``` 


## API-Schlüssel aktualisieren

Wenn Sie den Namen oder die Beschreibung eines API-Schlüssels ändern möchten, führen Sie die folgenden Schritte in der Benutzerschnittstelle oder der Befehlszeilenschnittstelle aus.

Führen Sie die folgenden Schritte aus, um einen API-Schlüssel zu bearbeiten:

1. Rufen Sie **Verwalten** &gt; **Sicherheit** &gt; **Plattform-API-Schlüssel** auf.
2. Klicken Sie im Menü **Aktionen** eines in der Tabelle aufgeführten API-Schlüssels auf **Name & Beschreibung bearbeiten**. 
3. Aktualisieren Sie die Informationen für den API-Schlüssel.
4. Klicken Sie auf **API-Schlüssel aktualisieren**.

Geben Sie den folgenden Befehl ein, um einen API-Schlüssel über die Befehlszeilenschnittstelle zu bearbeiten:

1. Geben Sie `ibmcloud iam api-key-update NAME [-n NAME] [-d DESCRIPTION]` in der Eingabeaufforderung ein und geben Sie dabei den alten Namen, den neuen Namen und die neue Beschreibung für den Schlüssel an. Beispiel:

```
ibmcloud iam api-key-update MyCurrentName -n MyNewName -d "neue Beschreibung des Schlüssels"
```

## API-Schlüssel sperren

Sie können das Löschen von API-Schlüsseln der Plattform, die Ihre Benutzeridentität darstellen, verhindern, indem Sie sie sperren. Ein gesperrter API-Schlüssel ist durch das Symbol ![Sperrsymbol](images/locked.svg "Gesperrt") gekennzeichnet. Das Sperren und Entsperren von API-Schlüsseln ist über die Benutzerschnittstelle oder die Befehlszeilenschnittstelle möglich.

### API-Schlüssel über die Benutzerschnittstelle sperren bzw. entsperren

1. Klicken Sie in der Menüleiste auf **Verwalten** &gt; **Sicherheit** &gt; **Identität und Zugriff** und wählen Sie dann **Plattform-API-Schlüssel** aus.
2. Ermitteln Sie die Zeile des API-Schlüssels, der gesperrt werden soll, und wählen Sie dann die Option **API-Schlüssel sperren** im Menü **Aktionen** aus.

Sie können den API-Schlüssel zu jedem beliebigen Zeitpunkt entsperren, um ihn zu aktualisieren, zu löschen oder aus Ihrem Konto zu entfernen oder um eine Zugriffsrichtlinie hinzuzufügen. Wählen Sie den API-Schlüssel,der entsperrt werden soll, in der Tabelle aus, und wählen Sie **API-Schlüssel entsperren** im Menü **Aktionen** aus.
{: tip}

### API-Schlüssel über die Befehlszeilenschnittstelle sperren bzw. entsperren

Verwenden Sie den folgenden Befehl, um einen Plattform-API-Schlüssel zu sperren:

```
ibmcloud iam api-key-lock (NAME|UUID) [-f, --force]
```

<strong>Voraussetzungen</strong>: Endpunkt, Anmeldung

<strong>Befehlsoptionen</strong>:
<dl>
<dt>NAME (erforderlich)</dt>
<dd>Der Name des zu sperrenden API-Schlüssels, gegenseitig ausschließend mit UUID</dd>
<dt>UUID (erforderlich)</dt>
<dd>Die UUID des zu sperrenden API-Schlüssels, gegenseitig ausschließend mit NAME</dd>
<dt>-f, --force</dt>
<dd>Sperren ohne Bestätigung erzwingen.</dd>
</dl>

<strong>Beispiel</strong>:

API-Schlüssel `test-api-key` sperren

```
ibmcloud iam api-key-lock test-api-key
```

Führen Sie den folgenden Befehl aus, um einen Plattform-API-Schlüssel zu sperren:

```
ibmcloud iam api-key-unlock (NAME|UUID) [-f, --force]
```

<strong>Voraussetzungen</strong>: Endpunkt, Anmeldung

<strong>Befehlsoptionen</strong>:
<dl>
<dt>NAME (erforderlich)</dt>
<dd>Der Name des zu entsperrenden API-Schlüssels, gegenseitig ausschließend mit UUID</dd>
<dt>UUID (erforderlich)</dt>
<dd>Die UUID des zu entsperrenden API-Schlüssels, gegenseitig ausschließend mit NAME</dd>
<dt>-f, --force</dt>
<dd>Entsperren ohne Bestätigung erzwingen.</dd>
</dl>

<strong>Beispiel</strong>:

API-Schlüssel `test-api-key` entsperren

```
ibmcloud iam api-key-unlock test-api-key
```


## API-Schlüssel löschen

Wenn Sie ein Schlüsselrotationsverfahren nutzen, können Sie einen älteren Schlüssel löschen und durch einen neuen ersetzen.

Führen Sie die folgenden Schritte aus, um einen API-Schlüssel zu löschen: 

1. Rufen Sie **Verwalten** &gt; **Sicherheit** &gt; **Plattform-API-Schlüssel** auf.
2. Klicken Sie im Menü **Aktionen** eines in der Tabelle aufgeführten API-Schlüssels auf **Löschen**.
3. Bestätigen Sie anschließend den Löschvorgang durch Klicken auf **Schlüssel löschen**.

Gehen Sie wie folgt vor, um einen API-Schlüssel über die Befehlszeilenschnittstelle zu löschen:
1. Geben Sie in der Eingabeaufforderung `ibmcloud iam api-key-delete NAME` ein und geben Sie dabei den Namen des zu löschenden Schlüssels an.
