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
servizio di _hosting_.

E' possibile usare questa installazione per provare il registro elettronico sul proprio computer,
ma si dovrà installare anche il web server _Apache_ e il database server _MySql_.
Si consiglia pertanto di utilizzare, in alternativa, l'[installazione tramite Docker](/install-docker.md).

Si tenga presente che questa modalità non permette l'installazione di applicazioni esterne, necessarie per alcune
funzionalità non essenziali del registro elettronico:
**non è pertanto operativa la conversione automatica in PDF dei documenti**.


## Requisiti di sistema

Per consentire l'utilizzo corretto dell'applicazione, il servizio di _hosting_ usato dovrà
rispettare i seguenti requisiti fondamentali:
  - web server **Apache 2.x** o superiore;
  - database server **MySQL 5.5** o superiore, oppure  **MariaDB 10.0** o superiore;
  - **PHP 7.4** o superiore.

Durante la procedura di installazione saranno verificati ulteriori requisiti di sistema,
evidenziandone le criticità.


## Scaricare l'archivio ZIP

Si può scaricare l'archivio ZIP dell'ultima versione stabile dell'applicazione (**consigliato**),
oppure quello contenente anche le ultime modifiche ancora in fase di revisione:

  - [Scarica la versione {{ site.data.version.tag }}](https://github.com/trinko/giuaschool/releases/latest/download/giuaschool-release-latest.zip)
    - [Visualizza i dettagli](/latest-release.md)

  - [Scarica l'ultima modifica](https://github.com/trinko/giuaschool/raw/builds/builds/giuaschool-build-latest.zip)
    - [Visualizza i dettagli](/latest-build.md)


## Copiare il codice nella cartella di destinazione

L'archivio ZIP va decompresso nella cartella principale che il servizio di _hosting_ mette a disposizione.

Si faccia attenzione che solo la cartella **public/** deve essere esposta pubblicamente sul web,
mentre tutto il resto deve rimanere inaccessibile.

Per far questo, alcuni servizi di _hosting_ permettono di scegliere la cartella da pubblicare
(spesso indicata come _domain_root_): in tal caso, impostare il percorso
della cartella **public/** caricata in precedenza.

Altri servizi di _hosting_, invece, hanno una cartella predefinita da usare per la pubblicazione
(spesso indicata come _public_html_): in questo caso, sarà necessario copiare tutto il contenuto
della cartella **public/** all'interno di quella di pubblicazione.

A questo punto, la pagina principale del registro elettronico dovrebbe essere visibile andando all'indirizzo:
  - **http://nome_sito** o **https://nome_sito**


## Eseguire la procedura di installazione

Per prima cosa, rinominare il file **.env-dist** in **.env**.
Quindi inserire la password di installazione: questa verrà
richiesta dalla procedura per evitare che possa essere eseguita da altre persone.

Il file **.env** dovrà pertanto contenere la seguente riga con la nuova password:
```
INSTALLATION_PSW='password_non_banale'
```

Bisogna ora eseguire la procedura di installazione, seguendo le istruzioni riportate a video.
Per eseguire la procedura di installazione andare alla pagina seguente:
  - **http://nome_sito/install/index.php** o **https://nome_sito/install/index.php**


## Installazione su server di produzione

Nel momento in cui si decide di usare il registro elettronico per l'uso scolastico quotidiano,
sarà opportuno fare ulteriori controlli di sicurezza.
In particolare, si controlli che i file al di fuori della cartella **public/** siano inaccessibili.

_E' fondamentale che il file **.env** non possa mai essere visualizzato dal web._

Per controllarlo, andare all'indirizzo seguente e verificare che sia mostrato un messaggio di errore:
  - **http://nome_sito/.env** o **https://nome_sito/.env**

**ATTENZIONE**:
_se si dovessero esporre pubblicamente sul web i file al di fuori della cartella **public/**,
ci saranno gravi conseguenze dal punto di vista della sicurezza._
