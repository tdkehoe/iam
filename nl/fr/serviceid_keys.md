---

copyright:

  years: 2015, 2017
lastupdated: "2017-11-16"

---

{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:screen: .screen}
{:new_window: target="_blank"}

# Gestion des clés d'API d'ID de service
{: #serviceidapikeys}

Des ID de service sont créés pour permettre l'accès à vos services {{site.data.keyword.Bluemix_notm}} par des applications hébergées à l'intérieur et à l'extérieur de {{site.data.keyword.Bluemix_notm}}. Les clés d'API sont utilisées par une application pour s'authentifier en tant qu'ID de service particulier et peuvent se voir accorder les droits d'accès associés à cet ID de service.

Une fois que vous avez créé un ID de service, vous pouvez commencer à créer des clés d'API et à affecter des règles de service. Chaque règle spécifie le niveau d'accès autorisé lorsque la clé d'API est utilisée pour l'authentification auprès de vos services. Pour plus d'informations sur la création d'un ID de service et l'affectation de règles, voir[Création et gestion d'ID de service](serviceids.html). Pour plus d'informations sur les commandes CLI utilisées pour gérer des clés d'API d'ID de service, voir [Commandes de gestion des clés d'API et des règles](/docs/cli/reference/bluemix_cli/bx_cli.html#bx_commands_iam).

Chaque clé d'API associée à un ID de service hérite de la règle qui a été affectée à cet ID de service. Par example, pour qu'une application puisse simplement afficher les ressources d'un service, vous devez utiliser une clé d'API associée à un ID de service auquel une règle dotée du rôle `Viewer` est affectée. Et, pour qu'une autre application ait des droits d'accès complets dans un service, vous devez utiliser une clé d'API associée à un second ID de service auquel une règle dotée du rôle `Administrator` est affectée.

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


## Suppression d'une clé d'API pour un ID de service

Vous pouvez supprimer une clé d'API associée à un ID de service. Cela dit, si vous supprimez une clé d'API utilisée par une application, celle-ci ne pourra plus s'authentifier auprès de vos services.

1. Accédez à **Gérer** &gt; **Sécurité** &gt; **Identity and Access** &gt; **ID de service**. 
2. Si vous ne possédez pas encore d'ID de service, créez-en un.
3. Dans le menu **Actions**, accédez à l'option **Gérer un ID de service**.
4. Dans le menu **Actions** de la section des clés d'API, accédez à l'option **Supprimer une clé**.


