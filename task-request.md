---
layout: default
title: Uso dei moduli
parent: Procedure
nav_order: 3
---

# Uso dei moduli
{: .no_toc .text-center .fw-400 .pb-5}

<details markdown="block">
  <summary>Indice dei contenuti</summary>
  {: .text-delta .text-center}
1. TOC
{:toc}
</details>
{: .my-5 .px-4 style="background-color:#efefef;border:1px solid #cccccc"}


## I moduli per le richieste

Le richieste consentono di semplificare la gestione di alcune istanze tipiche, provenienti
dai genitori o dagli alunni e rivolte ai docenti o alla scuola.
Alcuni tipi di richiesta hanno una gestione che viene automatizzata completamente sul registro, ma
se ne possono aggiungere altre, la cui gestione sarà però limitata alle funzioni essenziali.

Le richieste vengono gestite tramite uno stato, che permette di distinguere la situazione corrente:
- **NUOVE**: indica le nuove richieste inviate, non ancora gestite;
- **GESTITE**: indica le richieste che sono già state gestite (accolte o rifiutate);
- **RIMOSSE**: indica le richieste rifiutate o errate che sono state eliminate da chi è autorizzato alla loro gestione;
- **ANNULLATE**: indica le richieste che sono state annullate dal richiedente.

Per ogni modulo di richiesta inviato, viene creato il corrispondente documento in formato PDF, archiviato assieme agli altri documenti prodotti nel corso dell'anno scolastico.


## I moduli senza gestione

In alcuni casi non serve alcuna gestione degli stati, perché si tratta di un modulo in cui si comunicano
alcune informazioni da archiviare. Un esempio è il modulo per le prove di evacuazione.

In questo caso, i destinatari (tipicamente i componenti dello staff) si limitano ad esaminare i moduli per qualche controllo o a esportarli su un foglio elettronico per rielaborarli secondo le proprie esigenze.

Per ogni modulo inviato viene creato il corrispondente documento in formato PDF, archiviato assieme agli altri documenti prodotti nel corso dell'anno scolastico.


## Configurazione di un modulo di richiesta

Per creare un nuovo modulo di richiesta, come utente _amministratore_, andare alla pagina
**SCUOLA > MODULI DI RICHIESTA** e cliccare sul pulsante **AGGIUNGI**, presente a fine pagina.
Nella pagina di inserimento che verrà mostrata, si dovranno indicare:

- **Nome del modulo**: il nome identificativo della richiesta;
- **Sede**: eventuale sede scolastica alla quale è limitato l'uso della richiesta;
- **Utenti che possono presentare il modulo**: il tipo di utenti che sono autorizzati all'invio del modulo (_es. Genitori_);
- **Utenti che possono gestire la richiesta**: il tipo di utenti che sono autorizzati a gestire la richiesta (_es. Staff_);
- **Lista dei campi da compilare**: la definizione dei dati che dovranno essere inseriti da chi invia la richiesta;
    per ciascun dato si dovrà indicare il nome univoco, il tipo e se il suo inserimento è obbligatorio;
- **Nome del file del modello**: il modello (_template_) da usare per il modulo;
- **Numero di allegati da inserire nella richiesta**: il numero di documenti che dovranno essere allegati alla richiesta (0 = nessuno);
- **Ammessa una sola richiesta per utente**: indica se consentire l'invio di più richieste o solo una per utente.
- **Attiva la gestione degli stati della procedura**: per i moduli di richiesta la gestione degli stati deve essere sempre attivata;
- **Codifica del tipo di richiesta**: il codice di un carattere usato per distinguere la gestione utilizzata per i moduli.

I file del modello (_template_) vanno caricati nella cartella **PERSONAL/data/moduli**.
Il formato dei modelli sarà illustrato negli esempi seguenti.

La codifica del tipo di richiesta consente di avere più moduli con lo stesso tipo gestione.
I codici definiti di seguito indicano le gestioni che sono implementate sul registro:
- **U**: gestione delle richieste di uscita anticipata;
- **D**: gestione delle richieste di deroga all'orario di uscita;
- **E**: gestione delle richieste di deroga all'orario di entrata;
- **\***: gestione generica di un modulo di richiesta.

Una volta creato il modulo, questo può essere successivamente modificato o cancellato.
E' anche possibile disabilitare il modulo: questo renderà impossibile l'inserimento di
nuove richieste e la gestione di quelle esistenti.


