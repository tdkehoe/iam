---

copyright:

  years: 2015, 2016

lastupdated: "2017-10-06"

---

{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:screen: .screen}
{:new_window: target="_blank"}

# Funções e Permissões do Usuário
{: #userroles}

É possível gerenciar usuários na plataforma do {{site.data.keyword.Bluemix_notm}} e serviços de infraestrutura na página **Usuários** de sua conta. Para acessar a página Usuários, no menu do {{site.data.keyword.Bluemix_notm}}, clique
em **Gerenciar** &gt; **Conta** &gt; **Usuários**. Os proprietários da conta podem executar todas as operações para gerenciar usuários, permissões, organizações e espaços. Os gerenciadores de organização e gerenciadores de espaço do Cloud Foundry também têm acesso para gerenciar permissões para usuários incluídos em cada organização e espaço gerenciado.
{:shortdesc}

Se você for um usuário incluído na conta de outra pessoa e desejar visualizar suas funções e permissões designadas, acesse **Gerenciar** &gt; **Segurança** &gt; **Identidade e acesso** &gt; **Usuários** e clique em seu nome.

## Funções da conta
{: #userrolesinfo}

No nível de conta, há duas funções que permitem o acesso a diferentes recursos de gerenciamento de conta:

| Função da conta | Permissões |
|----------------|---------|
|Proprietário | Um proprietário para a conta tem acesso a seus perfis, usuários, informações de faturamento, notificações de gastos e painel de uso. Na página Usuários, o proprietário pode convidar novos usuários e ajustar as funções. O proprietário também pode incluir créditos promocionais, configurar ou mudar o limite de faturamento, configurar o acesso de
serviço e gerenciar organizações e espaços. |
|Membro | Um membro tem acesso a seu perfil, à página Usuários que exibe os usuários ativos na conta e aos créditos da conta e limites de faturamento no cabeçalho do {{site.data.keyword.Bluemix_notm}}.  |
{:caption="Tabela 1. Funções e permissões de conta" caption-side="top"}

Todos os novos usuários são incluídos como um membro da conta. É possível designar funções de organização e espaço para convidados, a fim de ativar visualizações e permissões específicas no
{{site.data.keyword.Bluemix_notm}}. Uma vez que seus convidados aceitam o convite e se associam ao {{site.data.keyword.Bluemix_notm}}, é possível editar suas funções na página Usuários.

## Funções do Cloud Foundry
{: #cfroles}

As funções do Cloud Foundry incluem as permissões de acesso para organizações e espaços definidos na conta. As funções do Cloud Foundry não ativam as permissões de usuário para concluir ações dentro do contexto de um serviço. As funções a seguir podem ser designadas no nível de organização:

| Função organizacional | Permissões |
|-------------------|-------------|
|Gerente | Os gerenciadores de organização podem criar, visualizar, editar ou excluir espaços dentro da organização, visualizar o uso e cota da organização, convidar os usuários para a organização, gerenciar quem tem acesso à organização e suas funções na organização, além de gerenciar domínios customizados para a organização. |
|Gerenciador de faturamento | Gerenciadores de faturamento podem visualizar informações de uso de tempo de execução e serviço para a organização na página de Painel de uso.  |
|Auditor | Auditores da organização podem visualizar o conteúdo do aplicativo e do serviço na organização. Os auditores também podem visualizar os usuários na organização e suas funções designadas, além da cota da organização. |
{:caption="Tabela 2. Funções e permissões de organização" caption-side="top"}

As funções a seguir podem ser designadas no nível de espaço:

| Função de espaço | Permissões |
|------------|-------------|
|Gerente | Os gerenciadores de espaço podem incluir usuários existentes e gerenciar funções dentro do espaço. O gerenciador de espaço também pode visualizar o número de instâncias, ligações de serviço e
o uso recurso para cada aplicativo no espaço. |
|Desenvolvedor | Desenvolvedores de espaço podem criar, excluir e gerenciar aplicativos e serviços dentro do espaço. Algumas das tarefas de gerenciamento incluem implementar aplicativos, iniciar ou parar
aplicativos, renomear um aplicativo, excluir um aplicativo, renomear um espaço, ligar ou desvincular um serviço para um aplicativo, visualizar o número ou as instâncias, ligações de serviço e uso de recurso
para cada aplicativo no espaço. Além disso, o desenvolvedor de espaço pode associar uma URL interna ou externa com um aplicativo no espaço.   |
|Auditor | Auditores de espaço têm acesso somente leitura a todas as informações sobre o espaço, como informações sobre o número de instâncias, ligações de serviço e uso de recurso para cada aplicativo no
espaço. |
{:caption="Tabela 3. Funções e permissões de espaço" caption-side="top"}

**Nota**: os usuários designados à função de espaço de gerenciador ou desenvolvedor podem acessar a variável de ambiente VCAP_SERVICES. No entanto, um usuário designado à função de auditor não pode acessar VCAP_SERVICES.

## Políticas e funções de Identidade e gerenciamento de acesso
{: #iamusermanpol}

Os proprietários da conta são automaticamente designados à função de administrador de conta para Identidade e gerenciamento de acesso (IAM) que permite designar e gerenciar políticas de serviço. As políticas de serviço podem ser designadas a usuários individuais ou aos IDs de serviço e a política designada pode definir o acesso para um serviço inteiro ou no nível da instância individual.

### Políticas de serviço

Uma política designa a um usuário ou um ID de serviço uma ou múltiplas funções para um conjunto de recursos usando uma combinação de atributos para definir o conjunto de recursos aplicável. Ao designar uma política, primeiro, você especifica o serviço. Em seguida, é possível selecionar uma função ou funções para designar. Opções de configuração adicionais poderão estar disponíveis, dependendo do serviço selecionado.

Será possível designar e gerenciar políticas se você possuir a função adequada. A tabela a seguir mostra tarefas de gerenciamento de política e a função necessária para cada uma.

| Ações | Função necessária |
|----------|---------|
| Criar políticas em uma conta para todos os serviços e instâncias | Administrador da conta |
| Criar uma política em um serviço em uma conta | Administrador da conta ou administrador no serviço na conta |
| Criar uma instância de serviço | Administrador da conta ou o administrador ou editor no serviço na conta |
| Criar uma política em uma instância de serviço | Administrador da conta ou administrador no serviço na conta ou administrador na instância de serviço |
{: caption="Tabela 4. Tarefas administrativas para gerenciar políticas de serviços ativadas por IAM" caption-side="top"}

### Funções de política de serviço
{: #iamusermanrol}

O IAM permite gerenciar e definir o acesso para usuários e recursos em sua conta. Se o serviço que você usa puder ser gerenciado usando IAM para controle de acesso de usuário, então, haverá dois tipos de funções que permitem ações diferentes em sua conta: gerenciamento de plataforma e funções de acesso de serviço.

<dl>
<dt>Funções de gerenciamento de plataforma</dt>
<dd>Funções disponíveis para todos os serviços que podem ser gerenciados usando o IAM para controle de acesso de usuário, que incluem administrador, editor, operador, visualizador e o administrador de faturamento. Essas funções são mapeadas para ações do usuário que podem ser executadas em recursos {{site.data.keyword.Bluemix_notm}} no nível da plataforma. Por exemplo, algumas dessas ações são a capacidade de criar instâncias, conectar instâncias a um aplicativo, gerenciar IDs de serviço, gerenciar usuários e permissões e gerenciar faturamento e cotas para a conta. </dd>
<dt>Funções de acesso de serviço</dt>
<dd>Essas funções são específicas do serviço. As funções de gerente, escritor e leitor definem a capacidade de o usuário usar o serviço e executar chamadas APIs de serviço. Como cada serviço define as ações que um usuário com uma determinada função pode executar, é possível que um serviço não use todas as funções disponíveis descritas nesta documentação. </dd>
</dl>

**Nota**: pode não ser possível ver todas as funções listadas como opções ao designar políticas na UI, pois apenas as funções aplicáveis ao serviço que você selecionou na política são exibidas. Para obter informações específicas sobre quais funções são ativadas e quais ações que cada função de acesso permite para cada serviço, consulte a documentação para esse serviço.


#### Funções de gerenciamento de plataforma

Funções de gerenciamento de plataforma permitem que os usuários sejam designados a diferentes níveis de permissão para executar ações da plataforma. Além das descrições das funções fornecidas no console, as tabelas a seguir fornecem exemplos para algumas das ações de gerenciamento de plataforma que os usuários designados a cada função podem ser capazes de fazer.

| Função de gerenciamento de plataforma  | Ações que um usuário pode executar em serviços na conta | Ações para IDs de serviço |
|:-----------------|:--------------|:---------------|
| Viewer | Visualizar instâncias | Visualizar IDs e chaves API |
| Operador |  Visualizar e ligar instâncias de serviço | Não aplicável |
| Aplicativos |  Criar, excluir, editar, suspender, continuar, visualizar, ligar instâncias de serviço | Excluir IDs e criar e excluir chaves API |
| Administrator |  Todas as ações de gerenciamento para serviços | Criar e excluir IDs e chaves API, designar políticas a IDs |
{: caption="Tabela 5. Exemplo de funções e ações de gerenciamento de plataforma" caption-side="top"}

Alguns serviços podem mapear ações específicas para as funções de gerenciamento de plataforma que estão relacionadas ao gerenciamento do serviço em vez do acesso do serviço. Como um exemplo, consulte a tabela a seguir que detalha as ações do serviço {{site.data.keyword.containershort_notm}} que são mapeadas para essas funções.


| Função de gerenciamento de plataforma | Descrição das ações | Exemplo de ações para o serviço {{site.data.keyword.containershort_notm}} |
|:-----------------|:-----------------|:-----------------|
| Viewer | É possível visualizar instâncias de serviço, mas não é possível modificá-las  | <ul><li>Listar clusters</li><li>Visualizar detalhes para um cluster</li></ul>|
| Aplicativos | Execute todas as ações da plataforma, exceto para gerenciar a conta e designar políticas de acesso |<ul><li>Ligar um serviço a um cluster</li><li>Criar um webhook</li></ul> |
| Operador | Execute ações de plataforma necessárias para configurar e operar instâncias de serviço, como visualizar um painel de serviço. | <ul><li>Incluir ou remover nós do trabalhador</li><li>Reinicializar ou recarregar nós do trabalhador</li><li>Ligar um serviço a um cluster</li></ul> |
| Administrator | Executa todas as ações de plataforma com base no recurso que esta função está sendo designada, incluindo designar políticas de acesso a outros usuários. |<ul><li>Remover um Cluster</li><li>Crie um cluster</li><li>Atualizar políticas de acesso de usuário</li><li>Todas as ações que um visualizador, um editor e um operador podem executar</li></ul>|
{: caption="Tabela 6. Exemplo de funções e ações de gerenciamento de plataforma" caption-side="top"}


#### Funções de acesso de serviço

Funções de acesso de serviço permitem que os usuários sejam designados a diferentes níveis de permissão para chamar a API do serviço. A tabela a seguir fornece ações de exemplo que podem ser tomadas dependendo das funções de acesso de serviço designadas com base no uso do serviço {{site.data.keyword.objectstorageshort}}.

**Nota**: as ações que podem ser tomadas para cada função designada variam com base no serviço que você selecionou para a política.

| Função de acesso de serviço | Descrição das ações | Exemplo de ações para o serviço {{site.data.keyword.objectstorageshort}} |
|:-----------------|:-----------------|:-----------------|
|  Reader | Execute ações somente leitura em um serviço como visualizar recursos específicos de serviço | Listar e fazer download de objetos |
| Gravador | Escritores têm permissões além da função leitor, incluindo a criação e a edição de recursos específicos do serviço. | Criar e destruir depósitos e objetos |
| Gerente | Gerentes têm permissões além da função de escritor para concluir ações privilegiadas, conforme definido pelo serviço. Além disso, é possível criar e editar recursos específicos do serviço. | Gerenciar todos os aspectos de armazenamento de dados, criar e destruir depósitos e objetos |
{: caption="Tabela 7. Exemplo de funções e ações de usuário de acesso de serviço" caption-side="top"}


## Permissões de infraestrutura
{: #infrapermissions}

É possível configurar as permissões iniciais a seguir quando você convida um usuário:

| Permissão configurada | Descrição das ações |
|---------------------------|------------------------|
|Visualização Apenas | Os usuários com essa permissão podem visualizar somente os itens dentro do sistema.|
|Usuário Básico | Os usuários com essa permissão podem executar ações básicas dentro do sistema, como incluir um chamado e
gerenciar dispositivos. |
|Super usuário | Os usuários com essa permissão podem executar todas as ações disponíveis no sistema. |
{:caption="Tabela 8. Permissões de infraestrutura" caption-side="top"}

Permissões adicionais podem ser configuradas depois que o usuário aceitou o convite. A permissão inicial configurada no momento do convite não concede acesso aos dispositivos, portanto, deve-se conceder acesso ao dispositivo no Portal de controle depois que o usuário aceita o convite.
