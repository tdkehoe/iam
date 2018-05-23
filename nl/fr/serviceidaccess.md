---

copyright:

  years: 2015, 2018
lastupdated: "2018-05-02"

---

{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:screen: .screen}
{:new_window: target="_blank"}

# Gestion des règles d'accès associées aux ID de service
{: #serviceidpolicy}

Lorsque vous créez un ID de service, vous pouvez affecter des règles de service pour cet ID de service afin de contrôler le niveau d'accès autorisé lorsqu'il est utilisé pour l'authentification auprès de vos services. Vous pouvez mettre à jour les règles d'accès affectées à tout moment en changeant une règle existante, en supprimant une règle ou en en affectant une nouvelle.

**Remarque** : le fait de supprimer ou d'éditer une règle existante pour un ID de service en cours d'utilisation peut entraîner une interruption de service.

## Affectation d'un nouvel accès

Pour affecter des droits d'accès à toutes les ressources d'un groupe de ressources ou uniquement à un service d'un groupe de ressources, procédez comme suit :

1. Dans la barre de menus, cliquez sur **Gérer** &gt; **Sécurité** &gt; **Identity and Access** &gt; **ID de service**.
2. Sélectionnez l'ID de service pour laquelle vous souhaitez affecter une règle de service.
3. Cliquez sur **Affecter un accès**.
4. Sélectionnez **Assign by resource group**.
5. Sélectionnez un groupe de ressources.
6. Sélectionnez un rôle dans la zone **Affecter l'accès à un groupe de ressources**. Cette option permet à l'utilisateur d'afficher le groupe de ressources sur son tableau de bord, d'éditer le nom du groupe de ressources ou de gérer l'accès des utilisateurs au groupe. Vous pouvez sélectionner **Aucun accès** si vous voulez que l'utilisateur accède uniquement à la ressource que vous indiquez et non au groupe auquel elle est affectée.
7. Sélectionnez un service dans le groupe de ressources ou sélectionnez d'accorder l'accès à tous les services du groupe sélectionné.
8. Sélectionnez toute combinaison de rôles pour affecter l'accès voulu à l'utilisateur. Cet accès s'applique uniquement aux ressources sélectionnées pour la règle. Il n'accorde pas l'accès au conteneur que constitue le groupe de ressources.
9. Sélectionnez **Affecter**.

Pour affecter des droits d'accès à une ressource individuelle du compte, procédez comme suit :

1. Dans la barre de menus, cliquez sur **Gérer** &gt; **Sécurité** &gt; **Identity and Access** &gt; **ID de service**.
2. Sélectionnez l'ID de service pour laquelle vous souhaitez affecter une règle de service.
3. Cliquez sur **Affecter un accès**.
4. Sélectionnez **Assign by resource**.
5. Sélectionnez un service.
6. Sélectionnez **Toutes les régions en cours** ou une région spécifique, si vous êtes invité à le faire.
7. Sélectionnez **Toutes les instances de service en cours** ou une instance de service spécifique.
8. Selon le service que vous avez sélectionné, les zones suivantes peuvent s'afficher. Si vous n'entrez pas de valeurs pour ces zones, la règle est affectée au niveau instance de service et au niveau compartiment.
    * **Type de ressource** : entrez **compartiment**.
    * **ID de ressource** : entrez le nom de votre compartiment
9. Sélectionnez toute combinaison de rôles pour affecter l'accès voulu à l'utilisateur.
10. Sélectionnez **Affecter**.



## Edition d'un accès existant

Pour éditer une règle existante :

1. Dans la barre de menus, cliquez sur **Gérer** &gt; **Sécurité** &gt; **Identity and Access** &gt; **ID de service**.
2. Sélectionnez l'ID de service pour laquelle vous souhaitez éditer une règle de service.
3. Identifiez la ligne contenant la règle à éditer, puis sélectionnez **Editer la règle** dans le menu **Actions**.
4. Apportez vos modifications, puis sauvegardez la règle.

## Retrait de l'accès

Pour retirer une règle existante :

1. Dans la barre de menus, cliquez sur **Gérer** &gt; **Sécurité** &gt; **Identity and Access** &gt; **ID de service**.
2. Sélectionnez l'ID de service pour laquelle vous souhaitez supprimer une règle de service.
3. Identifiez la ligne contenant la règle à supprimer, puis sélectionnez **Retirer** dans le menu **Actions**.
4. Revoyez les détails relatifs à la règle que vous êtes sur le point de retirer, puis cliquez sur **Retirer** pour confirmer.
