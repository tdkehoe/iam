---

copyright:

  years: 2015, 2017
lastupdated: "2017-08-30"

---

{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:screen: .screen}
{:new_window: target="_blank"}

# Gestione delle chiavi API
{: #manapikey}

Una chiave API è un codice che viene trasmesso dai programmi informatici che richiamano un'interfaccia di programmazione delle applicazioni (API) per identificare il programma chiamante, il suo sviluppatore o il suo utente nel sito Web. Le chiavi API vengono utilizzate per tracciare e controllare l'utilizzo dell'API, ad esempio per prevenire l'uso dannoso o l'abuso dell'API (come definito probabilmente dai termini di servizio). La chiave API spesso funge sia da identificativo univoco che da token segreto per l'autenticazione e generalmente dispone di una serie di diritti di accesso specifici per l'utente ad essa associata. Le chiavi API possono essere basate sul sistema UUID (universally unique identifier) per garantire che siano univoche per ogni utente.

Un utente federato o meno può creare una chiave API da utilizzare nella CLI o come parte dell'automazione ad accedere con il tuo nome utente. Puoi utilizzare la IU {{site.data.keyword.Bluemix_notm}} o la CLI {{site.data.keyword.Bluemix_notm}} per gestire le tue chiavi API attraverso l'elenco, la creazione, l'aggiornamento o l'eliminazione delle chiavi. Per gestire le tue chiavi API {{site.data.keyword.Bluemix_notm}} nella IU, vai a **Gestisci** &gt; **Sicurezza** &gt; **Chiavi API Bluemix** per visualizzare un elenco delle chiavi API con descrizioni e date. Quindi, da questa pagina puoi creare, modificare o eliminare le chiavi API. E per un elenco completo dei comandi CLI disponibili, consulta [`bluemix iam api-keys`](/docs/cli/reference/bluemix_cli/bx_cli.html#bluemix_iam).

Come [utente federato](/docs/admin/adminpublic.html#federatedid), puoi usare una chiave API per eseguire l'accesso utilizzando la variabile di ambiente `BLUEMIX_API_KEY`. Per ulteriori informazioni sull'utilizzo di una chiave API per l'accesso, vedi la documentazione per il comando [ `bluemix login` della CLI {{site.data.keyword.Bluemix_notm}}](/docs/cli/reference/bluemix_cli/bx_cli.html#bluemix_login) e il [comando `cf login` della CLI cf](/docs/cli/reference/cfcommands/index.html#cf_login).

## Creazione di una chiave API

In qualità di utente {{site.data.keyword.Bluemix_notm}}, potresti voler utilizzare una chiave API quando abiliti un programma o uno script senza distribuire la tua password allo script. Un vantaggio di utilizzare una chiave API può essere che un utente o un'organizzazione può creare più chiavi API per programmi diversi e le chiavi API possono essere eliminate in modo indipendente se compromesse senza interferire con altre chiavi API o con l'utente.

Per creare una chiave API nella IU:

1. Vai a **Gestisci** &gt; **Sicurezza** &gt; **Chiavi API Bluemix**.
2. Fai clic su **Crea chiave API**.
3. Immetti un nome e una descrizione per la tua chiave API.
4. Fai clic su **Crea chiave API**.
5. Infine, fai clic su **Mostra** per visualizzare la chiave API e per copiarla e salvarla per un uso successivo oppure fai clic su **Scarica chiave API**.

**Nota**: la chiave API è disponibile per la visualizzazione o il download solo durante la fase di creazione. Se la chiave API viene persa, dovrai crearne una nuova.

Per creare una chiave API utilizzando la CLI:

1. Immetti `bluemix iam api-key-create NAME [-d DESCRIPTION] [-f, --file FILE]` nel prompt dei comandi, e specificare un nome, una descrizione, e file per salvare la tua chiave. Ad
esempio:

```
bluemix iam api-key-create MyKey -d "this is my API key" -f key_file
``` 

Dopo aver creato una chiave API utilizzando la CLI, ci sono alcuni modi in cui puoi utilizzarla con bx CLI:

* Immettila con il comando `bx login`
```
 bx login --apikey <your api key>
```
* Crea un file chiave API da utilizzare con il comando `bx login`: 
 ```
 bx login --apkey @apikeyfile
 ```
 `apikeyfile` viene creato utilizzando l'opzione `—file` nel comando `bx iam api-key-create`.
* Nel tuo prompt dei comandi, puoi impostare la variabile di ambiente immettendo `BLUEMIX_API_KEY=<your api key>` e quindi immettendo `bx login`.
* Oppure, se desideri evitare bx CLI e soltanto accedere alla CLI cf utilizzando la tua chiave API, immetti:
 ```
 cf login -u apikey -p <yourapikey>
 ```
  In questa opzione, utilizzi il nome utente di `apikey` e la password è la tua `apikey`. Ora, puoi utilizzare `apikey` in altri strumenti come Eclipse o in altri posti che richiedono che `cf login` accetti solo il nome utente e la password.

## Modifica di una chiave API.

Se desideri modificare il nome o la descrizione di una chiave API, completa le seguenti istruzioni nella IU o nella CLI.

Per modificare una chiave API:

1. Vai a **Gestisci** &gt; **Sicurezza** &gt; **Chiavi API Bluemix**.
2. Dal menu **Azioni** di una chiave API elencata nella tabella, fai clic su **Modifica nome e descrizione** 
3. Aggiorna le informazioni per la tua chiave API.
4. Fai clic su **Aggiorna chiave API**.

Per modificare una chiave API utilizzando la CLI:

1. Immetti `bluemix iam api-key-update NAME [-n NAME] [-d DESCRIPTION]` nel tuo prompt dei comandi, specificando il vecchio nome, il nuovo nome e la nuova descrizione della chiave. Ad
esempio:

```
bluemix iam api-key-update MyCurrentName -n MyNewName -d "the new description of my key"
```

## Eliminazione di una chiave API

Se stai utilizzando una strategia di rotazione della chiave, potresti voler eliminare una chiave vecchia e sostituirla con una nuova.

Per eliminare una chiave API: 

1. Vai a **Gestisci** &gt; **Sicurezza** &gt; **Chiavi API Bluemix**.
2. Dal menu **Azioni** di una chiave API elencata nella tabella, fai clic su **Elimina**.
3. Conferma infine l'eliminazione facendo clic su **Elimina chiave**.

Per eliminare una chiave API utilizzando la CLI:
1. Immetti `bluemix iam api-key-delete NAME` nel tuo prompt dei comandi, specificano il nome della tua chiave che deve essere eliminata.
