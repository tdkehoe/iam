---

copyright:

  years: 2017, 2018

lastupdated: "2017-11-16"

---

{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:screen: .screen}
{:new_window: target="_blank"}

# Modèles d'accès IAM et Cloud Foundry
{: #accessmodels}

Actuellement, les services {{site.data.keyword.Bluemix_notm}} ne prennent pas tous en charge l'utilisation de la gestion des accès Cloud IAM. Les services pour lesquels l'utilisation de Cloud IAM n'est pas activée s'appuient toujours sur un rôle utilisateur et un espace dans une organisation Cloud Foundry pour déterminer si un utilisation détient le droit d'accéder aux ressources. Vous pouvez utiliser l'interface utilisateur {{site.data.keyword.Bluemix_notm}} Identity and Access pour gérer l'accès aux services qui se servent de systèmes de gestion des accès Cloud IAM ou Cloud Foundry.


## Passage des services Cloud Foundry à Cloud IAM
{: #cftoiam}

Si vous utilisez actuellement un service Cloud Foundry qui commence à prendre en charge l'utilisation de la gestion des accès Cloud IAM, vous recevrez une notification vous indiquant que vous pouvez désormais bénéficier du contrôle d'accès avec IAM pour les nouvelles instances de service que vous créez.

A mesure que les services commence à activer l'utilisation de Cloud IAM, vous pourrez noter les évolutions suivantes :

* Pour les instances existantes de votre compte qui utilisent déjà la gestion des accès Cloud Foundry en affectant des utilisateurs à une organisation et un espace avec un rôle Cloud Foundry, vous pouvez continuer à utiliser ces instances sans aucune modification.
* Pour la création de nouvelles instances, vous affectez à chacune un groupe de ressources dans votre compte, puis vous pouvez utiliser Cloud IAM pour gérer l'accès à cette instance et au groupe de ressources auquel elle appartient, si vous être l'administrateur du groupe de ressources.

Les services qui prennent en charge l'utilisation de Cloud IAM en tirent plusieurs avantages, notamment la possibilité de se connecter à des applications et des services dans n'importe quel espace Cloud Foundry, ce qui vous permet de vous connecter à des applications et des services à partir de différentes régions. De plus, chaque instance gérée par Cloud IAM appartient à un groupe de ressources et la portée des groupes de ressources n'est pas établie par région, de sorte que vous pouvez mettre à disposition des applications et des services issus de différentes régions dans un même groupe de ressources. Vous avez également la possibilité d'utiliser le contrôle d'accès à granularité fine jusqu'au niveau d'une instance individuelle.
