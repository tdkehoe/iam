---

copyright:

  years: 2015, 2017
lastupdated: "2017-06-27"

---

{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:screen: .screen}
{:new_window: target="_blank"}

# Managing service ID access policies
{: #serviceidpolicy}

When you create a service ID, you can assign service policies for that service ID to control the level of access that is allowed when it is used to authenticate with your services. You can update these assigned access policies at any time by changing an existing policy, deleting a policy, or assigning a new one. 

**Note**: If you delete or edit an existing policy for a service ID currently being used, it might cause service interupption.

## Assigning new policies

To assign a new policy:

1. From the menu bar, click **Manage** &gt; **Security** &gt; **Identity & Access** &gt; **Service IDs**.
2. Select the service ID from the table that you want to assign a service policy for.
3. Click **Assign policies**.
4. Select the service from the list that you want to define permissions for.
5. Optional: Click **Specify optional service context**, if you want to refine the region and service instance for the policy.
6. Select the role that you want to assign.
7. Optional: Select **Add role** if you want to add additional roles for the policy.

## Editing existing policies

To edit an existing policy:

1. From the menu bar, click **Manage** &gt; **Security** &gt; **Identity & Access** &gt; **Service IDs**.
2. Select the service ID from the table that you want to edit a service policy for.
3. Identify the row of the policy that you want to edit, and select **Edit policy** from the **Actions** menu.
4. Make your changes, and then save the policy.

## Deleting existing policies

To delete an existing policy:

1. From the menu bar, click **Manage** &gt; **Security** &gt; **Identity & Access** &gt; **Service IDs**.
2. Select the service ID from the table that you want to delete a service policy for.
3. Identify the row of the policy that you want to delete, and select **Remove policy** from the **Actions** menu.
4. Make your changes, and then save the policy.
