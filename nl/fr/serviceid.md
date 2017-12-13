---

copyright:

  years: 2017
lastupdated: "2017-11-16"

---

{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:screen: .screen}
{:new_window: target="_blank"}

# Création et gestion des ID de service
{: #serviceids}

Un ID de service identifie un service ou une application de la même façon qu'un ID utilisateur identifie un utilisateur. Un ID de service que vous créez peut être utilisé pour permettre à une application située en dehors de {{site.data.keyword.Bluemix_notm}} d'accéder à vos services {{site.data.keyword.Bluemix_notm}}. Vous pouvez affecter des règles d'accès spécifiques à l'ID de service qui limitent les droits d'utilisation à des services spécifiques ou bien combiner des droits d'accès à différents services. Les ID de service n'étant pas liés à un utilisateur spécifique, si un utilisateur quitte une organisation et est supprimé du compte, l'ID de service est conservé de sorte que votre application ou service reste fonctionnel.

Lorsque vous créez un ID de service, vous créez un nom unique et une description facilement identifiables et gérables dans l'interface utilisateur. Une fois que vous avez créé votre ID de service, vous pouvez créer des clés d'API propres à chaque ID de service utilisable par votre application pour s'authentifier auprès de vos services {{site.data.keyword.Bluemix_notm}}. Pour faire en sorte que votre application dispose des droits d'accès appropriés pour s'authentifier auprès de vos services {{site.data.keyword.Bluemix_notm}}, vous utilisez les règles de service affectées à chaque ID de service que vous créez. 

Les règles d'accès associées à un ID de service permettent d'activer des actions spécifiques qui peuvent être effectuées lorsque cet ID de service est utilisé pour accéder à un service donné. Un ID de service unique peut se voir attribuer plusieurs règles qui définissent le niveau d'accès autorisé lors de l'accès à plusieurs services avec l'offre Identity and Access activée voir même à des différentes instances d'un seul et même service. Par exemple, vous possédez deux services dotés chacun de deux instances de service. Vous pouvez  affecter le rôle `Viewer` pour toutes les instances disponibles d'un service et affecter le rôle `Editor` pour une seule instance d'un second service. Ainsi, vous pouvez personnaliser l'accès à plusieurs services, mais utiliser une seule clé d'API pour l'authentification auprès de tous les services.


## Création d'un ID de service

Pour créer un ID de service, accédez à **Gérer** &gt; **Sécurité** &gt; **Identity and Access**, sélectionnez **ID de service** dans le panneau latéral. Suivez le processus afin de créer un nom et une description pour votre ID de service. Ensuite, utilisez le menu **Actions** pour gérer votre ID de service. Vous pouvez commencer par affecter une règle et créer des clés d'API. Pour plus d'informations sur la gestion des clés d'API, voir  [Gestion des clés d'API d'ID de service](/docs/iam/serviceid_keys.html#serviceidapikeys). Pour plus d'informations sur les commandes d'interface de ligne de commande utilisées pour gérer un ID de service, voir [Commandes de gestion des clés d'API et des règles](/docs/cli/reference/bluemix_cli/bx_cli.html#bx_commands_iam). 

## Mise à jour d'un ID de service

Vous pouvez mettre à jour un ID de service en changeant le nom et la description à tout moment. Vous pouvez également supprimer et créer des clés d'API selon vos besoins ou mettre à jour les règles d'accès affectées. Cela dit, chaque fois que vous modifiez un ID de service existant, par exemple, si vous changez les règles affectées ou supprimez une clé d'API en cours d'utilisation, des interruptions de service peuvent se produire sur les applications qui utilisent cet ID de service.


