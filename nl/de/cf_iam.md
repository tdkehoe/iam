---

copyright:

  years: 2017

lastupdated: "2017-11-16"

---

{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:screen: .screen}
{:new_window: target="_blank"}

# IAM- und Cloud Foundry-Zugriffsmodelle
{: #accessmodels}

Derzeit unterstützen nicht alle {{site.data.keyword.Bluemix_notm}}-Services die Verwendung des Cloud IAM-Zugriffsmanagements. Services, für die die Nutzung von Cloud IAM nicht aktiviert wurde, arbeiten weiterhin mit den Benutzerrollen in einer Cloud Foundry-Organisation und einem entsprechenden Bereich, um festzustellen, ob ein Benutzer über die Berechtigung für den Zugriff auf die Ressourcen verfügt. Sie können die {{site.data.keyword.Bluemix_notm}}-Benutzerschnittstelle für Identität und Zugriff verwenden, um den Zugriff für Services zu verwalten, die mit den Cloud IAM- oder Cloud Foundry-Systemen für das Zugriffsmanagement arbeiten. 


## Cloud Foundry-Services auf Cloud IAM umstellen
{: #cftoiam}

Wenn Sie momentan mit einem Cloud Foundry-Service arbeiten, der nun auch die Verwendung des Cloud IAM-Zugriffsmanagements unterstützt, dann erhalten Sie eine Benachrichtigung, in der Sie darüber informiert werden, dass Sie für neue Serviceinstanzen, die Sie erstellen, nun auch die IAM-Zugriffssteuerung verwenden können.

Wenn Services für die Nutzung von Cloud IAM aktiviert werden, dann können Sie das folgende Systemverhalten erwarten: 

* Vorhandene Instanzen in Ihrem Konto, die bereits mit dem Cloud Foundry-Zugriffsmanagement arbeiten und dabei Benutzer einer Organisation und einem Bereich mit einer Cloud Foundry-Rolle zuweisen, können weiterhin ohne Änderungen benutzt werden. 
* Bei der Erstellung neuer Instanzen müssen Sie jede der Instanzen einer Ressourcengruppe in Ihrem Konto zuweisen. Anschließend können Sie Cloud IAM verwenden, um den Zugriff auf diese Instanz und die Ressourcengruppe zu verwalten, zu der sie gehört, sofern Sie der Administrator der Ressourcengruppe sind. 

Services, die die Benutzung von Cloud IAM unterstützen, verfügen über verschiedene Vorteile einschließlich der Möglichkeit zur Herstellung von Verbindungen zu Apps und Services in einem beliebigen Cloud Foundry-Bereich. Auf diese Weise können Sie Verbindungen für Apps und Services aus unterschiedlichen Regionen herstellen. Zusätzlich hierzu gehört jede von Cloud IAM verwaltete Instanz zu einer Ressourcengruppe. Die Ressourcengruppen sind nicht regionsorientiert, sodass Sie Apps und Services aus unterschiedlichen Regionen in derselben Ressourcengruppe bereitstellen können. Außerdem verfügen Sie über die Möglichkeit, die differenzierte Zugriffssteuerung für jede einzelne Instanz zu verwenden.  

