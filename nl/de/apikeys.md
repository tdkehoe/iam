---

copyright:

  years: 2015, 2017
lastupdated: "2017-07-27"

---

{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:screen: .screen}
{:new_window: target="_blank"}

# API-Schlüssel verwalten
{: #manapikey}

Ein API-Schlüssel ist ein Code, der von Computerprogrammen übergeben wird, die eine Anwendungsprogrammierschnittstelle (API) aufrufen, um das aufrufende Programm, dessen Entwickler oder den zugehörigen Benutzer der Website zu identifizieren. Mit API-Schlüsseln kann überwacht und gesteuert werden, wie die API verwendet wird, beispielsweise um die böswillige Verwendung oder den Missbrauch der API zu verhindern (wie z. B. durch die Nutzungsbestimmungen festgelegt). Der API-Schlüssel dient oft als eine eindeutige Kennung und geheimes Token für die Authentifizierung, normalerweise ist ihm eine Gruppe von Zugriffsberechtigungen zugeordnet, die für den ihm zugeordneten Benutzer spezifisch ist. API-Schlüssel können auf einem UUID-System (UUID - Universal Unique Identifier) basieren, um sicherzustellen, dass sie für jeden Benutzer eindeutig sind.

Ein föderierter oder nicht föderierter Benutzer kann einen API-Schlüssel erstellen, der in der Befehlszeilenschnittstelle oder als Teil der automatischen Anmeldung mit Ihrem Benutzernamen verwendet wird. Sie können die {{site.data.keyword.Bluemix_notm}}-Benutzerschnittstelle oder die {{site.data.keyword.Bluemix_notm}}-Befehlszeilenschnittstelle verwenden, um Ihre API-Schlüssel zu verwalten, indem Sie Schlüssel auflisten, erstellen, aktualisieren oder löschen. Zum Verwalten der {{site.data.keyword.Bluemix_notm}}-API-Schlüssel über die Benutzerschnittstelle rufen Sie **Verwalten** &gt; **Sicherheit** &gt; **Bluemix-API-Schlüssel** auf, um eine Liste Ihrer API-Schlüssel mit Beschreibungen und Datumsangaben anzuzeigen. Sie können dann über diese Seite API-Schlüssel erstellen, bearbeiten oder löschen. Eine vollständige Liste der verfügbaren CLI-Befehle können Sie über [`bluemix iam api-keys`](/docs/cli/reference/bluemix_cli/bx_cli.html#bluemix_iam) aufrufen.

Als [föderierter Benutzer](/docs/admin/adminpublic.html#federatedid) können Sie einen API-Schlüssel für die Anmeldung nutzen, indem Sie die Umgebungsvariable `BLUEMIX_API_KEY` verwenden. Weitere Informationen zur Verwendung eines API-Schlüssel für die Anmeldung finden Sie in der Dokumentation zum [{{site.data.keyword.Bluemix_notm}}-CLI-Befehl `bluemix login`](/docs/cli/reference/bluemix_cli/bx_cli.html#bluemix_login) und zum [Befehl `cf login` der Befehlszeilenschnittstelle 'cf'](/docs/cli/reference/cfcommands/index.html#cf_login).

## API-Schlüssel erstellen

Als {{site.data.keyword.Bluemix_notm}}-Benutzer können Sie einen API-Schlüssel verwenden, wenn Sie ein Programm oder Script aktivieren, ohne Ihr Kennwort an das Script weiterzugeben. Ein Vorteil bei der Verwendung eines API-Schlüssels kann sein, dass ein Benutzer oder eine Organisation mehrere API-Schlüssel für verschiedene Programme erstellen kann und die API-Schlüssel können einzeln gelöscht werden, wenn diese kompromittiert wurden, ohne dass sich dies auf andere API-Schlüssel oder gar den Benutzer auswirkt.

Gehen Sie wie folgt vor, um einen API-Schlüssel über die Benutzerschnittstelle zu erstellen:

1. Wechseln Sie zu **Verwalten** &gt; **Sicherheit** &gt; **Bluemix-API-Schlüssel**.
2. Klicken Sie auf **API-Schlüssel erstellen**.
3. Geben Sie einen Namen und eine Beschreibung für den API-Schlüssel ein.
4. Klicken Sie auf **API-Schlüssel erstellen**.
5. Klicken Sie anschließend auf **Anzeigen**, um den API-Schlüssel anzuzeigen, um ihn zu kopieren und für eine spätere Verwendung zu speichern, oder klicken Sie auf **API-Schlüssel herunterladen**.

**Hinweis**: Der API-Schlüssel steht nur zum Zeitpunkt seiner Erstellung zum Anzeigen oder Herunterladen zur Verfügung. Wenn der API-Schlüssel verloren geht, müssen Sie einen neuen API-Schlüssel erstellen.

Gehen Sie wie folgt vor, um einen API-Schlüssel über die Befehlszeilenschnittstelle zu erstellen:

1. Geben Sie `bluemix iam api-key-create NAME [-d DESCRIPTION] [-f, --file FILE]` in der Eingabeaufforderung ein und geben Sie einen Namen, eine Beschreibung und eine Datei zum Speichern des Schlüssels ein. Beispiel:

```
bluemix iam api-key-create MyKey -d "this is my API key" -f key_file
``` 

Nach der Erstellung eines API-Schlüssels über die Befehlszeilenschnittstelle gibt es mehrere Möglichkeiten, den Schlüssel in der Befehlszeilenschnittstelle 'bx' einzusetzen:

* Eingabe des Schlüssels mit dem Befehl `bx login`
```
 bx login —apikey <eigener API-Schlüssel>
```
* Erstellen einer API-Schlüsseldatei zur Verwendung mit dem Befehl `bx login` 
 ```
 bx login —apkey @apikeyfile
 ```
 `apikeyfile` wird mit der Option `—file` im Befehl `bx iam api-key-create` erstellt.
* In der Eingabeaufforderung können Sie die Umgebungsvariable festlegen, indem Sie `BLUEMIX_API_KEY=<eigener API-Schlüssel>` und dann `bx login` eingeben.
* Alternativ dazu können Sie, wenn Sie die Befehlszeilenschnittstelle 'bx' nicht verwenden, sondern sich mit Ihrem API-Schlüssel direkt bei der Befehlszeilenschnittstelle 'cf' anmelden möchten, Folgendes eingeben:
 ```
 cf login -u apikey -p <eigener API-Schlüssel>
 ```
  Bei dieser Option verwenden Sie den Benutzernamen `apikey`, das Kennwort ist Ihr `apikey`. Nun können Sie `apikey` in anderen Tools wie Eclipse oder an anderer Stelle mit `cf login` verwenden, wo nur Benutzername und Kennwort akzeptiert werden.

## API-Schlüssel bearbeiten

Wenn Sie den Namen oder die Beschreibung eines API-Schlüssels ändern möchten, führen Sie die folgenden Schritte in der Benutzerschnittstelle oder der Befehlszeilenschnittstelle aus.

Gehen Sie wie folgt vor, um einen API-Schlüssel zu bearbeiten:

1. Wechseln Sie zu **Verwalten** &gt; **Sicherheit** &gt; **Bluemix-API-Schlüssel**.
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

1. Wechseln Sie zu **Verwalten** &gt; **Sicherheit** &gt; **Bluemix-API-Schlüssel**.
2. Klicken Sie im Menü **Aktionen** eines in der Tabelle aufgeführten API-Schlüssels auf **Löschen**.
3. Bestätigen Sie anschließend den Löschvorgang durch Klicken auf **Schlüssel löschen**.

Gehen Sie wie folgt vor, um einen API-Schlüssel über die Befehlszeilenschnittstelle zu löschen:
1. Geben Sie `bluemix iam api-key-delete NAME` in der Eingabeaufforderung ein und geben Sie den Namen des Schlüssels an, der gelöscht werden soll.
