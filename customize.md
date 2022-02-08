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

L'applicazione **giua@school** è nata dalla volontà di utilizzare un Registro Elettronico _open source_
per le attività scolastiche dell'**Istituto di Istruzione Superiore "Michele Giua"**.
Di conseguenza, risponde alle esigenze organizzative di questa scuola, sia per quanto
riguarda la gestione didattica che quella amministrativa.

Seppure si stia cercando di rendere,
via via, sempre più configurabile ogni aspetto della gestione del registro, rimangono
tuttora diverse funzionalità che è possibile personalizzare solo attraverso apposite
modifiche del codice dell'applicazione.


## Personalizzazione delle pagine del registro

Ogni pagina visualizzata nel registro elettronico corrisponde ad un _template_: un modello
scritto utilizzando [Twig](https://twig.symfony.com/), che permette di effettuare delle
modifiche nella visualizzazione dei dati e del loro aspetto, senza necessità di
scrivere codice di programmazione PHP.

Modificando i _template_, si può cambiare il testo dei messaggi visualizzati, il loro aspetto,
o anche nascondere informazioni ritenute poco utili.

Tutti i _template_ si trovano nella cartella **templates**.

Inoltre, è presente anche una codifica dei messaggi di uso frequente:
si usa un'etichetta che li identifica e ne permette l'utilizzo nei _template_.

Anche questi messaggi sono facilmente modificabili e si trovano all'interno della
cartella **translations**.


## Personalizzazione dei documenti prodotti
DA COMPLETARE

## Passi da eseguire per le personalizzazioni
DA COMPLETARE
