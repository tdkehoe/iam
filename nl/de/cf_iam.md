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

# Cloud Foundry-Serviceinstanzen in eine Ressourcengruppe migrieren
{: #accessmodels}

Wenn Services von Cloud Foundry-Organisationen, -Bereichen und -Rollen auf die Verwendung von Cloud Identity and Access Management (IAM) und Ressourcengruppen übergehen, werden Sie in Ihrem Dashboard benachrichtigt. Wenn ein Service von Cloud Foundry abgezogen wird, werden Sie aufgefordert, Ihre vorhandenen Serviceinstanzen, die zu einer Organisation und einem Bereich gehören, in eine [Ressourcengruppe](/docs/account/resourcegroups.html#rgs) zu migrieren. 

Wenn Sie vorhandene Cloud Foundry-Serviceinstanzen in eine Ressourcengruppe migrieren, kann die Gruppenzuweisung nicht mehr geändert werden, nachdem die Migration abgeschlossen ist. Sie müssen sich also vor der Migration sicher sein, wie Sie die Ressourcen in dem Konto organisieren möchten. Dies könnte bedeuten, dass Sie vor der Migration eine oder mehrere Ressourcengruppen erstellen müssen, wenn Sie ein gebührenpflichtiges Konto haben.
{: tip}

## Warum sollte ich Serviceinstanzen migrieren?

Services, die Cloud IAM unterstützen, haben diverse Vorteile. Dazu zählt die Möglichkeit zur Herstellung von Verbindungen zu Apps und Services in einem beliebigen Cloud Foundry-Bereich. Auf diese Weise können Sie Verbindungen für Apps und Services aus unterschiedlichen Regionen herstellen. Darüber hinaus gehört jede von Cloud IAM verwaltete Instanz zu einer Ressourcengruppe. Da Ressourcengruppen nicht auf eine bestimmte Region bezogen sind, können Sie Apps und Services aus verschiedenen Regionen in derselben Ressourcengruppe bereitstellen. Außerdem können Sie die differenzierte Zugriffssteuerung für jede einzelne Instanz verwenden.
 

## Wie funktioniert Migration?

Bei der Migration einer Serviceinstanz aus einer Cloud Foundry-Organisation und einem Cloud Foundry-Bereich in einer Ressourcengruppe wird eine neue verknüpfte Serviceinstanz in der Ressourcengruppe erstellt. Die ursprüngliche Instanz in der Cloud Foundry-Organisation und dem Cloud Foundry-Bereich wird zu einem [Aliasnamen](/docs/cfapps/connecting_apps.html#what_is_alias).

Sie können Ihre Serviceinstanzen einzeln migrieren, wenn Sie benachrichtigt werden. Sie werden über ein Symbol im Dashboard benachrichtigt, das Ihrer Cloud Foundry-Serviceinstanz zugeordnet ist, oder mit der Nachricht auf der Seite mit den Servicedetails, die Sie direkt zu dem Assistenten leiten kann, der Sie durch den Prozess führt. Vor der Migration müssen Sie entscheiden, wie Ihre Ressourcen organisiert sein sollen. Dann können Sie eine infrage kommende Serviceinstanz wählen, indem Sie im Dashboard im Menü **Aktionen** die Option **In eine Ressourcengruppe migrieren** auswählen. Während des Prozesses wählen Sie eine Ressourcengruppe aus, in die die Instanz migriert werden soll. Nachdem Sie eine Instanz erfolgreich migriert haben, wird sie im Bereich 'Services' Ihres Dashboards angezeigt. Der Aliasname verbleibt im Abschnitt 'Cloud Foundry' des Dashboards. 


