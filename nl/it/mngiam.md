---

copyright:

  years: 2017, 2018

lastupdated: "2018-09-04"

---

{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:screen: .screen}
{:new_window: target="_blank"}
{:tip: .tip}

# Gestione dell'accesso alle risorse
{: #iammanidaccser}

Per gestire l'accesso o assegnare un nuovo accesso per gli utenti utilizzando le politiche IAM, devi essere il proprietario dell'account, l'amministratore su tutti i servizi nell'account o l'amministratore assegnato per il servizio o l'istanza del servizio particolare. Per ulteriori informazioni sulle politiche di accesso e sui ruoli, vedi [Accesso IAM](/docs/iam/users_roles.html).

## Modifica dell'accesso esistente

1. Dalla barra dei menu, fai clic su **Gestisci** &gt; **Sicurezza** &gt; **Identità e accesso** e seleziona **Utenti**.
2. Seleziona il nome dell'utente a cui vuoi assegnare l'accesso.
3. Dalla riga per la politica che vuoi modificare, seleziona il menu **Azioni** e fai quindi clic su **Modifica politica**.
4. Modifica la politica.
5. Fai clic su **Salva**.

Quando modifichi l'accesso per un utente o un gruppo, potresti ricevere un messaggio relativo al non consentimento delle politiche duplicate. Se stai modificando una politica esistente e le modifiche apportate sono in conflitto con l'accesso già assegnato, puoi scegliere di modificare la politica che stai modificando al momento per fornire un accesso differente, oppure puoi andare alla politica esistente in conflitto per controllare e apportare le modifiche se necessario. Potresti voler eliminare la politica che stai modificando, se esiste già una politica duplicata che soddisfa le tue esigenze.
{: tip}

Per aggiornare una politica utente utilizzando la CLI, puoi utilizzare il comando [ibmcloud iam user-policy-update](/docs/cli/reference/ibmcloud/cli_api_policy.html#ibmcloud_iam_user_policy_update).
```
ibmcloud iam user-policy-update NOME_UTENTE ID_POLITICA [-v, --version VERSIONE] {-f, --file FILE_JSON | [--roles NOME_RUOLO1,NOME_RUOLO2...] [--service-name NOME_SERVIZIO] [--service-instance ISTANZA_SERVIZIO] [--region REGIONE] [--resource-type TIPO_RISORSA] [--resource RISORSA] [--resource-group-name NOME_GRUPPO_RISORSE] [--resource-group-id ID_GRUPPO_RISORSE]}
```
{: codeblock}

## Assegnazione del nuovo accesso
{: #assignaccess}

Per consentire a un utente di accedere a tutte le risorse dell'account con la possibilità di gestire l'accesso degli utenti, creare gruppi di risorse e completare tutte le altre attività di gestione IAM, seleziona l'opzione **Tutti i sevizi abilitati per l'accesso e l'identità** per questa politica con il ruolo **Amministratore** assegnato.
{: tip}

### Accesso alle risorse all'interno di un gruppo di risorse 

Per assegnare l'accesso a tutte le risorse in un gruppo di risorse o a un solo servizio all'interno di un gruppo di risorse, completa la seguente procedura:

1. Dalla barra dei menu, fai clic su **Gestisci** &gt; **Sicurezza** &gt; **Identità e accesso** e seleziona **Utenti**.
2. Dalla riga per l'utente a cui desideri assegnare l'accesso, seleziona il menu **Azioni** e fai quindi clic su **Assegna accesso**.
3. Seleziona **Assegna l'accesso in un gruppo di risorse**.
4. Seleziona un gruppo di risorse.
5. Scegli un ruolo per il campo **Assegna accesso a un gruppo di risorse** per consentire all'utente di visualizzare il gruppo di risorse sul proprio dashboard, modificare il nome del gruppo di risorse o gestire l'accesso dell'utente al gruppo. Puoi selezionare **Nessun accesso** se vuoi che l'utente abbia accesso solo alla risorsa da te specificata e non al gruppo in cui è organizzata.
6. Seleziona un servizio nel gruppo di risorse o scegli di fornire l'accesso a tutti i servizi all'interno del gruppo selezionato.
7. Scegli qualsiasi combinazione di ruoli per assegnare l'accesso desiderato per l'utente. Questo accesso si applica solo alle risorse che hai selezionato per la politica. Non dà accesso al contenitore reale che è il gruppo di risorse.
8. Fai clic su **Assegna**.

### Accesso alle risorse
{: #resourceaccess}

Per assegnare l'accesso a una singola risorsa o a tutte le risorse nell'account, completa la seguente procedura: 

1. Dalla barra dei menu, fai clic su **Gestisci** &gt; **Sicurezza** &gt; **Identità e accesso** e seleziona **Utenti**.
2. Dalla riga per l'utente a cui desideri assegnare l'accesso, seleziona il menu **Azioni** e fai quindi clic su **Assegna accesso**.
3. Seleziona **Assegna l'accesso alle risorse**.
4. Seleziona un servizio o seleziona **Tutti i servizi abilitati per l'accesso e l'identità**.
5. Seleziona **Tutte le regioni correnti** su una specifica regione, se ti viene richiesto. 
6. Seleziona **Tutte le istanze del servizio correnti** o una specifica istanza del servizio.
7. A seconda del servizio che hai selezionato, potresti visualizzare i seguente campi. Se non immetti valori per questi campi, la politica viene assegnata a livello dell'istanza del servizio anziché a livello del bucket. 
    * **Tipo di risorsa**: immetti **bucket**.
    * **ID risorsa**: immetti il nome del tuo bucket.
8. Scegli qualsiasi combinazione di ruoli per assegnare l'accesso desiderato per l'utente.
9. Fai clic su **Assegna**.

Potresti ricevere un messaggio che indica che esiste già una politica per i dettagli che hai selezionato. Se stai creando una politica con gli stessi dettagli e ruoli, ti viene richiesto di apportare modifiche alla nuova politica poiché non sono consentite politiche duplicate. Se stai creando una politica con gli stessi dettagli ma con assegnazioni di ruoli differenti rispetto a una politica esistente, ti viene richiesto di controllare e aggiornare la politica esistente con le assegnazioni dei ruoli che vuoi assegnare.
{: tip}




## Rimozione dell'accesso

1. Dalla barra dei menu, fai clic su **Gestisci** &gt; **Sicurezza** &gt; **Identità e accesso** e seleziona **Utenti**.
2. Seleziona il nome dell'utente per il quale vuoi rimuovere l'accesso.
3. Dalla riga per la politica che vuoi rimuovere, seleziona il menu **Azioni** e fai quindi clic su **Rimuovi**.
4. Riesamina i dettagli della politica utente che stai per rimuovere e quindi conferma facendo clic su **Rimuovi**.

Per rimuovere una politica utente utilizzando la CLI, puoi utilizzare il comando [ibmcloud iam user-policy-delete](/docs/cli/reference/ibmcloud/cli_api_policy.html#ibmcloud_iam_user_policy_delete).
```
ibmcloud iam user-policy-delete ID_UTENTE ID_POLITICA [-f, --force]
```
{: codeblock}

## Controllo del tuo accesso assegnato

Se devi controllare il tuo accesso assegnato in un account a cui sei stato aggiunto, completa la seguente procedura:

1. Dalla barra dei menu, fai clic su **Gestisci** &gt; **Sicurezza** &gt; **Identità e accesso** e seleziona **Utenti**.
2. Seleziona il tuo nome.
3. Controlla il tuo accesso assegnato nella sezione **Politiche di accesso**.

Se hai bisogno di ulteriore accesso, devi contattare il proprietario dell'account per aggiornare il tuo accesso o contattare l'amministratore del servizio o dell'istanza del servizio per aggiornare la politica di accesso Cloud IAM.
