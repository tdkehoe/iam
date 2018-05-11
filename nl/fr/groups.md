---

copyright:

  years: 2018
lastupdated: "2018-03-30"

---

{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:screen: .screen}
{:new_window: target="_blank"}
{:tip: .tip}


# Configuration de groupes d'accès
{: #groups}

Un groupe d'accès peut être créé afin d'organiser un ensemble d'utilisateurs et d'ID de service dans une seule entité et de faciliter l'affectation de droits d'accès. Vous pouvez affecter une seule règle au groupe au lieu d'affecter individuellement le même accès plusieurs fois pour chaque utilisateur ou ID de service. 

Pour faciliter davantage l'affectation et la gestion des accès, vous pouvez connfigurer des groupes de ressources afin d'organiser un ensemble de ressources auxquelles un groupe d'utilisateurs doit avoir accès. Lorsque votre groupe de ressources est configuré, vous pouvez affecter une règle donnant accès à toutes les ressources au sein de ce groupe au lieu de créer des règles d'accès individuellement pour des instances de service au sein de votre compte.   

## Création d'un groupe d'accès

Pour créer un groupe d'accès, procédez comme suit :

1. Dans la barre de menus, cliquez sur **Gérer** &gt; **Sécurité** &gt; **Identity and Access**, puis sélectionnez **Groupes d'accès**.
2. Cliquez sur **Créer**.
3. Entrez un nom et une description facultative pour votre groupe, puis cliquez sur **Créer**.

Ensuite, continuez de configurer votre groupe en ajoutant des utilisateurs ou des ID de service :

1. Sélectionnez le nom du groupe sur lequel vous voulez effectuer des ajouts. 
2. Cliquez sur **Ajouter des utilisateurs** sur l'onglet **Utilisateurs**.  
3. Sélectionnez dans la liste les utilisateurs que vous souhaitez ajouter, puis cliquez sur **Ajouter au groupe**.
4. Pour ajouter des ID de service au groupe, cliquez sur l'onglet **ID de service**, puis cliquez sur **Ajouter un ID de service**.
5. Sélectionnez dans la liste les ID que vous souhaitez ajouter, puis cliquez sur **Ajouter au groupe**.

Vous pouvez supprimer un groupe en sélectionnant l'option **Retirer le groupe**. Lorsque vous retirez un groupe du compte, vous retirez tous les utilisateurs et ID de service du groupe et tous les accès affectés à ce dernier.
{: tip}


## Affectation d'accès à un groupe

Après avoir configuré votre groupe avec des utilisateurs et des ID de service, vous pouvez affecter une règle d'accès commune au groupe. N'oubliez pas que les règles que vous définissez pour le groupe s'appliquent à toutes les entités qu'il contient. 

1. Dans la barre de menus, cliquez sur **Gérer** &gt; **Sécurité** &gt; **Identity and Access**, puis sélectionnez **Groupes d'accès**.
2. Sélectionnez le nom du groupe auquel vous voulez affecter des accès.  
3. Cliquez sur l'onglet **Règles d'accès**. 
4. Cliquez sur **Affecter un accès**. 
5. Choisissez d'affecter l'accès à des ressources d'un groupe de ressources ou à des ressources individuelles disponibles dans le compte. 
