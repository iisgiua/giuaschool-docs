---
layout: default
title: Docker
parent: Installazione
nav_order: 2
---

# Installazione tramite Docker
{: .no_toc .text-center .fw-400 .pb-5}

<details markdown="block">
  <summary>Indice dei contenuti</summary>
  {: .text-delta .text-center}
1. TOC
{:toc}
</details>
{: .my-5 .px-4 style="background-color:#efefef;border:1px solid #cccccc"}


## Perché usare le immagini Docker

L'installazione tramite immagini _Docker_ ([cosa è un'immagine Docker?](https://it.wikipedia.org/wiki/Docker){:target="_blank"})
è consigliata per provare il registro elettronico direttamente sul proprio computer.

L'uso delle immagini _Docker_ semplifica notevolmente la gestione delle dipendenze
richieste dai diversi componenti dell'applicazione, creando un ambiente virtuale,
completo di tutto quanto necessario, in cui eseguire l'applicazione.


## Installazione del gestore Docker

Se non è già presente il gestore _Docker_ nel proprio computer, è necessario procedere alla sua installazione:
  - [installazione per Windows](https://docs.docker.com/docker-for-windows/install/){:target="_blank"}
  - [installazione per MacOs](https://docs.docker.com/docker-for-mac/install/){:target="_blank"}
  - [installazione per Linux Ubuntu](https://docs.docker.com/engine/install/ubuntu/){:target="_blank"}
  - [installazione per Linux Debian](https://docs.docker.com/engine/install/debian/){:target="_blank"}

Esistono in rete diverse guide in italiano che forniscono maggiori dettagli sull'installazione e
sull'uso dei contenitori _Docker_, come, ad esempio, quella di [HTML.IT](https://www.html.it/guide/docker/){:target="_blank"}.


## Avvio del server

Anzi tutto, per evitare di utilizzare un'immagine dell'applicazione scaricata in precedenza e
non aggiornata alle ultime modifiche, si consiglia di cancellarla dalla memoria
con il comando seguente:
```
docker rmi ghcr.io/trinko/giuaschool:latest
```

Per avviare il server nell'ambiente virtuale del _Docker_,
si dovrà utilizzare il comando seguente, che scarica l'immagine dell'applicazione
e manda in esecuzione il contenitore:
```
docker run -d --rm --name gs_test -p 443:443 ghcr.io/trinko/giuaschool:latest
```

Nel caso il comando riporti un errore di rete del tipo
**"listen tcp4 0.0.0.0:443: bind: address already in use"**,
significa che la porta 443 è già utilizzata da un altro servizio del proprio computer.
Si può quindi impostare una porta differente, ad esempio 8443, modificando il comando come indicato di seguito:
```
docker run -d --rm --name gs_test -p 8443:443 ghcr.io/trinko/giuaschool:latest
```


## Uso dell'applicazione

Una volta avviato il server, usare l'indirizzo seguente nel proprio browser per visualizzare la pagina di accesso:
  - **https://localhost**

Nel caso sia stato modificato il numero della porta di comunicazione, è necessario specificarlo
nell'indirizzo.
Ad esempio, se è stata impostata la porta 8443, l'indirizzo da utilizzare sarà:
  - **https://localhost:8443**

A questo punto si può accedere all'applicazione utilizzando le seguenti credenziali per l'utente amministratore:
  - nome utente: **admin**
  - password: **admin**

Le pagine di amministrazione consentono di impostare tutto quanto è necessario per il funzionamento del
registro elettronico.

Una volta caricati i dati, è possibile utilizzare la funzione _Alias_ (menu **SISTEMA > ALIAS**), che
permette all'amministratore di impersonare un altro utente, senza necessità di inserire password.


## Chiusura del server

Al termine dell'utilizzo, per chiudere il server e liberare la memoria utilizzata,
eseguire il comando seguente:
```
docker container stop gs_test
```


## Docker su server di produzione

L'immagine dell'applicazione può anche essere utilizzata su un servizio di _hosting_ basato
sulla piattaforma _Docker_, che permette la gestione di server virtuali in modo semplice ed efficace.

Si tenga presente, però, che l'immagine è progettata per essere utilizzata in un ambiente di prova:
se si desidera utilizzarla in produzione, si dovrà modificare le impostazioni di sistema a riguardo degli
aspetti della sicurezza e delle prestazioni.


## Immagini Docker per lo sviluppo e i test

Su GitHub sono anche presenti le immagini:
  - **giuaschool-dev**, che contiene l'installazione per lo sviluppo dell'applicazione;
  - **giuaschool-test**, che contiene l'installazione per l'esecuzione automatica dei test.

Per utilizzarle, è sufficiente cambiare il nome dell'immagine nei comandi illustrati in precedenza.
