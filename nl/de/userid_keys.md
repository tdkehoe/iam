---

copyright:

  years: 2015, 2017
lastupdated: "2017-11-16"

---

{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:screen: .screen}
{:new_window: target="_blank"}

# API-Schlüssel für Benutzer verwalten
{: #userapikey}

Ein eingebundener oder nicht eingebundener Benutzer kann einen API-Schlüssel erstellen, der in der Befehlszeilenschnittstelle (CLI = Command-Line Interface) oder im Rahmen der automatisierten Anmeldung als Benutzeridentität verwendet wird. Sie können die Benutzerschnittstelle oder die Befehlszeilenschnittstelle verwenden, um Ihre API-Schlüssel zu verwalten, indem Sie Schlüssel auflisten, erstellen, aktualisieren oder löschen. Zum Verwalten der {{site.data.keyword.Bluemix_notm}}-API-Schlüssel, die Ihrer Benutzeridentität zugeordnet sind, rufen Sie **Verwalten** &gt; **Sicherheit** &gt; **Plattform-API-Schlüssel** auf, um eine Liste Ihrer API-Schlüssel mit Beschreibungen und Datumsangaben anzuzeigen. Sie können dann über diese Seite API-Schlüssel erstellen, bearbeiten oder löschen. Eine vollständige Liste der verfügbaren CLI-Befehle finden Sie in [Befehle zur Verwaltung von API-Schlüsseln und Richtlinien](/docs/cli/reference/bluemix_cli/bx_cli.html#bx_commands_iam).

Als [eingebundener Benutzer](/docs/admin/adminpublic.html#federatedid) können Sie einen API-Schlüssel für die Anmeldung nutzen, indem Sie die Umgebungsvariable `BLUEMIX_API_KEY` verwenden. Weitere Informationen zur Verwendung eines API-Schlüssels für die Anmeldung finden Sie in [Mit eingebundener ID anmelden](/docs/iam/login_fedid.html).

## API-Schlüssel erstellen

Als {{site.data.keyword.Bluemix_notm}}-Benutzer können Sie einen API-Schlüssel verwenden, wenn Sie ein Programm oder Script aktivieren, ohne Ihr Kennwort an das Script weiterzugeben. Ein Vorteil bei der Verwendung eines API-Schlüssels kann sein, dass ein Benutzer oder eine Organisation mehrere API-Schlüssel für verschiedene Programme erstellen kann und die API-Schlüssel können einzeln gelöscht werden, wenn diese kompromittiert wurden, ohne dass sich dies auf andere API-Schlüssel oder gar den Benutzer auswirkt.

Gehen Sie wie folgt vor, um einen API-Schlüssel für Ihre Benutzeridentität in der Benutzerschnittstelle zu erstellen:

1. Rufen Sie **Verwalten** &gt; **Sicherheit** &gt; **Plattform-API-Schlüssel** auf.
2. Klicken Sie auf **API-Schlüssel erstellen**.
3. Geben Sie einen Namen und eine Beschreibung für den API-Schlüssel ein.
4. Klicken Sie auf **API-Schlüssel erstellen**.
5. Klicken Sie anschließend auf **Anzeigen**, um den API-Schlüssel anzuzeigen, um ihn zu kopieren und für eine spätere Verwendung zu speichern, oder klicken Sie auf **API-Schlüssel herunterladen**.

**Hinweis:** Aus Sicherheitsgründen kann der API-Schlüssel nur zum Zeitpunkt seiner Erstellung kopiert oder heruntergeladen werden. Wenn der API-Schlüssel verloren geht, müssen Sie einen neuen API-Schlüssel erstellen.

Gehen Sie wie folgt vor, um einen API-Schlüssel über die Befehlszeilenschnittstelle zu erstellen:

1. Geben Sie `bluemix iam api-key-create NAME [-d DESCRIPTION] [-f, --file FILE]` in der Eingabeaufforderung ein und geben Sie einen Namen, eine Beschreibung und eine Datei zum Speichern des Schlüssels ein. Beispiel:

```
bluemix iam api-key-create MyKey -d "this is my API key" -f key_file
``` 


## API-Schlüssel aktualisieren

Wenn Sie den Namen oder die Beschreibung eines API-Schlüssels ändern möchten, führen Sie die folgenden Schritte in der Benutzerschnittstelle oder der Befehlszeilenschnittstelle aus.

Gehen Sie wie folgt vor, um einen API-Schlüssel zu bearbeiten:

1. Rufen Sie **Verwalten** &gt; **Sicherheit** &gt; **Plattform-API-Schlüssel** auf.
2. Klicken Sie im Menü **Aktionen** eines in der Tabelle aufgeführten API-Schlüssels auf **Name & Beschreibung bearbeiten**. 
3. Aktualisieren Sie die Informationen für den API-Schlüssel.
4. Klicken Sie auf **API-Schlüssel aktualisieren**.

Gehen Sie wie folgt vor, um einen API-Schlüssel über die Befehlszeilenschnittstelle zu bearbeiten:

1. Geben Sie `bluemix iam api-key-update NAME [-n NAME] [-d DESCRIPTION]` in der Eingabeaufforderung ein und geben Sie dabei den alten Namen, den neuen Namen und die neue Beschreibung für den Schlüssel an. Beispiel:

```
bluemix iam api-key-update MyCurrentName -n MyNewName -d "neue Beschreibung des Schlüssels"
```

## API-Schlüssel löschen

Wenn Sie ein Schlüsselrotationsverfahren nutzen, können Sie einen älteren Schlüssel löschen und durch einen neuen ersetzen.

Gehen Sie wie folgt vor, um einen API-Schlüssel zu löschen: 

1. Rufen Sie **Verwalten** &gt; **Sicherheit** &gt; **Plattform-API-Schlüssel** auf.
2. Klicken Sie im Menü **Aktionen** eines in der Tabelle aufgeführten API-Schlüssels auf **Löschen**.
3. Bestätigen Sie anschließend den Löschvorgang durch Klicken auf **Schlüssel löschen**.

Gehen Sie wie folgt vor, um einen API-Schlüssel über die Befehlszeilenschnittstelle zu löschen:
1. Geben Sie `bluemix iam api-key-delete NAME` in der Eingabeaufforderung ein und geben Sie den Namen des Schlüssels an, der gelöscht werden soll.
