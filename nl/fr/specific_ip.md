---

copyright:

  years: 2018

lastupdated: "2018-11-30"

---

{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:screen: .screen}
{:new_window: target="_blank"}
{:tip: .tip}
{:note: .note}

# Autorisation d'adresses IP spécifiques pour un utilisateur
{: #ips}

Par défaut, toutes les adresses IP peuvent être utilisées pour la connexion à la console {{site.data.keyword.cloud}} et l'accès aux API d'infrastructure classique. Vous pouvez définir les adresses IP disposant de l'accès. Seules les adresses spécifiées autorisées peuvent être utilisées et toutes les autres sont restreintes.
{:shortdesc}

Si vous disposez de l'accès affecté suivant, vous pouvez mettre à jour les adresses IP restreintes pour un autre utilisateur :

  * Règle IAM avec un rôle Editeur ou supérieur dans le service Gestion des utilisateurs.
  * Vous êtes un ancêtre dans la hiérarchie d'infrastructure classique pour l'utilisateur. Vous disposez également du droit de gestion d'infrastructure classique d'utilisateurs.

Pour faire en sorte qu'un utilisateur utilise uniquement des adresses IP spécifiques, procédez comme suit :

1. Dans la barre de menus, cliquez sur **Gérer** &gt; **Accès (IAM)** puis sélectionnez **Utilisateurs**.
2. Sélectionnez un utilisateur dans la liste.
3. Sur la page Détails de l'utilisateur, accédez à la section **Restrictions d'adresse IP**.
4. Dans la zone **Plateforme Cloud**, entrez les adresses IP. Les adresses IP répertoriées sont les seules à partir desquelles cet utilisateur peut se connecter à {{site.data.keyword.Bluemix}}.
5. Dans la zone **Infrastructure classique**, entrez les adresses IP. Les adresses IP répertoriées sont les seules à partir desquelles l'utilisateur peut appeler une API d'infrastructure classique.

  Pour entrer une adresse IP d'infrastructure classique, une clé d'API d'infrastructure classique doit déjà être créée pour l'utilisateur. {: note}

  Vous pouvez gérer ce paramètre pour votre compte si l'option Connexion gérée par l'utilisateur est activée sur votre page Détails de l'utilisateur.
  {: tip}
