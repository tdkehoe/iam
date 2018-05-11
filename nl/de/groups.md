---

copyright:

  years: 2018
lastupdated: "2018-03-30"

---

{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:screen: .screen}
{:new_window: target="_blank"}
{:tip: .tip}


# Zugriffsgruppen einrichten
{: #groups}

Eine Zugriffsgruppe kann erstellt werden, um eine Gruppe von Benutzern und Service-IDs in einer einzigen Entität zu organisieren, die es Ihnen leicht macht, Berechtigungen zuzuweisen. Sie können der Gruppe eine einzige Richtlinie zuweisen, anstatt denselben Zugriff mehrmals für den einzelnen Benutzer oder die einzelne Service-ID zuzuweisen.

Um die Zuweisung und Verwaltung des Zugriffs noch einfacher zu gestalten, können Sie Ressourcengruppen einrichten, um eine Gruppe von Ressourcen zu organisieren, auf die eine Gruppe von Benutzern Zugriff haben soll. Wenn Ihre Ressourcengruppe eingerichtet ist, können Sie eine Richtlinie zuordnen, die den Zugriff auf alle Ressourcen in dieser Gruppe ermöglicht, anstatt Zugriffsrichtlinien für einzelne Serviceinstanzen innerhalb Ihres Kontos zu erstellen.  

## Zugriffsgruppe erstellen

Führen Sie die folgenden Schritte aus, um eine Zugriffsgruppe zu erstellen:

1. Klicken Sie in der Menüleiste auf **Verwalten** &gt; **Sicherheit** &gt; **Identität und Zugriff** und wählen Sie dann **Zugriffsgruppen** aus.
2. Klicken Sie auf **Erstellen**.
3. Geben Sie einen Namen und eine optionale Beschreibung für Ihre Gruppe ein und klicken Sie auf **Erstellen**.

Fahren Sie danach mit der Einrichtung Ihrer Gruppe fort, indem Sie Benutzer oder Service-IDs hinzufügen:

1. Wählen Sie den Namen der Gruppe aus, zu der Sie diese hinzufügen wollen.
2. Klicken Sie auf der Registerkarte **Benutzer** auf **Benutzer hinzufügen**. 
3. Wählen Sie die Benutzer, die Sie hinzufügen möchten, in der Liste aus und klicken Sie auf **Zu Gruppe hinzufügen**.
4. Wenn Sie Service-IDs zu der Gruppe hinzufügen wollen, klicken Sie auf **Service-IDs** und anschließend auf **Service-ID hinzufügen**.
5. Wählen Sie die IDs, die Sie hinzufügen möchten, in der Liste aus und klicken Sie auf **Zu Gruppe hinzufügen**.

Sie können eine Gruppe löschen, indem Sie die Option **Gruppe entfernen** auswählen. Beim Entfernen einer Gruppe aus dem Konto entfernen Sie alle Benutzer und Service-IDs aus der Gruppe sowie den gesamten der Gruppe zugewiesenen Zugriff.
{: tip}


## Zugriff auf eine Gruppe zuweisen

Nachdem Sie Ihre Gruppe mit Benutzern und Service-IDs eingerichtet haben, können Sie der Gruppe eine gemeinsame Zugriffsrichtlinie zuweisen. Denken Sie daran, dass alle Richtlinien, die Sie für die Gruppe festlegen, für alle Entitäten in der Gruppe gelten.

1. Klicken Sie in der Menüleiste auf **Verwalten** &gt; **Sicherheit** &gt; **Identität und Zugriff** und wählen Sie dann **Zugriffsgruppen** aus.
2. Wählen Sie den Namen der Gruppe aus, auf die Sie Zugriff zuweisen wollen. 
3. Klicken Sie auf die Registerkarte **Zugriffsrichtlinien**.
4. Klicken Sie auf **Zugriff zuweisen**. 
5. Wählen Sie die Zuweisung von Zugriff nach Ressourcen in einer Ressourcengruppe oder nach einzelnen im Konto verfügbaren Ressourcen aus.
