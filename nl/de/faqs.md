---



copyright:

  years: 2018

lastupdated: "2018-10-17"



---

{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:screen: .screen}
{:new_window: target="_blank"}
{:tip: .tip}

# Häufig gestellte Fragen (FAQs)
{: #iamfaq}

## Was ist das Identitäts- und Zugriffsmanagement von {{site.data.keyword.cloud_notm}}? 
{: #whatisiam}

IAM (Identity and Access Management, Identitäts- und Zugriffsmanagement) ermöglicht Ihnen, Benutzer sicher für Plattformservices zu authentifizieren und den Zugriff auf Ressourcen innerhalb der {{site.data.keyword.cloud_notm}}-Plattform zu steuern. Eine Reihe von IBM Cloud-Services kann Cloud IAM für die Zugriffssteuerung verwenden. Diese Services sind in Ressourcengruppen innerhalb Ihres Kontos organisiert, um Benutzern einen schnellen und bequemen Zugriff auf mehrere Ressourcen gleichzeitig zu ermöglichen. Die Cloud IAM-Zugriffsrichtlinien werden verwendet, um Benutzern und Service-IDs die Zugriffsberechtigungen für die Ressourcen innerhalb Ihres Kontos zuzuweisen. Weitere Informationen finden Sie in [{{site.data.keyword.cloud_notm}} Identity and Access Management](/docs/iam/index.html#iamoverview).

## Was ist ein IAM-fähiger Service?
{: #iam-enabled}

Ein IAM-fähiger Service muss in einer Ressourcengruppe enthalten sein und der Zugriff auf den Service erfolgt über die Verwendung von IAM-Zugriffsrichtlinien. Wenn Sie einen IAM-fähigen Service aus dem Katalog erstellen, müssen Sie ihn einer Ressourcengruppe zuordnen. Weitere Informationen finden Sie in [Was ist eine Ressource?](/docs/resources/acct_resources.html#resource)

{{site.data.keyword.containerlong_notm}} ist die einzige Ausnahme. Der Zugriff wird über IAM gesteuert aber die Zuordnung zur Standardressourcengruppe ist immer gegeben. Daher können Sie bei der Erstellung aus dem Katalog keine Ressourcengruppe auswählen. Die Zuordnung zu einer beliebigen anderen Ressourcengruppe ist nicht möglich. 


## Sind IAM und Cloud Foundry verwandt?
{: #iam-cloudfoundry}

Sie sind nicht verwandt. Cloud Foundry ist eine Open-Source-Plattform, die Organisationen, Bereiche und Cloud-Foundry-Rollen für den Zugriff auf die Verwaltung verwendet. IAM ist die sichere Methode, Benutzer für Plattformservices zu authentifizieren und den Zugriff auf Ressourcen über die {{site.data.keyword.cloud_notm}}-Plattform zu steuern, indem Ressourcengruppen und IAM-Zugriffsrollen verwendet werden.

Die Systeme für das Zugriffsmanagement sind völlig unterschiedlich. IAM-Ressourcen gehören zu einer Ressourcengruppe, und Cloud Foundry-Ressourcen gehören zu einer Organisation und einem Bereich. IAM-Zugriffsrichtlinien werden verwendet, um Zugriff auf Ressourcen in einer Ressourcengruppe bereitzustellen. Darüber hinaus, werden Cloud Foundry-Organisations- und Bereichsrollen verwendet, um in einem Bereich Benutzerzugriff auf Cloud Foundry-Ressourcen zu bieten. IAM bietet keinen Zugriff auf Elemente in Cloud Foundry-Bereichen und Cloud Foundry-Rollen können keinen Zugriff auf Ressourcen in einer Ressourcengruppe gewähren. 

## Wie stelle ich fest, worauf ich Zugriff haben? 
{: #iam-access}

Wechseln Sie zu **Verwalten** &gt; **Zugriff (IAM)** und wählen Sie Ihren Namen in der Spalte mit den Benutzern aus. Öffnen Sie dann abhängig von dem Zugriff, nach dem Sie suchen, die verschiedenen Registerkarten. 

* Um festzustellen, in welchen Zugriffsgruppen Sie sich befinden, wählen Sie **Zugriffsgruppe** aus.
* Für einen IAM-Zugriff wählen Sie **Zugriffsrichtlinien** aus.
* Für Cloud Foundry-Rollen wählen Sie **Cloud Foundry-Zugriff** aus.

## Wie fordere ich Zugriff auf eine Ressource an?
{: #request-access}

Der Kontoeigner kann Ihren Zugriff auf eine beliebige Ressource im Konto aktualisieren oder Sie können einen beliebigen Benutzer kontaktieren, der die Administratorrolle für den Service oder die Serviceinstanz innehat.  

## Warum soll ich Ressourcengruppen und Zugriffsgruppen verwenden?  
{: #resource-groups}

Eine Ressourcengruppe ist ein logischer Container für Ressourcen. Wenn eine Ressource erstellt wird, wird sie einer Ressourcengruppe zugeordnet und kann nicht verschoben werden, nachdem sie hinzugefügt wurde. 

Eine Zugriffsgruppe wird verwendet, um eine Gruppe von Benutzern und Service-IDs ohne großen Aufwand in einer einzigen Entität zu organisieren, um so Zuordnungen zu vereinfachen. Sie können einer Zugriffsgruppe eine einzige Richtlinie zuordnen, um allen Mitgliedern diese Berechtigungen zu erteilen. Wenn Sie mehr als einen Benutzer oder mehr als eine Service-ID haben, die denselben Zugriff benötigen, erstellen Sie eine Zugriffsgruppe, anstatt denselben Zugriff mehrmals für den einzelnen Benutzer oder die einzelne Service-ID zuzuweisen. 

Durch die Verwendung sowohl von Ressourcengruppen als auch von Zugriffsgruppen können Sie die Zugriffszuordnungsrichtlinie optimieren, indem Sie eine begrenzte Anzahl von Richtlinien zuordnen. Sie können alle Ressourcen, auf die eine bestimmte Gruppe von Benutzern und Service-IDs Zugriff benötigt, in einer einzigen Ressourcengruppe organisieren, alle Benutzer oder Service-IDs in einer Zugriffsgruppe gruppieren und dann eine einzige Richtlinie zuordnen, die Zugriff auf alle Ressourcen in der Ressourcengruppe gewährt. 

## Wie stelle ich sicher, dass meine Benutzer Ressourcen in einer Ressourcengruppe erstellen können?
{: #resources}

Um eine Ressource in einer Ressourcengruppe zu erstellen, muss der Benutzer über zwei Zugriffsrichtlinien verfügen: Eine Richtlinie, die der Ressourcengruppe selbst zugeordnet ist, und eine Richtlinie, die den Ressourcen in der Gruppe zugeordnet ist. Der Zugriff auf die Ressourcengruppe selbst ist einfach ein Zugriff auf den Container,  der die Ressourcen verwaltet. Diese Art von Richtlinie erlaubt einem Benutzer, den Zugriff auf die Gruppe anzuzeigen, zu bearbeiten oder zu verwalten. Sie erlaubt jedoch  keinen Zugriff auf die Ressourcen innerhalb der Gruppe. Der Zugriff auf Services innerhalb der Ressourcengruppe ermöglicht einem Benutzer die Arbeit mit den Serviceinstanzen. Das heißt, der Benutzer kann eine Serviceinstanz erstellen. 

Der Benutzer muss also mindestens über folgende Zugriffsrechte verfügen:

* Anzeigeberechtigten-Rolle oder höher für die Ressourcengruppe selbst
* Bearbeiterrolle oder höher für den Service oder für alle Services in der Ressourcengruppe


## Welchen Zugriff brauche ich, um anderen Zugriff zu ermöglichen?
{: #user-access}

Sie müssen die Administratorrolle für den Service oder die Ressource innehaben, zu dem bzw. der Sie Benutzern Zugriff gewähren möchten. Wenn Sie den Zugriff auf alle Services oder Ressourcen im Account zuordnen möchten, benötigen Sie eine Richtlinie für alle IAM-fähigen Services mit der Administratorrolle.  

## Was ist der Unterschied zwischen der Bereitstellung eines Zugriffs zur Verwaltung einer Ressourcengruppe und dem Zugriff auf Ressourcen innerhalb einer Ressourcengruppe? 
{: #providing-access}

Wenn Sie über Zugriff zur Verwaltung einer Ressourcengruppe verfügen, können Sie den Namen anzeigen und bearbeiten und den Zugriff auf die Ressourcengruppe selbst abhängig von der zugeordneten Rolle verwalten. Der Zugriff auf die Ressourcengruppe selbst bedeutet nicht, dass der Benutzer Zugriff auf die Ressourcen innerhalb der Ressourcengruppe hat. 

Wenn Sie über Zugriff auf die Ressourcen innerhalb einer Ressourcengruppe haben, können Sie Instanzen bearbeiten, löschen und erstellen oder abhängig von der zugeordneten Rolle über alle Verwaltungsaktionen für die angegebenen Services innerhalb der Ressourcengruppe verfügen.  

Informationen zu Plattformmanagementrollen und Aktionen für die Account-Management-Services finden Sie zum Beispiel in den Tabellen der Plattformrollen unter [Platform roles table](/docs/iam/users_roles.html#platformrolestable2).

## Wer kann Benutzer entfernen?
{: #remove-users}

Nur der Kontoeigner kann Benutzer entfernen.  

## Wie schalte ich die Mehrfaktorauthentifizierung ein? 
{: #multi-factor}

Wechseln Sie zu **Verwalten** &gt; **Zugriff (IAM)** und wählen Sie **Einstellungen** aus.
Wählen Sie **Mehrfaktorauthentifizierung** aus, und klicken Sie anschließend auf **Änderungen anwenden**. Weitere Informationen hierzu finden Sie im Abschnitt [Mehrfaktorauthentifizierung aktivieren](/docs/iam/mfa.html#enablemfa).

## Was ist der Unterschied zwischen Service- und Plattformrollen? 
{: #service-platform-roles}

Service- und Plattformrollen sind zwei verschiedene Typen von Rollen: 

* Plattformrollen sind die Art und Weise, wie Sie mit einem Service in einem Konto arbeiten, z. B. Instanzen erstellen, Instanzen binden und den Benutzerzugriff auf den Service verwalten. Für Plattformservices ermöglichen diese Rollen den Benutzern beispielsweise, Ressourcengruppen zu erstellen und Service-IDs zu verwalten. Plattformrollen sind: Administrator, Editor (Bearbeiter), Operator (Bediener) und Viewer (Anzeigeberechtigter).  

* Servicerollen definieren die Möglichkeit, Aktionen für einen Service auszuführen und sind für jeden Service spezifisch. Zu den Aktionen zählen das Ausführen von API-Aufrufen oder das Zugreifen auf die Benutzerschnittstelle. Servicerollen sind: Manager, Schreibberechtigter (Writer) und Leseberechtigter (Reader). Weitere Informationen darüber, wie diese Rollen angewendet werden, finden Sie in der Dokumentation des jeweiligen Service.

## Was ist der Unterschied zwischen einer Ressourcengruppe und Cloud Foundry-Organisationen und -Bereichen?
{: #groups-organizations}

Am Anfang von {{site.data.keyword.Bluemix_notm}} war der Open-Source-Plattform-Service für die Zugriffssteuerung und die Organisation von Ressourcen Cloud Foundry die einzige Methode für die Organisierung und Steuerung des Zugriffs auf Ressourcen. Mit der Erweiterung von {{site.data.keyword.Bluemix_notm}} wurde eine neue Methode erforderlich, die von allen Service- und Ressourcentypen verwendet werden kann. Ressourcengruppen werden jetzt verwendet, um viele Typen von Ressourcen zu gruppieren und zu organisieren. IAM wird verwendet, um den Zugriff auf Services und Ressourcen konsistent zu steuern. Eine Reihe von Services sind bereits dazu übergegangen, Ressourcengruppen und IAM zu verwenden. Weitere Services werden im Laufe der Zeit diese neue Methode der Ressourcenorganisation und Zugriffsverwaltung verwenden. 

Die Zugriffssteuerung und die Ressourcenorganisation des Kontos sind die wesentlichen Unterschiede zwischen Ressourcengruppen und Cloud Foundry-Organisationen und -Bereichen. Ressourcengruppen organisieren IAM-fähige Services in einem Konto, dessen Zugriffssteuerung über IAM-Richtlinien erfolgt. Die Zugriffssteuerung für Organisationen und Bereiche erfolgt über Cloud Foundry-Rollen und Cloud Foundry-Ressourcen werden Bereichen zugeordnet. Organisationen und Bereiche können verwendet werden, um Ressourcen innerhalb eines Cloud Foundry-Bereichs zu organisieren und den Zugriff auf sie zu steuern, während Ressourcengruppen und IAM für mehrere Ressourcentypen in {{site.data.keyword.Bluemix_notm}} verwendet werden können.

