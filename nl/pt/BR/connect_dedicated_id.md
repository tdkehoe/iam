---



copyright:

  years: 2015，2018

lastupdated: "2018-05-22"

---

{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:screen: .screen}
{:tip: .tip}
{:new_window: target="_blank"}

# Conectando um ID dedicado ao seu IBMid público
{: #connect_dedicated_id}

Para efetuar login em uma nuvem dedicada na qual o serviço IAM público está disponível, deve-se efetuar login na CLI do {{site.data.keyword.Bluemix_notm}} com seu IBMid público em vez do ID dedicado.


```
  $ ibmcloud login -a https://api.{dedicated_env}.bluemix.net
  Terminal da API: https://api.{dedicated_env}.bluemix.net

  O serviço de token público do IAM está disponível no ambiente dedicado.
  Efetue login com seu IBMid público ou use '--no-iam' para efetuar login somente como um usuário dedicado.

  E-mail>
```

Se seu ID dedicado já está conectado ao IBMid público, ele se autentica e efetua login:

```
  Authenticating...
  OK

  Conectado ao usuário dedicado my_dedicated_id
```

No entanto, se seu ID dedicado ainda não estiver conectado ao IBMid público, será solicitado que você se conecte manualmente ao IBMid público:

```
  You are logging in with an IBMid that is not associated with any dedicated user.
  To set up the connection, input the credentials of the dedicated user.

  Choose a credential type:
  1. User name and password
  2. One Time Code (Get one at https://login.{dedicated_env}.bluemix.net.com/passcode)
  Enter a number>
```

Selecione uma opção para inserir as credenciais para o ID dedicado. Após a autenticação bem-sucedida, seu ID dedicado será conectado a seu IBMid público.

## Forçar o login no servidor UAA local

Para forçar a criação de log para o servidor do UAA com um ID dedicado, especifique a opção `--no-iam` no comando `ibmcloud login`:

```
  $ ibmcloud login --no-iam
```

## Desconectar seu ID dedicado do IBMid público 

É possível usar `ibmcloud iam dedicated-id-disconnect` para desconectar o IBMid público com o ID dedicado conectado.

```
  $ ibmcloud iam dedicated-id-disconnect Você realmente deseja desconectar my_dedicated_id do IBMid público? (Y/N)> y
  Disconnecting dedicated user my_dedicated_id from public IBMid...
  OK

  Logging out...
  OK
```
