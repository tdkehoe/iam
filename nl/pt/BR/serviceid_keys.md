---

copyright:

  years: 2015, 2018
lastupdated: "2018-06-01"

---

{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:screen: .screen}
{:new_window: target="_blank"}

# Gerenciando chaves API do ID de serviço
{: #serviceidapikeys}

Os IDs de serviço são criados para permitir acesso aos serviços do {{site.data.keyword.Bluemix_notm}} por aplicativos hospedados dentro e fora do {{site.data.keyword.Bluemix_notm}}. As chaves API são usadas por um aplicativo para autenticar como um ID de serviço específico e receber o acesso associado a esse ID de serviço.

Depois de criar um ID de serviço, será possível começar a criar as chaves API e designar políticas de serviço. Cada política especifica o nível de acesso permitido quando a chave API é usada para autenticação nos serviços. Para obter mais informações sobre como criar um ID de serviço e designar políticas, veja [Criando e gerenciando IDs de serviço](/docs/iam/serviceid.html#serviceids). Para obter detalhes sobre os comandos da CLI usados para gerenciar chaves API do ID de serviço, veja [Comandos para gerenciar chaves API e políticas](/docs/cli/reference/bluemix_cli/bx_cli.html#bx_commands_iam).

Cada chave API que estiver associada a um ID de serviço herdará a política que tiver sido designada ao ID de serviço. Por exemplo, se você quiser que um aplicativo seja capaz de simplesmente visualizar recursos em um serviço, então será necessário usar uma chave API associada a um ID de serviço que tenha uma política designada com a função `Viewer`. E se desejar que outro aplicativo possa ter acesso total em um serviço, então será necessário usar uma chave API associada a um segundo ID de serviço que tenha uma política designada com a função `Administrator`.

Para obter mais informações, consulte
[Exemplos de como usar um ID de serviço](/docs/iam/serviceid.html#examples-of-how-to-use-a-service-id).

## Criando uma chave API para um ID de serviço

Crie uma chave API para associar a um ID de serviço.

1. Acesse **Gerenciar** &gt; **Segurança** &gt; **Identidade e acesso** &gt; **IDs de serviço**.
2. Se você não tiver um ID de serviço já criado, crie o ID de serviço.
3. No menu **Ações**, acesse a opção **Gerenciar ID de serviço**.
4. Clique em **Criar** na seção de chaves API.
5. Inclua um nome e uma descrição para identificar facilmente a chave API.
6. Clique em **Criar**.
7. Salve sua chave API copiando ou fazendo download dela em um local seguro.

**Nota**: por razões de segurança, a chave API está disponível para ser copiada ou transferida por download somente no momento da criação. Se a chave API for perdida, uma nova chave API deverá ser criada.

## Atualizando uma chave API para um ID de serviço

É possível atualizar uma chave API editando o nome ou a descrição usada para identificar a chave na UI.

1. Acesse **Gerenciar** &gt; **Segurança** &gt; **Identidade e acesso** &gt; **IDs de serviço**.
2. Se você não tiver um ID de serviço já criado, crie o ID de serviço.
3. No menu **Ações**, acesse a opção **Gerenciar ID de serviço**.
4. No menu **Ações** na seção de chaves API, acesse a opção **Editar nome e descrição**.

## Bloqueando um ID da chave API de serviço
{: #lockkey}

Para chaves API que representam a identidade do ID do serviço, é possível evitar que a chave API seja excluída bloqueando-a. Uma chave API bloqueada é indicada pelo ícone ![Ícone Bloqueado](images/locked.svg "Bloqueado") na UI.

1. Na barra de menus, clique em **Gerenciar** &gt; **Segurança** &gt; **Identidade e acesso** e, em seguida, selecione **IDs de serviço**.
2. Identifique a linha do ID do serviço para o qual você deseja selecionar uma chave API e selecione o nome do ID do serviço.
3. Selecione **chaves API**.
4. Passe o mouse sobre a linha da chave API que você deseja bloquear e clique no menu **Ações** para abrir uma lista de opções.
5. Clique em **Bloquear API key**.

É possível desbloquear sua chave API a qualquer momento para atualizar, excluir ou incluir uma política de acesso ou para remover a chave API.
{: tip}

### Bloqueando ou desbloqueando uma chave API do ID do serviço com a CLI

Para bloquear uma chave API do ID do serviço, use o comando a seguir:

```
ibmcloud iam service-api-key-lock (APIKEY_NAME|APIKEY_UUID) (SERVICE_ID_NAME|SERVICE_ID_UUID) [-f, --force]
```

<strong>Pré-requisitos</strong>: Terminal, Login, Destino

<strong>Opções de comando</strong>:
<dl>
  <dt>APIKEY_NAME (necessário)</dt>
  <dd>Nome da chave API, exclusivo com APIKEY_UUID</dd>
  <dt>APIKEY_UUID (necessário)</dt>
  <dd>UUID da chave API, exclusivo com APIKEY_NAME</dd>
  <dt>SERVICE_ID_NAME (necessário)</dt>
  <dd>Nome do ID do serviço, exclusivo com SERVICE_ID_UUID</dd>
  <dt>SERVICE_ID_UUID (necessário)</dt>
  <dd>UUID do ID do serviço, exclusivo com SERVICE_ID_NAME</dd>
  <dt>-f, --force</dt>
  <dd>Bloquear sem confirmação</dd>
</dl>

<strong>Exemplos</strong>:

Bloquear a chave API de serviço `sample-key` do ID do serviço `sample-service`:

```
Ibmcloud iam service-api-key-bloqueio sample-key sample-service
```

Para desbloquear uma chave API do ID do serviço, use o comando a seguir:

```
ibmcloud iam service-api-key-unlock (APIKEY_NAME|APIKEY_UUID) (SERVICE_ID_NAME|SERVICE_ID_UUID) [-f, --force]
```


## Excluindo uma chave API de um ID de serviço

É possível excluir uma chave API associada a um ID de serviço. No entanto, a exclusão de uma chave API atualmente em uso por um aplicativo removerá a capacidade de autenticação desse aplicativo nos serviços.

1. Acesse **Gerenciar** &gt; **Segurança** &gt; **Identidade e acesso** &gt; **IDs de serviço**.
2. Se você não tiver um ID de serviço já criado, crie o ID de serviço.
3. No menu **Ações**, acesse a opção **Gerenciar ID de serviço**.
4. No menu **Ações** na seção de chaves API, acesse a opção **Excluir chave**.
