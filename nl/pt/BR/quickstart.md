---

copyright:

  years: 2017, 2018

lastupdated: "2018-06-06"

---

{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:screen: .screen}
{:new_window: target="_blank"}

# Tutorial Introdução
{: #getstarted}

Este tutorial é destinado a ajudá-lo a deixar o IBM Cloud Identity and Access Management (IAM) funcionando rapidamente, convidando usuários para sua conta e designando acesso ao Cloud IAM para esses usuários.

Este tutorial se aplica somente a [recursos](/docs/resources/acct_resources.html#resource) gerenciados pelo IAM. Para serviços que não suportam a criação de políticas do Cloud IAM para gerenciar acesso, é possível usar o [acesso do Cloud Foundry](/docs/iam/cfaccess.html#cfaccess).


## Etapa 1: convidar usuários e designar acesso inicial

É possível convidar um ou múltiplos usuários e configurar uma política de acesso inicial para os usuários no convite. Se você convidar múltiplos usuários em um convite, o mesmo acesso será designado a cada um deles. Na seção **Acesso** da página Convidar usuários, você vê somente as seções que você tem permissão para designar.

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

## Etapa 2: criar grupos de acesso

Para aperfeiçoar o processo de designação de acesso aos usuários em sua conta, é possível criar grupos
de acesso que sejam formados por usuários e IDs de serviço que você seleciona e, em seguida, é possível
designar acesso facilmente definindo uma política única para o grupo inteiro.

### Configure seus grupos

Para criar um grupo de acesso, conclua as etapas a seguir:

1. Na barra de menus, clique em **Gerenciar** &gt; **Segurança** &gt; **Identidade e acesso** e, em seguida, selecione **Grupos de acesso**.
2. Clique em **Criar**.
3. Insira um nome e uma descrição opcional para seu grupo e clique em **Criar**.

Em seguida, continue a configurar seu grupo incluindo usuários ou IDs de serviço:

1. Selecione o nome do grupo que deseja incluir.
2. Clique em **Incluir usuários**.
3. Selecione os usuários que deseja incluir na lista e clique em **Incluir no grupo**.
4. Para incluir IDs de serviço no grupo, clique na guia **IDs de serviço** e
clique em **Incluir ID de serviço**.
5. Selecione os IDs que deseja incluir na lista e clique em **Incluir no grupo**.

### Designe acesso aos seus grupos

Depois de ter criado seus grupos, é possível designar acesso a todas as entidades dentro do grupo com uma
política única.

1. Na barra de menus, clique em **Gerenciar** &gt; **Segurança** &gt; **Identidade e acesso** e, em seguida, selecione **Grupos de acesso**.
2. Selecione o nome do grupo para o qual você deseja designar acesso.
3. Clique em **Designar acesso** para configurar uma política que designa acesso a
um único recurso na conta ou a todos os recursos em um grupo de recursos.

Ao organizar recursos em grupos de recursos e usuários em grupos de acesso, é possível designar a um
grupo de usuários acesso a um grupo de recursos com uma política única, reduzindo, portanto, o número geral de
políticas que você precisa gerenciar.
{: tip}


## Etapa 3: gerenciar acesso para usuários existentes

Depois de ter convidado usuários, designado acesso inicial e criado seus grupos de acesso, talvez você
queira designar acesso adicional ou editar o acesso inicial que você designou para assegurar que todos os
usuários e grupos em sua conta tenham o nível de acesso desejado.

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
