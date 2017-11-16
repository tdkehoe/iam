---

copyright:

  years: 2017

lastupdated: "2017-10-22"

---

{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:screen: .screen}
{:new_window: target="_blank"}

# IAM and Cloud Foundry access models
{: #accessmodels}

Currently, not all {{site.data.keyword.Bluemix_notm}} services support using Cloud IAM access management. Services that have not enabled the use of Cloud IAM continue to rely on a user’s role in a Cloud Foundry org and space to determine whether a user has permission to access the resources. You can use the {{site.data.keyword.Bluemix_notm}} Identity and Access UI to manage access for services that use the Cloud IAM or Cloud Foundry access management systems.


## Cloud Foundry services switching to Cloud IAM
{: #cftoiam}

If you are currently using a Cloud Foundry service that starts supporting the use of Cloud IAM access management, you will receive a notification that you can now take advantage of access control with IAM for new service instances that you create.

As services start to enable the use of Cloud IAM, you can expect the following:

* For existing instances in your account that already use Cloud Foundry access management by assigning users to an org and space with a Cloud Foundry role, you can continue to use those instances without any changes.
* For creating new instances, you assign each to a resource group in your account, and then you can use Cloud IAM to manage access to that instance and to the resource group to which it belongs, if you are administrator on the resource group.

Services that support using Cloud IAM have several benefits including the ability to connect to apps and services in any Cloud Foundry space, which allows you to connect apps and services from different regions. In addition, each instance managed by Cloud IAM belongs to a resource group, and resource groups are not scoped by region, so you can provision apps and services from different regions into the same resource group. You also have the ability to use fine-grained access control down to an individual instance. 

