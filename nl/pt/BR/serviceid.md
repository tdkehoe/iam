---

copyright:

  anos: 2017 última atualização: "16-11-2017"

---

{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:screen: .screen}
{:new_window: target="_blank"}

# Criando e gerenciando IDs de serviço
{: #serviceids}

Um ID de serviço identifica um serviço ou um aplicativo semelhante a como um ID de usuário identifica um usuário. Um ID de serviço criado pode ser usado para ativar um aplicativo fora do acesso do {{site.data.keyword.Bluemix_notm}} aos serviços do {{site.data.keyword.Bluemix_notm}}. É possível designar políticas de acesso específicas ao ID de serviço que restringem permissões para usar serviços específicos ou até mesmo combinar permissões para acessar serviços diferentes. Como os IDs de serviço não são ligados a um usuário específico, se acontecer de um usuário deixar uma organização e for excluído da conta, o ID de serviço continuará assegurando que seu aplicativo ou serviço permaneça funcionando.

Ao criar um ID de serviço, você cria um nome exclusivo e uma descrição de fácil identificação e trabalho na UI. Depois de ter criado seu ID de serviço, será possível criar chaves API específicas para cada ID de serviço que o aplicativo poderá usar para autenticação nos serviços do {{site.data.keyword.Bluemix_notm}}. Para assegurar-se de que seu aplicativo tenha o acesso apropriado para autenticação nos serviços do {{site.data.keyword.Bluemix_notm}}, você usará políticas de serviço designadas a cada ID de serviço criado. 

As políticas de acesso associadas a um ID de serviço permitem ações específicas que podem ser tomadas quando o ID do serviço é usado para acessar um serviço específico. Um único ID de serviço pode ter múltiplas políticas designadas que definem o nível de acesso permitido ao acessar múltiplos serviços ativados por Identidade e por acesso e até mesmo diferentes instâncias de um único serviço. Por exemplo, você tem dois serviços com duas instâncias de serviço cada um. Por exemplo, é possível designar a função `Viewer` a todas as instâncias disponíveis de um serviço e designar a função `Editor` a apenas uma instância de um segundo serviço. Dessa maneira é possível customizar o acesso a múltiplos serviços, mas usar uma única chave API para autenticação em todos.


## Criando um ID de serviço

Para criar um ID de serviço, acesse **Gerenciar** &gt; **Segurança** &gt; **Identity and Access** e, em seguida, selecione **IDs de serviço** no painel lateral. Siga o processo para criar um nome e uma descrição para seu ID de serviço. Em seguida, use o menu **Ações** para gerenciar seu ID de serviço. É possível iniciar designando uma política e criando chaves API. Para obter mais informações sobre como trabalhar com chaves API, veja [Gerenciando chaves API do ID de serviço](/docs/iam/serviceid_keys.html#serviceidapikeys). Para obter detalhes sobre os comandos da CLI que são usados para gerenciar um ID de serviço, veja [Comandos para gerenciar chaves API e políticas](/docs/cli/reference/bluemix_cli/bx_cli.html#bx_commands_iam). 

## Atualizando um ID de serviço

É possível atualizar um ID de serviço mudando o nome e a descrição a qualquer momento. Também é possível excluir e criar novas chaves API, conforme necessário, ou atualizar as políticas de acesso designadas. No entanto, quaisquer mudanças feitas em um ID de serviço existente, como mudar as políticas designadas ou excluir uma chave API que esteja sendo usada atualmente, poderão causar interrupções de serviço em aplicativos que estejam usando esse ID de serviço.


