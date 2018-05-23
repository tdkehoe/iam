---

copyright:

  years: 2018
lastupdated: "2018-03-30"

---

{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:screen: .screen}
{:new_window: target="_blank"}
{:tip: .tip}


# Configurazione dei gruppi di accesso
{: #groups}

Un gruppo di accesso può essere creato per organizzare un insieme di utenti e ID del servizio in una sola entità che ti rende più facile assegnare le autorizzazioni. Puoi assegnare una sola politica al gruppo invece di assegnare lo stesso accesso più volte per ogni utente o ID del servizio individuale.

Per rendere l'assegnazione e la gestione dell'accesso ancora più semplice, puoi configurare i gruppi di accesso per organizzare una serie di risorse a cui vuoi che un gruppo di utenti abbia accesso. Quando il tuo gruppo di risorse è configurato, puoi assegnare una politica che fornisce l'accesso a tutte le risorse in tale gruppo invece di creare le politiche di accesso per istanze del servizio individuali nel tuo account.  

## Creazione di un gruppo di accesso

Per creare un gruppo di accesso, completa la seguente procedura:

1. Dalla barra dei menu, fai clic su **Gestisci** &gt; **Sicurezza** &gt; **Identità e accesso** e seleziona **Gruppi di accesso**.
2. Fai clic su **Crea**.
3. Immetti un nome e una descrizione facoltativi per il gruppo e fai clic su **Crea**.

Successivamente, continua a configurare il tuo gruppo aggiungendo utenti o ID del servizio:

1. Seleziona il nome del gruppo che vuoi aggiungere.
2. Fai clic su **Aggiungi utenti** nella scheda **Utenti**. 
3. Seleziona gli utenti che vuoi aggiungere dall'elenco e fai clic su **Aggiungi al gruppo**.
4. Per aggiungere gli ID del servizio al gruppo, fai clic sulla scheda **ID servizio** e su **Aggiungi ID servizio**.
5. Seleziona gli ID che vuoi aggiungere dall'elenco e fai clic su **Aggiungi al gruppo**.

Puoi eliminare un gruppo selezionando l'opzione **Rimuovi gruppo**. Quando rimuovi un gruppo dall'account, stai rimuovendo tutti gli utenti e gli ID del servizio dal gruppo e tutto l'accesso assegnato al gruppo.
{: tip}


## Assegnazione dell'accesso a un gruppo

Dopo aver configurato il tuo gruppo con gli utenti e gli ID del servizio, puoi assegnare una politica di accesso comune al gruppo. Ricorda, qualsiasi politica configuri per il gruppo si applica a tutte le entità all'interno del gruppo.

1. Dalla barra dei menu, fai clic su **Gestisci** &gt; **Sicurezza** &gt; **Identità e accesso** e seleziona **Gruppi di accesso**.
2. Seleziona il nome del gruppo a cui vuoi assegnare l'accesso. 
3. Fai clic sulla scheda **Politiche di accesso**.
4. Fai clic su **Assegna accesso**. 
5. Scegli di assegnare l'accesso alle risorse all'interno di un gruppo di risorse o alle risorse individuali disponibili nell'account.
