---

copyright:

  years: 2018
lastupdated: "2018-05-22"

---

{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:screen: .screen}
{:new_window: target="_blank"}
{:tip: .tip}

# Ativando a autenticação de diversos fatores
{: #enablemfa}

A autenticação de diversos fatores (MFA) inclui uma camada extra de segurança em sua conta solicitando que todos os usuários forneçam uma senha descartável baseada em tempo, além de seu IBMid e senha padrão durante o login. Isso também é conhecido geralmente como autenticação de dois fatores (2FA). A ativação desse recurso para sua conta requer que não apenas você use o padrão de segurança adicional no login, mas também todos os usuários que são incluídos em sua conta.

## Considerações

Antes de ativar a autenticação de diversos fatores para sua conta, revise as considerações a seguir:

* Quando você ativar a MFA para sua conta, todos os usuários nela incluídos deverão concluir o processo 2FA na próxima vez que efetuarem login.
* As chaves API para usuários e IDs de serviço continuarão funcionando após a MFA ser ativada.
* Se você requer o uso de login de CLI ou UI do CF nativo no Cloud Foundry, deve-se usar as chaves API ou a conexão única (SSO) após a MFA ser ativada para a conta.
* A MFA não é suportada para usuários que efetuam login com uma identidade federada.
* Planeje uma estratégia de comunicação e suporte para usuários em sua conta:
  * Escolha uma data e hora que você planeja ativar a MFA que resulte no menor impacto para seus negócios.
  * Notifique seus usuários da conta depois de ativar a MFA com informações sobre como [configurar](mfa.html#setupapp).
  
Se você tem uma conta vinculada e configurou anteriormente a [2FA no portal de controle](/docs/customer-portal/cpenable2fa.html#customerportal_2fa), considere o seguinte:

* A MFA para sua conta do {{site.data.keyword.Bluemix_notm}} se estende pelo serviços de plataforma e infraestrutura para sua conta vinculada. Como a configuração da conta da MFA substitui a 2FA no portal de controle, você pode escolher desativar a 2FA que foi comprada e configurar somente para seus recursos de infraestrutura em favor da opção de configuração da MFA.
* Se você é um usuário federado, a MFA não é suportada. Portanto, talvez você deseje reter sua 2FA somente para recursos de infraestrutura para assegurar a segurança de seus recursos.

## Ativando a autenticação de diversos fatores

Para ativar a MFA, deve-se ser o administrador de conta. A ativação da MFA não afeta usuários já conectados, pois o cumprimento da MFA na conta entra em vigor apenas em novos logins. Qualquer administrador que ative a MFA para a conta deve notificar os usuários da conta de que a MFA está ativada e descrever o impacto para os usuários em seu próximo login. 

1. Na barra de menus, clique em **Gerenciar** &gt; **Segurança** &gt; **Identidade e acesso** e, em seguida, selecione **Configurações**.
2. Selecione **Autenticação de diversos fatores** &gt; e, em seguida, clique em **Aplicar mudanças**.
3. Nas janelas de confirmação, clique em **Sim, tenho certeza**.

## Configurando a senha descartável
{: #setupapp}

Depois que você ativa a MFA em sua conta, deve-se configurar a senha descartável com um app autenticador na próxima vez que o login é efetuado. Todos os usuários em sua conta também devem configurar a senha descartável no próximo login. 

Conclua as etapas a seguir para configurar sua senha descartável com um aplicativo autenticador pela primeira vez:

1. Efetue login com seu IBMid e senha. 

Pode levar até 5 minutos para que você possa efetuar login novamente com a MFA configurada após ela ser ativada.

2. Selecione **Verificar** na tela **Verificação é necessária** para configurar a MFA com um aplicativo autenticador.
3. Selecione **Configurar seu aplicativo autenticador** para ter um código descartável enviado para seu e-mail para continuar a configurar o aplicativo autenticador.
4. Selecione **Verificar**.
5. Varra o código de barras com seu app ou clique em **Não é possível varrer o código de barras?** para inserir uma chave fornecida manualmente. 
6. Clique em **Continuar** para inserir seu código.
7. Insira seu código e selecione **Verificar**. 

Se você encontra uma mensagem de erro indicando que já configurou a autenticação, mas seu código de verificação não está funcionando ou você não tem o código de verificação para inserir, deve-se entrar em contato com o [Help desk](https://www.ibm.com/ibmid/myibm/help/us/helpdesk.html){: new_window} ![Ícone de link externo](../icons/launch-glyph.svg "Ícone de link externo") para reconfigurar sua inscrição da MFA.
{: tip}
{: #mfahelp}


## Desativando a autenticação de diversos fatores
{: #disablemfa}

Para desativar a MFA, deve-se ser o administrador de conta. A desativação da MFA não afeta usuários que já estão com login efetuado e a ação entra em vigor em todos os logins novos.

1. Na barra de menus, clique em **Gerenciar** &gt; **Segurança** &gt; **Identidade e acesso** e, em seguida, selecione **Configurações**.
2. Selecione **Padrão** &gt; e, em seguida, clique em **Sim, tenho certeza**.
3. Nas janelas de confirmação, clique em **Sim, tenho certeza**.
