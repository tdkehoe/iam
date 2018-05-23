---

copyright:

  years: 2015, 2018
lastupdated: "2018-01-26"

---

{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:screen: .screen}
{:new_window: target="_blank"}

# Gestione delle chiavi API
{: #manapikey}

Una chiave API (application programming interface) è un codice univoco passato a una API (application programming interface) per identificare l'applicazione o l'utente chiamante.  Le chiavi API vengono utilizzate per tracciare e controllare la modalità di utilizzo della API, ad esempio per prevenire l'uso dannoso o l'abuso della API. La chiave API spesso funge sia da identificativo univoco che da token segreto per l'autenticazione e generalmente dispone di una serie di diritti di accesso specifici per l'identità ad essa associata.

## Chiavi API della piattaforma

Le chiavi API della piattaforma vengono create nell'interfaccia utente di Identity and Access Management e possono essere associate a:

* Utenti di un account
* ID servizio creati in un account

Puoi creare e utilizzare chiavi API collegate al tuo account. Un utente federato o non federato può creare una chiave API da utilizzare nella CLI o come parte dell'automazione per eseguire l'accesso come tua identità utente. Per ulteriori informazioni sull'utilizzo di una chiave API associata alla tua identità utente, consulta [Gestione delle chiavi API utente](userid_keys.html).

Puoi anche utilizzare le chiavi API associate agli ID servizio che crei. Gli ID servizio sono utilizzati per connettere un'applicazione all'interno o all'esterno di {{site.data.keyword.Bluemix_notm}} a un servizio {{site.data.keyword.Bluemix_notm}}. Per ulteriori informazioni sulla creazione di chiavi API associate a un ID servizio, consulta [Gestione delle chiavi API di un ID servizio](serviceid_keys.html).

## Altre chiavi API {{site.data.keyword.Bluemix_notm}}

Oltre alle chiavi API della tua piattaforma, ci sono un paio di altri tipi di chiavi API che potresti utilizzare in {{site.data.keyword.Bluemix_notm}}:

* Chiavi API dell'infrastruttura
* Chiavi API specifiche del servizio

Le chiavi API dell'infrastruttura vengono create nel portale clienti, sono associate al tuo ID utente dell'account SoftLayer e vengono utilizzate quando accedi alle API per i servizi di infrastruttura.

Alcuni servizi in {{site.data.keyword.Bluemix_notm}} potrebbero anche fornire una chiave API da utilizzare durante l'interazione con il servizio. Ad esempio, se stai visualizzando i dettagli di un servizio Watson dal tuo dashboard, puoi creare una credenziale, che include una chiave e un segreto API, specifica solo per tale servizio nella scheda Credenziali del servizio.

