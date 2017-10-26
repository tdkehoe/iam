---

copyright:

  years: 2015, 2017

lastupdated: "2017-10-03"

---

{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:screen: .screen}
{:new_window: target="_blank"}

# Gestión de usuarios y políticas de acceso
{: #iamusermanage}

Según las opciones de acceso que esté autorizado a gestionar, puede ver y gestionar usuarios de la cuenta o de la organización. Como propietario de una cuenta, puede gestionar cualquiera de las opciones de acceso que administre de los usuarios y el acceso que asignará a los mismos en la cuenta actual.
{:shortdesc}

## Gestión de usuarios

Complete los siguientes pasos para gestionar los usuarios de su cuenta:

1. Desde la barra de menús, pulse **Gestionar** &gt; **Cuenta** &gt; **Usuarios**. La ventana Usuarios muestra una lista de los usuarios con sus direcciones de correo electrónico de las cuentas actualmente seleccionadas.
2. Seleccione el nombre de usuario o pulse **Gestionar usuario** desde el menú **Acciones**.
3. A continuación, dependiendo de qué acción deba realizar, puede optar por eliminar el usuario, asignar una nueva política o gestionar el acceso existente del usuario.

Revise las siguientes secciones para obtener información adicional sobre la gestión de cada tipo de acceso.

Si necesita revisar su acceso asignado en una cuenta a la que ha sido añadido, complete los siguientes pasos:

1. Desde la barra de menús, pulse **Gestionar** &gt; **Seguridad** &gt; **Identity & Access** &gt; **Usuarios**.
2. Seleccione su nombre.
3. Revise los roles que tiene asignados.

Si necesita privilegios adicionales, debe ponerse en contacto con el gestor de la organización o el propietario de la cuenta para actualizar el rol de Cloud Foundry, o ponerse en contacto con el administrador del servicio o la instancia de servicio para actualizar la política de servicio.

Para obtener más información sobre los mandatos de la interfaz de línea de mandatos que se utilizan para gestionar cuentas, organizaciones y espacios, consulte [Mandatos para la gestión de cuentas, organizaciones y roles](/docs/cli/reference/bluemix_cli/bx_cli.html#bx_commands_acctorg).

## Acceso de Cloud Foundry
{: #iammancfser}

Para gestionar el acceso a espacios y organizaciones de la cuenta, debe ser el propietario de la cuenta, un gestor de organización o un gestor de espacio:

1. Desde la barra de menús, pulse **Gestionar** &gt; **Seguridad** &gt; **Identity & Access** &gt; **Usuarios**.
2. Seleccione el usuario al que desea editar sus roles.
3. En el menú **Acciones** en la sección de Cloud Foundry, puede:

  * Eliminar el usuario de la organización
  * Editar el rol de la organización
  * Editar el rol de espacio

También puede añadir un usuario a otra organización pulsando **Asignar organización**, si es el gestor de una organización a la que todavía no pertenezca el usuario.


## Identidad y políticas de acceso de servicio habilitadas para el acceso
{: #iammanidaccser}

Para gestionar políticas de servicio o asignar nuevas políticas de servicio a los usuarios, debe ser un administrador de cuenta local o el administrador asignado para la instancia de servicio o servicio concreto. Para obtener información sobre los roles y las políticas de servicio, consulte [Políticas y roles para la gestión de acceso e identidades](/docs/iam/users_roles.html#iamusermanpol). Para obtener detalles sobre los mandatos CLI que se utilizan para gestionar políticas, consulte [Mandatos para gestionar claves de API y políticas](/docs/cli/reference/bluemix_cli/bx_cli.html#bx_commands_iam).

### Edición de una política existente

1. Desde la barra de menús, pulse **Gestionar** &gt; **Seguridad** &gt; **Identity & Access** &gt; **Usuarios**.
2. Seleccione el usuario al que desea asignar políticas de servicios.
3. En la fila de la política que desee editar, seleccione el menú **Acciones** y pulse **Editar política**.
4. Edite la política.
5. Pulse **Guardar política**.

### Adición de una nueva política

1. Desde la barra de menús, pulse **Gestionar** &gt; **Seguridad** &gt; **Identity & Access** &gt; **Usuarios**.
2. Seleccione el usuario al que desea asignar políticas de servicios.
3. Seleccione **Asignar políticas**.
4. Seleccione un servicio.
5. Seleccione **Todas las regiones actuales** o una región específica, si se le solicita.
**Nota**: No todos los servicios requieren una selección de región.
6. Seleccione **Todas las instancias de servicio actuales** o seleccione una instancia de servicio específica.
7. Seleccione un rol para definir el ámbito del acceso para la política.
8. Opcional: Seleccione **Añadir rol** para especificar un rol adicional para la política.

### Eliminación de una política

1. Desde la barra de menús, pulse **Gestionar** &gt; **Seguridad** &gt; **Identity & Access** &gt; **Usuarios**.
2. Seleccione el usuario al que desea asignar políticas de servicios.
3. En la fila de la política que desea eliminar, seleccione el menú **Acciones** y pulse **Eliminar política**.
4. Revise los detalles de la política de usuario que está a punto de eliminar y confirme pulsando **Eliminar política**.
  

## Infraestructura de permisos de servicios

Pulse el enlace **Asignar acceso a la infraestructura** para asignar o actualizar permisos de infraestructura.

