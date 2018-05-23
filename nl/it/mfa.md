---

copyright:

  years: 2018
lastupdated: "2018-05-04"

---

{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:screen: .screen}
{:new_window: target="_blank"}
{:tip: .tip}

# Abilitazione dell'autenticazione multifattore
{: #enablemfa}

L'autenticazione multifattore (MFA, multi-factor authentication) aggiunge un ulteriore livello di sicurezza al tuo account richiedendo che tutti gli utenti forniscano un passcode monouso con scadenza oltre ai loro ID IBM e password standard durante l'accesso. Questa è anche comunemente nota come autenticazione a due fattori (2FA, two-factor authentication). L'abilitazione di questa funzione per il tuo account richiede l'utilizzo dello standard di sicurezza aggiuntivo quando si esegue l'accesso non solo a te ma anche a tutti gli utenti aggiunti al tuo account.

## Considerazioni

Prima di abilitare l'autenticazione multifattore per il tuo account, esamina le seguenti considerazioni:

* Quando abiliti la MFA per il tuo account, tutti gli utenti aggiunti al tuo account devono completare il processo 2FA la prossima volta che eseguono l'accesso.
* Le chiavi API per gli utenti e gli ID servizio continueranno a funzionare dopo che la MFA è stata abilitata.
* Se devi utilizzare l'accesso IU o CLI CF nativa in Cloud Foundry, devi utilizzare le chiavi API oppure SSO (single sign-on) dopo l'abilitazione della MFA per l'account.
* La MFA non è supportata per gli utenti che eseguono l'accesso con un'identità federata.
* Pianifica una strategia di comunicazione e supporto per gli utenti nel tuo account:
  * Scegli una data e ora in cui intendi abilitare la MFA che produca il minimo impatto sulla tua attività aziendale.
  * Dopo che hai abilitato la MFA, notifica agli utenti del tuo account le informazioni su come [procedere alla configurazione](mfa.html#setupapp).
  
Se hai un account collegato e hai in precedenza configurato la [2FA nel portale di controllo](/docs/customer-portal/cpenable2fa.html#customerportal_2fa), tieni conto di quanto segue:

* La MFA per il tuo account {{site.data.keyword.Bluemix_notm}} si estende all'ambito dei servizi di piattaforma e infrastruttura per il tuo account collegato. Poiché l'impostazione dell'account dell'MFA sovrascrive la 2FA nel portale di controllo, puoi scegliere di disabilitare la 2FA che hai acquistato ed eseguire la configurazione solo per le tue risorse dell'infrastruttura a favore dell'opzione di impostazione dell'MFA.
* Se sei un utente federato, la MFA non è supportata. Sarebbe pertanto opportuno conservare la tua 2FA solo per le risorse dell'infrastruttura per garantire la sicurezza delle tue risorse.

## Abilitazione dell'autenticazione multifattore

Per abilitare la MFA devi essere l'amministratore dell'account. L'abilitazione della MFA non ha ripercussioni sugli utenti che hanno già eseguito l'accesso, poiché l'implementazione della MFA sull'account ha effetto solo sui nuovi accessi. Qualsiasi amministratore che abilita la MFA per l'account deve informare gli utenti dell'account che la MFA è abilitata e descrivere l'impatto sugli utenti al loro successivo accesso nel caso in cui gli utenti desiderino eseguirne la configurazione anticipatamente.

1. Dalla barra dei menu, fai clic su **Gestisci** &gt; **Sicurezza** &gt; **Identità e accesso** e seleziona quindi **Impostazioni**.
2. Seleziona **Autenticazione multifattore (MFA)** &gt; e fai quindi clic su **Applica le modifiche**.
3. Nelle finestre di conferma, fai clic su **Sì, sono sicuro**.

## Configurazione del passcode monouso
{: #setupapp}

Dopo che hai abilitato la MFA per il tuo account, dovrai configurare il passcode monouso con un'applicazione autenticatore la volta successiva che esegui l'accesso. Anche tutti gli utenti nel tuo account dovranno configurare il passcode monouso al loro successivo accesso. 

Completa la seguente procedura per configurare il tuo passcode monouso con l'applicazione autenticatore per la prima volta.

1. Accedi con i tuoi ID IBM e password. 

Potrebbero volerci fino a 5 minuti perché tu possa eseguire nuovamente l'accesso con la MFA configurata dopo la sua abilitazione.

2. Seleziona **Verify** nella schermata **Verification is required** per configurare la MFA con un'applicazione autenticatore.
3. Seleziona **Setup your authenticator app** per ottenere un codice monouso inviato alla tua email per continuare la configurazione dell'applicazione autenticatore.
4. Seleziona **Verify**.
5. Esegui la scansione del codice a barre con la tua applicazione oppure fai clic su **Can't scan the barcode?** per immettere una chiave fornita manualmente. 
6. Fai clic su **Continue** per immettere il tuo codice.
7. Immetti il tuo codice e seleziona **Verify**. 

Se riscontri un messaggio di errore che indica che hai già configurato l'autenticazione ma il tuo codice di verifica non sta funzionando o non hai il tuo codice di verifica da immettere, devi contattare l'[Helpdesk](https://www.ibm.com/ibmid/myibm/help/us/helpdesk.html){: new_window} ![Icona link esterno](../icons/launch-glyph.svg "Icona link esterno") per reimpostare la tua registrazione dell'MFA.
{: tip}
{: #mfahelp}


## Disabilitazione dell'autenticazione multifattore
{: #disablemfa}

Per disabilitare la MFA devi essere l'amministratore dell'account. La disabilitazione della MFA non ha ripercussioni sugli utenti che hanno già eseguito l'accesso e l'azione ha effetto su tutti i nuovi accessi.

1. Dalla barra dei menu, fai clic su **Gestisci** &gt; **Sicurezza** &gt; **Identità e accesso** e seleziona quindi **Impostazioni**.
2. Seleziona **Standard** &gt; e fai quindi clic su **Sì, sono sicuro**.
3. Nelle finestre di conferma, fai clic su **Sì, sono sicuro**.
