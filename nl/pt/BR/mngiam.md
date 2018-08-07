---

copyright:

  years: 2017, 2018

lastupdated: "2018-08-02"

---

{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:screen: .screen}
{:new_window: target="_blank"}
{:tip: .tip}

# Gerenciando acesso ao IAM
{: #iammanidaccser}

Para gerenciar o acesso ou designar um novo acesso para usuários, deve-se ser o proprietário da conta, o administrador em todos os serviços na conta ou o administrador designado para o serviço específico ou instância de serviço. Para obter mais informações sobre funções e políticas de acesso, veja [Acesso ao IAM](/docs/iam/users_roles.html).

## Editando acesso existente

1. Na barra de menus, clique em **Gerenciar** &gt; **Segurança** &gt; **Identidade e acesso** e, em seguida, selecione **Usuários**.
2. Selecione o nome do usuário para o qual você deseja designar acesso.
3. Na linha da política que você deseja editar, selecione o menu **Ações** e, em seguida, clique em **Editar política**.
4. Edite a política.
5. Clique em **Salvar**.

Para atualizar uma política de usuário usando a CLI, é possível usar o comando [ibmcloud iam user-policy-update](/docs/cli/reference/ibmcloud/cli_api_policy.html#ibmcloud_iam_user_policy_update).
```
ibmcloud iam user-policy-update USER_NAME POLICY_ID [-v, --version VERSION] {-f, --file JSON_FILE | [--roles ROLE_NAME1,ROLE_NAME2...] [--service-name SERVICE_NAME] [--service-instance SERVICE_INSTANCE] [--region REGION] [--resource-type RESOURCE_TYPE] [--resource RESOURCE] [--resource-group-name RESOURCE_GROUP_NAME] [--resource-group-id RESOURCE_GROUP_ID]}
```
{: codeblock}

## Designando novo acesso
{: #assignaccess}

Para permitir a um usuário o acesso a todos os recursos com a capacidade de gerenciar o acesso de usuário, criar grupos de recursos e concluir todas as outras tarefas de gerenciamento do IAM, selecione a opção **Todos os serviços ativados pelo Identity and Access** para essa política com a função **Administrador** designada.
{: tip}

### Acesso aos recursos dentro de um grupo de recursos 

Para designar acesso a todos os recursos em um grupo de recursos ou a apenas um serviço em um grupo de recursos, conclua as etapas a seguir:

1. Na barra de menus, clique em **Gerenciar** &gt; **Segurança** &gt; **Identidade e acesso** e, em seguida, selecione **Usuários**.
2. Na linha para o usuário que você deseja designar acesso, selecione o menu **Ações** e, em seguida, clique em **Designar acesso**.
3. Selecione **Designar acesso dentro de um grupo de recursos**.
4. Selecione um grupo de recursos.
5. Escolha uma função para o campo **Designar acesso a um grupo de recursos** para permitir que o usuário visualize o grupo de recursos em seu painel, edite o nome do grupo de recursos ou gerencie o acesso de usuário ao grupo. É possível selecionar **Sem acesso**, se você deseja que o usuário tenha acesso somente ao recurso especificado e não ao grupo em que ele está organizado.
6. Selecione um serviço no grupo de recursos ou opte por fornecer acesso a todos os serviços no grupo selecionado.
7. Escolha qualquer combinação de funções para designar o acesso desejado ao usuário. Este acesso só se aplica aos recursos que você selecionou para a política. Ela não fornece acesso ao contêiner real que é o grupo de recursos.
8. Clique em **Designar**.

### Acesso a recursos
{: #resourceaccess}

Para designar acesso a um recurso individual na conta ou acesso a todos os recursos na conta, conclua as etapas a seguir: 

1. Na barra de menus, clique em **Gerenciar** &gt; **Segurança** &gt; **Identidade e acesso** e, em seguida, selecione **Usuários**.
2. Na linha para o usuário que você deseja designar acesso, selecione o menu **Ações** e, em seguida, clique em **Designar acesso**.
3. Selecione **Designar acesso a recursos**.
4. Selecione um serviço ou selecione **Todos os serviços ativados pelo Identity and Access**.
5. Selecione **Todas as regiões atuais** ou uma região específica, se solicitado. 
6. Selecione **Todas as instâncias de serviço atuais** ou selecione uma instância de serviço específica.
7. Dependendo do serviço que você selecionou, será possível ver os campos a seguir. Se você não digitar valores para esses campos, a política será designada no nível da instância de serviço em vez do nível de depósito. 
    * **Tipo de recurso**: insira **depósito**.
    * **ID do recurso**: Insira o nome do bucket.
8. Escolha qualquer combinação de funções para designar o acesso desejado ao usuário.
9. Clique em **Designar**.


## Removendo o acesso

1. Na barra de menus, clique em **Gerenciar** &gt; **Segurança** &gt; **Identidade e acesso** e, em seguida, selecione **Usuários**.
2. Selecione o nome do usuário para o qual você deseja remover o acesso.
3. Na linha para a política que você deseja remover, selecione o menu **Ações** e, em seguida, clique em **Remover**.
4. Revise os detalhes de política do usuário que você está prestes a remover e, em seguida, confirme clicando em **Remover**.

Para remover uma política de usuário usando a CLI, é possível usar o comando [ibmcloud iam user-policy-delete](/docs/cli/reference/ibmcloud/cli_api_policy.html#ibmcloud_iam_user_policy_delete).
```
ibmcloud iam user-policy-delete USER_ID POLICY_ID [-f, --force]
```
{: codeblock}

## Revisando seu acesso designado

Se for necessário revisar seu acesso designado em uma conta à qual tenha sido incluído, conclua as etapas a seguir:

1. Na barra de menus, clique em **Gerenciar** &gt; **Segurança** &gt; **Identidade e acesso** e, em seguida, selecione **Usuários**.
2. Selecione seu nome.
3. Revise seu acesso designado na seção **Políticas de acesso**.

Se você precisa de mais acesso, deve-se entrar em contato com o proprietário da conta para atualizar seu acesso ou entrar em contato com o administrador para o serviço ou instância de serviço para atualizar a política de acesso do Cloud IAM.
