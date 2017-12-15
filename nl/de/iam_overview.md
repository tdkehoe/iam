---

copyright:

  years: 2017

lastupdated: "2017-11-16"

---

{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:screen: .screen}
{:new_window: target="_blank"}

# IAM-Konzepte
{: #iamconcepts}

## Identität

Das Konzept der Identität in {{site.data.keyword.Bluemix_notm}} IAM basiert auf den folgenden Komponenten: 

<dl>
<dt>Benutzeridentitäten</dt>
<dd>Alle Benutzer werden durch ihre IBMid identifiziert. </dd>
<dt>Service- und App-Identitäten</dt>
<dd>Bei den Service-IDs handelt es sich um die Funktion von Cloud IAM, die zur Bereitstellung einer separaten Identität für Services und Anwendungen benutzt wird. Sie können eine Service-ID erstellen, die von einer Anwendung benutzt wird, die Zugriff auf Ihre {{site.data.keyword.Bluemix_notm}}-Services benötigt, damit die individuellen Benutzerberechtigungsnachweise nicht verwendet werden müssen. </dd>
<dt>API-Schlüssel</dt>
<dd>Die API-Schlüssel einer Plattform stehen Ihnen über Cloud IAM zur Verfügung und können zur Authentifizierung mithilfe der API oder CLI als Benutzer- oder Service-ID verwendet
werden. Diese API-Schlüssel werden über Cloud IAM bereitgestellt und können aus diesem Grund nicht allgemein für die Authentifizierung mit einer IBMid außerhalb von IBM Cloud eingesetzt werden. </dd>
<dt>Ressourcen</dt>
<dd>{{site.data.keyword.Bluemix_notm}}-Ressourcen werden durch ihre Cloud-Ressourcennamen (CRNs) identifiziert. Weitere Informationen hierzu finden Sie in [Cloudressourcennamen](/docs/iam/crn.html).</dd>
</dl>

## Zugriffsmanagement

Das Konzept des Zugriffsmanagements in {{site.data.keyword.Bluemix_notm}} basiert auf einer Reihe von Komponenten, die zueinander in Beziehung stehen. Dazu gehören Benutzer, Ressourcen, Richtlinien, Rollen, Aktionen und das Cloud IAM-Steuersystem, die es Benutzern erlauben, Aktionen für die Ressourcen innerhalb eines Kontos auszuführen.  

In der folgenden Liste erfahren Sie mehr über diese Cloud IAM-Komponenten:

<dl>
<dt>Benutzer</dt>
<dd>Alle Benutzer innerhalb eines Kontos werden mithilfe Ihrer IBMid identifiziert. Benutzer können zu dem Konto eingeladen werden und es kann ihnen Zugriff auf Ressourcen erteilt werden. Der Zugriff kann einzelnen Ressourcen (bis zur Instanzebene) oder aber einem Set von Ressourcen zugewiesen werden, die in einer Kontoressourcengruppe organisiert sind.</dd>
<dt>Ressourcen</dt>
<dd>Kontoressourcen stellen die bereitgestellten Serviceangebote dar, die aus dem Katalog oder den differenzierteren Ressourcen innerhalb einer Serviceinstanz ausgewählt werden.</dd>
<dt>Richtlinien</dt>
<dd>Richtlinien legen die Vorgehensweise fest, die bei der Erteilung von Berechtigungen für den Zugriff auf die Ressourcen eines Kontos an Benutzer oder Service-IDs angewendet wird. Richtlinien umfassen ein Subjekt, ein Ziel und eine Rolle. Das Subjekt stellt die Benutzer- oder Service-ID dar, der Sie die Zugriffsberechtigungen erteilen. Das Ziel der Richtlinie ist die Ressource, auf die Zugriff bereitgestellt werden soll. Die Rollen legen die Zugriffsebene oder die zulässigen Aktionen für das Ziel der Richtlinie fest. Es stehen drei Typen von Richtlinien zur Verfügung, die den Zugriff auf die Ressourcen eines Kontos zulassen, und zwar eine Ressourcengruppenrichtlinie, eine Ressourceninstanzrichtlinie und eine kontoweite Richtlinie für den Zugriff auf alle Services, die durch Identity and Access aktiviert wurden. Abhängig von den von Ihnen ausgewählten Optionen können angepasste Konfigurationsoptionen verfügbar sein, z. B. zum Definieren des Zugriffs bis zur Ressourcenebene in einer bestimmten Region oder zum Definieren des Zugriffs auf die differenzierte Ebene einer servicespezifischen Ressource innerhalb einer Instanz.</dd>
<dt>Rollen</dt>
<dd>Die Cloud IAM-Zugriffsrollen ermöglichen einem Benutzer die Ausführung bestimmter Tasks für die Ressource, die in der Richtlinie definiert ist. Es stehen zwei Typen von Zugriffsrollen zur Verfügung: Zugriffsrollen für das Plattformmanagement und den Servicezugriff. Die Rollen für das Plattformmanagement definieren die zulässigen Aktionen für die Verwaltung von Ressourcen auf Plattformebene einschließlich Benutzerzugriff, Erstellung von Instanzen und Service-IDs und Verwaltung der Ressourcengruppen. Die Servicezugriffsrollen definieren außerdem die zulässigen Aktionen innerhalb des Kontextes der Servicenutzung. Diese Rollen werden basierend auf dem Service angepasst, der in der Richtlinie ausgewählt wird.</dd>
<dt>Aktionen</dt>
<dd>Aktionen werden bestimmten Cloud IAM-Rollen zugeordnet. Auf diese Weise erhalten Benutzer nur dann die Möglichkeit, spezielle Tasks auszuführen, wenn ihnen die entsprechenden Rollen zugewiesen wurden. Die zulässigen Aktionen der einzelnen Rollen können sich abhängig vom Service, auf den zugegriffen wird, ändern. Dies ist darauf zurückzuführen, dass jeder Service festlegt, wie eine bestimmte Rolle der Verwendung des Service zugeordnet wird.</dd>
<dt>System für das Zugriffsmanagement</dt>
<dd>Das Cloud IAM-Steuersystem erlaubt oder verweigert die Ausführung von Aktionen durch Benutzer innerhalb des Kontextes eines Service auf Basis der zugewiesenen Richtlinie. Wenn ein Benutzer versucht, eine bestimmte Aktion auszuführen, dann verwendet das Steuersystem die Attribute, die in der Richtlinie definiert sind, um festzustellen, ob der Benutzer über die Berechtigung zur Ausführung dieser Task verfügt.</dd>
</dl>






