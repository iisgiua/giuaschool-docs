---
layout: default
title: Gestione notifiche
parent: Procedure
nav_order: 6
---

# Gestione delle notifiche
{: .no_toc .text-center .fw-400 .pb-5}

<details markdown="block">
  <summary>Indice dei contenuti</summary>
  {: .text-delta .text-center}
1. TOC
{:toc}
</details>
{: .my-5 .px-4 style="background-color:#efefef;border:1px solid #cccccc"}


## Uso delle notifiche nel registro elettronico

Il registro elettronico permette all'utente di configurare quale mezzo utilizzare per l'invio delle
notifiche e quali eventi notificare.
L'utente può impostare le notifiche dalle pagine del profilo: cliccare sul _nome utente_, sempre
visibile in alto nella pagina, selezionare poi la voce **NOTIFICHE**.

Per prima cosa si può scegliere il canale, ovvero il mezzo utilizzato per l'invio delle notifiche.
La scelta è tra le seguenti opzioni:
- **Email**: tutte le notifiche saranno inviate tramite posta elettronica all'indirizzo email dell'utente.
- **Telegram**: se si utilizza _Telegram_ sul proprio smartphone, si può impostare questa app per
ricevere tutte le notifiche; questa opzione sarà disabilitata se non è stato ancora configurato il
canale _Telegram_.

Si possono inoltre scegliere quali eventi saranno notificati:
- **Lista nuove circolari**: viene creata una lista giornaliera che riporta le nuove circolari;
sarà inviata al massimo una notifica al giorno.
- **Nuovo avviso**: viene inviata una notifica per ogni nuovo avviso.
- **Nuova verifica**: viene inviata una notifica per ogni nuova verifica (solo per utenti genitori e alunni).
- **Nuovo compito**: viene inviata una notifica per ogni nuovo compito per casa (solo per utenti genitori e alunni).

Se l'utente sceglie di utilizzare _Telegram_, sarà necessario creare la chat
su cui ricevere le notifiche: **la procedura deve essere eseguita direttamente sullo smartphone
dove è installata l'app _Telegram_**.
Cliccando su **CONTINUA** nella pagina informativa mostrata subito dopo l'inserimento delle impostazioni,
si potrà vedere la pagina di presentazione Telegram: cliccare sul pulsante di invio messaggio
(**SEND MESSAGE**) per aprire la nuova chat.
A questo punto sarà sufficiente cliccare sul pulsante **AVVIO** (o **START**) presente nella chat (in basso).
Se la configurazione è stata completata con successo, l'utente riceverà un messaggio di benvenuto.


## Configurazione del canale Telegram

Per utilizzare Telegram per l'invio delle notifiche è necessario creare un _bot_e memorizzare il
suo _nome_ e il suo _token_. La procedura è molto semplice, si può ad esempio seguire la seguente
guida che spiega i passi necessari per la creazione del _bot_ e come ricavare il _token_:
  - [Creare il bot](https://www.html.it/pag/394635/creare-telegram-bot/)

A questo punto, come utente amministratore, andare alla pagina **SISTEMA > Configura Telegram**.
In questa pagina si dovrà inserire il _nome_ e il _token_ del _bot_ che si è creato.

Cliccando su **CONFERMA**, il registro provvede a registrare il proprio servizio su Telegram (_webhook_),
completando la configurazione. Da questo momento sarà utilizzabile il canale Telegram nelle scelte di
configurazione delle notifiche.


## Come effettuare l'invio delle notifiche

L'invio delle notifiche viene effettuato tramite un apposito comando, eseguito
ciclicamente con un intervallo di tempo prefissato.
A seconda del servizio di _hosting_, si può utilizzare il comando _cron_ o un servizio
esterno.

In ogni caso, si tenga presente che per le circolari viene effettuata una notifica al giorno,
subito dopo l'ora impostata nel parametro **notifica_circolari**.
Tutti gli altri eventi, invece, vengono notificati con mezzora di ritardo, per evitare
che eventuali correzioni inserite dopo pochi minuti generino un secondo evento.


### Utilizzo di cron

Se il vostro _hosting_ consente l'accesso completo ai comandi di sistema del server, si può
utilizzare _cron_ per impostare l'esecuzione del comando ad intervalli regolari.

Si consiglia di configurare la ripetizione ogni ora del comando seguente (la directory
di esecuzione sarà quella principale del registro elettronico):
```
php bin/console messenger:consume --time-limit 1800 notifica avviso evento circolare
```

In questo caso il comando sarà eseguito ogni ora e viene imposto un limite massimo di tempo
di mezzora (1800 secondi). Il limite di tempo è necessario per evitare che un'esecuzione
duri troppo a lungo, continuando anche quando inizia quella del ciclo successivo.


### Utilizzo di un servizio esterno

Non potendo usare il comando _cron_, si dovrà utilizzare un servizio esterno che permette
di richiamare ripetutamente, ad intervalli regolari, una apposita pagina del registro elettronico
che esegue l'invio delle notifiche.

Anzi tutto, come utente amministratore, andare alla configurazione dei parametri, alla
pagina **SISTEMA > Parametri**, e inserire il valore di un codice segreto in
**comando_token**. Questo impedirà che la pagina di esecuzione delle notifiche possa essere
richiamata da una persona non autorizzata.

La pagina che dovrà essere richiamata è la seguente:
  - http://mio_sito/command/notify/token/tempo

Sostituire _token_ con il codice impostato nel parametro _comando_token_ e _tempo_ con
il limite di tempo previsto, in secondi.

Si consiglia di prevedere l'esecuzione ogni 15 minuti, impostando un tempo massimo di 10 minuti
(600 secondi). Se ad esempio il _token_ fosse "prova", l'indirizzo completo della pagina
risulterebbe essere:
  - http://mio_sito/command/notify/prova/600

Come servizio esterno, si consiglia di utilizzare il sito web seguente:
  - [https://cron-job.org/en/](https://cron-job.org/en/)

Questo servizio, completamente gratuito, permette di pianificare l'esecuzione automatica
della procedura. Una volta registrati, si può creare una nuova pianificazione (_crea cron job_).
Sarà necessario inserire:
  - un nome qualsiasi per il servizio;
  - l'indirizzo della pagina da richiamare, come indicato in precedenza;
  - l'intervallo di tempo di esecuzione.

A questo punto si può attivare l'esecuzione pianificata.
