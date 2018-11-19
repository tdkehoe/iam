---

copyright:

  years: 2015, 2018
lastupdated: "2018-10-30"

---

{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:screen: .screen}
{:new_window: target="_blank"}

# Gestion des règles d'accès associées aux ID de service
{: #serviceidpolicy}

Lorsque vous créez un ID de service, vous pouvez affecter des règles de service pour cet ID de service afin de contrôler le niveau d'accès autorisé lorsqu'il est utilisé pour l'authentification auprès de vos services. Vous pouvez mettre à jour les règles d'accès affectées à tout moment en changeant une règle existante, en supprimant une règle ou en en affectant une nouvelle.

**Remarque** : le fait de supprimer ou d'éditer une règle existante pour un ID de service en cours d'utilisation peut entraîner une interruption de service.

## Affectation d'un nouvel accès

Pour affecter des droits d'accès à toutes les ressources d'un groupe de ressources ou uniquement à un service d'un groupe de ressources, procédez comme suit :

1. Dans la barre de menus, cliquez sur **Gérer** &gt; **Sécurité** &gt; **Identity and Access** &gt; **ID de service**.
2. Sélectionnez l'ID de service pour laquelle vous souhaitez affecter une règle de service.
3. Cliquez sur **Affecter un accès**.
4. Sélectionnez l'option d'affectation par groupe de ressources****.
5. Sélectionnez un groupe de ressources.
6. Sélectionnez un rôle dans la zone **Affecter l'accès à un groupe de ressources**. Cette option permet à l'utilisateur d'afficher le groupe de ressources sur son tableau de bord, d'éditer le nom du groupe de ressources ou de gérer l'accès des utilisateurs au groupe. Vous pouvez sélectionner **Aucun accès** si vous voulez que l'utilisateur accède uniquement à la ressource que vous indiquez et non au groupe auquel elle est affectée.
7. Sélectionnez un service dans le groupe de ressources ou sélectionnez d'accorder l'accès à tous les services du groupe sélectionné.
8. Sélectionnez toute combinaison de rôles pour affecter l'accès voulu à l'utilisateur. Cet accès s'applique uniquement aux ressources sélectionnées pour la règle. Il n'accorde pas l'accès au conteneur que constitue le groupe de ressources.
9. Sélectionnez **Affecter**.

Pour affecter des droits d'accès à une ressource individuelle du compte, procédez comme suit :

1. Dans la barre de menus, cliquez sur **Gérer** &gt; **Sécurité** &gt; **Identity and Access** &gt; **ID de service**.
2. Sélectionnez l'ID de service pour laquelle vous souhaitez affecter une règle de service.
3. Cliquez sur **Affecter un accès**.
4. Sélectionnez **Assign by resource**.
5. Sélectionnez un service.
6. Sélectionnez **Toutes les régions en cours** ou une région spécifique, si vous êtes invité à le faire.
7. Sélectionnez **Toutes les instances de service en cours** ou une instance de service spécifique.
8. Selon le service que vous avez sélectionné, les zones suivantes peuvent s'afficher. Si vous n'entrez pas de valeurs pour ces zones, la règle est affectée au niveau instance de service et au niveau compartiment.
    * **Type de ressource** : entrez **compartiment**.
    * **ID de ressource** : entrez le nom de votre compartiment
9. Sélectionnez toute combinaison de rôles pour affecter l'accès voulu à l'utilisateur.
10. Sélectionnez **Affecter**.

Pour accorder un accès à des services de gestion de compte individuels ou à tous ces services, procédez comme suit :

1. Dans la barre de menus, cliquez sur **Gérer** &gt; **Sécurité** &gt; **Identity and Access** &gt; **ID de service**.
2. Sélectionnez l'ID de service pour laquelle vous souhaitez affecter une règle de service.
3. Cliquez sur **Affecter un accès**.
4. Sélectionnez d'affecter l'accès aux **Services de gestion des comptes**
5. Sélectionnez **Tous les services de gestion des comptes** ou bien un service de gestion de compte spécifique.
6. Sélectionnez toute combinaison de rôles pour affecter l'accès voulu.




## Edition d'un accès existant

Pour éditer une règle existante :

1. Dans la barre de menus, cliquez sur **Gérer** &gt; **Sécurité** &gt; **Identity and Access** &gt; **ID de service**.
2. Sélectionnez l'ID de service pour laquelle vous souhaitez éditer une règle de service.
3. Identifiez la ligne contenant la règle à éditer, puis sélectionnez **Editer la règle** dans le menu **Actions**.
4. Apportez vos modifications, puis sauvegardez la règle.

Pour mettre à jour une règle de service à l'aide de l'interface CLI, vous pouvez utiliser la commande [ibmcloud iam service-policy-update](/docs/cli/reference/ibmcloud/cli_api_policy.html#ibmcloud_iam_service_policy_update).
```
ibmcloud iam service-policy-update SERVICE_ID POLICY_ID [-v, --version VERSION] {--file JSON_FILE | [-r, --roles ROLE_NAME1,ROLE_NAME2...] [--service-name SERVICE_NAME] [--service-instance SERVICE_INSTANCE] [--region REGION] [--resource-type RESOURCE_TYPE] [--resource RESOURCE] [--resource-group-name RESOURCE_GROUP_NAME] [--resource-group-id RESOURCE_GROUP_ID]} [-f, --force]",
```
{: codeblock}

## Retrait de l'accès

Pour retirer une règle existante :

1. Dans la barre de menus, cliquez sur **Gérer** &gt; **Sécurité** &gt; **Identity and Access** &gt; **ID de service**.
2. Sélectionnez l'ID de service pour laquelle vous souhaitez supprimer une règle de service.
3. Identifiez la ligne contenant la règle à supprimer, puis sélectionnez **Retirer** dans le menu **Actions**.
4. Revoyez les détails relatifs à la règle que vous êtes sur le point de retirer, puis cliquez sur **Retirer** pour confirmer.

Pour supprimer une règle de service à l'aide de l'interface CLI, vous pouvez utiliser la commande [ibmcloud iam service-policy-delete](/docs/cli/reference/ibmcloud/cli_api_policy.html#ibmcloud_iam_service_policy_delete).
```
ibmcloud iam service-policy-delete SERVICE_ID POLICY_ID [-f, --force]
```
{: codeblock}