## Configurazione di un modulo senza gestione

La creazione di un modulo di questo tipo avviene come illustrato in precedenza, tranne che per il
campo **Attiva la gestione degli stati della procedura** che dovrà essere impostato a _NO_.

Inoltre, viene utilizzata la seguente codifica del tipo modulo:
- **V**: utilizzato per il modulo delle prove di evacuazione;
- **#**: per un modulo generico.


## Esempio 1: richieste di uscita anticipata per un dato giorno

Questo esempio illustra la tipologia di gestione indicata con il codice **U**.

Nel caso si voglia consentire le uscite anticipate solo tramite autorizzazione preventiva,
si dovrà anzi tutto impostare il parametro di configurazione **gestione_uscite** al valore **A**.

Si andrà quindi a creare un nuovo modulo con i seguenti valori:
- **Nome del modulo**: Richiesta uscita anticipata per la data indicata
- **Sede**: lasciare vuoto per tutte le sedi
- **Utenti che possono presentare il modulo**: Genitori, Alunni maggiorenni
- **Utenti che possono gestire la richiesta**: Staff, Docenti
- **Lista dei campi da compilare**:
  - nome: _ora_, tipo: ORA, obbligatorio: SI
  - nome: _motivazione_, tipo TESTO SU PIU' RIGHE, obbligatorio: SI
- **Nome del file del modello**: uscita_anticipata
- **Numero di allegati da inserire nella richiesta**: 0
- **Ammessa una sola richiesta per utente**: NO
- **Attiva la gestione degli stati della procedura**: SI
- **Codifica del tipo di richiesta**: U

Viene indicato che sono possibili più richieste per utente, perché si può fare più volte
richiesta per l'uscita anticipata. Quando si usa questa impostazione, poiché la richiesta
sarà necessariamente relativa ad una certa data, questo campo viene inserito automaticamente,
senza dover essere specificato:
- nome: _data_, tipo: DATA, obbligatorio: SI

A questo punto, genitori o alunni maggiorenni potranno andare alla pagina **RICHIESTE** per
inserire la richiesta di uscita anticipata.
Il modulo dovrà essere inserito entro una certa ora del giorno precedente alla data indicata per
l'uscita. Per configurare l'ora entro cui inviare le richieste, modificare il parametro
di configurazione **scadenza_invio_richiesta**.

Una volta inserita la richiesta, il genitore o alunno maggiorenne la vede nello stato IN ATTESA.

La procedura di gestione prevede che, al momento in cui l'alunno chiede di uscire, il docente
dell'ora o qualcuno dello staff controlli la presenza della richiesta e confermi l'autorizzazione.
Il docente potrà fare questa operazione dalla pagina **LEZIONI > ASSENZE**, cliccando sul pulsante **U**
relativo al nome dell'alunno.
Lo staff, invece, potrà farlo dalla pagina **STAFF > STUDENTI > RITARDI E USCITE**.

Al momento della conferma dell'uscita, la richiesta passa nello stato GESTITA.

I moduli di richiesta, in formato PDF, vengono conservati nell'archivio dei documenti di classe;
ad esempio, se la classe è la 1A, il documento si troverà nella cartella
**FILES/archivio/classi/1A/documenti**.


## Esempio 2: richieste di deroga all'orario di uscita

Questo esempio illustra la tipologia di gestione indicata con il codice **D**.

Si dovrà creare un nuovo modulo con i seguenti valori:
- **Nome del modulo**: Richiesta deroga all'orario di uscita da scuola
- **Sede**: lasciare vuoto per tutte le sedi
- **Utenti che possono presentare il modulo**: Genitori, Alunni maggiorenni
- **Utenti che possono gestire la richiesta**: Staff
- **Lista dei campi da compilare**:
  - nome: _minuti_, tipo: NUMERO INTERO, obbligatorio: SI
  - nome: _giorni_, tipo: TESTO SU UNA RIGA, obbligatorio: SI
  - nome: _mezzo_, tipo: TESTO SU UNA RIGA, obbligatorio: SI
  - nome: _ora_, tipo: ORA, obbligatorio: SI
  - nome: _azienda_, tipo: TESTO SU UNA RIGA, obbligatorio: SI
  - nome: _fermata_, tipo: TESTO SU UNA RIGA, obbligatorio: SI
  - nome: _note_, tipo: TESTO SU PIU' RIGHE, obbligatorio: NO
