---

copyright:

  years: 2015, 2017
lastupdated: "2017-10-06"

---

{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:screen: .screen}
{:new_window: target="_blank"}

# Invitación de usuarios y asignación de acceso
{: #iamuserinv}

Puede invitar a los usuarios de servicios de {{site.data.keyword.Bluemix_notm}}, aplicaciones e infraestructura de {{site.data.keyword.Bluemix_notm}} desde una sola ubicación. Para invitar a usuarios y gestionar invitaciones pendientes, debe ser propietario de cuenta o gestor de la organización o bien debe tener permisos de la infraestructura para añadir usuarios. Puede invitar a usuarios, cancelar invitaciones y volver a enviar una invitación pendiente a un usuario invitado. Puede invitar a un solo usuario o, si proporciona el mismo acceso para todos los miembros de un grupo de usuarios, puede invitar a varios usuarios a la vez.  
{:shortdesc}

## Invitación a usuarios

Complete los siguientes pasos para invitar a usuarios o para gestionar invitaciones de usuario en su cuenta: 

1. Desde la barra de menús, pulse **Gestionar** &gt; **Seguridad** &gt; **Identity & Access** &gt; **Usuarios**. La ventana Usuarios muestra una lista de los usuarios con sus direcciones de correo electrónico y el estado actual en las cuentas actualmente seleccionadas.
2. Pulse **Invitar usuarios**.
3. Especifique la dirección de correo electrónico o el IBMid del usuario. Si proporciona el mismo acceso a varios usuarios, escriba varias direcciones de correo electrónico o ID de IBM separando las entradas del ID de usuario con comas, espacios o saltos de línea.
4. Añada una o varias de las opciones de acceso que gestionará. Debe asignar al menos una opción de acceso y configurar los valores para el usuario en cada opción de acceso que asigne. Para las opciones de acceso adicionales que no desee añadir y configurar, se asigna el valor predeterminado *no access* (sin acceso). Es posible que vea una o todas las opciones de acceso siguientes, en función de las opciones que está autorizado a gestionar: **Servicios habilitados de acceso e identidad**, **Acceso de Cloud Foundry**, **Acceso de infraestructura**. Consulte [Asignación de acceso de usuario](/docs/iam/iamuserinv.html#assignaccess) para obtener más información.

Si determina que un usuario no necesita acceso, puede cancelar una invitación para cualquier usuario que se muestre en estado **Procesando** o **Pendiente** en la columna **Estado**. Si un usuario invitado no ha recibido una invitación, puede volver a enviar la invitación a cualquier usuario en estado **Pendiente**.

Si desea invitar a usuarios utilizando la interfaz de línea de mandatos, consulte el mandato [bluemix iam account-user-invite](/docs/cli/reference/bluemix_cli/bx_cli.html#bluemix_iam_account_user_invite).

## Asignación de acceso de usuario
{: #assignaccess}

Puede asignar acceso a los usuarios a medida que los invita, asignando permisos de infraestructura, políticas y roles de Cloud Foundry. Según las opciones de acceso que esté autorizado a gestionar, puede invitar y proporcionar acceso a usuarios de la cuenta, organización, espacio e instancias de servicio. En las secciones siguientes se describen los tres tipos de acceso que se pueden asignar a un usuario invitado.

### Servicios habilitados para identificación y acceso

Puede asignar una política de servicio individual cuando invite a un nuevo usuario. Una vez que el usuario ha aceptado la invitación, puede añadir políticas de servicio adicionales. Consulte [Identidad y políticas de acceso de servicio habilitadas para el acceso](/docs/iam/iamusermanage.html#iammanidaccser) para obtener detalles sobre la edición de políticas para añadir roles adicionales, la adición de políticas de servicio adicionales o la eliminación de una política para un usuario.

**Nota**: Dependiendo de qué servicio seleccione al asignar la política, es posible que no vea todos los campos descritos en el procedimiento siguiente.

1. Desde la pantalla **Invitar a usuarios**, amplíe la sección **Servicios habilitados para Identity and Access**.
2. Seleccione un servicio.
3. Seleccione **Todas las regiones actuales** o una región específica, si se le solicita. 
**Nota**: No todos los servicios requieren una selección de región.
4. Seleccione **Todas las instancias de servicio actuales** o seleccione una instancia de servicio específica.
5. En función del servicio seleccionado, puede que vea los campos siguientes. Si no indica ningún valor en ellos, la política se asigna a nivel de instancia de servicio en lugar de a nivel de grupo. 
    * **Tipo de recurso**: indique **grupo**.
    * **Recurso**: indique el nombre del grupo.
6. Seleccione un rol para definir el ámbito del acceso para la política.
7. Opcional: Seleccione **Añadir rol** para especificar un rol adicional para la política.


Consulte [Roles y políticas de gestión de acceso e identidad](/docs/iam/users_roles.html#iamusermanpol) para obtener información específica sobre los roles al establecer políticas de servicio.

### Acceso de Cloud Foundry

Cuando invita a nuevos usuarios, puede elegir añadirlos a una organización en la cuenta. Si añade los usuarios a una organización, puede asignar al usuario un rol de organización. A continuación, seleccione proporcionar acceso al usuario invitado a uno o a todos los espacios de la organización seleccionada con un rol de espacio asignado.

1. Desde la pantalla **Invitar usuarios**, expanda la sección **Acceso de Cloud Foundry**.
2. Seleccione una organización para añadirla al usuario.
3. Seleccione un rol de organización para definir el nivel de acceso a la organización seleccionada.
4. Opcional: Seleccione **Añadir rol** para especificar un rol adicional.
5. Seleccione **Todas las regiones actuales** o una región específica.
6. Seleccione **Todos los espacios actuales** o un espacio específico.
7. Seleccione un rol de espacio para definir el nivel de acceso a los espacios seleccionados.
8. Opcional: Seleccione **Añadir rol** para especificar un rol adicional.

Consulte [Roles de Cloud Foundry](/docs/iam/users_roles.html#cfroles) para obtener información más específica sobre estos roles.

**Nota**: Es posible añadir un rol de Cloud Foundry utilizando el mandato de interfaz de línea de mandatos [bluemix iam account-user-invite](/docs/cli/reference/bluemix_cli/bx_cli.html#bluemix_iam_account_user_invite), sin embargo, se debe utilizar la interfaz de usuario para asignar otros permisos o accesos.

### Acceso de infraestructura

Los permisos reales asignados se limitan automáticamente al subconjunto de permisos que posee. Para obtener más información sobre los permisos y las acciones que puede desempeñar el usuario, consulte [Permisos de infraestructura](/docs/iam/users_roles.html#infrapermissions).

1. Desde la pantalla **Invitar usuarios**, expanda la sección **Acceso de infraestructura**.
2. Seleccione un permiso para definir el ámbito del acceso.

Para obtener información sobre la configuración del acceso para los usuarios después de que hayan sido añadidos a su cuenta, consulte [Gestión de usuarios y accesos](/docs/iam/iamusermanage.html).
