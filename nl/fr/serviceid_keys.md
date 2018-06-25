---

copyright:

  years: 2015, 2018
lastupdated: "2018-06-01"

---

{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:screen: .screen}
{:new_window: target="_blank"}

# Gestion des clés d'API d'ID de service
{: #serviceidapikeys}

Des ID de service sont créés pour permettre l'accès à vos services {{site.data.keyword.Bluemix_notm}} par des applications hébergées à l'intérieur et à l'extérieur de {{site.data.keyword.Bluemix_notm}}. Les clés d'API sont utilisées par une application pour s'authentifier en tant qu'ID de service particulier et peuvent se voir accorder les droits d'accès associés à cet ID de service.

Une fois que vous avez créé un ID de service, vous pouvez commencer à créer des clés d'API et à affecter des règles de service. Chaque règle spécifie le niveau d'accès autorisé lorsque la clé d'API est utilisée pour l'authentification auprès de vos services. Pour plus d'informations sur la création d'un ID de service et l'affectation de règles, voir[Création et gestion d'ID de service](/docs/iam/serviceid.html#serviceids). Pour plus d'informations sur les commandes CLI utilisées pour gérer des clés d'API d'ID de service, voir [Commandes de gestion des clés d'API et des règles](/docs/cli/reference/bluemix_cli/bx_cli.html#bx_commands_iam).

Chaque clé d'API associée à un ID de service hérite de la règle qui a été affectée à cet ID de service. Par exemple, pour qu'une application puisse simplement afficher les ressources d'un service, vous devez utiliser une clé d'API associée à un ID de service auquel une règle dotée du rôle `Afficheur` est affectée. Et, pour qu'une autre application ait des droits d'accès complets dans un service, vous devez utiliser une clé d'API associée à un second ID de service auquel une règle dotée du rôle `Administrateur` est affectée.

Pour plus d'informations, voir [Exemples d'utilisation d'un ID de service](/docs/iam/serviceid.html#examples-of-how-to-use-a-service-id).

## Création d'une clé d'API pour un ID de service

Créez une clé d'API à associer à un ID de service.

1. Accédez à **Gérer** &gt; **Sécurité** &gt; **Identity and Access** &gt; **ID de service**.
2. Si vous ne possédez pas encore d'ID de service, créez-en un.
3. Dans le menu **Actions**, accédez à l'option **Gérer un ID de service**.
4. Cliquez sur **Créer** dans la section de clés d'API.
5. Ajoutez un nom et une description permettant d'identifier facilement la clé d'API.
6. Cliquez sur **Créer**.
7. Sauvegardez votre clé d'API en la copiant ou en la téléchargeant vers un emplacement sécurisé.

**Remarque ** : pour des raisons de sécurité, la clé d'API ne peut être copiée ou téléchargée qu'au moment de sa création. Si la clé d'API est perdue, vous devez en créer une autre.

## Mise à jour d'une clé d'API pour un ID de service

Vous pouvez mettre à jour une clé d'API en éditant le nom ou la description utilisés pour l'identifier dans l'interface utilisateur.

1. Accédez à **Gérer** &gt; **Sécurité** &gt; **Identity and Access** &gt; **ID de service**.
2. Si vous ne possédez pas encore d'ID de service, créez-en un.
3. Dans le menu **Actions**, accédez à l'option **Gérer un ID de service**.
4. Dans le menu **Actions** de la section des clés d'API, accédez à l'option **Editer un nom & une description**.

## Verrouillage d'une clé d'API d'un ID de service
{: #lockkey}

Vous pouvez empêcher la suppression des clés d'API représentant l'identité de l'ID de service en les verrouillant. Une clé d'API verrouillée est indiquée par l'icône ![Icône Verrouillé](images/locked.svg "Verrouillé") dans l'interface utilisateur.

1. Dans la barre de menus, cliquez sur **Gérer** &gt; **Sécurité** &gt; **Identity and Access** puis sélectionnez **ID de service**.
2. Identifiez la ligne de l'ID de service pour lequel vous souhaitez sélectionner une clé d'API puis sélectionnez le nom de l'ID de service.
3. Sélectionnez **Clés d'API**.
4. Survolez la ligne de la clé d'API à verrouiller puis cliquez sur le menu **Actions** pour ouvrir une liste d'options.
5. Cliquez sur **Verrouiller la clé d'API**.

Vous pouvez verrouiller votre clé d'API à tout moment pour mettre à jour, supprimer ou ajouter une règle d'accès ou pour retirer la clé d'API.
{: tip}

### Verrouillage ou déverrouillage d'une clé d'API d'ID de service à l'aide de l'interface CLI

Pour verrouiller une clé d'API d'ID de service, utilisez la commande suivante :

```
ibmcloud iam service-api-key-lock (APIKEY_NAME|APIKEY_UUID) (SERVICE_ID_NAME|SERVICE_ID_UUID) [-f, --force]
```

<strong>Prérequis</strong> : Noeud final, Connexion, Cible

<strong>Options de commande</strong> :
<dl>
  <dt>APIKEY_NAME (obligatoire)</dt>
  <dd>Nom de la clé d'API, s'utilise exclusivement avec APIKEY_UUID</dd>
  <dt>APIKEY_UUID (obligatoire)</dt>
  <dd>Identificateur unique universel de la clé d'API, s'utilise exclusivement avec APIKEY_NAME</dd>
  <dt>SERVICE_ID_NAME (obligatoire)</dt>
  <dd>Nom de l'ID de service, s'utilise exclusivement avec SERVICE_ID_UUID</dd>
  <dt>SERVICE_ID_UUID (obligatoire)</dt>
  <dd>Identificateur unique universel de l'ID de service, s'utilise exclusivement avec SERVICE_ID_NAME</dd>
  <dt>-f, --force</dt>
  <dd>Verrouiller sans confirmation</dd>
</dl>

<strong>Exemples</strong> :

Verrouiller la clé d'API de service `sample-key` de l'ID de service `sample-service` :

```
ibmcloud iam service-api-key-lock sample-key sample-service
```

Pour déverrouiller une clé d'API d'ID de service, utilisez la commande suivante :

```
ibmcloud iam service-api-key-unlock (APIKEY_NAME|APIKEY_UUID) (SERVICE_ID_NAME|SERVICE_ID_UUID) [-f, --force]
```


## Suppression d'une clé d'API pour un ID de service

Vous pouvez supprimer une clé d'API associée à un ID de service. Cela dit, si vous supprimez une clé d'API utilisée par une application, celle-ci ne pourra plus s'authentifier auprès de vos services.

1. Accédez à **Gérer** &gt; **Sécurité** &gt; **Identity and Access** &gt; **ID de service**.
2. Si vous ne possédez pas encore d'ID de service, créez-en un.
3. Dans le menu **Actions**, accédez à l'option **Gérer un ID de service**.
4. Dans le menu **Actions** de la section des clés d'API, accédez à l'option **Supprimer une clé**.
