---

copyright:

  years: 2015, 2016

lastupdated: "2017-10-06"

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

A los propietarios de las cuentas se les asigna de forma automática el rol de administrador de cuenta para Identity and access management (IAM) que permite asignar y gestionar políticas de servicio. Las políticas de servicio pueden asignarse a usuarios individuales o a ID de servicio, y la política asignada puede definir el acceso a un servicio completo o en el nivel de instancia individual.

### Políticas de servicio

Una política asigna a un usuario o ID de servicio uno o varios roles sobre un conjunto de recursos utilizando una combinación de atributos para definir el conjunto de recursos aplicable. Cuando se asigna una política, primero hay que especificar el servicio. A continuación, se debe seleccionar el rol o los roles que desea asignar. En función del servicio que seleccione, podrían haber disponibles opciones de configuración adicionales.

Puede asignar y gestionar políticas si tiene el rol adecuado. En la tabla siguiente se muestran las tareas de gestión de políticas y el rol necesario para cada una.

| Acción | Rol necesario |
|----------|---------|
| Crear políticas en una cuenta para todos los servicios e instancias | Administrador de la cuenta |
| Crear una política en un servicio de una cuenta | Administrador de la cuenta o administrador en el servicio en la cuenta |
| Crear una instancia de servicio | Administrador de la cuenta o administrador o editor en el servicio en la cuenta |
| Crear una política en una instancia de servicio | Administrador de la cuenta o administrador en el servicio en la cuenta o administrador en la instancia de servicio |
{: caption="Tabla 4. Tareas administrativas para gestionar políticas de servicios habilitados para IAM" caption-side="top"}

