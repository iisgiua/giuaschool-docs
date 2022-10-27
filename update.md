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


## Effettuare il backup

Sebbene la procedura di aggiornamento sia sempre controllata con attenzione, non si può escludere che
un problema non previsto abbia come conseguenza la perdita di dati.
Per evitare ogni possibile problema, è sempre opportuno effettuare un backup dei file e del database prima
di eseguire l'aggiornamento, in modo che in caso di problemi si possa ripristinare la situazione iniziale.

Per eseguire il backup dei file si consiglia un software come **Filezilla**,
che si userà per scaricare sul proprio computer una copia di sicurezza dei file presenti nel server di _hosting_.

Per eseguire il backup del database, si può utilizzare il software **phpMyAdmin**, che solitamente è reso disponibile
dal proprio servizio di _hosting_. Con questa applicazione, si può esportare l'intero database in un file, che
verrà scaricato sul proprio computer. In caso di necessità, la stessa applicazione permette di importare
nel database il file creato in precedenza, ripristinando tutti i dati presenti.


## Nuova procedura di aggiornamento

Per avviare la nuova procedura di aggiornamento, come utente amministratore, andare alla
pagina **SISTEMA > AGGIORNAMENTO** e seguire le indicazioni.

Per utilizzare questa procedura è indispensabile aver già aggiornato il sistema almeno alla
versione **1.5.0**.

A seconda delle impostazioni del servizio di hosting, la procedura potrebbe non funzionare
correttamente. In tal caso, utilizzare la vecchia procedura.

In particolare, i servizi di _hosting_ spesso bloccano, per questioni di sicurezza, le
funzioni necessarie per scaricare i file direttamente sul server (_fsockopen_ o _cURL_):
in tal caso, controllare la documentazione del prorio _hosting_ per cnonoscere le modalità
previste per lo sblocco.

A titolo di esempio, si riporta la procedura di sblocco per _Altervista_:
1. eseguire il login per entrare nel pannello di amministrazione del proprio sito;
2. andare alla pagina **RISORSE**;
3. nella scheda **PHP**, cliccare su **Modifica Impostazioni PHP**;
4. scorrere la pagina sino alla sezione **Connessioni Server to Server**;
5. abilitare il **Collegamento esterno senza restrizioni** (sarà necessario autenticare il proprio
    numero di telefono).


## Vecchia procedura di aggiornamento

### Scaricare l'archivio ZIP

Come prima cosa bisogna scaricare l'archivio ZIP della nuova versione dell'applicazione.
- [Scarica la versione {{ site.data.version.tag }}](/latest-release.md)

Se si sta già utilizzando la versione {{ site.data.version.tag }}, si può anche scaricare l'ultimo aggiornamento,
che contiene solo i file modificati dal rilascio dell'ultima versione.
- [Scarica l'ultimo aggiornamento](latest-build.md)


### Copiare il codice nella cartella di destinazione

L'archivio ZIP va decompresso nella cartella principale che il servizio di _hosting_ mette a disposizione.

Naturalmente, si faccia attenzione a non sovrascrivere eventuali file che sono stati personalizzati in precedenza
(ad esempio i template).

Si suggerisce, per evitare problemi, di creare sempre una copia dei file personalizzati
utilizzando un suffisso del tipo **.modificato**: ad esempio, se si personalizza il template della
pagina di accesso al registro, chiamato **form.html.twig**, se ne può creare una copia
con il nome **form.html.twig.modificato**. In questo modo si evita il rischio di perdere
le proprie personalizzazioni durante gli aggiornamenti, andando poi a decidere
quali modifiche riportare nella nuova versione dei file.


### Eseguire la procedura di aggiornamento

Bisogna ora eseguire la procedura di aggiornamento, seguendo le istruzioni riportate a video.

Per eseguire la procedura di aggiornamento andare alla pagina seguente:
  - **https://nome_sito/install/index.php**

Al termine della procedura, il file PHP viene rinominato con suffisso **.txt**, in modo
da impedirne una nuova esecuzione.
