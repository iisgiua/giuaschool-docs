---
layout: default
title: Gestione ritardi e uscite
parent: Procedure
nav_order: 4
---

# Gestione dei ritardi e delle uscite anticipate
{: .no_toc .text-center .fw-400 .pb-5}

<details markdown="block">
  <summary>Indice dei contenuti</summary>
  {: .text-delta .text-center}
1. TOC
{:toc}
</details>
{: .my-5 .px-4 style="background-color:#efefef;border:1px solid #cccccc"}


## Gestione dei ritardi

I ritardi vengono inseriti dai docenti dalla pagina **LEZIONI > ASSENZE**, cliccando sul pulsante
**R** relativo ad un certo alunno.

Si definisce il _ritardo breve_ come un lieve ritardo per il quale non è richiesta la
giustificazione. La durata di tale ritardo viene inserita nel parametro di configurazione _ritardo_breve_.
Di conseguenza, se il ritardo è entro i minuti specificati nel parametro, non viene chiesta la giustificazione.
Appena si supera questo valore, viene segnato il ritardo da giustificare.

Esiste un conteggio separato dei ritardi che serve per tenere traccia di quelli validi per il numero
massimo di ritardi ammessi. E' infatti spesso presente nel regolamento di Istituto un numero massimo
di ritardi, oltre il quale avviene una sanzione o una comunicazione alla famiglia.
La necessità di avere tale secondo contatore dei ritardi è dovuta al fatto che non tutti i ritardi
possono essere ritenuti validi per tale conteggio.
Ad es., si possono non considerare i ritardi dovuti ai mezzi pubblici, perché non imputabili all'alunno.

La gestione dei ritardi può essere effettuata anche dallo staff, utilizzando la
pagina **STAFF > STUDENTI > RITARDI E USCITE**.

Se la scuola non è interessata a tale conteggio, può semplicemente ignorarlo, o personalizzare i
template per non visualizzare questa informazione alle famiglie.


## Gestione delle uscite anticipate

E' presente apposito parametro di configurazione, chiamato _gestione_uscite_, che permette di
distinguere due gestioni differenti:
- la gestione delle uscite con giustificazione (indicata con **G** nel parametro);
- la gestione tramite autorizzazione preventiva (indicata con **A** nel parametro).

La gestione tramite giustificazioni funziona esattamente come quella dei ritardi.
Anche qui è previsto un conteggio separato per i ritardi validi per il numero massimo previsto.

La gestione tramite autorizzazione permette di inserire l'uscita anticipata, intesa
come autorizzazione.
La procedura può essere eseguita dai docenti, dalla pagina **LEZIONI > ASSENZE**,
cliccando sul pulsante **U** relativo ad un dato studente.

In alternativa, le uscite anticipate possono essere gestite dallo staff, dalla pagina
**STAFF > STUDENTI > RITARDI E USCITE**.

E' anche prevista la possibilità di inserire un modulo di richiesta per l'autorizzazione
all'uscita anticipata. Se la richiesta è presente, sarà visualizzata nella pagina di gestione
dell'autorizzazione all'uscita.

Per maggiori dettagli sulle richieste, si veda [la pagina dei moduli di richiesta](/task-request.md).
