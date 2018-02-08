---

copyright:

  years: 2015, 2018
lastupdated: "2017-12-07"

---

{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:screen: .screen}
{:new_window: target="_blank"}
{:tip: .tip}

# Invitación de usuarios y asignación de acceso
{: #iamuserinv}

Para invitar a usuarios y gestionar invitaciones pendientes, debe ser propietario de cuenta o gestor de la organización o bien debe tener permisos de la infraestructura para añadir usuarios. Puede invitar a usuarios, cancelar invitaciones y volver a enviar una invitación pendiente a un usuario invitado. Además, puede invitar a un único usuario o a varios usuarios de una vez.  
{:shortdesc}

## Invitación a usuarios

Complete los siguientes pasos para invitar a usuarios o para gestionar invitaciones de usuario en su cuenta:

1. Desde la barra de menús, pulse **Gestionar** &gt; **Seguridad** &gt; **Identidad y acceso** y luego pulse **Usuarios**. La página Usuarios muestra una lista de los usuarios con sus direcciones de correo electrónico y el estado actual de las cuentas actualmente seleccionadas.
2. Pulse **Invitar usuarios**.
3. Especifique la dirección de correo electrónico del usuario. Si está invitando a más de un usuario con una única invitación, a todos se les asigna el mismo acceso.
4. Añada una o varias de las opciones de acceso que gestionará. Debe asignar al menos una opción de acceso. Para las opciones de acceso adicionales que no desee añadir y configurar, se asigna el valor predeterminado *no access* (sin acceso). Es posible que vea una o todas las opciones de acceso siguientes, en función de las opciones que está autorizado a gestionar: **Servicios**, **Acceso de Cloud Foundry**, **Acceso de infraestructura de {{site.data.keyword.Bluemix_notm}}**. Para obtener más información, consulte [Asignación de acceso de usuario](/docs/iam/iamuserinv.html#assignaccess).

Si determina que un usuario no necesita acceso, puede cancelar una invitación para cualquier usuario que se muestre en estado **Procesando** o **Pendiente** en la columna **Estado**. Si un usuario invitado no ha recibido una invitación, puede volver a enviar la invitación a cualquier usuario en estado **Pendiente**.

Si desea invitar a usuarios utilizando la interfaz de línea de mandatos, consulte el mandato [bluemix iam account-user-invite](/docs/cli/reference/bluemix_cli/bx_cli.html#bluemix_iam_account_user_invite).
{: tip}

## Asignación de acceso de usuario
{: #assignaccess}

Puede asignar acceso a los usuarios a medida que los invita, asignando políticas de Cloud IAM, acceso de Cloud Foundry y permisos de infraestructura. Según las opciones de acceso que esté autorizado a gestionar, puede invitar y proporcionar acceso a usuarios de la cuenta, grupos de recursos, organizaciones, espacios, instancias de servicio e infraestructuras. En las secciones siguientes se describen los tres tipos de acceso que se pueden asignar a un usuario invitado.

### Servicios

Puede asignar acceso creando una política de acceso de Cloud IAM inicial cuando invite a un nuevo usuario. En esta sección, puede proporcionar un acceso de usuario a los servicios en un grupo de recursos con acceso al grupo de recursos o a un recurso individual en la cuenta. Cuando el usuario acepte la invitación, puede asignarle acceso adicional. Consulte [Gestión del acceso IAM](/docs/iam/mngiam.html#iammanidaccser) para obtener detalles sobre la edición de políticas para añadir roles extra, asignar más acceso o eliminar una política para un usuario.

**Nota**: Dependiendo de qué servicio seleccione al asignar la política, es posible que no vea todos los campos descritos en los procedimientos siguientes.

#### Acceso a grupo de recursos

Puede asignar acceso a todos los servicios dentro de un grupo de recursos o a un único tipo de servicio en un grupo de recursos.

1. Desde la pantalla **Invitar usuarios**, expanda la sección **Servicios**.
2. Seleccione para asignar acceso a recursos en un **Grupo de recursos**.
3. Elija un grupo de recursos.
4. Elija un rol para el campo **Asignar acceso a un grupo de recursos** para permitir al usuario ver el grupo de recursos en el panel de control, editar el nombre del grupo de recursos o gestionar el acceso de usuario al grupo. Puede seleccionar **Sin acceso** si desea que el usuario solo tenga acceso al recurso que especifique y no al grupo en el que está organizado.
5. Seleccione un servicio dentro del grupo de recursos o seleccione proporcionar acceso a todos los servicios dentro del grupo seleccionado.
6. Seleccione cualquier combinación de roles para asignar el acceso deseado. Este acceso solo se aplica a los recursos que ha seleccionado para la política. No proporciona acceso al contenedor actual que es el grupo de recursos.


#### Acceso de recurso

Puede asignar acceso a un único recurso dentro de su cuenta en la instancia.

1. Desde la pantalla **Invitar usuarios**, expanda la sección **Servicios**.
2. Seleccione para asignar acceso a un **Recurso**.
3. Seleccione un servicio.
4. Seleccione **Todas las regiones actuales** o una región específica, si se le solicita.
5. Seleccione **Todas las instancias de servicio actuales** o seleccione una instancia de servicio específica.
6. En función del servicio seleccionado, puede que vea los campos siguientes. Si no indica ningún valor en ellos, la política se asigna a nivel de instancia de servicio en lugar de a nivel de grupo.
    * **Tipo de recurso**: indique **grupo**.
    * **ID de recurso**: Especifique el nombre de su grupo.
7. Seleccione cualquier combinación de roles para asignar el acceso deseado.

Para obtener información más específica sobre los roles al asignar acceso, consulte [Acceso de IAM](/docs/iam/users_roles.html#iamusermanrol).

### Acceso de Cloud Foundry

Cuando invita a nuevos usuarios, puede elegir añadirlos a una organización en la cuenta. Si añade los usuarios a una organización, puede asignar al usuario un rol de organización. A continuación, seleccione proporcionar acceso al usuario invitado a uno o a todos los espacios de la organización seleccionada con un rol de espacio asignado.

1. Desde la pantalla **Invitar usuarios**, expanda la sección **Acceso de Cloud Foundry**.
2. Seleccione una organización en la que añadir al usuario.
3. Seleccione un rol de organización para definir el nivel de acceso para la organización seleccionada.
4. Opcional: Seleccione **Añadir rol de organización** para especificar un rol extra.
5. Seleccione **Todas las regiones actuales** o una región específica.
6. Seleccione **Todos los espacios actuales** o un espacio específico.
7. Seleccione un rol de espacio para definir el nivel de acceso para los espacios seleccionados.
8. Opcional: Seleccione **Añadir rol de espacio** para especificar un rol extra.

Consulte [Roles de Cloud Foundry](/docs/iam/cfaccess.html#cfroles) para obtener más información sobre los roles.

Es posible añadir un rol de Cloud Foundry utilizando el mandato de interfaz de línea de mandatos [bluemix iam account-user-invite](/docs/cli/reference/bluemix_cli/bx_cli.html#bluemix_iam_account_user_invite), sin embargo, se debe utilizar la interfaz de usuario para asignar otros permisos o accesos.
{: tip}

### Acceso de infraestructura de {{site.data.keyword.BluSoftlayer_notm}}

Los permisos asignados se limitan automáticamente al subconjunto de permisos que posee. Para obtener más información sobre los conjuntos de permisos, consulte [Permisos de infraestructura](/docs/iam/infrastructureaccess.html#infrapermission).

1. Desde la pantalla **Invitar usuarios**, expanda la sección **Acceso de infraestructura**.
2. Seleccione un conjunto de permisos para definir el ámbito del acceso.

El acceso a dispositivos se otorga de forma separada después de añadir el usuario navegando a la opción **Infraestructura** en la consola.
{: tip}

Para obtener información sobre la configuración del acceso para los usuarios después de que hayan sido añadidos a su cuenta, consulte [Gestión de acceso a infraestructura](/docs/iam/mnginfra.html#managing-infrastructure-access).

## Adición de usuarios de solo VPN

Como propietario de la cuenta de una cuenta enlazada, puede añadir un usuario de solo VPN.

1. Pulse el icono de Menú ![Icono de menú](../icons/icon_hamburger.svg) y seleccione **Infraestructura**.
2. Vaya a **Cuenta** &gt; **Usuarios**.
3. Pulse **Añadir usuario solo VPN**.
4. Especifique los detalles de la información personal del usuario.
5. Pulse **Añadir usuario**.
6. Establezca permisos de portal para el usuario.
7. Pulse **Añadir permisos del portal** para guardar los permisos.
8. Establezca el acceso de dispositivo para el usuario.
9. Pulse **Actualizar acceso de dispositivos** para guardar y asignar el acceso.
