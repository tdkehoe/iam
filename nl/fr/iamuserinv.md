---

copyright:

  years: 2015, 2018
lastupdated: "2018-10-30"

---

{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:screen: .screen}
{:new_window: target="_blank"}
{:tip: .tip}

# Invitation d'utilisateurs et affectation d'accès
{: #iamuserinv}

Pour inviter des utilisateurs et gérer des invitations en attente, vous devez être propriétaire du compte, responsable de l'organisation ou encore disposer des droits d'infrastructure permettant d'ajouter des utilisateurs. Vous pouvez inviter des utilisateurs, annuler des invitations, et renvoyer une invitation en attente à un utilisateur invité. En outre, vous pouvez inviter un utilisateur unique ou plusieurs utilisateurs à la fois.  
{:shortdesc}

## Invitation d'utilisateurs

Pour inviter des utilisateurs ou gérer les invitations d'utilisateur sur votre compte, procédez comme suit : 

1. Dans la barre de menus, cliquez sur **Gérer** &gt; **Sécurité** &gt; **Identity and Access**, puis sur **Utilisateurs**. La page Utilisateurs affiche une liste d'utilisateurs avec leur adresse électronique et leur statut pour le compte actuellement sélectionné.
2. Cliquez sur **Inviter des utilisateurs**.
3. Spécifiez l'adresse électronique de l'utilisateur. Si vous invitez plusieurs utilisateurs avec une même invitation, ils bénéficient tous du même droit d'accès.
4. Ajoutez une ou plusieurs options d'accès que vous gérez. Vous devez affecter au moins une option d'accès. Pour les options d'accès supplémentaires que vous n'ajoutez ou ne configurez pas, la valeur par défaut *Aucun accès* lui est affectée. L'une des options suivantes ou toutes les options d'accès suivantes peuvent s'afficher, selon celles que vous êtes autorisé à gérer : **Services**, **Accès Cloud Foundry**, **Accès à l'infrastructure {{site.data.keyword.Bluemix_notm}}**. Pour plus d'informations, voir [Octroi d'un accès utilisateur](/docs/iam/iamuserinv.html#assignaccess).

Si vous déterminez qu'un utilisateur n'a pas besoin d'un accès, vous pouvez annuler l'invitation de n'importe quel utilisateur dont l'état indique **En cours de traitement** ou **En attente** dans la colonne **Statut**. Si un utilisateur invité n'a pas reçu d'invitation, vous pouvez renvoyer l'invitation à n'importe quel utilisateur dont l'état indique **En attente**.

Si vous voulez inviter des utilisateurs depuis l'interface de ligne de commande, reportez-vous à la commande [ibmcloud account user-invite](/docs/cli/reference/ibmcloud/cli_acct_org_role.html#ibmcloud_account_user_invite).
{: tip}

## Octroi d'un accès utilisateur
{: #assignaccess}

Vous accordez un accès aux utilisateurs lorsque vous les invitez, en leur affectant des règles Cloud IAM, des accès à Cloud Foundry et des autorisations sur l'infrastructure Cloud Foundry. En fonction des options d'accès que vous êtes autorisé à gérer, vous pouvez inviter des utilisateurs et leur accorder des droits d'accès au niveau du compte, des groupes de ressources, des organisations, des espaces, des instances de service et de l'infrastructure. Les sections ci-après décrivent les trois types d'accès pouvant être accordés à un utilisateur invité.

### Services

Vous pouvez affecter un accès en créant une règle d'accès Cloud IAM initiale lorsque vous invitez un nouvel utilisateur. Dans cette section, vous pouvez accorder un accès utilisateur à des services dans un groupe de ressources avec accès au groupe de ressources ou à une ressource spécifique du compte. Une fois que l'utilisateur a accepté l'invitation, vous pouvez lui accorder des accès supplémentaires. Pour plus d'informations sur l'édition de règles afin d'ajouter des rôles supplémentaires, d'accorder plus de droits d'accès ou de supprimer une règle pour un utilisateur, voir [Gestion d'accès IAM](/docs/iam/mngiam.html#iammanidaccser).

Selon le service que vous sélectionnez lorsque vous affectez la règle, il se peut que les zones décrites dans les procédures suivantes ne soient pas toutes affichées.
{: tip}

#### Accès aux services de gestion de compte

L'octroi à un utilisateur d'un accès aux services de gestion de compte permet de déléguer certaines de vos prérogatives en tant que propriétaire du compte. Par exemple, vous pouvez déléguer l'autorisation d'afficher les informations de facturation et d'utilisation, d'inviter et de supprimer des utilisateurs, de gérer des groupes d'accès ou de gérer des ID de service. Vous pouvez octroyer l'accès à tous les services de gestion de compte ou bien à un seul.

1. Dans l'écran **Inviter des utilisateurs**, développez la section **Services**.
2. Sélectionnez d'affecter l'accès aux **Services de gestion des comptes**
3. Sélectionnez **Tous les services de gestion des comptes** ou bien un service de gestion de compte spécifique.
4. Sélectionnez toute combinaison de rôles pour affecter l'accès voulu.

#### Accès au groupe de ressources

Vous pouvez accorder l'accès à tous les services d'un groupe de ressources ou à un seul type de service d'un groupe de ressources.

1. Dans l'écran **Inviter des utilisateurs**, développez la section **Services**.
2. Sélectionnez d'affecter l'accès aux ressources d'un **groupe de ressources**.
3. Sélectionnez un groupe de ressources.
4. Sélectionnez un rôle dans la zone **Affecter l'accès à un groupe de ressources** pour autoriser l'utilisateur à afficher le groupe de ressources sur le tableau de bord, éditer le nom du groupe de ressources ou gérer l'accès des utilisateurs au groupe. Vous pouvez sélectionner **Aucun accès** si vous voulez que l'utilisateur accède uniquement à la ressource que vous indiquez et non au groupe auquel elle appartient.
5. Sélectionnez un service dans le groupe de ressources ou sélectionnez d'accorder l'accès à tous les services du groupe sélectionné. 
6. Sélectionnez toute combinaison de rôles pour affecter l'accès voulu. Cet accès s'applique uniquement aux ressources sélectionnées pour la règle. Il n'accorde pas l'accès au conteneur que constitue le groupe de ressources.


#### Accès à la ressource

Vous pouvez accorder l'accès à une seule ressource de votre compte jusqu'au niveau instance.

1. Dans l'écran **Inviter des utilisateurs**, développez la section **Services**.
2. Sélectionnez d'affecter l'accès une **ressource**.
3. Sélectionnez un service.
4. Sélectionnez **Toutes les régions en cours** ou une région spécifique, si vous êtes invité à le faire. 
5. Sélectionnez **Toutes les instances de service en cours** ou une instance de service spécifique.
6. Selon le service que vous avez sélectionné, les zones suivantes peuvent s'afficher. Si vous n'entrez pas de valeurs pour ces zones, la règle est affectée au niveau instance de service et au niveau compartiment. 
    * **Type de ressource** : entrez **compartiment**.
    * **ID de ressource** : entrez le nom de votre compartiment
7. Sélectionnez toute combinaison de rôles pour affecter l'accès voulu.

Pour des informations plus précises sur les rôles lors de l'affectation d'accès, voir [Accès IAM](/docs/iam/users_roles.html#iamusermanrol).

### Accès Cloud Foundry

Lorsque vous invitez de nouveaux utilisateurs, vous pouvez choisir d'ajouter l'utilisateur à une organisation dans le compte. Si vous ajoutez l'utilisateur à une organisation, vous pouvez lui attribuer un rôle dans l'organisation. Vous pouvez ensuite accorder à l'utilisateur invité un accès à n'importe quel espace (voire à tous) dans l'organisation sélectionnée, avec le rôle d'espace qui lui est affecté.

1. Dans l'écran **Inviter des utilisateurs**, développez la section **Accès Cloud Foundry**.
2. Sélectionnez une organisation à laquelle ajouter l'utilisateur.
3. Sélectionnez un rôle d'organisation afin de définir le niveau d'accès pour l'organisation sélectionnée.
4. Facultatif : sélectionnez **Ajouter un rôle d'organisation** pour spécifier un rôle supplémentaire.
5. Sélectionnez **Toutes les régions en cours** ou une région spécifique.
6. Sélectionnez **Tous les espaces en cours** ou un espace spécifique.
7. Sélectionnez un rôle d'espace afin de définir un niveau d'accès pour les espaces sélectionnés.
8. Facultatif : sélectionnez **Ajouter un rôle d'espace** pour spécifier un rôle supplémentaire.

Pour plus d'informations sur les rôles, voir [Rôles Cloud Foundry](/docs/iam/cfaccess.html#cfroles).

Vous pouvez ajouter un rôle Cloud Foundry à l'aide de la commande de l'interface de ligne de commande [ibmcloud account user-invite](/docs/cli/reference/ibmcloud/cli_acct_org_role.html#ibmcloud_account_user_invite),
mais vous devez utiliser l'interface utilisateur pour lui accorder d'autres accès ou autorisations.
{: tip}

### Accès à l'infrastructure {{site.data.keyword.BluSoftlayer_notm}}

Les droits accordés sont automatiquement limités au sous-ensemble de droits dont vous disposez. Pour plus d'informations sur les ensembles de droits, voir[Droits relatifs à l'infrastructure](/docs/iam/infrastructureaccess.html#infrapermission).

1. Dans l'écran **Inviter des utilisateurs**, développez la section **Accès Infrastructure**.
2. Sélectionnez un ensemble de droits afin de définir la portée de l'accès.

L'accès aux périphériques est accordé séparément après l'ajout de l'utilisateur par le biais de l'option **Infrastructure** dans la console.
{: tip}

Pour plus d'informations sur la configuration de l'accès des utilisateurs une fois que vous les avez ajoutés à votre compte, voir [Gestion de l'accès à l'infrastructure](/docs/iam/mnginfra.html#managing-infrastructure-access).

## Ajout d'utilisateurs VPN uniquement

En tant que propriétaire d'un compte lié, vous pouvez ajouter un utilisateur VPN uniquement.

1. Cliquez sur l'icône menu ![Icône de menu](../icons/icon_hamburger.svg), puis sélectionnez **Infrastructure**.
2. Accédez à **Compte** &gt; **Utilisateurs**.
3. Cliquez sur **Add VPN Only User**.
4. Entrez les détails des informations personnelles de l'utilisateur. 
5. Cliquez sur **Ajouter un utilisateur**.
6. Définissez les droits sur le portail de l'utilisateur.
7. Cliquez sur **Add Portal Permissions** pour sauvegarder les droits.
8. Définissez l'accès aux périphériques de l'utilisateur.
9. Cliquez sur **Update Device Access** pour sauvegarder et affecter l'accès.
