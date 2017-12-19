---

copyright:

  years: 2017

lastupdated: "2017-11-16"

---

{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:screen: .screen}
{:new_window: target="_blank"}

# Modelli di accesso IAM e Cloud Foundry
{: #accessmodels}

Attualmente, non tutti i servizi {{site.data.keyword.Bluemix_notm}} supportano l'utilizzo della gestione dell'accesso di Cloud IAM. I servizi che non hanno abilitato l'utilizzo di Cloud IAM continuano a fare affidamento sul ruolo di un utente in un'organizzazione e spazio Cloud Foundry per determinare se un utente ha l'autorizzazione per accedere alle risorse. Puoi utilizzare l'interfaccia utente {{site.data.keyword.Bluemix_notm}} Identity and Access per gestire l'accesso per i servizi che utilizzano i sistemi di gestione dell'accesso Cloud IAM o Cloud Foundry.


## Passaggio dei servizi Cloud Foundry a Cloud IAM
{: #cftoiam}

Se attualmente stai utilizzando un servizio Cloud Foundry che inizia a supportare l'utilizzo della gestione dell'accesso Cloud IAM, riceverai una notifica che ti indica che puoi ora usufruire del controllo dell'accesso con IAM per le nuove istanze del servizio che crei.

Quando i servizi iniziano ad abilitare l'utilizzo di Cloud IAM, puoi aspettarti quanto segue:

* Per le istanze esistenti nel tuo account che già utilizzano la gestione dell'accesso di Cloud Foundry assegnando gli utenti a un'organizzazione e uno spazio con un ruolo di Cloud Foundry, puoi continuare a utilizzare tali istanze senza alcuna modifica.
* Per creare nuove istanze, assegna ciascuna di esse a un gruppo di risorse nel tuo account e quindi utilizza Cloud IAM per gestire l'accesso a tale istanza e al gruppo di risorse a cui appartiene, se sei l'amministratore nel gruppo di risorse. 

I servizi che supportano l'utilizzo di Cloud IAM dispongono di numerosi vantaggi, tra cui la possibilità di connettersi ad applicazioni e servizi in qualsiasi spazio Cloud Foundry, che ti consente di connettere applicazioni e servizi da regioni diverse. Inoltre, ogni istanza gestita da Cloud IAM appartiene a un gruppo di risorse e i gruppi di risorse non sono definiti dalla regione, pertanto puoi eseguire il provisioning di applicazioni e servizi da diverse regioni nello stesso gruppo di risorse. Hai anche la possibilità di utilizzare il controllo dell'accesso specifico su una singola istanza. 

