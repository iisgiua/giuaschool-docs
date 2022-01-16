---
layout: default
title: Il progetto
nav_order: 2
---

# Il progetto
{: .text-center .fw-400}

Il progetto nasce dalla volontà di utilizzare un Registro Elettronico *open source* per le attività scolastiche
dell'**Istituto di Istruzione Superiore "Michele Giua"**.

Il primo candidato è stato l'ottimo [Lampschool](http://www.lampschool.it/),
al quale sono state apportate parecchie modifiche per renderlo idoneo alle esigenze dell'Istituto,
tra cui le principali sono:
  - gestione di due sedi scolastiche, con docenti che possono lavorare anche in entrambe le sedi;
  - orario scolastico differente per sede, con unità orarie anche da 90 minuti, la prima o l'ultima a seconda della sede;
  - orario provvisorio di inizio anno con solo 4 unità orarie da 60 minuti;
  - calcolo delle ore di assenza degli studenti, come pure la relativa visualizzazione sul registro,
    tenendo conto dell'orario in uso (quello provvisorio o quello definitivo) e
    della sede a cui appartiene la classe;
  - gestione dello scrutinio, comprese le problematiche della non ammissione per
    superamento del limite delle assenze o dell'eventuale deroga;
  - gestione dell'importazione e dell'esportazione dei dati, per consentire il dialogo
    con il sistema proprietario utilizzato dalla Segreteria Alunni.

Successivamente, poiché le modifiche stavano diventando sempre più numerose, si
è deciso di creare un nuovo progetto basato su strumenti più idonei per la
gestione di un codice ormai troppo complesso.

Nasce così **giua@school** che, sebbene sia stato riscritto da zero, può essere
considerato una *fork* di [Lampschool](http://www.lampschool.it/), perché
riprende da questo diverse soluzioni algoritmiche e l'importante esperienza
maturata con il suo uso.

Da allora, il software del registro elettronico viene aggiornato di continuo,
seguendo le esigenze dei docenti e dell'organizzazione scolastica, ma cercando, al tempo stesso,
di mantenerlo semplice e intuitivo per l'utente finale.

Il progetto **giua@school** è basato sull'uso di:
  - [Symfony](https://symfony.com/) per la gestione generale del sistema e in particolare della sicurezza;
  - [Doctrine](http://www.doctrine-project.org/) per la gestione del livello di astrazione del database;
  - [Twig](https://twig.symfony.com/) per la gestione dei *template*;
  - [Jquery](https://jquery.com/), [Bootstrap](https://getbootstrap.com/)
    e [Bootstrap Italia](https://italia.github.io/bootstrap-italia/) per l'interfaccia grafica.
