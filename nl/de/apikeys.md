---

copyright:

  years: 2015, 2017
lastupdated: "2017-08-23"

---

{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:screen: .screen}
{:new_window: target="_blank"}

# Mit API-Schlüsseln arbeiten
{: #manapikey}

Bei einem Schlüssel einer Anwendungsprogrammierschnittstelle (API-Schlüssel) handelt es sich um einen eindeutigen Code, der an eine Anwendungsprogrammierschnittstelle (API) übergeben wird, um die aufrufende Anwendung oder den aufrufenden Benutzer zu identifizieren. API-Schlüssel werden verwendet, um zu verfolgen und zu steuern, wie die API verwendet wird, um so z. B. Verwendung in böswilliger Absicht oder Missbrauch der API zu verhindern. Der API-Schlüssel dient oft als eine eindeutige Kennung und geheimes Token für die Authentifizierung. Normalerweise ist ihm eine Gruppe von Zugriffsberechtigungen zugeordnet, die speziell für die ihm zugeordnete Identität gelten. 

API-Schlüssel können den folgenden Entitäten zugeordnet werden:

* Benutzern
* Service-IDs

Sie können API-Schlüssel erstellen und verwenden, die mit Ihrem Konto verknüpft sind. Ein eingebundener oder nicht eingebundener Benutzer kann einen API-Schlüssel erstellen, der in der Befehlszeilenschnittstelle (CLI = Command-Line Interface) oder im Rahmen der automatisierten Anmeldung als Benutzeridentität verwendet wird. Weitere Informationen zur Verwendung eines API-Schlüssels, der Ihrer Benutzeridentität zugeordnet ist, finden Sie in [API-Schlüssel für Benutzer verwalten](userid_keys.html).

Sie können außerdem API-Schlüssel verwenden, die den von Ihnen erstellten Service-IDs zugeordnet sind. Service-IDs werden verwendet, um eine Verbindung zwischen einer Anwendung innerhalb oder außerhalb von {{site.data.keyword.Bluemix_notm}} und einem {{site.data.keyword.Bluemix_notm}}-Service herzustellen. Weitere Informationen zum Erstellen von API-Schlüsseln, die einer Service-ID zugeordnet sind, finden Sie in [API-Schlüssel für Service-IDs verwalten](serviceid_keys.html).


