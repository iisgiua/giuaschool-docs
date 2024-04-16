---
layout: default
title: Archivio ZIP
parent: Installazione
nav_order: 1
---

# Installazione tramite archivio ZIP
{: .no_toc .text-center .fw-400 .pb-5}

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

Si dovrà scaricare l'archivio ZIP dell'ultima versione stabile dell'applicazione:

  - [Scarica la versione {{ site.data.version.tag }}](/latest-release.md)


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
  - **https://nome_sito**


## Eseguire la procedura di installazione

Per eseguire la procedura di installazione iniziale, andare alla pagina seguente e seguire
le istruzioni:
  - **https://nome_sito/install/app.php**

Al termine della procedura, il file PHP della procedura viene rimosso, per ragioni di sicurezza.


## Esempio di installazione su Altervista

La procedura per l'installazione iniziale usando il servizio di hosting _Altervista_ viene descritta di seguito: si raccomanda di eseguire con attenzione ogni passaggio.

1.  Per prima cosa, se non l'hai già fatto, registrati su *Altervista* e scegli il nome del tuo dominio.
    In fase di registrazione, assicurati di scegliere il servizio **Hosting con file manager**.
    Se non sai come fare, segui [questo tutorial](https://www.smartworld.it/guide/come-creare-sito-gratis-altervista.html).

1.  Vai al pannello di controllo di _Altervista_ e clicca sul menu **RISORSE**.
    Cerca nella pagina il riquadro **PHP** e clicca sul collegamento **Modifica Impostazioni PHP**.
    A questo punto cerca la configurazione della _versione PHP_ e impostala su **PHP8**; infine clicca sul pulsante **SALVA**.

1.  Scarica il file ZIP dell'[ultima versione](https://iisgiua.github.io/giuaschool-docs/latest-release.html) e decomprimilo sul tuo computer.

1.  Usa un programma FTP come _FileZilla_ ([scaricalo da qui](https://filezilla-project.org/download.php?platform=win64) se non ce l'hai).
    _FileZilla_ ti permette di caricare i file sul tuo spazio Altervista: se non conosci questo programma guarda [questo tutorial](https://www.youtube.com/watch?v=8kOMTK3XOp8).

1.  Connettiti con _FileZilla_ al tuo spazio Altervista, utilizzando le credenziali FTP che ti hanno inviato.
    I file del tuo spazio _Altervista_ appariranno nel riquadro **SITO REMOTO**.
    Imposta nel riquadro **SITO LOCALE** la cartella presente nel tuo computer con i file estratti dallo ZIP di _giua@school_.
    Effettua il trasferimento di tutti i file dal sito LOCALE al sito REMOTO (richiederà un po' di tempo, sono tanti file).
    Alla fine, controlla se ci sono stati errori: in tal caso ricarica solo i file indicati come errati.

1. Quando sei sicuro di aver caricato tutto, esegui la procedura di installazione andando all'indirizzo:
    **http://nome_sito_altervista/public/install/app.php**


## Installazione su server di produzione

Nel momento in cui si decide di usare il registro elettronico per l'uso scolastico quotidiano,
è opportuno rafforzare la sicurezza del sistema utilizzato.

_Per prima cosa, è indispensabile che il registro elettronico utilizzi il protocollo HTTPS._

Inoltre, si controlli che i file al di fuori della cartella **public/** siano inaccessibili.

In particolare, _è fondamentale che il file **.env** non possa mai essere visualizzato dal web_.

Per controllarlo, andare all'indirizzo seguente e verificare che sia mostrato un messaggio di errore:
  - **https://nome_sito/.env**

**ATTENZIONE**:
_se si dovessero esporre pubblicamente sul web i file al di fuori della cartella **public/**,
ci saranno gravi conseguenze dal punto di vista della sicurezza._
