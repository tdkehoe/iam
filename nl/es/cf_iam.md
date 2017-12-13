---

copyright:

  years: 2017

lastupdated: "2017-11-16"

---

{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:screen: .screen}
{:new_window: target="_blank"}

# Modelos de acceso IAM y Cloud Foundry
{: #accessmodels}

Actualmente, no todos los servicios de {{site.data.keyword.Bluemix_notm}} suportan el uso de la gestión de acceso de Cloud IAM. Los servicios que no han habilitado el uso de Cloud IAM continúan confiando en el rol de un usuario en una organización o espacio de Cloud Foundry para determinar si un usuario tiene permiso para acceder a los recursos. Puede utilizar la interfaz de usuario de Identidad y acceso de {{site.data.keyword.Bluemix_notm}} para gestionar el acceso para los servicios que utilizan los sistemas de gestión de acceso Cloud IAM o Cloud Foundry.


## Servicios de Cloud Foundry cambiando a Cloud IAM
{: #cftoiam}

Si actualmente está utilizando un servicio de Cloud Foundry que empieza a soportar el uso de la gestión de acceso Cloud IAM, recibirá una notificación de que ahora puede aprovechar el control de acceso con IAM para las nuevas instancias de servicio que cree.

Como los servicios empiezan a habilitar el uso de Cloud IAM, puede esperar lo siguiente:

* Para las instancias existentes en su cuenta que ya utilizan la gestión de acceso de Cloud Foundry asignando usuarios a una organización o espacio con un rol de Cloud Foundry, puede seguir utilizando estas instancias sin ningún cambio.
* Para crear nuevas instancias, asigne cada una a un grupo de recursos en su cuenta y, luego, puede utilizar Cloud IAM para gestionar el acceso a esa instancia y al grupo de recursos al que pertenece, si es administrador en el grupo de recursos.

Los servicios que soportan el uso de Cloud IAM tienen varios beneficios, incluyendo la capacidad de conectarse con apps y servicios en cualquier espacio de Cloud Foundry, que le permite conectar apps y servicios de diferentes regiones. Además, cada instancia que gestiona Cloud IAM pertenece a un grupo de recursos y los grupos de recursos no se tratan por región, por lo tanto, puede disponer de apps y servicios de diferentes regiones en el mismo grupo de recursos. También tiene la capacidad de utilizar el control de acceso preciso en una instancia individual. 

