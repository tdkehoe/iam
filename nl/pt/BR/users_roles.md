---

copyright:

  years: 2015, 2018

lastupdated: "2018-06-07"

---

{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:screen: .screen}
{:tip: .tip}
{:new_window: target="_blank"}

# Acesso ao IAM
{: #userroles}

Todos os serviços que são organizados em um grupo de recursos em sua conta são gerenciados usando o {{site.data.keyword.Bluemix_notm}} Identity and Access Management (IAM). Os proprietários de contas são designados automaticamente à função de administrador de conta para o Cloud IAM. Como administrador de conta, é possível designar e gerenciar o acesso para usuários, criar grupos de recursos e provisionar instâncias de serviço designando as funções do Cloud IAM. Você fornece acesso para usuários e IDs de serviço criando políticas que configuram um destino para o usuário ou ID de serviço acessar e uma função que define qual tipo de acesso é permitido.


## O que são políticas do Cloud IAM e quem pode designá-las?
{: #iamusermanpol}

Uma política concede a um usuário ou ID de serviço uma ou múltiplas funções para um conjunto de recursos
para permitir que ações específicas sejam tomadas dentro do contexto dos recursos de destino especificados. Ao designar uma política, primeiro você escolhe entre configurar a política para um grupo de recursos ou um recurso individual. Em seguida, dependendo de sua seleção inicial, é possível selecionar um serviço dentro de um grupo de recursos ou uma única instância para o recurso selecionado. Mais opções de configuração podem estar disponíveis, dependendo do serviço selecionado. Finalmente, é possível selecionar uma função ou funções, para designar. 

Será possível designar e gerenciar políticas se você possuir a função adequada. A tabela a seguir mostra as tarefas de gerenciamento de política e a função que é necessária para cada uma.

| Ações | Função necessária |
|----------|---------|
| Criar uma política em uma conta para todos os serviços e instâncias | Proprietário ou administrador de conta em todos os serviços na conta | 
| Criar uma política em um serviço em uma conta | Proprietário ou administrador da conta no serviço na conta |
| Criar uma política em uma instância de serviço | Proprietário da conta, administrador no serviço na conta, administrador em todos os serviços no grupo de recursos relevantes ou administrador na instância de serviço |
| Criar uma política para gerenciar um grupo de recursos | Proprietário ou administrador da conta para um grupo de recursos |
{: caption="Tabela 1. Usuários que têm permissão para criar políticas de acesso" caption-side="top"} 


## Funções do Cloud IAM
{: #iamusermanrol}

Com o Cloud IAM, é possível gerenciar e definir acesso para usuários e recursos em sua conta. Há dois
tipos de funções que podem ser designadas: funções de gerenciamento de plataforma e funções de acesso de
serviço.

<dl>
<dt>Funções de gerenciamento de plataforma</dt> 
<dd>As funções de gerenciamento de plataforma abrangem uma gama de ações, incluindo a capacidade de criar instâncias, gerenciar IDs de serviço, gerenciar usuários e permissões e criar grupos de recursos. As funções da plataforma mais comuns são administrador, editor, operador, visualizador. </dd>
<dt>Funções de acesso de serviço</dt>
<dd>As funções de acesso ao serviço definem a capacidade de um usuário ou serviço para executar ações em uma instância de serviço, como acessar a UI ou executar chamadas API. Há três funções possíveis: gerenciador, gravador e leitor. </dd>
</dl> 

Talvez você não veja todas as funções listadas como opções ao designar políticas na UI, pois apenas as
funções disponíveis para o serviço que você selecionou são exibidas. Para obter informações específicas sobre quais funções são ativadas e quais ações que cada função de acesso permite para cada serviço, consulte a documentação para esse serviço.
{: tip}

Usando uma combinação dessas funções em uma política de acesso único, é possível fornecer acesso de baixa granularidade para usuários e IDs de serviço designando acesso em qualquer um dos seguintes:

* Todos os recursos na conta
* Todos os recursos em todos os serviços que pertencem a um grupo de recursos individuais, bem como a capacidade de gerenciar o grupo de recursos
* Todos os recursos em um único serviço em um grupo de recursos, bem como a capacidade de gerenciar o grupo de recursos
* Todos os recursos em um único serviço na conta, independentemente do grupo de recursos ao qual eles são designados
* Recursos em uma instância individual
* Um tipo de recurso único em uma instância, por exemplo, um depósito em uma instância do {{site.data.keyword.objectstorageshort}}

Para permitir que outro usuário tenha acesso total à conta com o propósito de gerenciar acesso de usuário e gerenciar todos os recursos da conta, incluindo a capacidade de criar grupos de recursos, configure uma política que dê ao usuário acesso a todos os recursos da conta selecionando **Todos os serviços ativados pelo Identity and Access** com a função **Administrador** designada. 
{: tip}

### Funções de gerenciamento de plataforma

As funções de gerenciamento de plataforma permitem que os usuários sejam designados a diferentes níveis de permissão para executar ações da plataforma na conta. As tabelas a seguir fornecem exemplos para algumas das ações de gerenciamento de plataforma que os usuários
designados a cada função podem executar. É possível consultar a documentação para cada serviço para entender como as funções se aplicam a usuários dentro do contexto do serviço que está sendo usado.

| Detalhes da política de acesso  | Ações que um usuário pode executar em serviços na conta | Ações para IDs de serviço | Ações para acesso a grupos de recursos | Ação em recursos em grupos de recursos | Ações para gerenciamento de grupos de acesso |
|:-----------------|:--------------|:---------------|:----------------|:-----------------|:--------------|
| Designar acesso a | Um ou todos os serviços ativados por IAM | Serviço de identidade do IAM | Grupo de recursos selecionados | Serviço selecionado em um grupo de recursos | Grupos de acesso ao IAM |
| Função de visualizador | Visualizar instâncias, aliases, ligações e credenciais | Visualizar IDs e chaves API | Visualizar grupo de recursos | Visualizar somente instâncias especificadas no grupo de recursos | Visualizar grupos de acesso e membros |
| Função de operador |  Visualizar instâncias e gerenciar aliases, ligações e credenciais | Não aplicável | Não aplicável | Não aplicável | Não aplicável |
| Função do editor |  Criar, excluir, editar e visualizar instâncias. Gerenciar aliases, ligações e credenciais | Criar e excluir IDs e chaves API | Visualizar e editar o nome do grupo de recursos | Criar, excluir, editar, suspender, continuar, visualizar e ligar somente as instâncias especificadas no grupo de recursos | Visualizar, criar, excluir e editar grupos de acesso na conta |
| Função de administrador |  Todas as ações de gerenciamento para serviços | Criar e excluir IDs e chaves API, designar políticas a IDs | Visualizar, editar e gerenciar o acesso para o grupo de recursos | Todas as ações de gerenciamento para as instâncias especificadas no grupo de recursos | Visualizar, criar, excluir, editar e gerenciar o acesso para trabalhar com grupos de acesso |
{: caption="Tabela 2. Exemplo de funções e ações de gerenciamento de plataforma" caption-side="top"}
{: #platformrolestable}

Alguns serviços podem mapear ações específicas para as funções de gerenciamento de plataforma que estão relacionadas ao gerenciamento do serviço em vez do acesso do serviço. Como um exemplo, consulte a tabela a seguir que detalha as ações do serviço {{site.data.keyword.containershort_notm}} que são mapeadas para essas funções.


| Função de gerenciamento de plataforma | Descrição das ações | Exemplo de ações para o {{site.data.keyword.containershort_notm}} |
|:-----------------|:-----------------|:-----------------|
| Visualizador | É possível visualizar instâncias de serviço, mas não é possível modificá-las  | <ul><li>Listar clusters</li><li>Visualizar detalhes para um cluster</li></ul>|
| Aplicativos | Execute todas as ações da plataforma, exceto para gerenciar a conta e designar políticas de acesso |<ul><li>Ligar um serviço a um cluster</li><li>Criar um webhook</li></ul> |
| Operador | Execute ações de plataforma necessárias para configurar e operar instâncias de serviço, como visualizar um painel de serviço. | <ul><li>Incluir ou remover nós do trabalhador</li><li>Reinicializar ou recarregar nós do trabalhador</li><li>Ligar um serviço a um cluster</li></ul> |
| Administrador | Executa todas as ações de plataforma com base no recurso que esta função está sendo designada, incluindo designar políticas de acesso a outros usuários. |<ul><li>Remover um Cluster</li><li>Crie um cluster</li><li>Atualizar políticas de acesso de usuário</li><li>Todas as ações que um visualizador, um editor e um operador podem executar</li></ul>|
{: caption="Tabela 3. Exemplo de funções e ações de gerenciamento de plataforma para o serviço {{site.data.keyword.containershort_notm}}" caption-side="top"}


### Funções de acesso de serviço

As funções de acesso ao serviço permitem que os usuários sejam designados a diferentes níveis de permissão para chamar a API do serviço e acessar a UI para o serviço. A tabela a seguir fornece exemplos de ações que podem ser tomadas dependendo das funções designadas com base no uso do serviço {{site.data.keyword.objectstorageshort}}.

**Nota**: as ações que podem ser tomadas para cada função designada variam com base no serviço que você selecionou para a política.

| Função de acesso de serviço | Descrição das ações | Exemplo de ações para o serviço {{site.data.keyword.objectstorageshort}} |
|:-----------------|:-----------------|:-----------------|
|  Leitor | Execute ações somente leitura em um serviço como visualizar recursos específicos de serviço | Listar e fazer download de objetos |
| Gravador | Escritores têm permissões além da função leitor, incluindo a criação e a edição de recursos específicos do serviço. | Criar e destruir depósitos e objetos |
| Gerente | Gerentes têm permissões além da função de escritor para concluir ações privilegiadas, conforme definido pelo serviço. Além disso, é possível criar e editar recursos específicos do serviço. | Gerenciar todos os aspectos de armazenamento de dados, criar e destruir depósitos e objetos |
{: caption="Tabela 4. Exemplo de funções de usuário e ações de acesso ao serviço" caption-side="top"}

