---

copyright:

  years: 2018

lastupdated: "2018-11-30"

---

{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:screen: .screen}
{:new_window: target="_blank"}
{:tip: .tip}
{:note: .note}

# Concessione di specifici indirizzi IP per un utente
{: #ips}

Per impostazione predefinita, è possibile utilizzare tutti gli indirizzi IP per accedere alla console {{site.data.keyword.cloud}} e alle API dell'infrastruttura classica. Puoi specificare quali indirizzi IP hanno accesso in modo che potranno essere utilizzati solo gli indirizzi specificati mentre tutti gli altri verranno limitati.
{:shortdesc}

Se disponi del seguente accesso assegnato, puoi aggiornare gli indirizzi IP limitati per un altro utente:

  * Una politica IAM con il ruolo Editor o superiore nel servizio di gestione utenti.
  * Sei un predecessore nella gerarchia dell'infrastruttura classica per l'utente e ti è stata assegnata l'autorizzazione di gestione utenti dell'infrastruttura classica

Per limitare un utente a utilizzare solo indirizzi IP specifici, completa la seguente procedura:

1. Dalla barra dei menu, fai clic su **Gestisci** &gt; **Accesso (IAM)** e seleziona **Utenti**.
2. Seleziona un utente dall'elenco.
3. Dalla pagina Dettagli utente, vai alla sezione **Limitazioni indirizzo IP**.
4. Per **Piattaforma cloud**, immetti gli indirizzi IP. Gli indirizzi IP elencati sono gli unici da cui questo utente può accedere a {{site.data.keyword.Bluemix}}.
5. Per **Infrastruttura classica**, immetti gli indirizzi IP. Gli indirizzi IP elencati sono gli unici da cui l'utente può richiamare un'API dell'infrastruttura classica.

  Per immettere un indirizzo IP dell'infrastruttura classica, l'utente deve aver già creato una chiave API dell'infrastruttura classica.
  {: note}

  Puoi gestire autonomamente questa impostazione se l'impostazione di Accesso gestito dall'utente è abilitata nella tua pagina Dettagli utente.
  {: tip}
