---
layout: default
title: Uso delle consultazioni
parent: Procedure
nav_order: 5
---

# Uso delle consultazioni
{: .no_toc .text-center .fw-400 .pb-5}

<details markdown="block">
  <summary>Indice dei contenuti</summary>
  {: .text-delta .text-center}
1. TOC
{:toc}
</details>
{: .my-5 .px-4 style="background-color:#efefef;border:1px solid #cccccc"}


## Le consultazioni

L'uso delle consultazioni è utile per acquisire formalmente un parere da parte di genitori o alunni.

Nasce dall'esigenza di evitare la convocazione di una assemblea in presenza che, soprattutto per i genitori, spesso non ha una grande partecipazione: tramite la consultazione online si conta di mettere tutti in condizione di far valere la propria opinione.

Il sistema consente all'utente _amministratore_ di:
- creare nuove consultazioni;
- modificarne le caratteristiche;
- scegliere le classi destinatarie;
- creare campi personalizzati;
- associare un modello (_template_) per la visualizzazione.

Gli utenti appartenenti allo _staff_ possono:
- consultare i risultati;
- esportare gli esiti in formato PDF.

## Gestione delle consultazioni

Come utente _amministratore_, andando alla pagina **SCUOLA > CONSULTAZIONI** si potrà
vedere l'elenco di tutte le consultazioni presenti nel sistema.

Per ciascuna consultazione vengono mostrate le seguenti informazioni:
- Stato (abilitata/disabilitata);
- Nome della consultazione;
- Inizio/Fine del periodo di validità;
- Azioni disponibili.

Da questa pagina è possibile creare, modificare o cancellare una consultazione.
Inoltre si può disabilitarla o abilitarla, rendendendola indisponibile quando necessario.


## Creazione, modifica e cancellazione di una consultazione

Per creare una nuova consultazione, come utente _amministratore_, andare alla pagina
**SCUOLA > CONSULTAZIONI** e cliccare sul pulsante **AGGIUNGI**, presente a fine pagina.

Nella pagina di inserimento che verrà mostrata, si dovranno indicare:
- **Nome della consultazione**: titolo identificativo della consultazione;
- **Sede**: la sede scolastica a cui è rivolta la consultazione;
- **Data** e **Ora dell'apertura della consultazione**: inizio dell'intervallo temporale in cui si potrà compilare la consultazione;
- **Data** e **Ora della chiusura della consultazione**: fine dell'intervallo temporale in cui si potrà compilare la consultazione;
- **Destinatari della consultazione**: tipo di utenti che possono rispondere alla consultazione (_Genitori_ o _Alunni_);
- **Classi dei destinatari**: classi a cui è rivolta la consultazione;
- **Lista dei campi della consultazione**: la definizione dei dati che dovranno essere inseriti da chi invia la consultazione; per ciascun dato si dovrà indicare:
  - **Nome del campo**: il nome che identifica il dato raccolto; il nome può contenere solo lettere e cifre;
  - **Tipo del campo**: il tipo determina la modalità con cui l'utente inserirà il dato;
  - **Campo obbligatorio**: indica se l'utente è obbligato a inserire il dato o se può lasciarlo in bianco.
- **Nome del file del modello**: il modello (_template_) da usare per il modulo.

Si tenga presente che i nomi dei campi devono essere univoci: non è possibile utilizzare due campi con lo stesso nome all'interno di una consultazione.

Come per i moduli di richiesta, il modello (_template_) usato è nel formato _Twig_, che corrisponde ad una pagina HTML in cui si possono inserire dei valori variabili, indicati da doppie parentesi graffe, e altri comandi
racchiusi tra parentesi graffe e simbolo di percentuale.
Si veda la [documentazione sui moduli di richiesta](/task-request.md) per maggiori dettagli.

L'elenco dei modelli disponibili viene caricato automaticamente tra quelli presenti nella cartella
**PERSONAL/data/consultazioni**.

Dalla pagina di gestione è anche possibile modificarne una esistente, cliccando sul pulsante **MODIFICA**: si potranno modificare tutte le informazioni inserite.

Si può inoltre cancellare una consultazione, cliccando sul pulsante **CANCELLA**: se però risultano risposte già pervenute, l'eliminazione non sarà permessa.


## Esiti delle consultazioni

Per visualizzare le consultazioni come utente _staff_, andare alla pagina
**STAFF > MODULI > CONSULTAZIONI**.
Saranno mostrate solo le consultazioni abilitate, con indicato il nome, lo stato (in attesa, in corso, terminata) e il numero di risposte ricevute.

Cliccando sul pulsante **DETTAGLI** saranno mostrate le impostazioni della consultazione: lo stato, il periodo di tempo previsto per la consultazione e i destinatari.

Nel caso di una consultazione terminata, usando i pulsanti **MOSTRA ESITO** o **SCARICA ESITO**, è possibile generare un report con l'esito della consultazione,
con le statistiche dettagliate dei votanti e delle diverse risposte ricevute.


## Risposta ad una consultazione

Quando una consultazione è abilitata e siamo all'interno del periodo indicato, i destinari possono visualizzarla e inviare la risposta dalla pagina **MODULI**.

Potranno visualizzare il modulo di autorizzazione solo i genitori e gli studenti appartenenti alle sedi e classi che sono state indicate come destinatarie.
Il modulo non sarà più visibile una volta passata la data indicata per lo svolgimento della consultazione.

Quando il genitore o lo studente compila il modulo della consultazione:
1. viene registrata la data e l'ora dell'invio;
2. viene generato automaticamente il documento PDF;
3. il documento viene archiviato nei documenti di classe.

Genitori e studenti possono scaricare la propria risposta alla consultazione.


## Esempio di consultazione

Questo esempio illustra la modalità di utilizzo di una consultazione per acquisire il parere di genitori e alunni su un cambio nell'organizzazione dell'orario delle lezioni.

Per prima cosa si dovrà caricare sul server il modello necessario.
Per fare questo seguire i seguenti passi:
- verificare che esista la cartella **PERSONAL/data/consultazioni**; se non dovesse esistere, crearla;
- caricare sul server, all'interno della cartella **PERSONAL/data/consultazioni**, il modello seguente.
  - [settimana_corta.html.twig](/assets/docs/settimana_corta.html.twig)

Si dovrà creare una nuova consultazione con i valori seguenti:
- **Nome della consultazione**: Introduzione della settimana corta;
- **Sede**: qualsiasi;
- **Data** e **Ora dell'apertura della consultazione**: ad es. 01/09/2026 ore 0:00;
- **Data** e **Ora della chiusura della consultazione**: ad es. 11/09/2026 ore 23:59;
- **Destinatari della consultazione**: Genitori e Alunni;
- **Classi dei destinatari**: tutte;
- **Lista dei campi della consultazione**: si userà un solo campo, definito nel modo seguente
  - **Nome del campo**: risposta;
  - **Tipo del campo**: SI/NO;
  - **Campo obbligatorio**: si.
- **Nome del file del modello**: settimana_corta.
