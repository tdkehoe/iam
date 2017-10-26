---

copyright:

  years: 2015, 2017
lastupdated: "2017-06-27"

---

{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:screen: .screen}
{:new_window: target="_blank"}

# Gestión de políticas de acceso de ID de servicio
{: #serviceidpolicy}

Al crear un ID de servicio, puede asignar políticas de servicio para dicho ID de servicio para controlar el nivel de acceso permitido cuando se utiliza para autenticarse con los servicios. Puede actualizar estas políticas de acceso asignadas en cualquier momento cambiando una política existente, suprimiendo una política o asignando una nueva. 

**Nota**: Si suprime o edita una política existente para un ID de servicio actualmente en uso, puede causar una interrupción de servicio.

## Asignación de nuevas políticas

Para asignar una nueva política:

1. Desde la barra de menús, pulse **Gestionar** &gt; **Seguridad** &gt; **Identity & Access** &gt; **ID de servicio**.
2. Seleccione el ID de servicio desde la tabla para la que desea asignar una política de servicios.
3. Pulse **Asignar políticas**.
4. Seleccione el servicio de la lista para la que desea definir permisos.
5. Opcional: Pulse **Especificar el contexto de servicio opcional**, si desea acotar la región y la instancia de servicio para la política.
6. Seleccione el rol que desea asignar.
7. Opcional: Seleccione **Añadir rol** si desea añadir roles adicionales para la política.

## Edición de políticas existentes

Para editar una política existente:

1. Desde la barra de menús, pulse **Gestionar** &gt; **Seguridad** &gt; **Identity & Access** &gt; **ID de servicio**.
2. Seleccione el ID de servicio de la tabla para la que desea editar una política de servicios.
3. Identifique la fila de la política que desea editar y seleccione **Editar política** desde el menú **Acciones**.
4. Realice los cambios y, a continuación, guarde la política.

## Supresión de políticas existentes

Para suprimir una política existente:

1. Desde la barra de menús, pulse **Gestionar** &gt; **Seguridad** &gt; **Identity & Access** &gt; **ID de servicio**.
2. Seleccione el ID de servicio de la tabla para la que desea suprimir una política de servicios.
3. Identifique la fila de la política que desea suprimir y seleccione **Eliminar política** del menú **Acciones**.
4. Realice los cambios y, a continuación, guarde la política.
