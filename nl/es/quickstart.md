---

copyright:

  years: 2017, 2018

lastupdated: "2018-04-02"

---

{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:screen: .screen}
{:new_window: target="_blank"}

# Guía de aprendizaje de iniciación
{: #getstarted}

Esta guía de aprendizaje está pensada para ayudarle a preparar y ejecutar rápidamente con IBM Cloud Identity and Access Management (IAM) invitando usuarios a su cuenta y asignándoles acceso de Cloud IAM.

Esta guía de aprendizaje es para recursos gestionados por IAM. Para los servicios que no soportan la creación de políticas de Cloud IAM para gestionar el acceso, puede utilizar el [Acceso de Cloud Foundry](/docs/iam/cfaccess.html#cfaccess).


## Paso 1: Invitar usuarios y asignar acceso inicial

Puede invitar a uno o varios usuarios y establecer una política de acceso inicial para los usuarios en la invitación. Si invita varios usuarios en una invitación se asigna el mismo acceso a todos ellos. En la sección Acceso de la página Invitar a usuarios solo ve las secciones que tiene permitido asignar.

Como propietario de cuenta, puede asignar roles de Cloud IAM a los usuarios que invite en la sección Servicios. Puede proporcionar acceso a todos los recursos en un grupo de recursos, a todos los recursos para un servicio específico en un grupo de recursos, a todos los servicios habilitados para identificación y acceso en la cuenta o a un único recurso en la política inicial que asigne en la invitación:

1. Vaya a **Gestionar** &gt; **Seguridad** &gt; **Identidad y acceso** y luego seleccione **Usuarios**.
2. Pulse **Invitar usuarios**.
3. Especifique la dirección de correo electrónico de los usuarios que desee invitar.
4. En la sección **Acceso**, expanda la opción **Servicios**.
5. Elija asignar acceso a un **Recurso** o a recursos dentro de un **Grupo de recursos**.
6. Dependiendo de su elección, siga las solicitudes para especificar el acceso a una instancia de servicio individual, a todos los servicios habilitados para identificación y acceso, a todos los recursos de un grupo de recursos o a un servicio específico dentro del grupo de recursos seleccionado. Si ha seleccionado la opción del grupo de recursos, también debe proporcionar el usuario con acceso para ver, editar o gestionar el acceso al grupo de recursos seleccionando un rol para acceder al grupo de recursos.
7. Si tiene permisos, también puede asignar acceso de Cloud Foundry o de infraestructura en la invitación.
8. Pulse **Invitar usuarios**.

Para obtener más información, consulte [Invitación de usuarios y asignación de acceso](/docs/iam/iamuserinv.html#iamuserinv).

## Paso 2: Crear grupos de acceso

Para racionalizar el proceso de asignación de acceso a los usuarios de su cuenta, puede crear grupos de acceso compuestos por usuarios e ID de servicio que haya seleccionado y asignar acceso fácilmente definiendo una política única para todo el grupo.

### Configurar los grupos

Para crear un grupo de acceso, complete los pasos siguientes:

1. Desde la barra de menús, pulse **Gestionar** &gt; **Seguridad** &gt; **Identidad y acceso** y luego seleccione **Grupos de acceso**.
2. Pulse **Crear**.
3. Especifique un nombre y una descripción opcional para el grupo y pulse **Crear**.

A continuación, siga configurando el grupo añadiendo usuarios o ID de servicio:

1. Seleccione el nombre del grupo al que desea añadir.
2. Pulse **Añadir usuarios**.
3. Seleccione los usuarios de la lista que desea añadir y pulse **Añadir a grupo**.
4. Para añadir ID de servicio al grupo pulse el separador **ID de servicio** y luego **Añadir ID de servicio**.
5. Seleccione los ID de la lista que desea añadir y pulse **Añadir grupo**.

### Asignar acceso a los grupos

Cuando haya creado los grupos, puede asignar acceso a todas las entidades del grupo con una política única.

1. Desde la barra de menús, pulse **Gestionar** &gt; **Seguridad** &gt; **Identidad y acceso** y luego seleccione **Grupos de acceso**.
2. Seleccione el nombre del grupo al que desea asignar el acceso.
3. Pulse **Asignar acceso** para configurar una política que asigne acceso a un único recurso de la cuenta o a todos los recursos dentro de un grupo de recursos.

Al organizar recursos en grupos de recursos y usuarios en grupos de acceso, puede asignar a un grupo de usuarios el acceso a un grupo de recursos con una política única reduciendo el número total de políticas que debe gestionar.
{: tip}


## Paso 3: Gestionar el acceso de usuarios existentes

Después de invitar usuarios, asignar el acceso inicial y crear grupos de acceso, es posible que desee asignar acceso adicional o editar el acceso inicial asignado para garantizar que todos los usuarios y grupos de su cuenta tienen el nivel de acceso deseado.

### Asignación de nuevos accesos

Puede asignar acceso a un usuario para un grupo de recursos o un único recurso.

1. Desde la barra de menús, pulse **Gestionar** &gt; **Seguridad** &gt; **Identidad y acceso** y luego seleccione **Usuarios**.
2. Pulse el nombre del usuario al que desea asignar el acceso.
3. Pulse **Asignar acceso**.
4. Elija la forma de asignar el acceso:
    * Seleccione **Asignar acceso dentro de un grupo de recursos** para asignar acceso a todos los recursos dentro de un grupo o solo a los recursos de un servicio específico dentro de un grupo. También debe proporcionar el usuario con acceso para ver, editar o gestionar el acceso al grupo de recursos seleccionando un rol para acceder al grupo de recursos. Seleccione **Sin acceso** si desea que el usuario solo tenga acceso al recurso especificado y no al grupo en el que está organizado.
    * Seleccione **Asignar acceso a recursos** para asignar acceso a todos los recursos habilitados para identificación y acceso en la cuenta, a todos los recursos de un servicio específico en la cuenta, a una única instancia o a un único recurso dentro de una instancia de servicio específica.
5. Seleccione cualquier combinación de roles para definir el ámbito del acceso. Consulte [Roles de Cloud IAM](/docs/iam/users_roles.html#iamusermanrol) para obtener más información.
6. Pulse **Asignar**.


### Edición de accesos existentes

Puede actualizar los accesos existentes editando los roles asignados a un usuario.

1. Desde la barra de menús, pulse **Gestionar** &gt; **Seguridad** &gt; **Identidad y acceso** y luego seleccione **Usuarios**.
2. Seleccione el nombre del usuario para el que desea editar el acceso.
3. En la fila de la política que desea editar, pulse **Editar política** desde el menú de **Acciones**.
4. Edite la política actualizando los roles asignados.
5. Pulse **Guardar**.

Puede eliminar el acceso de un usuario pulsando la opción **Eliminar** en el menú de **Acciones** de la política que desea eliminar.

## Pasos siguientes

Aprenda qué más puede realizar con Cloud IAM echando un vistazo a la lista de [Características de Cloud IAM](/docs/iam/index.html#features).
