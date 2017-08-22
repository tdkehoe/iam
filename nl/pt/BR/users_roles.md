---

copyright:

  years: 2015, 2016

lastupdated: "2017-08-08"

---

{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:screen: .screen}
{:new_window: target="_blank"}

# Funções e Permissões do Usuário
{: #userroles}

É possível gerenciar usuários nos serviços Platform and Infrastructure do {{site.data.keyword.Bluemix_notm}} na página **Usuários** de sua conta. Para acessar a página Usuários, no menu do {{site.data.keyword.Bluemix_notm}}, clique
em **Gerenciar** &gt; **Conta** &gt; **Usuários**. Os proprietários da conta executam todas as operações nas organizações e nos espaços, incluindo o gerenciamento de usuários e suas funções designadas. Os gerenciadores de organização e de espaço também têm acesso para gerenciar funções.
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

Os proprietários da conta são designados automaticamente à função de administrador de acesso da conta para Identidade e gerenciamento de acesso, que permite designar e gerenciar políticas de serviço. Esse tipo de controle de acesso permite a designação de políticas por serviço ou instância de serviço para permitir níveis de acesso para gerenciar recursos e usuários dentro do contexto designado.

### Políticas de serviço

Uma política designa a um usuário uma ou
mais funções para um conjunto de recursos usando uma combinação de atributos para definir o conjunto
de recursos aplicável. Ao designar uma política a um usuário, primeiro você especifica o serviço. Em seguida, é possível selecionar uma função ou funções para designar. Opções de configuração adicionais poderão estar disponíveis, dependendo do serviço selecionado.

Será possível designar e gerenciar políticas se você possuir a função adequada. A tabela a seguir mostra tarefas de gerenciamento de política e a função necessária para cada uma.

| Ações | Atribuição necessária |
|----------|---------|
| Criar políticas em uma conta para todos os serviços e instâncias | Administrador de acesso à conta |
| Criar uma política em um serviço em uma conta | Administrador de acesso à conta ou administrador no serviço na conta |
| Criar uma instância de serviço | Administrador de acesso à conta ou o administrador ou editor no serviço na conta |
| Criar uma política em uma instância de serviço | Administrador de acesso à conta, administrador no serviço na conta ou administrador na instância de serviço |
{: caption="Tabela 4. Tarefas administrativas para gerenciar políticas de serviços ativadas para Identidade e acesso" caption-side="top"}

### Funções de política de serviço
{: #iamusermanrol}

Funções são uma coleção de ações; as ações que são mapeadas para essas funções são específicas de
serviço. Consulte a documentação do serviço selecionado para obter detalhes adicionais sobre os tipos de ações que cada função permite.

Além das descrições das funções fornecidas no console, a tabela a seguir fornece exemplos de algumas das tarefas que os usuários designados a cada função podem conseguir fazer no serviço do {{site.data.keyword.containershort_notm}}.  

| Função | Descrição das ações | Exemplo de ações|
|:-----------------|:-----------------|:-----------------|
| Viewer | Executa ações que não mudam o estado; ações somente leitura | <ul><li>Listar clusters</li><li>Visualizar detalhes para um cluster</li></ul>|
| Aplicativos | Executa ações que modificam o estado e criam ou excluem sub-recursos |<ul><li>Ligar um serviço a um cluster</li><li>Criar um webhook</li></ul> |
| Operador | Executa ações necessárias para configurar e operar recursos. | <ul><li>Incluir ou remover nós do trabalhador</li><li>Reinicializar ou recarregar nós do trabalhador</li><li>Ligar um serviço a um cluster</li></ul> |
| Administrator | Executa todas as ações, incluindo a capacidade de gerenciar o controle de acesso |<ul><li>Remover um Cluster</li><li>Crie um cluster</li><li>Atualizar políticas de acesso de usuário</li><li>Todas as ações que um visualizador, um editor e um operador podem executar</li></ul>|
{: caption="Tabela 5. Exemplo de funções e ações do usuário" caption-side="top"}


## Permissões de infraestrutura
{: #infrapermissions}

É possível configurar as permissões a seguir ao convidar um usuário:

| Permissão de infraestrutura | Descrição das ações |
|---------------------------|------------------------|
|Visualização Apenas | Os usuários com essa permissão podem visualizar somente os itens dentro do sistema.|
|Usuário Básico | Os usuários com essa permissão podem executar ações básicas dentro do sistema, como incluir um chamado e
gerenciar dispositivos. |
|Super usuário | Os usuários com essa permissão podem executar todas as ações disponíveis no sistema. |
{:caption="Tabela 6. Permissões de infraestrutura" caption-side="top"}

Permissões adicionais podem ser configuradas depois que o usuário aceitou o convite.
