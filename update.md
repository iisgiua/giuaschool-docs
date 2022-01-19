---
layout: default
title: Aggiornamento
nav_order: 4
---

# Aggiornamento dell'applicazione
{: .no_toc .text-center .fw-400 .pb-5}

<details markdown="block">
  <summary>Indice dei contenuti</summary>
  {: .text-delta .text-center}
1. TOC
{:toc}
</details>
{: .my-5 .px-4 style="background-color:#efefef;border:1px solid #cccccc"}


## Scaricare l'archivio ZIP

Come prima cosa bisogna scaricare l'archivio ZIP
della nuova versione dell'applicazione, oppure quello contenente anche le ultime modifiche
ancora in fase di revisione:

  - [Scarica la versione {{ site.data.version.tag }}](https://github.com/trinko/giuaschool/releases/latest/download/giuaschool-release-latest.zip)
    - [Visualizza i dettagli](/latest-release.md)

  - [Scarica l'ultima modifica](https://github.com/trinko/giuaschool/raw/builds/builds/giuaschool-build-latest.zip)
    - [Visualizza i dettagli](/latest-build.md)


## Copiare il codice nella cartella di destinazione

L'archivio ZIP va decompresso nella cartella principale che il servizio di _hosting_ mette a disposizione.

Naturalmente, si faccia attenzione a non sovrascrivere eventuali file che sono stati personalizzati in precedenza
(ad esempio i template).

Si suggerisce, per evitare problemi, di creare sempre una copia dei file personalizzati
utilizzando un suffisso del tipo **.modificato**: ad esempio, se si personalizza il template della
pagina di accesso al registro, chiamato **form.html.twig**, se ne può creare una copia
con il nome **form.html.twig.modificato**. In questo modo si evita il rischio di perdere
le proprie personalizzazioni durante gli aggiornamenti, andando poi a decidere
quali modifiche riportare nella nuova versione dei file.


## Eseguire la procedura di aggiornamento

Bisogna ora eseguire la procedura di aggiornamento, seguendo le istruzioni riportate a video.

Per eseguire la procedura di aggiornamento andare alla pagina seguente:
  - **http://nome_sito/install/index.php** o **https://nome_sito/install/index.php**

Al termine della procedura, il file PHP viene rinominato con suffisso **.txt**, in modo
da impedirne una nuova esecuzione.
