---

copyright:

  years: 2017, 2018

lastupdated: "2017-11-16"

---

{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:screen: .screen}
{:new_window: target="_blank"}

# Tutorial Introdução
{: #getstarted}

Este tutorial é destinado a ajudá-lo a deixar o IBM Cloud Identity and Access Management (IAM) funcionando rapidamente, convidando usuários para sua conta e designando acesso ao Cloud IAM para esses usuários.

Este tutorial diz respeito aos recursos gerenciados pelo IAM. Para serviços que não suportam a criação de políticas do Cloud IAM para gerenciar acesso, é possível usar o [acesso do Cloud Foundry](/docs/iam/cfaccess.html#cfaccess).


## Etapa 1: convidar usuários e designar acesso inicial

É possível convidar um ou múltiplos usuários e configurar uma política de acesso inicial para os usuários no convite. Se você convidar múltiplos usuários em um convite, o mesmo acesso será designado a cada um deles. Na seção Acesso da página Convidar usuários, aparecem somente as seções que você tem permissão para designar.

Como proprietário da conta, é possível designar funções do Cloud IAM para usuários que você convida na seção Serviços. É possível fornecer acesso a todos os recursos em um grupo de recursos, todos os recursos para um serviço específico em um grupo de recursos, todos os serviços ativados pelo Identity and Access na conta ou um único recurso na política inicial que você designa no convite:

1. Acesse **Gerenciar** &gt; **Segurança** &gt; **Identity and Access** e, em seguida, selecione **Usuários**.
2. Clique em **Convidar usuários**.
3. Especifique o endereço de e-mail dos usuários que você deseja convidar.
4. Na seção **Acesso**, expanda a opção **Serviços**.
5. Escolha designar o acesso a um **Recurso** ou a recursos em um **Grupo de recursos**.
6. Dependendo de sua seleção, siga os prompts para especificar o acesso a uma instância de serviço individual, todos os serviços ativados pelo Identity and Access, todos os recursos em um grupo de recursos ou a um serviço específico dentro do grupo de recursos selecionado. Se você selecionou a opção de grupo de recursos, também é possível fornecer ao usuário o acesso para visualizar, editar ou gerenciar acesso para o grupo de recursos, selecionando uma função para acesso ao grupo de recursos.
7. Se você tiver permissão, também será possível designar o acesso ao Cloud Foundry ou à infraestrutura no convite.
8. Clique em **Convidar usuários**.

Para obter mais informações, veja [Convidando usuários e designando acesso](/docs/iam/iamuserinv.html#iamuserinv).

## Etapa 2: gerenciar acesso para usuários existentes

Depois de ter convidado usuários e designado o acesso inicial, você talvez deseje designar acesso adicional ou editar o acesso inicial designado para assegurar que todos os usuários em sua conta tenham o nível desejado de acesso.

### Designando novo acesso

É possível designar acesso a um usuário para um grupo de recursos ou um único recurso.

1. Na barra de menus, clique em **Gerenciar** &gt; **Segurança** &gt; **Identidade e acesso** e, em seguida, selecione **Usuários**.
2. Clique no nome do usuário para o qual você deseja designar acesso.
3. Clique em **Designar acesso**.
4. Escolha como deseja designar o acesso:
    * Selecione **Designar acesso dentro de um grupo de recursos** para designar acesso a todos os recursos em um grupo ou apenas a recursos para um serviço específico em um grupo. Também é possível fornecer ao usuário o acesso para visualizar, editar ou gerenciar acesso para o grupo de recursos, selecionando uma função para acesso ao grupo de recursos. Selecione **Sem acesso** se você deseja que o usuário tenha acesso somente ao recurso especificado e não ao grupo em que ele está organizado.
    * Selecione **Designar acesso a recursos** para designar acesso a todos os recursos ativados pelo Identity and Access na conta, todos os recursos de um serviço específico na conta, uma única instância ou um único recurso em uma instância de serviço específica.
5. Selecione qualquer combinação de funções para definir o escopo de acesso. Veja [Funções do Cloud IAM](/docs/iam/users_roles.html#iamusermanrol) para obter mais informações.
6. Clique em **Designar**.


### Editando acesso existente

É possível atualizar o acesso existente editando as funções designadas para um usuário.

1. Na barra de menus, clique em **Gerenciar** &gt; **Segurança** &gt; **Identidade e acesso** e, em seguida, selecione **Usuários**.
2. Selecione o nome do usuário para o qual você deseja editar o acesso.
3. Na linha para a política que você deseja editar, clique em **Editar política** no menu **Ações**.
4. Edite a política atualizando as funções designadas.
5. Clique em **Salvar**.

É possível remover o acesso de um usuário clicando na opção **Remover** do menu **Ações** para a política que você deseja remover.

## Próximas Etapas

Saiba o que mais é possível fazer com o Cloud IAM verificando a lista [Recursos do Cloud IAM](/docs/iam/index.html#features).
