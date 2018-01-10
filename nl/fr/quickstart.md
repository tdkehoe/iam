---

copyright:

  years: 2017

lastupdated: "2017-11-16"

---

{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:screen: .screen}
{:new_window: target="_blank"}

# Tutoriel d'initiation
{: #getstarted}

Ce tutoriel a pour objectif de vous aider à démarrer et à travailler rapidement avec IBM Cloud Identity and Access Management (IAM) en invitant les utilisateurs de votre compte et en affectant des droits d'accès Cloud IAM à ces utilisateurs. 

Ce tutoriel concerne les ressources gérées par IAM. Pour les services qui ne prennent pas en charge la création de règles Cloud IAM pour la gestion des accès, vous pouvez utiliser [Accès Cloud Foundry](/docs/iam/cfaccess.html#cfaccess). 


## Etape 1 : invitez des utilisateurs et affectez-leur un accès initial

Vous pouvez inviter un ou plusieurs utilisateurs et définir une règle d'accès initiale sur l'invitation pour ces utilisateurs. Si vous invitez plusieurs utilisateurs avec une seule invitation, le même accès est accordé à chacun de ces utilisateurs. Dans la section Accès de la page Inviter des utilisateurs, vous ne voyez que les sections des accès que vous êtes autorisé à affecter.

En tant que propriétaire de compte, vous pouvez affecter des rôles Cloud IAM aux utilisateurs que vous invitez dans la section Services. Dans la règle initiale que vous affectez dans l'invitation, vous pouvez accorder l'accès à toutes les ressources d'un groupe de ressources, toutes les ressources d'un service spécifique d'un groupe de ressources, toutes les ressources des services avec l'offre Identity and Access activée du compte ou à une seule ressource :

1. Accédez à **Gérer** &gt; **Sécurité** &gt; **Identity and Access**, puis sélectionnez **Utilisateurs**.
2. Cliquez sur **Inviter des utilisateurs**.
3. Indiquez l'adresse électronique de l'utilisateur que vous voulez inviter.
4. Dans la section **Accès**, développez l'option **Services**.
5. Sélectionner d'accorder l'accès à une **Ressource** ou à des ressources d'un **Groupe de ressources**.
6. En fonction de votre sélection, suivez les invites afin de spécifier l'accès à une instance de service individuelle, à tous les services avec l'offre Identity and Access activée, à toutes les ressources d'un groupe de ressources ou à un service spécifique du groupe de ressources sélectionné. Si vous avez sélectionné l'option Groupe de ressources, vous pouvez également accorder à l'utilisateur le droit d'afficher, d'éditer ou de gérer l'accès au groupe de ressources en sélectionnant un rôle pour l'accès au groupe de ressources.
7. Si vous détenez le droit approprié, vous pouvez également affecter un accès Cloud Foundry ou à l'infrastructure sur l'invitation.
8. Cliquez sur **Inviter des utilisateurs**.

Pour plus d'informations, voir [Invitation d'utilisateurs et affectation d'accès](/docs/iam/iamuserinv.html#iamuserinv).

## Etape 2 : Gérez l'accès d'utilisateurs existants

Après avoir invité des utilisateurs et leur avoir affecté un accès initial, vous voudrez sans doute leur affecter des accès supplémentaires ou éditer leur accès initial pour vous assure que tous les utilisateurs de votre compte bénéficient du niveau d'accès souhaité.

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
