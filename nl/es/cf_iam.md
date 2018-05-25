---

copyright:

  years: 2017, 2018

lastupdated: "2018-05-02"

---

{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:screen: .screen}
{:new_window: target="_blank"}
{:tip: .tip}

# Migración de instancias de servicio de Cloud Foundry a un grupo de recursos
{: #accessmodels}

Cuando los servicios pasen de utilizar organizaciones, espacios y roles de Cloud Foundry a utilizar Cloud Identity and Access Management (IAM) y grupos de recursos, se le notifica en el panel de control. Si un servicio abandona Cloud Foundry, se le solicitará que migre las instancias de servicio existentes que pertenecen a una organización y a un espacio a un [grupo de recursos](/docs/account/resourcegroups.html#rgs). 

Cuando migre instancias de servicio de Cloud Foundry a un grupo de recursos, no podrá cambiar la asignación de grupos una vez la migración sea definitiva. Por lo tanto, debe estar seguro de cómo desea organizar los recursos de la cuenta antes de realizar la migración. Por lo tanto, es posible que necesite crear uno o varios grupos de recursos, si dispone de una cuenta de pago, antes de realizar la migración
{: tip}

## ¿Por qué migrar instancias de servicio?

Los servicios que ofrecen soporte al uso de Cloud IAM tienen varios beneficios. Entre algunos de estos beneficios se incluye la capacidad de conectarse a apps y servicios en un espacio de Cloud Foundry, lo que significa que puede conectar apps y servicios de distintas regiones. Asimismo, cada instancia gestionada por Cloud IAM pertenece a un grupo de recursos. Los grupos de recursos no se tratan por regiones, por lo que puede proporcionar apps y servicios de distintas regiones en el mismo grupo de recursos. También puede utilizar el control de acceso preciso en una instancia individual.
 

## ¿Cómo funciona la migración?

La migración a una instancia de servicio desde una organización o espacio de Cloud Foundry a un grupo de recursos crea una nueva instancia de servicio enlazada en el grupo de recursos. La instancia original de la organización y el espacio de Cloud Foundry pasa a ser un [alias](/docs/cfapps/connecting_apps.html#what_is_alias).

Puede migrar las instancias de servicio de una en una cuando se le notifique. Se le notificará en el panel de control mediante un icono asociado con la instancia de servicio de Cloud Foundry, o el mensaje en la página de detalles del servicio que puede llevarle directamente al asistente que le guía durante el proceso. Antes de migrar, decida cómo desea organizar los recursos. A continuación, puede seleccionar una instancia de servicio elegible utilizando el menú **Acciones** del panel de control y seleccionando **Migrar a un grupo de recursos**. Seleccione un grupo de recursos al que migrar la instancia durante el proceso. Cuando haya migrado una instancia correctamente, la verá reflejada en la sección Servicio del panel de control. El alias permanecerá en la sección de Cloud Foundry del panel de control. 


