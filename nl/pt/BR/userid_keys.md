---

copyright:

  years: 2015, 2017 lastupdated: "2017-10-03"

---

{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:screen: .screen}
{:new_window: target="_blank"}

# Gerenciando chaves API do usuário
{: #userapikey}

Um usuário federado ou não federado pode criar uma chave API a ser usada na CLI ou como parte da automação para efetuar login como sua identidade do usuário. É possível usar a UI do {{site.data.keyword.Bluemix_notm}} ou a CLI do {{site.data.keyword.Bluemix_notm}} para gerenciar suas chaves API listando suas chaves, criando chaves, atualizando chaves ou excluindo chaves. Para gerenciar as chaves API do {{site.data.keyword.Bluemix_notm}} associadas à sua identidade de usuário, acesse **Gerenciar** &gt; **Segurança** &gt; **Chaves API do Bluemix** para ver uma lista de suas chaves API com descrições e datas. Em seguida, é possível criar, editar ou excluir chaves API desta página. Para obter uma lista completa de comandos da CLI disponíveis, veja [Comandos para gerenciar chaves API e políticas](/docs/cli/reference/bluemix_cli/bx_cli.html#bx_commands_iam).

Como um [usuário federado](/docs/admin/adminpublic.html#federatedid), é possível usar uma chave API para efetuar login usando a variável de ambiente `BLUEMIX_API_KEY`. Para obter mais informações sobre como usar uma chave API para efetuar login, veja a documentação do [comando `bluemix login` da CLI do {{site.data.keyword.Bluemix_notm}}](/docs/cli/reference/bluemix_cli/bx_cli.html#bluemix_login) e o [comando `cf login` da CLI cf](/docs/cli/reference/cfcommands/index.html#cf_login).

## Criando uma chave API

Como um usuário do {{site.data.keyword.Bluemix_notm}}, talvez você queira usar uma chave API quando ativar um programa ou um script sem distribuir sua senha para o script. É possível que um benefício de uso de uma chave API seja que um usuário ou uma organização possa criar várias chaves API para diferentes programas e que as chaves API poderão ser excluídas independentemente se comprometidas sem interferir com outras chaves API ou até mesmo com o usuário.

Para criar uma chave API para sua identidade de usuário na UI:

1. Acesse **Gerenciar** &gt; **Segurança** &gt; **Chaves API do Bluemix**.
2. Clique em **Criar chave API**.
3. Insira um nome e uma descrição para sua chave API.
4. Clique em **Criar chave API**.
5. Em seguida, clique em **Mostrar** para exibir a chave API para copiá-la e salvá-la para mais tarde ou clique em **Fazer download da chave API**.

**Nota**: por razões de segurança, a chave API está disponível para ser copiada ou transferida por download somente no momento da criação. Se a chave API for perdida, uma nova chave API deverá ser criada.

Para criar uma chave API usando a CLI:

1. Insira `bluemix iam api-key-create NAME [-d DESCRIPTION] [-f, --file FILE]` no prompt de comandos e especifique um nome, uma descrição e um arquivo para salvar sua chave. Por
exemplo:

```
bluemix iam api-key-create MyKey -d "this is my API key" -f key_file
``` 

Depois que uma chave API é criada usando a CLI, há algumas maneiras de poder usar a chave com o bx CLI:

* Insira-a com o comando `bx login`
```
 bx login --apikey <your api key>
```
* Crie um arquivo de chave API para usar com o comando `bx login`: 
 ```
 bx login --apkey @apikeyfile
 ```
 O `apikeyfile` é criado usando a opção `—file` no comando `bx iam api-key-create`.
* No prompt de comandos, é possível configurar a variável de ambiente inserindo `BLUEMIX_API_KEY=<your api key>` e, em seguida, inserindo `bx login`.
* Ou, se desejar evitar o bx CLI e apenas efetuar login no cf CLI usando a chave API, insira:
 ```
 cf login -u apikey -p <yourapikey>
 ```
  Nessa opção, você usa o nome de usuário de `apikey` e a senha é seu `apikey`. Agora, é possível usar `apikey` em outras ferramentas, como Eclipse, ou outros locais, procurando `cf login`, que aceita apenas o nome do usuário e a senha.

## Atualizando uma chave API

Se desejar mudar o nome ou a descrição de uma chave API, conclua as etapas a seguir na UI ou na CLI.

Para editar uma chave API:

1. Acesse **Gerenciar** &gt; **Segurança** &gt; **Chaves API do Bluemix**.
2. No menu **Ações** de uma chave API listada na tabela, clique em **Editar o nome e a descrição** 
3. Atualize as informações de sua chave API.
4. Clique em **Atualizar chave API**.

Para editar uma chave API usando a CLI:

1. Insira `bluemix iam api-key-update NAME [-n NAME] [-d DESCRIPTION]` no prompt de comandos, especificando o nome antigo, o novo nome e a nova descrição para a chave. Por
exemplo:

```
bluemix iam api-key-update MyCurrentName -n MyNewName -d "the new description of my key"
```

## Excluindo uma chave API

Se você está usando uma estratégia de rotação de chave, talvez queira excluir uma chave mais antiga e substituí-la por uma nova.

Para excluir uma chave API: 

1. Acesse **Gerenciar** &gt; **Segurança** &gt; **Chaves API do Bluemix**.
2. No menu **Ações** de uma chave API listada na tabela, clique em **Excluir**.
3. Em seguida, confirme a exclusão clicando em **Excluir chave**.

Para excluir uma chave API usando a CLI:
1. Insira `bluemix iam api-key-delete NAME` no prompt de comandos, especificando o nome da chave que deve ser excluída.
