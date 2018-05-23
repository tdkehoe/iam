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


# Concessione dell'accesso tra i servizi
{: #serviceauth}

Molte delle funzionalità del sistema {{site.data.keyword.Bluemix_notm}} Identity and Access Management (IAM) sono focalizzati sulla gestione e l'applicazione dell'accesso alle risorse {{site.data.keyword.Bluemix_notm}} da parte degli utenti e delle loro applicazioni. Tuttavia, esistono altri scenari in cui potresti dover fornire un servizio con accesso alla risorsa di un utente in un altro servizio. Tutti gli utenti nel tuo account possono creare un'autorizzazione, ma solo un utente con il ruolo `Amministratore` può eliminare un'autorizzazione. Puoi configurare e visualizzare le autorizzazioni all'interno del tuo account utilizzando la pagina **Autorizzazioni**.

## Crea un'autorizzazione

Puoi concedere solo il livello di accesso di cui disponi come utente del servizio di destinazione. Ad esempio, se disponi solo dell'accesso di visualizzatore sul servizio a cui si accederà, puoi assegnare solo il ruolo di visualizzatore per l'autorizzazione.

1. Dalla barra dei menu, fai clic su **Gestisci** &gt; **Account** &gt; **Identità e accesso** e seleziona quindi **Autorizzazioni**.
2. Fai clic su **Crea autorizzazione**.
3. Seleziona un'origine e una destinazione per l'autorizzazione. Al servizio di origine viene fornito accesso al servizio di destinazione selezionato.
4. Seleziona un ruolo per assegnare l'accesso al servizio di origine quando accede al servizio di destinazione.
5. Fai clic su **Autorizza**.

**Nota**: solo i servizi che consentono di concedere questo tipo di accesso sono disponibili come opzioni.

## Rimuovi un'autorizzazione

1. Dalla barra dei menu, fai clic su **Gestisci** &gt; **Account** &gt; **Identità e accesso** e seleziona quindi **Autorizzazioni**.
2. Identifica la riga per l'autorizzazione che desideri rimuovere dall'account.
3. Dal menu **Azioni**, seleziona **Rimuovi autorizzazione**.
5. Seleziona **Rimuovi**.
