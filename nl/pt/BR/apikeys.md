---

copyright:

  years: 2015, 2018
lastupdated: "2018-01-26"

---

{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:screen: .screen}
{:new_window: target="_blank"}

# Trabalhando com chaves API
{: #manapikey}

Uma chave da interface de programação de aplicativos (chave API) é um código exclusivo passado para uma interface de programação de aplicativos (API) para identificar o aplicativo de chamada ou o usuário.  As chaves API são usadas para rastrear e controlar como a API está sendo usada, por exemplo, para evitar uso malicioso ou abuso da API. A chave API muitas vezes age como um identificador exclusivo e um token secreto para autenticação e geralmente tem um conjunto de direitos de acesso específicos para a identidade associada a ele.

## Chaves API da plataforma

As chaves API da plataforma são criadas na UI do Identity and Access Management e podem ser associadas ao seguinte:

* Usuário de uma conta
* IDs de serviço criados em uma conta

É possível criar e usar as chaves API que estão vinculadas a sua conta. Um usuário federado ou não federado pode criar uma chave API a ser usada na CLI ou como parte da automação para efetuar login como sua identidade do usuário. Para obter mais informações sobre como usar uma chave API associada à sua identidade de usuário, veja [Gerenciando chaves API do usuário](userid_keys.html).

Também é possível usar as chaves API associadas aos IDs de serviço criados. Os IDs de serviço são usados para conectar um aplicativo dentro ou fora do {{site.data.keyword.Bluemix_notm}} a um serviço {{site.data.keyword.Bluemix_notm}}. Para obter mais informações sobre como criar chaves API associadas a um ID de serviço, veja [Gerenciando chaves API do ID de serviço](serviceid_keys.html).

## Outras chaves API do {{site.data.keyword.Bluemix_notm}}

Além das chaves API de sua plataforma, há alguns outros tipos de chaves API que você pode usar ao usar o {{site.data.keyword.Bluemix_notm}}:

* Chaves API de infraestrutura
* Chaves API específicas do serviço

As chaves API de infraestrutura são criadas no portal do cliente, estão associadas ao ID do usuário de sua conta do SoftLayer e são usadas ao acessar as APIs para serviços de infraestrutura.

Alguns serviços no {{site.data.keyword.Bluemix_notm}} também podem fornecer uma chave API para você usar ao interagir com o serviço. Por exemplo, se você estiver visualizando os detalhes do serviço de um serviço do Watson em seu painel, será possível criar uma credencial, que inclui uma chave API e o segredo, que é específica apenas para esse serviço na guia Credenciais de serviço.

