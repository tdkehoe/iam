---

copyright:

  years: 2015, 2018
lastupdated: "2017-08-23"

---

{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:screen: .screen}
{:new_window: target="_blank"}

# Trabajo con las claves de API
{: #manapikey}

Una clave de interfaz de programación de aplicaciones (clave de API) es un código exclusivo que se pasa en una interfaz de programación de aplicaciones (API) para identificar la aplicación de llamada o el usuario.  Las claves de API se utilizan para realizar un seguimiento y un control sobre la forma la que se utiliza la API, por ejemplo, para impedir un uso malintencionado o abusivo de la misma. La clave de API a menudo actúa a la vez como un identificador exclusivo y como una señal secreta para la autenticación, y habitualmente tiene un conjunto de derechos específicos de la identidad asociado a la misma.

Las claves de API pueden estar asociadas con lo siguiente:

* Users
* ID de servicio

Puede crear y utilizar claves de API que están vinculadas a su cuenta. Un usuario federado o no federado puede crear una clave de API para utilizarla en la CLI o como parte de la automatización para iniciar sesión con su identidad de usuario. Para obtener más información sobre la utilización de una clave de API asociada con su identidad de usuario, consulte [Gestión de las claves de API de usuario](userid_keys.html).

También puede utilizar las claves de API asociadas con los ID de servicio que cree. Los ID de servicio se utilizan para conectar una aplicación dentro o fuera de {{site.data.keyword.Bluemix_notm}} con un servicio de {{site.data.keyword.Bluemix_notm}}. Para obtener más información sobre cómo crear claves de API asociadas con un ID de servicio, consulte [Gestión de claves de API de ID de servicio](serviceid_keys.html).
