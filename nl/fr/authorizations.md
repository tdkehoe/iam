---

copyright:

  years: 2017, 2018

lastupdated: "2017-12-15"

---

{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:screen: .screen}
{:new_window: target="_blank"}
{:tip: .tip}


# Octroi d'accès entre services
{: #serviceauth}

La plupart des fonctionnalités du système IAM (Identity and Access Management) {{site.data.keyword.Bluemix_notm}} se concentrent sur la gestion et l'application de l'accès aux ressources {{site.data.keyword.Bluemix_notm}} par les utilisateurs et leurs applications. Il existe toutefois d'autres scénarios dans lesquels vous pouvoir avoir besoin de fournir un service avec accès à une ressource d'un utilisateur dans un autre service. Tous les utilisateurs de votre compte peuvent créer une autorisation, mais seul un utilisateur disposant du rôle `Administrateur` est en mesure de supprimer une autorisation. Vous pouvez définir et afficher les autorisations qui ont été accordées dans votre compte sur la page **Autorisations**.

## Création d'une autorisation

Vous pouvez accorder uniquement le niveau d'accès dont vous disposez en tant qu'utilisateur du service cible. Ainsi, si vous n'avez qu'un accès afficheur au service qui va être utilisé, vous ne pouvez accorder que le rôle afficheur pour l'autorisation.

1. Dans la barre de menus, cliquez sur **Gérer** &gt; **Compte** &gt; **Identity and Access** et sélectionnez **Autorisations**.
2. Cliquez sur **Créer une autorisation**.
3. Sélectionnez une source et une cible pour l'autorisation. Le service source se voit accorder l'accès au service cible sélectionné.
4. Sélectionnez un rôle pour affecter l'accès au service source lors de l'accès au service cible.
5. Cliquez sur **Autoriser**.

**Remarque** : seuls les services qui autorisent l'octroi de ce type d'accès sont disponibles en tant qu'options.

## Retrait d'une autorisation

1. Dans la barre de menus, cliquez sur **Gérer** &gt; **Compte** &gt; **Identity and Access** et sélectionnez **Autorisations**.
2. Identifiez la ligne contenant l'autorisation que vous voulez retirer du compte.
3. Dans le menu **Actions**, sélectionnez **Retirer l'autorisation**.
5. Sélectionnez **Retirer**.
