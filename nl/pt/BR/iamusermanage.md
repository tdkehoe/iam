---

copyright:

  years: 2015, 2017

lastupdated: "2017-10-06"

---

{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:screen: .screen}
{:new_window: target="_blank"}

# Gerenciando usuários e políticas de acesso
{: #iamusermanage}

Dependendo das opções de acesso que você estiver autorizado a gerenciar, é possível visualizar e
gerenciar usuários na conta ou na organização. Como um proprietário da conta, será possível gerenciar usuários em qualquer uma das opções de acesso que você administrar e às quais o usuário tem acesso designado na conta atual.
{:shortdesc}

## Gerenciando Usuários

Para gerenciar usuários em sua conta, conclua as etapas a seguir:

1. Na barra de menus, clique em **Gerenciar** &gt; **Conta** &gt; **Usuários**. A janela Usuários exibe uma lista de usuários com seus endereços de e-mail para a conta selecionada atualmente.
2. Selecione o nome do usuário ou clique em **Gerenciar usuários** no menu **Ações**.
3. Em seguida, dependendo de qual ação você precisa tomar, poderá optar por remover o usuário, designar uma nova política ou gerenciar o acesso existente do usuário.

Revise as seções a seguir para obter informações adicionais sobre como gerenciar cada tipo de acesso.

Se for necessário revisar seu acesso designado em uma conta à qual tenha sido incluído, conclua as etapas a seguir:

1. Na barra de menus, clique em **Gerenciar** &gt; **Segurança** &gt; **Identidade e acesso** &gt; **Usuários**.
2. Selecione seu nome.
3. Revise suas funções designadas.

Caso precise de privilégios adicionais, deve-se entrar em contato com o gerenciador de organização ou proprietário da conta para atualizar a função Cloud Foundry ou entrar em contato com o administrador para o serviço ou instância de serviço para atualizar a política de serviço.

Para obter detalhes sobre os comandos da CLI que são usados para gerenciar contas, organizações e espaços, veja [Comandos para gerenciar contas, organizações e funções](/docs/cli/reference/bluemix_cli/bx_cli.html#bx_commands_acctorg).

## Acesso ao Cloud Foundry
{: #iammancfser}

Para gerenciar o acesso a organizações e espaços da conta, deve-se ser o proprietário da conta, o gerenciador de organização ou o gerenciador de espaço:

1. Na barra de menus, clique em **Gerenciar** &gt; **Segurança** &gt; **Identidade e acesso** &gt; **Usuários**.
2. Selecione o nome de usuário para o qual você deseja editar funções.
3. No menu **Ações** na seção Cloud Foundry, é possível:

  * Remover o usuário da organização
  * Editar a função de organização
  * Editar a função de espaço

Também será possível incluir um usuário em outra organização clicando em **Designar organização**, se você for o gerenciador de uma organização da qual o usuário ainda não for membro.


## Políticas de acesso de serviço ativadas por Identidade e por acesso
{: #iammanidaccser}

Para gerenciar políticas de serviço ou designar novas políticas de serviço aos usuários, deve-se ser o administrador de acesso da conta ou o administrador designado para o serviço ou para a instância de serviço específicos. Para obter mais informações sobre políticas de serviço e funções, veja [Políticas e funções de gerenciamento de identidade e acesso](/docs/iam/users_roles.html#iamusermanpol). Para obter detalhes sobre os comandos da CLI usados para gerenciar políticas, veja [Comandos para gerenciar chaves API e políticas](/docs/cli/reference/bluemix_cli/bx_cli.html#bx_commands_iam).

### Editando uma política existente

1. Na barra de menus, clique em **Gerenciar** &gt; **Segurança** &gt; **Identidade e acesso** &gt; **Usuários**.
2. Selecione o nome de usuário para o qual você deseja designar políticas de serviço.
3. Na linha da política que você deseja editar, selecione o menu **Ações** e, em seguida, clique em **Editar política**.
4. Edite a política.
5. Clique em **Salvar política**.

### Incluindo uma nova política

1. Na barra de menus, clique em **Gerenciar** &gt; **Segurança** &gt; **Identidade e acesso** &gt; **Usuários**.
2. Selecione o nome de usuário para o qual você deseja designar políticas de serviço.
3. Selecione **Designar políticas**.
4. Selecione um serviço.
5. Selecione **Todas as regiões atuais** ou uma região específica, se solicitado. 
**Nota**: nem todos os serviços requerem uma seleção de região.
6. Selecione **Todas as instâncias de serviço atuais** ou selecione uma instância de serviço específica.
7. Dependendo do serviço que você selecionou, será possível ver os campos a seguir. Se você não digitar valores para esses campos, a política será designada no nível da instância de serviço em vez do nível de depósito. 
    * **Tipo de recurso**: insira **depósito**.
    * **Recurso**: insira o nome de seu depósito.
8. Selecione uma função para definir o escopo de acesso da política.
9. Opcional: selecione **Incluir função** para especificar uma função adicional para a política.

### Removendo uma política

1. Na barra de menus, clique em **Gerenciar** &gt; **Segurança** &gt; **Identidade e acesso** &gt; **Usuários**.
2. Selecione o nome de usuário para o qual você deseja designar políticas de serviço.
3. Na linha da política que você deseja remover, selecione o menu **Ações** e, em seguida, clique em **Remover política**.
4. Revise os detalhes da política de usuário que você está prestes a remover e, em seguida, confirme clicando em **Remover política**.
  

## Permissões de serviços de infraestrutura

Para designar ou atualizar permissões de infraestrutura, clique no link **Designar acesso à infraestrutura**.

