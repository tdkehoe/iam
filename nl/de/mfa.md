---

copyright:

  years: 2018
lastupdated: "2018-05-22"

---

{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:screen: .screen}
{:new_window: target="_blank"}
{:tip: .tip}

# Mehrfaktorauthentifizierung aktivieren
{: #enablemfa}

Durch die Mehrfaktorauthentifizierung (MFA) wird eine zusätzliche Sicherheitsebene zu Ihrem Konto hinzugefügt, denn Benutzer müssen bei der Anmeldung neben ihrer Standard-IBMid und ihrem Kennwort zusätzlich einen zeitbasierten einmaligen Kenncode eingeben. Dieser Mechanismus wird gängigerweise auch als Zwei-Faktor-Authentifizierung (2FA) bezeichnet. Wenn dieses Feature für Ihr Konto aktiviert ist, müssen nicht nur Sie bei der Anmeldung einen zusätzlichen Sicherheitsstandard verwenden, sondern auch alle Benutzer, die Ihrem Konto hinzugefügt werden.

## Überlegungen

Stellen Sie die folgenden Überlegungen an, bevor Sie die Mehrfaktorauthentifizierung für Ihr Konto aktivieren:

* Wenn Sie MFA für Ihr Konto aktivieren, müssen alle Benutzer, die zu Ihrem Konto hinzugefügt werden, bei der nächsten Anmeldung den Prozess der Zwei-Faktor-Authentifizierung (2FA) durchführen.
* API-Schlüssel für Benutzer und Service-IDs funktionieren weiter, nachdem MFA aktiviert wurde.
* Wenn Sie sich über eine native CF-CLI oder -UI bei Cloud Foundry anmelden, müssen Sie API-Schlüssel oder Single Sign-on verwenden, nachdem MFA für das Konto aktiviert wurde.
* MFA wird nicht für Benutzer unterstützt, die sich mit einer föderierten Identität anmelden.
* Planen Sie eine Kommunikations- und Supportstrategie für Benutzer in Ihrem Konto.
  * Wählen Sie ein Datum und eine Uhrzeit mit möglichst geringer Auswirkung auf Ihr Geschäft für die Aktivierung von MFA aus.
  * Informieren Sie Ihre Kontobenutzer nach der Aktivierung von MFA darüber, [welche Schritte sie ausführen müssen](mfa.html#setupapp).
  
Berücksichtigen Sie Folgendes, wenn Sie über ein verknüpftes Konto verfügen und zuvor eine [Zwei-Faktor-Authentifizierung (2FA) im Steuerungsportal](/docs/customer-portal/cpenable2fa.html#customerportal_2fa) konfiguriert haben:

* Die MFA für Ihr {{site.data.keyword.Bluemix_notm}}-Konto gilt auch für die Plattform- und Infrastrukturservices für ihr verknüpftes Konto. Da die MFA-Kontoeinstellung 2FA im Steuerungsportal außer Kraft setzt, können Sie 2FA, das Sie nur für Ihre Infrastrukturressourcen erworben und konfiguriert haben, zugunsten der MFA-Einstellung inaktivieren.
* Für föderierte Benutzer wird MFA nicht unterstützt. Behalten Sie in diesem Fall die 2FA für die Infrastrukturressourcen bei, damit diese weiterhin gesichert sind.

## Mehrfaktorauthentifizierung aktivieren

Um die Mehrfaktorauthentifizierung (MFA) aktivieren zu können, müssen Sie der Kontoadministrator sein. Das Aktivieren der MFA wirkt sich nicht auf Benutzer aus, die bereits angemeldet sind, da sich die Aktion nur bei neuen Anmeldungen bemerkbar macht. Jeder Administrator, der MFA für ein Konto aktiviert, sollte die Kontobenutzer darüber informieren und die Auswirkungen dieser Änderung auf ihre nächste Anmeldung beschreiben. 

1. Klicken Sie in der Menüleiste auf **Verwalten** &gt; **Sicherheit** &gt; **Identität und Zugriff** und wählen Sie dann **Einstellungen** aus.
2. Wählen Sie **Mehrfaktorauthentifizierung** &gt; **Änderungen anwenden** aus.
3. Klicken Sie in den Bestätigungsfenstern auf **Ja, ich bin sicher**.

## Einmaligen Kenncode festlegen
{: #setupapp}

Nachdem Sie MFA für Ihr Konto aktiviert haben, müssen Sie bei der nächsten Anmeldung mithilfe einer Authentifikator-App den einmaligen Kenncode festlegen. Alle Benutzer in Ihrem Konto müssen bei ihrer nächsten Anmeldung ebenfalls den einmaligen Kenncode festlegen. 

Führen Sie die folgenden Schritte aus, um Ihren einmaligen Kenncode mit einer Authentifikator-App erstmalig festzulegen:

1. Melden Sie sich mit Ihrer IBMid und Ihrem Kennwort an. 

Es kann bis zu fünf Minuten dauern, bis Sie sich mit der MFA erneut anmelden können, nachdem sie eingerichtet wurde.

2. Wählen Sie **Verifizieren** im Bildschirm **Verifizierung ist erforderlich** aus, um MFA mit einer Authentifikator-App einzurichten.
3. Wählen Sie **Authentifikator-App konfigurieren** aus, damit ein einmaliger Code an Ihre E-Mail-Adresse gesendet wird, den Sie für die weitere Einrichtung der Authentifikator-App benötigen.
4. Wählen Sie **Verifizieren** aus.
5. Scannen Sie den Barcode mit Ihrer App oder klicken Sie auf **Barcode kann nicht gescannt werden?**, um einen manuell bereitgestellten Schlüssel einzugeben. 
6. Klicken Sie auf **Weiter**, um Ihren Code einzugeben.
7. Geben Sie Ihren Code ein und wählen Sie **Verifizieren** aus. 

Wenn eine Fehlernachricht mit dem Inhalt angezeigt wird, dass Sie die Authentifizierung bereits eingerichtet haben, doch Ihr Verifizierungscode funktioniert nicht oder Sie verfügen über keinen Verifizierungscode für die Eingabe, so müssen Sie sich an den [Help-Desk](https://www.ibm.com/ibmid/myibm/help/us/helpdesk.html){: new_window} ![Symbol für externen Link](../icons/launch-glyph.svg "Symbol für externen Link") wenden, um Ihre MFA-Registrierung zurückzusetzen.
{: tip}
{: #mfahelp}


## Mehrfaktorauthentifizierung inaktivieren
{: #disablemfa}

Um die Mehrfaktorauthentifizierung (MFA) inaktivieren zu können, müssen Sie der Kontoadministrator sein. Das Inaktivieren der MFA wirkt sich nicht auf Benutzer aus, die bereits angemeldet sind, da sich die Aktion nur bei neuen Anmeldungen bemerkbar macht. 

1. Klicken Sie in der Menüleiste auf **Verwalten** &gt; **Sicherheit** &gt; **Identität und Zugriff** und wählen Sie dann **Einstellungen** aus.
2. Klicken Sie auf **Standard** und dann auf **Ja, ich bin sicher**.
3. Klicken Sie in den Bestätigungsfenstern auf **Ja, ich bin sicher**.
