---

copyright:

  years: 2015, 2018

lastupdated: "2018-04-04"

---

{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:screen: .screen}
{:tip: .tip}
{:new_window: target="_blank"}

# Accesso IAM
{: #userroles}

Tutti i servizi che sono organizzati in un gruppo di risorse nel tuo account vengono gestiti utilizzando {{site.data.keyword.Bluemix_notm}} Identity and Access Management (IAM). Ai proprietari dell'account viene assegnato automaticamente il ruolo di amministratore di account per Cloud IAM. Come amministratore dell'account, puoi assegnare e gestire l'accesso per gli utenti, creare gruppi di risorse, eseguire il provisioning delle istanze del servizio e tutte le altre attività che possono essere delegate assegnando i ruoli di Cloud IAM. Fornisci l'accesso per gli utenti e gli ID servizio creando delle politiche che impostano una destinazione per l'accesso dell'utente o dell'ID servizio e un ruolo che definisce quale tipo di accesso è consentito.


## Cosa sono le politiche Cloud IAM e chi può assegnarle?
{: #iamusermanpol}

Una politica concede a un utente o ID servizio uno o più ruoli per un insieme di risorse per abilitare l'utilizzo di azioni specifiche all'interno del contesto delle risorse di destinazione specificate. Quando assegni una politica, per prima cosa devi scegliere se impostare la politica per un gruppo di risorse o per una singola risorsa. Quindi, a seconda della tua selezione iniziale, puoi selezionare un servizio all'interno di un gruppo di risorse o una singola istanza per la risorsa selezionata. Potrebbero essere disponibili altre opzioni di configurazione, a seconda del servizio che selezioni. Infine, puoi selezionare uno o più ruoli da assegnare. 

Puoi assegnare e gestire le politiche se hai il ruolo appropriato. La seguente tabella mostra le attività di gestione delle politiche e il ruolo richiesto per ciascuna.

| Azione | Ruolo richiesto |
|----------|---------|
| Creare una politica in un account per tutti i servizi e le istanze | Proprietario dell'account o amministratore su tutti i servizi nell'account | 
| Creare una politica su un servizio in un account | Proprietario dell'account o amministratore sul servizio nell'account |
| Creare una politica su un'istanza del servizio | Proprietario dell'account, amministratore sul servizio nell'account, amministratore su tutti i servizi nel gruppo di risorse relativo o amministratore sull'istanza del servizio |
| Creare una politica per gestire un gruppo di risorse | Proprietario dell'account o amministratore su un gruppo di risorse |
{: caption="Tabella 1. Utenti autorizzati a creare politiche di accesso" caption-side="top"} 


## Ruoli Cloud IAM
{: #iamusermanrol}

Con Cloud IAM, puoi gestire e definire l'accesso per gli utenti e le risorse nel tuo account. Esistono due tipi di ruoli: i ruoli di gestione della piattaforma e i ruoli di accesso al servizio.

<dl>
<dt>Ruoli di gestione della piattaforma</dt> 
<dd>I ruoli di gestione della piattaforma comprendono una serie di azioni, tra cui la possibilità di creare istanze, gestire gli ID servizio, gestire utenti e autorizzazioni e creare gruppi di risorse. I ruoli della piattaforma più comuni sono amministratore, editor, operatore, visualizzatore. </dd>
<dt>Ruoli di accesso al servizio</dt>
<dd>I ruoli di accesso al servizio definiscono la capacità di un utente o un servizio di eseguire azioni su un'istanza del servizio, come l'accesso all'interfaccia utente o l'esecuzione di chiamate API. Ci sono tre possibili ruoli: gestore, scrittore e lettore. </dd>
</dl> 

Potresti non vedere tutti i ruoli elencati come opzioni quando assegni le politiche nell'interfaccia utente perché vengono visualizzati solo i ruoli disponibili per il servizio che hai selezionato. Per informazioni specifiche su quali ruoli sono abilitati e quali azioni sono consentite da ciascun ruolo di accesso per ogni servizio, fai riferimento alla documentazione di quel servizio.
{: tip}

Utilizzando una combinazione di questi ruoli in una singola politica di accesso, puoi fornire l'accesso specifico per utenti e ID servizio assegnando l'accesso con una delle seguenti opzioni:

* Tutte le risorse nell'account
* Tutte le risorse all'interno di tutti i servizi che appartengono a un singolo gruppo di risorse nonché la possibilità di gestire il gruppo di risorse
* Tutte le risorse all'interno di un singolo servizio in un gruppo di risorse nonché la possibilità di gestire il gruppo di risorse
* Tutte le risorse all'interno di un singolo servizio nell'account, indipendentemente dal gruppo di risorse a cui sono assegnate
* Le risorse in una singola istanza
* Un singolo tipo di risorsa all'interno di un'istanza, ad esempio un bucket in un'istanza {{site.data.keyword.objectstorageshort}}

Per consentire a un altro utente l'accesso completo all'account ai fini della gestione dell'accesso degli utenti e della gestione di tutte le risorse dell'account, inclusa la possibilità di creare gruppi di risorse, imposta una politica che consenta all'utente di accedere a tutte le risorse dell'account selezionando **Tutti i sevizi abilitati per l'accesso e l'identità** con il ruolo **Amministratore** assegnato. 
{: tip}

### Ruoli di gestione della piattaforma

I ruoli di gestione della piattaforma consentono di assegnare agli utenti diversi livelli di autorizzazione per l'esecuzione di azioni della piattaforma all'interno dell'account. Le seguenti tabelle forniscono esempi di alcune azioni di gestione della piattaforma che gli utenti assegnati a ciascun ruolo possono eseguire. Puoi fare riferimento alla documentazione di ciascun servizio per comprendere in che modo i ruoli vengano applicati agli utenti nel contesto del servizio utilizzato.

| Dettagli della politica di accesso  | Azioni che un utente può eseguire sui servizi dell'account | Azioni per gli ID di servizio | Azioni per l'accesso ai gruppi di risorse | Azione sulle risorse nei gruppi di risorse | Azioni per la gestione dei gruppi di accesso |
|:-----------------|:--------------|:---------------|:----------------|:-----------------|:--------------|
| Assegna accesso a | Uno o tutti i servizi abilitati a IAM | Servizio di identità IAM | Gruppo di risorse selezionato | Servizio selezionato in un gruppo di risorse | Gruppi di accesso IAM |
| Ruolo visualizzatore | Visualizzare istanze, alias, bind e credenziali | Visualizzare ID e chiavi API | Visualizzare il gruppo di risorse | Visualizzare solo le istanze specificate nel gruppo di risorse | Visualizza i gruppi di accesso e i membri |
| Ruolo operatore |  Visualizzare istanze e gestire alias, bind e credenziali | Non applicabile | Non applicabile | Non applicabile | Non applicabile |
| Ruolo editor |  Creare, eliminare, modificare e visualizzare istanze. Gestire alias, bind e credenziali | Creare ed eliminare ID e chiavi API | Visualizzare e modificare il nome del gruppo di risorse | Creare, eliminare, modificare, sospendere, riprendere, visualizzare e associare solo le istanze specificate nel gruppo di risorse | Visualizzare, creare, eliminare e modificare i gruppi di accesso nell'account. |
| Ruolo amministratore |  Tutte le azioni di gestione per i servizi | Creare ed eliminare ID e chiavi API, assegnare politiche agli ID | Visualizzare, modificare e gestire l'accesso per il gruppo di risorse | Tutte le azioni di gestione per le istanze specificate nel gruppo di risorse | Visualizzare, creare, eliminare, modificare e gestire l'accesso per utilizzare i gruppi di accesso |
{: caption="Tabella 2. Ruoli e azioni di esempio per la gestione della piattaforma" caption-side="top"}
{: #platformrolestable}

Alcuni servizi potrebbero associare specifiche azioni ai ruoli di gestione della piattaforma correlati alla gestione del servizio piuttosto che all'accesso del servizio. Come esempio, consulta la seguente tabella che descrive le azioni del servizio {{site.data.keyword.containershort_notm}} associate a questi ruoli.


| Ruolo di gestione della piattaforma | Descrizione delle azioni | Azioni di esempio per {{site.data.keyword.containershort_notm}} |
|:-----------------|:-----------------|:-----------------|
| Visualizzatore | Può visualizzare le istanze del servizio ma non può modificarle  | <ul><li>Elencare i cluster</li><li>Visualizzare i dettagli per un cluster</li></ul>|
| Editor | Eseguire tutte le azioni di piattaforma eccetto la gestione dell'account e l'assegnazione delle politiche di accesso |<ul><li>Eseguire il bind di un servizio a un cluster</li><li>Crea un webhook</li></ul> |
| Operatore | Eseguire le azioni di piattaforma necessarie per configurare e gestire le istanze del servizio, come ad esempio visualizzare il dashboard di un servizio. | <ul><li>Aggiungere o rimuovere i nodi di lavoro</li><li>Riavviare o ricaricare i nodi di lavoro</li><li>Eseguire il bind di un servizio a un cluster</li></ul> |
| Amministratore | Esegue tutte le azioni di piattaforma in base alla risorsa assegnata a questo ruolo, inclusa l'assegnazione di politiche di accesso ad altri utenti. |<ul><li>Rimuovere un cluster</li><li>Creare un cluster</li><li>Aggiorna le politiche di accesso utente</li><li>Tutte le azioni che possono essere eseguite da un visualizzatore, un operatore e un editor</li></ul>|
{: caption="Tabella 3. Ruoli e azioni di esempio per la gestione della piattaforma per il servizio {{site.data.keyword.containershort_notm}}" caption-side="top"}


### Ruoli di accesso al servizio

I ruoli di accesso al servizio consentono di assegnare agli utenti diversi livelli di autorizzazione per richiamare l'API del servizio e accedere all'interfaccia utente del servizio. La seguente tabella fornisce le azioni di esempio che è possibile eseguire a seconda dei ruoli assegnati in base all'utilizzo del servizio {{site.data.keyword.objectstorageshort}}.

**Nota**: le azioni che possono essere eseguite per ogni ruolo assegnato variano in base al servizio selezionato per la politica.

| Ruolo di accesso al servizio | Descrizione delle azioni | Azioni di esempio per il servizio {{site.data.keyword.objectstorageshort}} |
|:-----------------|:-----------------|:-----------------|
|  Lettore | Eseguire azioni di sola lettura all'interno di un servizio, ad esempio visualizzare le risorse specifiche del servizio | Elencare e scaricare oggetti |
| Scrittore | Gli scrittori dispongono di autorizzazioni al di sopra del ruolo di lettore, incluse la creazione e la modifica di risorse specifiche del servizio. | Creare ed eliminare bucket e oggetti |
| Gestore | I gestori dispongono di autorizzazioni al di sopra del ruolo di scrittore per completare le azioni privilegiate definite dal servizio. Inoltre, puoi creare e modificare le risorse specifiche del servizio. | Gestire tutti gli aspetti dell'archiviazione dati, creare ed eliminare bucket e oggetti |
{: caption="Tabella 4. Ruoli utente e azioni di esempio per l'accesso al servizio" caption-side="top"}

