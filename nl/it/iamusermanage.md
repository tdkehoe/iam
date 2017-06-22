---

copyright:

  years: 2015, 2017

lastupdated: "2017-05-30"

---

{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:screen: .screen}
{:new_window: target="_blank"}

# Gestione di utenti e accesso
{: #iamusermanage}

A seconda delle opzioni di accesso che sei autorizzato a gestire, puoi visualizzare e gestire gli utenti nell'account o nell'organizzazione. Come proprietario di un account, puoi gestire gli utenti in tutte le opzioni di accesso che gestisci e alle quali è assegnato l'accesso dell'utente nell'account corrente.
{:shortdesc}

Per gestire gli utenti nel tuo account, completa la seguente procedura:

1. Dalla barra dei menu, fai clic su **Gestisci ** &gt; **Account** &gt; **Utenti**. La finestra Utenti visualizza un elenco di utenti con i rispettivi indirizzi email per l'account attualmente selezionato. 
2. Seleziona il nome utente o fai clic su **Gestisci utente** dal menu **Azioni**. 
3. Quindi, a seconda dell'accesso che puoi gestire, aggiorna l'accesso per l'utente nelle sezioni Politiche di servizio o Ruoli Cloud Foundry oppure fai clic sul link per accedere alla pagina Assegna accesso infrastruttura.

Consulta le seguenti sezioni per ulteriori informazioni sulla gestione di ciascun tipo di accesso.

Se devi controllare il tuo accesso assegnato in un account a cui sei stato aggiunto, completa la seguente procedura:

1. Dalla barra dei menu, fai clic su **Gestisci** &gt; **Sicurezza** &gt; **Identità e accesso** &gt; **Utenti**. 
2. Seleziona il tuo nome. 
3. Controlla i tuoi ruoli assegnati.

Se hai bisogno di privilegi aggiuntivi, devi contattare il gestore dell'organizzazione o il proprietario dell'account per aggiornare il ruolo Cloud Foundry oppure devi contattare l'amministratore per il servizio o l'istanza del servizio per aggiornare la politica di servizio.

Per informazioni dettagliate sui comandi CLI utilizzati per gestire account, organizzazioni e spazi, vedi [Comandi per gestire account, organizzazioni e ruoli](https://console.stage1.bluemix.net/docs/cli/reference/bluemix_cli/bx_cli.html#bx_commands_acctorg).

## Accesso Cloud Foundry
{: #iammancfser}

Per gestire l'accesso alle organizzazioni e agli spazi dell'account, devi essere il proprietario dell'account, il gestore organizzazione o il gestore spazio:

1. Dalla barra dei menu, fai clic su **Gestisci** &gt; **Sicurezza** &gt; **Identità e accesso** &gt; **Utenti**. 
2. Seleziona il nome utente per il quale vuoi modificare i ruoli.
3. Dal menu **Azioni** nella sezione Cloud Foundry, puoi:

  * Rimuovere l'utente dall'organizzazione
  * Modificare il ruolo organizzazione
  * Modificare il ruolo spazio

Se sei il gestore di un'organizzazione di cui l'utente non è ancora membro, puoi anche aggiungere un utente a un'altra organizzazione facendo clic su **Assegna organizzazione**. 


## Servizi abilitati per l'accesso e l'identità
{: #iammanidaccser}

Per gestire le politiche di servizio o assegnare nuove politiche di servizio per gli utenti, devi essere l'amministratore di accesso account o l'amministratore assegnato per il servizio o l'istanza del servizio particolare.

1. Dalla barra dei menu, fai clic su **Gestisci** &gt; **Sicurezza** &gt; **Identità e accesso** &gt; **Utenti**. 
2. Seleziona il nome utente per il quale vuoi assegnare le politiche di servizio.
3. Seleziona **Assegna politiche del servizio** per creare una nuova politica di servizio oppure, dal menu **Azioni** nella sezione Politiche di servizio, puoi:
  
  * Modificare la politica
  * Rimuovere la politica

Per ulteriori informazioni sulle politiche di servizio e sui ruoli, vedi [Politiche e ruoli per la gestione di identità e accesso](/docs/iam/users_roles.html#iamusermanpol).

## Servizi di infrastruttura

Per assegnare o aggiornare autorizzazioni dell'infrastruttura, fai clic sul link **Assegna accesso infrastruttura**.
