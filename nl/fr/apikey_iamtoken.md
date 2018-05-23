---

copyright:
  years: 2018
lastupdated: "2018-05-09"

---


{:shortdesc: .shortdesc}
{:new_window: target="_blank"}
{:codeblock: .codeblock}
{:screen: .screen}
{:tip: .tip}

# Comment obtenir un jeton {{site.data.keyword.Bluemix_notm}} IAM à l'aide d'une clé d'API
{: #iamtoken_from_apikey}

Les API {{site.data.keyword.Bluemix}} ne sont accessibles que par des utilisateurs auxquels un rôle IAM est affecté. Par conséquent, l'utilisateur qui appelle l'API doit transmettre des données d'identification pour l'API afin de s'authentifier. Vous pouvez générer un jeton IAM en utilisant votre clé d'API d'ID de service ou personnelle, comme expliqué ici. Ce processus est également utilisé si vous développez une application qui doit fonctionner avec d'autres services {{site.data.keyword.Bluemix_notm}}. Vous devez utiliser une clé d'API d'ID de service pour obtenir un jeton d'accès à transmettre à chacun des services {{site.data.keyword.Bluemix_notm}}. 

1. Exécutez la commande `curl` suivante pour générer un jeton IAM en utilisant une clé d'API :

### POST /identity/token

### En-têtes :
  - Content-Type: application/x-www-form-urlencoded
  - Accept: application/json

### Avec les paramètres :
  - grant_type=urn:ibm:params:oauth:grant-type:apikey
  - apikey=*[Api key]*

```
curl -k -X POST \
  --header "Content-Type: application/x-www-form-urlencoded" \
  --header "Accept: application/json" \
  --data-urlencode "grant_type=urn:ibm:params:oauth:grant-type:apikey" \
  --data-urlencode "apikey=<apikey>" \
  "https://iam.bluemix.net/identity/token"
```
{: codeblock}

La réponse attendue est présentée ci-dessous :

### Réponse :

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
