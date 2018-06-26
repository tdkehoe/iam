---

copyright:

  years: 2017, 2018
  
lastupdated: "2018-06-01"

---

{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:screen: .screen}
{:new_window: target="_blank"}
{:tip: .tip}

# Creación y trabajo con los ID de servicio
{: #serviceids}

Un ID de servicio identifica un servicio o una aplicación de forma similar a cómo un ID de usuario identifica un usuario. Un ID de servicio que cree puede utilizarse para habilitar una aplicación fuera del acceso de {{site.data.keyword.Bluemix_notm}} a sus servicios de {{site.data.keyword.Bluemix_notm}}. Puede asignar políticas de acceso específicas al ID de servicio que restrinjan permisos para utilizar servicios específicos, o incluso combinar permisos para acceder a servicios distintos. Puesto que los ID de servicio no están vinculados a un usuario específico, si un usuario abandona una organización y se suprime de la cuenta, el ID de servicio seguirá garantizando que su aplicación o servicio permanece activo y en ejecución.

Cuando se crea un ID de servicio, se crea un nombre exclusivo y una descripción que es fácil para identificar y trabajar en la IU. Una vez que haya creado el ID de servicio, puede crear claves de API específicas para cada ID de servicio que la aplicación puede utilizar para autenticarse con los servicios de {{site.data.keyword.Bluemix_notm}}. Para asegurarse de que la aplicación tenga el acceso apropiado para autenticar con los servicios de {{site.data.keyword.Bluemix_notm}}, utilice políticas de acceso asignadas a cada ID de servicio que cree. 

Las políticas de acceso asociadas con un ID de servicio permiten acciones específicas que se pueden realizar cuando se utilice dicho ID de servicio para acceder a un servicio específico. Un ID de servicio único puede tener asignadas varias políticas que definen el nivel de acceso permitido cuando se accede a varios servicios habilitados por Identidad y acceso. Por ejemplo, tiene dos servicios con dos instancias de servicio cada uno. Por ejemplo, puede asignar el rol `Visor` para todas las instancias disponibles de un servicio y asignar el rol `Editor` sólo para una instancia de un segundo servicio. De esta forma, puede personalizar el acceso a varios servicios, pero utilizar una única clave de API para la autenticación a todos.


## Creación de un ID de servicio

Para crear un ID de servicio, vaya a **Gestionar** &gt; **Seguridad** &gt; **Identidad y acceso** y seleccione **ID de servicio**. Siga el proceso para crear un nombre y una descripción para el ID de servicio. A continuación, utilice el menú **Acciones** para gestionar el ID de servicio. Puede empezar asignando una política y creando claves de API. Para obtener más información sobre cómo trabajar con las claves de API, consulte [Gestión de claves de API de ID de servicio](/docs/iam/serviceid_keys.html#serviceidapikeys). 

## Actualización de un ID de servicio

Puede actualizar un ID de servicio cambiando el nombre y la descripción en cualquier momento. También puede suprimir y crear nuevas claves de API según sea necesario o actualizar las políticas de acceso asignadas. Sin embargo, los cambios que realice en un ID de servicio existente, como por ejemplo cambiar las políticas asignadas o suprimir una clave de API que se está utilizando actualmente, podría causar interrupciones del servicio para aplicaciones que utilizan dicho ID de servicio.

## Bloqueo de un ID de servicio

Para evitar una situación donde su ID de servicio se suprima provocando una interrupción o alteración para los usuarios del servicio, tiene la opción de bloquear el ID de servicio mediante la IU o CLI. El bloqueo de un ID de servicio también impide que las políticas de acceso se cambien, se supriman o se asignen, así como que se creen o se supriman claves de API asociadas con el ID de servicio. Además de la capacidad de bloquear un ID de servicio, puede [bloquear claves de API individuales](/docs/iam/serviceid_keys.html#lockkey) asociadas con cada ID de servicio de la cuenta. 

Los ID de servicio bloqueados no pueden suprimirse y las políticas de acceso no se pueden actualizar. Sin embargo, los ID de servicio bloqueados todavía pueden eliminarse de cualquier grupo de acceso al que se añadan. Esto significa que cualquier acceso asignado al ID mediante su suscripción en un grupo de acceso se elimina cuando el ID de servicio se elimina del grupo de acceso.
{: tip}

### Suministro de acceso de usuario para el bloqueo de los ID de servicio

Para que un usuario tenga acceso a bloquear y desbloquear ID de servicio y claves de API asociados con los ID de servicio, deben tener asignados una política de acceso específica. Dos tipos de políticas de acceso pueden otorgar el acceso apropiado:

* Acceso a todos los ID de servicio de la cuenta
* Acceso a un ID de servicio específico de la cuenta

Para asignar acceso a todos los ID de servicio de la cuenta, establezca una política de acceso con los detalles siguientes:

* Rol de Editor o Administrador 
* Servicio de identidad IAM

Para asignar acceso a un ID de servicio específico de la cuenta, establezca una política de acceso con los detalles siguientes:

* Rol de Editor o Administrador
* Servicio de identidad IAM
* Especifique `serviceid` en el campo **Tipo de recurso** 
* Especifique el identificador del ID de servicio en el campo **ID de recurso**

Para obtener el identificador de un ID de servicio específico, vaya a **Gestionar** > **Seguridad** > **Identidad y acceso** y seleccione **ID de servicio**. Seleccione el ID de servicio para el que desea ver detalles, y copie el valor del ID.
{: tip}

### Bloqueo de un ID de servicio desde la IU

Un ID de servicio bloqueado se indica mediante el icono ![icono Bloqueado](images/locked.svg "Bloqueado").

1. Desde la barra de menús, pulse **Gestionar** &gt; **Seguridad** &gt; **Identidad y acceso** y seleccione **ID de servicio**.
2. Identifique la fila del ID de servicio que desee bloquear y seleccione **Bloquear ID de servicio** desde el menú **Acciones**.

Para desbloquear un ID de servicio, seleccione el ID de servicio desde la tabla que desee bloquear y seleccione **Desbloquear ID de servicio** desde el menú **Acciones**. Debe tener el nivel de acceso apropiado para desbloquear un ID de servicio.
{: tip}

### Bloqueo y desbloqueo de un ID de servicio utilizando la CLI

Para bloquear un ID de servicio, utilice el mandato siguiente:

```
ibmcloud iam service-id-lock (NAME|UUID) [-f, --force]
```

Opciones de mandato:

<dl>
  <dt>NAME (necesario)</dt>
  <dd>Nombre del servicio, exclusivo con UUID</dd>
  <dt>UUID (necesario)</dt>
  <dd>UUID del servicio, exclusivo con NAME</dd>
  <dt>-f, --force</dt>
  <dd>Bloquear sin confirmación</dd>
</dl>

<strong>Ejemplos</strong>:

Bloquear ID de servicio `sample-test` sin confirmación

```
ibmcloud iam service-id-lock sample-test -f
```

Bloquear ID de servicio `ServiceId-cb258cb9-8de3-4ac0-9aec-b2b2d27ac976`

```
ibmcloud iam service-id-lock ServiceId-cb258cb9-8de3-4ac0-9aec-b2b2d27ac976
```

Para desbloquear un ID de servicio, utilice el mandato siguiente:

 ```
ibmcloud iam service-id-unlock (NAME|UUID) [-f, --force]
```

Opciones de mandato:

<dl>
  <dt>NAME (necesario)</dt>
  <dd>Nombre del servicio, exclusivo con UUID</dd>
  <dt>UUID (necesario)</dt>
  <dd>UUID del servicio, exclusivo con NAME</dd>
  <dt>-f, --force</dt>
  <dd>Desbloquear sin confirmación</dd>
</dl>

<strong>Ejemplos</strong>:

Desbloquear ID de servicio `sample-test` sin confirmación

```
ibmcloud iam service-id-unlock sample-test -f
```

Desbloquear ID de servicio `ServiceId-cb258cb9-8de3-4ac0-9aec-b2b2d27ac976`

```
ibmcloud iam service-id-unlock ServiceId-cb258cb9-8de3-4ac0-9aec-b2b2d27ac976
```



## Ejemplos de cómo utilizar un ID de servicio

A continuación, se muestran ejemplos sobre cómo utilizar un ID de servicio con los servicios {{site.data.keyword.objectstorageshort}} y Cloud SQL Query.

- {{site.data.keyword.objectstorageshort}} - [Cómo empezar](/docs/services/cloud-object-storage/getting-started-cli.html#getting-started-cli-).
- Cloud SQL Query - [Cómo utilizar la API REST de SQL Query ![Icono de enlace externo](../icons/launch-glyph.svg)](https://www.youtube.com/embed/s6S4AdJItHk?rel=0){: new_window}.

