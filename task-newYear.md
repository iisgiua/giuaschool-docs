---
layout: default
title: Nuovo A.S.
parent: Procedure
nav_order: 2
---

# Passaggio al nuovo Anno Scolastico
{: .no_toc .text-center .fw-400 .pb-5}

<details markdown="block">
  <summary>Indice dei contenuti</summary>
  {: .text-delta .text-center}
1. TOC
{:toc}
</details>
{: .my-5 .px-4 style="background-color:#efefef;border:1px solid #cccccc"}


## Procedura di passaggio al nuovo anno

Per iniziare il nuovo Anno Scolastico è necessaria un'operazione di pulizia del registro elettronico,
che rimuova tutti i dati non più necessari.
Tale procedura andrà quindi a **distruggere dati e documenti esistenti**, per cui, prima di iniziare,
ci si assicuri di avere effettuato le seguenti operazioni:
  1. [Chiusura dell'Anno Scolastico](/task-endYear.md), con l'archiviazione dei documenti prodotti;
  1. backup completo, dei file e del database, in modo da poter effettuare il ripristino in caso di problemi.

Per eseguire il backup dei file si consiglia un software come **Filezilla**,
che si userà per scaricare sul proprio computer una copia di sicurezza dei file presenti nel server di _hosting_.

Per eseguire il backup del database, si può utilizzare il software **phpMyAdmin**, che solitamente è reso disponibile
dal proprio servizio di _hosting_. Con questa applicazione, si può esportare l'intero database in un file, che
verrà scaricato sul proprio computer. In caso di necessità, la stessa applicazione permette di importare
nel database il file creato in precedenza, ripristinando tutti i dati presenti.


## Iniziare la procedura

La procedura deve essere eseguita dall'utente _amministratore_ e viene suddivisa in diversi passi successivi.
Una volta iniziata, eseguire tutti i passi necessari sino al termine.

Per evitare ogni possibile interferenza durante l'esecuzione della procedura, è necessario:
  - porre il registro in _modalità manutenzione_, dalla pagina **SISTEMA > MANUTENZIONE**
    (si consiglia di impostare almeno un'ora intera di manutenzione);
  - _disconnettere gli altri utenti_ eventualmente collegati, dalla pagina **SISTEMA > MANUTENZIONE > LOGOUT UTENTI**

Per una questione tecnica, non sempre la procedura di _logout_ degli utenti riesce a disconnettere tutti quanti.
Pertanto si consiglia di ripeterla una seconda volta dopo una decina di secondi.

A questo punto si può iniziare la procedura, dalla pagina **SISTEMA > NUOVO A.S.**:
cliccando sul pulsante **INIZIA**, saranno rimossi tutti i documenti generati nel corso del precedente
anno e non più necessari.


## Completare la procedura

Nei passi successivi, la procedura eseguirà le seguenti operazioni:
  - svuotamento delle tabelle dai dati del precedente anno scolastico;
  - recupero delle circolari del precedente anno scolastico;
  - rimozione degli utenti che risultano disabilitati;
  - recupero degli esiti scolastici del precedente anno scolastico;
  - passaggio di classe degli alunni promossi;
  - rimozione degli utenti di alunni e genitori in uscita dalla scuola (alunni ammessi in quinta);
  - impostazione del nuovo anno scolastico nell'apposito parametro della configurazione di sistema;
  - svuotamento della cache di sistema.

Si tenga presente che, nel passaggio di classe, l'alunno viene portato all'anno successivo della medesima sezione.
Nel caso la classe di destinazione non esista, l'alunno non avrà una classe assegnata.

Al termine delle operazioni, è opportuno completare la configurazione dei parametri di sistema del nuovo
anno scolastico. Dalla pagina **SISTEMA > PARAMETRI** aggiornare i parametri:
  - **anno_inizio**, data dell'inizio dell'anno scolastico, nel formato "AAAA-MM-GG";
  - **anno_fine**, data della fine dell'anno scolastico, nel formato "AAAA-MM-GG";
  - **periodo1_fine**, data del giorno finale del primo periodo, nel formato "AAAA-MM-GG";
  - **periodo2_fine**, data del giorno finale sel secondo periodo (se usato) o la data della
    fine dell'anno scolastico, nel formato "AAAA-MM-GG".