- **Nome del file del modello**: deroga_orario_uscita
- **Numero di allegati da inserire nella richiesta**: 0
- **Ammessa una sola richiesta per utente**: SI
- **Codifica del tipo di richiesta**: D
- **Attiva la gestione degli stati della procedura**: SI

Viene indicato che è possibile solo una richiesta per utente, perché la deroga vale per
l'intero anno scolastico.

A questo punto, genitori o alunni maggiorenni potranno andare alla pagina **RICHIESTE** per
inserire la richiesta di deroga.
Una volta compilata la richiesta, questa sarà in stato IN ATTESA.
In qualsiasi momento, il genitore o l'alunno maggiorenne potranno annullare la richiesta ed
inserirne una nuova.

La procedura di gestione prevede che sia lo staff (o il dirigente) a concedere l'autorizzazione,
controllando i dati inseriti nella richiesta.
Questa operazione viene effettuata dalla pagina **STAFF > STUDENTI > RICHIESTE**, dove è
possibile vedere tutte le richieste e filtrarle in base al tipo, allo stato, alla sede,
alla classe, al nome dell'alunno o alla sua città di residenza.

Per ogni richiesta è possibile, utilizzando gli appositi pulsanti, vederne i dettagli, gestirla
o rimuoverla.

La gestione di una richiesta permette di inserire una nota nel campo delle _autorizzazioni in uscita_
e cambia lo stato in GESTITA.
Inoltre è possibile inserire un messaggio di risposta che sarà visualizzato dal richiedente.


La rimozione di una richiesta non modifica l'impostazione corrente del campo _autorizzazioni in uscita_,
ma permette solo di inserire un messaggio di risposta che sarà visualizzato dal richiedente.
Lo stato sarà cambiato in RIMOSSA.

Il genitore e l'alunno potranno visualizzare il nuovo stato e il messaggio eventualmente inserito
andando alla pagina **RICHIESTE**.
Inoltre, dalla pagina **SITUAZIONE > AUTORIZZAZIONI** potranno vedere le autorizzazioni concesse.


## Esempio 3: richieste di deroga all'orario di entrata

Questo esempio illustra la tipologia di gestione indicata con il codice **E**.

Si dovrà creare un nuovo modulo con i seguenti valori:
- **Nome del modulo**: Richiesta deroga all'orario di entrata a scuola
- **Sede**: lasciare vuoto per tutte le sedi
- **Utenti che possono presentare il modulo**: Genitori, Alunni maggiorenni
- **Utenti che possono gestire la richiesta**: Staff
- **Lista dei campi da compilare**:
  - nome: _minuti_, tipo: NUMERO INTERO, obbligatorio: SI
  - nome: _giorni_, tipo: TESTO SU UNA RIGA, obbligatorio: SI
  - nome: _mezzo_, tipo: TESTO SU UNA RIGA, obbligatorio: SI
  - nome: _ora_, tipo: ORA, obbligatorio: SI
  - nome: _azienda_, tipo: TESTO SU UNA RIGA, obbligatorio: SI
  - nome: _fermata_, tipo: TESTO SU UNA RIGA, obbligatorio: SI
  - nome: _note_, tipo: TESTO SU PIU' RIGHE, obbligatorio: NO
- **Nome del file del modello**: deroga_orario_ingresso
- **Numero di allegati da inserire nella richiesta**: 0
- **Ammessa una sola richiesta per utente**: SI
- **Attiva la gestione degli stati della procedura**: SI
- **Codifica del tipo di richiesta**: E

La procedura di gestione è del tutto analoga a quella illustrata in precedenza.


## Esempio 4: modulo per la prova di evacuazione

Questo esempio illustra l'utilizzo di un modulo per le prove di evacuazione.

Si dovrà creare un nuovo modulo con i seguenti valori:
- **Nome del modulo**: Prove di evacuazione
- **Sede**: lasciare vuoto per tutte le sedi
- **Utenti che possono presentare il modulo**: Docenti
- **Utenti che possono gestire la richiesta**: Staff
- **Lista dei campi da compilare**:
  - nome: _classe_, tipo: TESTO SU UNA RIGA, obbligatorio: SI
  - nome: _presenti_, tipo: NUMERO INTERO, obbligatorio: SI
  - nome: _evacuati_, tipo: NUMERO INTERO, obbligatorio: SI
  - nome: _dispersi_, tipo: TESTO SU PIU' RIGHE, obbligatorio: NO
  - nome: _feriti_, tipo: TESTO SU PIU' RIGHE, obbligatorio: NO
  - nome: _punto_, tipo: TESTO SU UNA RIGA, obbligatorio: NO
  - nome: _note_, tipo: TESTO SU PIU' RIGHE, obbligatorio: NO
