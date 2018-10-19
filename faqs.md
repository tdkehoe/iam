---



copyright:

  years: 2018

lastupdated: "2018-10-17"



---

{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:screen: .screen}
{:new_window: target="_blank"}
{:tip: .tip}

# FAQs
{: #iamfaq}

## What is {{site.data.keyword.cloud_notm}} Identity and Access Management? 
{: #whatisiam}

Identity and Access Management (IAM) enables you to securely authenticate users for platform services and control access to resources across the {{site.data.keyword.cloud_notm}} platform. A set of IBM Cloud services are enabled to use Cloud IAM for access control. They are organized into resource groups within your account to enable giving users quick and easy access to more than one resource at a time. Cloud IAM access policies are used to assign users and service IDs access to the resources within your account. For more information, see [{{site.data.keyword.cloud_notm}} Identity and Access Management](/docs/iam/index.html#iamoverview).

## What is an IAM-enabled service?
{: #iam-enabled}

An IAM-enabled service must be in a resource group and access to the service is given by using IAM access policies. When you create an IAM-enabled service from the catalog, you must assign it to a resource group. For more information, see [What is a resource?](/docs/resources/acct_resources.html#resource)

{{site.data.keyword.containerlong_notm}} is the only exception; it’s IAM-access controlled, but it is always assigned to the default resource group. Therefore, you aren’t given the option to choose one when you create it from the catalog. And, it can’t be assigned to any other resource group


## Are IAM and Cloud Foundry related?
{: #iam-cloudfoundry}

They aren't related. Cloud Foundry is an open source platform that uses organizations, spaces, and Cloud Foundry roles for access management. IAM is the secure way to authenticate users for platform services and control access to resources across the {{site.data.keyword.cloud_notm}} platform by using resource groups and IAM access roles.

The access management systems are entirely different. IAM resources belong to a resource group and Cloud Foundry resources belong to an organization and space. IAM access policies are used to provide access to resources in a resource group. And, Cloud Foundry org and space roles are used to provide users access to Cloud Foundry resources in a space. IAM doesn’t give you access to anything within Cloud Foundry spaces, and Cloud Foundry roles can’t grant access to resources within a resource group.

## How do I find out what I have access to?
{: #iam-access}

Go to **Manage** &gt; **Access (IAM)**, and select your name in the User column. Then, depending on the access you're looking for, open the different tabs:

* To determine which access groups you're in, select **Access group**.
* For IAM access, select the **Access policies**.
* For Cloud Foundry roles, select **Cloud Foundry access**.

## How do I request access to a resource?
{: #request-access}

The account owner can update your access to any resource in the account, or you can contact any user who is assigned the administrator role on the service or service instance. 

## Why should I use resource groups and access groups?? 
{: #resource-groups}

A resource group is a logical container for resources. When a resource is created, it's assigned to a resource group and can’t be moved after it's added. 

An access group is used to easily organize a set of users and service IDs into a single entity to make access assignments easy. You can assign a single policy to an access group to grant all members those permissions. If you have more than one user or service ID that needs the same access, create an access group instead of assigning the same access multiple times per individual user or service ID.

By using both resource groups and access groups, you can streamline the access assignment policy by assigning a limited number of policies. You can organize all the resources a specific group of users and service IDs needs access to in a single resource group, group all the users or service IDs into an access group, and then assign a single policy giving access to all resources in the resource group.

## How do I ensure that my users can create resources within a resource group?
{: #resources}

To create a resource in a resource group, the user must have two access policies: one assigned to the resource group itself, and one assigned to the resources in the group. Access to the resource group itself is simply access to the container that organizes the resources, and this type of policy allows a user to view, edit, or manage access to the group, but not the resources within it. Access to services within the resource group enables a user to work with the service instances, which means the user can create a service instance.

So, minimally the user must have the following access:

* Viewer role or higher on the resource group itself
* Editor role or higher on the service or all services in the resource group


## What access do I need to provide others access?
{: #user-access}

You must have administrator role on the service or resource that you want to assign users access to. If you want to assign access to all services or resources in the account, you need a policy on all Identity and Access enabled services with the administrator role. 

## What's the difference between providing access to manage a resource group versus access to resources within a resource group?
{: #providing-access}

When you have access to manage a resource group, you can view, edit the name, and manage access for the resource group itself depending on the assigned role. Access to a resource group itself doesn't give a user access to the resources within the group.

When you have access to resources within a resource group, you can edit, delete, and create instances, or have all management actions for the specified services within the resource group depending on the assigned role. 

For example platform management roles and actions for account management services, see [Platform roles table](/docs/iam/users_roles.html#platformrolestable2).

## Who can remove users?
{: #remove-users}

Only the account owner can remove users. 

## How do I turn on multi-factor authentication?
{: #multi-factor}

Go to **Manage** &gt; **Access (IAM)**, and choose **Settings**. 
Choose **Multi-factor authentication**, and then click **Apply changes**. For more information, see [Enabling multi-factor authentication](/docs/iam/mfa.html#enablemfa).

## What is the difference between service and platform roles? 
{: #service-platform-roles}

Service and platform roles are two different types of roles: 

* Platform roles are how you work with a service within an account such as creating instances, binding instances, and managing user's access to the service. For platform services these roles enable users to create resource groups and manage service IDs, for example. Platform roles are: administrator, editor, operator, and viewer. 

* Service roles define the ability to perform actions on a service and are specific to every service such as performing API calls or accessing the UI. Service roles are: manager, writer, and reader. For more information about how these roles apply, refer to the specific service's documentation.

## What is the difference between a resource group and Cloud Foundry orgs and spaces?
{: #groups-organizations}

With the start of {{site.data.keyword.Bluemix_notm}}, an open source platform service for access control and the organization of resources called Cloud Foundry was the single method for organizing and controlling access to resources. As {{site.data.keyword.Bluemix_notm}} has expanded, a new method was needed that could be used by all types of services and resources. Resource groups are now used to group and organize many types of resources, and IAM is used to consistently control access to services and resources. A number of services have already adopted using resource groups and IAM, and additional services will move over time to the new method for organizing resources and managing access.

Access control and account resource organization are the major differences between resource groups and Cloud Foundry orgs and spaces. Resource groups organize IAM-enabled services in an account that are access controlled by using IAM policies. Orgs and spaces are managed by using Cloud Foundry roles for access control, and Cloud Foundry resources are assigned to spaces. Orgs and spaces can be used to organize and control access to resources only within the Cloud Foundry realm, while resource groups and IAM can be used for multiple types of resources across {{site.data.keyword.Bluemix_notm}}.

