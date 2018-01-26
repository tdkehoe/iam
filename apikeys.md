---

copyright:

  years: 2015, 2018
lastupdated: "2018-01-26"

---

{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:screen: .screen}
{:new_window: target="_blank"}

# Working with API keys
{: #manapikey}

An application programming interface key (API key) is a unique code that is passed in to an application programming interface (API) to identify the calling application or user.  API keys are used to track and control how the API is being used, for example to prevent malicious use or abuse of the API. The API key often acts as both a unique identifier and a secret token for authentication, and generally has a set of access rights specific to the identity associated with it.

## Platform API keys

Platform API keys are created in the Identity and Access Management UI and can be associated with the following:

* User of an account
* Service IDs created in an account

You can create and use API keys that are linked to your account. A federated or non-federated user can create an API key to use on the CLI or as part of automation to log in as your user identity. For more information about using an API key associated with your user identity, see [Managing user API keys](userid_keys.html).

You can also use API keys that are associated with service IDs that you create. Service IDs are used to connect an application inside or outside of {{site.data.keyword.Bluemix_notm}} to an {{site.data.keyword.Bluemix_notm}} service. For more information about creating API keys associated with a service ID, see [Managing service ID API keys](serviceid_keys.html).

## Other {{site.data.keyword.Bluemix_notm}} API keys

In addition to your platform API keys, there are a couple other types of API keys that you might use while using {{site.data.keyword.Bluemix_notm}}:

* Infrastructure API keys
* Service-specific API keys

Infrastructure API keys are created in the customer portal and are associated with your SoftLayer account user ID and are used when accessing the APIs for infrastructure services.

Some services in {{site.data.keyword.Bluemix_notm}} might also provide an API key for you to use when interacting with the service. For example, if you are viewing the service details of a Watson service from your dashboard, you can create a credential, which includes an API key and secret, that is specific to just that service on the Service Credentials tab.

