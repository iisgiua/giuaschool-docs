---
layout: default
title: Archivio ZIP
parent: Installazione
nav_order: 1
---

# Installazione tramite archivio ZIP
{: .no_toc .text-center .fw-400}

<details markdown="block">
  <summary>Indice dei contenuti</summary>
  {: .text-delta .text-center}
1. TOC
{:toc}
</details>
{: .my-5 .px-4 style="background-color:#efefef;border:1px solid #cccccc"}


## Perché usare l'archivio ZIP

L'uso dell'archivio _ZIP_ ([che cosa è un archivio ZIP?](https://it.wikipedia.org/wiki/ZIP_(formato_di_file)){:target="_blank"})
permette di semplificare la procedura di installazione, nel caso si utilizzi un apposito
servizio di hosting.

E' anche possibile usare questa installazione per provare il registro elettronico sul proprio computer,
ma si dovrà installare anche il web server _Apache_ e il database server _MySql_.
Si consiglia pertanto di utilizzare, in alternativa, l'[installazione tramite Docker](/install-docker.md).

Si tenga presente che questa modalità non permette l'installazione di applicazioni esterne, necessarie per alcune
funzionalità non essenziali del registro elettronico:
**non è pertanto operativa la conversione automatica in PDF dei documenti**.


## Requisiti di sistema

Per consentire l'utilizzo corretto dell'applicazione, il servizio di hosting usato dovrà
rispettare i seguenti requisiti fondamentali:
  - web server **Apache 2.x** o superiore;
  - database server **MySQL 5.5** o superiore, oppure  **MariaDB 10.0** o superiore;
  - **PHP 7.4** o superiore.

Durante la procedura di installazione saranno verificati ulteriori requisiti di sistema,
evidenziando le criticità.


## Scaricare l'archivio ZIP

Si può scaricare l'archivio ZIP dell'ultima versione stabile dell'applicazione (**consigliato**),
oppure quello contenente anche le ultime modifiche ancora in fase di revisione:

  - [Scarica la versione {{ site.data.version.tag }}](https://github.com/trinko/giuaschool/releases/latest/download/giuaschool-release-latest.zip)
    - [Visualizza i dettagli](/latest-release.md)

  - [Scarica l'ultima modifica](https://github.com/trinko/giuaschool/raw/builds/builds/giuaschool-build-latest.zip)
    - [Visualizza i dettagli](/latest-build.md)







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
