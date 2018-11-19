---



copyright:

  years: 2018

lastupdated: "2018-10-30"



---

{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:screen: .screen}
{:new_window: target="_blank"}
{:tip: .tip}

# Preguntas más frecuentes
{: #iamfaq}

## ¿Qué es {{site.data.keyword.cloud_notm}} Identity and Access Management? 
{: #whatisiam}

Identity and Access Management (IAM) le permite autenticar usuarios de forma segura para servicios de la plataforma y controlar el acceso a los recursos de la plataforma {{site.data.keyword.cloud_notm}}. Se ha habilitado un conjunto de servicios de IBM Cloud para que utilicen Cloud IAM para el control de accesos. Están organizados en grupos de recursos dentro de su cuenta para que pueda otorgar a los usuarios acceso rápido y sencillo a más de un recurso a la vez. Las políticas de acceso de Cloud IAM se utilizan para asignar accesos de usuario e ID de servicio a los recursos de su cuenta. Para obtener más información, consulte [{{site.data.keyword.cloud_notm}} Identity and Access Management](/docs/iam/index.html#iamoverview).

## ¿Qué es un servicio habilitado para IAM?
{: #iam-enabled}

Un servicio habilitado para IAM debe estar en un grupo de recursos y el acceso al servicio se proporciona mediante las políticas de acceso de IAM. Cuando cree un servicio habilitado para IAM desde el catálogo, debe asignarlo a un grupo de recursos. Para obtener más información, consulte [¿Qué es un recurso?](/docs/resources/acct_resources.html#resource)

{{site.data.keyword.containerlong_notm}} es la única excepción; el acceso se controla mediante IAM, pero siempre se asigna al grupo de recursos predeterminado. Por lo tanto, no tiene la opción de elegir uno cuando lo crea desde el catálogo. Y no se puede asignar a ningún otro grupo de recursos


## ¿Están relacionados IAM y Cloud Foundry?
{: #iam-cloudfoundry}

No están relacionados. Cloud Foundry es una plataforma de código abierto que utiliza organizaciones, espacios y roles de Cloud Foundry para la gestión de accesos. IAM constituye el método seguro de autenticar usuarios para servicios de la plataforma y para controlar el acceso a los recursos en la plataforma {{site.data.keyword.cloud_notm}} utilizando grupos de recursos y roles de acceso de IAM.

Los sistemas de gestión de accesos son totalmente diferentes. Los recursos de IAM pertenecen a un grupo de recursos y los recursos de Cloud Foundry pertenecen a una organización y un espacio. Las políticas de acceso de IAM se utilizan para proporcionar acceso a los recursos de un grupo de recursos. Y los roles de organización y de espacio de Cloud Foundry se utilizan para proporcionar a los usuarios acceso a los recursos de Cloud Foundry en un espacio. IAM no le da acceso a nada dentro de los espacios de Cloud Foundry, y los roles de Cloud Foundry no pueden otorgar acceso a recursos dentro de un grupo de recursos.

## ¿Cómo puedo averiguar a qué tengo acceso?
{: #iam-access}

Vaya a **Gestionar** &gt; **Acceso (IAM)** y seleccione el nombre en la columna Usuario. Luego, en función del acceso que busque, abra los distintos separadores:

* Para determinar los grupos de acceso en los que se encuentra, seleccione **Grupos de acceso**.
* Para acceso de IAM, seleccione **Políticas de acceso**.
* Para roles de Cloud Foundry, seleccione **Acceso de Cloud Foundry**.

## ¿Cómo puedo solicitar acceso a un recurso?
{: #request-access}

El propietario de la cuenta puede actualizar su acceso a cualquier recurso de la cuenta, o bien puede ponerse en contacto con cualquier usuario que tenga asignado el rol de administrador sobre el servicio o la instancia de servicio. 

## ¿Por qué debo utilizar grupos de recursos y grupos de acceso? 
{: #resource-groups}

Un grupo de recursos es un contenedor lógico para los recursos. Cuando se crea un recurso, se asigna a un grupo de recursos y no se puede mover después de que se añada. 

Un grupo de acceso se utiliza para organizar fácilmente un conjunto de usuarios e ID de servicio en una sola entidad para facilitar las asignaciones de acceso. Puede asignar una única política a un grupo de acceso para otorgar dichos permisos a todos los miembros. Si tiene más de un usuario o ID de servicio que necesita el mismo acceso, cree un grupo de acceso en lugar de asignar el mismo acceso varias veces por usuario o ID de servicio individual.

Mediante el uso de grupos de recursos y de grupos de acceso, puede agilizar la política de asignación de acceso al asignar un número limitado de políticas. Puede organizar todos los recursos a los que debe acceder un grupo específico de usuarios y de ID de servicio en un solo grupo de recursos, agrupar todos los usuarios o ID de servicio en un grupo de acceso y luego asignar una única política que dé acceso a todos los recursos en el grupo de recursos.

## ¿Cómo puedo asegurarme de que mis usuarios pueden crear recursos dentro de un grupo de recursos?
{: #resources}

Para crear un recurso en un grupo de recursos, el usuario debe tener dos políticas de acceso: una asignada al propio grupo de recursos y una asignada a los recursos del grupo. El acceso al propio grupo de recursos es simplemente el acceso al contenedor que organiza los recursos, y este tipo de política permite a un usuario ver, editar o gestionar el acceso al grupo, pero no los recursos contenidos en el mismo. El acceso a los servicios contenidos en el grupo de recursos permite a un usuario trabajar con las instancias de servicio, lo que significa que el usuario puede crear una instancia de servicio.

Por lo tanto, como mínimo el usuario debe tener el siguiente acceso:

* Rol de visor o superior sobre el propio grupo de recursos
* Rol de editor o superior sobre el servicio o sobre todos los servicios del grupo de recursos


## ¿Qué acceso necesito para proporcionar acceso a otros usuarios?
{: #user-access}

Debe tener el rol de administrador sobre el servicio o recurso al que desea asignar acceso a los usuarios. Si desea asignar acceso a todos los servicios o recursos de la cuenta, necesita una política sobre todos los servicios habilitados para Identity and Access con el rol de administrador. 

## ¿Qué diferencia hay entre proporcionar acceso para gestionar un grupo de recursos y proporcionar acceso a los recursos contenidos en un grupo de recursos?
{: #providing-access}

Si tiene acceso para gestionar un grupo de recursos, puede ver, editar el nombre y gestionar el acceso para el propio grupo de recursos, en función del rol asignado. El acceso a un grupo de recursos en sí no da al usuario acceso a los recursos contenidos en el grupo.

Si tiene acceso a los recursos contenidos en un grupo de recursos, puede editar, suprimir y crear instancias, o bien puede tener acceso a todas las acciones de gestión para los servicios especificados dentro del grupo de recursos, en función del rol asignado. 

Para ver acciones y roles de gestión de plataforma de ejemplo para servicios de gestión de cuentas, consulte la [Tabla de roles de plataforma](/docs/iam/users_roles.html#platformrolestable2).

## ¿Quién puede eliminar usuarios?
{: #remove-users}

El propietario de la cuenta siempre puede añadir y eliminar usuarios. Además, cualquier usuario con los dos tipos de política siguientes puede eliminar usuarios:

* Editor o administrador sobre todos los servicios de gestión de cuentas
* Editor o administrador sobre el servicio de gestión de cuentas de gestión de usuarios

## ¿Cómo se activa la autenticación de varios factores?
{: #multi-factor}

Vaya a **Gestionar** &gt; **Acceso (IAM)** y elija **Configuración**. 
Seleccione **Autenticación de multifactores** y luego pulse **Aplicar cambios**. Para obtener más información, consulte [Habilitación de la autenticación de multifactores](/docs/iam/mfa.html#enablemfa).

## ¿Qué diferencia hay entre los roles de servicio y de plataforma? 
{: #service-platform-roles}

Los roles de servicio y de plataforma son dos tipos distintos de roles: 

* Los roles de plataforma están relacionados con la forma en que trabaja con un servicio dentro de una cuenta, como por ejemplo crear instancias, enlazar instancias y gestionar el acceso de usuario al servicio. Para los servicios de plataforma, estos roles permiten a los usuarios crear grupos de recursos y gestionar los ID de servicio, por ejemplo. Los roles de plataforma son: administrador, editor, operador y visor. 

* Los roles de servicio definen la capacidad de realizar acciones sobre un servicio y son específicos de cada servicio, como por ejemplo realizar llamadas de API o acceder a la interfaz de usuario. Los roles de servicio son: gestor, escritor y lector. Para obtener más información sobre cómo se aplican estos roles, consulte la documentación del servicio específico.

## ¿Qué diferencia hay entre un grupo de recursos y las organizaciones y los espacios de Cloud Foundry?
{: #groups-organizations}

Al comienzo de {{site.data.keyword.Bluemix_notm}}, un servicio de plataforma de código abierto para el control de accesos y la organización de recursos denominado Cloud Foundry era el único método para organizar y controlar el acceso a los recursos. A medida que {{site.data.keyword.Bluemix_notm}} se fue ampliando, surgió la necesidad de disponer de un nuevo método que pudieran utilizar todos los tipos de servicios y recursos. Ahora se utilizan grupos de recursos para agrupar y organizar muchos tipos de recursos, y se utiliza IAM para controlar de forma coherente el acceso a los servicios y recursos. Varios servicios ya han adoptado el uso de grupos de recursos y de IAM, y otros servicios pasarán con el tiempo a utilizar el nuevo método para organizar recursos y gestionar el acceso.

El control de accesos y la organización de los recursos de la cuenta son las principales diferencias entre los grupos de recursos y las organizaciones y espacios de Cloud Foundry. Los grupos de recursos organizan los servicios habilitados para IAM en una cuenta cuyo acceso se controla mediante políticas de IAM. Las organizaciones y los espacios se gestionan utilizando roles de Cloud Foundry para el control de accesos y se asignan recursos de Cloud Foundry a espacios. Las organizaciones y los espacios se pueden utilizar para organizar y controlar el acceso a los recursos solo dentro del dominio de Cloud Foundry, mientras que los grupos de recursos e IAM se pueden utilizar para varios tipos de recursos en {{site.data.keyword.Bluemix_notm}}.

## ¿Cómo designo un usuario como administrador de la cuenta? 
{: #account-administrator}

Para delegar el rol de administrador de la cuenta mediante políticas de IAM, debe crear dos políticas:

* Administrador sobre todos los servicios habilitados para Identity and Access, lo que permite a un usuario crear instancias de servicio y asignar a los usuarios acceso a todos los recursos de la cuenta
* Administrador sobre todos los servicios de gestión de cuentas, lo que permite a un usuario realizar tareas como invitar y eliminar usuarios, gestionar grupos de acceso, gestionar ID de servicio, gestionar ofertas de catálogo privadas y realizar un seguimiento de la facturación y del uso.