### Roles de política de servicio
{: #iamusermanrol}

IAM permite gestionar y definir el acceso para los usuarios y los recursos en su cuenta. Si el servicio que utiliza se puede gestionar mediante IAM para control de accesos de usuario, hay dos tipos de roles que permiten diferentes acciones en su cuenta: los roles de gestión de plataforma y los de acceso de servicio.

<dl>
<dt>Roles de gestión de plataforma</dt>
<dd>Roles disponibles para todos los servicios que se pueden gestionar mediante IAM para control de accesos de usuario, que incluyen administrador, editor, operador, visor y administrador de facturación. Estos roles están correlacionados con acciones de usuario que se pueden realizar en los recursos de {{site.data.keyword.Bluemix_notm}} a nivel de plataforma. Por ejemplo, algunas de estas acciones son la capacidad de crear instancias, conectar instancias con una aplicación, gestionar ID de servicio, gestionar usuarios y permisos y gestionar la facturación y las cuotas de la cuenta. </dd>
<dt>Roles de acceso de servicio</dt>
<dd>Estos roles son específicos de servicio. Los roles gestor, escritor y lector definen la capacidad del usuario para utilizar el servicio y realizar llamadas a las API de servicio. Puesto que cada servicio define las acciones que un usuario con un rol predeterminado puede realizar, es posible que un servicio no utilice todos los roles disponibles descritos en esta documentación. </dd>
</dl>

**Nota**: Puede que no vea todos los roles listados como opciones al asignar políticas en la IU porque solo se muestran los roles aplicables al servicio que ha seleccionado en la política. Para obtener información específica sobre qué roles están habilitados y qué acciones permite cada rol de acceso para cada servicio, consulte la documentación para dicho servicio.


#### Roles de gestión de plataforma

Los roles de gestión de plataforma permiten asignar a los usuarios distintos niveles de permiso para realizar acciones de plataforma. Además de las descripciones de los roles que se proporcionan en la consola, las siguientes tablas proporcionan ejemplos para algunas de acciones de gestión de plataforma que los usuarios asignados a cada rol podría hacer.

| Rol de gestión de plataforma  | Acciones que un usuario puede realizar en servicios de la cuenta | Acciones para ID de servicio |
|:-----------------|:--------------|:---------------|
| Visor | Ver instancias | Ver ID y claves de API |
| Operador |  Ver y enlazar instancias de servicio | No aplicable |
| Editor |  Crear, suprimir, editar, suspender, reanudar, ver y enlazar instancias de servicio | Suprimir ID y crear y suprimir claves de API |
| Administrador |  Todas las acciones de gestión para los servicios | Crear y suprimir ID y claves de API, asignar políticas a ID |
{: caption="Tabla 5. Roles y acciones de gestión de plataforma de ejemplo" caption-side="top"}

Algunos servicios pueden correlacionar acciones específicas con los roles de gestión de plataforma que están relacionados con la gestión del servicio en lugar de con el acceso al servicio. Como ejemplo, consulte en la tabla siguiente los detalles de las acciones de servicio de {{site.data.keyword.containershort_notm}} que están correlacionadas con dichos roles.


| Rol de gestión de plataforma | Descripción de acciones | Acciones de ejemplo para el servicio de {{site.data.keyword.containershort_notm}} |
|:-----------------|:-----------------|:-----------------|
| Visor | Puede ver las instancias de servicio, pero no las puede modificar  | <ul><li>Listar clústeres</li><li>Ver los detalles de un clúster</li></ul>|
| Editor | Realizar todas las acciones de plataforma excepto la gestión de la cuenta y la asignación de políticas de acceso |<ul><li>Enlazar un servicio a un clúster</li><li>Crear un webhook</li></ul> |
| Operador | Realizar acciones de plataforma necesarias para configurar y operar instancias de servicio, como la visualización de un panel de control de servicio. | <ul><li>Añadir o eliminar nodos trabajadores</li><li>Rearrancar o recargar nodos trabajadores</li><li>Enlazar un servicio a un clúster</li></ul> |
| Administrador | Realiza todas las acciones de plataforma basadas en el recurso al que se está asignando este rol, incluida la asignación de políticas de acceso a otros usuarios. |<ul><li>Eliminar un clúster</li><li>Crear un clúster</li><li>Actualizar políticas de acceso de usuarios</li><li>Todas las acciones que puede realizar un visor, un editor, y un operador</li></ul>|
{: caption="Tabla 6. Roles y acciones de gestión de plataforma de ejemplo" caption-side="top"}


#### Roles de acceso de servicio

Los roles de acceso de servicio permiten asignar a los usuarios diferentes niveles de permiso para llamar a la API del servicio. La tabla siguiente proporciona acciones de ejemplo que se pueden realizar en los roles de acceso de servicio asignados en función del uso del servicio de {{site.data.keyword.objectstorageshort}}.

**Nota**: Las acciones que se pueden llevar a cabo para cada rol asignado varían en función de servicio seleccionado para la política.

| Rol de acceso de servicio | Descripción de acciones | Acciones de ejemplo para el servicio de {{site.data.keyword.objectstorageshort}} |
|:-----------------|:-----------------|:-----------------|
|  Lector | Realizar acciones de sólo lectura dentro de un servicio como la visualización de recursos específicos del servicio | Listar y descargar objetos |
| Escritor | Los escritores tienen permisos más allá del rol de lector, incluida la creación y la edición de recursos específicos del servicio. | Crear y destruir grupos y objetos |
| Gestor | Los gestores tienen permisos más allá del rol de escritor para completar las acciones privilegiadas tal como define el servicio. Además, pueden crear y editar recursos específicos del servicio. | Gestionar todos los aspectos del almacenamiento de datos, crear y destruir grupos y objetos |
{: caption="Tabla 7. Roles y acciones de usuario de acceso de servicio de ejemplo" caption-side="top"}


## Permisos de infraestructura
{: #infrapermissions}

Puede establecer los siguientes permisos iniciales al invitar a un usuario:

| Conjunto de permisos | Descripción de acciones |
|---------------------------|------------------------|
|Solo visualización | Los usuarios con este permiso solo pueden ver los elementos del sistema.|
|Usuario básico | Los usuarios con este permiso pueden realizar acciones básicas en el sistema, como, por ejemplo, añadir una incidencia y gestionar dispositivos. |
|Superusuario | Los usuarios con este permiso pueden realizar todas las acciones disponibles en el sistema. |
{:caption="Tabla 8. Permisos de infraestructura" caption-side="top"}

Se pueden establecer permisos adicionales después de que el usuario haya aceptado la invitación. El permiso inicial establecido en el momento de invitación no otorga acceso a los dispositivos, por lo que debe otorgar acceso de dispositivo en el Portal de control una vez que el usuario haya aceptado la invitación.
