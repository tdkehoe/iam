---

copyright:

  years: 2015, 2017
lastupdated: "2017-09-29"

---

{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:screen: .screen}
{:new_window: target="_blank"}

# Convidando usuários e designando acesso
{: #iamuserinv}

É possível convidar usuários em serviços do {{site.data.keyword.Bluemix_notm}},
aplicativos e infraestrutura do {{site.data.keyword.Bluemix_notm}} em um único local. Para convidar usuários e gerenciar convites pendentes, deve-se ser um proprietário da conta, um
gerenciador de organização ou ter permissões de infraestrutura para incluir usuários. É possível convidar
usuários, cancelar convites e reenviar um convite pendente para um usuário convidado. É possível convidar um
único usuário ou, se fornece o mesmo acesso para todos os membros em um grupo de usuários,
é possível convidar múltiplos usuários de uma vez.  
{:shortdesc}

## Convidando usuários

Para convidar usuários ou gerenciar convites de usuários em sua conta, conclua as etapas a seguir: 

1. Na barra de menus, clique em **Gerenciar** &gt; **Segurança** &gt; **Identidade e acesso** &gt; **Usuários**. A janela Usuários exibe uma lista de usuários com seus endereços de e-mail e o status atual na conta selecionada atualmente.
2. Clique em **Convidar usuários**.
3. Especifique o endereço de e-mail ou o IBMid do usuário. Se você estiver fornecendo a múltiplos usuários o mesmo acesso, insira múltiplos endereços de e-mail ou IBMids, separando as entradas de ID de usuário com vírgulas, espaços ou quebras de linha.
4. Inclua uma ou mais das opções de acesso que você gerencia. Deve-se
designar pelo menos uma opção de acesso e definir as configurações para o usuário em cada opção de acesso que
você designar. Para quaisquer opções de acesso adicionais que você não incluir nem configurar, o valor padrão de
*no access* é designado. Será possível ver uma ou todas as opções de acesso a seguir, dependendo das opções que você estiver autorizado a gerenciar: **Serviços ativados para identidade e acesso**, **Acesso ao Cloud Foundry**, **Acesso à infraestrutura**. Veja [Designando acesso de usuário](/docs/iam/iamuserinv.html#assignaccess) para obter mais informações.

Se você determinar que um usuário não precisa de acesso, será possível cancelar um convite de quaisquer usuários que forem mostrados em um estado **Processando** ou **Pendente** na coluna **Status**. Se um usuário convidado não tiver recebido um convite, será possível reenviar o convite para qualquer usuário em um estado **Pendente**.

Se você deseja convidar usuários usando a CLI, veja o comando [bluemix iam account-user-invite](/docs/cli/reference/bluemix_cli/bx_cli.html#bluemix_iam_account_user_invite).

## Designando Acesso do Usuário
{: #assignaccess}

Você designa acesso para os usuários à medida que os convida, designando funções, políticas e permissões de infraestrutura do Cloud Foundry. Dependendo das opções de acesso que você estiver autorizado a gerenciar, será possível convidar e fornecer acesso para usuários na conta, na organização, no espaço e nas instâncias de serviço. As seções a seguir descrevem os três tipos de acesso que podem ser designados a um usuário convidado.

### Serviços ativados para identidade e acesso

É possível designar uma única política de serviço ao convidar um novo usuário. Quando o usuário aceitar o convite, será possível incluir políticas de serviço adicionais. Veja [Políticas de acesso de serviço ativadas por Identidade e por acesso](/docs/iam/iamusermanage.html#iammanidaccser) para obter detalhes sobre como editar políticas para incluir funções adicionais, como incluir políticas de serviço adicionais ou como remover uma política de um usuário.

**Nota**: dependendo do serviço selecionado ao designar a política, é possível que você não veja todos os campos descritos no procedimento a seguir.

1. Na tela **Convidar usuários**, expanda a seção **Serviços ativados para identidade e acesso**.
2. Selecione um serviço.
3. Selecione **Todas as regiões atuais** ou uma região específica, se solicitado. 
**Nota**: nem todos os serviços requerem uma seleção de região.
4. Selecione **Todas as instâncias de serviço atuais** ou selecione uma instância de serviço específica.
5. Selecione uma função para definir o escopo de acesso da política.
6. Opcional: selecione **Incluir função** para especificar uma função adicional para a política.

Veja [Políticas e funções de gerenciamento de acesso e identidade](/docs/iam/users_roles.html#iamusermanpol) para obter informações mais específicas sobre as funções ao configurar as políticas de serviço.

### Acesso ao Cloud Foundry

Ao convidar novos usuários, é possível escolher incluir o usuário em uma organização na conta. Se você incluir o usuário em uma organização, será possível designar uma função de organização ao usuário. Em seguida, você optará por fornecer ao usuário convidado acesso a qualquer um ou a todos os espaços na organização selecionada com uma função de espaço designada.

1. Na tela **Convidar usuários**, expanda a seção **Acesso do Cloud Foundry**.
2. Selecione uma organização na qual incluir o usuário.
3. Selecione uma função de organização para definir o nível de acesso à organização selecionada.
4. Opcional: selecione **Incluir função** para especificar uma função adicional.
5. Selecione **Todas as regiões atuais** ou uma região específica.
6. Selecione **Todos os espaços atuais** ou um espaço específico.
7. Selecione uma função de espaço para definir o nível de acesso aos espaços selecionados.
8. Opcional: selecione **Incluir função** para especificar uma função adicional.

Veja [Funções do Cloud Foundry](/docs/iam/users_roles.html#cfroles) para obter informações mais específicas sobre essas funções.

**Nota**: é possível incluir uma função do Cloud Foundry usando o comando da CLI [bluemix iam account-user-invite](/docs/cli/reference/bluemix_cli/bx_cli.html#bluemix_iam_account_user_invite), mas a UI deve ser usada para designar outro acesso ou permissões.

### Acesso ao Infrastructure

As permissões reais designadas são limitadas automaticamente ao subconjunto de permissões que você tem. Para obter mais informações sobre as permissões e quais ações o usuário pode executar com cada uma, veja [Permissões de infraestrutura](/docs/iam/users_roles.html#infrapermissions).

1. Na tela **Convidar usuários**, expanda a seção **Acesso à infraestrutura**.
2. Selecione uma permissão para definir o escopo de acesso.

Para obter informações sobre como configurar o acesso para os usuários depois que eles tiverem sido incluídos em sua conta, veja [Gerenciando usuários e acesso](/docs/iam/iamusermanage.html).
