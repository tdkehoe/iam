---

copyright:

  years: 2015, 2017
lastupdated: "2017-12-07"

---

{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:screen: .screen}
{:new_window: target="_blank"}

# API-Schlüssel für Service-IDs verwalten
{: #serviceidapikeys}

Service-IDs werden erstellt, um Anwendungen, die sowohl in als auch außerhalb von {{site.data.keyword.Bluemix_notm}} gehostet werden, den Zugriff auf Ihre {{site.data.keyword.Bluemix_notm}}-Services zu ermöglichen. API-Schlüssel werden von einer Anwendung benutzt, um sich mit einer bestimmten Service-ID zu authentifizieren und den Zugriff zu erhalten, der dieser Service-ID zugeordnet ist.

Nach Erstellung einer Service-ID können Sie mit der Erstellung von API-Schlüsseln und der Zuweisung von Servicerichtlinien beginnen. Jede Richtlinie gibt eine bestimmte Zugriffsebene an, die zulässig ist, wenn der API-Schlüssel zur Authentifizierung bei Ihren Services verwendet wird. Weitere Informationen zur Erstellung einer Service-ID und zur Zuweisung von Richtlinien finden Sie in [Service-IDs erstellen und verwalten](/docs/iam/serviceid.html#serviceids). Detaillierte Informationen zu den CLI-Befehlen, die zur Verwaltung der API-Schlüssel von Service-IDs verwendet werden, sind in [Befehle zur Verwaltung von API-Schlüsseln und Richtlinien](/docs/cli/reference/bluemix_cli/bx_cli.html#bx_commands_iam) zu finden.

Jeder API-Schlüssel, der einer Service-ID zugeordnet wurde, übernimmt die Richtlinie, die der Service-ID zugewiesen wurde. Wenn Sie z. B. festlegen möchten, dass eine Anwendung nur zur Anzeige von Ressourcen in einem Service berechtigt sein soll, dann müssen Sie einen API-Schlüssel verwenden, der einer Service-ID zugeordnet ist, für die eine Richtlinie definiert wurde, der die Rolle `Anzeigeberechtigter` zugeordnet wurde. Wenn Sie hingegen für eine andere Anwendung festlegen möchten, dass diese über vollständigen Zugriff innerhalb eines Service verfügen soll, dann müssen Sie einen API-Schlüssel verwenden, dem eine zweite Service-ID zugeordnet ist, für die eine Richtlinie zugewiesen wurde, der die Rolle `Administrator` zugeordnet wurde.

## API-Schlüssel für Service-ID erstellen

Erstellen Sie einen API-Schlüssel, der einer Service-ID zugeordnet werden soll.

1. Rufen Sie **Verwalten** &gt; **Sicherheit** &gt; **Identität und Zugriff** &gt; **Service-IDs** auf. 
2. Wenn Sie noch keine Service-ID erstellt haben, dann erstellen Sie nun die Service-ID.
3. Rufen Sie im Menü **Aktionen** die Option **Service-ID verwalten** auf.
4. Klicken Sie im Abschnitt für die API-Schlüssel auf **Erstellen**.
5. Fügen Sie einen Namen und eine Beschreibung hinzu, um den API-Schlüssel auf einfache Weise identifizieren zu können.
6. Klicken Sie auf **Erstellen**.
7. Speichern Sie den API-Schlüssel, indem Sie ihn kopieren oder an eine sichere Speicherposition herunterladen.

**Hinweis:** Aus Sicherheitsgründen kann der API-Schlüssel nur zum Zeitpunkt seiner Erstellung kopiert oder heruntergeladen werden. Wenn der API-Schlüssel verloren geht, müssen Sie einen neuen API-Schlüssel erstellen.

## API-Schlüssel für Service-ID aktualisieren

Sie können einen API-Schlüssel aktualisieren, indem Sie den Namen oder die Beschreibung bearbeiten, der bzw. die zur Identifikation des Schlüssels in der Benutzerschnittstelle verwendet wird.

1. Rufen Sie **Verwalten** &gt; **Sicherheit** &gt; **Identität und Zugriff** &gt; **Service-IDs** auf. 
2. Wenn Sie noch keine Service-ID erstellt haben, dann erstellen Sie nun die Service-ID.
3. Rufen Sie im Menü **Aktionen** die Option **Service-ID verwalten** auf.
4. Rufen Sie im Menü **Aktionen** im Abschnitt für die API-Schlüssel die Option **Name & Beschreibung bearbeiten** auf.


## API-Schlüssel für Service-ID löschen

Sie können einen API-Schlüssel löschen, der einer Service-ID zugeordnet ist. Allerdings wird durch das Löschen eines momentan durch eine Anwendung benutzten API-Schlüssels dieser Anwendung die Möglichkeit entzogen, sich bei Ihren Services zu authentifizieren.

1. Rufen Sie **Verwalten** &gt; **Sicherheit** &gt; **Identität und Zugriff** &gt; **Service-IDs** auf. 
2. Wenn Sie noch keine Service-ID erstellt haben, dann erstellen Sie nun die Service-ID.
3. Rufen Sie im Menü **Aktionen** die Option **Service-ID verwalten** auf.
4. Rufen Sie im Menü **Aktionen** im Abschnitt für die API-Schlüssel die Option **Schlüssel löschen** auf.


