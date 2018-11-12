---



copyright:

  years: 2018

lastupdated: "2018-10-30"



---

{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:screen: .screen}
{:new_window: target="_blank"}
{:tip: .tip}

# FAQ
{: #iamfaq}

## O que é o  {{site.data.keyword.cloud_notm}}  Identity and Access Management? 
{: #whatisiam}

O Identity and Access Management (IAM) permite que você autentique com segurança os usuários para os serviços da
plataforma e controle o acesso aos recursos na plataforma {{site.data.keyword.cloud_notm}}. Um conjunto de
serviços do IBM Cloud é ativado para usar o Cloud IAM para controle de acesso. Eles são organizados em grupos de
recursos dentro da conta para permitir que o acesso rápido e fácil a mais de um recurso de cada
vez seja concedido aos usuários. As políticas de acesso ao Cloud IAM são usadas para designar aos usuários e IDs de serviço o acesso aos recursos em sua conta. Para obter mais informações, consulte [{{site.data.keyword.cloud_notm}}
Identity and Access Management](/docs/iam/index.html#iamoverview).

## O que é um serviço ativado pelo IAM?
{: #iam-enabled}

Um serviço ativado para IAM deve estar em um grupo de recursos e o acesso ao serviço é fornecido por meio do uso
das políticas de acesso do IAM. Ao criar um serviço ativado para IAM por meio do catálogo, deve-se designá-lo a um grupo
de recursos. Para obter mais informações, consulte [O que é um recurso?](/docs/resources/acct_resources.html#resource)

O {{site.data.keyword.containerlong_notm}} é a única exceção. O seu acesso é controlado pelo IAM, mas ele
sempre é designado ao grupo de recursos padrão. Portanto, você não tem a opção de escolher um ao criá-lo por meio do catálogo. Além
disso, ele não pode ser designado a nenhum outro grupo de recursos


## O IAM e o Cloud Foundry estão relacionados?
{: #iam-cloudfoundry}

Eles não estão relacionados. O Cloud Foundry é uma plataforma de software livre que usa as organizações, os
espaços e as funções do Cloud Foundry para o gerenciamento de acesso. O IAM é a maneira segura de autenticar os usuários
para os serviços da plataforma e controlar o acesso aos recursos na plataforma {{site.data.keyword.cloud_notm}}
usando os grupos de recursos e as funções de acesso do IAM.

Os sistemas de gerenciamento de acesso são completamente diferentes. Os recursos do IAM pertencem a um grupo de
recursos e os recursos do Cloud Foundry pertencem a uma organização e um espaço. As políticas de acesso do IAM são
usadas para fornecer acesso aos recursos em um grupo de recursos. As funções de espaço e de organização do Cloud
Foundry são usadas para fornecer aos usuários acesso aos recursos do Cloud Foundry em um espaço. O IAM não concede
acesso a nada dentro dos espaços do Cloud Foundry e as funções do Cloud Foundry não podem conceder acesso aos recursos
dentro de um grupo de recursos.

## Como descobrir ao que tenho acesso?
{: #iam-access}

Acesse **Gerenciar** &gt; **Acesso (IAM)** e selecione o seu nome na coluna
Usuário. Então, dependendo do acesso que esteja procurando, abra as diferentes guias:

* Para determinar em quais grupos de acesso você está, selecione **Grupos de acesso**.
* Para acesso ao IAM, selecione as **Políticas de acesso**.
* Para as funções do Cloud Foundry, selecione **Acesso do Cloud Foundry**.

## Como solicitar acesso a um recurso?
{: #request-access}

O proprietário da conta pode atualizar o seu acesso a qualquer recurso na conta ou é possível entrar em contato
com qualquer usuário que tenha a função de administrador designada no serviço ou na instância de serviço. 

## Por que devo usar os grupos de recursos e os grupos de acesso? 
{: #resource-groups}

Um grupo de recursos é um contêiner lógico para os recursos. Quando um recurso é criado, ele é designado a um
grupo de recursos e não pode ser movido depois de ser incluído. 

Um grupo de acesso é usado para organizar facilmente um conjunto de usuários e IDs de serviço em uma única
entidade para facilitar as designações de acesso. É possível designar uma política única a um grupo de acesso para
conceder a todos os membros essas permissões. Se você tiver mais de um usuário ou ID de serviço que precisa do mesmo
acesso, crie um grupo de acesso em vez de designar o mesmo acesso múltiplas vezes por usuário ou ID de serviço
individual.

Usando os grupos de recursos e os grupos de acesso, é possível aperfeiçoar a política de cessão de acesso designando um número limitado de políticas. É possível organizar todos os recursos aos quais um grupo específico de
usuários e de IDs de serviço precisa de acesso em um único grupo de recursos, agrupar todos os usuários ou IDs de serviço
em um grupo de acesso e, em seguida, designar uma política única que fornece acesso a todos os recursos no grupo de
recursos.

## Como assegurar que os usuários possam criar recursos em um grupo de recursos?
{: #resources}

Para criar um recurso em um grupo de recursos, o usuário deve ter duas políticas de acesso: uma designada ao
próprio grupo de recursos e uma designada aos recursos no grupo. O acesso ao próprio grupo de recursos é
simplesmente o acesso ao contêiner que organiza os recursos e esse tipo de política permite que um usuário visualize,
edite ou gerencie o acesso ao grupo, mas não aos recursos dentro dele. O acesso aos serviços dentro do grupo de recursos
permite que um usuário trabalhe com as instâncias de serviço, o que significa que o usuário pode criar uma instância de
serviço.

Portanto, minimamente, o usuário deve ter o seguinte acesso:

* Função de visualizador ou superior no próprio grupo de recursos
* Função de editor ou superior no serviço ou em todos os serviços no grupo de recursos


## Qual acesso é necessário para fornecer acesso aos outros?
{: #user-access}

Deve-se ter a função de administrador no serviço ou recurso ao qual deseja designar o acesso dos usuários. Se
desejar designar acesso a todos os serviços ou recursos na conta, precisará de uma política em todos os serviços
ativados para o Identity and Access com a função de administrador. 

## Qual é a diferença entre fornecer acesso para gerenciar um grupo de recursos e fornecer acesso a recursos
dentro de um grupo de recursos?
{: #providing-access}

Quando você tem acesso para gerenciar um grupo de recursos, é possível visualizar, editar o nome e gerenciar o
acesso para o próprio grupo de recursos, dependendo da função designada. O acesso ao próprio grupo de recursos não
concede a um usuário acesso aos recursos dentro do grupo.

Quando você tem acesso aos recursos dentro de um grupo de recursos, é possível editar, excluir e criar instâncias
ou ter todas as ações de gerenciamento para os serviços especificados no grupo de recursos, dependendo da função
designada. 

Para obter exemplos das funções de gerenciamento da plataforma e das ações para os serviços de gerenciamento de
conta, consulte a [Tabela de funções da plataforma](/docs/iam/users_roles.html#platformrolestable2).

## Quem pode remover usuários?
{: #remove-users}

O proprietário da conta sempre pode incluir e remover usuários. Além disso, qualquer usuário com um dos dois
tipos de política a seguir pode remover usuários:

* Editor ou administrador em todos os serviços de gerenciamento de conta
* Editor ou administrador no serviço de gerenciamento de conta do gerenciamento de usuários

## Como ativar a autenticação de diversos fatores?
{: #multi-factor}

Acesse **Gerenciar** &gt; **Acesso (IAM)** e escolha
**Configurações**.
Escolha **Autenticação de diversos fatores** e, em seguida, clique em **Aplicar
mudanças**. Para obter mais informações, consulte [Ativando a
autenticação de diversos fatores](/docs/iam/mfa.html#enablemfa).

## Qual é a diferença entre as funções do serviço e da plataforma? 
{: #service-platform-roles}

As funções do serviço e da plataforma são dois tipos diferentes de funções: 

* As funções da plataforma se referem a como você trabalha com um serviço dentro de uma conta, como a criação
de instâncias, a ligação de instâncias e o gerenciamento do acesso do usuário ao serviço. Para os serviços da plataforma,
essas funções permitem que os usuários criem os grupos de recursos e gerenciem os IDs de serviço, por exemplo. As
funções da plataforma são: administrador, editor, operador e visualizador. 

* As funções de serviço definem a capacidade de executar ações em um serviço e são específicas para todos os
serviços, como a execução de chamadas API ou o acesso à UI. As funções de serviço são: gerenciador, gravador e leitor. Para obter mais informações sobre como essas funções se aplicam, consulte a documentação do serviço específico.

## Qual é a diferença entre um grupo de recursos e as organizações e os espaços do Cloud Foundry?
{: #groups-organizations}

Com o início do {{site.data.keyword.Bluemix_notm}}, um serviço da plataforma de software livre para
controle de acesso e organização de recursos chamado Cloud Foundry era o único método para organizar e controlar o
acesso aos recursos. Com a expansão do {{site.data.keyword.Bluemix_notm}}, um novo método que
pudesse ser usado por todos os tipos de serviços e recursos se fez necessário. Os grupos de recursos agora são usados
para agrupar e organizar muitos tipos de recursos e o IAM é usado para controlar consistentemente o acesso aos serviços e
recursos. Alguns serviços já adotaram o uso dos grupos de recursos e do IAM, e os serviços adicionais serão
movidos ao longo do tempo para o novo método para organizar os recursos e gerenciar o acesso.

O controle de acesso e a organização do recurso da conta são as principais diferenças entre os grupos de recursos
e as organizações e os espaços do Cloud Foundry. Os grupos de recursos organizam os serviços ativados para o IAM em uma
conta que tem o acesso controlado por meio do uso das políticas do IAM. As organizações e os espaços são gerenciados
usando as funções do Cloud Foundry para controle de acesso e os recursos do Cloud Foundry são designados aos espaços. As
organizações e os espaços podem ser usados para organizar e controlar o acesso aos recursos somente dentro da região do
Cloud Foundry, enquanto os grupos de recursos e o IAM podem ser usados para múltiplos tipos de recursos no {{site.data.keyword.Bluemix_notm}}.

## Como designar um usuário como um administrador de conta? 
{: #account-administrator}

Para delegar a função de administrador da conta usando as políticas do IAM, é necessário criar duas políticas:

* Administrator em todos os serviços ativados para o Identity and Access, que permite a um usuário criar
instâncias de serviço e designar aos usuários acesso a todos os recursos na conta
* Administrator em todos os serviços de gerenciamento de conta, que permite a um usuário concluir tarefas,
como convidar e remover usuários, gerenciar os grupos de acesso, gerenciar os IDs de serviço, gerenciar as ofertas do
catálogo privado e rastrear o faturamento e o uso.
