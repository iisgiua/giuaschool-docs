---
layout: default
title: Uso dei moduli
parent: Procedure
nav_order: 3
---

# Uso dei moduli di richiesta
{: .no_toc .text-center .fw-400 .pb-5}

<details markdown="block">
  <summary>Indice dei contenuti</summary>
  {: .text-delta .text-center}
1. TOC
{:toc}
</details>
{: .my-5 .px-4 style="background-color:#efefef;border:1px solid #cccccc"}


## I moduli di richiesta

I moduli di richiesta consentono di semplificare la gestione di alcune istanze tipiche, provenienti
dai genitori o dagli alunni e rivolte ai docenti o alla scuola.
Alcuni tipi di richiesta hanno una gestione che viene automatizzata completamente sul registro, ma
se ne possono aggiungere altre, la cui gestione sarà però limitata alle funzioni essenziali.

Per ogni modulo di richiesta inviato, viene creato il corrispondente documento in formato PDF, archiviato assieme agli
altri documenti prodotti nel corso dell'anno scolastico.


## Configurazione di un modulo di richiesta

Per creare un nuovo modulo di richiesta, come utente _amministratore_, andare alla pagina
**SCUOLA > MODULI DI RICHIESTA** e cliccare sul pulsante **AGGIUNGI**, presente a fine pagina.
Nella pagina di inserimento che verrà mostrata, si dovranno indicare:

- **Nome del modulo**: il nome identificativo della richiesta;
- **Utenti che possono presentare il modulo**: il tipo di utenti che sono autorizzati all'invio del modulo (_es. Genitori_);
- **Utenti che possono gestire la richiesta**: il tipo di utenti che sono autorizzati a gestire la richiesta (_es. Staff_);
- **Lista dei campi da compilare**: la definizione dei dati che dovranno essere inseriti da chi invia la richiesta;
    per ciascun dato si dovrà indicare il nome univoco, il tipo e se il suo inserimento è obbligatorio;
- **Nome del file del modello**: il modello (_template_) da usare per il modulo;
- **Numero di allegati da inserire nella richiesta**: il numero di documenti che dovranno essere allegati alla richiesta (0 = nessuno);
- **Codifica del tipo di richiesta**: il codice di un carattere usato per distinguere la gestione utilizzata per i moduli;
- **Ammessa una sola richiesta per utente**: indica se consentire l'invio di più richieste o solo una per utente.

Si tenga presente che attualmente i docenti possono gestire solo una tipologia di modulo, relativa alle
uscite anticipate, come sarà spiegato in seguito.

I file del modello (_template_) vanno caricati nella cartella **templates/PERSONALI/moduli**.
Il formato dei modelli sarà illustrato negli esempi seguenti.

La codifica del tipo di richiesta consente di avere più moduli con lo stesso tipo gestione.
I codici definiti di seguito indicano le gestioni che sono implementate sul registro:
- **U**: gestione delle richieste di uscita anticipata;
- **D**: gestione delle richieste di deroga all'orario di uscita;
- **E**: gestione delle richieste di deroga all'orario di entrata.

Ogni altro codice utilizzerà una gestione generica per le richieste.

Una volta creato il modulo, questo può essere successivamente modificato o cancellato.
E' anche possibile disabilitare il modulo: questo renderà impossibile l'inserimento di
nuove richieste e la gestione di quelle esistenti.


## Esempio 1: richieste di uscita anticipata per un dato giorno

Questo esempio illustra la tipologia di gestione indicata con il codice **U**.

Nel caso si voglia consentire le uscite anticipate solo tramite autorizzazione preventiva,
si dovrà anzi tutto impostare il parametro di configurazione **gestione_uscite** al valore **A**.

Si andrà quindi a creare un nuovo modulo con i seguenti valori:
- **Nome del modulo**: Richiesta uscita anticipata per la data indicata
- **Utenti che possono presentare il modulo**: Genitori, Alunni maggiorenni
- **Utenti che possono gestire la richiesta**: Staff, Docenti
- **Lista dei campi da compilare**:
  - nome: ora, tipo: ORA, obbligatorio: SI
  - nome: motivazione, tipo TESTO SU PIU' RIGHE, obbligatorio: SI
- **Nome del file del modello**: uscita_anticipata
- **Numero di allegati da inserire nella richiesta**: 0
- **Codifica del tipo di richiesta**: U
- **Ammessa una sola richiesta per utente**: NO

Viene indicato che sono possibili più richieste per utente, perché si può fare più volte
richiesta per l'uscita anticipata. Quando si usa questa impostazione, poiché la richiesta
sarà necessariamente relativa ad una certa data, questo campo viene inserito automaticamente,
senza dover essere specificato:
- nome: data, tipo: DATA, obbligatorio: SI

A questo punto, genitori o alunni maggiorenni potranno andare alla pagina **RICHIESTE** per
inserire la richiesta di uscita anticipata.
Il modulo dovrà essere inserito entro una certa ora del giorno precedente alla data indicata per
l'uscita. Per configurare l'ora entro cui inviare le richieste, modificare il parametro
di configurazione **scadenza_invio_richiesta**.
Una volta inserita la richiesta, il genitore o alunno maggiorenne la vede nello stato IN ATTESA.

La procedura di gestione prevede che, al momento in cui l'alunno chiede di uscire, il docente
dell'ora o qualcuno dello staff controlli la presenza della richiesta e confermi l'autorizzazione.
Il docente potrà fare questa operazione dalla pagina **LEZIONI > ASSENZE**, cliccando sul pulsante U
relativo al nome dell'alunno.
Lo staff, invece, potrà farlo dalla pagina **STAFF > STUDENTI > RITARDI E USCITE**.

Al momento della conferma dell'uscita, la richiesta passa nello stato GESTITA.

I moduli di richiesta, in formato PDF, vengono conservati nell'archivio dei documenti di classe;
ad esempio, se la classe è la 1A, il documento si troverà nella cartella
**FILES/archivio/classi/1A/documenti**.



## ...

Il modello usato è nel formato _twig_, che corrisponde ad una pagina HTML in cui si possono
inserire dei dati parametrici indicat da doppie parentesi graffe. Ad esempio:
```
<p>Il/La sottoscritto/a <em>{{ app.user.nome }} {{ app.user.cognome }}</em>,
genitore/tutore dell'alunno/a...</p>
```
