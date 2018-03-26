---

copyright:

  years: 2015, 2018
lastupdated: "2018-01-26"

---

{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:screen: .screen}
{:new_window: target="_blank"}

# Gestion des clés d'API
{: #manapikey}

Une clé d'interface de programmation (clé d'API) est un code unique transmis à une interface de programmation (API) afin d'identifier l'application ou l'utilisateur appelant.  Les clés d'API permettent de suivre et contrôler la façon dont l'API est utilisée, par exemple pour empêcher toute utilisation malveillante ou abusive de l'API. La clé d'API fait souvent office à la fois d'identificateur unique et de jeton confidentiel pour l'authentification, et dispose généralement de droits d'accès spécifiques de l'identité qui lui est associée.

## Clés d'API de la plateforme

Les clés d'API de la plateforme sont créées dans l'interface utilisateur d'Identity and Access Management et peuvent être associées :

* à l'utilisateur d'un compte
* aux ID de service créés dans un compte

Vous pouvez créer et utiliser des clés d'API qui sont liées à votre compte. Un utilisateur, fédéré ou non, peut créer une clé d'API afin de l'utiliser depuis l'interface CLI ou, dans le cadre de l'automatisation, pour se connecter sous votre identité d'utilisateur. Pour plus d'informations sur l'utilisation d'une clé d'API associée à votre identité utilisateur, voir[Gestion des clés d'API d'utilisateur](userid_keys.html).

Vous pouvez également utiliser les clés d'API associées aux ID de service que vous créez. Les ID de service sont utilisés pour connecter une application à l'intérieur ou à l'extérieur de {{site.data.keyword.Bluemix_notm}} à un service {{site.data.keyword.Bluemix_notm}}. Pour plus d'informations sur la création de clés d'API associées à un ID de service, voir  [Gestion des clés d'API d'ID de service](serviceid_keys.html).

## Autres clés d'{{site.data.keyword.Bluemix_notm}}

Outre les clés d'API de votre plateforme, il existe d'autres types d'API que vous pouvez employer lorsque vous utilisez {{site.data.keyword.Bluemix_notm}} :

* clés d'API de l'infrastructure
* clés d'API spécifiques au service

Les clés d'API de l'infrastructure sont créés dans le portail client et sont associées à l'ID utilisateur de votre compte SoftLayer ; elles sont utilisées lorsque vous accédez aux API des services d'infrastructure.

Certains services dans {{site.data.keyword.Bluemix_notm}} peuvent également fournir une clé d'API que vous utilisez lorsque vous interagissez avec le service. Par exemple, si vous affichez les détails d'un service Watson à partir de votre tableau de bord, vous pouvez créer des données d'identification, qui incluent une clé d'API et une valeur confidentielle, spécifiques uniquement à ce service sur l'onglet Données d'identification pour le service.

