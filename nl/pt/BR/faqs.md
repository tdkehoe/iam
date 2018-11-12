---



copyright:

  years: 2018

lastupdated: "2018-10-17"



---

{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:screen: .screen}
{:new_window: target="_blank"}
{:tip: .tip}

# FAQ
{: #iamfaq}

## O que é o {{site.data.keyword.cloud_notm}} Identity and Access Management? 
{: #whatisiam}

O Identity and Access Management (IAM) permite que você autentique os usuários com segurança para os serviços de
plataforma e controle o acesso aos recursos em toda a plataforma {{site.data.keyword.cloud_notm}}. Um conjunto
de serviços do IBM Cloud é ativado para usar o Cloud IAM para controle de acesso. Eles são organizados em grupos de
recursos dentro da conta para permitir que os usuários recebam acesso rápido e fácil a mais de um recurso ao
mesmo tempo. As políticas de acesso ao Cloud IAM são usadas para designar aos usuários e IDs de serviço o acesso aos recursos em sua conta. Para obter mais informações, consulte [{{site.data.keyword.cloud_notm}}
Identity and Access Management](/docs/iam/index.html#iamoverview).

## O que é um serviço ativado para IAM?
{: #iam-enabled}

Um serviço ativado para IAM deve estar em um grupo de recursos e o acesso ao serviço é fornecido usando
as políticas de acesso do IAM. Ao criar um serviço ativado para IAM por meio do catálogo, deve-se designá-lo a um
grupo de recursos. Para obter mais informações, consulte [O que é um recurso?](/docs/resources/acct_resources.html#resource)

O {{site.data.keyword.containerlong_notm}} é a única exceção; seu acesso é controlado pelo IAM, mas
sempre é designado ao grupo de recursos padrão. Portanto, você não tem a opção de escolher um ao criá-lo por meio do catálogo. E, ele não pode ser designado a nenhum outro grupo de recursos


## O IAM e o Cloud Foundry são relacionados?
{: #iam-cloudfoundry}

Eles não são relacionados. O Cloud Foundry é uma plataforma de software livre que usa as organizações, os espaços
e as funções do Cloud Foundry para o gerenciamento de acesso. O IAM é a maneira segura de autenticar os usuários para
os serviços da plataforma e controlar o acesso aos recursos na plataforma {{site.data.keyword.cloud_notm}}
usando os grupos de recursos e as funções de acesso do IAM.

Os sistemas de gerenciamento de acesso são completamente diferentes. Os recursos do IAM pertencem a um grupo de
recursos e os recursos do Cloud Foundry pertencem a uma organização e um espaço. As políticas de acesso do IAM são
usadas para fornecer acesso aos recursos em um grupo de recursos. E, as funções de espaço e de organização do Cloud
Foundry são usadas para fornecer aos usuários acesso aos recursos do Cloud Foundry em um espaço. O IAM não concede
acesso a nada dentro dos espaços do Cloud Foundry e as funções do Cloud Foundry não podem conceder acesso a recursos
dentro de um grupo de recursos.

## Como descobrir ao que tenho acesso?
{: #iam-access}

Acesse **Gerenciar** &gt; **Acesso (IAM)** e selecione o seu nome na coluna
Usuário. Então, dependendo do acesso que esteja procurando, abra as diferentes guias:

* Para determinar em quais grupos de acesso você está, selecione **Grupo de acesso**.
* Para acesso ao IAM, selecione as **Políticas de acesso**.
* Para as funções do Cloud Foundry, selecione **Acesso do Cloud Foundry**.

## Como solicitar acesso a um recurso?
{: #request-access}

O proprietário da conta pode atualizar o seu acesso a qualquer recurso na conta ou é possível entrar em contato
com qualquer usuário com a função de administrador designada no serviço ou na instância de serviço. 

## Por que devo usar os grupos de recursos e os grupos de acesso? 
{: #resource-groups}

Um grupo de recursos é um contêiner lógico para os recursos. Quando um recurso é criado, ele é designado a um
grupo de recursos e não pode ser movido depois de ser incluído. 

Um grupo de acesso é usado para organizar facilmente um conjunto de usuários e IDs de serviço em uma única
entidade para facilitar as designações de acesso. É possível designar uma política única a um grupo de acesso para
conceder a todos os membros essas permissões. Se você tiver mais de um usuário ou ID de serviço que precisa do mesmo
acesso, crie um grupo de acesso em vez de designar o mesmo acesso múltiplas vezes por usuário ou ID de serviço
individual.

Usando os grupos de recursos e os grupos de acesso, é possível aperfeiçoar a política de designação de acesso,
designando um número limitado de políticas. É possível organizar todos os recursos aos quais um grupo específico de
usuários e IDs de serviço precisa de acesso em um único grupo de recursos, agrupar todos os usuários ou IDs de serviço em um grupo
de acesso e, em seguida, designar uma política única que fornece acesso a todos os recursos no grupo de recursos.

## Como assegurar que os usuários possam criar recursos em um grupo de recursos?
{: #resources}

Para criar um recurso em um grupo de recursos, o usuário deve ter duas políticas de acesso: uma designada para o
próprio grupo de recursos e uma designada para os recursos no grupo. O acesso ao próprio grupo de recursos é
simplesmente o acesso ao contêiner que organiza os recursos e esse tipo de política permite que um usuário visualize,
edite ou gerencie o acesso ao grupo, mas não aos recursos dentro dele. O acesso aos serviços dentro do grupo de recursos
permite que um usuário trabalhe com as instâncias de serviço, o que significa que o usuário pode criar uma instância de
serviço.

Portanto, minimamente, o usuário deve ter o acesso a seguir:

* Função de visualizador ou superior no próprio grupo de recursos
* Função de editor ou superior no serviço ou em todos os serviços no grupo de recursos


## Qual acesso eu preciso para fornecer acesso aos outros?
{: #user-access}

Deve-se ter a função de administrador no serviço ou recurso ao qual deseja designar o acesso dos usuários. Se
desejar designar acesso a todos os serviços ou recursos na conta, precisará de uma política em todos os serviços
ativados para o Identity and Access com a função de administrador. 

## Qual é a diferença entre fornecer acesso para gerenciar um grupo de recursos e fornecer acesso a recursos dentro
de um grupo de recursos?
{: #providing-access}

Quando você tem acesso para gerenciar um grupo de recursos, é possível visualizar, editar o nome e gerenciar o
acesso para o próprio grupo de recursos, dependendo da função designada. O acesso ao próprio grupo de recursos não dá
a um usuário acesso aos recursos dentro do grupo.

Quando você tem acesso aos recursos dentro de um grupo de recursos, é possível editar, excluir e criar instâncias
ou ter todas as ações de gerenciamento para os serviços especificados no grupo de recursos, dependendo da função
designada. 

Para obter exemplos das funções de gerenciamento de plataforma e das ações para os serviços de gerenciamento de
conta, consulte a [Tabela de funções da plataforma](/docs/iam/users_roles.html#platformrolestable2).

## Quem pode remover os usuários?
{: #remove-users}

Apenas o proprietário da conta pode remover os usuários. 

## Como ativar a autenticação de diversos fatores?
{: #multi-factor}

Acesse **Gerenciar** &gt; **Acesso (IAM)** e escolha
**Configurações**.
Escolha **Autenticação de diversos fatores** e, em seguida, clique em **Aplicar
mudanças**. Para obter mais informações, consulte [Ativando a autenticação de diversos fatores](/docs/iam/mfa.html#enablemfa).

## Qual é a diferença entre as funções de serviço e de plataforma? 
{: #service-platform-roles}

As funções de serviço e de plataforma são dois tipos diferentes de funções: 

* As funções de plataforma são como você trabalha com um serviço dentro de uma conta, como a criação de
instâncias, a ligação de instâncias e o gerenciamento do acesso do usuário ao serviço. Para os serviços de plataforma,
essas funções permitem que os usuários criem grupos de recursos e gerenciem IDs de serviço, por exemplo. As funções de
plataforma são: administrador, editor, operador e visualizador. 

* As funções de serviço definem a capacidade de executar as ações em um serviço e são específicas para todos os
serviços, como executar chamadas API ou acessar a UI. As funções de serviço são: gerenciador, gravador e leitor. Para
obter mais informações sobre como essas funções se aplicam, consulte a documentação do serviço específico.

## Qual é a diferença entre um grupo de recursos e as organizações e os espaços do Cloud Foundry?
{: #groups-organizations}

Com o início do {{site.data.keyword.Bluemix_notm}}, um serviço de plataforma de software livre
para controle de acesso e a organização de recursos chamada Cloud Foundry era o único método para organizar e
controlar o acesso aos recursos. À medida que o {{site.data.keyword.Bluemix_notm}} se expandiu, um novo método
foi necessário que pudesse ser usado por todos os tipos de serviços e recursos. Agora, os grupos de recursos são
usados para agrupar e organizar muitos tipos de recursos e o IAM é usado para controlar consistentemente o acesso aos serviços e
recursos. Alguns serviços já foram adotados usando os grupos de recursos e o IAM, e serviços adicionais serão
movidos ao longo do tempo para o novo método para organizar os recursos e gerenciar o acesso.

O controle de acesso e a organização do recurso da conta são as principais diferenças entre os grupos de recursos
e as organizações e os espaços do Cloud Foundry. Os grupos de recursos organizam serviços ativados para IAM em uma conta
que tem o acesso controlado por meio das políticas do IAM. As organizações e os espaços são gerenciados usando as funções
do Cloud Foundry para controle de acesso e os recursos do Cloud Foundry são designados aos espaços. As organizações e os
espaços podem ser usados para organizar e controlar o acesso aos recursos apenas dentro da região do Cloud Foundry, enquanto os
grupos de recursos e o IAM podem ser usados para múltiplos tipos de recursos no {{site.data.keyword.Bluemix_notm}}.

