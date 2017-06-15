---

copyright:

  years: 2015, 2017

lastupdated: "2017-05-30"

---

{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:screen: .screen}
{:new_window: target="_blank"}

# Gestion des utilisateurs et de l'accès
{: #iamusermanage}

Vous pouvez afficher et gérer les utilisateurs au niveau du compte ou de l'organisation en fonction des options d'accès que vous êtes habilité à gérer. En tant que propriétaire du compte, vous pouvez gérer les utilisateurs au niveau des options d'accès que vous administrez et pour lesquelles l'accès a été accordé à l'utilisateur sur le compte en cours.
{:shortdesc}

Pour gérer des utilisateurs sur votre compte, procédez comme suit :

1. Dans la barre de menu, cliquez sur **Gérer** &gt; **Compte** &gt; **Utilisateurs**. La fenêtre Utilisateurs affiche une liste d'utilisateurs avec leur adresse électronique et leur statut dans le compte actuellement sélectionné.  
2. Sélectionnez le nom d'utilisateur ou cliquez sur **Gérer un utilisateur** dans le menu **Actions**. 
3. Ensuite, selon l'accès que vous pouvez gérer, mettez à jour l'accès pour l'utilisateur dans les sections Règles de service ou Rôles Cloud Foundry, ou cliquez sur le lien d'accès à la page Affecter l'accès Infrastructure.

Reportez-vous aux sections suivantes pour plus d'informations sur la gestion de chaque type d'accès.

Si vous devez vérifier l'accès qui vous a été affecté sur un compte auquel vous avez ajouté, procédez comme suit :

1. Dans la barre de menu, cliquez sur **Gérer** &gt; **Sécurité** &gt; **Identity & Access** &gt; **Utilisateurs**. 
2. Sélectionnez votre nom. 
3. Passez en revue les rôles qui vous ont été affectés.

Si vous avez besoin d'autorisations supplémentaires, vous devez contacter le responsable de votre organisation ou le propriétaire du compte afin de mettre à jour le rôle Cloud Foundry, ou encore contacter l'administrateur du service ou de l'instance de service pour mettre à jour la règle du service.

Pour plus d'informations sur les commandes CLI utilisées pour gérer les comptes, les organisations, et les espaces, voir [Commandes pour la gestion de comptes, d'organisations et de rôles](https://console.stage1.bluemix.net/docs/cli/reference/bluemix_cli/bx_cli.html#bx_commands_acctorg).

## Accès Cloud Foundry
{: #iammancfser}

Pour pouvoir gérer l'accès à des organisations et des espaces de compte, vous devez être le propriétaire du compte, le responsable de l'organisation ou le responsable de l'espace :

1. Dans la barre de menu, cliquez sur **Gérer** &gt; **Sécurité** &gt; **Identity & Access** &gt; **Utilisateurs**. 
2. Sélectionnez le nom d'utilisateur pour lequel éditer les rôles.
3. Depuis le menu **Actions** de la section Cloud Foundry, vous pouvez :

  * Retirer l'utilisateur de l'organisation
  * Editer le rôle d'organisation
  * Editer le rôle d'espace

Vous pouvez aussi ajouter un utilisateur à une autre organisation en cliquant sur **Affecter une organisation**, si vous êtes le responsable d'une organisation dont l'utilisateur n'est pas encore membre. 


## Services avec l'offre Identity and Access activée
{: #iammanidaccser}

Pour pouvoir gérer les règles de service ou affecter de nouvelles règles de service à des utilisateurs, vous devez être l'administrateur des accès au compte ou l'administrateur désigné pour le service ou l'instance de service spécifique.

1. Dans la barre de menu, cliquez sur **Gérer** &gt; **Sécurité** &gt; **Identity & Access** &gt; **Utilisateurs**. 
2. Sélectionnez le nom d'utilisateur auquel affecter des règles de service.
3. Sélectionnez **Affecter des règles de service** pour créer une règle de service ou depuis le menu **Actions** de la section Règles de service :
  
  * Editez la règle
  * Retirez la règle

Pour plus d'informations sur les règles de service et les rôles, voir [Règles de gestion de l'identité et de l'accès et rôles](/docs/iam/users_roles.html#iamusermanpol).

## Services d'infrastructure

Pour affecter ou mettre à jour des autorisations sur l'infrastructure, cliquez sur le lien **Affecter un accès à l'infrastructure**.
