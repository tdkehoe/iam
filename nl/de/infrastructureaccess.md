---

copyright:

  years: 2017, 2018

lastupdated: "2018-04-12"

---

{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:screen: .screen}
{:new_window: target="_blank"}

# Infrastructure-Berechtigungen
{: #infrapermission}

Sie können bei der Einladung eines Benutzers die folgenden Ausgangsberechtigungssets festlegen:

| Festgelegte Berechtigung | Beschreibung von Aktionen |
|---------------------------|------------------------|
|Nur anzeigen | Benutzer mit dieser Berechtigung können nur Elemente im System anzeigen. Benutzer können beispielsweise Tickets, Details zu Hardware und virtuellen Servern, Lizenzen, Bandbreitendetails und die Kontozusammenfassung mit Rechnungen und Zahlungen anzeigen. |
|Basisbenutzer | Benutzer mit dieser Berechtigung können Tickets anzeigen, suchen, hinzufügen und bearbeiten, Geräte verwalten, auf die sie Zugriff haben, IP-Adressen hinzufügen, E-Mail-Zustellungsservices verwalten, DNS-Datensätze hinzufügen, bearbeiten und anzeigen, neue Benutzer mit Zugriff auf die Infrastruktur hinzufügen und Benachrichtigungen verwalten. |
|Superuser | Benutzer mit dieser Berechtigung können alle verfügbaren Aktionen im System ausführen. |
{:caption="Tabelle 1. Infrastructure-Berechtigungen" caption-side="top"}

Weitere Berechtigungen können festgelegt werden, nachdem der Benutzer die Einladung akzeptiert hat. Das Ausgangsberechtigungsset, das zum Zeitpunkt der Einladung festgelegt wird, erteilt keinen Zugriff auf Geräte. Die Zugriffsberechtigungen für Geräte müssen deshalb im Steuerungsportal erteilt werden, nachdem der Benutzer die Einladung akzeptiert hat.  

Wenn Sie jemanden zum Konto einladen, können nur Sie und der Masterbenutzer des SoftLayer-Kontos die Berechtigungen für den Benutzer anpassen. Wenn Sie die Berechtigungen zuweisen und nicht der Masterbenutzer sind, können Sie nur die Berechtigungsebene oder eine Untergruppe der bereits zugewiesenen Berechtigungen zuweisen. Ein Masterbenutzer kann jedoch die Berechtigungen jedes Benutzers in dem Konto aktualisieren, um eine beliebige Zugriffsebene zu haben. 

Rufen Sie das Menüsymbol ![Menüsymbol](../icons/icon_hamburger.svg) auf und wählen Sie dann **Infrastruktur** auf, um auf das Steuerungsportal zuzugreifen und mit den Benutzerberechtigungen für die Infrastruktur zu arbeiten. Wenn Sie **Konto** &gt; **Benutzer** aufrufen, dann wird Ihre Benutzerliste angezeigt, in der Sie den Gerätezugriff und andere Infrastructure-Berechtigungen festlegen können. Weitere Informationen zum Zuweisen von Zugriff finden Sie unter [Infrastructure-Zugriff verwalten](/docs/iam/mnginfra.html#managing-infrastructure-access).






