---

copyright:

  years: 2018
lastupdated: "2018-05-22"

---

{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:screen: .screen}
{:new_window: target="_blank"}
{:tip: .tip}

# Activation de l'authentification multifacteur
{: #enablemfa}

L'authentification multi-facteur ajoute une couche supplémentaire de sécurité à votre compte en exigeant de tous les utilisateurs de fournir un code d'accès à usage unique et durée définie, en plus de leur IBMid et mot de passe associé standard, lors de la connexion. Ce type d'authentification est également communément appelé authentification à deux facteurs (2FA). L'activation de cette fonction pour votre compte nécessite que vous, ainsi que tous les utilisateurs qui sont ajoutés à votre compte, utilisiez la norme de sécurité supplémentaire lors de la connexion.

## Remarques

Avant d'activer l'authentification multi-facteur pour votre compte, lisez les remarques suivantes :

* Lorsque vous activez l'authentification multi-facteur (MFA) pour votre compte, tous les utilisateurs qui sont ajoutés à votre compte doivent se soumettre au processus d'authentification à deux facteurs (2FA) lorsqu'ils se connectent.
* Les clés d'API pour vos utilisateurs et les ID de service continuent de fonctionner après l'activation de l'authentification multi-facteur.
* Si la connexion par interface de ligne de commande CF ou interface utilisateur dans Cloud Foundry est nécessaire, vous devez utiliser des clés d'API ou un code d'accès unique une fois que l'authentification multi-facteur est activée pour le compte.
* L'authentification multi-facteur (MFA) n'est pas prise en charge pour les utilisateurs qui se connectent avec une identité fédérée.
* Planifiez une stratégie de communication et de support pour les utilisateurs ajoutés à votre compte :
  * Choisissez une date et une heure d'activation de l'authentification multi-facteur dont l'impact sur votre activité doit être minimal.
  * Une fois l'authentification multi-facteur activée, informez les utilisateurs de votre compte en leur envoyant des informations leur expliquant comment la [configurer](mfa.html#setupapp).
  
Si vous disposez d'un compte lié et que vous avez déjà configuré l'[authentification à deux facteurs dans le portail de contrôle](/docs/customer-portal/cpenable2fa.html#customerportal_2fa), lisez ce qui suit :

* L'authentification multi-facteur pour votre compte {{site.data.keyword.Bluemix_notm}} s'étend aux services de plateforme et d'infrastructure pour votre compte lié. Etant donné que la configuration du compte pour l'authentification multi-facteur écrase l'authentification à deux facteurs définie dans le portail de contrôle, vous pouvez choisir de désactiver l'authentification à deux facteurs que vous avez acquise et de configurer uniquement les ressources d'infrastructure avec l'option d'authentification multi-facteur.
* Si vous êtes un utilisateur fédéré, l'authentification multi-facteur n'est pas prise en charge. Par conséquent, vous souhaiterez peut-être conserver la configuration de l'authentification à deux facteurs uniquement pour les ressources d'infrastructure afin de garantir la sécurité de vos ressources.

## Activation de l'authentification multifacteur

Pour activer l'authentification multi-facteur (MFA), vous devez être l'administrateur du compte. Cette activation n'a pas d'incidence sur les utilisateurs déjà connectés, vu que l'application de l'authentification multi-facteur sur le compte ne prend effet que lors des nouvelles connexions. Un administrateur qui active l'authentification multi-facteur (MFA) pour le compte doit avertir les utilisateurs du compte que cette authentification est activée et décrire les conséquences aux utilisateurs à leur prochaine connexion. 

1. Dans la barre de menus, cliquez sur **Gérer** &gt; **Sécurité** &gt; **Identity and Access**, puis sélectionnez **Paramètres**.
2. Sélectionnez **Authentification multi-facteur** &gt;, puis cliquez sur **Appliquer les changements**.
3. Dans les fenêtres de confirmation, cliquez sur **Oui, je suis sûr**.

## Configuration du  code d'accès à utilisation unique
{: #setupapp}

Une fois l'authentification multi-facteur (MFA) activée sur votre compte, vous devez configurer le code d'accès à utilisation unique avec une application d'authentification à votre prochaine connexion. Tous les utilisateurs de votre compte doivent également utiliser le code d'accès à utilisation unique à leur prochaine connexion. 

Procédez comme suit pour configurer votre code d'accès à utilisation unique avec une application d'authentification pour la première fois :

1. Connectez-vous avec votre IBMid et le mot de passe associé. 

5 minutes peuvent s'écouler avant que vous puissiez vous reconnecter avec l'authentification multi-facteur activée et configurée.

2. Sélectionnez **Verify** sur l'écran **Verification is required** pour configurer l'authentification multi-facteur avec une application d'authentification.
3. Sélectionnez **Setup your authenticator app** pour obtenir un code d'accès à utilisation unique envoyé à votre adresse électronique afin de pouvoir continuer à configurer l'application d'authentification.
4. Sélectionnez **Verify**.
5. Scannez le code à barres avec votre application ou cliquez sur **Can't scan the bar?** pour entrer manuellement une clé. 
6. Cliquez sur **Continue** pour entrer votre code.
7. Entrez votre code et sélectionnez **Verify**. 

Si un message d'erreur s'affiche pour vous indiquer que vous avez déjà configuré l'authentification, mais que votre code de vérification ne fonctionne pas ou si vous ne disposez pas du code de vérification à saisir, vous devez contacter le [centre d'assistance](https://www.ibm.com/ibmid/myibm/help/us/helpdesk.html){: new_window} ![Icône de lien externe](../icons/launch-glyph.svg "Icône de lien externe") pour réinitialiser votre inscription à l'authentification multi-facteur (MFA).
{: tip}
{: #mfahelp}


## Désactivation de l'authentification multifacteur
{: #disablemfa}

Pour désactiver l'authentification multi-facteur (MFA), vous devez être l'administrateur du compte. La désactivation de l'authentification multi-facteur n'a aucune incidence sur les utilisateurs déjà connectés, car cette action ne prend effet que lors des nouvelles connexions.

1. Dans la barre de menus, cliquez sur **Gérer** &gt; **Sécurité** &gt; **Identity and Access**, puis sélectionnez **Paramètres**.
2. Sélectionnez **Standard** &gt;, puis cliquez sur **Oui, je suis sûr**.
3. Dans les fenêtres de confirmation, cliquez sur **Oui, je suis sûr**.
