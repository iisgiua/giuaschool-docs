---
layout: default
title: Archivio zip
parent: Installazione
nav_order: 1
---

# Installazione dall'archivio compresso con ZIP
{: .text-center .fw-400}

ewtt


## INSTALLAZIONE SEMPLIFICATA

## REQUISITI DI SISTEMA

I requisiti minimi per l'installazione sono:
  - web server **Apache 2.x** o superiore;
  - database server **MySQL 5.5** o superiore, o versioni equivalenti di **MariaDB**;
  - **PHP 7.4**;
  - framework **Symfony 4.4**.

Ci sono ulteriori requisiti minori che sono richiesti dal framework *Symfony*.




### 1. Cosa contiene una release
Nel file compresso della versione dell'applicazione sono presenti tutti i file necessari.
Questa versione non permette l'installazione di applicazioni esterne, necessarie per alcune particolari funzionalità del registro elettronico:
non è pertanto operativa la conversione automatica in PDF dei documenti caricati.

### 1. Scaricare il codice dell'applicazione
Scaricare il codice dell'applicazione e decomprimere la cartella di installazione.
Il codice dell'ultima versione è sempre disponibile nella pagina principale del progetto:

[<img src="https://img.shields.io/badge/DOWNLOAD-release-blue?style=for-the-badge">](https://github.com/trinko/giuaschool/releases/latest/download/giuaschool-release-latest.zip)

### 2. Copiare il codice nella cartella del web server
I file andranno copiati nella cartella di destinazione del server web.

**ATTENZIONE**: il web server deve essere configurato in modo che solo la cartella **public** sia accessibile agli utenti del sito web.
Infatti l'unico contenuto che deve essere esposto sul sito internet è quello all'interno della cartella **public**, mentre il resto del codice deve rimanere inaccessibile.

**Se si dovesse esporre pubblicamente su internet l'intera cartella di installazione, ci sarebbero gravi problemi di sicurezza.**

### 3. Eseguire la procedura di installazione
A questo punto bisogna eseguire la procedura di installazione e seguire le istruzioni riportate a video.
La procedura permette anche di eseguire un aggiornamento di versione.

Per eseguire la procedura di installazione andare alla pagina seguente:
**https://nome_sito/install/index.php**
