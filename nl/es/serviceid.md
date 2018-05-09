---

copyright:

  years: 2017, 2018
lastupdated: "2018-03-19"

---

{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:screen: .screen}
{:new_window: target="_blank"}

# Creación y gestión de ID de servicio
{: #serviceids}

Un ID de servicio identifica un servicio o una aplicación de forma similar a cómo un ID de usuario identifica un usuario. Un ID de servicio que cree puede utilizarse para habilitar una aplicación fuera del acceso de {{site.data.keyword.Bluemix_notm}} a sus servicios de {{site.data.keyword.Bluemix_notm}}. Puede asignar políticas de acceso específicas al ID de servicio que restrinjan permisos para utilizar servicios específicos, o incluso combinar permisos para acceder a servicios distintos. Puesto que los ID de servicio no están vinculados a un usuario específico, si un usuario abandona una organización y se suprime de la cuenta, el ID de servicio seguirá garantizando que su aplicación o servicio permanece activo y en ejecución.

Cuando se crea un ID de servicio, se crea un nombre exclusivo y una descripción que es fácil para identificar y trabajar en la IU. Una vez que haya creado el ID de servicio, puede crear claves de API específicas para cada ID de servicio que la aplicación puede utilizar para autenticarse con los servicios de {{site.data.keyword.Bluemix_notm}}. Para asegurarse de que la aplicación tenga el acceso apropiado para autenticar con los servicios de {{site.data.keyword.Bluemix_notm}}, utilice políticas de servicio asignadas a cada ID de servicio que cree.

Las políticas de acceso asociadas con un ID de servicio permiten acciones específicas que se pueden realizar cuando se utilice dicho ID de servicio para acceder a un servicio específico. Un ID de servicio único puede tener varias políticas asignadas que definen el nivel de acceso permitido cuando se accede a varios servicios habilitados para Identidad y servicios habilitados para el acceso, e incluso distintas instancias de un único servicio. Por ejemplo, tiene dos servicios con dos instancias de servicio cada uno. Por ejemplo, puede asignar el rol `Visor` para todas las instancias disponibles de un servicio y asignar el rol `Editor` sólo para una instancia de un segundo servicio. De esta forma, puede personalizar el acceso a varios servicios, pero utilizar una única clave de API para la autenticación a todos.


## Creación de un ID de servicio

Para crear un ID de servicio, vaya a **Gestionar** &gt; **Seguridad** &gt; **Identidad y acceso** y seleccione **ID de servicio** en el panel lateral. Siga el proceso para crear un nombre y una descripción para el ID de servicio. A continuación, utilice el menú **Acciones** para gestionar el ID de servicio. Puede empezar asignando una política y creando claves de API. Para obtener más información sobre cómo trabajar con las claves de API, consulte [Gestión de claves de API de ID de servicio](/docs/iam/serviceid_keys.html#serviceidapikeys). Para obtener detalles sobre los mandatos de CLI que se utilizan para gestionar un ID de servicio, consulte [Mandatos para gestionar claves de API y políticas](/docs/cli/reference/bluemix_cli/bx_cli.html#bx_commands_iam).

## Actualización de un ID de servicio

Puede actualizar un ID de servicio cambiando el nombre y la descripción en cualquier momento. También puede suprimir y crear nuevas claves de API según sea necesario o actualizar las políticas de acceso asignadas. Sin embargo, los cambios que realice en un ID de servicio existente, como por ejemplo cambiar las políticas asignadas o suprimir una clave de API que se está utilizando actualmente, podría causar interrupciones del servicio para aplicaciones que utilizan dicho ID de servicio.

## Ejemplos sobre cómo utilizar un ID de servicio

A continuación, se muestran ejemplos sobre cómo utilizar un ID de servicio con los servicios {{site.data.keyword.objectstorageshort}} y Cloud SQL Query.

- {{site.data.keyword.objectstorageshort}} - [Guía de inicio](/docs/services/cloud-object-storage/getting-started-cli.html#getting-started-cli-).
- Cloud SQL Query - [Cómo utilizar la API REST de SQL Query ![Icono de enlace externo](../icons/launch-glyph.svg)](https://www.youtube.com/embed/s6S4AdJItHk?rel=0){: new_window}.
