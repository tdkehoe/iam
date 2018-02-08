---

copyright:

  years: 2017, 2018

lastupdated: "2017-11-16"

---

{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:screen: .screen}
{:new_window: target="_blank"}

# Modelos de acesso do IAM e do Cloud Foundry
{: #accessmodels}

Atualmente, nem todos os serviços do {{site.data.keyword.Bluemix_notm}} suportam o uso de gerenciamento de acesso do Cloud IAM. Os serviços que não ativaram o uso do Cloud IAM continuam a depender da função de um usuário em uma organização e espaço do Cloud Foundry para determinar se um usuário tem permissão para acessar os recursos. É possível usar a UI do {{site.data.keyword.Bluemix_notm}} Identity and Access para gerenciar o acesso para serviços que usam os sistemas de gerenciamento de acesso do Cloud IAM ou Cloud Foundry.


## Alternância de serviços do Cloud Foundry para o Cloud IAM
{: #cftoiam}

Se estiver usando atualmente um serviço do Cloud Foundry que começa a suportar o uso do gerenciamento de acesso do Cloud IAM, você receberá uma notificação de que agora é possível aproveitar o controle de acesso com o IAM para as novas instâncias de serviço criadas.

Conforme os serviços começam a ativar o uso do Cloud IAM, é possível esperar o seguinte:

* Para as instâncias existentes em sua conta que já usam o gerenciamento de acesso do Cloud Foundry designando usuários a uma organização e espaço com uma função do Cloud Foundry, é possível continuar a usar essas instâncias sem nenhuma mudança.
* Para criar novas instâncias, cada uma será designada a um grupo de recursos em sua conta e, depois, será possível usar o Cloud IAM para gerenciar o acesso a essa instância e ao grupo de recursos ao qual ela pertence, se você for administrador no grupo de recursos.

Os serviços que suportam o uso do Cloud IAM têm vários benefícios, incluindo a capacidade de se conectar a apps e serviços em qualquer espaço do Cloud Foundry, que permite conectar apps e serviços de diferentes regiões. Além disso, cada instância gerenciada pelo Cloud IAM pertence a um grupo de recursos e os grupos de recursos não têm o escopo definido por região, portanto é possível provisionar apps e serviços de regiões diferentes no mesmo grupo de recursos. Você também tem a capacidade de usar o controle de acesso de baixa granularidade para uma instância individual.
