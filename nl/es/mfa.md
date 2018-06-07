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

# Habilitación de la autenticación de multifactores
{: #enablemfa}

La autenticación de multifactores (MFA) añade una capa de seguridad extra a su cuenta solicitando a todos los usuarios que proporcionen un código de acceso de una sola vez basado en tiempo además del IBMid y la contraseña estándar durante el inicio de sesión. También se conoce como autenticación de dos factores (2FA). La habilitación de esta función en su cuenta no solo requiere que utilice un estándar de seguridad adicional en el inicio de sesión, también son necesarios todos los usuarios agregados a su cuenta.

## Consideraciones

Antes de habilitar la autenticación de multifactores en su cuenta, revise las consideraciones siguientes:

* Cuando habilite la MFA en su cuenta, todos los usuarios agregados a su cuenta deben completar el proceso de 2FA la próxima vez que inicien sesión.
* Las claves API para los usuarios y los ID de servicio seguirán funcionando cuando la MFA esté habilitada.
* Si necesita utilizar una CLI CF nativa o un inicio de sesión de IU en Cloud Foundry, debe utilizar las claves de API o el inicio de sesión único (SSO) cuando la MFA esté habilitada en la cuenta.
* No se ofrece soporte de la MFA para los usuarios que inician sesión con una identidad federada.
* Planifique una estrategia de soporte y comunicación para los usuarios de su cuenta:
  * Elija la fecha y la hora en habilitar la MFA que produzca el menor impacto en su empresa.
  * Cuando haya habilitado la MFA, proporcione a los usuarios de su cuenta información sobre cómo [realizar la configuración](mfa.html#setupapp).
  
Si dispone de una cuenta enlazada y ha configurado previamente la [2FA en el portal de control](/docs/customer-portal/cpenable2fa.html#customerportal_2fa), tenga en cuenta lo siguiente:

* La MFA de su cuenta de {{site.data.keyword.Bluemix_notm}} se extiende por toda la plataforma y los servicios de infraestructura de su cuenta enlazada. Puesto que el valor de la cuenta de la MFA sustituye la 2FA en el portal de control, puede elegir inhabilitar la 2FA que ha adquirido y configurarla solo para los recursos de infraestructura en favor de la opción de configuración de MFA.
* Si es un usuario federado, la MFA no se admite. Por lo tanto, es posible que desee retener la 2FA solo para los recursos de infraestructura para garantizar la seguridad de sus recursos.

## Habilitación de la autenticación de multifactores

Para habilitar la MFA, debe ser el administrador de la cuenta. La habilitación de la MFA no afecta a los usuarios que ya han iniciado sesión, ya que el cumplimiento de la MFA de la cuenta solo será efectiva en los inicios de sesión nuevos. Cualquier administrador que habilite la MFA para la cuenta debe notificar a los usuarios de la cuenta que la MFA está activada y describir el impacto a los usuarios en el próximo inicio de sesión. 

1. En la barra de menús, pulse **Gestionar** &gt; **Seguridad** &gt; **Identidad y acceso** y seleccione **Valores**.
2. Seleccione **Autenticación de multifactores** &gt; y pulse **Aplicar cambios**.
3. En la ventana de confirmación, pulse **Sí, estoy seguro**.

## Configuración del código de acceso de una sola vez
{: #setupapp}

Después de habilitar la MFA en su cuenta, debe configurar el código de acceso de un solo uso con una app de autenticador la próxima vez que inicie sesión. Todos los usuarios de su cuenta deben configurar también el código de acceso de un solo uso la próxima vez que inicien sesión. 

Complete los pasos siguientes para configurar por primera vez el código de acceso de una sola vez con una app de autenticador:

1. Inicie sesión con su IBMid y contraseña. 

Puede tardar hasta 5 minutos en iniciar sesión de nuevo con la MFA configurada una vez que esta se haya habilitado.

2. Seleccione **Verificar** en la pantalla **Es necesaria la verificación** para configurar la MFA con una app de autenticador.
3. Seleccione **Configurar la app de autenticador** para obtener un código de acceso de una sola vez en su correo electrónico y continuar configurando la app de autenticador.
4. Seleccione **Verificar**.
5. Explore el código de barras con su app, o pulse **¿No puede explorar el código de barras?** para especificar una clave proporcionada manualmente. 
6. Pulse **Continuar** para introducir el código.
7. Especifique el código y seleccione **Verificar**. 

Si encuentra un mensaje de error que indica que ya ha configurado la autenticación, pero su código de verificación no funciona o no tiene un código de verificación que especificar, póngase en contacto con el [Centro de atención al cliente](https://www.ibm.com/ibmid/myibm/help/us/helpdesk.html){: new_window} ![Icono de enlace externo](../icons/launch-glyph.svg "Icono de enlace externo") para restablecer la inscripción de MFA.
{: tip}
{: #mfahelp}


## Inhabilitación de la autenticación de multifactores
{: #disablemfa}

Para inhabilitar MFA, debe ser el administrador de la cuenta. La inhabilitación de la MFA no afecta a los usuarios que ya han iniciado sesión y la acción será efectiva en todos los inicios de sesión nuevos.

1. En la barra de menús, pulse **Gestionar** &gt; **Seguridad** &gt; **Identidad y acceso** y seleccione **Valores**.
2. Seleccione **Estándar** &gt; y pulse **Sí, estoy seguro**.
3. En la ventana de confirmación, pulse **Sí, estoy seguro**.
