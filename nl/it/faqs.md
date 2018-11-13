---



copyright:

  years: 2018

lastupdated: "2018-10-30"



---

{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:screen: .screen}
{:new_window: target="_blank"}
{:tip: .tip}

# Domande frequenti
{: #iamfaq}

## Cos'è {{site.data.keyword.cloud_notm}} Identity and Access Management? 
{: #whatisiam}

IAM (Identity and Access Management) ti consente di autenticare in modo protetto gli utenti per i servizi di piattaforma e di controllare l'accesso alle risorse nella piattaforma {{site.data.keyword.cloud_notm}}. Un insieme di servizi IBM Cloud è abilitato ad utilizzare Cloud IAM per il controllo dell'accesso. Tali servizi sono organizzati in gruppi di risorse all'interno del tuo account per abilitare la concessione agli utenti di un accesso rapido e facile e più di una risorsa per volta. Le politiche di accesso Cloud IAM vengono utilizzate per assegnare agli utenti e agli ID servizio l'accesso alle risorse all'interno del tuo account. Per ulteriori informazioni, vedi [{{site.data.keyword.cloud_notm}} Identity and Access Management](/docs/iam/index.html#iamoverview).

## Cos'è un servizio abilitato a IAM?
{: #iam-enabled}

Un servizio abilitato a IAM deve trovarsi in un gruppo di risorse e l'accesso al servizio viene concesso utilizzando le politiche di accesso IAM. Quando crei un servizio abilitato a IAM dal catalogo,devi assegnarlo ad un gruppo di risorse. Per ulteriori informazioni, vedi [Che cosa è una risorsa?](/docs/resources/acct_resources.html#resource)

{{site.data.keyword.containerlong_notm}} è l'unica eccezione; è controllato dall'accesso IAM ma è sempre assegnato al gruppo di risorse predefinito. Pertanto non ti viene offerta l'opzione di sceglierne uno quando lo crei dal catalogo. Non può inoltre essere assegnato a un altro gruppo di risorse


## IAM e Cloud Foundry sono correlati?
{: #iam-cloudfoundry}

Non sono correlati. Cloud Foundry è una piattaforma open source che utilizza le organizzazioni, gli spazi e i ruoli Cloud Foundry per la gestione degli accessi. IAM è il modo sicuro per autenticare gli utenti per i servizi di piattaforma e per controllare l'accesso alle risorse in tutta la piattaforma {{site.data.keyword.cloud_notm}} utilizzando i gruppi di risorse e i ruoli di accesso IAM.

I sistemi di gestione dell'accesso sono completamente diversi. Le risorse IAM appartengono ad un gruppo di risorse e le risorse Cloud Foundry appartengono a un'organizzazione e a uno spazio. Le politiche di accesso IAM vengono utilizzate per fornire l'accesso alle risorse in un gruppo di risorse. I ruoli di organizzazione e spazio di Cloud Foundry sono utilizzati per fornire l'accesso agli utenti alle risorse Cloud Foundry in uno spazio. IAM non ti dà accesso a nulla all'interno degli spazi Cloud Foundry e i ruoli Cloud Foundry non possono concedere l'accesso alle risorse all'interno di un gruppo di risorse.

## Come faccio a scoprire a cosa ho accesso?
{: #iam-access}

Vai a **Gestisci** &gt; **Accesso (IAM)** e seleziona il tuo nome nella colonna Utente. Quindi, a seconda dell'accesso che stai cercando, apri le diverse schede:

* Per determinare quali sono i gruppi di accesso in cui ti trovi, seleziona **Gruppi di accesso**.
* Per l'accesso IAM, seleziona **Politiche di accesso**.
* Per i ruoli Cloud Foundry, seleziona **Accesso Cloud Foundry**.

## Come richiedo l'accesso a una risorsa?
{: #request-access}

Il proprietario dell'account può aggiornare il tuo accesso a qualsiasi risorsa nell'account oppure puoi contattare qualsiasi utente a cui è assegnato il ruolo di amministratore sul servizio o sull'istanza del servizio. 

## Perché devo utilizzare i gruppi di risorse e i gruppi di accesso? 
{: #resource-groups}

Un gruppo di risorse è un contenitore logico per le risorse. Quando viene creata, una risorsa viene assegnata ad un gruppo di risorse e non può essere spostata dopo che è stata aggiunta. 

Un gruppo di accesso viene utilizzato per organizzare facilmente un insieme di utenti e ID servizio in una singola entità per rendere facile le assegnazioni dell'accesso. Puoi assegnare una singola politica a un gruppo di accesso per concedere a tutti i membri tali autorizzazioni. Se hai più di un utente o ID servizio che ha bisogno dello stesso accesso, crea un gruppo di accesso invece di assegnare lo stesso accesso più volte per ogni singolo utente o ID servizio.

Utilizzando sia gruppi di risorse che gruppi di accesso, puoi ottimizzare la politica di assegnazione dell'accesso assegnando un numero limitato di politiche. Puoi organizzare tutte le risorse a cui uno specifico gruppo di utenti e ID servizio ha bisogno di accedere in un singolo gruppo di risorse, raggruppare tutti gli utenti o gli ID servizio in un gruppo di accesso e assegnare quindi una singola politica concedendo l'accesso a tutte le risorse nel gruppo di risorse.

## Come faccio a garantire che i miei utenti possano creare risorse all'interno di un gruppo di risorse?
{: #resources}

Per creare una risorsa in un gruppo di risorse, l'utente deve disporre di due politiche di accesso: una assegnata al gruppo di risorse stesso e una assegnata alle risorse nel gruppo. L'accesso al gruppo di risorse stesso è semplicemente l'accesso al contenitore che organizza le risorse e questo tipo di politica consente ad un utente di visualizzare, modificare o gestire l'accesso al gruppo ma non le risorse al suo interno. L'accesso ai servizi all'interno del gruppo di risorse consente ad un utente di gestire le istanze di servizio, il che significa che l'utente può creare un'istanza di servizio.

Quindi, come minimo, l'utente deve disporre del seguente accesso:

* Ruolo visualizzatore o superiore sul gruppo di risorse stesso
* Ruolo editor o superiore sul servizio o su tutti i servizi nel gruppo di risorse


## Di quale accesso ho bisogno per fornire l'accesso ad altri utenti?
{: #user-access}

Devi avere il ruolo di amministratore sul servizio o sulla risorsa per cui vuoi assegnare agli utenti l'accesso. Se vuoi assegnare l'accesso a tutti i servizi o a tutte le risorse nell'account, hai bisogno di una politica su tutti i servizi abilitati a identità e accesso con il ruolo di amministratore. 

## Qual è la differenza tra fornire l'accesso per gestire un gruppo di risorse rispetto all'accesso alle risorse all'interno di un gruppo di risorse?
{: #providing-access}

Quando disponi dell'accesso per gestire un gruppo di risorse, puoi visualizzare, modificare il nome e gestire l'accesso per il gruppo di risorse stesso a seconda del ruolo assegnato. L'accesso a un gruppo di risorse stesso non dà all'utente l'accesso alle risorse all'interno del gruppo.

Quando disponi dell'accesso alle risorse all'interno di un gruppo di risorse, puoi modificare, eliminare e creare istanze oppure disporre di tutte le azioni di gestione per i servizi specificati all'interno del gruppo di risorse a seconda del ruolo assegnato. 

Un esempio sono i ruoli e le azioni di gestione della piattaforma per i servizi di gestione dell'account; vedi [Tabella ruoli della piattaforma](/docs/iam/users_roles.html#platformrolestable2).

## Chi può rimuovere gli utenti?
{: #remove-users}

Il proprietario dell'account può sempre aggiungere e rimuovere gli utenti. Inoltre, tutti gli utenti con i seguenti due tipi di politica possono rimuovere gli utenti:

* Editor o Amministratore su tutti i servizi di gestione dell'account
* Editor o Amministratore sul servizio di gestione dell'account di gestione dell'utente

## Come attivo l'autenticazione multifattore?
{: #multi-factor}

Vai a **Gestisci** &gt; **Accesso (IAM)** e scegli **Impostazioni**. 
Scegli **Autenticazione multifattore (MFA)** e fai quindi clic su **Applica le modifiche**. Per ulteriori informazioni, vedi [Abilitazione dell'autenticazione multifattore](/docs/iam/mfa.html#enablemfa).

## Qual è la differenza tra i ruoli del servizio e della piattaforma? 
{: #service-platform-roles}

I ruoli del servizio e della piattaforma sono due tipi diversi di ruoli: 

* I ruoli della piattaforma sono il modo in cui lavori con un servizio all'interno di un account, ad esempio la creazione di istanze, l'esecuzione del bind di istanze e la gestione dell'accesso dell'utente al servizio. Per i servizi della piattaforma, questi ruoli abilitano gli utenti a creare gruppi di risorse e gestire ID servizio, ad esempio. I ruoli della piattaforma sono: amministratore, editor, operatore e visualizzatore. 

* I ruoli del servizio definiscono la capacità di eseguire azioni su un servizio e sono specifici per ogni servizio come l'esecuzione di chiamate API o l'accesso all'interfaccia utente. I ruoli del servizio sono: gestore, scrittore e lettore. Per ulteriori informazioni su come si applicano questi ruoli, fai riferimento alla documentazione del servizio specifico.

## Qual è la differenza tra un gruppo di risorse e le organizzazioni e gli spazi Cloud Foundry?
{: #groups-organizations}

Con l'inizio di {{site.data.keyword.Bluemix_notm}}, un servizio di piattaforma open source per il controllo dell'accesso e l'organizzazione di risorse denominato Cloud Foundry era il singolo metodo per organizzare e controllare l'accesso alle risorse. Man mano che {{site.data.keyword.Bluemix_notm}} si è espanso, era necessario un nuovo metodo che potesse essere utilizzato da tutti i tipi di servizi e risorse. I gruppi di risorse sono ora utilizzati per raggruppare e organizzare molti tipi di risorse, e IAM viene utilizzato per controllare in modo uniforme l'accesso ai servizi e alle risorse. Diversi servizi hanno già adottato l'utilizzo di gruppi di risorse e IAM e ulteriori servizi passeranno progressivamente al nuovo metodo per organizzare le risorse e gestire l'accesso.

Il controllo dell'accesso e l'organizzazione delle risorse dell'account sono le principali differenze tra i gruppi di risorse le organizzazioni e gli spazi Cloud Foundry. I gruppi di risorse organizzano i servizi abilitati a IBM in un account di cui viene controllato l'accesso utilizzando le politiche IAM. Le organizzazioni e gli spazi sono gestiti utilizzando i ruoli Cloud Foundry per il controllo dell'accesso e le risorse Cloud Foundry sono assegnate agli spazi. Le organizzazioni e gli spazi possono essere utilizzati per organizzare e controllare l'accesso alle risorse solo all'interno dell'ambito Cloud Foundry mentre i gruppi di risorse e IAM possono essere utilizzati per più tipi di risorse in tutto {{site.data.keyword.Bluemix_notm}}.

## Come posso assegnare un utente come amministratore dell'account? 
{: #account-administrator}

Per delegare il ruolo di amministratore dell'account utilizzando le politiche IAM, devi creare due politiche:

* Amministratore su tutti i servizi di identità e accesso abilitati, che consente ad un utente di creare le istanze del servizio e di assegnare l'accesso utente a tutte le risorse nell'account
* Amministratore su tutti i servizi di gestione dell'account, che consente ad un utente di completare attività come l'invito e la rimozione di utenti, la gestione dei gruppi di accesso, la gestione degli ID servizio, la gestione delle offerte del catalogo private e la traccia della fatturazione e dell'utilizzo.
