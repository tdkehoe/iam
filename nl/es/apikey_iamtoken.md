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

# Obtención de una señal de {{site.data.keyword.Bluemix_notm}} IAM mediante una clave de API
{: #iamtoken_from_apikey}

Solo pueden acceder a las API de {{site.data.keyword.Bluemix}} los usuarios autorizados por un rol de IAM asignado. Por lo tanto, el usuario que está llamando a la API debe pasar credenciales para la API para autenticar. Puede generar una señal de IAM utilizando su [clave de API personal](/docs/iam/userid_keys.html#userapikey) o bien una [clave de API del ID de servicio](/docs/iam/serviceid_keys.html#serviceidapikeys). Este proceso también se utiliza si está desarrollando una aplicación que debe trabajar con otros servicios de {{site.data.keyword.Bluemix_notm}}. Debe utilizar una clave API de ID de servicio para obtener una señal de acceso y pasarla a cada uno de los servicios de {{site.data.keyword.Bluemix_notm}}.

1. Utilice el mandato `curl` siguiente para generar una señal de IAM utilizando una clave de API.

### POST /identidad/señal

### Cabeceras
  - Content-Type: application/x-www-form-urlencoded
  - Accept: application/json

### Parámetros
  - grant_type=urn:ibm:params:oauth:grant-type:apikey
  - apikey=*[clave API]*

```
curl -k -X POST \
  --header "Content-Type: application/x-www-form-urlencoded" \
  --header "Accept: application/json" \
  --data-urlencode "grant_type=urn:ibm:params:oauth:grant-type:apikey" \
  --data-urlencode "apikey=<apikey>" \
  "https://iam.bluemix.net/identity/token"
```
{: codeblock}

El ejemplo siguiente es la respuesta esperada:

### Respuesta

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
