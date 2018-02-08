---

copyright:

  years: 2017, 2018

lastupdated: "2017-11-16"

---

{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:screen: .screen}
{:new_window: target="_blank"}

# Acesso ao Cloud Foundry
{: #cfaccess}

No momento, nem todos os serviços podem ser gerenciados usando o Cloud IAM. É possível continuar a usar o Cloud Foundry para essas instâncias de serviço, fornecendo aos usuários acesso à organização e ao espaço aos quais a instância pertence com uma função do Cloud Foundry designada para definir o nível de acesso que é permitido.


## Funções do Cloud Foundry
{: #cfroles}

As funções do Cloud Foundry concedem acesso a organizações e espaços dentro da conta. As funções do Cloud Foundry não ativam as permissões de usuário para concluir ações dentro do contexto de um serviço na conta.

As funções a seguir podem ser designadas no nível de organização:

| Função organizacional | Permissões |
|-------------------|-------------|
|Gerente | Os gerenciadores de organização podem criar, visualizar, editar ou excluir espaços dentro da organização, visualizar o uso e cota da organização, convidar os usuários para a organização, gerenciar quem tem acesso à organização e suas funções na organização, além de gerenciar domínios customizados para a organização. |
|Gerenciador de faturamento | Gerenciadores de faturamento podem visualizar informações de uso de tempo de execução e serviço para a organização na página de Painel de uso.  |
|Auditor | Auditores da organização podem visualizar o conteúdo do aplicativo e do serviço na organização. Os auditores também podem visualizar os usuários na organização e suas funções designadas, além da cota da organização. |
{:caption="Tabela 1. Funções e permissões de organização" caption-side="top"}

As funções a seguir podem ser designadas no nível de espaço:

| Função de espaço | Permissões |
|------------|-------------|
|Gerente | Os gerenciadores de espaço podem incluir usuários existentes e gerenciar funções dentro do espaço. O gerenciador de espaço também pode visualizar o número de instâncias, ligações de serviço e
o uso recurso para cada aplicativo no espaço. |
|Desenvolvedor | Desenvolvedores de espaço podem criar, excluir e gerenciar aplicativos e serviços dentro do espaço. Algumas das tarefas de gerenciamento incluem implementar aplicativos, iniciar ou parar
aplicativos, renomear um aplicativo, excluir um aplicativo, renomear um espaço, ligar ou desvincular um serviço para um aplicativo, visualizar o número ou as instâncias, ligações de serviço e uso de recurso
para cada aplicativo no espaço. Além disso, o desenvolvedor de espaço pode associar uma URL interna ou externa com um aplicativo no espaço.   |
|Auditor | Auditores de espaço têm acesso somente leitura a todas as informações sobre o espaço, como informações sobre o número de instâncias, ligações de serviço e uso de recurso para cada aplicativo no
espaço. |
{:caption="Tabela 2. Funções e permissões de espaço" caption-side="top"}

**Nota**: os usuários designados à função de espaço de gerenciador ou desenvolvedor podem acessar a variável de ambiente VCAP_SERVICES. No entanto, um usuário designado à função de auditor não pode acessar VCAP_SERVICES.
