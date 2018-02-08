---

copyright:

  years: 2015, 2018
lastupdated: "2017-08-23"

---

{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:screen: .screen}
{:new_window: target="_blank"}

# Trabalhando com chaves API
{: #manapikey}

Uma chave da interface de programação de aplicativos (chave API) é um código exclusivo passado para uma interface de programação de aplicativos (API) para identificar o aplicativo de chamada ou o usuário.  As chaves API são usadas para rastrear e controlar como a API está sendo usada, por exemplo, para evitar uso malicioso ou abuso da API. A chave API muitas vezes age como um identificador exclusivo e um token secreto para autenticação e geralmente tem um conjunto de direitos de acesso específicos para a identidade associada a ele.

As chaves API podem ser associadas ao seguinte:

* Usuários
* IDs de Serviço

É possível criar e usar as chaves API que estão vinculadas a sua conta. Um usuário federado ou não federado pode criar uma chave API a ser usada na CLI ou como parte da automação para efetuar login como sua identidade do usuário. Para obter mais informações sobre como usar uma chave API associada à sua identidade de usuário, veja [Gerenciando chaves API do usuário](userid_keys.html).

Também é possível usar as chaves API associadas aos IDs de serviço criados. Os IDs de serviço são usados para conectar um aplicativo dentro ou fora do {{site.data.keyword.Bluemix_notm}} a um serviço {{site.data.keyword.Bluemix_notm}}. Para obter mais informações sobre como criar chaves API associadas a um ID de serviço, veja [Gerenciando chaves API do ID de serviço](serviceid_keys.html).
