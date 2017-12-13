---

copyright:

  years: 2017

lastupdated: "2017-11-16"

---

{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:screen: .screen}
{:new_window: target="_blank"}
{:tip: .tip}

# Gestión del acceso IAM
{: #iammanidaccser}

Para gestionar el acceso o asignar nuevos accesos a usuarios, debe ser el propietario de la cuenta, el administrado de todos los servicios de la cuenta o el administrador asignado para un servicio o instancia de servicio particular. Para obtener más información sobre las políticas de acceso y los roles, consulte [Acceso de IAM](/docs/iam/users_roles.html).

## Edición de accesos existentes

1. Desde la barra de menús, pulse **Gestionar** &gt; **Seguridad** &gt; **Identidad y acceso** y luego seleccione **Usuarios**.
2. Seleccione el nombre del usuario al que desea asignar el acceso.
3. En la fila de la política que desee editar, seleccione el menú **Acciones** y pulse **Editar política**.
4. Edite la política.
5. Pulse **Guardar**.

## Asignación de nuevos accesos
{: #assignaccess}

### Acceso a recursos dentro de un grupo de recursos 

Para asignar acceso a todos los recursos de un grupo de recursos o solo a un servicio del grupo, complete los siguientes pasos:

1. Desde la barra de menús, pulse **Gestionar** &gt; **Seguridad** &gt; **Identidad y acceso** y luego seleccione **Usuarios**.
2. En la fila del usuario al que desea asignar acceso, seleccione el menú **Acciones** y pulse **Asignar acceso**.
3. Seleccione **Asignar acceso dentro de un grupo de recursos**.
4. Seleccione un grupo de recursos.
5. Elija un rol para el campo **Asignar acceso a un grupo de recursos** para permitir al usuario ver el grupo de recursos en su panel de control, editar el nombre del grupo de recursos o gestionar el acceso de usuario al grupo. Puede seleccionar **Sin acceso** si desea que el usuario solo tenga acceso a los recursos que especifique y no al grupo en el que están organizados.
6. Seleccione un servicio dentro del grupo de recursos o seleccione proporcionar acceso a todos los servicios dentro del grupo seleccionado.
7. Elija cualquier combinación de roles para asignar el acceso deseado para el usuario. Este acceso solo se aplica a los recursos que ha seleccionado para la política. No proporciona acceso al contenedor actual que es el grupo de recursos.
8. Pulse **Asignar**.

### Acceso a recursos
{: #resourceaccess}

Para asignar acceso a un recurso individual en la cuenta o acceso a todos los recursos de la cuenta, complete los siguientes pasos: 

1. Desde la barra de menús, pulse **Gestionar** &gt; **Seguridad** &gt; **Identidad y acceso** y luego seleccione **Usuarios**.
2. En la fila del usuario al que desea asignar acceso, seleccione el menú **Acciones** y pulse **Asignar acceso**.
3. Seleccione **Asignar acceso a recursos**.
4. Seleccione un servicio o seleccione **Todos los servicios habilitados para identidad y acceso**.
5. Seleccione **Todas las regiones actuales** o una región específica, si se le solicita. 
6. Seleccione **Todas las instancias de servicio actuales** o seleccione una instancia de servicio específica.
7. En función del servicio seleccionado, puede que vea los campos siguientes. Si no indica ningún valor en ellos, la política se asigna a nivel de instancia de servicio en lugar de a nivel de grupo. 
    * **Tipo de recurso**: indique **grupo**.
    * **ID de recurso**: Especifique el nombre de su grupo.
8. Elija cualquier combinación de roles para asignar el acceso deseado para el usuario.
9. Pulse **Asignar**.

Para permitir que un usuario acceda a todos los recursos de cuenta con la capacidad de gestionar el acceso de usuario, crear grupos de recursos y completar todas las otras tareas de gestión de IAM, seleccione la opción **Todos los servicios habilitados para identidad y acceso** para esta política con el rol **Administrador** asignado.
{: tip}


## Eliminación de acceso

1. Desde la barra de menús, pulse **Gestionar** &gt; **Seguridad** &gt; **Identidad y acceso** y luego seleccione **Usuarios**.
2. Seleccione el nombre de usuario al que desea eliminar el acceso.
3. En la fila de la política que desea eliminar, seleccione el menú **Acciones** y pulse **Eliminar**.
4. Revise los detalles de la política de usuario que está a punto de eliminar y confirme pulsando **Eliminar**.

## Revisión de su acceso asignado

Si necesita revisar su acceso asignado en una cuenta a la que ha sido añadido, complete los siguientes pasos:

1. Desde la barra de menús, pulse **Gestionar** &gt; **Seguridad** &gt; **Identidad y acceso** y luego seleccione **Usuarios**.
2. Seleccione su nombre.
3. Revise su acceso asignado en la sección **Políticas de acceso**.

Si necesita más acceso, debe ponerse en contacto con el propietario de la cuenta para actualizar su acceso o con el administrador del servicio o la instancia de servicio para que actualice la política de acceso de Cloud IAM.
