---

copyright:

  years: 2015, 2018
lastupdated: "2018-06-01"

---

{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:screen: .screen}
{:new_window: target="_blank"}

# Gestione delle chiavi API di un ID servizio
{: #serviceidapikeys}

Gli ID servizio vengono creati per abilitare l'accesso ai tuoi servizi {{site.data.keyword.Bluemix_notm}} dalle applicazioni ospitate sia all'interno che all'esterno di {{site.data.keyword.Bluemix_notm}}. Le chiavi API vengono utilizzate da un'applicazione per eseguire l'autenticazione come uno specifico ID servizio e ottenere l'accesso associato a tale ID servizio.

Dopo che hai creato un ID servizio, puoi iniziare a creare le chiavi API e ad assegnare le politiche di servizio. Ciascuna politica specifica il livello di accesso consentito quando la chiave API viene utilizzata per eseguire l'autenticazione presso i tuoi servizi. Per ulteriori informazioni sulla creazione di un ID servizio e l'assegnazione di politiche, consulta [Creazione e gestione degli ID servizio](/docs/iam/serviceid.html#serviceids). Per i dettagli sui comandi CLI utilizzati per gestire le chiavi API di un ID servizio, consulta [Comandi per la gestione di politiche e chiavi API](/docs/cli/reference/bluemix_cli/bx_cli.html#bx_commands_iam).

Ogni chiave API associata a un ID servizio eredita la politica che è stata assegnata all'ID servizio. Ad esempio, se vuoi che un'applicazione possa semplicemente visualizzare le risorse in un servizio, devi utilizzare una chiave API associata a un ID servizio che ha una politica assegnata con il ruolo `Visualizzatore`. Se poi vuoi che un'altra applicazione possa avere un accesso completo in un servizio, devi utilizzare una chiave API associata a un secondo ID servizio che ha una politica assegnata con il ruolo `Amministratore`.

Per ulteriori informazioni, vedi [Esempi di come utilizzare un ID servizio](/docs/iam/serviceid.html#examples-of-how-to-use-a-service-id).

## Creazione di una chiave API per un ID servizio

Crea una chiave API da associare a un ID servizio.

1. Vai a **Gestisci** &gt; **Sicurezza** &gt; **Identità e accesso** &gt; **ID servizio**.
2. Se non hai già un ID servizio creato, crea l'ID servizio.
3. Dal menu **Azioni**, vai all'opzione **Gestisci ID servizio**.
4. Fai clic su **Crea** nella sezione delle chiavi API.
5. Aggiungi un nome e una descrizione per identificare facilmente la chiave API.
6. Fai clic su **Crea**.
7. Salva la tua chiave API copiandola o scaricandola in un'ubicazione sicura.

**Nota**: per motivi di sicurezza, la chiave API è disponibile per essere copiata o scaricata solo durante la fase di creazione. Se la chiave API viene persa, dovrai crearne una nuova.

## Aggiornamento di una chiave API per un ID servizio

Puoi aggiornare una chiave API modificando il nome o la descrizione utilizzati per identificare la chiave nell'IU.

1. Vai a **Gestisci** &gt; **Sicurezza** &gt; **Identità e accesso** &gt; **ID servizio**.
2. Se non hai già un ID servizio creato, crea l'ID servizio.
3. Dal menu **Azioni**, vai all'opzione **Gestisci ID servizio**.
4. Dal menu **Azioni** nella sezione delle chiavi API, vai all'opzione **Modifica nome e descrizione**.

## Blocco di una chiave API dell'ID servizio
{: #lockkey}

Per le chiavi API che rappresentano l'identità dell'ID servizio, puoi impedire l'eliminazione della chiave API bloccandola. Un chiave API bloccata viene indicata dall'icona ![icona Bloccato](images/locked.svg "Bloccato") nella IU.

1. Dalla barra dei menu, fai clic su **Gestisci** &gt; **Sicurezza** &gt; **Identità e accesso** e seleziona quindi **ID servizio**.
2. Identifica la riga dell'ID servizio di cui vuoi selezionare una chiave API e seleziona il nome dell'ID servizio. 
3. Seleziona **Chiavi API**.
4. Passa con il mouse sulla riga della chiave API che vuoi bloccare e fai clic sul menu **Azioni** per aprire un elenco di opzioni.
5. Fai clic su **Blocca chiave API**.

Puoi sbloccare la tua chiave API in qualsiasi momento per aggiornare, eliminare o aggiungere una politica di accesso o per rimuovere la chiave API.
{: tip}

### Blocco e sblocco di una chiave API dell'ID servizio con la CLI

Per bloccare una chiave API dell'ID servizio, utilizza il seguente comando: 

```
ibmcloud iam service-api-key-lock (NOME_CHIAVE_API|UUID_CHIAVE_API) (NOME_ID_SERVIZIO|UUID_ID_SERVIZIO) [-f, --force]
```

<strong>Prerequisiti</strong>: Endpoint, Accesso, Destinazione

<strong>Opzioni del comando</strong>:
<dl>
  <dt>NOME_CHIAVE_API (obbligatorio)</dt>
  <dd>Nome della chiave API, esclusivo con UUID_CHIAVE_API</dd>
  <dt>UUID_CHIAVE_API (obbligatorio)</dt>
  <dd>UUID della chiave API, esclusivo con NOME_CHIAVE_API</dd>
  <dt>NOME_ID_SERVIZIO (obbligatorio)</dt>
  <dd>Nome dell'ID servizio, esclusivo con UUID_ID_SERVIZIO</dd>
  <dt>UUID_ID_SERVIZIO (obbligatorio)</dt>
  <dd>UUID dell'ID servizio, esclusivo con NOME_ID_SERVIZIO</dd>
  <dt>-f, --force</dt>
  <dd>Blocca senza conferma</dd>
</dl>

<strong>Esempi</strong>:

Blocca la chiave API del servizio `sample-key` dell'ID servizio `sample-service`:

```
ibmcloud iam service-api-key-lock sample-key sample-service
```

Per sbloccare una chiave API dell'ID servizio, utilizza il seguente comando: 

```
ibmcloud iam service-api-key-unlock (NOME_CHIAVE_API|UUID_CHIAVE_API) (NOME_ID_SERVIZIO|UUID_ID_SERVIZIO) [-f, --force]
```


## Eliminazione di una chiave API per un ID servizio

Puoi eliminare una chiave API associata a un ID servizio. Tuttavia, l'eliminazione di una chiave API attualmente utilizzata da un'applicazione non consentirà più a tale applicazione di eseguire l'autenticazione presso i tuoi servizi.

1. Vai a **Gestisci** &gt; **Sicurezza** &gt; **Identità e accesso** &gt; **ID servizio**.
2. Se non hai già un ID servizio creato, crea l'ID servizio.
3. Dal menu **Azioni**, vai all'opzione **Gestisci ID servizio**.
4. Dal menu **Azioni** nella sezione delle chiavi API, vai all'opzione **Elimina chiave**.
