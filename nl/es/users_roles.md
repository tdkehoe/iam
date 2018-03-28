---

copyright:

  years: 2015, 2018

lastupdated: "2018-02-15"

---

{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:screen: .screen}
{:tip: .tip}
{:new_window: target="_blank"}

# Acceso de IAM
{: #userroles}

Todos los servicios organizados en un grupo de recursos en su cuenta se gestionan utilizando la Gestión de identidad y acceso de {{site.data.keyword.Bluemix_notm}} (IAM). A los propietarios de las cuentas se les asigna automáticamente el rol de administrador de la cuenta para Cloud IAM. Como propietario de la cuenta, puede asignar y gestionar el acceso de los usuarios, crear grupos de recursos, suministrar instancias de servicio y todas las otras tareas que se pueden delegar asignando roles de Cloud IAM. Puede proporcionar acceso a los usuarios e ID de servicio creando políticas que establezcan un objetivo para que el usuario o ID de servicio acceda y un rol que defina qué tipo de acceso está permitido.


## ¿Qué son las políticas de Cloud IAM y quien las puede asignar?
{: #iamusermanpol}

Puede proporcionar acceso a los usuarios e ID de servicio creando políticas que establezcan un objetivo para que el usuario o ID de servicio acceda y un rol que defina qué tipo de acceso está permitido. Una política concede a un usuario o ID de servicio uno o varios roles sobre un conjunto de recursos utilizando una combinación de atributos para definir el conjunto de recursos aplicable. Cuando se asigna una política, primero elige si establece la política para un grupo de recursos o un recurso individual. A continuación, en función de su selección inicial, puede seleccionar un servicio dentro de un grupo de recursos o una instancia única del recurso seleccionado. En función del servicio que seleccione, podría haber disponibles opciones de configuración adicionales. Por último, se debe seleccionar el rol o los roles que desea asignar. 

Puede asignar y gestionar políticas si tiene el rol adecuado. En la tabla siguiente se muestran las tareas de gestión de políticas y el rol necesario para cada una de ellos.

| Acción | Rol necesario |
|----------|---------|
| Crear una política en una cuenta para todos los servicios e instancias | Propietario de la cuenta o administrador en todos los servicios en la cuenta | 
| Crear una política en un servicio de una cuenta | Propietario de la cuenta o administrador en el servicio en la cuenta |
| Crear una política en una instancia de servicio | Propietario de la cuenta, administrador en el servicio en la cuenta, administrador en todos los servicios en el grupo de recursos relevante o administrador en la instancia de servicio |
| Crear una política para gestionar un grupo de recursos | Propietario de la cuenta o administrador de un grupo de recursos |
{: caption="Tabla 1. Usuarios que pueden crear políticas de acceso" caption-side="top"} 


## Roles de Cloud IAM
{: #iamusermanrol}

Con Cloud IAM, puede gestionar y definir el acceso para usuarios y recursos en su cuenta. Si el servicio que utiliza se puede gestionar utilizando IAM, se pueden asignar dos tipos de roles: Roles de gestión de plataforma y roles de acceso de servicio.

<dl>
<dt>Roles de gestión de plataforma</dt> 
<dd>Los roles de gestión de plataforma cubren un rango de acciones, incluyendo la capacidad de crear instancias, gestionar ID de servicio, gestionar usuarios y permisos y crear grupos de recursos. Los roles de plataforma más comunes son: Administrador, editor, operador y visor. </dd>
<dt>Roles de acceso de servicio</dt>
<dd>Los roles de acceso de servicio definen la capacidad de un usuario o servicio de realizar acciones en una instancia de servicio como acceder a la interfaz de usuario o realizar llamadas de API. Hay tres posibles roles: Gestor, escritor y lector. </dd>
</dl> 

Puede que no vea todos los roles listados como opciones cuando asigna políticas en la IU porque solo se muestran los roles disponibles para el servicio que ha seleccionado en la política. Para obtener información específica sobre qué roles están habilitados y qué acciones permite cada rol de acceso para cada servicio, consulte la documentación para dicho servicio.
{: tip}

Utilizando una combinación de estos roles en una única política de acceso, puede proporcionar acceso preciso para usuarios e ID de servicio asignando acceso en:

* Todos los recursos en la cuenta
* Todos los recursos en todos los servicios que pertenecen a un grupo de recursos individual así como la capacidad de gestionar el grupo de recursos
* Todos los recursos en un único servicio en un grupo de recursos así como la capacidad de gestionar el grupo de recursos
* Todos los recursos en un único servicio en toda la cuenta, independientemente del grupo de recursos al que estén asignados
* Recursos en una instancia individual
* Un único tipo de recurso en una instancia, por ejemplo, un grupo en una instancia de {{site.data.keyword.objectstorageshort}}

Otorgar acceso completo a la cuenta a otro usuario, con el propósito de gestionar accesos de usuario y gestionar todos los recursos de la cuenta, incluyendo la capacidad de crear grupos de recursos, definir una política que otorgue acceso al usuario a todos los recursos de la cuenta seleccionando **Todos los servicios habilitados para identidad y acceso** con el rol **Administrador** asignado. 
{: tip}

### Roles de gestión de plataforma

Los roles de gestión de plataforma permiten asignar a los usuarios distintos niveles de permiso para realizar acciones de plataforma en la cuenta. Además de las descripciones de los roles que se proporcionan en la consola, las siguientes tablas proporcionan ejemplos para algunas de acciones de gestión de plataforma que los usuarios asignados a cada rol pueden hacer. Puede consultar la documentación de cada servicio para saber cómo se aplican los roles a los usuarios en el contexto del servicio que está utilizando.

| Detalles de política de acceso  | Acciones que un usuario puede realizar en servicios de la cuenta | Acciones para ID de servicio | Acciones para acceder a grupos de recursos | Acción en recursos dentro de grupos de recursos |
|:-----------------|:--------------|:---------------|:----------------|:-----------------|
| Asignar acceso a | Uno o todos los servicios habilitados de IAM | Servicio de identidad IAM | Grupo de recursos seleccionado | Servicio seleccionado en un grupo de recursos |
| Rol Visor | Ver instancias, alias, enlaces y credenciales | Ver ID y claves de API | Ver grupo de recursos | Ver solo instancias especificadas en el grupo de recursos |
| Rol Operador |  Ver instancias y gestionar alias, enlaces y credenciales | No aplicable | No aplicable | No aplicable |
| Rol Editor |  Crear, suprimir, editar y ver instancias. Gestionar alias, enlaces y credenciales | Crear y suprimir ID y claves de API | Ver y editar el nombre de grupo de recursos | Crear, suprimir, editar, suspender, reanudar, ver y enlazar solo instancias especificadas en el grupo de recursos |
| Rol Administrador |  Todas las acciones de gestión para los servicios | Crear y suprimir ID y claves de API, asignar políticas a ID | Ver, editar y gestionar el acceso para el grupo de recursos | Todas las acciones de gestión para las instancias especificadas en el grupo de recursos |
{: caption="Tabla 2. Roles y acciones de gestión de plataforma de ejemplo" caption-side="top"}
{: #platformrolestable}

Algunos servicios pueden correlacionar acciones específicas con los roles de gestión de plataforma que están relacionados con la gestión del servicio en lugar de con el acceso al servicio. Como ejemplo, consulte en la tabla siguiente los detalles de las acciones de servicio de {{site.data.keyword.containershort_notm}} que están correlacionadas con dichos roles.


| Rol de gestión de plataforma | Descripción de acciones | Acciones de ejemplo para {{site.data.keyword.containershort_notm}} |
|:-----------------|:-----------------|:-----------------|
| Visor | Puede ver las instancias de servicio, pero no las puede modificar  | <ul><li>Listar clústeres</li><li>Ver los detalles de un clúster</li></ul>|
| Editor | Realizar todas las acciones de plataforma excepto la gestión de la cuenta y la asignación de políticas de acceso |<ul><li>Enlazar un servicio a un clúster</li><li>Crear un webhook</li></ul> |
| Operador | Realizar acciones de plataforma necesarias para configurar y operar instancias de servicio, como la visualización de un panel de control de servicio. | <ul><li>Añadir o eliminar nodos trabajadores</li><li>Rearrancar o recargar nodos trabajadores</li><li>Enlazar un servicio a un clúster</li></ul> |
| Administrador | Realiza todas las acciones de plataforma basadas en el recurso al que se está asignando este rol, incluida la asignación de políticas de acceso a otros usuarios. |<ul><li>Eliminar un clúster</li><li>Crear un clúster</li><li>Actualizar políticas de acceso de usuarios</li><li>Todas las acciones que puede realizar un visor, un editor, y un operador</li></ul>|
{: caption="Tabla 3. Roles y acciones de gestión de plataforma de ejemplo para el servicio de {{site.data.keyword.containershort_notm}}" caption-side="top"}


### Roles de acceso de servicio

Los roles de acceso de servicio permiten asignar a los usuarios diferentes niveles de permiso para llamar a la API del servicio y acceder a la IU para el servicio. La tabla siguiente proporciona acciones de ejemplo que se pueden realizar en los roles asignados en función del uso del servicio de {{site.data.keyword.objectstorageshort}}.

**Nota**: Las acciones que se pueden llevar a cabo para cada rol asignado varían en función de servicio seleccionado para la política.

| Rol de acceso de servicio | Descripción de acciones | Acciones de ejemplo para el servicio de {{site.data.keyword.objectstorageshort}} |
|:-----------------|:-----------------|:-----------------|
|  Lector | Realizar acciones de sólo lectura dentro de un servicio como la visualización de recursos específicos del servicio | Listar y descargar objetos |
| Escritor | Los escritores tienen permisos más allá del rol de lector, incluida la creación y la edición de recursos específicos del servicio. | Crear y destruir grupos y objetos |
| Gestor | Los gestores tienen permisos más allá del rol de escritor para completar las acciones privilegiadas tal como define el servicio. Además, pueden crear y editar recursos específicos del servicio. | Gestionar todos los aspectos del almacenamiento de datos, crear y destruir grupos y objetos |
{: caption="Tabla 4. Roles y acciones de usuario de acceso de servicio de ejemplo" caption-side="top"}

