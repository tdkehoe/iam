---

copyright:

  years: 2015, 2017
lastupdated: "2017-07-27"

---

{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:screen: .screen}
{:new_window: target="_blank"}

# Gestion des clés d'API
{: #manapikey}

Une clé d'interface de programmation (clé d'API) est un code transmis par des programmes informatiques qui appellent une interface de programmation (API) afin d'identifier le programme appelant, son développeur ou son utilisateur sur le site Web. Les clés d'API permettent de suivre et de contrôler l'utilisation de l'API, par exemple pour empêcher toute utilisation malveillante ou abusive de l'API (telle qu'elle peut être définie dans les conditions du service). La clé d'API fait souvent office à la fois d'identificateur unique et de jeton confidentiel pour l'authentification et dispose généralement de droits d'accès spécifiques à l'utilisateur qui lui est associé. Les clés d'API peuvent reposer sur le système d'identificateurs uniques universels (UUID) afin de garantir que chacune d'entre elles est unique pour chaque utilisateur.

Un utilisateur, fédéré ou non, peut créer une clé d'API pour son utilisation depuis l'interface CLI ou, dans le cadre de l'automatisation, pour se connecter sous votre nom d'utilisateur. Vous pouvez utiliser l'interface utilisateur de {{site.data.keyword.Bluemix_notm}} ou l'interface de ligne de commande de {{site.data.keyword.Bluemix_notm}} pour gérer vos clés d'API en les répertoriant, en créant des clés, en les mettant à jour, ou en les supprimant. Pour gérer vos clés d'API {{site.data.keyword.Bluemix_notm}} depuis l'interface utilisateur, accédez à l'option **Gérer** &gt; **Sécurité** &gt; **Clés d'API Bluemix** afin d'afficher la liste de vos clés d'API, leurs descriptions et leurs dates. Depuis cette page, vous pouvez ensuite créer; éditer ou supprimer des clés d'API. Pour la liste complète des commandes CLI disponibles, voir [`Clés d'API bluemix iam`](/docs/cli/reference/bluemix_cli/bx_cli.html#bluemix_iam).

En tant qu'[utilisateur fédéré](/docs/admin/adminpublic.html#federatedid), vous pouvez utiliser une clé d'API pour vous connecter par le biais de la variable d'environnement `BLUEMIX_API_KEY`. Pour plus d'informations sur l'utilisation d'une clé d'API pour la connexion, voir la documentation relative à la [commande `bluemix login` de l'interface de ligne de commande {{site.data.keyword.Bluemix_notm}}](/docs/cli/reference/bluemix_cli/bx_cli.html#bluemix_login) et à la [commande `cf login` de l'interface de ligne de commande cf](/docs/cli/reference/cfcommands/index.html#cf_login).

## Création d'une clé d'API

En tant qu'utilisateur {{site.data.keyword.Bluemix_notm}}, vous pouvez choisir d'utiliser une clé d'API lorsque vous activez un programme ou un script sans fournir votre mot de passe au script. L'utilisation d'une clé d'API présente l'avantage suivant : un utilisateur ou une organisation peut créer plusieurs clés d'API pour divers programmes et les clés d'API peuvent être supprimées indépendamment si elles sont compromises sans interférence avec d'autres clés d'API, ou l'utilisateur.

Pour créer une clé d'API dans l'interface utilisateur, procédez comme suit :

1. Sélectionnez **Gérer** &gt; **Sécurité** &gt; **Clés d'API Bluemix**.
2. Cliquez sur **Créer une clé d'API**.
3. Entrez un nom et une description pour votre clé d'API.
4. Cliquez sur **Créer une clé d'API**.
5. Ensuite, cliquez sur **Afficher** afin d'afficher la clé d'API pour la copier et la sauvegarder en vue d'une utilisation ultérieure, ou cliquez sur **Télécharger une clé d'API**.

**Remarque ** : la clé d'API ne peut être affichée ou téléchargée qu'au moment de sa création. Si la clé d'API est perdue, vous devez en créer une autre.

Pour créer une clé d'API dans l'interface de ligne de commande (CLI), procédez comme suit :

1. Entrez `bluemix iam api-key-create NOM [-d DESCRIPTION] [-f, --file FICHIER]` dans votre invite de commande et spécifiez un nom, une description et un fichier pour l'enregistrement de votre clé. Par exemple :

```
bluemix iam api-key-create MyKey -d "this is my API key" -f key_file
``` 

Une fois qu'une clé d'API a été créée depuis l'interface CLI, vous pouvez l'utiliser de différentes manières depuis l'interface de ligne de commande bx :

* Entrez cette clé avec la commande `bx login` 
```
 bx login —apikey <votre clé d'API>
```
* Créez un fichier de clés d'API à utiliser avec la commande `bx login` : 
 ```
 bx login —apkey @apikeyfile
 ```
 Le fichier `apikeyfile` est créé via l'option `—file` dans la commande `bx iam api-key-create`.
* Dans votre invite de commande, vous pouvez spécifier la variable d'environnement en entrant `BLUEMIX_API_KEY=<your api key>`, puis `bx login`.
* Ou si vous désirez éviter d'utiliser l'interface de ligne de commande bx et vous connecter directement à l'interface de ligne de commande cf à l'aide de votre clé d'API, entrez :
 ```
 cf login -u apikey -p <yourapikey>
 ```
  Dans cette option, vous utilisez `apikey` comme nom d'utilisateur et le mot de passe `apikey`. Vous pouvez à présent utiliser `apikey` dans d'autres outils, comme Eclipse, ou d'autres situations utilisant `cf login` et n'acceptant qu'un nom d'utilisateur et son mot de passe.

## Edition d'une clé d'API

Si vous désirez modifier le nom ou la description d'une clé d'API, procédez comme suit dans l'interface de ligne de commande ou l'interface utilisateur.

Pour éditer une clé d'API :

1. Sélectionnez **Gérer** &gt; **Sécurité** &gt; **Clés d'API Bluemix**.
2. Dans le menu **Actions** d'une clé d'API répertoriée dans la table, cliquez sur **Editer un nom & et une description**. 
3. Mettez à jour les informations relatives à votre clé d'API.
4. Cliquez sur **Mettre à jour une clé d'API**.

Pour modifier une clé d'API à l'aide de l'interface de ligne de commande :

1. Entrez `bluemix iam api-key-update NOM [-n NOM] [-d DESCRIPTION]` dans votre invite de commande, en spécifiant l'ancien nom, le nouveau et la nouvelle description de la clé. Par exemple :

```
bluemix iam api-key-update MyCurrentName -n MyNewName -d "the new description of my key"
```

## Suppression d'une clé d'API

Si vous utilisez une stratégie de rotation des clés, vous pouvez être amené à supprimer une ancienne clé et la remplacer par une nouvelle.

Pour supprimer une clé d'API : 

1. Sélectionnez **Gérer** &gt; **Sécurité** &gt; **Clés d'API Bluemix**.
2. Dans le menu **Actions** d'une clé d'API répertoriée dans la table, cliquez sur **Supprimer**.
3. Ensuite, confirmez la suppression en cliquant sur **Supprimer la clé**.

Pour supprimer une clé d'API à l'aide de l'interface de ligne de commande :
1. Entrez `bluemix iam api-key-delete NOM` dans votre invite de commande, en spécifiant le nom de la clé à supprimer.
