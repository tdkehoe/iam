---

copyright:

  years: 2015, 2017

lastupdated: "2017-05-30"

---

{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:screen: .screen}
{:new_window: target="_blank"}

# Gerenciando usuários e o acesso
{: #iamusermanage}

Dependendo das opções de acesso que você estiver autorizado a gerenciar, é possível visualizar e
gerenciar usuários na conta ou na organização. Como um proprietário da conta, será possível gerenciar usuários em qualquer uma das opções de acesso que você administrar e às quais o usuário tem acesso designado na conta atual.
{:shortdesc}

Para gerenciar usuários em sua conta, conclua as etapas a seguir:

1. Na barra de menus, clique em **Gerenciar** &gt; **Conta** &gt; **Usuários**. A janela Usuários exibe uma lista de usuários com seus endereços de e-mail para a conta selecionada atualmente. 
2. Selecione o nome do usuário ou clique em **Gerenciar usuários** no menu **Ações**. 
3. Em seguida, dependendo do acesso que você pode gerenciar, atualize o acesso para o usuário nas seções Políticas de serviço ou Funções do Cloud Foundry ou clique no link para acessar a página Designar acesso à infraestrutura.

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


## Serviços ativados para identidade e acesso
{: #iammanidaccser}

Para gerenciar políticas de serviço ou designar novas políticas de serviço aos usuários, deve-se ser o administrador de acesso da conta ou o administrador designado para o serviço ou para a instância de serviço específicos.

1. Na barra de menus, clique em **Gerenciar** &gt; **Segurança** &gt; **Identidade e acesso** &gt; **Usuários**. 
2. Selecione o nome de usuário para o qual você deseja designar políticas de serviço.
3. Selecione **Designar políticas de serviço** para criar uma nova política de serviço ou no menu **Ações**, na seção Políticas de serviço, será possível:
  
  * Editar a política
  * Remover a política

Para obter mais informações sobre políticas de serviço e funções, veja [Políticas e funções de gerenciamento de identidade e acesso](/docs/iam/users_roles.html#iamusermanpol).

## Serviços de Infraestrutura

Para designar ou atualizar permissões de infraestrutura, clique no link **Designar acesso à infraestrutura**.
