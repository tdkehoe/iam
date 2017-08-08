---

copyright:

  year: 2015, 2016
  
lastupdated: "2017-06-20"

---

{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:screen: .screen}
{:new_window: target="_blank"}

# Ruoli utente e autorizzazioni
{: #userroles}

<!-- staging only content in the service policy roles table. Do not move entire topic to production -->

Puoi gestire gli utenti attraverso i servizi della piattaforma e dell'infrastruttura {{site.data.keyword.Bluemix_notm}} dalla pagina **Utenti** relativa al tuo account. Per accedere alla pagina Utenti, dal menu {{site.data.keyword.Bluemix_notm}}, fai clic su **Gestione** &gt; **Account** &gt; **Utenti**. I proprietari dell'account eseguono tutte le operazioni sulle organizzazioni e sugli spazi, compresa la gestione degli utenti e dei loro ruoli assegnati. I gestori dell'organizzazione e i gestori dello spazio dispongono anche dell'accesso per gestire i ruoli. 
{:shortdesc}

Se sei un utente aggiunto all'account di un'altra persona e vuoi visualizzare i tuoi ruoli assegnati e le tue autorizzazioni, vai a **Gestisci** &gt; **Sicurezza** &gt; **Identità e accesso** &gt; **Utenti** e fai clic sul tuo nome.

## Ruoli dell'account
{: #userrolesinfo}

A livello di account, esistono due ruoli che abilitano l'accesso a funzioni di gestione dell'account differenti:

| Ruolo dell'account | Autorizzazioni |
|----------------|---------|
|Proprietario | Un proprietario per l'account ha accesso al suo profilo, al dashboard di utilizzo e agli utenti, alle informazioni di fatturazione e alle notifiche di spesa. Dalla pagina Utenti, il proprietario può invitare nuovi utenti e regolare i ruoli. Il proprietario può anche aggiungere dei crediti promozionali, impostare o modificare il limite di fatturazione, impostare l'accesso al servizio e gestire organizzazioni e spazi. |
|Membro | Un membro ha accesso al suo profilo e alla pagina Utenti che visualizza gli utenti attivi nell'account, i crediti dell'account e i limiti di fatturazione nell'intestazione {{site.data.keyword.Bluemix_notm}}.  |
{:caption="Tabella 1. Ruoli e autorizzazioni dell'account" caption-side="top"}

Tutti i nuovi utenti vengono aggiunti come membri dell'account. Puoi assegnare i ruoli organizzazione e spazio agli invitati per abilitare specifiche viste e autorizzazioni in {{site.data.keyword.Bluemix_notm}}. Dopo che gli invitati hanno accettato l'invito e si sono uniti a {{site.data.keyword.Bluemix_notm}}, puoi modificarne i ruoli nella pagina Utenti.

## Ruoli Cloud Foundry
{: #cfroles}

I ruoli Cloud Foundry includono le autorizzazioni di accesso per le organizzazioni e gli spazi definiti nell'account. I ruoli Cloud Foundry non abilitano le autorizzazioni utente per completare le azioni nel contesto di un servizio. I seguenti ruoli possono essere assegnati a livello dell'organizzazione:

| Ruolo organizzazione | Autorizzazioni |
|-------------------|-------------|
|Gestore | I gestori dell'organizzazione possono creare, visualizzare, modificare o eliminare gli spazi nell'organizzazione, visualizzare l'utilizzo e la quota dell'organizzazione, invitare utenti all'organizzazione, gestire chi ha accesso all'organizzazione e i loro ruoli al suo interno e gestire i domini personalizzati per l'organizzazione. |
|Gestore fatturazione | I gestori fatturazione possono visualizzare le informazioni sull'utilizzo di runtime e servizi per l'organizzazione nella pagina Dashboard di utilizzo.  |
|Revisore | I revisori organizzazione possono visualizzare il contenuto di applicazioni e servizi nell'organizzazione. I revisori possono anche visualizzare gli utenti nell'organizzazione e i ruoli ad essi assegnati, nonché la quota per l'organizzazione. Al momento dell'invito, a tutti gli utenti viene assegnato il ruolo di revisore per impostazione predefinita. Una volta che l'utente accetta l'invito, puoi aggiornare questo ruolo a gestore o gestore fatturazione. |
{:caption="Tabella 2. Ruoli e autorizzazioni dell'organizzazione" caption-side="top"}

I seguenti ruoli possono essere assegnati a livello dello spazio:

| Ruolo spazio | Autorizzazioni |
|------------|-------------|
|Gestore | I gestori spazio possono aggiungere utenti esistenti e gestire i ruoli nello spazio. Il gestore spazio può anche visualizzare il numero di istanze, i bind di servizio e l'utilizzo delle risorse per ciascuna applicazione nello spazio. |
|Sviluppatore | Gli sviluppatori spazio possono creare, eliminare e gestire applicazioni e servizi nello spazio. Alcune delle attività di gestione includono la distribuzione di applicazioni, l'avvio e l'arresto di applicazioni, la rinominazione di un'applicazione, l'eliminazione di un'applicazione, la rinominazione di uno spazio, il bind o l'annullamento del bind di un servizio a un'applicazione, la visualizzazione del numero di istanze, i bind di servizi e l'utilizzo di risorse per ciascuna applicazione nello spazio. Inoltre, lo sviluppatore spazio può associare un URL interno o esterno a un'applicazione nello spazio.   |
|Revisore | I revisori spazio hanno un accesso in sola lettura a tutte le informazioni sullo spazio, quali le informazioni sul numero di istanze, i bind di servizio e l'utilizzo di risorse per ciascuna applicazione nello spazio. |
{:caption="Tabella 3. Ruoli e autorizzazioni dello spazio" caption-side="top"}

**Nota**: gli utenti a cui nello spazio è assegnato il ruolo di gestore o sviluppatore possono accedere alla variabile di ambiente VCAP_SERVICES. Tuttavia, un utente a cui è assegnato il ruolo di revisore non può accedere a VCAP_SERVICES.

## Politiche e ruoli per la gestione di identità e accesso
{: #iamusermanpol}

Ai proprietari dell'account viene assegnato automaticamente il ruolo di amministratore di accesso account per la gestione di Identità e accesso che ti consente di assegnare e gestire le politiche di servizio. Questo tipo di controllo di accesso permette l'assegnazione di politiche per ogni servizio o istanza di servizio per consentire livelli di accesso per la gestione delle risorse e degli utenti all'interno del contesto assegnato.

### Politiche di servizio

Una politica assegna uno o più ruoli a una serie di risorse utilizzando una combinazione di attributi per definire la serie di risorse applicabile. Quando assegni una politica a un utente, specifichi prima il servizio. Puoi quindi selezionare un ruolo o i ruoli da assegnare. Potrebbero essere disponibili ulteriori opzioni di configurazione, a seconda del servizio che selezioni.

Puoi assegnare e gestire le politiche se hai il ruolo appropriato. La seguente tabella mostra le attività di gestione della politica e il ruolo richiesto per ognuna di esse.

| Azione | Ruolo richiesto |
|----------|---------|
| Creare politiche su un account per tutti i servizi e tutte le istanze | Amministratore di accesso account |
| Creare una politica su un servizio in un account | Amministratore di accesso account o amministratore del servizio nell'account |
| Creare un'istanza del servizio | Amministratore di accesso account o amministratore o editor del servizio nell'account|
| Creare una politica su un'istanza del servizio | Amministratore di accesso account o amministratore del servizio nell'account o amministratore dell'istanza del servizio |
{: caption="Tabella 4. Attività amministrative per la gestione delle politiche dei Servizi abilitati per l'accesso e l'identità" caption-side="top"}

### Ruoli delle politiche di servizio
{: #iamusermanrol}

I ruoli sono una raccolta di azioni; le azioni che vengono associate a questi ruoli sono specifiche per servizio. Fai riferimento alla documentazione del servizio selezionato per ulteriori dettagli su quali tipi di azioni sono consentiti da ogni ruolo.

In aggiunta alle descrizioni dei ruoli fornite nella console, la seguente tabella fornisce gli esempi di alcune attività che gli utenti assegnati ad ogni ruolo possono eseguire per il servizio IBM Container.  

**Nota**: il ruolo operatore non è al momento disponibile per il servizio IBM Container. L'esempio che segue è incluso solo a scopo informativo.

| Ruolo | Descrizione delle azioni | Azioni di esempio|
|:-----------------|:-----------------|:-----------------|
| Visualizzatore | Esegue le azioni che non modificano lo stato; solo le azioni in lettura | <ul><li>Elencare i cluster</li><li>Visualizzare i dettagli per un cluster</li></ul>|
| Editor | Esegue le azioni che modificano la stato e creano o eliminano le risorse secondarie |<ul><li>Aggiungere o rimuovere i nodi di lavoro</li><li>Riavviare o ricaricare i nodi di lavoro</li><li>Eseguire il bind di un servizio a un cluster</li></ul> |
| Operatore | Esegue le azioni richieste per configurare e gestire le risorse. | <ul><li>Aggiungere o rimuovere i nodi di lavoro</li><li>Riavviare o ricaricare i nodi di lavoro</li><li>Eseguire il bind di un servizio a un cluster</li></ul> |
| Amministratore | Esegue tutte le azioni, inclusa la capacità di gestire il controllo dell'accesso |<ul><li>Rimuovere un cluster</li><li>Creare un cluster</li><li>Aggiorna le politiche di accesso utente</li><li>Tutte le azioni che possono essere eseguite da un visualizzatore, un operatore e un editor</li></ul>|
{: caption="Tabella 5. Ruoli utente e azioni di esempio" caption-side="top"}


## Autorizzazioni dell'infrastruttura
{: #infrapermissions}

Quando inviti un utente, puoi impostare le seguenti autorizzazioni: 

| Autorizzazione infrastruttura | Descrizione delle azioni |
|---------------------------|------------------------|
|Solo visualizzazione | Gli utenti con questa autorizzazione possono soltanto visualizzare gli elementi nel sistema.|
|Utente base | Gli utenti con questa autorizzazione possono eseguire le azioni di base nel sistema, come aggiungere un ticket e gestire i dispositivi. |
|Super utente | Gli utenti con questa autorizzazione possono eseguire tutte le azioni disponibili nel sistema. |
{:caption="Tabella 6. Autorizzazioni dell'infrastruttura" caption-side="top"}

Ulteriori autorizzazioni possono essere impostate dopo che l'utente ha accettato l'invito.
