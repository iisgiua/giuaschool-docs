---
layout: default
title: Gruppi classe
parent: Procedure
nav_order: 7
---

# Uso dei gruppi classe
{: .no_toc .text-center .fw-400 .pb-5}

<details markdown="block">
  <summary>Indice dei contenuti</summary>
  {: .text-delta .text-center}
1. TOC
{:toc}
</details>
{: .my-5 .px-4 style="background-color:#efefef;border:1px solid #cccccc"}


## Le classi articolate

Una classe articolata prevede che gli alunni siano suddivisi in più gruppi, in
modo che ogni studente appartenga solo a uno dei gruppi configurati.
Tipicamente i gruppi sono creati per consentire indirizzi di studio differenti all'interno della stessa classe.

Dal punto di vista della gestione degli scrutini e della maggior parte delle operazioni sul registro, la classe articolata è gestita come se esistessero solo le classi corrispondenti ai gruppi definiti.

Per quanto riguarda le cattedre dei docenti, ne esistono di due tipi: quelle relative alle materie comuni a tutti gli studenti (es. Italiano, Storia...) e quelle specifiche per i gruppi definiti.
Per quanto riguarda i docenti delle materie comuni, la gestione del registro non cambia rispetto al solito.

Invece, nelle ore di lezione relative alle materie dei gruppi, avremo più docenti che firmano separatamente il registro, ognuno in una sezione relativa al proprio gruppo.
Non solo, questi docenti gestiranno anche tutte le operazioni sul registro (assenze, voti, ecc.)
solo relativamente agli alunni del proprio gruppo.

Per definire una classe articolata, come utente amministratore, si dovrà andare alla pagina
**Scuola > Classi** e definire anzi tutto la classe, come normalmente si fa, lasciando in bianco il campo del _gruppo classe_.
Successivamente si andranno a creare altre due classi con il medessimo anno e la stessa sezione, ma indicando nomi differenti per i gruppi.

Ad esempio, si vuole creare la classe articolata **3C** suddivisa in due gruppi: il gruppo **CHI** per l'indirizzo _Chimico_ e il gruppo **INF** per l'indirizzo _Informatico_.

Si andrà quindi a creare la classe 3C, lasciando in bianco il campo del _gruppo classe_.
Succcessivamente si andrà a creare un'altra classe 3C a indirizzo chimico, indicando come gruppo classe **CHI**.
Infine, si andrà a creare un'ulteriore classe 3C a indirizzo informatico, indicando come gruppo classe **INF**.

Una volta definiti i gruppi si possono impostare le cattedre sulle materie comuni, scegliendo come classe quella senza gruppi. Per le altre cattedre si sceglieranno i gruppi classe definiti.

Nel nostro esempio, si potrà impostare la cattedra di Italiano sulla classe **3C**, mentre quella di Informatica sul gruppo classe **3C-INF** e quella di Chimica sul sul gruppo classe **3C-CHI**.


## I gruppi di religione

Quando si svolge una lezione per la materia Religione, si creano automaticamente tre gruppi separati di studenti:
- **Gruppo Religione**: comprende tutti gli studenti che si avvalgono della materia;
- **Gruppo Mat. Alt.**: comprende tutti gli studenti che si avvalgono della Materia Alternativa alla Religione;
- **Gruppo N.A.**: comprende tutti gli studenti che non si avvalgono della materia.

Sono previste firme e gestioni separate per ciascuno dei gruppi.
Il docente di Religione o della Materia Alternativa gestirà gli alunni del proprio gruppo.

Per gli alunni che non si avvalgono si possono verificare diverse situazioni, ma in ogni caso questi non svolgono una lezione curricolare: pertanto un docente che eventualmente si occupi di loro
potrà firmare solo come **SUPPLENZA** sul _gruppo N.A._

Nel caso di un docente di sostegno che segue un alunno che non si avvale, tale docente potrà firmare solo come **SUPPLENZA** sul _gruppo N.A._
