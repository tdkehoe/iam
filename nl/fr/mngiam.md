---

copyright:

  years: 2017, 2018

lastupdated: "2018-10-30"

---

{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:screen: .screen}
{:new_window: target="_blank"}
{:tip: .tip}

# Gestion de l'accès aux ressources
{: #iammanidaccser}

Pour gérer les droits d'accès ou en accorder de nouveaux à des utilisateurs en utilisant des règles IAM, vous devez être le propriétaire du compte, l'administrateur de tous les services du compte ou l'administrateur affecté au service ou à l'instance de service spécifique. Pour plus d'informations sur les règles d'accès et les rôles, voir [Accès IAM](/docs/iam/users_roles.html).

## Edition d'un accès existant

1. Dans la barre de menus, cliquez sur **Gérer** &gt; **Sécurité** &gt; **Identity and Access**, puis sélectionnez **Utilisateurs**.
2. Sélectionnez le nom de l'utilisateur auquel vous voulez affecter un accès.
3. Sur la ligne contenant la règle à éditer, sélectionnez le menu **Actions**, puis cliquez sur **Editer la règle**.
4. Editez la règle.
5. Cliquez sur **Sauvegarder**.

Lorsque vous modifiez l'accès pour un utilisateur ou un groupe, un message peut s'afficher indiquant que les règles en double ne sont pas autorisées. Si vous éditez une règle existante et que les modifications effectuées entrent en conflit avec l'accès déjà affecté, vous pouvez choisir de changer la règle en cours d'édition pour offrir un autre accès ou accéder à la règle existante en conflit afin d'effectuer les modifications nécessaires. Vous pouvez également supprimer la règle en cours d'édition s'il existe déjà une règle identique répondant à vos besoins.
{: tip}

Pour mettre à jour une règle utilisateur à l'aide de l'interface CLI, vous pouvez utiliser la commande [ibmcloud iam user-policy-update](/docs/cli/reference/ibmcloud/cli_api_policy.html#ibmcloud_iam_user_policy_update).
```
ibmcloud iam user-policy-update USER_NAME POLICY_ID [-v, --version VERSION] {-f, --file JSON_FILE | [--roles ROLE_NAME1,ROLE_NAME2...] [--service-name SERVICE_NAME] [--service-instance SERVICE_INSTANCE] [--region REGION] [--resource-type RESOURCE_TYPE] [--resource RESOURCE] [--resource-group-name RESOURCE_GROUP_NAME] [--resource-group-id RESOURCE_GROUP_ID]}
```
{: codeblock}

### Affectation d'un nouvel accès
{: #assignaccess}

Vous pouvez affecter un accès via trois types de règle : 

* Accès aux ressources d'un groupe de ressources spécifique avec l'option de n'en inclure qu'une ou de les inclure toutes
* Accès aux ressources du compte avec l'option de n'en inclure qu'un seul type ou de les inclure tous
* Accès aux services de gestion de compte avec l'option de n'inclure qu'un seul service ou de les inclure tous

Si vous désirez accorder à un utilisateur un accès administrateur complet pour lui permettre d'effectuer des tâches comme l'invitation ou la suppression d'utilisateurs, l'affichage de la facturation et de l'utilisation, la gestion des ID service, des groupes d'accès, des accès utilisateur et l'accès à toutes les ressources du compte, vous devez créer deux règles : une sur **Tous les services avec l'offre Identity and Access activée** avec le rôle administrateur et l'autre sur **Tous les services de gestion des comptes** avec le rôle administrateur.
{: tip}

### Accès à des ressources au sein d'un groupe de ressources 

Pour affecter des droits d'accès à toutes les ressources d'un groupe de ressources ou uniquement à un service d'un groupe de ressources, procédez comme suit :

1. Dans la barre de menus, cliquez sur **Gérer** &gt; **Sécurité** &gt; **Identity and Access**, puis sélectionnez **Utilisateurs**.
2. Sur la ligne de l'utilisateur auquel vous voulez affecter un accès, sélectionnez le menu **Actions**, puis cliquez sur **Affecter un accès**.
3. Sélectionnez **Affecter l'accès au sein d'un groupe de ressources**.
4. Sélectionnez un groupe de ressources.
5. Sélectionnez un rôle dans la zone **Affecter l'accès à un groupe de ressources** pour autoriser l'utilisateur à afficher le groupe de ressources sur son tableau de bord, éditer le nom du groupe de ressources ou gérer l'accès des utilisateurs au groupe. Vous pouvez sélectionner **Aucun accès** si vous voulez que l'utilisateur accède uniquement à la ressource que vous indiquez et non au groupe auquel elle appartient.
6. Sélectionnez un service dans le groupe de ressources ou sélectionnez d'accorder l'accès à tous les services du groupe sélectionné.
7. Sélectionnez toute combinaison de rôles pour affecter l'accès voulu à l'utilisateur. Cet accès s'applique uniquement aux ressources sélectionnées pour la règle. Il n'accorde pas l'accès au conteneur réel constitué par le groupe de ressources.
8. Cliquez sur **Affecter**.

### Accès aux ressources
{: #resourceaccess}

Pour affecter des droits d'accès à une ressource individuelle du compte ou l'accès à toutes les ressources du compte, procédez comme suit : 

1. Dans la barre de menus, cliquez sur **Gérer** &gt; **Sécurité** &gt; **Identity and Access**, puis sélectionnez **Utilisateurs**.
2. Sur la ligne de l'utilisateur auquel vous voulez affecter un accès, sélectionnez le menu **Actions**, puis cliquez sur **Affecter un accès**.
3. Sélectionnez **Affecter l'accès aux ressources**.
4. Sélectionnez un service ou sélectionnez **Tous les services avec l'offre Identity and Access activée**.
5. Sélectionnez **Toutes les régions en cours** ou une région spécifique, si vous êtes invité à le faire. 
6. Sélectionnez **Toutes les instances de service en cours** ou une instance de service spécifique.
7. Selon le service que vous avez sélectionné, les zones suivantes peuvent s'afficher. Si vous n'entrez aucune valeur dans ces zones, la règle est affectée au niveau instance de service et non au niveau compartiment. 
    * **Type de ressource** : entrez **compartiment**.
    * **ID de ressource** : entrez le nom de votre compartiment
8. Sélectionnez toute combinaison de rôles pour affecter l'accès voulu à l'utilisateur.
9. Cliquez sur **Affecter**.

Un message peut s'afficher indiquant qu'il existe déjà une règle s'appliquant aux éléments sélectionnés. Si une règle incluant exactement les même rôles et les mêmes détails est créée, vous êtes invité à modifier la nouvelle règle car il n'est pas autorisé d'avoir des règles en double. Si vous créez une règle ayant les mêmes détails qu'une règle existante mais différentes affectations de rôle, vous êtes invité à consulter et mettre à jour la règle existante en incluant les affectations de rôle souhaitées.
{: tip}

### Accès aux services de gestion de compte 

Pour attribuer l'accès à l'un ou à tous les services de gestion de compte, procédez comme suit : 

1. Dans la barre de menus, cliquez sur **Gérer** &gt; **Sécurité** &gt; **Identity and Access**, puis sélectionnez **Utilisateurs**.
2. Sur la ligne de l'utilisateur auquel vous voulez affecter un accès, sélectionnez le menu **Actions**, puis cliquez sur **Affecter un accès**.
3. Sélectionnez d'affecter l'accès aux **Services de gestion des comptes**
4. Sélectionnez **Tous les services de gestion des comptes** ou bien un service de gestion de compte spécifique.
5. Sélectionnez toute combinaison de rôles pour affecter l'accès voulu.


## Retrait de l'accès

1. Dans la barre de menus, cliquez sur **Gérer** &gt; **Sécurité** &gt; **Identity and Access**, puis sélectionnez **Utilisateurs**.
2. Sélectionnez le nom de l'utilisateur auquel vous voulez retirer des l'accès.
3. Sur la ligne contenant la règle à retirer, sélectionnez le menu **Actions**, puis cliquez sur **Retirer**.
4. Revoyez les détails relatifs à la règle que vous êtes sur le point de retirer, puis confirmez le retrait en cliquant sur **Retire**.

Pour retirer une règle utilisateur à l'aide de l'interface CLI, vous pouvez utiliser la commande [ibmcloud iam user-policy-delete](/docs/cli/reference/ibmcloud/cli_api_policy.html#ibmcloud_iam_user_policy_delete).
```
ibmcloud iam user-policy-delete USER_ID POLICY_ID [-f, --force]
```
{: codeblock}

## Révision des accès affectés

Pour vérifier l'accès affecté à un compte auquel vous avez été ajouté, procédez comme suit :

1. Dans la barre de menus, cliquez sur **Gérer** &gt; **Sécurité** &gt; **Identity and Access**, puis sélectionnez **Utilisateurs**.
2. Sélectionnez votre nom.
3. Revoyez les accès affectés dans la section **Règles d'accès**.

Si vous avez besoin d'accès supplémentaires, vous devez contacter le propriétaire du compte afin de mettre à jour vos droits d'accès ou l'administrateur du service ou de l'instance de service pour mettre à jour la règle d'accès Cloud IAM.
