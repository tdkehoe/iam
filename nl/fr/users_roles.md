---

copyright:

  years: 2015, 2016

lastupdated: "2017-09-29"

---

{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:screen: .screen}
{:new_window: target="_blank"}

# Rôles utilisateur et droits
{: #userroles}

Vous pouvez gérer les utilisateurs dans les services de plateforme et d'infrastructure {{site.data.keyword.Bluemix_notm}} depuis la page **Utilisateurs** de votre compte. Pour accéder à la page Utilisateurs, depuis le menu {{site.data.keyword.Bluemix_notm}}, cliquez sur **Gérer** &gt; **Compte** &gt; **Utilisateurs**. Les propriétaires de compte peuvent effectuer toutes les opérations de gestion des utilisateurs, des droits, des organisations et des espaces. Les responsables d'organisation et gestionnaires d'espace Cloud Foundry disposent également des accès nécessaires pour gérer les droits relatifs aux utilisateurs ajoutés pour chaque organisation et chaque espace gérés par leurs soins.
{:shortdesc}

Si, en tant qu'utilisateur, vous avez été ajouté au compte d'une autre personne et voulez consulter les rôles et les droits qui vous sont affectés, sélectionnez **Gérer** &gt; **Sécurité** &gt; **Identity & Access** &gt; **Utilisateurs**, et cliquez sur votre nom.

## Rôles de compte
{: #userrolesinfo}

Au niveau du compte, deux rôles permettent l'accès à différentes fonctions de gestion des comptes :

| Rôle de compte | Droits |
|----------------|---------|
|Propriétaire | Le propriétaire du compte a accès à leur profil, aux utilisateurs, aux informations de facturation, aux notifications de dépenses et au tableau de bord de la consommation. Depuis la page Utilisateurs, le propriétaire peut inviter de nouveaux utilisateurs et ajuster les rôles. Il peut également ajouter des offres promotionnelles, définir ou changer la limite de facturation, définir l'accès aux services et gérer les organisations et les espaces. |
|Membre | Un membre a accès à leur profil, à la page Utilisateurs affichant les utilisateurs actifs dans le compte, aux crédits de compte et aux limites de dépenses dans l'en-tête {{site.data.keyword.Bluemix_notm}}.  |
{:caption="Tableau 1. Rôles de compte et droits" caption-side="top"}

Tous les nouveaux utilisateurs sont ajoutés en tant que membre du compte. Vous pouvez affecter des rôles d'organisation et d'espace aux invités afin
d'activer des vues et des droits spécifiques dans {{site.data.keyword.Bluemix_notm}}. Une fois que vos invités ont accepté l'invitation et ont rejoint {{site.data.keyword.Bluemix_notm}}, vous pouvez modifier leurs rôles depuis la page Utilisateurs.

## Rôles Cloud Foundry
{: #cfroles}

Les rôles Cloud Foundry incluent les droits d'accès pour les organisations et les espaces définis sur le compte. Les rôles Cloud Foundry n'activent pas d'autorisations utilisateurs leur permettant de réaliser des actions dans le contexte d'un service. Les rôles suivants peuvent être affectés au niveau de l'organisation :

| Rôle d'organisation | Droits |
|-------------------|-------------|
|Responsable | Les responsables de l'organisation peuvent créer, visualiser, éditer ou supprimer des espaces dans celle-ci, examiner l'utilisation et le quota de l'organisation, inviter des utilisateurs dans l'organisation, désigner les utilisateurs y ayant accès et leurs rôles, ainsi que les domaines personnalisés de l'organisation. |
|Responsable de la facturation | Un responsable de la facturation peut afficher des informations sur l'utilisation des contextes d'exécution et des services pour l'organisation dans la page Tableau de bord de l'utilisation.  |
|Auditeur | Un auditeur de l'organisation peut afficher le contenu des applications et des services dans l'organisation. Il peut également afficher les utilisateurs dans l'organisation et les rôles qui leur sont affectés, ainsi que le quota pour l'organisation. |
{:caption="Tableau 2. Rôles d'organisation et droits" caption-side="top"}

Les rôles suivants peuvent être affectés au niveau de l'espace :

| Rôle d'espace | Droits |
|------------|-------------|
|Responsable | Un responsable de l'espace peut ajouter des utilisateurs existants et gérer les rôles dans l'espace. Il peut également afficher le nombre d'instances, les liaisons de service et l'utilisation des ressources pour chaque application dans l'espace. |
|Développeur | Un développeur de l'espace peut créer, supprimer et gérer des applications et des services dans l'espace. Certaines tâches de gestion impliquent le déploiement d'applications, le démarrage ou l'arrêt d'applications, le changement de nom d'une application, la suppression d'une application, le changement de nom d'un espace, la liaison d'un service ou l'annulation de la liaison d'un service à une application ainsi que l'affichage du nombre d'instances, des liaisons de service et de l'utilisation des ressources pour chaque application dans l'espace. De plus, le développeur de l'espace peut associer une adresse URL interne ou externe à une application dans l'espace.   |
|Auditeur | Un auditeur de l'espace dispose de l'accès en lecture à toutes les informations sur l'espace, telles que le nombre d'instances, les liaisons de service et l'utilisation des ressources pour chaque application dans l'espace. |
{:caption="Tableau 3. Rôles d'espace et droits" caption-side="top"}

**Remarque** : les utilisateurs qui possèdent le rôle de responsable ou de développeur de l'espace peuvent accéder à la
variable
d'environnement VCAP_SERVICES. Toutefois, un utilisateur possédant le rôle d'auditeur ne peut pas y accéder.

## Règles de gestion de l'identité et de l'accès et rôles
{: #iamusermanpol}

Le rôle d'administrateur des accès au compte pour le service Identity and Access Management est automatiquement affecté aux propriétaires de compte, ce qui leur permet d'affecter et de gérer des règles de service. Les règles de service peuvent être affectées à des utilisateurs ou à des ID de service et la règle affectée peut définir les droits d'accès pour un service entier ou au niveau de chaque instance.  

### Règles de service

Une règle affecte à un utilisateur ou à un ID de service un ou plusieurs rôles sur un ensemble de ressources en utilisant une combinaison d'attributs pour définir l'ensemble de ressources applicable. Lorsque vous affectez une règle à un utilisateur, vous devez d'abord spécifier le service concerné. Vous pouvez ensuite sélectionner le ou les rôles à lui affecter. D'autres options de configuration peuvent être disponibles, selon le service que vous sélectionnez.

Vous pouvez affecter et gérer des règles si le rôle approprié vous a été attribué. Le tableau suivant décrit les tâches de gestion de règles et le rôle requis pour chacune.

| Action | Rôle requis |
|----------|---------|
| Créer une règle sur un compte pour tous les services et instances | Administrateur de compte |
| Créer une règle sur un service dans un compte | Administrateur de compte ou administrateur sur le service dans le compte |
| Créer une instance de service | Administrateur de compte ou administrateur ou éditeur sur le service dans le compte |
| Créer une règle sur une instance de service | Administrateur de compte ou administrateur sur le service dans le compte ou administrateur sur l'instance de service |
{: caption="Tableau 4. Tâches d'administration pour la gestion des règles de service avec l'offre Identity and Access activée" caption-side="top"}

### Rôles de règle de service
{: #iamusermanrol}

Les rôles sont un assortiment d'actions ; les actions mappées à ces rôles sont spécifiques au service concerné. Voir la documentation du service sélectionné pour des détails supplémentaires sur les types d'action que chaque rôle autorise.

En complément des descriptions des rôles disponibles dans la console, le tableau ci-dessous présente des exemples de diverses tâches que les utilisateurs affectés à chaque rôle peuvent effectuer dans le service {{site.data.keyword.containershort_notm}}.  

| Rôle | Description des actions | Exemples d'actions|
|:-----------------|:-----------------|:-----------------|
| Visualiseur | Exécute des actions qui ne modifient pas l'état ; actions en lecture seule | <ul><li>Listage des clusters</li><li>Affichage' des détails d'un cluster</li></ul>|
| Editeur | Exécute des actions qui modifient l'état et créent ou suppriment des sous-ressources |<ul><li>Liaison d'un service à un cluster</li><li>Créez un webhook</li></ul> |
| Opérateur | Effectue des actions requises pour configurer et opérer sur des ressources. | <ul><li>Ajout ou retrait de noeuds d'agent</li><li>Réamorçage ou rechargement de noeud d'agent</li><li>Liaison d'un service à un cluster</li></ul> |
| Administrateur | Peut effectuer toutes les actions, notamment de gestion du contrôle d'accès |<ul><li>Retrait d'un cluster</li><li>Création d'un cluster</li><li>Mise à jour des règles d'accès utilisateur</li><li>Toutes les actions qu'un afficheur, un éditeur et un opérateur peuvent effectuer</li></ul>|
{: caption="Tableau 5. Exemples de rôles et d'actions utilisateur" caption-side="top"}



## Autorisations relatives à l'infrastructure
{: #infrapermissions}

Vous pouvez attribuer les droits initiaux suivants lorsque vous invitez un utilisateur :

| Ensemble de droits | Description des actions |
|---------------------------|------------------------|
|Affichage uniquement | Les utilisateurs avec cette autorisation peuvent uniquement afficher les éléments dans le système.|
|Utilisateur de base | Les utilisateurs avec cette autorisation peuvent effectuer des actions élémentaires dans le système, comme l'ajout d'un ticket et la gestion de périphériques. |
|Superutilisateur | Les utilisateurs avec cette autorisation peuvent réaliser toutes les actions disponibles dans le système. |
{:caption="Tableau 6. Droits relatifs à l'infrastructure" caption-side="top"}

Des autorisations supplémentaires peuvent être accordées à l'utilisateur après son acceptation de l'invitation. L'ensemble de droits initiaux défini lors de l'invitation ne donne pas accès aux appareils, par conséquent, vous devez octroyer l'accès aux appareils dans le portail de contrôle après que l'utilisateur a accepté l'invitation. 
