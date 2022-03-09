---
layout: default
title: Configurazione
nav_order: 5
---

# Configurazione
{: .no_toc .text-center .fw-400 .pb-5}

<details markdown="block">
  <summary>Indice dei contenuti</summary>
  {: .text-delta .text-center}
1. TOC
{:toc}
</details>
{: .my-5 .px-4 style="background-color:#efefef;border:1px solid #cccccc"}


## Configurazione iniziale

Utilizzando l'utente _amministratore_ è possibile procedere alla configurazione iniziale
dell'applicazione, andando al menu **SISTEMA > PARAMETRI**.

Verranno mostrati i parametri che permettono di modificare il funzionamento
generale dell'applicazione, raggruppati in tre categorie:
  - **ACCESSO**: contenente la configurazione relativa alla procedura di accesso degli utenti;
  - **SCUOLA**: contenente la configurazione relativa all'organizzazione della scuola;
  - **SISTEMA**: contenente la configurazione relativa al funzionamento generale del sistema.

Per ogni parametro viene fornita una breve descrizione del suo uso. In caso di dubbi,
lasciare inalterato il valore predefinito.

Dal menu **SCUOLA**, invece, è possibile inserire o modificare:
- l'utente amministratore e l'utente del Dirigente Scolastico;
- i dati dell'istituto e delle sedi;
- i dati dei corsi di studio, delle materie e delle classi;
- i giorni delle festività annuali;
- la scansione oraria settimanale;
- i dati di gestione degli scrutini.

**Per il corretto funzionamento del registro, dovranno essere obbligatoriamente inseriti**:
- un utente amministratore;
- un utente Dirigente Scolastico;
- i dati dell'istituto;
- i dati di almeno una sede scolastica;
- i dati di almeno un corso di studio e di almeno una classe;
- i dati di un orario con relativa scansione oraria;
- almeno le materie seguenti:
  - 1 materia di tipo **SOSTEGNO**;
  - 1 materia di tipo **EDUCAZIONE CIVICA**;
  - 1 materia di tipo **RELIGIONE**;
  - 1 materia di tipo **CONDOTTA**;
  - 1 materia di tipo **SUPPLENZA**.


## Importazione degli utenti

Sempre come utente _amministratore_ è anche possibile importare gli utenti da file e
modificarli una volta caricati:
- il menu **ATA** gestisce gli utenti relativi al personale ATA;
- il menu **DOCENTI** gestisce gli utenti docenti, permettendo anche di impostare le
    cattedre, i colloqui, i coordinatori, i segretari e i componenti dello staff della
    dirigenza;
- il menu **ALUNNI** gestisce gli utenti alunni, con i dati dei relativi genitori,
    permettendo anche di gestire i trasferimenti in corso d'anno scolastico.

I file di importazione sono nel formato CSV, cioè dei file di testo dove viene usata la virgola come
separatore dei dati. Il file deve contenere la prima riga con tutte le intestazioni previste,
anche se non bisogna necessariamente inserire i valori non obbligatori.

Se si utilizzano lettere accentate all'interno dei file (ad es. _Nicolò_), si faccia
attenzione a salvare i file con la codifica **UNICODE (UTF-8)**: in caso contrario,
durante l'importazione verrà generato un errore che terminerà la procedura.

Come esempio, vengono forniti i file di importazione con alcuni dati di prova:
  - [importazione utenti ATA](/assets/docs/IMPORTA_ATA.csv)
  - [importazione utenti DOCENTI](/assets/docs/IMPORTA_DOCENTI.csv)
  - [importazione cattedre DOCENTI](/assets/docs/IMPORTA_CATTEDRE.csv)
  - [importazione colloqui DOCENTI](/assets/docs/IMPORTA_COLLOQUI.csv)
  - [importazione utenti ALUNNI e GENITORI](/assets/docs/IMPORTA_ALUNNI_GENITORI.csv)


## Configurazione del server email

Durante la procedura di installazione è possibile configurare il server per la spedizione delle email.

**Si tenga presente che la spedizione delle email può essere bloccata o limitata dal servizio
di _hosting_ che si utilizza.**

E' possibile scegliere tra tre modalità per la configurazione:
  - **GMAIL**: verrà utilizzato un utente GMAIL esistente; dalle impostazioni di sicurezza dell'utente GMAIL,
    si dovrà concedere il permesso di utilizzo delle _"app meno sicure"_
    ([vedi la documentazione Google](https://support.google.com/accounts/answer/6010255))

  - **SMTP**: verrà utilizzato un server esterno tramite protocollo SMTP;
    questa modalità richiede i parametri del server di posta forniti dal servizio di _hosting_.

  - **SENDMAIL**: verrà utilizzato un apposito servizio di spedizione (SENDMAIL) presente sul
    server dell'applicazione.

Per poter utilizzare la modalità **SMTP** o **SENDMAIL** è necessario che questa sia prevista
dal proprio servizio di _hosting_.
In alternativa la modalità **GMAIL** dovrebbe funzionare, ma dipende sempre dalle
scelte dell'_hosting_ utilizzato.


## Configurazione dello SPID

Durante la procedura di installazione è possibile configurare l'accesso tramite SPID:
verrà configurato un accesso per lo SPID di livello 1, per le pubbliche amministrazioni.

Per l'attivazione dello SPID bisogna fare riferimento alle indicazioni dell'AgID per
diventare fornitori di servizi:
  - [SPID - Diventa forntore di servizi](https://www.spid.gov.it/cos-e-spid/diventa-fornitore-di-servizi/)

L'AgID prevede una procedura tecnica ed una amministrativa per l'attivazione dello SPID:
la configurazione predisposta risponde ai requisiti tecnici richiesti.
Restano a carico dell'utilizzatore:
  - la verifica di collaudo tramite lo **SPID Validator**;
  - l'invio della richiesta di attivazione all'AgID;
  - la procedura amministrativa.

Nel caso di prima attivazione dello SPID, durante la configurazione si dovrà attivare la
modalità di validazione, in modo da poter eseguire il collaudo.
