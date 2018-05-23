---

copyright:

  years: 2017, 2018

lastupdated: "2018-05-02"

---

{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:screen: .screen}
{:new_window: target="_blank"}
{:tip: .tip}

# Migration des instances de service Cloud Foundry vers un groupe de ressources
{: #accessmodels}

Vous êtes prévenu sur votre tableau de bord à mesure que les services cessent d'utiliser des organisations, des espaces et des rôles Cloud Foundry au profit d'IAM (Identity and Access Management) et de groupes de ressources Cloud. Lorsqu'un service quitte Cloud Foundry, vous êtes invité à faire migrer les instances de service existantes qui appartiennent à une organisation et à un espace dans un [groupe de ressources](/docs/account/resourcegroups.html#rgs). 

Lorsque vous faites migrer des instances de service Cloud Foundry existantes vers un groupe de ressources, l'affectation de groupe que vous effectuez ne peut pas être modifiée une fois la migration terminée. Par conséquent, vous devez être certain de la manière dont vous souhaitez organiser des ressources dans le compte avant de procéder à la migration. Par conséquent, il se peut que vous deviez créer un ou plusieurs groupes de ressources, si vous disposez d'un compte payant, avant de procéder à la migration.
{: tip}

## Pourquoi faire migrer des instances de service ?

Les services qui prennent en charge l'utilisation de Cloud IAM présentent plusieurs avantages. Parmi ces avantages, citons notamment la possibilité de se connecter à des applications et des services dans n'importe quel espace Cloud Foundry, ce qui vous permet de vous connecter à des applications et des services à partir de différentes régions. De plus, chaque instance gérée par Cloud IAM appartient à un groupe de ressources. La portée des groupes de ressources n'est pas établie par région, de sorte que vous pouvez mettre à disposition des applications et des services issus de différentes régions dans un même groupe de ressources. Vous pouvez également utiliser le contrôle d'accès à granularité fine jusqu'au niveau d'une instance individuelle.  
 

## Comment fonctionne la migration ?

Lors de la migration d'une instance de service depuis une organisation et un espace Cloud Foundry dans un groupe de ressources, une nouvelle instance de service liée est créée dans le groupe de ressources. L'instance d'origine dans l'organisation et l'espace Cloud Foundry se transforme en [alias](/docs/cfapps/connecting_apps.html#what_is_alias).

Vous pouvez faire migrer vos instances de service une par une lorsque vous êtes averti. Vous êtes prévenu sur le tableau de bord par une icône associée à votre instance de service Cloud Foundry, ou le message sur la page des détails de service peut vous conduire directement à l'assistant qui vous guide lors du processus. Avant la migration, déterminez de quelle façon vous voulez organiser vos ressources. Choisissez ensuite une instance de service éligible en utilisant le menu **Actions** sur le tableau de bord et en sélectionnant **Faire migrer vers un groupe de ressources**. Sélectionnez un groupe de ressources vers lequel faire migrer l'instance durant le processus. Une fois que vous avez correctement fait migré une instance, elle apparaît dans la section Services de votre tableau de bord. L'alias demeure dans la section Cloud Foundry du tableau de bord.  


