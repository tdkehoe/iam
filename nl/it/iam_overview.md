---

copyright:

  years: 2017, 2018

lastupdated: "2018-04-02"

---

{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:screen: .screen}
{:new_window: target="_blank"}

# Concetti di IAM
{: #iamconcepts}

## Identità

Il concetto di identità in {{site.data.keyword.Bluemix_notm}} IAM è costituito dai seguenti componenti:

<dl>
<dt>Identità dell'utente</dt>
<dd>Tutti gli utenti sono identificati dal proprio ID IBM.</dd>
<dt>Identità di servizi e di applicazioni</dt>
<dd>Gli ID servizio rappresentano la funzione di Cloud IAM utilizzata per fornire un'identità separata per i servizi e le applicazioni. Puoi creare un ID servizio che venga utilizzato da un'applicazione che deve accedere ai tuoi servizi {{site.data.keyword.Bluemix_notm}} in modo che non sia necessario utilizzare le credenziali dei singoli utenti.</dd>
<dt>Chiavi API</dt>
<dd>Le chiavi API della piattaforma sono disponibili tramite Cloud IAM per eseguire l'autenticazione tramite API o CLI come utente o ID servizio. Queste chiavi API vengono fornite tramite Cloud IAM e pertanto non possono essere utilizzate generalmente per l'autenticazione con l'ID IBM all'esterno di IBM Cloud. </dd>
<dt>Risorse</dt>
<dd>Le risorse {{site.data.keyword.Bluemix_notm}} sono identificate dai loro nomi di risorsa cloud (CRN). Per ulteriori informazioni, vedi [Nomi delle risorse cloud](/docs/overview/crn.html#crn).</dd>
</dl>

## Gestione accesso

Il concetto di gestione dell'accesso in {{site.data.keyword.Bluemix_notm}} è costituito da alcuni componenti correlati, inclusi utenti, risorse, politiche, ruoli, azioni e il sistema di controllo Cloud IAM, che consentono agli utenti di intraprendere azioni sulle risorse all'interno di un account.

Puoi esaminare il seguente elenco per ulteriori informazioni su questi componenti Cloud IAM:

<dl>
<dt>Utenti</dt>
<dd>Tutti gli utenti all'interno di un account sono identificati dai loro ID IBM. Gli utenti possono essere invitati all'account e avere accesso alle risorse. L'accesso può essere assegnato a singole risorse, fino al livello di istanza, o a un insieme di risorse che sono organizzate in un gruppo di risorse dell'account.</dd>
<dt>Gruppo di accesso </dt>
<dd>Un gruppo di utenti e di ID del servizio può essere creato dal proprietario dell'account in modo che lo stesso accesso possa essere assegnato a tutte le entità all'interno del gruppo con una sola politica.</dd>
<dt>Risorse</dt>
<dd>Le risorse dell'account sono le offerte dei servizi con provisioning selezionate dal catalogo o le risorse specifiche all'interno di un'istanza del servizio.</dd>
<dt>Politiche</dt>
<dd>Le politiche sono il modo in cui gli utenti o gli ID servizio nell'account ricevono l'autorizzazione per accedere alle risorse dell'account. Le politiche includono un oggetto, una destinazione e un ruolo. L'oggetto è l'utente o l'ID servizio a cui fornisci l'accesso. La destinazione della politica è la risorsa per la quale vuoi fornire l'accesso. I ruoli sono il modo per definire il livello di accesso o le azioni consentite sulla destinazione della politica. Ci sono tre tipi di politiche che consentono l'accesso alle risorse dell'account: una politica del gruppo di risorse, una politica dell'istanza della risorsa e una politica a livello di account per l'accesso a tutti i servizi abilitati per l'accesso e l'identità. A seconda delle tue selezioni, potrebbero esserci opzioni di configurazione personalizzate come la definizione dell'accesso alle risorse in una regione specifica o la definizione dell'accesso al livello granulare di una risorsa specifica del servizio all'interno di un'istanza.</dd>
<dt>Ruoli</dt>
<dd>I ruoli di accesso Cloud IAM consentono a un utente di completare attività specifiche sulla risorsa definita nella politica. Esistono due tipi di ruoli di accesso: gestione della piattaforma e accesso al servizio. I ruoli di gestione della piattaforma definiscono le azioni consentite per la gestione delle risorse a livello di piattaforma, tra cui l'accesso degli utenti, la creazione di istanze e ID servizio e la gestione dei gruppi di risorse. Mentre i ruoli di accesso al servizio definiscono le azioni consentite nel contesto dell'utilizzo del servizio. Questi ruoli sono personalizzati in base al servizio selezionato nella politica.</dd>
<dt>Azioni</dt>
<dd>Le azioni vengono associate ai ruoli Cloud IAM per consentire agli utenti di eseguire solo attività specifiche quando vengono assegnati i diversi ruoli. Le azioni consentite per ciascun ruolo potrebbero cambiare in base al servizio a cui si accede poiché ogni servizio definisce il modo in cui quel ruolo viene associato all'utilizzo del servizio. </dd>
<dt>Sistema di gestione degli accessi</dt>
<dd>Il sistema di controllo di Cloud IAM consente o nega le azioni degli utenti nel contesto di un servizio in base alla politica assegnata. Quando un utente tenta di completare un'azione specifica, il sistema di controllo utilizza gli attributi definiti nella politica per determinare se l'utente dispone dell'autorizzazione per eseguire tale attività.</dd>
</dl>
