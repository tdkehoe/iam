---

copyright:

  years: 2017, 2018

lastupdated: "2018-08-21"

---

{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:screen: .screen}
{:new_window: target="_blank"}

# Tutoriel d'initiation
{: #getstarted}

Ce tutoriel a pour objectif de vous aider à démarrer et à travailler rapidement avec IBM Cloud Identity and Access Management (IAM) en invitant les utilisateurs de votre compte et en affectant des droits d'accès Cloud IAM à ces utilisateurs.

Ce tutoriel concerne les [ressources](/docs/resources/acct_resources.html#resource) gérées par IAM uniquement. Pour les services qui ne prennent pas en charge la création de règles Cloud IAM pour la gestion des accès, vous pouvez utiliser [Accès Cloud Foundry](/docs/iam/cfaccess.html#cfaccess).


## Etape 1. Inviter des utilisateurs et leur affecter un accès initial

Vous pouvez inviter un ou plusieurs utilisateurs et définir une règle d'accès initiale sur l'invitation pour les utilisateurs. Si vous invitez plusieurs utilisateurs avec une seule invitation, le même accès est accordé à chacun de ces utilisateurs. Dans la section **Accès** de la page Inviter des utilisateurs, vous ne voyez que les sections des accès que vous êtes autorisé à affecter.

En tant que propriétaire de compte, vous pouvez affecter des rôles Cloud IAM aux utilisateurs que vous invitez dans la section Services. Dans la règle initiale que vous affectez dans l'invitation, vous pouvez accorder l'accès à toutes les ressources d'un groupe de ressources, toutes les ressources d'un service spécifique d'un groupe de ressources, toutes les ressources des services avec l'offre Identity and Access activée du compte ou à une seule ressource :

1. Accédez à **Gérer** &gt; **Sécurité** &gt; **Identity and Access**, puis sélectionnez **Utilisateurs**.
2. Cliquez sur **Inviter des utilisateurs**.
3. Indiquez l'adresse électronique de l'utilisateur que vous voulez inviter.
4. Dans la section **Accès**, développez l'option **Services**.
5. Sélectionner d'accorder l'accès à une **Ressource** ou à des ressources d'un **Groupe de ressources**.
6. En fonction de votre sélection, suivez les invites afin de spécifier l'accès à une instance de service individuelle, à tous les services avec l'offre Identity and Access activée, à toutes les ressources d'un groupe de ressources ou à un service spécifique du groupe de ressources sélectionné. Si vous avez sélectionné l'option Groupe de ressources, vous pouvez également accorder à l'utilisateur le droit d'afficher, d'éditer ou de gérer l'accès au groupe de ressources en sélectionnant un rôle pour l'accès au groupe de ressources.
7. Si vous détenez le droit approprié, vous pouvez également affecter un accès à Cloud Foundry ou à l'infrastructure lors de l'invitation.
8. Cliquez sur **Inviter des utilisateurs**.

Pour plus d'informations, voir [Invitation d'utilisateurs et affectation d'accès](/docs/iam/iamuserinv.html#iamuserinv).

## Etape 2. Créer des groupes d'accès

Afin de rationaliser le processus d'affectation d'accès à des utilisateurs de votre compte, vous pouvez créer des groupes d'accès constitués d'utilisateurs et d'ID de service que vous sélectionnez, puis affecter facilement des accès en définissant une seule règle pour l'ensemble du groupe.

### Configuration de vos groupes

Pour créer un groupe d'accès, procédez comme suit :

1. Dans la barre de menus, cliquez sur **Gérer** &gt; **Sécurité** &gt; **Identity and Access**, puis sélectionnez **Groupes d'accès**.
2. Cliquez sur **Créer**.
3. Entrez un nom et une description facultative pour votre groupe, puis cliquez sur **Créer**.

Ensuite, continuez de configurer votre groupe en ajoutant des utilisateurs ou des ID de service :

1. Sélectionnez le nom du groupe sur lequel vous voulez effectuer des ajouts.
2. Cliquez sur **Ajouter des utilisateurs**.
3. Sélectionnez dans la liste les utilisateurs que vous souhaitez ajouter, puis cliquez sur **Ajouter au groupe**.
4. Pour ajouter des ID de service au groupe, cliquez sur l'onglet **ID de service**, puis cliquez sur **Ajouter un ID de service**.
5. Sélectionnez dans la liste les ID que vous souhaitez ajouter, puis cliquez sur **Ajouter au groupe**.

### Affectation d'accès à vos groupes

Une fois votre groupe créé, vous pouvez affecter des accès à toutes les entités du groupe à l'aide d'une seule règle.

1. Dans la barre de menus, cliquez sur **Gérer** &gt; **Sécurité** &gt; **Identity and Access**, puis sélectionnez **Groupes d'accès**.
2. Sélectionnez le nom du groupe auquel vous voulez affecter des accès.
3. Cliquez sur **Affecter un accès** pour définir une règle permettant d'affecter un accès à une seule ressource du compte ou à toutes les ressources d'un groupe de ressources.

Le fait d'organiser des ressources en groupes de ressources et des utilisateurs en groupes d'accès vous permet d'affecter un groupe d'accès utilisateur à un groupe de ressources à l'aide d'une seule règle et de réduire ainsi le nombre global de règles que vous devez gérer.
{: tip}


## Etape 3. Gérer l'accès d'utilisateurs existants

Après avoir invité des utilisateurs, leur avoir affecté un accès initial et avoir créé des groupes d'accès, vous voudrez sans doute leur affecter des accès supplémentaires ou éditer leur accès initial pour vous assurer que tous les utilisateurs et groupes de votre compte bénéficient du niveau d'accès souhaité.

### Affectation d'un nouvel accès

Vous pouvez accorder à un utilisateur l'accès à un groupe de ressources ou à une seule ressource.

1. Dans la barre de menus, cliquez sur **Gérer** &gt; **Sécurité** &gt; **Identity and Access**, puis sélectionnez **Utilisateurs**.
2. Cliquez sur le nom de l'utilisateur auquel vous voulez affecter un accès.
3. Cliquez sur **Affecter un accès**.
4. Choisissez comment vous voulez affecter l'accès :
    * Sélectionnez **Affecter l'accès au sein d'un groupe de ressources** pour accorder l'accès à toutes les ressources d'un groupe ou uniquement aux ressources d'un service spécifique du groupe. Vous pouvez également accorder à l'utilisateur le droit d'afficher, d'éditer ou de gérer l'accès au groupe de ressources en sélectionnant un rôle pour l'accès au groupe de ressources. Sélectionnez **Aucun accès** si vous voulez que l'utilisateur accède uniquement à la ressource que vous indiquez et non au groupe auquel elle appartient.
    * Sélectionnez **Affecter l'accès aux ressources** pour affecter l'accès à toutes les ressources du compte pour lesquelles l'offre Identity and Access est activée, à toutes les ressources d'un service spécifique du compte, à une seule instance ou à une seule ressource d'une instance de service spécifique.
5. Sélectionnez toute combinaison de rôles afin de définir la portée de l'accès. Pour plus d'informations, voir [Rôles Cloud IAM](/docs/iam/users_roles.html#iamusermanrol).
6. Cliquez sur **Affecter**.


### Edition d'un accès existant

Vous pouvez mettre à jour un accès existant en éditant les rôles affectés à un utilisateur.

1. Dans la barre de menus, cliquez sur **Gérer** &gt; **Sécurité** &gt; **Identity and Access**, puis sélectionnez **Utilisateurs**.
2. Sélectionnez le nom de l'utilisateur dont vous voulez éditer l'accès.
3. Depuis la ligne contenant la règle à éditer, cliquez sur **Editer la règle** dans le menu **Actions**.
4. Editez la règle en mettant à jour les rôles affectés.
5. Cliquez sur **Sauvegarder**.

Vous pouvez supprimer l'accès d'un utilisateur en cliquant sur l'option **Retirer** dans le menu **Actions** de la règle que vous voulez retirer.

## Etapes suivantes

Explorez les autres possibilités offertes par Cloud IAM en consultant la liste [Fonctionnalités de Cloud IAM](/docs/iam/index.html#features).
