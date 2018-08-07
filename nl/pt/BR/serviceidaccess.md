---

copyright:

  years: 2015, 2018
lastupdated: "2018-08-02"

---

{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:screen: .screen}
{:new_window: target="_blank"}

# Gerenciando políticas de acesso do ID de serviço
{: #serviceidpolicy}

Ao criar um ID de serviço, é possível designar políticas de serviço para esse ID de serviço para controlar o nível de acesso permitido quando ele é usado para autenticação nos serviços. É possível atualizar essas políticas de acesso designadas a qualquer momento mudando uma política existente, excluindo uma política ou designando uma nova.

**Nota**: se você exclui ou edita uma política existente para um ID de serviço atualmente em uso, isso pode causar interrupção do serviço.

## Designando novo acesso

Para designar acesso a todos os recursos em um grupo de recursos ou a apenas um serviço em um grupo de recursos, conclua as etapas a seguir:

1. Na barra de menus, clique em **Gerenciar** &gt; **Segurança** &gt; **Identidade e acesso** &gt; **IDs de serviço**.
2. Selecione o ID de serviço na tabela para a qual você deseja designar uma política de serviço.
3. Clique em **Designar acesso**.
4. Selecione **Designar por grupo de recursos**.
5. Selecione um grupo de recursos.
6. Escolha uma função para o campo **Designar acesso ao grupo de recursos**. Essa opção permite que o usuário visualize o grupo de recursos em seu painel, edite o nome do grupo de recursos ou gerencie o acesso de usuário ao grupo. É possível selecionar **Sem acesso** se você deseja que o usuário tenha acesso somente ao recurso especificado e não ao grupo ao qual ele está designado.
7. Selecione um serviço no grupo de recursos ou opte por fornecer acesso a todos os serviços no grupo selecionado.
8. Escolha qualquer combinação de funções para designar o acesso desejado ao usuário. Este acesso só se aplica aos recursos que você selecionou para a política. Ela não fornece acesso ao contêiner real que é o grupo de recursos.
9. Selecione **Designar**.

Para designar acesso a um recurso individual na conta, conclua as etapas a seguir:

1. Na barra de menus, clique em **Gerenciar** &gt; **Segurança** &gt; **Identidade e acesso** &gt; **IDs de serviço**.
2. Selecione o ID de serviço na tabela para a qual você deseja designar uma política de serviço.
3. Clique em **Designar acesso**.
4. Selecione **Designar por recurso**.
5. Selecione um serviço.
6. Selecione **Todas as regiões atuais** ou uma região específica, se solicitado.
7. Selecione **Todas as instâncias de serviço atuais** ou selecione uma instância de serviço específica.
8. Dependendo do serviço que você selecionou, será possível ver os campos a seguir. Se você não digitar valores para esses campos, a política será designada no nível da instância de serviço em vez do nível de depósito.
    * **Tipo de recurso**: insira **depósito**.
    * **ID do recurso**: Insira o nome do bucket.
9. Escolha qualquer combinação de funções para designar o acesso desejado ao usuário.
10. Selecione **Designar**.



## Editando acesso existente

Para editar uma política existente:

1. Na barra de menus, clique em **Gerenciar** &gt; **Segurança** &gt; **Identidade e acesso** &gt; **IDs de serviço**.
2. Selecione o ID de serviço na tabela para a qual você deseja editar uma política de serviço.
3. Identifique a linha da política que você deseja editar e selecione **Editar política** no menu **Ações**.
4. Faça suas mudanças e, em seguida, salve a política.

Para atualizar uma política de serviço usando a CLI, é possível usar o comando [ibmcloud iam service-policy-update](/docs/cli/reference/ibmcloud/cli_api_policy.html#ibmcloud_iam_service_policy_update).
```
ibmcloud iam service-policy-update SERVICE_ID POLICY_ID [-v, --version VERSION] {--file JSON_FILE | [-r, --roles ROLE_NAME1,ROLE_NAME2...] [--service-name SERVICE_NAME] [--service-instance SERVICE_INSTANCE] [--region REGION] [--resource-type RESOURCE_TYPE] [--resource RESOURCE] [--resource-group-name RESOURCE_GROUP_NAME] [--resource-group-id RESOURCE_GROUP_ID]} [-f, --force]",
```
{: codeblock}

## Removendo o acesso

Para remover uma política existente:

1. Na barra de menus, clique em **Gerenciar** &gt; **Segurança** &gt; **Identidade e acesso** &gt; **IDs de serviço**.
2. Selecione o ID de serviço na tabela da qual você deseja excluir uma política de serviço.
3. Identifique a linha da política que você deseja excluir e selecione **Remover** no menu **Ações**.
4. Revise os detalhes da política que você está prestes a remover e, em seguida, clique em **Remover** para confirmar.

Para excluir uma política de serviço usando a CLI, é possível usar o comando [ibmcloud iam service-policy-delete](/docs/cli/reference/ibmcloud/cli_api_policy.html#ibmcloud_iam_service_policy_delete).
```
ibmcloud iam service-policy-delete SERVICE_ID POLICY_ID [-f, --force]
```
{: codeblock}
