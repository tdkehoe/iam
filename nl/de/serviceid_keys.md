---

copyright:

  years: 2015, 2018
lastupdated: "2018-08-02"

---

{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:screen: .screen}
{:new_window: target="_blank"}
{:tip: .tip}


# API-Schlüssel für Service-IDs verwalten
{: #serviceidapikeys}

Service-IDs werden erstellt, um Anwendungen, die sowohl in als auch außerhalb von {{site.data.keyword.Bluemix_notm}} gehostet werden, den Zugriff auf Ihre {{site.data.keyword.Bluemix_notm}}-Services zu ermöglichen. API-Schlüssel werden von einer Anwendung benutzt, um sich mit einer bestimmten Service-ID zu authentifizieren und den Zugriff zu erhalten, der dieser Service-ID zugeordnet ist.

Nach Erstellung einer Service-ID können Sie mit der Erstellung von API-Schlüsseln und der Zuweisung von Servicerichtlinien beginnen. Jede Richtlinie gibt eine bestimmte Zugriffsebene an, die zulässig ist, wenn der API-Schlüssel zur Authentifizierung bei Ihren Services verwendet wird. Weitere Informationen zur Erstellung einer Service-ID und zur Zuweisung von Richtlinien finden Sie in [Service-IDs erstellen und verwalten](/docs/iam/serviceid.html#serviceids). Detaillierte Informationen zu den CLI-Befehlen, die zur Verwaltung der API-Schlüssel von Service-IDs verwendet werden, sind in [Befehle zur Verwaltung von API-Schlüsseln und Richtlinien](/docs/cli/reference/ibmcloud/cli_api_policy.html#ibmcloud_commands_iam) zu finden.

Jeder API-Schlüssel, der einer Service-ID zugeordnet wurde, übernimmt die Richtlinie, die der Service-ID zugewiesen wurde. Wenn Sie z. B. festlegen möchten, dass eine Anwendung nur zur Anzeige von Ressourcen in einem Service berechtigt sein soll, dann müssen Sie einen API-Schlüssel verwenden, der einer Service-ID zugeordnet ist, für die eine Richtlinie definiert wurde, der die Rolle `Anzeigeberechtigter` zugeordnet wurde. Wenn Sie hingegen für eine andere Anwendung festlegen möchten, dass diese über vollständigen Zugriff innerhalb eines Service verfügen soll, dann müssen Sie einen API-Schlüssel verwenden, dem eine zweite Service-ID zugeordnet ist, für die eine Richtlinie zugewiesen wurde, der die Rolle `Administrator` zugeordnet wurde.

Weitere Informationen finden Sie unter [Beispiele für die Verwendung einer Service-ID](/docs/iam/serviceid.html#examples-of-how-to-use-a-service-id).

## API-Schlüssel für Service-ID erstellen

Erstellen Sie einen API-Schlüssel, der einer Service-ID zugeordnet werden soll.

1. Rufen Sie **Verwalten** &gt; **Sicherheit** &gt; **Identität und Zugriff** &gt; **Service-IDs** auf.
2. Wenn Sie noch keine Service-ID erstellt haben, dann erstellen Sie nun die Service-ID.
3. Rufen Sie im Menü **Aktionen** die Option **Service-ID verwalten** auf.
4. Klicken Sie im Abschnitt für die API-Schlüssel auf **Erstellen**.
5. Fügen Sie einen Namen und eine Beschreibung hinzu, um den API-Schlüssel auf einfache Weise identifizieren zu können.
6. Klicken Sie auf **Erstellen**.
7. Speichern Sie den API-Schlüssel, indem Sie ihn kopieren oder an eine sichere Speicherposition herunterladen.

Aus Sicherheitsgründen kann der API-Schlüssel nur zum Zeitpunkt seiner Erstellung kopiert oder heruntergeladen werden. Wenn der API-Schlüssel verloren geht, müssen Sie einen neuen API-Schlüssel erstellen.
{: tip}

Wenn Sie einen API-Schlüssel für eine Service-ID über die Befehlszeilenschnittstelle erstellen möchten, können Sie den Befehl [ibmcloud iam service-api-key-create](/docs/cli/reference/ibmcloud/cli_api_policy.html#ibmcloud_iam_api_key_create) verwenden.
```
ibmcloud iam service-api-key-create NAME SERVICE_ID [-d, --description DESCRIPTION] [--file FILE] [-f, --force]
```
{: codeblock}

## API-Schlüssel für Service-ID aktualisieren

Sie können einen API-Schlüssel aktualisieren, indem Sie den Namen oder die Beschreibung bearbeiten, der bzw. die zur Identifikation des Schlüssels in der Benutzerschnittstelle verwendet wird.

1. Rufen Sie **Verwalten** &gt; **Sicherheit** &gt; **Identität und Zugriff** &gt; **Service-IDs** auf.
2. Wenn Sie noch keine Service-ID erstellt haben, dann erstellen Sie nun die Service-ID.
3. Rufen Sie im Menü **Aktionen** die Option **Service-ID verwalten** auf.
4. Rufen Sie im Menü **Aktionen** im Abschnitt für die API-Schlüssel die Option **Name & Beschreibung bearbeiten** auf.

Wenn Sie einen API-Schlüssel für eine Service-ID über die Befehlszeilenschnittstelle aktualisieren möchten, können Sie den Befehl [ibmcloud iam service-api-key-update](/docs/cli/reference/ibmcloud/cli_api_policy.html#ibmcloud_iam_api_key_update) verwenden.
```
ibmcloud iam service-api-key-update NAME SERVICE_ID  [-n, --name NEW_sNAME] [-d, --description DESCRIPTION] [-v, --version VERSION] [-f, --force]
```
{: codeblock}

## API-Schlüssel einer Service-ID sperren
{: #lockkey}

Sie können das Löschen von API-Schlüsseln, die die Identität der Service-ID darstellen, verhindern, indem Sie sie sperren. Ein gesperrter API-Schlüssel ist in der Benutzerschnittstelle durch das Symbol ![Sperrsymbol](images/locked.svg "Gesperrt") gekennzeichnet.

1. Klicken Sie in der Menüleiste auf **Verwalten** &gt; **Sicherheit** &gt; **Identität und Zugriff** und wählen Sie dann **Service-IDs** aus.
2. Bestimmen Sie die Zeile der Service-ID, für die Sie einen API-Schlüssel auswählen möchten, und wählen Sie den Namen der Service-ID aus.
3. Wählen Sie **API-Schlüssel** aus.
4. Bewegen Sie den Mauszeiger über die Zeile des API-Schlüssels, der gesperrt werden soll, und klicken Sie auf das Menü **Aktionen**, um eine Liste mit Optionen zu öffnen.
5. Klicken Sie auf **API-Schlüssel sperren**.

Sie können den API-Schlüssel zu jedem beliebigen Zeitpunkt entsperren, um ihn zu aktualisieren, zu löschen oder zu entfernen oder um eine Zugriffsrichtlinie hinzuzufügen.
{: tip}

### API-Schlüssel einer Service-ID über die Befehlszeilenschnittstelle sperren bzw. entsperren

Verwenden Sie den folgenden Befehl, um den API-Schlüssel einer Service-ID zu sperren:

```
ibmcloud iam service-api-key-lock (APIKEY_NAME|APIKEY_UUID) (SERVICE_ID_NAME|SERVICE_ID_UUID) [-f, --force]
```

<strong>Voraussetzungen</strong>: Endpunkt, Anmeldung, Ziel

<strong>Befehlsoptionen</strong>:
<dl>
  <dt>APIKEY_NAME (erforderlich)</dt>
  <dd>Der Name des API-Schlüssels, gegenseitig ausschließend mit APIKEY_UUID</dd>
  <dt>APIKEY_UUID (erforderlich)</dt>
  <dd>Die UUID des API-Schlüssels, gegenseitig ausschließend mit APIKEY_NAME</dd>
  <dt>SERVICE_ID_NAME (erforderlich)</dt>
  <dd>Der Name der Service-ID, gegenseitig ausschließend mit SERVICE_ID_UUID</dd>
  <dt>SERVICE_ID_UUID (erforderlich)</dt>
  <dd>Die UUID der Service-ID, gegenseitig ausschließend mit SERVICE_ID_NAME</dd>
  <dt>-f, --force</dt>
  <dd>Sperren ohne Bestätigung</dd>
</dl>

<strong>Beispiele</strong>:

Service-API-Schlüssel `sample-key` der Service-ID `sample-service` sperren:

```
ibmcloud iam service-api-key-lock sample-key sample-service
```

Verwenden Sie den folgenden Befehl, um den API-Schlüssel einer Service-ID zu entsperren:

```
ibmcloud iam service-api-key-unlock (APIKEY_NAME|APIKEY_UUID) (SERVICE_ID_NAME|SERVICE_ID_UUID) [-f, --force]
```


## API-Schlüssel für Service-ID löschen

Sie können einen API-Schlüssel löschen, der einer Service-ID zugeordnet ist. Allerdings wird durch das Löschen eines momentan durch eine Anwendung benutzten API-Schlüssels dieser Anwendung die Möglichkeit entzogen, sich bei Ihren Services zu authentifizieren.

1. Rufen Sie **Verwalten** &gt; **Sicherheit** &gt; **Identität und Zugriff** &gt; **Service-IDs** auf.
2. Wenn Sie noch keine Service-ID erstellt haben, dann erstellen Sie nun die Service-ID.
3. Rufen Sie im Menü **Aktionen** die Option **Service-ID verwalten** auf.
4. Rufen Sie im Menü **Aktionen** im Abschnitt für die API-Schlüssel die Option **Schlüssel löschen** auf.

Wenn Sie einen API-Schlüssel für eine Service-ID über die Befehlszeilenschnittstelle löschen möchten, können Sie den Befehl [ibmcloud iam service-api-key-delete](/docs/cli/reference/ibmcloud/cli_api_policy.html#ibmcloud_iam_api_key_delete) verwenden.
```
ibmcloud iam service-api-key-delete NAME SERVICE_ID [-f, --force]
```
{: codeblock}
