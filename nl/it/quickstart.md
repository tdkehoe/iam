---

copyright:

  years: 2017

lastupdated: "2017-11-16"

---

{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:screen: .screen}
{:new_window: target="_blank"}

# Esercitazione introduttiva
{: #getstarted}

Questa esercitazione ha lo scopo di aiutarti a iniziare rapidamente a lavorare con IBM Cloud Identity and Access Management (IAM) invitando gli utenti al tuo account e assegnando loro l'accesso a Cloud IAM. 

Questa esercitazione riguarda solo le risorse gestite da IAM. Per i servizi che non supportano la creazione di politiche Cloud IAM per la gestione dell'accesso, puoi utilizzare [Accesso Cloud Foundry](/docs/iam/cfaccess.html#cfaccess). 


## Passo 1: invita gli utenti e assegna l'accesso iniziale

Puoi invitare uno o più utenti e impostare una politica di accesso iniziale per gli utenti al momento dell'invito. Se inviti più utenti in un unico invito, lo stesso accesso viene assegnato a ciascuno degli utenti. Nella sezione Accesso della pagina Invita utenti, sono visualizzate solo le sezioni che sei autorizzato ad assegnare.

In qualità di proprietario dell'account, puoi assegnare i ruoli di Cloud IAM per gli utenti che inviti nella sezione Servizi. Puoi fornire l'accesso a tutte le risorse in un gruppo di risorse, a tutte le risorse per un servizio specifico in un gruppo di risorse, a tutti i servizi abilitati per l'accesso e l'identità nell'account o a una singola risorsa nella politica iniziale assegnata nell'invito:

1. Vai a **Gestisci** &gt; **Sicurezza** &gt; **Identità e accesso** e seleziona **Utenti**.
2. Fai clic su **Invita utenti**.
3. Specifica l'indirizzo e-mail degli utenti che vuoi invitare.
4. Nella sezione **Accesso**, espandi l'opzione **Servizi**.
5. Scegli di assegnare l'accesso a una **Risorsa** o alle risorse all'interno di un **Gruppo di risorse**.
6. A seconda della tua selezione, segui i prompt per specificare l'accesso a una singola istanza del servizio, a tutti i servizi abilitati per l'accesso e l'identità, a tutte le risorse in un gruppo di risorse o a uno specifico servizio all'interno del gruppo di risorse selezionato. Se hai selezionato l'opzione del gruppo di risorse, puoi anche fornire all'utente l'accesso per visualizzare, modificare o gestire l'accesso al gruppo risorse selezionando un ruolo per l'accesso al gruppo di risorse.
7. Se disponi dell'autorizzazione, puoi anche assegnare l'accesso a Cloud Foundry o all'infrastruttura al momento dell'invito.
8. Fai clic su **Invita utenti**.

Per ulteriori informazioni, vedi [Invito di utenti e assegnazione dell'accesso](/docs/iam/iamuserinv.html#iamuserinv).

## Passo 2: gestisci l'accesso per gli utenti esistenti

Dopo aver invitato gli utenti e assegnato l'accesso iniziale, potresti voler assegnare un accesso aggiuntivo o modificare l'accesso iniziale che hai assegnato per garantire che tutti gli utenti nel tuo account abbiano il livello di accesso desiderato.

### Assegnazione del nuovo accesso

Puoi assegnare a un utente l'accesso per un gruppo di risorse o una singola risorsa.

1. Dalla barra dei menu, fai clic su **Gestisci** &gt; **Sicurezza** &gt; **Identità e accesso** e seleziona **Utenti**.
2. Fai clic sul nome dell'utente a cui vuoi assegnare l'accesso.
3. Fai clic su **Assegna accesso**.
4. Scegli in che modo assegnare l'accesso: 
    * Seleziona **Assegna l'accesso in un gruppo di risorse** per assegnare l'accesso a tutte le risorse in un gruppo o solo alle risorse per un servizio specifico all'interno di un gruppo. Puoi anche fornire all'utente l'accesso per visualizzare, modificare o gestire l'accesso al gruppo risorse selezionando un ruolo per l'accesso al gruppo di risorse. Seleziona **Nessun accesso** se vuoi che l'utente abbia accesso solo alla risorsa specificata e non al gruppo in cui è organizzata.
    * Seleziona **Assegna l'accesso alle risorse** per assegnare l'accesso a tutte le risorse abilitate all'accesso e l'identità nell'account, a tutte le risorse di uno specifico servizio nell'account, a una singola istanza o a una singola risorsa all'interno di una specifica istanza del servizio. 
5. Seleziona qualsiasi combinazione di ruoli per definire l'ambito di accesso. Per ulteriori informazioni, vedi [Ruoli Cloud IAM](/docs/iam/users_roles.html#iamusermanrol).
6. Fai clic su **Assegna**.


### Modifica dell'accesso esistente

Puoi aggiornare l'accesso esistente modificando i ruoli assegnati per un utente.

1. Dalla barra dei menu, fai clic su **Gestisci** &gt; **Sicurezza** &gt; **Identità e accesso** e seleziona **Utenti**.
2. Seleziona il nome dell'utente per il quale vuoi modificare l'accesso.
3. Dalla riga per la politica che vuoi modificare, fai clic su **Modifica politica** dal menu **Azioni**.
4. Modifica la politica aggiornando i ruoli assegnati.
5. Fai clic su **Salva**. 

Puoi rimuovere l'accesso da un utente facendo clic sull'opzione **Rimuovi** dal menu **Azioni** per la politica che vuoi rimuovere.

## Passi successivi

Scopri cos'altro puoi fare con Cloud IAM controllando l'elenco delle [Funzioni di Cloud IAM](/docs/iam/index.html#features).
