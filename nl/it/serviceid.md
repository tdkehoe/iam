---

copyright:

  years: 2017, 2018
  
lastupdated: "2018-06-01"

---

{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:screen: .screen}
{:new_window: target="_blank"}
{:tip: .tip}

# Creazione e utilizzo degli ID servizio 
{: #serviceids}

Un ID servizio identifica un servizio o un'applicazione analogamente a come un ID utente identifica un utente. Un ID servizio da te creato può essere utilizzato per abilitare un'applicazione esterna a {{site.data.keyword.Bluemix_notm}} ad accedere ai tuoi servizi {{site.data.keyword.Bluemix_notm}}. Puoi assegnare delle specifiche politiche di accesso all'ID servizio che limitano le autorizzazioni per l'utilizzo di specifici servizi o anche combinare le autorizzazioni per l'accesso a servizi differenti. Poiché gli ID servizio non sono collegati a uno specifico utente, se capita che un utente lasci un'organizzazione e venga eliminato dall'account, l'ID servizio rimane, garantendo che la tua applicazione o il tuo servizio continuino a essere attivi e in esecuzione.

Quando crei un ID servizio, crei un nome univoco e una descrizione per te facili da identificare e gestire nell'IU. Dopo che hai creato il tuo ID servizio, puoi creare delle chiavi API specifiche per ciascun ID servizio che la tua applicazione può utilizzare per l'autenticazione presso i tuoi servizi {{site.data.keyword.Bluemix_notm}}. Per garantire che la tua applicazione disponga dell'accesso appropriato per eseguire l'autenticazione presso i tuoi servizi {{site.data.keyword.Bluemix_notm}}, utilizza le politiche di accesso assegnate a ciascun ID servizio che crei. 

Le politiche di accesso associate a un ID servizio abilitano delle specifiche azioni che possono essere eseguite quando tale ID servizio viene utilizzato per accedere a uno specifico servizio. Un singolo ID servizio può essere assegnato a più politiche che definiscono il livello di accesso consentito quando si accede a più servizi di identità e abilitati all'accesso. Ad esempio, hai due servizi con due istanze del servizio ciascuno. Puoi ad esempio assegnare il ruolo `Visualizzatore` per tutte le istanze disponibili di un servizio e assegnare il ruolo `Editor` per una sola istanza di un secondo servizio. In questo modo, puoi personalizzare l'accesso a più servizi ma utilizzare una singola chiave API per l'autenticazione per tutti. 


## Creazione di un ID servizio

Per creare un ID servizio, vai a **Gestisci** &gt; **Sicurezza** &gt; **Identità e accesso** e seleziona quindi **ID servizio**. Attieniti alla procedura per creare un nome e una descrizione per il tuo ID servizio. Usa quindi il menu **Azioni** per gestire il tuo ID servizio. Puoi iniziare assegnando una politica e creando le chiavi API. Per ulteriori informazioni sulla gestione delle chiavi API, consulta [Gestione delle chiavi API di un ID servizio](/docs/iam/serviceid_keys.html#serviceidapikeys). 

## Aggiornamento di un ID servizio

Puoi aggiornare un ID servizio modificando il nome e la descrizione in qualsiasi momento. Puoi anche eliminare e creare nuove chiavi API come necessario oppure aggiornare le politiche di accesso assegnate. Tuttavia, qualsiasi modifica da te apportata a un ID servizio esistente, quali la modifica delle politiche assegnate o l'eliminazione di una chiave API attualmente utilizzata, potrebbe causare delle interruzioni del servizio per le applicazioni che utilizzano tale ID servizio. 

## Blocco di un ID servizio

Per evitare una situazione in cui il tuo ID servizio venga eliminato causando delle interruzioni agli utenti del tuo servizio, disponi dell'opzione di bloccare l'ID servizio utilizzando la IU o la CLI. Bloccare un ID servizio impedisce anche che si apportino modifiche o assegnazioni delle politiche di accesso ed evita anche che vengano create o eliminate le chiavi API associate all'ID servizio. In aggiunta alla capacità di bloccare l'ID servizio, puoi [bloccare singole chiavi API](/docs/iam/serviceid_keys.html#lockkey) associate ad ogni ID servizio nel tuo account. 

Gli ID servizio bloccati non possono essere eliminati e le politiche di accesso non possono essere aggiornate. Tuttavia, gli ID servizio bloccati possono ancora essere rimossi da qualsiasi gruppo di accesso a cui sono stati aggiunti. Questo significa che l'accesso assegnato all'ID dalla sua appartenenza a un gruppo di accesso, viene rimosso quando l'ID servizio viene rimosso dal gruppo di accesso.
{: tip}

### Fornire l'accesso utente per blocccare gli ID servizio

In modo che un utente abbia l'accesso per bloccare o sbloccare gli ID servizio e le chiavi API associate agli ID servizio, gli deve venire assegnata una politica di accesso specifica. Due tipi di politiche di accesso possono concedere l'accesso appropriato:

* Accesso a tutti gli ID servizio nell'account
* Accesso a un ID servizio specifico nell'account

Per assegnare l'accesso a tutti gli ID servizio nell'account, imposta una politica di accesso con i seguenti dettagli: 

* Ruolo di editor o amministratore 
* Servizio di identità IAM

Per assegnare l'accesso a un ID servizio specifico nell'account, imposta una politica di accesso con i seguenti dettagli: 

* Ruolo di editor o amministratore
* Servizio di identità IAM
* Specifica `serviceid` nel campo **Tipo di risorsa**  
* Specifica l'identificativo dell'ID servizio nel campo **ID risorsa** 

Per ottenere l'identificativo di un ID servizio specifico, vai a **Gestisci** > **Sicurezza** > **Identità & accesso** e seleziona quindi **ID servizio**. Seleziona l'ID servizio di cui vuoi visualizzare i dettagli e copia il valore ID.
{: tip}

### Blocco di un ID servizio dalla IU

Un ID servizio bloccato viene indicato dall'icona ![icona Bloccato](images/locked.svg "Bloccato").

1. Dalla barra dei menu, fai clic su **Gestisci** &gt; **Sicurezza** &gt; **Identità e accesso** e seleziona quindi **ID servizio**.
2. Identifica la riga dell'ID servizio che vuoi bloccare e seleziona **Blocca l'ID del servizio** dal menu **Azioni**.

Per sbloccare un ID servizio, selezionalo dalla tabella che vuoi sbloccare e seleziona **Sblocca l'ID del servizio** dal menu **Azioni**. Devi avere il livello di accesso appropriato per sbloccare un ID servizio.
{: tip}

### Blocco e sblocco di un ID servizio utilizzando la CLI

Per bloccare un ID servizio, utilizza il seguente comando:

```
ibmcloud iam service-id-lock (NOME|UUID) [-f, --force]
```

Opzioni del comando:

<dl>
  <dt>NOME (obbligatorio)</dt>
  <dd>Nome del servizio, esclusivo con UUID</dd>
  <dt>UUID (obbligatorio)</dt>
  <dd>UUID del servizio, esclusivo con NOME</dd>
  <dt>-f, --force</dt>
  <dd>Blocca senza conferma</dd>
</dl>

<strong>Esempi</strong>:

Blocca ID servizio `sample-test` senza conferma

```
ibmcloud iam service-id-lock sample-test -f
```

Blocca ID servizio `ServiceId-cb258cb9-8de3-4ac0-9aec-b2b2d27ac976`

```
ibmcloud iam service-id-lock ServiceId-cb258cb9-8de3-4ac0-9aec-b2b2d27ac976
```

Per sbloccare un ID servizio, utilizza il seguente comando:

 ```
ibmcloud iam service-id-unlock (NOME|UUID) [-f, --force]
```

Opzioni del comando:

<dl>
  <dt>NOME (obbligatorio)</dt>
  <dd>Nome del servizio, esclusivo con UUID</dd>
  <dt>UUID (obbligatorio)</dt>
  <dd>UUID del servizio, esclusivo con NOME</dd>
  <dt>-f, --force</dt>
  <dd>Sblocca senza conferma</dd>
</dl>

<strong>Esempi</strong>:

Sblocca ID servizio `sample-test` senza conferma

```
ibmcloud iam service-id-unlock sample-test -f
```

Sblocca ID servizio `ServiceId-cb258cb9-8de3-4ac0-9aec-b2b2d27ac976`

```
ibmcloud iam service-id-unlock ServiceId-cb258cb9-8de3-4ac0-9aec-b2b2d27ac976
```



## Esempi di come utilizzare un ID servizio

I seguenti sono esempi di come un ID servizio viene utilizzato con i servizi {{site.data.keyword.objectstorageshort}} e Cloud SQL Query.

- {{site.data.keyword.objectstorageshort}} - [Introduzione](/docs/services/cloud-object-storage/getting-started-cli.html#getting-started-cli-).
- Cloud SQL Query - [How to use the SQL Query REST API ![Icona link esterno](../icons/launch-glyph.svg)](https://www.youtube.com/embed/s6S4AdJItHk?rel=0){: new_window}.

