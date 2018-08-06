---

copyright:

  years: 2015, 2018
lastupdated: "2018-06-06"

---

{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:screen: .screen}
{:new_window: target="_blank"}

# Gerenciando chaves API do usuário
{: #userapikey}

Um usuário federado ou não federado pode criar uma chave API a ser usada na CLI ou como parte da automação para efetuar login como sua identidade do usuário. É possível usar a UI ou CLI para gerenciar suas chaves API, listando suas chaves, criando chaves, atualizando chaves ou excluindo chaves. Para gerenciar as chaves API do {{site.data.keyword.Bluemix_notm}} que estão associadas à sua identidade de usuário, acesse **Gerenciar** &gt; **Segurança** &gt; **Chaves API da plataforma** para ver uma lista de suas chaves API com descrições e datas. Em seguida, é possível criar, editar ou excluir chaves API. E, para obter uma lista completa de comandos da CLI disponíveis, veja [`ibmcloud iam api-keys`](/docs/cli/reference/bluemix_cli/bx_cli.html#ibmcloud_iam).

Como um [usuário federado](/docs/account/adminpublic.html#federatedid), é possível usar uma chave API para efetuar login usando a variável de ambiente `BLUEMIX_API_KEY`. Para obter mais informações sobre como usar uma chave API para efetuar login, veja [Efetuando login com um ID federado](/docs/cli/login_federated_id.html#federated_id).

## Criando uma chave API

Como um usuário do {{site.data.keyword.Bluemix_notm}}, você pode desejar usar uma chave API quando ativar um programa ou script sem distribuir sua senha para o script. É possível que um benefício de uso de uma chave API seja que um usuário ou uma organização possa criar várias chaves API para diferentes programas e que as chaves API poderão ser excluídas independentemente se comprometidas sem interferir com outras chaves API ou até mesmo com o usuário. É possível criar até 20 chaves API.

Para criar uma chave API para sua identidade do usuário na UI, conclua as etapas a seguir:

1. Acesse **Gerenciar** &gt; **Segurança** &gt; **Chaves API da plataforma**.
2. Clique em **Criar chave API**.
3. Insira um nome e uma descrição para sua chave API.
4. Clique em **Criar chave API**.
5. Em seguida, clique em **Mostrar** para exibir a chave API para copiá-la e salvá-la para mais tarde ou clique em **Fazer download da chave API**.

**Nota**: por razões de segurança, a chave API está disponível para ser copiada ou transferida por download somente no momento da criação. Se a chave API for perdida, uma nova chave API deverá ser criada.

Para criar uma chave API usando a CLI, use o comando a seguir:

1. Insira `ibmcloud iam api-key-create NAME [-d DESCRIPTION] [-f, --file FILE]` no prompt de comandos e especifique um nome, uma descrição e um arquivo para salvar sua chave. Consulte o exemplo a seguir:

```
ibmcloud iam api-key-create MyKey -d "this is my API key" --file key_file
``` 


## Atualizando uma chave API

Se desejar mudar o nome ou a descrição de uma chave API, conclua as etapas a seguir na UI ou na CLI.

Para editar uma chave API, conclua as etapas a seguir:

1. Acesse **Gerenciar** &gt; **Segurança** &gt; **Chaves API da plataforma**.
2. No menu **Ações** de uma chave API listada na tabela, clique em **Editar o nome e a descrição** 
3. Atualize as informações de sua chave API.
4. Clique em **Atualizar chave API**.

Para editar uma chave API usando a CLI, insira o comando a seguir:

1. Insira `ibmcloud iam api-key-update NAME [-n NAME] [-d DESCRIPTION]` no prompt de comandos, especificando o nome antigo, o novo nome e a nova descrição para a chave. Por exemplo:

```
ibmcloud iam api-key-update MyCurrentName -n MyNewName -d "the new description of my key"
```

## Bloqueando uma chave API

Para chaves API da plataforma que representam sua identidade do usuário, é possível evitar que a chave API seja excluída bloqueando-a. Uma chave API bloqueada é indicada pelo ícone ![Ícone Bloqueado](images/locked.svg "Bloqueado"). É possível bloquear e desbloquear sua chave API usando a UI ou CLI.

### Bloqueando e desbloqueando uma chave API da UI

1. Na barra de menus, clique em **Gerenciar** &gt; **Segurança** &gt; **Identidade e acesso** e, em seguida, selecione **Chaves API da plataforma**.
2. Identifique a linha da chave API que você deseja bloquear e selecione **Bloquear chave API** no menu **Ações**.

É possível desbloquear sua chave API a qualquer momento para atualizar, excluir ou incluir uma política de acesso ou remover a chave API de sua conta. Selecione a chave API da tabela que você deseja desbloquear e selecione **Desbloquear chave API** no **Menu Ações**.
{: tip}

### Bloqueando e desbloqueando uma chave API usando a CLI

Para bloquear uma chave API da plataforma, use o comando a seguir:

```
Ibmcloud iam api-key-bloqueio (NAME | UUID) [ -f, -- force ]
```

<strong>Pré-requisitos</strong>: Terminal, Login

<strong>Opções de comando</strong>:
<dl>
<dt>NAME (necessário)</dt>
<dd>Nome da chave API a ser bloqueada, exclusiva com UUID.</dd>
<dt>UUID (necessário)</dt>
<dd>UUID da chave API a ser bloqueada, exclusiva com NAME.</dd>
<dt>-f, --force</dt>
<dd>Força o bloqueio sem confirmação.</dd>
</dl>

<strong>Exemplo</strong>:

Bloquear chave API `test-api-key`

```
Ibmcloud iam api-key-bloqueio de teste api-key
```

Para desbloquear uma chave API da plataforma, execute o comando a seguir:

```
Ibmcloud iam api-key-desbloquear (NAME | UUID) [ -f, -- force ]
```

<strong>Pré-requisitos</strong>: Terminal, Login

<strong>Opções de comando</strong>:
<dl>
<dt>NAME (necessário)</dt>
<dd>Nome da chave API a ser desbloqueada, exclusiva com UUID.</dd>
<dt>UUID (necessário)</dt>
<dd>UUID da chave API a ser desbloqueada, exclusiva com NAME.</dd>
<dt>-f, --force</dt>
<dd>Forças desbloquear sem confirmação.</dd>
</dl>

<strong>Exemplo</strong>:

Desbloquear chave API `test-api-key`

```
Ibmcloud iam api-key-unlock-api-chave de teste
```


## Excluindo uma chave API

Se você está usando uma estratégia de rotação de chave, talvez queira excluir uma chave mais antiga e substituí-la por uma nova.

Para excluir uma chave API, conclua as etapas a seguir: 

1. Acesse **Gerenciar** &gt; **Segurança** &gt; **Chaves API da plataforma**.
2. No menu **Ações** de uma chave API listada na tabela, clique em **Excluir**.
3. Em seguida, confirme a exclusão clicando em **Excluir chave**.

Para excluir uma chave API usando a CLI:
1. Insira `ibmcloud iam api-key-delete NAME` no prompt de comandos, especificando o nome da chave a ser excluída.
