---

copyright:

  years: 2017, 2018

lastupdated: "2018-05-02"

---

{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:screen: .screen}
{:new_window: target="_blank"}
{:tip: .tip}


# Concedendo acesso entre os serviços
{: #serviceauth}

Muitos dos recursos do sistema do {{site.data.keyword.Bluemix_notm}} Identity and Access Management (IAM) são focados em gerenciar e cumprir o acesso aos recursos do {{site.data.keyword.Bluemix_notm}} pelos usuários e seus aplicativos. No entanto, há outros cenários em que você pode precisar fornecer um serviço com acesso ao recurso de um usuário em outro serviço. Todos os usuários em sua conta podem criar uma autorização, mas somente um usuário com a função `Administrator` pode excluir uma autorização. É possível configurar e visualizar autorizações dentro de sua conta na página **Autorizações**.

## Criar uma autorização

É possível conceder somente o nível de acesso que você tem como um usuário do serviço de destino. Por exemplo, se você tem somente acesso de visualizador no serviço que vai ser acessado, é possível designar somente a função de visualizador para a autorização.

1. Na barra de menus, clique em **Gerenciar** &gt; **Conta** &gt; **Identidade e acesso** e, em seguida, selecione **Autorizações**.
2. Clique em **Criar autorização**.
3. Selecione uma origem e um destino para a autorização. O serviço de origem recebe acesso para o serviço de destino selecionado.
4. Selecione uma função para designar acesso ao serviço de origem quando ele acessa o serviço de destino.
5. Clique em **Autorizar**.

**Nota**: somente os serviços que permitem que esse tipo de acesso seja concedido estão disponíveis como opções.

## Remover uma autorização

1. Na barra de menus, clique em **Gerenciar** &gt; **Conta** &gt; **Identidade e acesso** e, em seguida, selecione **Autorizações**.
2. Identifique a linha para a autorização que você deseja remover da conta.
3. No menu **Ações**, selecione **Remover autorização**.
5. Selecione **Remover**.
