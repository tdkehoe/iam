---

copyright:

  years: 2015, 2017

lastupdated: "2017-10-06"

---

{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:screen: .screen}
{:new_window: target="_blank"}

# Gestion des utilisateurs et des règles d'accès
{: #iamusermanage}

Vous pouvez afficher et gérer les utilisateurs au niveau du compte ou de l'organisation en fonction des options d'accès que vous êtes habilité à gérer. En tant que propriétaire du compte, vous pouvez gérer les utilisateurs au niveau des options d'accès que vous administrez et pour lesquelles l'accès a été accordé à l'utilisateur sur le compte en cours.
{:shortdesc}

## Gestion des utilisateurs

Pour gérer des utilisateurs sur votre compte, procédez comme suit :

1. Dans la barre de menu, cliquez sur **Gérer** &gt; **Compte** &gt; **Utilisateurs**. La fenêtre Utilisateurs affiche une liste d'utilisateurs avec leur adresse électronique et leur statut dans le compte actuellement sélectionné.
2. Sélectionnez le nom d'utilisateur ou cliquez sur **Gérer un utilisateur** dans le menu **Actions**.
3. Ensuite, selon l'action que vous devez exécuter, vous pouvez choisir de retirer l'utilisateur, d'affecter une nouvelle règle ou de gérer l'accès existant de l'utilisateur.

Reportez-vous aux sections suivantes pour plus d'informations sur la gestion de chaque type d'accès.

Si vous devez vérifier l'accès qui vous a été affecté sur un compte auquel vous avez ajouté, procédez comme suit :

1. Dans la barre de menu, cliquez sur **Gérer** &gt; **Sécurité** &gt; **Identity & Access** &gt; **Utilisateurs**.
2. Sélectionnez votre nom.
3. Passez en revue les rôles qui vous ont été affectés.

Si vous avez besoin d'autorisations supplémentaires, vous devez contacter le responsable de votre organisation ou le propriétaire du compte afin de mettre à jour le rôle Cloud Foundry, ou encore contacter l'administrateur du service ou de l'instance de service pour mettre à jour la règle du service.

Pour plus d'informations sur les commandes CLI utilisées pour gérer les comptes, les organisations, et les espaces, voir [Commandes pour la gestion de comptes, d'organisations et de rôles](/docs/cli/reference/bluemix_cli/bx_cli.html#bx_commands_acctorg).

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


## Règles d'accès au service avec l'offre Identity and Access activée
{: #iammanidaccser}

Pour pouvoir gérer les règles de service ou affecter de nouvelles règles de service à des utilisateurs, vous devez être l'administrateur des accès au compte ou l'administrateur désigné pour le service ou l'instance de service spécifique. Pour plus d'informations sur les règles de service et les rôles, voir [Règles de gestion de l'identité et de l'accès et rôles](/docs/iam/users_roles.html#iamusermanpol). Pour plus d'informations sur les commandes CLI utilisées pour gérer les règles, voir [Commandes de gestion des règles d'API et des règles](/docs/cli/reference/bluemix_cli/bx_cli.html#bx_commands_iam).

### Edition d'une règle existante

1. Dans la barre de menu, cliquez sur **Gérer** &gt; **Sécurité** &gt; **Identity & Access** &gt; **Utilisateurs**.
2. Sélectionnez le nom d'utilisateur auquel affecter des règles de service.
3. Sur la ligne contenant la règle à éditer, sélectionnez le menu **Actions**, puis cliquez sur **Editer la règle**.
4. Editez la règle.
5. Cliquez sur **Sauvegarder la règle**.

### Ajout d'une nouvelle règle

1. Dans la barre de menu, cliquez sur **Gérer** &gt; **Sécurité** &gt; **Identity & Access** &gt; **Utilisateurs**.
2. Sélectionnez le nom d'utilisateur auquel affecter des règles de service.
3. Sélectionnez **Affecter des règles**.
4. Sélectionnez un service.
5. Sélectionnez **Toutes les régions en cours** ou une région spécifique, si vous êtes invité à le faire. 
**Remarque :** il n'est pas nécessaire de sélectionner une région pour tous les services.
6. Sélectionnez **Toutes les instances de service en cours** ou une instance de service spécifique.
7. Selon le service que vous avez sélectionné, les zones suivantes peuvent s'afficher. Si vous n'entrez pas de valeurs pour ces zones, la règle est affectée au niveau instance de service et au niveau compartiment.  
    * **Type de ressource** : entrez **bucket**.
    * **Ressource** : entrez le nom de votre compartiment. 
8. Sélectionnez un rôle afin de définir la portée de l'accès pour la règle.
9. Facultatif : sélectionnez **Ajouter un rôle** afin de spécifier un rôle supplémentaire pour la règle.

### Retrait d'une règle

1. Dans la barre de menu, cliquez sur **Gérer** &gt; **Sécurité** &gt; **Identity & Access** &gt; **Utilisateurs**.
2. Sélectionnez le nom d'utilisateur auquel affecter des règles de service.
3. Sur la ligne contenant la règle à retirer, sélectionnez le menu **Actions**, puis cliquez sur **Supprimer la règle**.
4. Consultez les détails relatifs à la règle que vous êtes sur le point de retirer, puis confirmez le retrait en cliquant sur **Supprimer la règle**.
  

## Droits relatifs aux services d'infrastructure

Pour affecter ou mettre à jour des droits relatifs à une infrastructure, cliquez sur le lien **Affecter un accès à l'infrastructure**.

