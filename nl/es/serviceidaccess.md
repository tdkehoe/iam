---

copyright:

  years: 2015, 2018
lastupdated: "2018-05-02"

---

{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:screen: .screen}
{:new_window: target="_blank"}

# Gestión de políticas de acceso de ID de servicio
{: #serviceidpolicy}

Al crear un ID de servicio, puede asignar políticas de servicio para dicho ID de servicio para controlar el nivel de acceso permitido cuando se utiliza para autenticarse con los servicios. Puede actualizar estas políticas de acceso asignadas en cualquier momento cambiando una política existente, suprimiendo una política o asignando una nueva.

**Nota**: Si suprime o edita una política existente para un ID de servicio actualmente en uso, puede causar una interrupción de servicio.

## Asignación de nuevos accesos

Para asignar acceso a todos los recursos de un grupo de recursos o solo a un servicio del grupo, complete los siguientes pasos:

1. Desde la barra de menús, pulse **Gestionar** &gt; **Seguridad** &gt; **Identidad y acceso** &gt; **ID de servicio**.
2. Seleccione el ID de servicio desde la tabla para la que desea asignar una política de servicios.
3. Pulse **Asignar acceso**.
4. Seleccione **Asignar por grupo de recursos**.
5. Seleccione un grupo de recursos.
6. Seleccione un rol para el campo **Asignar acceso a un grupo de recursos**. Esta opción permite al usuario visualizar el grupo de recursos en su panel de control, editar el nombre del grupo de recursos o gestionar el acceso de usuario al grupo. Puede seleccionar **Sin acceso**, si desea que el usuario tenga acceso solo al recurso que especifica y no al grupo al que está asignado.
7. Seleccione un servicio dentro del grupo de recursos o seleccione proporcionar acceso a todos los servicios dentro del grupo seleccionado.
8. Elija cualquier combinación de roles para asignar el acceso deseado para el usuario. Este acceso solo se aplica a los recursos que ha seleccionado para la política. No proporciona acceso al contenedor actual que es el grupo de recursos.
9. Seleccione **Asignar**.

Para asignar acceso a un recurso individual en la cuenta, complete los siguientes pasos:

1. Desde la barra de menús, pulse **Gestionar** &gt; **Seguridad** &gt; **Identidad y acceso** &gt; **ID de servicio**.
2. Seleccione el ID de servicio desde la tabla para la que desea asignar una política de servicios.
3. Pulse **Asignar acceso**.
4. Seleccione **Asignar por recurso**.
5. Seleccione un servicio.
6. Seleccione **Todas las regiones actuales** o una región específica, si se le solicita.
7. Seleccione **Todas las instancias de servicio actuales** o seleccione una instancia de servicio específica.
8. En función del servicio seleccionado, puede que vea los campos siguientes. Si no indica ningún valor en ellos, la política se asigna a nivel de instancia de servicio en lugar de a nivel de grupo.
    * **Tipo de recurso**: indique **grupo**.
    * **ID de recurso**: Especifique el nombre de su grupo.
9. Elija cualquier combinación de roles para asignar el acceso deseado para el usuario.
10. Seleccione **Asignar**.



## Edición de accesos existentes

Para editar una política existente:

1. Desde la barra de menús, pulse **Gestionar** &gt; **Seguridad** &gt; **Identidad y acceso** &gt; **ID de servicio**.
2. Seleccione el ID de servicio de la tabla para la que desea editar una política de servicios.
3. Identifique la fila de la política que desea editar y seleccione **Editar política** desde el menú **Acciones**.
4. Realice los cambios y, a continuación, guarde la política.

## Eliminación de acceso

Para eliminar una política existente:

1. Desde la barra de menús, pulse **Gestionar** &gt; **Seguridad** &gt; **Identidad y acceso** &gt; **ID de servicio**.
2. Seleccione el ID de servicio de la tabla para la que desea suprimir una política de servicios.
3. Identifique la fila de la política que desea suprimir y seleccione **Eliminar** del menú **Acciones**.
4. Revise los detalles de la política que va a eliminar y luego pulse **Eliminar** para confirmar.
