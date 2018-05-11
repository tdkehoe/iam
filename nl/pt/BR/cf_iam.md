---

copyright:

  years: 2017, 2018

lastupdated: "2018-04-17"

---

{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:screen: .screen}
{:new_window: target="_blank"}
{:tip: .tip}

# Migrando instâncias de serviço do Cloud Foundry para um grupo de recursos
{: #accessmodels}

Conforme os serviços se movimentam do uso de organizações, espaços e funções do Cloud Foundry
para o uso do Cloud Identity and Access Management (IAM) e de grupos de recursos, você é notificado em seu
painel. Quando um serviço é movido para fora do Cloud Foundry, você é solicitado a migrar suas instâncias de
serviço existentes que pertencem a uma organização e espaço para um
[grupo de recursos](/docs/account/resourcegroups.html#rgs). 

Ao migrar instâncias de serviços existentes do Cloud Foundry para um grupo de
recursos, a designação de grupo que você faz não pode ser mudada depois que a migração se torna definitiva.
Portanto, deve-se decidir corretamente como deseja organizar os recursos na conta antes da
migração. Isso pode significar a necessidade de criar um ou mais grupos de recursos, caso você tenha uma
conta paga, antes da migração.
{: tip}

## Por que migrar minhas instâncias de serviço?

Os serviços que suportam o uso do Cloud IAM têm vários benefícios, incluindo a capacidade de se conectar a apps e serviços em qualquer espaço do Cloud Foundry, que permite conectar apps e serviços de diferentes regiões. Além disso, cada instância gerenciada pelo Cloud IAM pertence a um grupo de recursos e os grupos de recursos não têm o escopo definido por região, portanto é possível provisionar apps e serviços de regiões diferentes no mesmo grupo de recursos. Você também tem a capacidade de usar o controle de acesso de baixa granularidade para uma instância individual.
 

## Como a migração funciona?

A migração de uma instância de serviço de uma organização e espaço do Cloud Foundry para um grupo de
recursos cria uma nova instância de serviço vinculada no grupo de recursos. A instância original na
organização e no espaço do Cloud Foundry se torna um
[alias](/docs/cfapps/connecting_apps.html#what_is_alias).

É possível migrar suas instâncias de um serviço por vez quando você é notificado no painel por um
ícone associado à sua instância de serviço do Cloud Foundry ou por uma mensagem na página de detalhes do serviço
que pode levá-lo diretamente para o assistente que orienta você pelo processo. Antes de migrar, decida
sobre como você deseja organizar seus recursos, para que seja possível escolher uma instância de serviço
elegível usando o menu **Ações** no painel e selecionando **Migrar para um
grupo de recursos**. Você seleciona um grupo de recursos para o qual migrar a instância durante o
processo. Depois de ter migrado uma instância com sucesso, ela é refletida na seção Serviços de seu painel. O
alias permanece na seção do Cloud Foundry do painel. 


