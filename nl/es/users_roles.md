---

copyright:

  years: 2015, 2016

lastupdated: "2017-09-29"

---

{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:screen: .screen}
{:new_window: target="_blank"}

# Permisos y roles de usuario
{: #userroles}

Puede gestionar los usuarios en los servicios de infraestructura y plataforma {{site.data.keyword.Bluemix_notm}} desde la página **Usuarios** de su cuenta. Para acceder a la página Usuarios, en el menú {{site.data.keyword.Bluemix_notm}} pulse **Gestionar** &gt; **Cuenta** &gt; **Usuarios**. Los propietarios de cuentas pueden realizar todas las operaciones para gestionar usuarios, permisos, organizaciones y espacios. Los gestores de espacios y organizaciones de Cloud Foundry también tienen acceso para gestionar permisos para usuarios añadidos a cada organización y espacio que gestionan.
{:shortdesc}

Si usted es un usuario que ha sido añadido a otra cuenta personal, y desea ver sus permisos y roles asignados, vaya a **Gestionar** &gt; **Seguridad** &gt; **Identity & Access** &gt; **Usuarios** y, a continuación, pulse en su nombre.

## Roles de cuenta
{: #userrolesinfo}

En el nivel de cuenta, hay dos roles que permiten acceder a distintas características de gestiones de cuentas:

| Rol de cuenta | Permisos |
|----------------|---------|
|Propietario | Un propietario para la cuenta tiene acceso a su perfil, usuarios, información de facturación, notificaciones de gasto y panel de control de uso. En la página de Usuarios, el propietario puede invitar a nuevos usuarios y ajustar roles. El propietario también puede añadir créditos promocionales, establecer o cambiar el límite de facturación, establecer acceso de servicios y gestionar organizaciones y espacios. |
|Miembro | Un miembro tiene acceso a su perfil, la página Usuarios visualizando los usuarios activos en la cuenta y cargos en la cuenta así como los límites de facturación en la cabecera de {{site.data.keyword.Bluemix_notm}}.  |
{:caption="Tabla 1. Permisos y roles de cuenta" caption-side="top"}

Todos los nuevos usuarios se añaden como un miembro de la cuenta. Puede asignar roles de organización y espacio a invitados para habilitar vistas y permisos específicos en {{site.data.keyword.Bluemix_notm}}. Una vez que los invitados aceptan la invitación y se unen a {{site.data.keyword.Bluemix_notm}}, puede editar sus roles en la página de Usuarios.

## Roles de Cloud Foundry
{: #cfroles}

Los roles de Cloud Foundry incluyen permisos de acceso para las organizaciones y espacios definidos dentro de la cuenta. Los roles de Cloud Foundry no habilitan permisos de usuario para completar acciones dentro del contexto de un servicio. Los siguientes roles se pueden asignar a nivel de organización:

| Rol de organización | Permisos |
|-------------------|-------------|
|Gestor | Los gestores de organización pueden crear, ver, editar o suprimir espacios dentro de la organización, ver la cuota y el uso de la organización, invitar a usuarios a la organización, gestionar quién tiene acceso a la organización y sus roles en la organización, y gestionar dominios personalizados para la organización. |
|Gestor de facturación | Los gestores de facturación pueden ver la información de uso de tiempo de ejecución y servicio para la organización de la página Panel de control de uso.  |
|Auditor | Los auditores de organización pueden ver el contenido de aplicación y servicio en la organización. Los auditores también pueden ver los usuarios de la organización y sus roles asignados, y la cuota para la organización. |
{:caption="Tabla 2. Permisos y roles de organización" caption-side="top"}

Los siguientes roles se pueden asignar a nivel de espacio:

| Rol de espacio | Permisos |
|------------|-------------|
|Gestor | Los gestores de espacios pueden añadir usuarios existentes y gestionar roles dentro del espacio. Los gestores de espacios también pueden ver el número de instancias, enlaces de servicio y uso de recursos para cada aplicación en el espacio. |
|Desarrollador | Los desarrolladores de espacios pueden crear, suprimir y gestionar aplicaciones y servicios dentro del espacio. Algunas de las tareas de gestión incluyen el desarrollo de apps, el inicio o la detención de apps, el cambio de nombre de una app, la supresión de una app, el enlace o desenlace de un servicio con una aplicación, ver el número o instancias, enlaces de servicio y uso de recursos para cada aplicación en el espacio. Además, el desarrollador de espacios puede asociar un URL interno o externo con una aplicación en el espacio.   |
|Auditor | Los auditores del espacio tienen acceso de solo lectura a toda la información sobre el espacio, como la información sobre el número de instancias, enlaces de servicio y uso de recursos para cada aplicación en el espacio. |
{:caption="Tabla 3. Permisos y roles de espacio" caption-side="top"}

**Nota**: Los usuarios que tienen asignado el rol de espacio de gestor o desarrollador pueden acceder a la variable de entorno VCAP_SERVICES. Sin embargo, un usuario que tienen asignado el rol de auditor no puede acceder a VCAP_SERVICES.

## Políticas y roles para la gestión de acceso e identidades
{: #iamusermanpol}

A los propietarios de las cuentas se les asigna de forma automática el rol de administrador de cuenta para la gestión de acceso e identidades que permite asignar y gestionar políticas de servicio. Las políticas de servicio pueden asignarse a usuarios individuales o a ID de servicio, y la política asignada puede definir el acceso a un servicio completo o en el nivel de instancia individual. 

### Políticas de servicio

Una política asigna a un usuario o ID de servicio uno o varios roles sobre un conjunto de recursos utilizando una combinación de atributos para definir el conjunto de recursos aplicable. Cuando se asigna una política a un usuario, primero hay que especificar el servicio. A continuación, se debe seleccionar el rol o los roles que desea asignar. En función del servicio que seleccione, podrían haber disponibles opciones de configuración adicionales.

Puede asignar y gestionar políticas si tiene el rol adecuado. En la tabla siguiente se muestran las tareas de gestión de políticas y el rol necesario para cada una.

| Acción | Rol necesario |
|----------|---------|
| Crear políticas en una cuenta para todos los servicios e instancias | Administrador de la cuenta |
| Crear una política en un servicio de una cuenta | Administrador de la cuenta o administrador en el servicio en la cuenta |
| Crear una instancia de servicio | Administrador de la cuenta o administrador o editor en el servicio en la cuenta |
| Crear una política en una instancia de servicio | Administrador de la cuenta o administrador en el servicio en la cuenta o administrador en la instancia de servicio |
{: caption="Tabla 4. Tareas administrativas para gestionar políticas de servicios habilitados para identidad y acceso" caption-side="top"}

### Roles de política de servicio
{: #iamusermanrol}

Los roles son una colección de acciones; las acciones que están correlacionadas con estos roles son específicas del servicio. Consulte la documentación del servicio seleccionado para obtener más información sobre los tipos de acciones que permite cada rol.

Además de las descripciones de los roles que se proporcionan en la consola, la siguiente tabla proporciona ejemplo de algunas de las tareas que los usuarios asignados a cada rol podría hacer para el servicio {{site.data.keyword.containershort_notm}}.  

| Rol | Descripción de acciones | Acciones de ejemplo|
|:-----------------|:-----------------|:-----------------|
| Visor | Realiza acciones que no cambian el estado; solo acciones de lectura | <ul><li>Listar clústeres</li><li>Ver los detalles de un clúster</li></ul>|
| Editor | Realiza acciones que modifican el estado y crean o suprimen subrecursos |<ul><li>Enlazar un servicio a un clúster</li><li>Crear un webhook</li></ul> |
| Operador | Realiza acciones necesarias para configurar y utilizar recursos. | <ul><li>Añadir o eliminar nodos trabajadores</li><li>Rearrancar o recargar nodos trabajadores</li><li>Enlazar un servicio a un clúster</li></ul> |
| Administrador | Realiza todas las acciones, incluida la capacidad para gestionar el control de accesos |<ul><li>Eliminar un clúster</li><li>Crear un clúster</li><li>Actualizar políticas de acceso de usuarios</li><li>Todas las acciones que puede realizar un visor, un editor, y un operador</li></ul>|
{: caption="Tabla 5. Roles y acciones de usuario de ejemplo" caption-side="top"}



## Permisos de infraestructura
{: #infrapermissions}

Puede establecer los siguientes permisos iniciales al invitar a un usuario:

| Conjunto de permisos | Descripción de acciones |
|---------------------------|------------------------|
|Solo visualización | Los usuarios con este permiso solo pueden ver los elementos del sistema.|
|Usuario básico | Los usuarios con este permiso pueden realizar acciones básicas en el sistema, como, por ejemplo, añadir una incidencia y gestionar dispositivos. |
|Superusuario | Los usuarios con este permiso pueden realizar todas las acciones disponibles en el sistema. |
{:caption="Tabla 6. Permisos de infraestructura" caption-side="top"}

Se pueden establecer permisos adicionales después de que el usuario haya aceptado la invitación. El permiso inicial establecido en el momento de invitación no otorga acceso a los dispositivos, por lo que debe otorgar acceso de dispositivo en el Portal de control una vez que el usuario haya aceptado la invitación.
