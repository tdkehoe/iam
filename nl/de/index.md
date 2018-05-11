---

copyright:

  years: 2017, 2018

lastupdated: "2018-04-05"

---

{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:screen: .screen}
{:new_window: target="_blank"}

# {{site.data.keyword.Bluemix_notm}} Identity and Access Management
{: #iamoverview}

## Was ist Cloud IAM?

{{site.data.keyword.Bluemix_notm}} Identity and Access Management (IAM) ermöglicht Ihnen die sichere Authentifizierung von Benutzern für Plattformservices und die einheitliche Steuerung des Zugriffs auf Ressourcen innerhalb der {{site.data.keyword.Bluemix_notm}}-Plattform. Ein Set von {{site.data.keyword.Bluemix_notm}}-Services sind für die Nutzung von Cloud IAM zur Zugriffssteuerung aktiviert und in [Ressourcengruppen](/docs/account/resourcegroups.html) innerhalb Ihres Kontos organisiert. Auf diese Weise erhalten Benutzer den schnellen und einfachen Zugriff auf mehrere Ressourcen gleichzeitig. Die Cloud IAM-Zugriffsrichtlinien werden verwendet, um Benutzern und Service-IDs die Zugriffsberechtigungen für die Ressourcen innerhalb Ihres Kontos zuzuweisen. Sie können eine Gruppe von Benutzern und Service-IDs in eine [Zugriffsgruppe](/docs/iam/groups.html) gruppieren, um allen Entitäten in der Gruppe ohne großen Aufwand einen Zugriff derselben Ebene zu ermöglichen.

Eine Richtlinie weist einer Benutzer- oder einer [Service-ID](/docs/iam/serviceid.html#serviceids) mindestens eine Rolle mit einer Kombination aus Attributen zu, die den Geltungsbereich der Zugriffsberechtigungen definieren. Die Richtlinie kann Zugriff auf einen einzelnen Service bis auf die Instanzebene erteilen, oder für ein Set von Ressourcen gelten, die in einer Ressourcengruppe organisiert sind. Abhängig von den von Ihnen zugewiesenen [Benutzerrollen](/docs/iam/users_roles.html#iamusermanrol) erhält die Benutzer- oder Service-ID variierende Ebenen des Zugriffs zur Ausführung von Tasks für das Plattformmanagement oder für den Zugriff auf einen Service mithilfe einer Benutzerschnittstelle oder durch Ausführung bestimmter Typen von API-Aufrufen.

![IAM zur Zugriffssteuerung in einem Konto](images/iam-diagram.svg "Informationen zum Zugriffsmanagement in einem Konto mit IAM")

Für Services, die die Erstellung von Cloud IAM-Richtlinien für die Verwaltung von Zugriffsberechtigungen nicht unterstützen, können Sie den [Cloud Foundry-Zugriff](/docs/iam/cfaccess.html#cfaccess) verwenden.


## Welche Funktionen bietet Cloud IAM?
{: #features}

<dl>
<dt>Benutzermanagement</dt>
<dd>Das einheitliche Benutzermanagement ermöglicht Ihnen das Hinzufügen und Löschen von Benutzern in einem Konto sowohl für Plattform- als auch für Infrastrukturservices. Sie können eine als Zugriffsgruppe bezeichnete Gruppe von Benutzern erstellen und so die Zuweisung von gleichzeitigem Zugriff auf mehrere Benutzer beschleunigen und vereinfachen.</dd>
<dt>Differenzierte Zugriffssteuerung</dt>
<dd>Der Zugriff für Benutzer und Service-IDs wird durch eine Richtlinie definiert. Innerhalb der Richtlinie kann der Geltungsbereich des Zugriffs für einen Benutzer, eine Service-ID oder eine Zugriffsgruppe einem Set von Ressourcen in einer Ressourcengruppe oder einer einzelnen Ressource zugewiesen werden. Nachdem der Geltungsbereich festgelegt wurde, können Sie definieren, welche Aktionen für das Subjekt der Richtlinie zulässig sind, indem Sie die Zugriffsrollen auswählen. Rollen stellen eine Möglichkeit zur Anpassung der für das Subjekt der Richtlinie erteilten Zugriffsebene bereit, um die Tasks für das Plattformmanagement auszuführen und auf die Benutzerschnittstelle eines Service zugreifen oder API-Aufrufe ausführen zu können.</dd>
<dt>API-Schlüssel für Benutzerauthentifizierung</dt>
<dd>Es können mehrere API-Schlüssel für einen Benutzer erstellt werden, um Schlüsselrotationsszenarios zu unterstützen, und der gleiche Schlüssel kann für den Zugriff auf mehrere Services verwendet werden. Die API-Schlüssel von Plattformbenutzern bieten Benutzern, die eine Zwei-Faktor-Authentifizierung oder eine eingebundene ID verwenden, die Möglichkeit, die Authentifizierung über die Befehlszeile zu automatisieren.</dd>
<dt>Service-IDs</dt>
<dd>Eine Service-ID dient (ähnlich wie eine Benutzer-ID, die einen Benutzer identifiziert) zur Identifikation eines Service oder einer Anwendung. Es existieren IDs, die von Anwendungen zur Authentifizierung bei einem {{site.data.keyword.Bluemix_notm}}-Service verwendet werden können. Jeder Service-ID können Richtlinien zugewiesen werden, um die Zugriffsebene zu steuern, die von einer Anwendung mit der Service-ID zugelassen wird. Zur Aktivierung der Authentifizierung kann ein API-Schlüssel erstellt werden.</dd>
</dl>


## Wie nutze ich Cloud IAM?

Sie können auf Cloud IAM zugreifen und Cloud IAM nutzen, indem Sie auf die Identity and Access Management-Benutzerschnittstelle oder die Befehlszeilenschnittstelle für {{site.data.keyword.Bluemix_notm}} zugreifen.

Um auf Cloud IAM über die Benutzerschnittstelle zuzugreifen, rufen Sie **Verwalten** &gt; **Sicherheit** &gt; **Identität und Zugriff** auf.

Um auf Cloud IAM über die CLI zuzugreifen, machen Sie sich mit den Informationen in [Befehle zur Verwaltung von API-Schlüsseln und Richtlinien](/docs/cli/reference/bluemix_cli/bx_cli.html#bx_commands_iam) vertraut.
