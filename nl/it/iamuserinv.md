---

copyright:

  years: 2015, 2018
lastupdated: "2018-11-30"

---

{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:screen: .screen}
{:new_window: target="_blank"}
{:tip: .tip}
{:note: .note}

# Invito di utenti
{: #iamuserinv}

Puoi invitare gli utenti, annullare gli inviti e reinviare un invito in sospeso a un utente invitato. Inoltre, puoi invitare un singolo utente o più utenti contemporaneamente.    
{:shortdesc}

Per invitare gli utenti e gestire gli inviti in sospeso, devi essere un proprietario dell'account, un gestore dell'organizzazione, un utente con una politica di accesso IAM con il ruolo Editor o superiore nel servizio di gestione utenti o devi avere la autorizzazioni dell'infrastruttura classica per aggiungere gli utenti.

## Configurazione di un invito
{: #invitations}

Per invitare gli utenti o per gestire gli inviti utente nel tuo account, completa la seguente procedura:

1. Dalla barra dei menu, fai clic su **Gestisci** &gt; **Accesso (IAM)** e seleziona **Utenti**.
2. Fai clic su **Invita utenti**.
3. Specifica l'indirizzo e-mail dell'utente. Se inviti più di un utente con un singolo invito, a tutti viene assegnato lo stesso accesso.
4. Aggiungi una o più delle opzioni di accesso che gestisci. Devi assegnare almeno un'opzione di accesso. Per tutte le ulteriori opzioni di accesso che non aggiungi e configuri, viene assegnato il valore predefinito **nessun accesso**. Potresti visualizzare una o tutte le seguenti opzioni di accesso, a seconda delle opzioni che sei autorizzato a gestire:

  * **Servizi**
  * **Accesso Cloud Foundry**
  * **Accesso all'infrastruttura classica**.

  Per ulteriori informazioni, vedi [Assegnazione dell'accesso utente](/docs/iam/iamuserinv.html#assignaccess).

Se determini che un utente non ha bisogno dell'accesso, puoi annullare un invito per tutti gli utenti visualizzati in uno stato **Elaborazione** o **In sospeso** nella colonna **Stato**. Se un utente invitato non riceve un invito, puoi reinviare l'invito a tutti gli utenti nello stato **In sospeso**.

Se vuoi invitare gli utenti utilizzando la CLI (command-line interface), vedi il comando [ibmcloud account user-invite](/docs/cli/reference/ibmcloud/cli_acct_org_role.html#ibmcloud_account_user_invite).
{: tip}

## Assegnazione dell'accesso utente da un invito
{: #assignaccess}

Assegni l'accesso per gli utenti nel momento in cui li inviti, assegnando le politiche {{site.data.keyword.Bluemix}} IAM, l'accesso Cloud Foundry e le autorizzazioni dell'infrastruttura classica. A seconda delle opzioni di accesso che sei autorizzato a gestire, puoi invitare e fornire l'accesso agli utenti per l'account, i gruppi di risorse, le organizzazioni, gli spazi, le istanze del servizio e l'infrastruttura classica. Le seguenti sezioni descrivono i tre tipi di accesso che puoi assegnare a un utente invitato.

### Servizi

Puoi assegnare l'accesso creando una politica di accesso {{site.data.keyword.Bluemix_notm}} IAM iniziale quando inviti un nuovo utente. Nella sezione Servizi, puoi fornire a un utente l'accesso ai servizi di gestione dell'account, ai servizi in un gruppo di risorse con accesso per gestire il gruppo di risorse o a una singola risorsa nell'account.

Dopo che l'utente ha accettato l'invito, puoi assegnare un accesso aggiuntivo. Vedi [Gestione dell'accesso alle risorse](/docs/iam/mngiam.html#iammanidaccser) per dettagli sulla modifica delle politiche per aggiungere altri ruoli, assegnare un ulteriore accesso o rimuovere una politica per un utente.

A seconda del servizio che selezioni quando assegni la politica, potresti non vedere tutti i campi descritti nelle seguenti procedure.
{: note}

#### Accesso ai servizi di gestione dell'account

Per delegare alcune delle tue responsabilità come proprietario dell'account, puoi fornire a un utente l'accesso ai servizi di gestione dell'account. Ad esempio, puoi delegare la capacità di visualizzare la fatturazione e l'utilizzo, di invitare gli utenti remoti, di gestire i gruppi di accesso o gli ID servizio. Puoi fornire l'accesso a tutti i servizi di gestione dell'account o a solo uno.

1. Dalla schermata **Invita utenti**, espandi la sezione **Servizi**.
2. Seleziona per assegnare l'accesso ai **servizi di gestione dell'account**
3. Seleziona **Tutti i servizi di gestione account** o seleziona un servizio specifico.
4. Seleziona qualsiasi combinazione di ruoli per assegnare l'accesso desiderato.

#### Accesso al gruppo di risorse

Puoi assegnare l'accesso a tutti i servizi all'interno di un gruppo di risorse o a un singolo tipo di servizio in un gruppo di risorse.

1. Dalla schermata **Invita utenti**, espandi la sezione **Servizi**.
2. Seleziona l'opzione per assegnare l'accesso alle risorse in un **Gruppo di risorse**.
3. Scegli un gruppo di risorse.
4. Scegli un ruolo per il campo **Assegna accesso a un gruppo di risorse** per consentire all'utente di visualizzare il gruppo di risorse nell'elenco delle risorse, modificare il nome del gruppo di risorse o gestire l'accesso dell'utente al gruppo. Puoi selezionare **Nessun accesso** se vuoi che l'utente possa accedere solo alla risorsa da te specificata e non al gruppo in cui è organizzata.
5. Seleziona un servizio nel gruppo di risorse o scegli di fornire l'accesso a tutti i servizi all'interno del gruppo selezionato.
6. Seleziona qualsiasi combinazione di ruoli per assegnare l'accesso desiderato. Questo accesso si applica solo alle risorse che hai selezionato per la politica. Non dà accesso al contenitore reale che è il gruppo di risorse.

#### Accesso alla risorsa

Puoi assegnare l'accesso a una singola risorsa all'interno del tuo account a seconda dell'istanza.

1. Dalla schermata **Invita utenti**, espandi la sezione **Servizi**.
2. Seleziona l'opzione per assegnare l'accesso a una **Risorsa**.
3. Seleziona un servizio.
4. Seleziona **Tutte le regioni correnti** su una specifica regione, se ti viene richiesto.
5. Seleziona **Tutte le istanze del servizio correnti** o una specifica istanza del servizio.
6. A seconda del servizio che hai selezionato, potresti visualizzare i seguente campi. Se non immetti valori per questi campi, la politica viene assegnata a livello dell'istanza del servizio anziché a livello del bucket.
    * **Tipo di risorsa**: immetti `bucket`.
    * **ID risorsa**: immetti il nome del tuo bucket.
7. Seleziona qualsiasi combinazione di ruoli per assegnare l'accesso desiderato.

Per ulteriori informazioni sui ruoli che vengono utilizzati quando assegni l'accesso, vedi [Accesso IAM](/docs/iam/users_roles.html#iamusermanrol).

### Accesso Cloud Foundry

Quando inviti un nuovo utente, puoi scegliere di aggiungerlo a un'organizzazione nell'account. Se aggiungi l'utente a un'organizzazione, puoi assegnargli un ruolo di organizzazione. Quindi, scegli di dare all'utente invitato l'accesso a qualsiasi spazio (o anche a tutti) nell'organizzazione selezionata con un ruolo dello spazio assegnato.

1. Dalla schermata **Invita utenti**, espandi la sezione **Accesso Cloud Foundry**.
2. Seleziona un'organizzazione a cui aggiungere l'utente.
3. Seleziona un ruolo organizzazione per definire il livello di accesso per l'organizzazione selezionata.
4. Facoltativo: seleziona **Aggiungi ruolo organizzazione** per specificare un ruolo supplementare.
5. Seleziona **Tutte le regioni correnti** o una regione specifica.
6. Seleziona **Tutti gli spazi correnti** o uno specifico spazio.
7. Seleziona un ruolo spazio per definire il livello di accesso per gli spazi selezionati.
8. Facoltativo: seleziona **Aggiungi ruolo spazio** per specificare un ruolo supplementare.

Per ulteriori informazioni sui ruoli che vengono utilizzati quando assegni l'accesso, vedi [Ruoli Cloud Foundry](/docs/iam/cfaccess.html#cfroles).

Puoi aggiungere un ruolo Cloud Foundry utilizzando il comando della CLI [ibmcloud account user-invite](/docs/cli/reference/ibmcloud/cli_acct_org_role.html#ibmcloud_account_user_invite), ma per assegnare un altro accesso o altre autorizzazioni è necessario utilizzare la console.
{: tip}

### Accesso all'infrastruttura classica

Le autorizzazioni che vengono assegnate sono automaticamente limitate al sottoinsieme di autorizzazioni di cui disponi. Diventi l'utente principale di qualsiasi utente che inviti.

1. Dalla schermata **Invita utenti**, espandi la sezione **Accesso all'infrastruttura classica**.
2. Seleziona una serie di autorizzazioni per assegnare autorizzazioni in blocco predefinite.

L'accesso ai dispositivi viene concesso separatamente dopo che l'utente viene aggiunto. Vai all'opzione di accesso **Infrastruttura classica** per un utente nella console.
{: note}

Per informazioni sulla configurazione dell'accesso per gli utenti dopo che sono stati aggiunti al tuo account, vedi [Gestione dell'accesso all'infrastruttura classica](/docs/iam/mnginfra.html#managing-infrastructure-access).

## Aggiunta di utenti solo VPN
{: #add-vpn-only}

Come proprietario dell'account o come utente con l'autorizzazione di gestione utenti dell'infrastruttura classica, puoi aggiungere un utente solo VPN.

1. Dalla pagina **Utenti**, fai clic su **Aggiungi utente solo VPN**.
3. Immetti i dettagli delle informazioni personali per l'utente.
4. Fai clic su **Salva**.
