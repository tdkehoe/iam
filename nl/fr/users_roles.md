---

copyright:

  years: 2015, 2018

lastupdated: "2018-04-04"

---

{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:screen: .screen}
{:tip: .tip}
{:new_window: target="_blank"}

# Accès IAM
{: #userroles}

Tous les services organisés en groupe de ressources dans votre compte sont gérés avec {{site.data.keyword.Bluemix_notm}} Identity and Access Management (IAM). Le rôle d'administrateur des accès au compte pour le service Cloud IAM est automatiquement affecté aux propriétaires de compte. En tant qu'administrateur de compte, vous pouvez affecter et gérer l'accès des utilisateurs, créer des groupes de ressources, mettre à disposition des instances de service et déléguer toutes les autres tâches en affectant les rôles Cloud IAM. Vous accordez l'accès à des ID utilisateur et de service en créant des règles qui définissent une cible à laquelle l'ID utilisateur ou de service peut accéder et un rôle qui détermine le type d'accès autorisé.


## Quelles sont les règles Cloud IAM et qui peut les affecter ?
{: #iamusermanpol}

Une règle affecte à un ID utilisateur ou de service un ou plusieurs rôles sur un ensemble de ressources afin d'activer des actions spécifiques à entreprendre dans le contexte des ressources cible spécifiées. Lorsque vous affectez une règle, vous commencez par sélectionner si elle s'applique à un groupe de ressources ou à une ressource individuelle. Ensuite, en fonction du choix initial, vous pouvez sélectionner un service dans un groupe de ressources ou une instance unique pour la ressource sélectionnée. D'autres options de configuration peuvent être disponibles, selon le service que vous sélectionnez. Enfin, vous pouvez sélectionner un ou des rôles à affecter. 

Vous pouvez affecter et gérer des règles si le rôle approprié vous a été attribué. Le tableau suivant décrit les tâches de gestion des règles et le rôle requis pour chacune.

| Action | Rôle requis |
|----------|---------|
| Créer une règle dans un compte pour tous les services et instances | Propriétaire ou administrateur du compte sur tous les services dans le compte | 
| Créer une règle sur un service dans un compte | Propriétaire ou administrateur du compte sur le service dans le compte |
| Créer une règle sur une instance de service | Propriétaire du compte, administrateur sur le service dans le compte, administrateur sur tous les services dans le groupe de ressources concerné ou administrateur sur l'instance de service |
| Créer une règle pour gérer un groupe de ressources | Propriétaire ou administrateur du compte sur un groupe de ressources |
{: caption="Tableau 1. Utilisateurs autorisés à créer des règles d'accès" caption-side="top"} 


## Rôles Cloud IAM
{: #iamusermanrol}

Cloud IAM vous permet de gérer et de définir les droits d'accès des utilisateurs et des ressources dans votre compte. Deux types de rôle peuvent être affectés : des rôles de gestion de plateforme et des rôles d'accès à un service.

<dl>
<dt>Rôles de gestion de plateforme</dt> 
<dd>Les rôles de gestion de plateforme couvrent un large éventail d'actions, notamment la possibilité de créer des instances, de gérer des ID de service, de gérer des utilisateurs et des droits, et de créer des groupes de ressources. Les rôles les plus courants associés à la plateforme sont administrateur, éditeur, opérateur et visualiseur. </dd>
<dt>Rôles Accès au service</dt>
<dd>Les rôles d'accès au service définissent la capacité qu'a un utilisateur ou un service d'exécuter des actions sur une instance de service, telles qu'accéder à l'interface utilisateur ou effectuer des appels API. Trois rôles sont possibles : gestionnaire, auteur et lecteur. </dd>
</dl> 

Vous ne verrez peut-être pas tous les rôles possibles lors de l'affectation de règles dans l'interface utilisateur car seuls les rôles qui s'appliquent au service que vous avez sélectionné s'affichent. Pour en savoir plus sur les rôles activés spécifiquement et sur les actions autorisées par chaque rôle d'accès pour chaque service, voir la documentation sur chaque service.
{: tip}

A l'aide d'une combinaison de ces rôles dans une même règle d'accès, vous pouvez offrir un accès à granularité fine à des ID utilisateur et de service en contrôlant l'accès aux entités suivantes :

* Toutes les ressources d'un compte
* Toutes les ressource de tous les services d'un groupe de ressources individuel et la possibilité de gérer le groupe de ressources
* Toutes les ressource d'un seul service d'un groupe de ressources et la possibilité de gérer le groupe de ressources
* Toutes les ressource d'un seul service du compte, quel que soit le groupe de ressources auquel elles sont affectées
* Les ressources d'une instance individuelle
* Un seul type de ressource dans une instance, par exemple, un compartiment dans une instance {{site.data.keyword.objectstorageshort}}

Pour accorder à un autre utilisateur l'accès complet au compte à des fins de gestion des utilisateurs et de gestion de toutes les ressources du compte ainsi que la possibilité de créer des groupes de ressources, définissez une règle accordant à l'utilisateur l'accès à toutes les ressources du compte en sélectionnant **Tous les services avec l'offre Identity and Access activée** et le rôle **Administrateur** affecté. 
{: tip}

### Rôles de gestion de plateforme

Les rôles Gestion de la plateforme permettent aux utilisateurs de se voir affecter différents niveaux de droits pour effectuer des actions de plateforme dans le compte. Les tableaux suivants fournissent des exemples de certaines des actions de gestion de plateforme que les utilisateurs affectés à chaque rôle peuvent réaliser. Pour comprendre comment les rôles s'appliquent aux utilisateurs dans le contexte du service que vous utilisez, reportez-vous à la documentation afférente à chaque service.

| Détails de la règle d'accès  | Actions qu'un utilisateur peut effectuer sur des services dans le compte | Actions pour les ID de service | Actions pour l'accès à des groupes de ressources | Actions sur des ressources dans des groupes de ressources | Actions pour la gestion de groupes d'accès |
|:-----------------|:--------------|:---------------|:----------------|:-----------------|:--------------|
| Affecter l'accès à | Un ou la totalité des services activés pour IAM | Service d'identité IAM | Groupe de ressources sélectionné | Service sélectionné dans un groupe de ressources | Groupes d'accès IAM |
| Rôle Afficheur | Afficher des instances, des alias, des liaisons et des données d'identification | Afficher des ID et des clés d'API | Afficher un groupe de ressources | Afficher uniquement des instances spécifiées du groupe de ressources | Afficher des groupes d'accès et des membres |
| Rôle Opérateur |  Afficher des instances et gérer des alias, des liaisons et des données d'identification | Non applicable | Non applicable | Non applicable | Non applicable |
| Rôle Editeur |  Créer, supprimer, éditer et afficher des instances. Gérer des alias, des liaisons et des données d'identification | Créer et supprimer des ID et des clés d'API | Afficher et éditer le nom d'un groupe de ressources | Créer, supprimer, éditer, suspendre, reprendre, afficher et lier uniquement des instances spécifiées du groupe de ressources | Afficher, créer, supprimer et éditer des groupes d'accès dans le compte |
| Rôle Administrateur |  Toutes les actions de gestion pour des services | Créer et supprimer des ID et des clés d'API, affecter des règles à des ID | Afficher, éditer et gérer l'accès pour le groupe de ressources | Toutes les actions de gestion pour des instances spécifiées du groupe de ressources | Afficher, créer, supprimer, éditer et gérer l'accès pour utiliser des groupes d'accès |
{: caption="Tableau 2. Exemples de rôles et d'actions de gestion de plateforme" caption-side="top"}
{: #platformrolestable}

Certains services peuvent mapper des actions spécifiques aux rôles de gestion de plateforme qui sont liés à la gestion du service plutôt qu'à l'accès du service. A titre d'exemple, voir le tableau suivant dans lequel sont décrites les actions de service {{site.data.keyword.containershort_notm}} mappées à ces rôles.


| Rôle Gestion de la plateforme | Description des actions | Exemples d'action pour le {{site.data.keyword.containershort_notm}} |
|:-----------------|:-----------------|:-----------------|
| Afficheur | Afficher des instances de service, sans pouvoir les modifier  | <ul><li>Répertorier les clusters</li><li>Afficher les détails d'un cluster</li></ul>|
| Editeur | Effectuer toutes les actions de plateforme à l'exception de la gestion du compte et de l'affectation de règles d'accès |<ul><li>Lier un service à un cluster</li><li>Créer un webhook</li></ul> |
| Opérateur | Effectuer les actions de plateforme requises pour configurer et exploiter des instances de service, par exemple, l'affichage de tableau de bord d'un service. | <ul><li>Ajouter ou retirer des noeuds d'agent</li><li>Réamorcer ou recharger des noeuds d'agent</li><li>Lier un service à un cluster</li></ul> |
| Administrateur | Effectuer toutes les actions de plateforme en fonction de la ressource pour laquelle ce rôle est affecté, y compris l'affectation de règles d'accès à d'autres utilisateurs. |<ul><li>Retirer un cluster</li><li>Créer un cluster</li><li>Mise à jour des règles d'accès utilisateur</li><li>Toutes les actions qu'un afficheur, un éditeur et un opérateur peuvent effectuer</li></ul>|
{: caption="Tableau 3. Exemples de rôles et d'actions de gestion de plateforme pour le service {{site.data.keyword.containershort_notm}}" caption-side="top"}


### Rôles Accès au service

Les rôles Accès au service permettent aux utilisateurs de se voir affecter différents niveaux de droits pour appeler l'API du service et accéder à l'interface utilisateur du service. Le tableau ci-après présente des exemples d'actions qui peuvent être exécutées en fonction des rôles affectés lors de l'utilisation du service {{site.data.keyword.objectstorageshort}}.

**Remarque** : les actions qui peuvent être exécutées pour chaque rôle affecté varient selon le service que vous avez sélectionné pour la règle.

| Rôle Accès au service | Description des actions | Exemples d'action pour le service {{site.data.keyword.objectstorageshort}} |
|:-----------------|:-----------------|:-----------------|
|  Lecteur | Effectuer des actions en lecture seule dans un service, par exemple, afficher les ressources spécifiques d'un service. | Répertorier et télécharger des objets |
| Auteur | Les auteurs disposent de droits en plus du rôle de lecteur, par exemple, créer et éditer des ressources pour un service. | Créer et détruire des compartiments et des objets |
| Responsable | Les responsables disposent de droits en plus du rôle Auteur pour effectuer des actions privilégiées définies par le service. De plus, vous pouvez créer et éditer des ressources spécifiques au service. | Gérer tous les aspects de stockage de données. Créer et détruire des compartiments et des objets. |
{: caption="Tableau 4. Exemples de rôles et d'actions utilisateur d'accès au service" caption-side="top"}

