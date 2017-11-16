---

copyright:

  years: 2017

lastupdated: "2017-11-09"

---

{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:screen: .screen}
{:new_window: target="_blank"}
{:tip: .tip}


# Granting access between services
{: #serviceauth}

Many of the capabilities of the {{site.data.keyword.Bluemix_notm}} Identity and Access Management (IAM) system are focused on managing and enforcing access to {{site.data.keyword.Bluemix_notm}} resources by users and their applications. However, there are other scenarios in which you might need to provide one service with access to a user's resource in another service. All users in your account can create an authorization, but only a user with the `Administrator` role can delete an authorization. You can set up and view authorizations that have been granted within your account on the **Authorizations** page. 

## Create an authorization

You can only grant the level of access that you have as a user of the target service. For example, if you only have viewer access on the service that is going to be accessed, then you can only assign the viewer role for the authorization.

1. From the menu bar, click **Manage** &gt; **Account** &gt; **Identity and Access**, and then select **Authorizations**. 
2. Click **Create authorization**.
3. Select a source and target for the authorization. The source service is given access to the selected target service.
4. Select a role to assign access to the source service when accessing the target service.
5. Click **Authorize**.

**Note**: Only services that allow this type of access to be granted are available as options.

## Remove an authorization

1. From the menu bar, click **Manage** &gt; **Account** &gt; **Identity and Access**, and then select **Authorizations**. 
2. Identify the row for the authorization that you want to remove from the account.
3. From the **Actions** menu, select **Remove authorization**.
5. Select **Remove**.
