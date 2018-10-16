---

copyright:

  years: 2018
lastupdated: "2018-10-10"

---

{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:screen: .screen}
{:new_window: target="_blank"}
{:tip: .tip}


# Configurazione dei gruppi di accesso
{: #groups}

Un gruppo di accesso può essere creato per organizzare un insieme di utenti e ID del servizio in una sola entità che ti rende più facile assegnare le autorizzazioni. Puoi assegnare una sola politica al gruppo invece di assegnare lo stesso accesso più volte per ogni utente o ID del servizio individuale.

Per gestire o creare nuovi gruppi di accesso, devi essere il proprietario, l'amministratore o l'editor dell'account su tutti i servizi abilitati per l'identità e l'accesso (IAM) nell'account o l'amministratore o l'editor assegnati al servizio dei gruppi di accesso IAM. Per ulteriori informazioni sulle politiche di accesso e sui ruoli, vedi [Accesso IAM](/docs/iam/users_roles.html#userroles).

Inoltre, è possibile assegnare un amministratore o un editor a un solo gruppo creando una politica di accesso in cui la risorsa è l'ID del gruppo di accesso. Un amministratore o un editor del gruppo può aggiornare ed eliminare il gruppo, così come creare, aggiornare ed eliminare i membri o le politiche di accesso del gruppo. Un utente con assegnato il ruolo di visualizzatore può solo richiamare ed elencare i gruppi, i membri e l'accesso assegnato.

Per rendere l'assegnazione e la gestione dell'accesso ancora più semplice, puoi configurare i gruppi di accesso per organizzare una serie di risorse a cui vuoi che un gruppo di utenti abbia accesso. Quando il tuo gruppo di risorse è configurato, puoi assegnare una politica che fornisce l'accesso a tutte le risorse in tale gruppo invece di creare le politiche di accesso per istanze del servizio individuali nel tuo account. 
{: tip}

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

Per creare un gruppo di accesso utilizzando la CLI, puoi utilizzare il comando [ibmcloud iam access-group-create](/docs/cli/reference/ibmcloud/cli_api_policy.html#ibmcloud_iam_access_group_create).
```
ibmcloud iam access-group-create NOME_GRUPPO [-d, --description DESCRIZIONE]
```
{: codeblock}


## Assegnazione dell'accesso a un gruppo

Dopo aver configurato il tuo gruppo con gli utenti e gli ID del servizio, puoi assegnare una politica di accesso comune al gruppo. Ricorda, qualsiasi politica configuri per il gruppo si applica a tutte le entità all'interno del gruppo.

1. Dalla barra dei menu, fai clic su **Gestisci** &gt; **Sicurezza** &gt; **Identità e accesso** e seleziona **Gruppi di accesso**.
2. Seleziona il nome del gruppo a cui vuoi assegnare l'accesso. 
3. Fai clic sulla scheda **Politiche di accesso**.
4. Fai clic su **Assegna accesso**. 
5. Scegli di assegnare l'accesso alle risorse all'interno di un gruppo di risorse o alle risorse individuali disponibili nell'account.

Per creare una politica del gruppo di accesso utilizzando la CLI, puoi utilizzare il comando [ibmcloud iam access-group-policy-create](/docs/cli/reference/ibmcloud/cli_api_policy.html#ibmcloud_iam_access_group_policy_create).
```
ibmcloud iam access-group-policy-create NOME_GRUPPO {-f, --file @FILE_JSON | --roles NOME_RUOLO1,NOME_RUOLO2... [--service-name NOME_SERVIZIO] [--service-instance ISTANZA_SERVIZIO] [--region REGIONE] [--resource-type TIPO_RISORSA] [--resource RISORSA] [--resource-group-name NOME_GRUPPO_RISORSE] [--resource-group-id ID_GRUPPO_RISORSE]}
```
{: codeblock}
