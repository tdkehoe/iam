---

copyright:
  years: 2018
lastupdated: "2018-09-11"

---


{:shortdesc: .shortdesc}
{:new_window: target="_blank"}
{:codeblock: .codeblock}
{:screen: .screen}
{:tip: .tip}

# {{site.data.keyword.Bluemix_notm}} IAM-Token mithilfe eines API-Schlüssels abrufen
{: #iamtoken_from_apikey}

Auf {{site.data.keyword.Bluemix}}-APIs kann nur von Benutzern zugegriffen werden, die durch eine zugewiesene IAM-Rolle autorisiert sind. Deshalb muss der Benutzer, der die API aufruft, zur Authentifizierung Berechtigungsnachweise für die API übergeben. Sie können ein IAM-Token generieren, indem Sie Ihren [persönlichen API-Schlüssel](/docs/iam/userid_keys.html#userapikey) oder den [API-Schlüssel einer Service-ID](/docs/iam/serviceid_keys.html#serviceidapikeys) verwenden. Dieser Prozess wird auch verwendet, wenn Sie eine Anwendung entwickeln, die mit anderen {{site.data.keyword.Bluemix_notm}}-Services zusammenarbeiten muss. Sie müssen den API-Schlüssel einer Service-ID verwenden, um ein Zugriffstoken abzurufen, das an die einzelnen {{site.data.keyword.Bluemix_notm}}-Services übergeben werden soll.

1. Verwenden Sie den folgenden `curl`-Befehl, um ein IAM-Token mithilfe eines API-Schlüssels zu generieren.

### POST /identity/token

### Header
  - Content-Type: application/x-www-form-urlencoded
  - Accept: application/json

### Parameter
  - grant_type=urn:ibm:params:oauth:grant-type:apikey
  - apikey=*[api-schlüssel]*

```
curl -k -X POST \
  --header "Content-Type: application/x-www-form-urlencoded" \
  --header "Accept: application/json" \
  --data-urlencode "grant_type=urn:ibm:params:oauth:grant-type:apikey" \
  --data-urlencode "apikey=<api-schlüssel>" \
  "https://iam.bluemix.net/identity/token"
```
{: codeblock}

Das folgende Beispiel zeigt, welche Antwort erwartet wird:

### Antwort

```
{
  "access_token": "eyJhbGciOiJIUz......sgrKIi8hdFs",
  "refresh_token": "SPrXw5tBE3......KBQ+luWQVY=",
  "token_type": "Bearer",
  "expires_in": 3600,
  "expiration": 1473188353
}
```
{: codeblock}
