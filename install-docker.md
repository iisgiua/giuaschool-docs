---
layout: default
title: Docker
parent: Installazione
nav_order: 2
---

# Installazione tramite Docker
{: .text-center .fw-400}

L'installazione tramite contenitore *Docker* ([cosa è un contenitore Docker?](https://it.wikipedia.org/wiki/Docker){:target="_blank"})
è consigliata per provare il registro elettronico direttamente sul proprio computer.

L'uso dei contenitori *Docker* semplifica notevolmente la gestione delle dipendenze
richieste dai diversi componenti dell'applicazione, creando un ambiente virtuale,
completo di tutto quanto necessario, in cui eseguire l'applicazione.

Se non è già presente la gestione dei *Docker* nel proprio computer, è necessario procedere alla sua installazione:
  - [installazione per Windows](https://docs.docker.com/docker-for-windows/install/){:target="_blank"}
  - [installazione per MacOs](https://docs.docker.com/docker-for-mac/install/){:target="_blank"}
  - [installazione per Linux Ubuntu](https://docs.docker.com/engine/install/ubuntu/){:target="_blank"}
  - [installazione per Linux Debian](https://docs.docker.com/engine/install/debian/){:target="_blank"}

Esistono in rete diverse guide in italiano che forniscono maggiori dettagli sull'installazione e
sull'uso dei contenitori *Docker*, come, ad esempio, quella di [HTML.IT](https://www.html.it/guide/docker/){:target="_blank"}.


## Avvio del server

Anzi tutto, per evitare di utilizzare un'immagine dell'applicazione scaricata in precedenza e
non aggiornata alle ultime modifiche, si consiglia di cancellarla dalla memoria
con il comando seguente:
```
docker rmi ghcr.io/trinko/giuaschool:latest
```

Per avviare il server nell'ambiente virtuale del *Docker*,
si dovrà utilizzare il comando seguente, che scarica l'immagine dell'applicazione
e manda in esecuzione il contenitore:
```
docker run -d --rm --name gs_test -p 443:443 ghcr.io/trinko/giuaschool:latest
```

L'immagine dell'applicazione verrà scaricata dal repository di *GitHub*, ma se si preferisce
usare *Docker Hub*, si può modificare il comando nel modo seguente:
```
docker run -d --rm --name gs_test -p 443:443 trinkodok/giuaschool:latest
```

Nel caso il comando riporti un errore di rete del tipo
*"listen tcp4 0.0.0.0:443: bind: address already in use"*,
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
  - **https://localhost:8443

A questo punto si può accedere all'applicazione utilizzando le seguenti credenziali per l'utente amministratore:
  - nome utente: **admin**
  - password: **admin**

Le pagine di amministrazione consentono di impostare tutto quanto è necessario per il funzionamento del
registro elettronico.

Una volta caricati i dati, è possibile utilizzare la funzione *Alias* (menu **SISTEMA -> ALIAS**), che
permette all'amministratore di impersonare un altro utente, senza necessità di inserire password.


## Chiusura del server

Al termine dell'utilizzo, per chiudere il server e liberare la memoria utilizzata,
eseguire il comando seguente:
```
docker container stop gs_test
```


## Docker su server di produzione

L'immagine dell'applicazione può anche essere utilizzata su un servizio di *hosting* basato
sulla piattaforma *Docker*, che permette la gestione di server virtuali in modo semplice ed efficace.

Si tenga presente, però, che l'immagine è progettata per essere utilizzata per un ambiente di prova:
se si desidera utilizzarla in produzione, si dovrà modificarne le impostazioni a riguardo degli
aspetti della sicurezza e delle prestazioni.
