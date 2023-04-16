---
layout: default
title: Personalizzazione
nav_order: 6
---

# Personalizzazione
{: .no_toc .text-center .fw-400 .pb-5}

<details markdown="block">
  <summary>Indice dei contenuti</summary>
  {: .text-delta .text-center}
1. TOC
{:toc}
</details>
{: .my-5 .px-4 style="background-color:#efefef;border:1px solid #cccccc"}

## Perché è necessario personalizzare il registro

Seppure si stia cercando di rendere sempre più configurabile ogni aspetto della gestione del registro,
rimangono tuttora diverse funzionalità che è possibile personalizzare solo attraverso apposite
modifiche del codice dell'applicazione.

Questo è dovuto al fatto che l'applicazione **giua@school** nasce
per rispondere alle esigenze organizzative e didattiche dell'
**I.I.S. Istituto di Istruzione Superiore "Michele Giua"**: solo successivamente
si è deciso di renderla di uso più generale, iniziando un processo di revisione
del codice che è ancora in corso.


## Personalizzazione delle pagine del registro

Ogni pagina visualizzata nel registro elettronico corrisponde ad un _template_: un modello
scritto utilizzando [Twig](https://twig.symfony.com/), che permette di effettuare delle
modifiche nella visualizzazione dei dati e del loro aspetto, senza necessità di
scrivere codice di programmazione PHP.

Modificando i _template_, si può cambiare il testo dei messaggi visualizzati, il loro aspetto,
o anche nascondere informazioni ritenute poco utili.

Tutti i _template_ si trovano nella cartella **templates/**.

**ATTENZIONE**: se si desidera personalizzare un _template_, non si dovrà modificare direttamente il file,
ma bisognerà copiarlo all'interno della cartella **PERSONAL/templates/** e poi modificarlo.
Il sistema cerca prima eventuali template personalizzati all'interno della cartella **PERSONAL/templates/**,
ma se non li trova utiizza quelli predefiniti presenti nella cartella **templates/**.
Questo meccanismo permette di evitare che, durante gli aggiornamenti, si vada a sovrascrivere
il proprio template personalizzato con quello predefinito contenuto nella nuova versione.

Si faccia attenzione a replicare sempre lo stesso percorso del template predefinito.
Ad esempio, se si desidera modificare la pagina iniziale di login, copiare il file
**templates/login/form.html.twig** in **PERSONAL/templates/login/form.html.twig** e poi
modificarlo.


## Personalizzazione dei messaggi

Nelle pagine visualizzate è presente anche una codifica dei messaggi di uso frequente:
si usa un'etichetta che li identifica e ne permette l'utilizzo sia nei _template_ che nel codice
dell'applicazione.

Anche questi messaggi sono facilmente modificabili e si trovano all'interno della
cartella **translations/**.

**ATTENZIONE**: se si desidera personalizzare i messaggi, non si dovranno modificare direttamente
i file presenti nella cartella indicata,
ma bisognerà creare un nuovo file con lo stesso nome all'interno della cartella **PERSONAL/translations/**.
Il nuovo file conterrà solo le etichette dei messaggi da personalizzare.

Il sistema cerca l'etichetta del messaggio prima nei file all'interno dei file
presenti nella cartella **PERSONAL/translations/**,
ma se non li trova utiizza quelli predefiniti nella cartella **translations/**.
Questo meccanismo permette di evitare che, durante gli aggiornamenti, si vada a sovrascrivere
i messaggi personalizzati con quelli predefiniti contenuti nella nuova versione.


## Personalizzazione dell'intestazione dei documenti

L'intestazione dei documenti con i dati della scuola è riportata come immagine,
nel formato grafico JPEG, di dimensione 1000x252 pixel.

L'intestazione predefinita è presente nel file **public/img/intestazione-documenti.jpg**.

Se si desidera personalizzarla, creare una nuova immagine nel formato grafico JPEG, delle stesse
dimensioni di quella originale. Salvare poi la nuova immagine nel percorso seguente:
**PERSONAL/img/intestazione-documenti.jpg**


## Personalizzazione dei documenti degli scrutini

Anche i documenti degli scrutini sono generati attraverso l'uso di _template_, come indicato
in precedenza.
Tutti i modelli per i documenti degli scrutini si trovano nella cartella **templates/coordinatore/documenti**.

In particolare, sono sicuramente da personalizzare i seguenti modelli:
  - **scrutinio_verbale_P.html.twig**: verbale dello scrutinio intermedio del primo periodo (Primo Trimestre/Quadrimestre/Pentamestre);
  - **scrutinio_verbale_S.html.twig**: verbale dello scrutinio intermedio del secondo periodo (Secondo Trimestre);
  - **scrutinio_verbale_F.html.twig**: verbale dello scrutinio finale;
  - **scrutinio_verbale_E.html.twig**: verbale dello scrutinio per gli esami della sospensione del giudizio;
  - **scrutinio_verbale_X.html.twig**: verbale dello scrutinio rinviato;
  - **scrutinio_debiti_P.html.twig**: comunicazione dei debiti per lo scrutinio intermedio del primo periodo (Primo Trimestre/Quadrimestre/Pentamestre);
  - **scrutinio_debiti_S.html.twig**: comunicazione dei debiti per lo scrutinio intermedio del secondo periodo (Secondo Trimestre);
  - **scrutinio_debiti_F.html.twig**: comunicazione dei debiti per lo scrutinio finale.

Non dovrebbero avere necessità di modifica, invece, i seguenti modelli:
  - file che iniziano con **scrutinio_pagella_**: comunicazione dei voti dello scrutinio relativo al periodo indicato;
  - file che iniziano con **scrutinio_non_ammesso_**: comunicazione di non ammissione relativa al periodo indicato;
  - file che iniziano con **scrutinio_carenze_**: comunicazione delle carenze con recupero autonomo relative al periodo indicato;
  - file che iniziano con **scrutinio_riepilogo_**: quadro di riepilogo dei voti allegato al verbale dello scrutinio del periodo indicato;
  - file che iniziano con **scrutinio_tabellone_**: tabellone degli esiti della classe, relativo allo scrutinio del periodo indicato;
  - file che iniziano con **scrutinio_firme_**: foglio firme per il registro generale dei voti, relativo allo scrutinio del periodo indicato;
  - **scrutinio_certificazioni.html.twig**: certificazione delle competenze per le classi seconde;
  - **intestazione.html.twig**: intestazione per i documenti;
  - **firma.html.twig**: firma finale per i documenti.

Sono inoltre da personalizzare i criteri per il voto di condotta, che vengono riportati a verbale.
Si trovano nel file **translations/messages+intl-icu.it.yml**.
I criteri della condotta sono indicati con le etichette seguenti (corrispondenti ai possibili voti):
  - **message.giudizio_condotta_NC**
  - **message.giudizio_condotta_5**
  - **message.giudizio_condotta_6**
  - **message.giudizio_condotta_7**
  - **message.giudizio_condotta_8**
  - **message.giudizio_condotta_9**
  - **message.giudizio_condotta_10**


## Passi da eseguire per le personalizzazioni

Una volta effettuata la modifica di un _template_ o del file dei messaggi, è sempre necessario cancellare
la _cache_. Per fare questo, come utente amministratore, andare alla pagina **SISTEMA > MANUTENZIONE**
e poi cliccare sul pulsante **SVUOTA CACHE**.

Nel caso di modifica dei documenti dello scrutinio, se sono già stati creati in precedenza i
documenti da modificare, sarà anche necessario riaprire lo scrutinio e poi chiuderlo di nuovo, in modo
da cancellare le vecchie versioni di tali documenti.
