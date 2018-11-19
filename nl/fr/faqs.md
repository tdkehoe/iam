---



copyright:

  years: 2018

lastupdated: "2018-10-30"



---

{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:screen: .screen}
{:new_window: target="_blank"}
{:tip: .tip}

# Foire aux questions
{: #iamfaq}

## En quoi consiste l'application {{site.data.keyword.cloud_notm}} Identity and Access Management ? 
{: #whatisiam}

Identity and Access Management (IAM) vous permet d'authentifier de manière sécurisée les utilisateurs des services de plateforme et de contrôler l'accès aux ressources à travers la plateforme {{site.data.keyword.cloud_notm}}. Un ensemble de services IBM Cloud est activé afin d'utiliser Cloud IAM pour le contrôle d'accès. Ils sont organisés en groupes de ressources au sein de votre compte pour permettre aux utilisateurs un accès rapide et facile à plusieurs ressources à la fois. Des règles d'accès Cloud IAM permettent d'affecter à des ID utilisateur et de service un accès aux ressources de votre compte. Pour plus d'informations, voir [{{site.data.keyword.cloud_notm}} Identity and Access Management](/docs/iam/index.html#iamoverview).

## Qu'est-ce qu'un service activé pour IAM ?
{: #iam-enabled}

Un service activé pour IAM doit résider dans un groupe de ressources et l'accès au service est accordé via les règles d'accès IAM. Lorsque vous créez un service activé pour IAM depuis le catalogue, vous devez l'affecter à un groupe de ressources. Pour plus d'informations, voir [Qu'est-ce qu'une ressource ?](/docs/resources/acct_resources.html#resource)

{{site.data.keyword.containerlong_notm}} est la seule exception ; il est contrôlé par IAM, mais est toujours affecté au groupe de ressources par défaut. Par conséquent, vous ne disposez pas d'une autre option lorsque vous le créez depuis le catalogue. D'autre part, il ne peut pas être affecté à un autre groupe de ressources.


## IAM et Cloud Foundry sont-ils associés ?
{: #iam-cloudfoundry}

Ils ne sont pas associés. Cloud Foundry est une plateforme open source qui utilise des organisations, des espaces et des rôles Cloud Foundry pour gestion des accès. IAM est la méthode sécurisée pour authentifier les utilisateurs pour les services de la plateforme et le contrôle d'accès aux ressources à travers la plateforme {{site.data.keyword.cloud_notm}} à l'aide de groupes de ressources et de rôles d'accès IAM.

Leurs systèmes de gestion des accès sont complètement différents. Les ressources IAM appartiennent à un groupe de ressources tandis que les ressources Cloud Foundry appartiennent à une organisation et à un espace. Les règles d'accès IAM sont utilisées pour attribuer un accès aux ressources dans un groupe de ressources. Les rôles d'organisation et d'espace Cloud Foundry sont utilisés pour attribuer aux utilisateurs un accès aux ressources Cloud Foundry dans un espace. IAM ne vous accorde aucun accès dans les espaces Cloud Foundry et les rôles Cloud Foundry ne vous accordent pas d'accès à des ressources dans un groupe de ressources.

## Comment puis-je vérifier les accès qui me sont octroyés ?
{: #iam-access}

Accédez à **Gérer** &gt; **Accès (IAM)**et sélectionnez votre nom dans la colonne Utilisateur. Ensuite, selon l'accès recherché, ouvrez les différents onglets :

* Pour déterminer les groupes d'accès où vous figurez, sélectionnez **Groupes d'accès**.
* Pour accès IAM, sélectionnez **Règles d'accès**.
* Pour les rôles Cloud Foundry, sélectionnez **Accès Cloud Foundry**.

## Comment demander l'accès à une ressource ?
{: #request-access}

Le propriétaire du compte peut mettre à jour l'accès à n'importe quelle ressource du compte ou vous pouvez contacter un utilisateur affecté au rôle administrateur sur le service ou l'instance de service. 

## Pourquoi devrais-je utiliser des groupes de ressources et des groupes d'accès ? 
{: #resource-groups}

Un groupe de ressources est un conteneur logique de ressources. Lorsqu'une ressource est créée, elle est affectée à un groupe de ressources et ne peut dès lors pas être déplacée. 

Un groupe d'accès est utilisé pour organiser facilement un ensemble d'utilisateurs et d'ID de service dans une même entité afin de faciliter les affectations d'accès. Vous pouvez affecter une règle unique à un groupe d'accès afin d'octroyer à ses membres ces autorisations. Si vous avez plusieurs utilisateurs ou ID de service nécessitant le même accès, créez un groupe d'accès au lieu d'octroyer individuellement et successivement l'accès à chaque utilisateur ou ID de service concerné.

En utilisant à la fois des groupes de ressources et des groupes d'accès, vous pouvez rationaliser la procédure d'affectation d'accès en affectant un nombre limité de règles. Vous pouvez organiser toutes les ressources auxquelles a besoin d'accéder un groupe spécifique d'utilisateurs et d'ID de service en constituant un groupe d'accès, puis en affectant une seule règle octroyant l'accès à toutes les ressources du groupe de ressources.

## Comment m'assurer que mes utilisateurs puissent créer des ressources au sein d'un groupe de ressources ?
{: #resources}

Pour créer une ressource dans un groupe de ressources, l'utilisateur doit disposer de deux règles d'accès : une affecté au groupe de ressources lui-même, l'autre affectés aux ressources dans le groupe. L'accès au groupe de ressources lui-même est simplement l'accès au conteneur qui organise les ressources et ce type de règle autorise un utilisateur à afficher, éditer ou gérer l'accès au groupe, mais non pas aux ressources qu'il héberge. L'accès aux services dans le groupe de ressources permet à l'utilisateur de travailler avec les instances de service, ce qui indique que l'utilisateur peut en créer une.

Ainsi, l'utilisateur doit disposer au minimum de l'accès suivant :

* Rôle Afficheur ou supérieur sur le groupe de ressources lui-même
* Rôle Editeur ou supérieur sur le service ou sur tous les services du groupe de ressources


## De quel accès ais-je besoin pour accorder un accès à d'autres utilisateurs ?
{: #user-access}

Vous devez être rattaché au rôle administrateur sur le service ou la ressource auxquels vous désirez accorder l'accès à d'autres utilisateurs. Si vous désirez affecter l'accès à tous les services ou les ressources du compte, vous aurez besoin d'une règle sur tous les services ou ressources activés pour Identity and Access avec le rôle Administrateur. 

## Quelle est la différence entre l'octroi d'un accès pour gérer un groupe de ressources par rapport à l'accès aux ressources dans un groupe de ressources ?
{: #providing-access}

Lorsqu'un accès pour gérer un groupe de ressources vous est octroyé, vous pouvez afficher, modifier le nom et gérer l'accès au groupe de ressources lui-même en fonction du rôle assigné. L'accès à un groupe de ressources lui-même n'accorde pas à un utilisateur l'accès aux ressources dans le groupe.

Lorsque vous avez accès à des ressources d'un groupe de ressources, vous pouvez modifier, supprimer, et créer des instances, ou effectuer toutes les actions de gestion pour les services spécifiés dans le groupe de ressources en fonction du rôle affecté. 

Par exemple, pour les rôles de gestion de plateforme et les actions de services de gestion de compte, reportez-vous à [Table des rôles de plateforme](/docs/iam/users_roles.html#platformrolestable2).

## Qui est habilité à supprimer des utilisateurs ?
{: #remove-users}

Le propriétaire du compte peut toujours ajouter et supprimer des utilisateurs. Par ailleurs, tout utilisateur affecté à l'un des deux types de règles suivantes peut supprimer des utilisateurs :

* Editeur ou Administrateur pour Tous les services de gestion des comptes
* Editeur ou Administrateur pour le service de gestion de compte utilisateur

## Comment activer l'authentification multi-facteur ?
{: #multi-factor}

Accédez à **Gérer** &gt; **Accès (IAM)** et sélectionnez **Paramètres**.
Sélectionnez **Authentification multi-facteur**, puis cliquez sur **Appliquer les modifications**. Pour plus d'informations, voir [Activation de l'authentification multi-facteur](/docs/iam/mfa.html#enablemfa).

## Quelle est la différence entre rôles de service et de plateforme ? 
{: #service-platform-roles}

Les rôles de service et de plateforme sont deux types de rôles différents : 

* Les rôles de plateforme indiquent comment utiliser un service avec un compte, par exemple comment créer des instances, lier des instances et gérer l'accès de l'utilisateur au service. Pour les services de plateforme, ces rôles permettent aux utilisateurs de créer des groupes de ressources et de gérer les ID de service, par exemple. Les rôles de plateforme sont les suivants : administrateur, éditeur, opérateur et afficheur. 

* Rôles de service définissent la possibilité d'effectuer des actions sur un service et sont spécifiques à chaque service (par exemple, les appels d'API ou l'accès à l'interface utilisateur). Les rôles de service sont les suivants : responsable, auteur et lecteur. Pour plus d'informations sur la façon dont ces rôles s'appliquent, reportez-vous à la documentation du service spécifique.

## Quelle est la différence entre un groupe de ressources et les organisations et espaces Cloud Foundry ?
{: #groups-organizations}

Au début de {{site.data.keyword.Bluemix_notm}}, un service de plateforme open source pour le contrôle d'accès et l'organisation de ressources dénommée Cloud Foundry constituait l'unique méthode d'organisation et de contrôle d'accès aux ressources. Avec l'expansion d'{{site.data.keyword.Bluemix_notm}}, une nouvelle méthode pouvant être utilisée par tous les types de services et de ressources s'avérait nécessaire. Des groupes de ressources sont dorénavant utilisés pour regrouper et organiser de nombreux types de ressources et IAM est utilisé pour contrôle cohérent de l'accès aux services et aux ressources. Un certain nombre de services ont déjà adopté l'utilisation de groupes de ressources et d'IAM, d'autres passeront au fil du temps à la nouvelle méthode d'organisation des ressources et de contrôle d'accès.

Le contrôle d'accès et l'organisation des ressources du compte sont les principales différences entre les groupes de ressources et les organisations et espaces Cloud Foundry. Les groupes de ressources organisent les services activés pour IAM dans un compte dont l'accès est contrôlé via des règles IAM. Les organisations et les espaces sont gérés à l'aide de rôles Cloud Foundry pour le contrôle d'accès et les ressources Cloud Foundry sont affectées à des espaces. Vous ne pouvez utiliser des organisations et des espaces pour organiser et gérer l'accès aux ressources que dans le domaine Cloud Foundry, tandis que les groupes de ressources et IAM peuvent être utilisés pour de multiples types de ressources à travers {{site.data.keyword.Bluemix_notm}}.

## Comment désigner un utilisateur comme administrateur de compte ? 
{: #account-administrator}

Pour déléguer le rôle d'administrateur de compte à l'aide de règles IAM, vous devez créer deux règles :

* Administrateur sur Tous les services avec l'offre Identity and Access activée, ce qui autorise l'utilisateur à créer des instances de service et à attribuer aux utilisateurs un accès à toutes les ressources du compte
* Administrateur sur Tous les services de gestion des comptes, ce qui autorise l'utilisateur à effectuer des tâches comme l'invitation et la suppression d'utilisateurs, la gestion de groupes d'accès, d'ID de service, des offres de catalogue privé et le suivi des informations de facturation et d'utilisation.
