---

copyright:

  years: 2015, 2018
lastupdated: "2018-05-02"

---

{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:screen: .screen}
{:new_window: target="_blank"}

# Gestione delle politiche di accesso degli ID servizio
{: #serviceidpolicy}

Quando crei un ID servizio, puoi assegnare delle politiche di servizio per tale ID servizio per controllare il livello di accesso consentito quando viene utilizzato per eseguire l'autenticazione presso i tuoi servizi. Puoi aggiornare queste politiche di accesso assegnate in qualsiasi momento modificando una politica esistente, eliminando una politica o assegnandone una nuova.

**Nota**: l'eliminazione o la modifica di una politica esistente per un ID servizio attualmente utilizzato può causare un'interruzione del servizio.

## Assegnazione del nuovo accesso

Per assegnare l'accesso a tutte le risorse in un gruppo di risorse o a un solo servizio all'interno di un gruppo di risorse, completa la seguente procedura:

1. Dalla barra dei menu, fai clic su **Gestisci** &gt; **Sicurezza** &gt; **Identità e accesso** &gt; **ID servizio**.
2. Seleziona l'ID servizio dalla tabella per cui vuoi assegnare una politica di servizio.
3. Fai clic su **Assegna accesso**.
4. Seleziona **Assegna per gruppo di risorse**.
5. Seleziona un gruppo di risorse.
6. Scegli un ruolo per il campo **Assegna l'accesso al gruppo di risorse**. Questa opzione consente all'utente di visualizzare il gruppo di risorse sul proprio dashboard, modificare il nome del gruppo di risorse o gestire l'accesso dell'utente al gruppo. Puoi selezionare **Nessun accesso** se vuoi che l'utente abbia accesso solo alla risorsa da te specificata e non al gruppo a cui è assegnata.
7. Seleziona un servizio nel gruppo di risorse o scegli di fornire l'accesso a tutti i servizi all'interno del gruppo selezionato.
8. Scegli qualsiasi combinazione di ruoli per assegnare l'accesso desiderato per l'utente. Questo accesso si applica solo alle risorse che hai selezionato per la politica. Non dà accesso al contenitore reale che è il gruppo di risorse.
9. Seleziona **Assegna**.

Per assegnare l'accesso a una singola risorsa nell'account, completa la seguente procedura:

1. Dalla barra dei menu, fai clic su **Gestisci** &gt; **Sicurezza** &gt; **Identità e accesso** &gt; **ID servizio**.
2. Seleziona l'ID servizio dalla tabella per cui vuoi assegnare una politica di servizio.
3. Fai clic su **Assegna accesso**.
4. Seleziona **Assegna per risorsa**.
5. Seleziona un servizio.
6. Seleziona **Tutte le regioni correnti** su una specifica regione, se ti viene richiesto.
7. Seleziona **Tutte le istanze del servizio correnti** o una specifica istanza del servizio.
8. A seconda del servizio che hai selezionato, potresti visualizzare i seguente campi. Se non immetti valori per questi campi, la politica viene assegnata a livello dell'istanza del servizio anziché a livello del bucket.
    * **Tipo di risorsa**: immetti **bucket**.
    * **ID risorsa**: immetti il nome del tuo bucket.
9. Scegli qualsiasi combinazione di ruoli per assegnare l'accesso desiderato per l'utente.
10. Seleziona **Assegna**.



## Modifica dell'accesso esistente

Per modificare una politica esistente:

1. Dalla barra dei menu, fai clic su **Gestisci** &gt; **Sicurezza** &gt; **Identità e accesso** &gt; **ID servizio**.
2. Seleziona l'ID servizio dalla tabella per cui vuoi modificare una politica del servizio.
3. Identifica la riga della politica che vuoi modificare e seleziona **Modifica politica** dal menu **Azioni**.
4. Apporta le tue modifiche e salva quindi la politica.

## Rimozione dell'accesso

Per rimuovere una politica esistente:

1. Dalla barra dei menu, fai clic su **Gestisci** &gt; **Sicurezza** &gt; **Identità e accesso** &gt; **ID servizio**.
2. Seleziona l'ID servizio dalla tabella per cui vuoi eliminare una politica del servizio.
3. Identifica la riga della politica che vuoi eliminare e seleziona **Rimuovi** dal menu **Azioni**.
4. Riesamina i dettagli della politica che stai per rimuovere e fai clic su **Rimuovi** per confermare.