- **Nome del file del modello**: evacuazione
- **Numero di allegati da inserire nella richiesta**: 0
- **Ammessa una sola richiesta per utente**: NO
- **Attiva la gestione degli stati della procedura**: NO
- **Codifica del tipo di richiesta**: V

I docenti potranno compilare il modulo dalla pagina del registro di classe.
In qualsiasi momento, il docente potrà annullare il modulo ed inserirne uno nuovo.

La procedura prevede che sia lo staff a visionare i moduli dal menu **STAFF > MODULI > EVACUAZIONE**.
E' anche possibile esportare i dati in un file in formato CSV, facilmente utilizzabile su tutti i fogli elettronici.


## Esempio 5: modulo di consenso all'invio dei dati

Questo esempio illustra l'utilizzo di un modulo generico senza gestione: si tratta del consenso da parte
degli alunni maggiorenni all'invio dei loro dati alle aziende che ne faranno richiesta.

Si dovrà creare un nuovo modulo con i seguenti valori:
- **Nome del modulo**: Consenso per la diffusione dei dati personali degli studenti
- **Sede**: lasciare vuoto per tutte le sedi
- **Utenti che possono presentare il modulo**: Alunni maggiorenni
- **Utenti che possono gestire la richiesta**: Staff
- **Lista dei campi da compilare**:
  - nome: _autorizza_, tipo: SI/NO, obbligatorio: SI
  - nome: _email_, tipo: TESTO SU UNA RIGA, obbligatorio: NO
  - nome: _telefono_, tipo: TESTO SU UNA RIGA, obbligatorio: NO
- **Nome del file del modello**: diffusione_dati_alunni
- **Numero di allegati da inserire nella richiesta**: 0
- **Ammessa una sola richiesta per utente**: SI
- **Attiva la gestione degli stati della procedura**: NO
- **Codifica del tipo di richiesta**: #

Gli alunni maggiorenni potranno compilare il modulo dalla pagina delle richieste.
In qualsiasi momento, l'alunno potrà annullare il modulo ed inserirne uno nuovo.

La procedura prevede che sia lo staff a visionare i moduli dal menu **STAFF > MODULI > ALTRI**.
E' anche possibile esportare i dati in un file in formato CSV, facilmente utilizzabile su tutti i fogli elettronici.


## Uso dei modelli per i moduli di richiesta (_template_)

Il modello usato è nel formato _Twig_, che corrisponde ad una pagina HTML in cui si possono
inserire dei valori variabili, indicati da doppie parentesi graffe, e comandi
racchiusi tra parentesi graffe e simbolo di percentuale.
Maggiori informazioni sull'uso del formato Twig si trovano all'indirizzo
[https://twig.symfony.com/doc/3.x/](https://twig.symfony.com/doc/3.x/).

Vengono di seguito riportati i modelli utilizzati negli esempi precedenti:
- [uscita_anticipata](/assets/docs/uscita_anticipata.html.twig)
- [deroga_orario_uscita](/assets/docs/deroga_orario_uscita.html.twig)
- [deroga_orario_ingresso](/assets/docs/deroga_orario_ingresso.html.twig)
- [evacuazione](/assets/docs/evacuazione.html.twig)
- [diffusione_dati_alunni](/assets/docs/diffusione_dati_alunni.html.twig)

Per una corretta personalizzazione dei modelli di esempio, si tenga presente che:
- i modelli di richiesta sono divisi in due sezioni, per distinguere se l'utente collegato sia un genitore o un alunno;
- le variabili del tipo **&#123;&#123; app.user.XXX &#125;&#125;** corrispondono
  alle informazioni sull'utente collegato, in modo da inserire automaticamente i dati anagrafici
  nel modulo; queste variabili non sono obbligatorie e si possono usare come si ritiene opportuno;
- le variabili del tipo **&#123;&#123; form_widget(form.XXX) &#125;&#125;** corrispondono
  ai campi per l'inserimento dei dati e sono obbligatorie; è fondamentale che siano presenti tutti
  i campi definiti nel modulo e che abbiamo esattamente gli stessi nomi.
