---

copyright:

  years: 2015, 2018
lastupdated: "2018-05-02"

---

{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:screen: .screen}
{:new_window: target="_blank"}

# Designando Acesso do Usuário
{: #assignaccess}

Você designa acesso para os usuários à medida que os convida, designando funções, políticas e permissões de infraestrutura do Cloud Foundry. Dependendo das opções de acesso que você estiver autorizado a gerenciar, será possível convidar e fornecer acesso para usuários na conta, na organização, no espaço e nas instâncias de serviço. As seções a seguir descrevem os três tipos de acesso que podem ser designados a um usuário convidado.
{:shortdesc}

## Serviços ativados para identidade e acesso

É possível designar uma única política de serviço ao convidar um novo usuário. Quando o usuário aceita o convite, é possível incluir políticas de serviço adicionais.

1. Na tela **Convidar usuários**, expanda a seção **Serviços ativados para identidade e acesso**.
2. Selecione um serviço.
3. Selecione **Todas as regiões atuais** ou uma região específica.
4. Selecione **Todas as instâncias de serviço atuais** ou selecione uma instância de serviço específica.
5. Selecione uma função para definir o escopo de acesso da política.
6. Opcionalmente, é possível selecionar **Incluir função** para especificar outra função para a política.

Para obter mais informações sobre as funções ao configurar políticas de serviço, veja [Políticas e funções de gerenciamento de identidade e acesso](/docs/iam/users_roles.html#iamusermanpol).

## Acesso ao Cloud Foundry

Ao convidar novos usuários, é possível escolher incluir o usuário em uma organização na conta. Se você incluir o usuário em uma organização, será possível designar uma função de organização ao usuário. Em seguida, você optará por fornecer ao usuário convidado acesso a qualquer um ou a todos os espaços na organização selecionada com uma função de espaço designada.

1. Na tela **Convidar usuários**, expanda a seção **Acesso do Cloud Foundry**.
2. Selecione uma organização na qual incluir o usuário.
3. Selecione uma função de organização para definir o nível de acesso à organização selecionada.
4. Opcional: selecione **Incluir função** para especificar uma função adicional.
5. Selecione **Todas as regiões atuais** ou uma região específica.
6. Selecione **Todos os espaços atuais** ou um espaço específico.
7. Selecione uma função de espaço para definir o nível de acesso aos espaços selecionados.
8. Opcionalmente, é possível selecionar **Incluir função** para especificar outra função para a política.

Para obter mais informações sobre essas funções, veja [Funções do Cloud Foundry](/docs/iam/users_roles.html#cfroles).

**Nota**: é possível incluir uma função do Cloud Foundry usando o comando da CLI [bluemix iam account-user-invite](/docs/cli/reference/bluemix_cli/bx_cli.html#bluemix_iam_account_user_invite), mas a UI deve ser usada para designar outro acesso ou permissões.

## Acesso ao Infrastructure

As permissões reais designadas são limitadas automaticamente ao subconjunto de permissões que você tem. Para obter mais informações sobre as permissões e quais ações o usuário pode concluir com cada uma, veja [Permissões de infraestrutura](/docs/iam/users_roles.html#infrapermissions).

1. Na tela **Convidar usuários**, expanda a seção **Acesso à infraestrutura**.
2. Selecione uma permissão para definir o escopo de acesso.

Para obter informações sobre como configurar o acesso para usuários depois de eles serem incluídos em sua conta, veja [Gerenciando usuários e acesso](/docs/iam/iamusermanage.html).
