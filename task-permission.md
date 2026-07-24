---
layout: default
title: Uso delle autorizzazioni
parent: Procedure
nav_order: 4
---

# Uso delle autorizzazioni
{: .no_toc .text-center .fw-400 .pb-5}

<details markdown="block">
  <summary>Indice dei contenuti</summary>
  {: .text-delta .text-center}
1. TOC
{:toc}
</details>
{: .my-5 .px-4 style="background-color:#efefef;border:1px solid #cccccc"}


## Autorizzazioni per le attività scolastiche

La funzione **Autorizzazioni** consente ai componenti dello _staff_ di creare, pubblicare e gestire i moduli di autorizzazione che i genitori dovranno firmare per consentire ai propri figli la partecipazione ad attività organizzate dalla scuola.
Nel caso di studenti maggiorenni, questi potranno firmare il modulo che diventa una liberatoria.

Il sistema permette ai componenti dello _staff_ di:
- creare nuovi moduli di autorizzazione;
- modificarli;
- limitarli a specifiche sedi o classi;
- abilitarli o disabilitarli;
- visualizzarne l'anteprima;
- consultare le autorizzazioni ricevute;
- esportare l'elenco delle autorizzazioni come documento PDF.

## Configurazione iniziale

Affinché la gestione delle autorizzazioni funzioni correttamente, è necessario caricare nel sistema i modelli (_template_) utlizzati per le varie tipologie di autorizzazione.

I modelli sono disponibili in formato compresso nel file seguente:
- [autorizzazioni.zip](/assets/docs/autorizzazioni.zip)

Per configurare correttamente il sistema, eseguire i seguenti passi:
- verificare che esista la cartella **PERSONAL/data/autorizzazioni**; se non dovesse esistere, crearla;
- scaricare il file con i modelli indicato in precedenza ed estrarlo sul proprio computer;
- caricare sul server i cinque _template_ (uno per tipologia di autorizzazione), all'interno della cartella **PERSONAL/data/autorizzazioni**.

Si faccia attenzione a non modificare i nomi dei file.

I _template_ si possono modificare per adattarli alle proprie esigenze, ma si raccomanda di non alterare i codici corrispondenti al linguaggio _Twig_, individuabili facilmente perché racchiusi tra parentesi graffe.


## Gestione dei moduli di autorizzazione

Per visualizzare l'elenco di tutte le autorizzazioni esistenti, andare alla pagina
**STAFF > MODULI > AUTORIZZAZIONI** .

Per ogni autorizzazione vengono mostrate le principali informazioni:
- Stato (abilitata/disabilitata);
- Sede e classe dei destinatari;
- Tipologia;
- Data e ora dell'attività;
- Nome dell'attività;
- Azioni disponibili.

È possibile limitare l'elenco visualizzato utilizzando uno o più filtri: per sede, per classe, per tipologia dell'attività, per mese di svolgimento dell'attività e per nome (anche parziale) dell'attività.

I filtri vengono memorizzati automaticamente, così da essere mantenuti anche dopo aver aperto una scheda o cambiato pagina.


## Creazione e modifica di un modulo di autorizzazione

Per creare un nuovo modulo di autorizzazione, andare alla pagina **STAFF > MODULI > AUTORIZZAZIONI** e
cliccare sul pulsante **NUOVO**.

Si dovranno inserire i seguenti dati:
- **Nome**: nome dell'attività;
- **Tipo**: tipologia dell'attività che può essere svolta all'esterno della scuola (_Uscita didattica_ o _Visita guidata_) o al suo interno (_Conferenza_, _Evento_ o _Attività generica_);
- **Data**, **Inizio** e **Fine**: data dell'attività, ora di inizio e di fine;
- **Descrizione attività**: breve descrizione dell'attività;
- **Sede**: la sede scolastica a cui è rivolta l'attività;
- **Classi**: le classi a cui è rivolta l'attività.

Per le attività svolte all'esterno della scuola è necessario inserire:
- **Destinazione**: luogo di destinazione in cui viene svolta l'attività;
- **Modalità**: modo in cui gli alunni raggiungono il luogo di destinazione (_A piedi_, _Con i mezzi pubblici_ o _Altro_ da specificare);
- **Accompagnatori**: nomi dei docenti accompagnatori;
- **Luogo di partenza**: luogo di partenza;
- **Rientro**: luogo di rientro degli studenti al termine dell'attività (_a scuola_ o _al proprio domicilio_).

Per le attività svolte all'interno della scuola è necessario inserire:
- **Presso la sede**: la sede scolastica dove viene svolta l'attività;
- **Nell'aula**: nome dell'aula o dell'ambiente dove viene svolta l'attività;
- **Esperti esterni**: nomi degli esperti esterni che partecipano all'attività.

I nuovi moduli di autorizzazione vengono creati inizialmente in stato **Disabilitato**: per renderli disponibili è necessario cliccare sul pulsante **ABILITA**.

Per modificare una autorizzazione esistente, cliccare sul pulsante **MODIFICA** in corrispondenza del modulo desiderato: sarà possibile cambiare tutti i valori inseriti in precedenza.


## Anteprima del modulo di autorizzazione

Cliccando sul pulsante **ANTEPRIMA** in corrispondenza di un modulo di autorizzazione, verrà mostrato l'aspetto del modulo che sarà presentato agli utenti.

Durante l'anteprima:
- i dati personali vengono oscurati;
- è possibile verificare l'aspetto e la formattazione del documento;
- vengono mostrate sia la versione destinata ai genitori che quella destinata agli studenti maggiorenni.

Si consiglia di usare questa funzione prima di abilitare il modulo di autorizzazione.


## Consultazione delle autorizzazioni ricevute

Cliccando sul pulsante **DETTAGLI** in corrispondenza di un modulo di autorizzazione, verranno mostrate le
informazioni sulle autorizzazioni ricevute.

Viene mostrato l'elenco degli studenti autorizzati, separato per classe, con indicato anche da chi risulta firmata l'autorizzazione.

L'elenco delle autorizzazioni può essere esportato in formato PDF, cliccando sul pulsante **SCARICA ELENCO AUTORIZZATI**.

Per tornare alla pagina di gestione dei moduli di autorizzazione, cliccare sul pulsante **TORNA AI MODULI**.


## Firma dell'autorizzazione

Quando una autorizzazione è abilitata, genitori e studenti maggiorenni possono visualizzarla e firmarla dalla pagina **MODULI**.

Potranno visualizzare il modulo di autorizzazione solo i genitori e gli studenti maggiorenni appartenenti alle sedi e classi che sono state indicate come destinatarie.
Il modulo non sarà più visibile una volta passata la data indicata per lo svolgimento dell'attività.


Quando il genitore o lo studente maggiorenne firma il modulo:
1. viene registrata la data e l'ora dell'invio;
2. viene generato automaticamente il documento PDF;
3. il documento viene archiviato nei documenti di classe.

Se per la stessa attività esiste già un'autorizzazione firmata da un altro utente (ad esempio un secondo genitore), il sistema aggiunge in coda al documento esistente la nuova autorizzazione firmata.

Lo stesso utente non può inviare due volte la medesima autorizzazione.

Genitori e studenti maggiorenni possono scaricare il modulo firmato.
