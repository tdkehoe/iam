---

copyright:

  years: 2017
lastupdated: "2017-11-16"

---

{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:screen: .screen}
{:new_window: target="_blank"}

# Service-IDs erstellen und verwalten
{: #serviceids}

Eine Service-ID dient (ähnlich wie eine Benutzer-ID, die einen Benutzer identifiziert) zur Identifikation eines Service oder einer Anwendung. Eine von Ihnen erstellte Service-ID kann verwendet werden, um einer Anwendung außerhalb von {{site.data.keyword.Bluemix_notm}} den Zugriff auf Ihre {{site.data.keyword.Bluemix_notm}}-Services zu erteilen. Sie können der Service-ID spezielle Zugriffsrichtlinien zuweisen, die die Berechtigungen zur Verwendung bestimmter Services einschränken, oder auch die Berechtigungen für den Zugriff auf unterschiedliche Services kombinieren. Da Service-IDs nicht an bestimmte Benutzer gebunden sind, bleibt die Service-ID bestehen, wenn der zugehörige Benutzer Ihre Organisation verlässt und sein Konto deshalb gelöscht wird. Auf diese Weise wird sichergestellt, dass Ihre Anwendung oder Ihr Service weiterhin funktionsbereit bleibt.

Bei der Erstellung einer Service-ID werden ein eindeutiger Name und eine eindeutige Beschreibung erstellt, die Sie einfach identifizieren und mit der Sie in der Benutzerschnittstelle problemlos arbeiten können. Nach der Erstellung Ihrer Service-ID können Sie API-Schlüssel speziell für die einzelnen Service-IDs erstellen, die von Ihrer Anwendung benutzt werden können, um die Authentifizierung bei Ihren {{site.data.keyword.Bluemix_notm}}-Services durchzuführen. Um sicherzustellen, dass Ihre Anwendung über die korrekten Zugriffsberechtigungen für die Authentifizierung bei Ihren {{site.data.keyword.Bluemix_notm}}-Services verfügt, können Sie die Servicerichtlinien verwenden, die den von Ihnen erstellten Service-IDs zugewiesen werden. 

Die Zugriffsrichtlinien, die einer Service-ID zugewiesen werden, aktivieren bestimmte Aktionen, die ausgeführt werden können, wenn diese Service-ID für den Zugriff auf einen bestimmten Service verwendet wird. Einer einzelnen Service-ID können mehrere Richtlinien zugewiesen werden, die die Zugriffsebene definieren, die beim Zugriff auf mehrere identitäts- und zugriffsaktivierte Services und auf die unterschiedlichen Instanzen eines einzelnen Service zulässig ist. Sie verfügen beispielsweise über zwei Services mit jeweils zwei Serviceinstanzen. Sie können nun z. B. allen verfügbaren Instanzen des einen Service die Rolle `Anzeigeberechtigter` und nur einer Instanz des zweiten Service die Rolle `Editor` zuweisen. Auf diese Weise können Sie den Zugriff auf mehrere Services anpassen, jedoch bei allen einen einzigen API-Schlüssel zu Authentifizierungszwecken einsetzen.


## Service-ID erstellen

Zum Erstellen einer Service-ID müssen Sie die Optionen **Verwalten** &gt; **Sicherheit** &gt; **Identität und Zugriff** und anschließend **Service-IDs** in der Seitenleiste auswählen. Befolgen Sie die Vorgehensweise, um einen Namen und eine Beschreibung für Ihre Service-ID zu erstellen. Verwenden Sie dann das Menü **Aktionen**, um Ihre Service-ID zu verwalten. Als erstes können Sie eine Richtlinie zuweisen und API-Schlüssel erstellen. Weitere Informationen zum Arbeiten mit API-Schlüsseln finden Sie in [API-Schlüssel für Service-IDs verwalten](/docs/iam/serviceid_keys.html#serviceidapikeys). Detaillierte Informationen zu den CLI-Befehlen, die zur Verwaltung von Service-IDs verwendet werden, finden Sie in [Befehle zur Verwaltung von API-Schlüsseln und Richtlinien](/docs/cli/reference/bluemix_cli/bx_cli.html#bx_commands_iam). 

## Service-ID aktualisieren

Um eine Service-ID zu aktualisieren, können Sie jederzeit ihren Namen und die Beschreibung ändern. Außerdem können Sie API-Schlüssel löschen und neue API-Schlüssel erstellen, wenn dies erforderlich ist, oder die zugewiesenen Zugriffsrichtlinien aktualisieren. Alle von Ihnen an einer vorhandenen Service-ID durchgeführten Änderungen (z. B. das Ändern der zugewiesenen Richtlinien oder das Löschen eines API-Schlüssels, der momentan verwendet wird) können zu Serviceunterbrechungen für Anwendungen führen, die diese Service-ID verwenden.


