---

copyright:

  years: 2015, 2017
lastupdated: "2017-10-03"

---

{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:screen: .screen}
{:new_window: target="_blank"}

# Gestión de claves de API de usuario
{: #userapikey}

Un usuario federado o no federado puede crear una clave de API para utilizarla en la CLI o como parte de la automatización para iniciar sesión con su identidad de usuario. Puede utilizar la IU de {{site.data.keyword.Bluemix_notm}} o la CLI de {{site.data.keyword.Bluemix_notm}} para gestionar sus claves de API listando sus claves, creando claves, actualizando claves o suprimiendo claves. Para gestionar las claves de API de {{site.data.keyword.Bluemix_notm}} asociadas con su identidad de usuario, vaya a **Gestionar** &gt; **Seguridad** &gt; **Claves de API de Bluemix** para ver una lista de las claves de API con descripciones y fechas. A continuación, puede crear, editar o suprimir claves de API desde esta página. Para obtener una lista completa de mandatos de CLI disponibles, consulte [Mandatos para gestionar claves de API y políticas](/docs/cli/reference/bluemix_cli/bx_cli.html#bx_commands_iam).

Como [usuario federado](/docs/admin/adminpublic.html#federatedid), se puede utilizar una clave de API para iniciar una sesión mediante la variable de entorno `BLUEMIX_API_KEY`. Para obtener más información sobre la utilización de una clave de API para iniciar una sesión, consulte la documentación del mandato [`bluemix login` de la CLI de {{site.data.keyword.Bluemix_notm}}](/docs/cli/reference/bluemix_cli/bx_cli.html#bluemix_login) y el [mandato `cf login` de la CLI de cf](/docs/cli/reference/cfcommands/index.html#cf_login).

## Creación de una clave de API

Como usuario de {{site.data.keyword.Bluemix_notm}}, podría desear utilizar una clave de API al habilitar un programa o script sin distribuir su contraseña al script. Otra ventaja en la utilización de una clave de API, es que un usuario o una organización pueden crear varias claves de API para distintos programas y que es posible suprimirlas de forma independiente si están en riesgo sin interferir con otras claves de API o incluso el usuario.

Para crear una clave de API para la identidad de usuario en la IU:

1. Vaya a **Gestionar** &gt; **Seguridad** &gt; **Claves de API de Bluemix**.
2. Pulse **Crear una clave de API**.
3. Especifique un nombre y una descripción para su clave de API.
4. Pulse **Crear una clave de API**.
5. A continuación, pulse **Mostrar** para visualizar, copiar y guardar la clave de API para más tarde, o pulse **Descargar clave de API**.

**Nota**: Por motivos de seguridad, la clave de API sólo está disponible para copiarse o descargarse en el momento de la creación. Si se pierde la clave de API, deberá crear una nueva clave de API.

Para crear una clave de API con la CLI:

1. Escriba `bluemix iam api-key-create NAME [-d DESCRIPTION] [-f, --file FILE]` en el indicador de mandatos, y especifique un nombre, una descripción y un archivo para guardar la clave. Por ejemplo:

```
bluemix iam api-key-create MyKey -d "this is my API key" -f key_file
``` 

Una vez que se cree una clave de API utilizando la CLI, hay varias maneras en que puede utilizar la clave con la CLI de bx:

* Especifíquela con el mandato `bx login`
```
 bx login --apikey <su clave de api>
```
* Cree un archivo de claves de API para utilizarlo con el mandato `bx login`: 
 ```
 bx login --apkey @apikeyfile
 ```
 El `apikeyfile` se creará utilizando la opción `—file` en el mandato `bx iam api-key-create`.
* En el indicador de mandatos, puede establecer la variable de entorno especificando `BLUEMIX_API_KEY=<your api key>` y, a continuación, especificando `bx login`.
* O, si desea evitar la CLI de bx y solo iniciar sesión en la CLI de cf utilizando la clave de API, escriba:
 ```
 cf login -u apikey -p <suclaveapi>
 ```
  En esta opción, utiliza el nombre de usuario de `apikey` y la contraseña es su `apikey`. Ahora, puede utilizar `apikey` en otras herramientas, como Eclipse, u otros lugares buscando `cf login` que solo acepta el nombre de usuario y la contraseña.

## Actualización de una clave de API

Si desea cambiar el nombre o la descripción de una clave de API, lleve a cabo los pasos siguientes en la IU o CLI.

Siga estos pasos para editar una clave de API:

1. Vaya a **Gestionar** &gt; **Seguridad** &gt; **Claves de API de Bluemix**.
2. Desde el menú **Acciones** de una clave de API que aparezca listada en la tabla, pulse **Editar nombre y descripción ** 
3. Actualice la información de su clave de API.
4. Pulse **Actualizar clave de API**.

Para editar una clave de API con la CLI:

1. Escriba `bluemix iam api-key-update NAME [-n NAME] [-d DESCRIPTION]` en el indicador de mandatos, especificando el nombre antiguo, el nombre nuevo y una descripción nueva para la clave. Por ejemplo:

```
bluemix iam api-key-update MyCurrentName -n MyNewName -d "la nueva descripción de mi clave"
```

## Supresión de una clave de API

Si está utilizando una estrategia de rotación de clave, es posible que desee suprimir una clave más antigua y sustituirla por una clave nueva.

Siga estos pasos para suprimir una clave de API: 

1. Vaya a **Gestionar** &gt; **Seguridad** &gt; **Claves de API de Bluemix**.
2. Desde el menú **Acciones** de una clave de API que aparezca en la lista en la tabla, pulse **Suprimir**.
3. A continuación, confirme la supresión pulsando **Suprimir clave**.

Para suprimir una clave de API con la CLI:
1. Especifique `bluemix iam api-key-delete NAME` en el indicador de mandatos, especificando el nombre de la clave que debería suprimirse.
