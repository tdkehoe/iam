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

# 如何使用 API 密钥获取 {{site.data.keyword.Bluemix_notm}} IAM 令牌
{: #iamtoken_from_apikey}

只有获得了 IAM 角色授权的用户才能访问 {{site.data.keyword.Bluemix}} API。因此，用户在调用 API 时必须传递 API 的凭证，才能通过认证。您可以根据此处的说明，使用个人或服务标识的 API 密钥来生成 IAM 令牌。如果要开发的应用程序需要使用其他 {{site.data.keyword.Bluemix_notm}} 服务，也可以使用此过程。要使访问令牌能够传递到每个 {{site.data.keyword.Bluemix_notm}} 服务，必须使用服务标识 API 密钥。

1. 要使用 API 密钥生成 IAM 令牌，请使用以下 `curl` 命令。

### POST /identity/token

### 头：
  - Content-Type: application/x-www-form-urlencoded
  - Accept: application/json

### 参数：
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

下面是预期的响应：

### 响应：

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
