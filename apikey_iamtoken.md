---

copyright:
  years: 2018
lastupdated: "2018-05-08"

---


{:shortdesc: .shortdesc}
{:new_window: target="_blank"}
{:codeblock: .codeblock}
{:screen: .screen}
{:tip: .tip}

# How to get an {{site.data.keyword.Bluemix_notm}} IAM token using an API key
{: #iamtoken_from_apikey}

{{site.data.keyword.Bluemix}} APIs can be accessed only by users that are authorized by an assigned IAM role. Therefore, the user calling the API must pass credentials for the API in order to authenticate. You can generate an IAM token by using either your personal or service ID's API key as described here. 

### POST /identity/token

### Headers:
  - Content-Type: application/x-www-form-urlencoded
  - Accept: application/json

### With parameters:
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

### Response:

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
