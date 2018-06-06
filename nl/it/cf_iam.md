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

# Migrazione di istanze del servizio Cloud Foundry a un gruppo di risorse
{: #accessmodels}

Quando i servizi vengono spostati dall'utilizzo di organizzazioni, spazi e ruoli Cloud Foundry all'utilizzo di Cloud IAM (Identity and Access Management) e dei gruppi di risorse, ricevi una notifica nel tuo dashboard. Quando un servizio esegue il passaggio da Cloud Foundry, ti viene chiesto di migrare le tue istanze del servizio esistenti che appartengono a un'organizzazione o spazio in un [gruppo di risorse](/docs/account/resourcegroups.html#rgs). 

Quando migri le istanze del servizio Cloud Foundry esistenti a un gruppo di risorse, l'assegnazione del gruppo che effettui non può essere modificata dopo il completamento della migrazione. Quindi, devi essere sicuro della tua decisione su come vuoi organizzare le risorse nell'account prima della migrazione. Pertanto, potresti dover creare uno o più gruppi di risorse, se hai un account a pagamento, prima di eseguire la migrazione.
{: tip}

## Perché migrare le istanze del servizio?

I servizi che supportano l'utilizzo di Cloud IAM dispongono di diversi vantaggi. Alcuni di questi vantaggi includono la possibilità di connettersi ad applicazioni e servizi in qualsiasi spazio Cloud Foundry, il che significa che puoi stabilire connessioni per applicazioni e servizi da regioni differenti. Inoltre, ciascuna istanza gestita da Cloud IAM appartiene a un gruppo di risorse. I gruppi di risorse non sono definiti dalla regione e puoi pertanto eseguire il provisioning di applicazioni e servizi da diverse regioni nello stesso gruppo di risorse. Puoi anche utilizzare il controllo dell'accesso dettagliato fino a un livello di singola istanza.
 

## Come funziona la migrazione?

La migrazione a un'istanza del servizio da un'organizzazione o uno spazio Cloud Foundry in un gruppo di risorse crea una nuova istanza del servizio collegata nel gruppo di risorse. L'istanza originale nell'organizzazione o spazio Cloud Foundry diventa un [alias](/docs/cfapps/connecting_apps.html#what_is_alias).

Puoi eseguire la migrazione delle tue istanze del servizio una per volta, quando ricevi la notifica. Ricevi la notifica nel dashboard da un'icona associata all'istanza del servizio Cloud Foundry o da un messaggio nella pagina dei dettagli del servizio che ti può portare direttamente alla procedura guidata che ti guida attraverso il processo. Prima di eseguire la migrazione, decidi come vuoi organizzare le tue risorse. Puoi quindi scegliere un'istanza del servizio idonea utilizzando il menu **Azioni** nel dashboard e selezionando **Migra a un gruppo di risorse**. Seleziona un gruppo di risorse a cui migrare l'istanza durante il processo. Dopo che hai correttamente migrato un'istanza, la visualizzi nella sezione dei servizi del tuo dashboard. L'alias rimane nella sezione Cloud Foundry del dashboard. 


