---

copyright:

  years: 2015, 2018
lastupdated: "2017-12-07"

---

{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:screen: .screen}
{:new_window: target="_blank"}

# Gestión de claves de API de ID de servicio
{: #serviceidapikeys}

Los ID de servicio se crean para permitir el acceso a los servicios de {{site.data.keyword.Bluemix_notm}} mediante aplicaciones alojadas tanto dentro como fuera de {{site.data.keyword.Bluemix_notm}}. Las claves de API las utiliza una aplicación para autenticarse como un ID de servicio particular y para que se les otorgue el acceso asociado con dicho ID de servicio.

Una vez que haya creado un ID de servicio, puede empezar a crear claves de API y a asignar políticas de servicio. Cada política especifica el nivel de acceso permitido cuando se utiliza la clave de API para autenticarse con los servicios. Para obtener más información sobre la creación de un ID de servicio y la asignación de políticas, consulte [Creación y gestión de ID de servicio](/docs/iam/serviceid.html#serviceids). Para obtener detalles sobre los mandatos de CLI que se utilizan para gestionar las claves de API de ID de servicio, consulte [Mandatos para gestionar claves de API y políticas](/docs/cli/reference/bluemix_cli/bx_cli.html#bx_commands_iam).

Cada clave de API que está asociada con un ID de servicio hereda la política que se ha asignado al ID de servicio. Por ejemplo, si desea que una aplicación pueda simplemente ver recursos dentro de un servicio, necesitará utilizar una clave de API asociada con un ID de servicio que tenga una política asignada con el rol `Visor`. Y, si desea que otra aplicación pueda tener acceso completo dentro de un servicio, necesitará utilizar una clave de API asociada con un segundo ID de servicio que tenga una política asignada con el rol `Administrador`.

## Creación de una clave de API para un ID de servicio

Crear una clave de API para asociar con un ID de servicio.

1. Vaya a **Gestionar** &gt; **Seguridad** &gt; **Identidad y acceso** &gt; **ID de servicio**.
2. Si no tiene un ID de servicio ya creado, créelo.
3. Desde el menú **Acciones**, vaya a la opción **Gestionar ID de servicio**.
4. Pulse **Crear** en la sección de claves de API.
5. Añada un nombre y una descripción para identificar de forma sencilla la clave de API.
6. Pulse **Crear**.
7. Guarde la clave de API copiándola o descargándola a una ubicación segura.

**Nota**: Por motivos de seguridad, la clave de API sólo está disponible para copiarse o descargarse en el momento de la creación. Si se pierde la clave de API, deberá crear una nueva clave de API.

## Actualización de una clave de API para un ID de servicio

Puede actualizar una clave de API editando el nombre o la descripción utilizada para identificar la clave en la IU.

1. Vaya a **Gestionar** &gt; **Seguridad** &gt; **Identidad y acceso** &gt; **ID de servicio**.
2. Si no tiene un ID de servicio ya creado, créelo.
3. Desde el menú **Acciones**, vaya a la opción **Gestionar ID de servicio**.
4. Desde el menú **Acciones** de la sección de claves de API, vaya a la opción **Editar nombre y descripción**.


## Supresión de una clave de API para un ID de servicio

Puede suprimir una clave de API que esté asociada con un ID de servicio. Sin embargo, suprimir una clave de API que está utilizando actualmente una aplicación eliminará la capacidad de dicha aplicación para autenticarse con los servicios.

1. Vaya a **Gestionar** &gt; **Seguridad** &gt; **Identidad y acceso** &gt; **ID de servicio**.
2. Si no tiene un ID de servicio ya creado, créelo.
3. Desde el menú **Acciones**, vaya a la opción **Gestionar ID de servicio**.
4. Desde el menú **Acciones** de la sección de claves de API, vaya a la opción **Suprimir clave**.
