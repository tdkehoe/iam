---

copyright:

  years: 2015, 2018
lastupdated: "2018-04-16"

---

{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:screen: .screen}
{:new_window: target="_blank"}

# Gestione delle chiavi API utente
{: #userapikey}

Un utente federato o non federato può creare una chiave API da utilizzare nella CLI o come parte dell'automazione per eseguire l'accesso come tua identità utente. Puoi utilizzare l'IU o la CLI per gestire le tue chiavi API attraverso l'elenco, la creazione, l'aggiornamento o l'eliminazione delle chiavi. Per gestire le chiavi API {{site.data.keyword.Bluemix_notm}} associate alla tua identità utente, vai a **Gestisci** &gt; **Sicurezza** &gt; **Chiavi API della piattaforma** per visualizzare un elenco delle tue chiavi API con descrizioni e date. Quindi, da questa pagina puoi creare, modificare o eliminare le chiavi API. E per un elenco completo dei comandi CLI disponibili, consulta [`bluemix iam api-keys`](/docs/cli/reference/bluemix_cli/bx_cli.html#bluemix_iam).

Come [utente federato](/docs/account/adminpublic.html#federatedid), puoi usare una chiave API per eseguire l'accesso utilizzando la variabile di ambiente `BLUEMIX_API_KEY`. Per ulteriori informazioni sull'utilizzo di una chiave API per l'accesso, vedi [Accesso con un ID federato](/docs/cli/login_federated_id.html#federated_id).

## Creazione di una chiave API

In qualità di utente {{site.data.keyword.Bluemix_notm}}, potresti voler utilizzare una chiave API quando abiliti un programma o uno script senza distribuire la tua password allo script. Un vantaggio di utilizzare una chiave API può essere che un utente o un'organizzazione può creare più chiavi API per programmi diversi e le chiavi API possono essere eliminate in modo indipendente se compromesse senza interferire con altre chiavi API o con l'utente. Puoi creare fino a 20 chiavi API. 

Per creare una chiave API per la tua identità utente nell'IU:

1. Vai a **Gestisci** &gt; **Sicurezza** &gt; **Chiavi API della piattaforma**.
2. Fai clic su **Crea chiave API**.
3. Immetti un nome e una descrizione per la tua chiave API.
4. Fai clic su **Crea chiave API**.
5. Infine, fai clic su **Mostra** per visualizzare la chiave API e per copiarla e salvarla per un uso successivo oppure fai clic su **Scarica chiave API**.

**Nota**: per motivi di sicurezza, la chiave API è disponibile per essere copiata o scaricata solo durante la fase di creazione. Se la chiave API viene persa, dovrai crearne una nuova.

Per creare una chiave API utilizzando la CLI:

1. Immetti `bluemix iam api-key-create NAME [-d DESCRIPTION] [-f, --file FILE]` nel prompt dei comandi, e specificare un nome, una descrizione, e file per salvare la tua chiave. Ad
esempio:

```
bluemix iam api-key-create MyKey -d "questa è la mia chiave API" -f file_chiave
``` 


## Aggiornamento di una chiave API

Se desideri modificare il nome o la descrizione di una chiave API, completa le seguenti istruzioni nella IU o nella CLI.

Per modificare una chiave API:

1. Vai a **Gestisci** &gt; **Sicurezza** &gt; **Chiavi API della piattaforma**.
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

1. Vai a **Gestisci** &gt; **Sicurezza** &gt; **Chiavi API della piattaforma**.
2. Dal menu **Azioni** di una chiave API elencata nella tabella, fai clic su **Elimina**.
3. Conferma infine l'eliminazione facendo clic su **Elimina chiave**.

Per eliminare una chiave API utilizzando la CLI:
1. Immetti `bluemix iam api-key-delete NAME` nel tuo prompt dei comandi, specificano il nome della tua chiave che deve essere eliminata.
