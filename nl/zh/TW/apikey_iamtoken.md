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

# 使用 API 金鑰取得 {{site.data.keyword.Bluemix_notm}} IAM 記號
{: #iamtoken_from_apikey}

{{site.data.keyword.Bluemix}} API 只能由被指派的 IAM 角色所授權的使用者存取。因此，呼叫 API 的使用者必須傳遞認證，API 才能進行鑑別。您可以[個人 API 金鑰](/docs/iam/userid_keys.html#userapikey)或[服務 ID 的 API 金鑰](/docs/iam/serviceid_keys.html#serviceidapikeys)來產生 IAM 記號。如果您要開發需要使用其他 {{site.data.keyword.Bluemix_notm}} 服務的應用程式，也會使用此處理程序。您必須使用服務 ID API 金鑰，讓存取記號傳遞給每個 {{site.data.keyword.Bluemix_notm}} 服務。

1. 使用下列 `curl` 指令，以利用 API 金鑰產生 IAM 記號。

### POST /identity/token

### 標頭
  - Content-Type: application/x-www-form-urlencoded
  - Accept: application/json

### 參數
  - grant_type=urn:ibm:params:oauth:grant-type:apikey
  - apikey=*[API 金鑰]*

```
curl -k -X POST \
  --header "Content-Type: application/x-www-form-urlencoded" \
  --header "Accept: application/json" \
  --data-urlencode "grant_type=urn:ibm:params:oauth:grant-type:apikey" \
  --data-urlencode "apikey=<apikey>" \
  "https://iam.bluemix.net/identity/token"
```
{: codeblock}

下列範例是預期的回應：

### 回應

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
