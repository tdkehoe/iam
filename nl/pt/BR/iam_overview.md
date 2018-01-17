---

copyright:

  years: 2017

lastupdated: "2017-12-07"

---

{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:screen: .screen}
{:new_window: target="_blank"}

# Conceitos do IAM
{: #iamconcepts}

## Identidade

O conceito de identidade no {{site.data.keyword.Bluemix_notm}} IAM consiste nos componentes a seguir:

<dl>
<dt>Identidades do usuário</dt>
<dd>Todos os usuários são identificados por seus IBMids.</dd>
<dt>Identidades de serviço e app</dt>
<dd>Os IDs de serviço são o recurso Cloud IAM que é usado para fornecer uma identidade separada para serviços e aplicativos. É possível criar um ID de serviço para ser usado por um aplicativo que precisa de acesso a seus serviços do {{site.data.keyword.Bluemix_notm}} para que as credenciais do usuário individuais não tenham que ser usadas.</dd>
<dt>Chaves API (interface de programação de aplicativos)</dt>
<dd>As chaves API da plataforma estão disponíveis por meio do Cloud IAM para você usar para autenticar usando a API ou CLI como um ID de serviço ou de usuário. Essas chaves API são fornecidas por meio do Cloud IAM e, portanto, não podem ser usadas geralmente para autenticar com o IBMid fora do IBM Cloud. </dd>
<dt>Resources</dt>
<dd>Os recursos do {{site.data.keyword.Bluemix_notm}} são identificados por seus cloud resource names (CRN). Para obter mais informações, veja [Cloud Resource Names](/docs/overview/crn.html#crn).</dd>
</dl>

## Gerenciamento de acesso

O conceito de gerenciamento de acesso no {{site.data.keyword.Bluemix_notm}} consiste em alguns componentes inter-relacionados, incluindo usuários, recursos, políticas, funções, ações e o sistema de controle Cloud IAM, que permitem que os usuários tomem ações em recursos dentro de uma conta. 

É possível revisar a lista a seguir para saber mais sobre esses componentes do Cloud IAM:

<dl>
<dt>Usuários</dt>
<dd>Todos os usuários dentro de uma conta são identificados por seus IBMids. Os usuários podem ser convidados para a conta e receber acesso aos recursos. O acesso pode ser designado a recursos individuais, até o nível da instância ou a um conjunto de recursos que são organizados em um grupo de recursos da conta.</dd>
<dt>Resources</dt>
<dd>Os recursos de conta são as ofertas de serviços provisionados que são selecionadas do catálogo ou recursos de baixa granularidade em uma instância de serviço.</dd>
<dt>Políticas</dt>
<dd>As políticas são como os usuários ou IDs de serviço na conta recebem permissão para acessar recursos da conta. As políticas incluem um assunto, o destino e a função. O assunto é o ID do usuário ou serviço ao qual você está fornecendo acesso. O destino da política é o recurso ao qual você deseja fornecer acesso. Além disso, as funções servem para definir o nível de acesso ou as ações permitidas no destino da política. Há três tipos de políticas que permitem o acesso a recursos da conta: uma política de grupo de recursos, uma política de instância de recurso e uma política de conta para acesso a todos os serviços ativados pelo Identity and Access. Dependendo de suas seleções, pode haver opções de configuração customizada, como definir o acesso a recursos em uma região específica ou definir o acesso ao nível granular de um recurso específico de serviço dentro de uma instância.</dd>
<dt>Funções</dt>
<dd>As funções de acesso do Cloud IAM permitem que um usuário conclua tarefas específicas no recurso que é definido na política. Há dois tipos de funções de acesso: gerenciamento de plataforma e acesso de serviço. As funções de gerenciamento de plataforma definem as ações permitidas para gerenciar recursos no nível de plataforma, incluindo acesso de usuário, criação de instâncias e IDs de serviço e gerenciamento de grupos de recursos, por exemplo. Além disso, as funções de acesso de serviço definem as ações permitidas dentro do contexto de uso do serviço. Essas funções são customizadas com base no serviço que é selecionado dentro da política.</dd>
<dt>Ações</dt>
<dd>As ações são mapeadas para as funções do Cloud IAM para permitir que os usuários executem somente tarefas específicas quando eles são designados a funções diferentes. As ações permitidas para cada função podem mudar com base no serviço que está sendo acessado porque cada serviço define como essa função é mapeada para o uso do serviço. </dd>
<dt>Sistema de gerenciamento de acesso</dt>
<dd>O sistema de controle do Cloud IAM permite ou nega ações por usuários dentro do contexto de um serviço baseado na política designada. Quando um usuário tenta concluir uma ação específica, o sistema de controle usa os atributos que são definidos na política para determinar se o usuário tem permissão para executar essa tarefa.</dd>
</dl>






