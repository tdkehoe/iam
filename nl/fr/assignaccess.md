---

copyright:

  years: 2015, 2017
lastupdated: "2017-05-30"

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

Vous pouvez affecter une règle de service unique lorsque vous invitez un nouvel utilisateur. Une fois que l'utilisateur a accepté l'invitation, vous pouvez ajouter des règles de service supplémentaires.

1. Dans l'écran **Inviter des utilisateurs**, développez la section **Services avec l'offre Identity and Access activée**.
2. Sélectionnez un service.
3. Sélectionnez **Toutes les régions en cours** ou une région spécifique.
4. Sélectionnez **Toutes les instances de service en cours** ou une instance de service spécifique.
5. Sélectionnez un rôle afin de définir la portée de l'accès pour la règle.
6. Facultatif : sélectionnez **Ajouter un rôle** afin de spécifier un rôle supplémentaire pour la règle.

Voir [Règles et rôles dans Identity and Access Management](/docs/iam/users_roles.html#iamusermanpol) pour plus d'informations sur les rôles lors de la définition de règles de services.

## Accès Cloud Foundry

Lorsque vous invitez de nouveaux utilisateurs, vous pouvez choisir d'ajouter l'utilisateur à une organisation dans le compte. Si vous ajoutez l'utilisateur à une organisation, le rôle d'organisation Auditeur lui est affecté par défaut. Vous pouvez mettre à jour ce rôle par la suite en le transformant en Responsable de la facturation, de l'organisation, ou sans lui attribuer de rôle quelconque, une fois qu'il a accepté l'invitation. Par ailleurs, vous pouvez accorder à l'utilisateur invité un accès à n'importe quel espace (voire à tous) dans l'organisation sélectionnée.

1. Dans l'écran **Inviter des utilisateurs**, développez la section **Accès Cloud Foundry**.
2. Sélectionnez une organisation à laquelle ajouter l'utilisateur.
3. Sélectionnez **Toutes les régions en cours** ou une région spécifique.
4. Sélectionnez **Tous les espaces en cours** ou un espace spécifique.
5. Sélectionnez un rôle d'espace pour définir son niveau d'accès aux espaces sélectionnés.
6. Facultatif : sélectionnez **Ajouter un rôle** pour lui attribuer un rôle supplémentaire.

Voir [Rôles Cloud Foundry](/docs/iam/users_roles.html#cfroles) pour des informations plus spécifiques sur ces rôles.

**Remarque **: vous pouvez ajouter un rôle Cloud Foundry à l'aide de la commande CLI [bluemix iam account-user-invite](https://console.stage1.bluemix.net/docs/cli/reference/bluemix_cli/bx_cli.html#bluemix_iam_account_user_invite), mais vous devez utiliser l'interface utilisateur pour lui accorder d'autres accès ou autorisations.

## Accès à l'infrastructure

Les droits réels accordés sont limités automatiquement au sous-ensemble de droits dont vous disposez. Pour plus d'informations sur les droits et les actions que l'utilisateur peut effectuer avec chaque droit, voir [Droits relatifs à l'infrastructure](/docs/iam/users_roles.html#infrapermissions).

1. Dans l'écran **Inviter des utilisateurs**, développez la section **Accès Infrastructure**. 
2. Sélectionnez un droit afin de définir la portée de l'accès.

Pour plus d'informations sur la configuration de l'accès utilisateurs après leur ajout à votre compte, voir [Gestion des utilisateurs et des accès](/docs/iam/iamusermanage.html).
