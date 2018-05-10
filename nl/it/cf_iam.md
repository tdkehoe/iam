---

copyright:

  years: 2017, 2018

lastupdated: "2018-04-17"

---

{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:screen: .screen}
{:new_window: target="_blank"}
{:tip: .tip}

# Migrazione di istanze del servizio Cloud Foundry a un gruppo di risorse 
{: #accessmodels}

Quando i servizi vengono spostati dall'utilizzo di organizzazioni, spazi e ruoli Cloud Foundry all'utilizzo di IAM (Identity and Access Management) cloud e dei gruppi di risorse, riceverai una notifica nel tuo dashboard. Quando un servizio viene tolto da Cloud Foundry, ti viene chiesto di migrare le tue istanze del servizio esistenti che appartengono a un'organizzazione o spazio in un [gruppo di risorse](/docs/account/resourcegroups.html#rgs). 

Quando migri le istanze del servizio Cloud Foundry esistenti a un gruppo di risorse, l'assegnazione del gruppo che effettui non può essere modificata dopo il completamento della migrazione. Quindi, devi essere sicuro della tua decisione su come vuoi organizzare le risorse nell'account prima della migrazione. Questo potrebbe voler dire che devi creare uno o più gruppi di risorse, se hai un account a pagamento, prima della migrazione.
{: tip}

## Perché migrare le mie istanze del servizio? 

I servizi che supportano l'utilizzo di Cloud IAM dispongono di numerosi vantaggi, tra cui la possibilità di connettersi ad applicazioni e servizi in qualsiasi spazio Cloud Foundry, che ti consente di connettere applicazioni e servizi da regioni diverse. Inoltre, ogni istanza gestita da Cloud IAM appartiene a un gruppo di risorse e i gruppi di risorse non sono definiti dalla regione, pertanto puoi eseguire il provisioning di applicazioni e servizi da diverse regioni nello stesso gruppo di risorse. Hai anche la possibilità di utilizzare il controllo dell'accesso specifico su una singola istanza.
 

## Come funziona la migrazione? 

La migrazione a un'istanza del servizio da un'organizzazione o uno spazio Cloud Foundry in un gruppo di risorse crea una nuova istanza del servizio collegata nel gruppo di risorse. L'istanza originale nell'organizzazione o spazio Cloud Foundry diventa un [alias](/docs/cfapps/connecting_apps.html#what_is_alias).

Puoi migrare le tue istanze del servizio una alla volta quando ti viene notificato nel dashboard da un'icona associata all'istanza del servizio Cloud Foundry o da un messaggio nella pagina dei dettagli del servizio che ti può portare direttamente alla procedura guidata che ti guida attraverso il processo. Prima di migrare, prendi una decisione su come vuoi organizzare le tue risorse, quindi scegli un'istanza del servizio eleggibile utilizzando il menu **Azioni** nel dashboard e selezionando **Migra a un gruppo di risorse**. Seleziona un gruppo di risorse a cui migrare l'istanza durante il processo. Dopo aver correttamente migrato un'istanza, la visualizzerai nella sezione dei servizi del tuo dashboard. L'alias rimane nella sezione Cloud Foundry del dashboard. 


