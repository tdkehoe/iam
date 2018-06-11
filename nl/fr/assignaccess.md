---

copyright:

  years: 2015, 2018
lastupdated: "2018-05-22"

---

{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:screen: .screen}
{:new_window: target="_blank"}

# Octroi d'un accès utilisateur
{: #assignaccess}

Vous accordez un accès aux utilisateurs lorsque vous les invitez, en leur affectant des rôles, des règles, et des autorisations sur l'infrastructure Cloud Foundry. Vous pouvez inviter des utilisateurs et leur accorder un accès dans les instances de compte, d'organisation, d'espace et de service, en fonction des options d'accès que vous êtes habilité à gérer. Les sections ci-après décrivent les trois types d'accès pouvant être accordés à un utilisateur invité.
{:shortdesc}

## Services avec l'offre Identity and Access activée

Vous pouvez affecter une règle de service unique lorsque vous invitez un nouvel utilisateur. Lorsque l'utilisateur accepte l'invitation, vous pouvez ajouter des règles de service supplémentaires.

1. Dans l'écran **Inviter des utilisateurs**, développez la section **Services avec l'offre Identity and Access activée**.
2. Sélectionnez un service.
3. Sélectionnez **Toutes les régions en cours** ou une région spécifique.
4. Sélectionnez **Toutes les instances de service en cours** ou une instance de service spécifique.
5. Sélectionnez un rôle afin de définir la portée de l'accès pour la règle.
6. Vous pouvez éventuellement sélectionner **Ajouter un rôle** afin de spécifier un autre rôle pour la règle.

Pour plus d'informations sur les rôles à utiliser lors de la définition de règles de service, voir [Règles et rôles IAM (Identity and Access Management)](/docs/iam/users_roles.html#iamusermanpol).

## Accès Cloud Foundry

Lorsque vous invitez de nouveaux utilisateurs, vous pouvez choisir d'ajouter l'utilisateur à une organisation dans le compte. Si vous ajoutez l'utilisateur à une organisation, vous pouvez lui attribuer un rôle dans l'organisation. Vous pouvez ensuite accorder à l'utilisateur invité un accès à n'importe quel espace (voire à tous) dans l'organisation sélectionnée, avec le rôle d'espace qui lui est affecté.

1. Dans l'écran **Inviter des utilisateurs**, développez la section **Accès Cloud Foundry**.
2. Sélectionnez une organisation à laquelle ajouter l'utilisateur.
3. Sélectionnez un rôle dans l'organisation pour définir son niveau d'accès dans l'organisation sélectionnée.
4. Facultatif : sélectionnez **Ajouter un rôle** pour lui attribuer un rôle supplémentaire.
5. Sélectionnez **Toutes les régions en cours** ou une région spécifique.
6. Sélectionnez **Tous les espaces en cours** ou un espace spécifique.
7. Sélectionnez un rôle d'espace pour définir son niveau d'accès aux espaces sélectionnés.
8. Vous pouvez éventuellement sélectionner **Ajouter un rôle** afin de spécifier un autre rôle pour la règle.

Pour plus d'informations sur ces rôles, voir [Rôles Cloud Foundry](/docs/iam/users_roles.html#cfroles).

**Remarque **: vous pouvez ajouter un rôle Cloud Foundry à l'aide de la commande d'interface de ligne de commande [ibmcloud iam account-user-invite](/docs/cli/reference/bluemix_cli/bx_cli.html#ibmcloud_iam_account_user_invite), mais vous devez utiliser l'interface utilisateur pour lui accorder d'autres droits d'accès ou autorisations.

## Accès à l'infrastructure

Les droits réels accordés sont limités automatiquement au sous-ensemble de droits dont vous disposez. Pour plus d'informations sur les droits et les actions que l'utilisateur peut effectuer avec chaque droit, voir [Droits relatifs à l'infrastructure](/docs/iam/users_roles.html#infrapermissions).

1. Dans l'écran **Inviter des utilisateurs**, développez la section **Accès Infrastructure**.
2. Sélectionnez un droit afin de définir la portée de l'accès.

Pour plus d'informations sur la configuration des droits d'accès pour les utilisateurs une fois que vous les avez ajoutés à votre compte, voir [Gestion des utilisateurs et des accès](/docs/iam/iamusermanage.html).
