---
layout: default
title: Docker
parent: Installazione
nav_order: 2
---

# Installazione tramite l'uso dei docker
{: .text-center .fw-400}

## INSTALLAZIONE CON I CONTENITORI DOCKER

### 1. Uso dei docker

Per provare *giua@school* si consiglia l'installazione in locale, tramite l'uso di un contenitore *docker*
([cosa sono i docker?](https://it.wikipedia.org/wiki/Docker)).
L'uso dei *docker* semplifica notevolmente la gestione delle dipendenze richieste dai diversi componenti
dell'applicazione, creando un ambiente virtuale in cui eseguire l'installazione completa di tutto
quanto necessario.

Se non è già presente la gestione dei *docker* nel proprio computer, è necessario procedere alla sua installazione:
  - [installazione per Windows](https://docs.docker.com/docker-for-windows/install/)
  - [installazione per MacOs](https://docs.docker.com/docker-for-mac/install/)
  - [installazione per Linux Ubuntu](https://docs.docker.com/engine/install/ubuntu/)
  - [installazione per Linux Debian](https://docs.docker.com/engine/install/debian/)

Esistono in rete diverse guide in italiano che forniscono maggiori dettagli sull'installazion e sull'uso dei *docker*,
come, ad esempio, quella di [HTML.IT](https://www.html.it/guide/docker/).

### 2. Avvio del server

Il comando seguente scarica l'immagine dell'applicazione ed avvia il server in un contenitore *docker*:
```
docker run -d --rm --name gs_test -p 443:443 ghcr.io/trinko/giuaschool:latest
```

L'immagine verrà scaricata dal repository di *GitHub*, ma se si preferisce usare *Docker Hub*, allora
si può modificare il comando nel modo seguente:
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

### 3. Uso dell'applicazione

Una volta avviato il server, usare l'indirizzo seguente nel proprio browser per visualizzare la pagina di accesso:
  - [https://localhost](https://localhost)

Nel caso sia stato modificato il numero di porta, è necessario specificarlo nell'indirizzo.
Ad esempio, se è stata impostata la porta 8443, l'indirizzo da utilizzare sarà:
  - [https://localhost:8443](https://localhost:8443)

Accedere all'applicazione utilizzando le seguenti credenziali per l'utente amministratore:
  - nome utente: **admin**
  - password: **admin**

Se si desidera accedere all'applicazione con un altro utente, è necessario anzi tutto
visualizzare il nome utente del profilo desiderato: la password predefinita sarà identica al nome utente.
Si può, quindi, uscire dall'applicazione (pulsante ESCI in alto a destra) ed effettuare l'accesso con le
credenziali del nuovo utente.

In alternativa, si può utilizzare la funzione Alias (menu SISTEMA -> ALIAS), che
permette all'amministratore di impersonare un altro utente, senza necessità di inserire password.

### 4. Chiusura del server

Per chiudere il server e liberare le risorse occupate, eseguire i comandi seguenti:
```
docker container stop gs_test
```
