---

copyright:

  years: 2018
lastupdated: "2018-10-10"

---

{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:screen: .screen}
{:new_window: target="_blank"}
{:tip: .tip}


# Configuration de groupes d'accès
{: #groups}

Un groupe d'accès peut être créé afin d'organiser un ensemble d'utilisateurs et d'ID de service dans une seule entité et de faciliter l'affectation de droits d'accès. Vous pouvez affecter une seule règle au groupe au lieu d'affecter individuellement le même accès plusieurs fois pour chaque utilisateur ou ID de service.

Pour gérer ou créer des groupes d'accès, vous devez être le propriétaire du compte, l'administrateur ou l'éditeur de tous les services avec l'offre Identity and Access activée dans le compte, ou l'administrateur ou l'éditeur affecté pour le service Groupes d'accès IAM. Pour plus d'informations sur les règles d'accès et les rôles, voir [Accès IAM](/docs/iam/users_roles.html#userroles).

En outre, vous pouvez affecter un administrateur ou un éditeur à un groupe individuel en créant une règle d'accès dans laquelle la ressource est l'ID du groupe d'accès. Un administrateur ou un éditeur de groupe peut mettre à jour et supprimer le groupe, ainsi que créer, mettre à jour et supprimer des membres ou des règles d'accès du groupe. Un utilisateur auquel est affecté le rôle d'afficheur peut uniquement extraire et répertorier des groupes, des membres et les accès affectés. 

Pour faciliter davantage l'affectation et la gestion des accès, vous pouvez configurer des groupes de ressources afin d'organiser un ensemble de ressources auxquelles un groupe d'utilisateurs doit avoir accès. Lorsque votre groupe de ressources est configuré, vous pouvez affecter une règle donnant accès à toutes les ressources au sein de ce groupe au lieu de créer des règles d'accès individuellement pour des instances de service au sein de votre compte. 
{: tip}

## Création d'un groupe d'accès

Pour créer un groupe d'accès, procédez comme suit :

1. Dans la barre de menus, cliquez sur **Gérer** &gt; **Sécurité** &gt; **Identity and Access**, puis sélectionnez **Groupes d'accès**.
2. Cliquez sur **Créer**.
3. Entrez un nom et une description facultative pour votre groupe, puis cliquez sur **Créer**.

Ensuite, continuez de configurer votre groupe en ajoutant des utilisateurs ou des ID de service :

1. Sélectionnez le nom du groupe sur lequel vous voulez effectuer des ajouts.
2. Cliquez sur **Ajouter des utilisateurs** sur l'onglet **Utilisateurs**. 
3. Sélectionnez dans la liste les utilisateurs que vous souhaitez ajouter, puis cliquez sur **Ajouter au groupe**.
4. Pour ajouter des ID de service au groupe, cliquez sur l'onglet **ID de service**, puis cliquez sur **Ajouter un ID de service**.
5. Sélectionnez dans la liste les ID que vous souhaitez ajouter, puis cliquez sur **Ajouter au groupe**.

Vous pouvez supprimer un groupe en sélectionnant l'option **Retirer le groupe**. Lorsque vous retirez un groupe du compte, vous retirez tous les utilisateurs et ID de service du groupe et tous les accès affectés à ce dernier.
{: tip}

Pour créer un groupe d'accès à l'aide de l'interface CLI, vous pouvez utiliser la commande [ibmcloud iam access-group-create](/docs/cli/reference/ibmcloud/cli_api_policy.html#ibmcloud_iam_access_group_create).
```
ibmcloud iam access-group-create GROUP_NAME [-d, --description DESCRIPTION]
```
{: codeblock}


## Affectation d'accès à un groupe

Après avoir configuré votre groupe avec des utilisateurs et des ID de service, vous pouvez affecter une règle d'accès commune au groupe. N'oubliez pas que les règles que vous définissez pour le groupe s'appliquent à toutes les entités qu'il contient.

1. Dans la barre de menus, cliquez sur **Gérer** &gt; **Sécurité** &gt; **Identity and Access**, puis sélectionnez **Groupes d'accès**.
2. Sélectionnez le nom du groupe auquel vous voulez affecter des accès. 
3. Cliquez sur l'onglet **Règles d'accès**.
4. Cliquez sur **Affecter un accès**. 
5. Choisissez d'affecter l'accès à des ressources d'un groupe de ressources ou à des ressources individuelles disponibles dans le compte.

Pour créer une règle de groupe d'accès à l'aide de l'interface CLI, vous pouvez utiliser la commande [ibmcloud iam access-group-policy-create](/docs/cli/reference/ibmcloud/cli_api_policy.html#ibmcloud_iam_access_group_policy_create).
```
ibmcloud iam access-group-policy-create GROUP_NAME {-f, --file @JSON_FILE | --roles ROLE_NAME1,ROLE_NAME2... [--service-name SERVICE_NAME] [--service-instance SERVICE_INSTANCE] [--region REGION] [--resource-type RESOURCE_TYPE] [--resource RESOURCE] [--resource-group-name RESOURCE_GROUP_NAME] [--resource-group-id RESOURCE_GROUP_ID]}
```
{: codeblock}
