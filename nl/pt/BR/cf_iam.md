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

# Migrando instâncias de serviço do Cloud Foundry para um grupo de recursos
{: #accessmodels}

Conforme os serviços se movem do uso de organizações, espaços e funções do Cloud Foundry para o uso do Cloud Identity and Access Management (IAM) e de grupos de recursos, você é notificado em seu painel. Quando um serviço é movido para fora do Cloud Foundry, você é solicitado a migrar suas instâncias de
serviço existentes que pertencem a uma organização e espaço para um
[grupo de recursos](/docs/account/resourcegroups.html#rgs). 

Ao migrar instâncias de serviços existentes do Cloud Foundry para um grupo de
recursos, a designação de grupo que você faz não pode ser mudada depois que a migração se torna definitiva. Portanto, deve-se decidir corretamente como deseja organizar os recursos na conta antes da
migração. Portanto, você poderá precisar criar um ou mais grupos de recursos, se tiver uma conta paga, antes da migração.
{: tip}

## Por que migrar instâncias de serviço?

Os serviços que suportam o uso do Cloud IAM possuem vários benefícios. Alguns desses benefícios incluem a capacidade de conexão a apps e serviços em qualquer espaço do Cloud Foundry, o que significa que é possível conectar apps e serviços de diferentes regiões. Além disso, cada instância gerenciada pelo Cloud IAM pertence a um grupo de recursos. Os grupos de recursos não têm o escopo definido por região, portanto, é possível provisionar apps e serviços de regiões diferentes para o mesmo grupo de recursos. Também é possível usar o controle de acesso de baixa granularidade para uma instância individual.
 

## Como a migração funciona?

A migração de uma instância de serviço de uma organização e espaço do Cloud Foundry para um grupo de
recursos cria uma nova instância de serviço vinculada no grupo de recursos. A instância original na
organização e no espaço do Cloud Foundry se torna um
[alias](/docs/cfapps/connecting_apps.html#what_is_alias).

É possível migrar uma instância de serviço por vez quando você é notificado. Você é notificado no painel por um ícone que está associado à sua instância de serviço do Cloud Foundry ou pela mensagem na página de detalhes do serviço que pode levá-lo diretamente para o assistente que o conduz pelo processo. Antes da migração, decida como você deseja organizar seus recursos. Em seguida, é possível escolher uma instância de serviço elegível usando o menu **Ações** no painel e selecionando **Migrar para um grupo de recursos**. Você seleciona um grupo de recursos para o qual migrar a instância durante o
processo. Depois de migrar com êxito uma instância, você a verá refletida na seção Serviços de seu painel. O alias permanece na seção do Cloud Foundry do painel. 


