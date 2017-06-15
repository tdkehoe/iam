---

copyright:

  years: 2015, 2017
lastupdated: "2017-05-30"

---

{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:screen: .screen}
{:new_window: target="_blank"}

# Asignación de acceso de usuario
{: #assignaccess}

Puede asignar acceso a los usuarios a medida que los invita, asignando permisos de infraestructura, políticas y roles de Cloud Foundry. Según las opciones de acceso que esté autorizado a gestionar, puede invitar y proporcionar acceso a usuarios de la cuenta, organización, espacio e instancias de servicio. En las secciones siguientes se describen los tres tipos de acceso que se pueden asignar a un usuario invitado.
{:shortdesc}

## Servicios habilitados para identificación y acceso

Puede asignar una política de servicio individual cuando invite a un nuevo usuario. Una vez que el usuario ha aceptado la invitación, puede añadir políticas de servicio adicionales.

1. Desde la pantalla **Invitar a usuarios**, amplíe la sección **Servicios habilitados para Identity and Access**.
2. Seleccione un servicio. 
3. Seleccione **Todas las regiones actuales** o una región específica.
4. Seleccione **Todas las instancias de servicio actuales** o seleccione una instancia de servicio específica.
5. Seleccione un rol para definir el ámbito del acceso para la política.
6. Opcional: Seleccione **Añadir rol** para especificar un rol adicional para la política.

Consulte [Roles y políticas de gestión de acceso e identidad](/docs/iam/users_roles.html#iamusermanpol) para obtener información específica sobre los roles al establecer políticas de servicio. 

## Acceso de Cloud Foundry

Cuando invita a nuevos usuarios, puede elegir añadirlos a una organización en la cuenta. Si añade los usuarios a una organización, de forma predeterminada, a todos ellos se les asigna un rol de organización de auditor. Puede actualizar este rol más tarde a gestor de facturación, gestor de organización o rol de no organización después de que el usuario acepte la invitación. 
Además, es posible proporcionarles el acceso de usuario invitado a uno o a todos los espacios en la organización seleccionada. 

1. Desde la pantalla **Invitar usuarios**, expanda la sección **Acceso de Cloud Foundry**.
2. Seleccione una organización para añadirla al usuario.
3. Seleccione **Todas las regiones actuales** o una región específica.
4. Seleccione **Todos los espacios actuales** o un espacio específico.
5. Seleccione un rol de espacio para definir el nivel de acceso a los espacios seleccionados. 
6. Opcional: Seleccione **Añadir rol** para especificar un rol adicional. 

Consulte [Roles de Cloud Foundry](/docs/iam/users_roles.html#cfroles) para obtener información más específica sobre estos roles.

**Nota**: Es posible añadir un rol de Cloud Foundry utilizando el mandato de interfaz de línea de mandatos [bluemix iam account-user-invite](https://console.stage1.bluemix.net/docs/cli/reference/bluemix_cli/bx_cli.html#bluemix_iam_account_user_invite), sin embargo, se debe utilizar la interfaz de usuario para asignar otros permisos o accesos. 

## Acceso de infraestructura

Los permisos reales asignados se limitan automáticamente al subconjunto de permisos que posee. Para obtener más información sobre los permisos y las acciones que puede desempeñar el usuario, consulte [Permisos de infraestructura](/docs/iam/users_roles.html#infrapermissions).

1. Desde la pantalla **Invitar usuarios**, expanda la sección **Acceso de infraestructura**. 
2. Seleccione un permiso para definir el ámbito del acceso.

Para obtener información sobre la configuración del acceso para los usuarios después de que hayan sido añadidos a su cuenta, consulte [Gestión de usuarios y accesos](/docs/iam/iamusermanage.html).
