---

copyright:

  years: 2017, 2018

lastupdated: "2018-04-17"

---

{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:screen: .screen}
{:new_window: target="_blank"}
{:tip: .tip}

# Cloud Foundry-Serviceinstanzen in eine Ressourcengruppe migrieren
{: #accessmodels}

Wenn Services von Cloud Foundry-Organisationen, -Bereichen und -Rollen auf die Verwendung von Cloud Identity and Access Management (IAM) und Ressourcengruppen übergehen, werden Sie in Ihrem Dashboard benachrichtigt. Wenn ein Service von Cloud Foundry abgezogen wird, werden Sie aufgefordert, Ihre vorhandenen Serviceinstanzen, die zu einer Organisation und einem Bereich gehören, in eine [Ressourcengruppe](/docs/account/resourcegroups.html#rgs) zu migrieren. 

Wenn Sie vorhandene Cloud Foundry-Serviceinstanzen in eine Ressourcengruppe migrieren, kann die Gruppenzuweisung nicht mehr geändert werden, nachdem die Migration abgeschlossen ist. Sie müssen sich also vor der Migration sicher sein, wie Sie die Ressourcen in dem Konto organisieren möchten. Dies könnte bedeuten, dass Sie vor der Migration eine oder mehrere Ressourcengruppen erstellen müssen, wenn Sie ein gebührenpflichtiges Konto haben.
{: tip}

## Warum sollte ich meine Serviceinstanzen migrieren?

Services, die die Benutzung von Cloud IAM unterstützen, verfügen über verschiedene Vorteile einschließlich der Möglichkeit zur Herstellung von Verbindungen zu Apps und Services in einem beliebigen Cloud Foundry-Bereich. Auf diese Weise können Sie Verbindungen für Apps und Services aus unterschiedlichen Regionen herstellen. Zusätzlich hierzu gehört jede von Cloud IAM verwaltete Instanz zu einer Ressourcengruppe. Die Ressourcengruppen sind nicht regionsorientiert, sodass Sie Apps und Services aus unterschiedlichen Regionen in derselben Ressourcengruppe bereitstellen können. Außerdem verfügen Sie über die Möglichkeit, die differenzierte Zugriffssteuerung für jede einzelne Instanz zu verwenden.
 

## Wie funktioniert Migration?

Bei der Migration einer Serviceinstanz aus einer Cloud Foundry-Organisation und einem Cloud Foundry-Bereich in einer Ressourcengruppe wird eine neue verknüpfte Serviceinstanz in der Ressourcengruppe erstellt. Die ursprüngliche Instanz in der Cloud Foundry-Organisation und dem Cloud Foundry-Bereich wird zu einem [Aliasnamen](/docs/cfapps/connecting_apps.html#what_is_alias).

Sie können Ihre Serviceinstanzen einzeln migrieren, wenn Sie über ein Symbol im Dashboard benachrichtigt werden, das Ihrer Cloud Foundry-Serviceinstanz zugeordnet ist, oder mit der Nachricht auf der Seite mit den Servicedetails, die Sie direkt zu dem Assistenten leiten kann, der Sie durch den Prozess führt. Treffen Sie vor der Migration eine Entscheidung darüber, wie Sie Ihre Ressourcen organisieren wollen. Dann können Sie eine infrage kommende Serviceinstanz wählen, indem Sie im Dashboard im Menü **Aktionen** die Option **In eine Ressourcengruppe migrieren** auswählen. Während des Prozesses wählen Sie eine Ressourcengruppe aus, in die die Instanz migriert werden soll. Nachdem Sie eine Instanz erfolgreich migriert haben, wird sie im Bereich 'Services' Ihres Dashboards angezeigt. Der Aliasname verbleibt im Bereich 'Cloud Foundry' des Dashboards. 


