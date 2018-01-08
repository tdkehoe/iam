---

copyright:

  years: 2015, 2018
lastupdated: "2017-08-23"

---

{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:screen: .screen}
{:new_window: target="_blank"}

# Working with API keys
{: #manapikey}

An application programming interface key (API key) is a unique code that is passed in to an application programming interface (API) to identify the calling application or user.  API keys are used to track and control how the API is being used, for example to prevent malicious use or abuse of the API. The API key often acts as both a unique identifier and a secret token for authentication, and generally has a set of access rights specific to the identity associated with it.

API keys can associated with the following:

* Users
* Service IDs

You can create and use API keys that are linked to your account. A federated or non-federated user can create an API key to use on the CLI or as part of automation to log in as your user identity. For more information about using an API key associated with your user identity, see [Managing user API keys](userid_keys.html).

You can also use API keys that are associated with service IDs that you create. Service IDs are used to connect an application inside or outside of {{site.data.keyword.Bluemix_notm}} to an {{site.data.keyword.Bluemix_notm}} service. For more information about creating API keys associated with a service ID, see [Managing service ID API keys](serviceid_keys.html).
