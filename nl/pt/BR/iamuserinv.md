---

copyright:

  anos: 2015, 2017 última atualização: "16-11-2017"

---

{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:screen: .screen}
{:new_window: target="_blank"}
{:tip: .tip}

# Convidando usuários e designando acesso
{: #iamuserinv}

Para convidar usuários e gerenciar convites pendentes, deve-se ser um proprietário da conta, um
gerenciador de organização ou ter permissões de infraestrutura para incluir usuários. É possível convidar
usuários, cancelar convites e reenviar um convite pendente para um usuário convidado. Além disso, é possível convidar um único usuário ou múltiplos usuários de uma vez.  
{:shortdesc}

## Convidando usuários

Para convidar usuários ou gerenciar convites de usuários em sua conta, conclua as etapas a seguir: 

1. Na barra de menus, clique em **Gerenciar** &gt; **Segurança** &gt; **Identidade e acesso** e, em seguida, clique em **Usuários**. A página Usuários exibe uma lista de usuários com seus endereços de e-mail e o status atual para a conta atualmente selecionada.
2. Clique em **Convidar usuários**.
3. Especifique o endereço de e-mail do usuário. Se você estiver convidando mais de um usuário com um convite único, eles serão todos designados ao mesmo acesso.
4. Inclua uma ou mais das opções de acesso que você gerencia. Deve-se designar pelo menos uma opção de acesso. Para quaisquer opções de acesso adicionais que você não incluir nem configurar, o valor padrão de
*no access* é designado. Você pode ver uma ou todas as opções de acesso a seguir, dependendo das opções que você está autorizado a gerenciar: **Serviços**, **Acesso ao Cloud Foundry**, **Acesso à infraestrutura do {{site.data.keyword.Bluemix_notm}}**. Para obter mais informações, veja [Designando acesso de usuário](/docs/iam/iamuserinv.html#assignaccess).

Se você determinar que um usuário não precisa de acesso, será possível cancelar um convite de quaisquer usuários que forem mostrados em um estado **Processando** ou **Pendente** na coluna **Status**. Se um usuário convidado não tiver recebido um convite, será possível reenviar o convite para qualquer usuário em um estado **Pendente**.

Se você deseja convidar usuários usando a CLI, veja o comando [bluemix iam account-user-invite](/docs/cli/reference/bluemix_cli/bx_cli.html#bluemix_iam_account_user_invite).
{: tip}

## Designando Acesso do Usuário
{: #assignaccess}

Você designa acesso para os usuários à medida que os convida, designando políticas do Cloud IAM, acesso ao Cloud Foundry e permissões de infraestrutura. Dependendo das opções de acesso que você está autorizado a gerenciar, é possível convidar e fornecer acesso para usuários na conta, grupos de recursos, organizações, espaços, instâncias de serviço e infraestrutura. As seções a seguir descrevem os três tipos de acesso que podem ser designados a um usuário convidado.

### Serviços

É possível designar acesso criando uma política de acesso inicial ao Cloud IAM quando você convida um novo usuário. Nesta seção, é possível fornecer a um usuário acesso aos serviços em um grupo de recursos com acesso ao grupo de recursos ou a um recurso individual na conta. Depois que o usuário aceita o convite, é possível designar acesso adicional. Veja [Gerenciando acesso ao IAM](/docs/iam/mngiam.html#iammanidaccser) para obter detalhes sobre como editar políticas para incluir funções extras, designar mais acesso ou remover uma política para um usuário.

**Nota**: dependendo de qual serviço você seleciona ao designar a política, talvez não veja todos os campos que são descritos nos procedimentos a seguir.

#### Acesso ao grupo de recursos

É possível designar acesso a todos os serviços em um grupo de recursos ou a um único tipo de serviço em um grupo de recursos.

1. Na tela **Convidar usuários**, expanda a seção **Serviços**.
2. Selecione para designar acesso aos recursos em um **Grupo de recursos**.
3. Escolha um grupo de recursos.
4. Escolha uma função para o campo **Designar acesso a um grupo de recursos** para permitir que o usuário visualize o grupo de recursos no painel, edite o nome do grupo de recursos ou gerencie o acesso de usuário ao grupo. É possível selecionar **Sem acesso**, se você deseja que o usuário tenha acesso somente ao recurso especificado e não ao grupo em que ele está organizado.
5. Selecione um serviço no grupo de recursos ou opte por fornecer acesso a todos os serviços no grupo selecionado. 
6. Selecione qualquer combinação de funções para designar o acesso desejado. Este acesso só se aplica aos recursos que você selecionou para a política. Ela não fornece acesso ao contêiner real que é o grupo de recursos.


#### Acesso ao recurso

É possível designar acesso a um único recurso em sua conta para a instância.

1. Na tela **Convidar usuários**, expanda a seção **Serviços**.
2. Selecione para designar acesso a um **Recurso**.
3. Selecione um serviço.
4. Selecione **Todas as regiões atuais** ou uma região específica, se solicitado. 
5. Selecione **Todas as instâncias de serviço atuais** ou selecione uma instância de serviço específica.
6. Dependendo do serviço que você selecionou, será possível ver os campos a seguir. Se você não digitar valores para esses campos, a política será designada no nível da instância de serviço em vez do nível de depósito. 
    * **Tipo de recurso**: insira **depósito**.
    * **ID do recurso**: Insira o nome do bucket.
7. Selecione qualquer combinação de funções para designar o acesso desejado.

Para obter informações mais específicas sobre as funções ao designar acesso, veja [Acesso ao IAM](/docs/iam/users_roles.html#iamusermanrol).

### Acesso ao Cloud Foundry

Ao convidar novos usuários, é possível escolher incluir o usuário em uma organização na conta. Se você incluir o usuário em uma organização, será possível designar uma função de organização ao usuário. Em seguida, você optará por fornecer ao usuário convidado acesso a qualquer um ou a todos os espaços na organização selecionada com uma função de espaço designada.

1. Na tela **Convidar usuários**, expanda a seção **Acesso do Cloud Foundry**.
2. Selecione uma organização na qual incluir o usuário.
3. Selecione uma função de organização para definir o nível de acesso para a organização selecionada.
4. Opcional: selecione **Incluir função de organização** para especificar uma função extra.
5. Selecione **Todas as regiões atuais** ou uma região específica.
6. Selecione **Todos os espaços atuais** ou um espaço específico.
7. Selecione uma função de espaço para definir o nível de acesso para os espaços selecionados.
8. Opcional: selecione **Incluir função de espaço** para especificar uma função extra.

Veja [Funções do Cloud Foundry](/docs/iam/cfaccess.html#cfroles) para obter mais informações sobre as funções.

É possível incluir uma função do Cloud Foundry usando o comando da CLI [bluemix iam account-user-invite](/docs/cli/reference/bluemix_cli/bx_cli.html#bluemix_iam_account_user_invite), mas a UI deve ser usada para designar outro acesso ou permissões.
{: tip}

### Acesso à infraestrutura do {{site.data.keyword.BluSoftlayer_notm}}

As permissões designadas são limitadas automaticamente ao subconjunto de permissões que você tem. Para obter mais informações sobre os conjuntos de permissões, veja [Permissões de infraestrutura](/docs/iam/users_roles.html#infrapermissions).

1. Na tela **Convidar usuários**, expanda a seção **Acesso à infraestrutura**.
2. Selecione uma permissão configurada para definir o escopo de acesso.

O acesso aos dispositivos é concedido separadamente após o usuário ser incluído navegando para a opção **Infraestrutura** no console.
{: tip}

Para obter informações sobre como configurar o acesso para usuários depois de eles terem sido incluídos em sua conta, veja [Gerenciando o acesso à infraestrutura](/docs/iam/mnginfra.html#managing-infrastructure-access).

## Incluindo usuários somente VPN

Como proprietário da conta de uma conta vinculada, é possível incluir um usuário somente VPN.

1. Clique no ícone de Menu ![ícone de Menu](../icons/icon_hamburger.svg) e, em seguida, selecione **Infraestrutura**.
2. Acesse **Conta** &gt; **Usuários**.
3. Clique em **Incluir usuário somente VPN**.
4. Insira os detalhes de informações pessoais para o usuário. 
5. Clique em **Incluir usuário**.
6. Configure as permissões do portal para o usuário.
7. Clique em **Incluir permissões do portal** para salvar as permissões.
8. Configure o acesso ao dispositivo para o usuário.
9. Clique em **Atualizar acesso ao dispositivo** para salvar e designar o acesso.
