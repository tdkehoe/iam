---

copyright:

  years: 2015, 2017
lastupdated: "2017-10-06"

---

{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:screen: .screen}
{:new_window: target="_blank"}

# Invitation d'utilisateurs et affectation d'accès
{: #iamuserinv}

Vous pouvez depuis un emplacement unique inviter des utilisateurs dans des services {{site.data.keyword.Bluemix_notm}}, des applications, et l'infrastructure {{site.data.keyword.Bluemix_notm}}. Pour inviter des utilisateurs et gérer des invitations en attente, vous devez être propriétaire du compte, responsable de l'organisation ou encore disposer des droits d'infrastructure permettant d'ajouter des utilisateurs. Vous pouvez inviter des utilisateurs, annuler des invitations, et renvoyer une invitation en attente à un utilisateur invité. Vous pouvez inviter un seul utilisateur ou bien, si vous accordez le même accès à tous les membres d'un groupe d'utilisateurs, inviter simultanément plusieurs utilisateurs.  
{:shortdesc}

## Invitation d'utilisateurs

Pour inviter des utilisateurs ou gérer les invitations d'utilisateur sur votre compte, procédez comme suit : 

1. Dans la barre de menu, cliquez sur **Gérer** &gt; **Sécurité** &gt; **Identity & Access** &gt; **Utilisateurs**. La fenêtre Utilisateurs affiche une liste d'utilisateurs avec leur adresse électronique et leur statut actuel dans le compte actuellement sélectionné.
2. Cliquez sur **Inviter des utilisateurs**.
3. Spécifiez l'adresse électronique ou l'IBMid de l'utilisateur. Si vous affectez le même accès à plusieurs utilisateurs, entrez plusieurs adresses électroniques en séparant les entrées d'ID utilisateur par des virgules, des espaces ou des retours à la ligne.
4. Ajoutez une ou plusieurs options d'accès que vous gérez. Vous devez affecter au moins une option d'accès et configurer les paramètres pour l'utilisateur dans chaque option d'accès que vous lui affectez. Pour les options d'accès supplémentaires que vous n'ajoutez ou ne configurez pas, la valeur par défaut *Aucun accès* lui est affectée. L'une des options suivantes ou toutes les options d'accès suivantes peuvent s'afficher, selon celles que vous êtes autorisé à gérer : **Services avec l'offre Identity and Access activée**, **Accès Cloud Foundry**, **Accès Infrastructure**. Voir [Octroi d'un accès utilisateur](/docs/iam/iamuserinv.html#assignaccess) pour plus d'informations.

Si vous déterminez qu'un utilisateur n'a pas besoin d'un accès, vous pouvez annuler l'invitation de n'importe quel utilisateur dont l'état indique **En cours de traitement** ou **En attente** dans la colonne **Statut**. Si un utilisateur invité n'a pas reçu d'invitation, vous pouvez renvoyer l'invitation à n'importe quel utilisateur dont l'état indique **En attente**.

Si vous désirez inviter des utilisateurs à l'aide de l'interface CLI, reportez-vous à la commande [bluemix iam account-user-invite](/docs/cli/reference/bluemix_cli/bx_cli.html#bluemix_iam_account_user_invite).

## Octroi d'un accès utilisateur
{: #assignaccess}

Vous accordez un accès aux utilisateurs lorsque vous les invitez, en leur affectant des rôles, des règles, et des autorisations sur l'infrastructure Cloud Foundry. Vous pouvez inviter des utilisateurs et leur accorder un accès dans les instances de compte, d'organisation, d'espace et de service, en fonction des options d'accès que vous êtes habilité à gérer. Les sections ci-après décrivent les trois types d'accès pouvant être accordés à un utilisateur invité.

### Services avec l'offre Identity and Access activée

Vous pouvez affecter une règle de service unique lorsque vous invitez un nouvel utilisateur. Une fois que l'utilisateur a accepté l'invitation, vous pouvez ajouter des règles de service supplémentaires. Pour savoir comment éditer des règles d'accès afin d'ajouter des rôles, comment ajouter des règles de service ou comment retirer une règle pour un utilisateur, voir [Services avec l'offre Identity and Access activée](/docs/iam/iamusermanage.html#iammanidaccser).

**Remarque** : selon le service que vous sélectionnez lorsque vous affectez la règle, il se peut que les zones décrites dans la procédure ci-après ne soient pas toutes affichées.

1. Dans l'écran **Inviter des utilisateurs**, développez la section **Services avec l'offre Identity and Access activée**.
2. Sélectionnez un service.
3. Sélectionnez **Toutes les régions en cours** ou une région spécifique, si vous êtes invité à le faire. 
**Remarque :** il n'est pas nécessaire de sélectionner une région pour tous les services.
4. Sélectionnez **Toutes les instances de service en cours** ou une instance de service spécifique.
5. Selon le service que vous avez sélectionné, les zones suivantes peuvent s'afficher. Si vous n'entrez pas de valeurs pour ces zones, la règle est affectée au niveau instance de service et au niveau compartiment.  
    * **Type de ressource** : entrez **bucket**.
    * **Ressource** : entrez le nom de votre compartiment. 
6. Sélectionnez un rôle afin de définir la portée de l'accès pour la règle.
7. Facultatif : sélectionnez **Ajouter un rôle** afin de spécifier un rôle supplémentaire pour la règle.


Voir [Règles et rôles dans Identity and Access Management](/docs/iam/users_roles.html#iamusermanpol) pour plus d'informations sur les rôles lors de la définition de règles de services.

### Accès Cloud Foundry

Lorsque vous invitez de nouveaux utilisateurs, vous pouvez choisir d'ajouter l'utilisateur à une organisation dans le compte. Si vous ajoutez l'utilisateur à une organisation, vous pouvez lui attribuer un rôle dans l'organisation. Vous pouvez ensuite accorder à l'utilisateur invité un accès à n'importe quel espace (voire à tous) dans l'organisation sélectionnée, avec le rôle d'espace qui lui est affecté.

1. Dans l'écran **Inviter des utilisateurs**, développez la section **Accès Cloud Foundry**.
2. Sélectionnez une organisation à laquelle ajouter l'utilisateur.
3. Sélectionnez un rôle dans l'organisation pour définir son niveau d'accès dans l'organisation sélectionnée.
4. Facultatif : sélectionnez **Ajouter un rôle** pour lui attribuer un rôle supplémentaire.
5. Sélectionnez **Toutes les régions en cours** ou une région spécifique.
6. Sélectionnez **Tous les espaces en cours** ou un espace spécifique.
7. Sélectionnez un rôle d'espace pour définir son niveau d'accès aux espaces sélectionnés.
8. Facultatif : sélectionnez **Ajouter un rôle** pour lui attribuer un rôle supplémentaire.

Voir [Rôles Cloud Foundry](/docs/iam/users_roles.html#cfroles) pour des informations plus spécifiques sur ces rôles.

**Remarque **: vous pouvez ajouter un rôle Cloud Foundry à l'aide de la commande CLI [bluemix iam account-user-invite](/docs/cli/reference/bluemix_cli/bx_cli.html#bluemix_iam_account_user_invite), mais vous devez utiliser l'interface utilisateur pour lui accorder d'autres accès ou autorisations.

### Accès à l'infrastructure

Les droits réels accordés sont limités automatiquement au sous-ensemble de droits dont vous disposez. Pour plus d'informations sur les droits et les actions que l'utilisateur peut effectuer avec chaque droit, voir [Droits relatifs à l'infrastructure](/docs/iam/users_roles.html#infrapermissions).

1. Dans l'écran **Inviter des utilisateurs**, développez la section **Accès Infrastructure**.
2. Sélectionnez un droit afin de définir la portée de l'accès.

Pour plus d'informations sur la configuration de l'accès utilisateurs après leur ajout à votre compte, voir [Gestion des utilisateurs et des accès](/docs/iam/iamusermanage.html).
