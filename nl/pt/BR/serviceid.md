---

copyright:

  years: 2017, 2018
  
lastupdated: "2018-06-01"

---

{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:screen: .screen}
{:new_window: target="_blank"}
{:tip: .tip}

# Criando e trabalhando com IDs de serviço
{: #serviceids}

Um ID de serviço identifica um serviço ou um aplicativo semelhante a como um ID de usuário identifica um usuário. Um ID de serviço criado pode ser usado para ativar um aplicativo fora do acesso do {{site.data.keyword.Bluemix_notm}} aos serviços do {{site.data.keyword.Bluemix_notm}}. É possível designar políticas de acesso específicas ao ID de serviço que restringem permissões para usar serviços específicos ou até mesmo combinar permissões para acessar serviços diferentes. Como os IDs de serviço não são ligados a um usuário específico, se acontecer de um usuário deixar uma organização e for excluído da conta, o ID de serviço continuará assegurando que seu aplicativo ou serviço permaneça funcionando.

Ao criar um ID de serviço, você cria um nome exclusivo e uma descrição de fácil identificação e trabalho na UI. Depois de ter criado seu ID de serviço, será possível criar chaves API específicas para cada ID de serviço que o aplicativo poderá usar para autenticação nos serviços do {{site.data.keyword.Bluemix_notm}}. Para assegurar que seu aplicativo tenha o acesso apropriado para autenticação com os serviços do {{site.data.keyword.Bluemix_notm}}, você usa políticas de acesso designadas a cada ID de serviço criado. 

As políticas de acesso que estão associadas a um ID de serviço permitem ações específicas que podem ser tomadas quando o ID do serviço é usado para acessar um serviço específico. Um único ID de serviço pode ser designado a múltiplas políticas que definem o nível de acesso que é permitido ao acessar múltiplos serviços ativados por identidade e acesso. Por exemplo, você tem dois serviços com duas instâncias de serviço cada um. Por exemplo, é possível designar a função `Viewer` a todas as instâncias disponíveis de um serviço e designar a função `Editor` a apenas uma instância de um segundo serviço. Dessa forma, é possível customizar o acesso a múltiplos serviços, mas usar uma única chave API para autenticação em todos.


## Criando um ID de serviço

Para criar um ID de serviço, acesse **Gerenciar** &gt; **Segurança** &gt; **Identidade e acesso** e, em seguida, selecione **IDs de serviço**. Siga o processo para criar um nome e uma descrição para seu ID de serviço. Em seguida, use o menu **Ações** para gerenciar seu ID de serviço. É possível iniciar designando uma política e criando chaves API. Para obter mais informações sobre como trabalhar com chaves API, veja [Gerenciando chaves API do ID de serviço](/docs/iam/serviceid_keys.html#serviceidapikeys). 

## Atualizando um ID de serviço

É possível atualizar um ID de serviço mudando o nome e a descrição a qualquer momento. Também é possível excluir e criar novas chaves API, conforme necessário, ou atualizar as políticas de acesso designadas. No entanto, quaisquer mudanças feitas em um ID de serviço existente, como mudar as políticas designadas ou excluir uma chave API que está atualmente sendo usada, podem causar interrupções de serviço em aplicativos que usam esse ID de serviço.

## Bloqueando um ID de serviço

Para evitar uma situação em que seu ID de serviço é excluído causando uma indisponibilidade ou interrupção para os usuários de seu serviço, você tem a opção de bloquear seu ID de serviço usando a UI ou a CLI. Bloquear um ID de serviço também evita que quaisquer
políticas de acesso sejam mudadas, excluídas ou designadas, bem como quaisquer chaves API associadas com o ID de serviço de
ser criado ou excluído. Além da capacidade de bloquear um ID de serviço, é possível [bloquear as chaves API individuais](/docs/iam/serviceid_keys.html#lockkey) que estão associadas a cada ID de serviço em sua conta. 

Os IDs de serviço bloqueados não podem ser excluídos e as políticas de acesso não podem ser atualizadas. No entanto, os IDs de serviço bloqueados ainda podem ser removidos de qualquer grupo de acesso no qual eles tenham sido incluídos. Isso significa que qualquer acesso designado ao ID de sua associação em um grupo de acesso é removido quando o ID do serviço é removido do grupo de acesso.
{: tip}

### Fornecendo acesso de usuário para bloquear IDs de serviço

Para que um usuário tenha acesso para bloquear e desbloquear IDs de serviço e chaves API que estão associadas a IDs de serviço, eles devem ser designados a uma política de acesso específica. Dois tipos de políticas de acesso podem conceder o acesso adequado:

* Acesso a todos os IDs de serviço na conta
* Acesso a um ID de serviço específico na conta

Para designar acesso a todos os IDs de serviço na conta, configure uma política de acesso com os detalhes a seguir:

* Função Editor ou Administrador 
* Serviço de identidade do IAM

Para designar acesso a um ID de serviço específico na conta, configure uma política de acesso com os detalhes a seguir:

* Função Editor ou Administrador
* Serviço de identidade do IAM
* Especifique `serviceid` no campo **Tipo de recurso** 
* Especifique o identificador de ID do serviço no campo **ID do recurso**

Para obter o identificador de um ID de serviço específico, acesse **Gerenciar** > **Segurança** > **Identidade e acesso**, em seguida, selecione **IDs de serviço**. Selecione o ID do serviço para o qual você deseja visualizar detalhes e copie o valor do ID.
{: tip}

### Bloqueando um ID de serviço da UI

Um ID de serviço bloqueado é indicado pelo ícone ![Ícone Bloqueado](images/locked.svg "Bloqueado").

1. Na barra de menus, clique em **Gerenciar** &gt; **Segurança** &gt; **Identidade e acesso** e, em seguida, selecione **IDs de serviço**.
2. Identifique a linha do ID de serviço que você deseja bloquear e selecione **Bloquear ID do serviço** no menu **Ações**.

Para desbloquear um ID de serviço, selecione o ID de serviço na tabela que você deseja desbloquear e selecione **Desbloquear ID do serviço** no menu **Ações**. Deve-se ter o nível apropriado de acesso para desbloquear um ID de serviço.
{: tip}

### Bloqueando e desbloqueando um ID de serviço usando a CLI

Para bloquear um ID de serviço, use o comando a seguir:

```
Ibmcloud iam service-id-bloqueio (NAME | UUID) [ -f, -- force ]
```

Opções de comando:

<dl>
  <dt>NAME (necessário)</dt>
  <dd>Nome do serviço, exclusivo com UUID</dd>
  <dt>UUID (necessário)</dt>
  <dd>UUID do serviço, exclusivo com NAME</dd>
  <dt>-f, --force</dt>
  <dd>Bloquear sem confirmação</dd>
</dl>

<strong>Exemplos</strong>:

Bloquear ID de serviço `sample-teste` sem confirmação

```
Ibmcloud iam service-id-bloqueio sample-teste -f
```

Bloquear ID do serviço `ServiceId-cb258cb9-8de3-4ac0-9aec-b2b2d27ac976`

```
Ibmcloud iam service-id-de bloqueio ServiceId-cb258cb9-8de3-4ac0-9aec-b2b2d27ac976
```

Para desbloquear um ID de serviço, use o comando a seguir:

 ```
ibmcloud iam service-id-unlock (NAME|UUID) [-f, --force]
```

Opções de comando:
<dl>
  <dt>NAME (necessário)</dt>
  <dd>Nome do serviço, exclusivo com UUID</dd>
  <dt>UUID (necessário)</dt>
  <dd>UUID do serviço, exclusivo com NAME</dd>
  <dt>-f, --force</dt>
  <dd>Desbloquear sem confirmação</dd>
</dl>

<strong>Exemplos</strong>:

Desbloquear ID do serviço ` sample-test sem confirmação

```
Ibmcloud iam service-id-sample-teste -f desbloqueio
```

Desbloquear ID do serviço ` ServiceId-cb258cb9-8de3-4ac0-9aec-b2b2d27ac976 `

```
Ibmcloud iam service-id-desbloquear ServiceId-cb258cb9-8de3-4ac0-9aec-b2b2d27ac976
```



## Exemplos de como usar um ID de serviço

A seguir estão exemplos de como um ID de Serviço é usado com o {{site.data.keyword.objectstorageshort}} e serviços do SQL Query do Cloud.

- {{site.data.keyword.objectstorageshort}} - [Introdução](/docs/services/cloud-object-storage/getting-started-cli.html#getting-started-cli-).
- Consulta SQL de nuvem - [Como usar a API de REST da consulta SQL![Ícone de link externo](../icons/launch-glyph.svg)](https://www.youtube.com/embed/s6S4AdJItHk?rel=0){: new_window}.

