---

copyright:

  years: 2015, 2018
lastupdated: "2017-08-23"

---

{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:screen: .screen}
{:new_window: target="_blank"}

# Gestion des clés d'API
{: #manapikey}

Une clé d'interface de programmation (clé d'API) est un code unique transmis à une interface de programmation (API) afin d'identifier l'application ou l'utilisateur appelant.  Les clés d'API permettent de suivre et contrôler la façon dont l'API est utilisée, par exemple pour empêcher toute utilisation malveillante ou abusive de l'API. La clé d'API fait souvent office à la fois d'identificateur unique et de jeton confidentiel pour l'authentification, et dispose généralement de droits d'accès spécifiques de l'identité qui lui est associée.

Les clés d'API peuvent être associées aux éléments suivants :

* Utilisateurs
* ID de service

Vous pouvez créer et utiliser des clés d'API qui sont liées à votre compte. Un utilisateur, fédéré ou non, peut créer une clé d'API afin de l'utiliser depuis l'interface CLI ou, dans le cadre de l'automatisation, pour se connecter sous votre identité d'utilisateur. Pour plus d'informations sur l'utilisation d'une clé d'API associée à votre identité utilisateur, voir[Gestion des clés d'API d'utilisateur](userid_keys.html).

Vous pouvez également utiliser les clés d'API associées aux ID de service que vous créez. Les ID de service sont utilisés pour connecter une application à l'intérieur ou à l'extérieur de {{site.data.keyword.Bluemix_notm}} à un service {{site.data.keyword.Bluemix_notm}}. Pour plus d'informations sur la création de clés d'API associées à un ID de service, voir  [Gestion des clés d'API d'ID de service](serviceid_keys.html).
