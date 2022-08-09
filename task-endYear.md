---
layout: default
title: Chiusura A.S.
parent: Procedure
nav_order: 1
---

# Chiusura dell'Anno Scolastico
{: .no_toc .text-center .fw-400 .pb-5}

<details markdown="block">
  <summary>Indice dei contenuti</summary>
  {: .text-delta .text-center}
1. TOC
{:toc}
</details>
{: .my-5 .px-4 style="background-color:#efefef;border:1px solid #cccccc"}


## Procedura di fine anno

Alla fine dell'Anno Scolastico e prima di passare a quello successivo, è necessario archiviare
tutti i dati formalmente rilevanti prodotti dal registro elettronico.
L'applicazione prevede la generazione di documenti in formato PDF che dovranno poi essere
scaricati sul proprio computer e archiviati nella modalità più idonea.


## Creare i documenti

I documenti generati dall'applicazione sono i seguenti:
- **Registro del docente**: corrisponde al classico registro personale del docente, con tutte le informazioni
    riguardanti le lezioni (argomenti, assenze, valutazioni, osservazioni, proposte di voto);
- **Registro di sostegno**: corrisponde al registro personale del docente di sostegno, sostanzialmente
    simile al precedente ma con un formato idoneo all'attività del sostegno;
- **Registro di classe**: corrisponde al classico registro di classe, con tutte le informazioni
    riguardanti l'attività svolta in classe (firme delle lezioni, argomenti, assenze, giustificazioni,
    note disciplinari, annotazioni);
- **Documenti dello scrutinio**: sono i documenti fondamentali prodotti per ogni scrutinio (verbale,
    riepilogo dei voti, comunicazione dei debiti e delle carenze);
- **Archivio delle circolari**: archivio completo delle circolari pubblicate con i relativi allegati.

Per generare i documenti, come utente _amministratore_, scegliere dal menu **SISTEMA > ARCHIVIAZIONE**.
Nella pagina della procedura è possibile selezionare quali documenti generare e se crearli singolarmente
(indicando il nome del docente o della classe) o tutti quanti assieme.

### Attenzione
{: .label .label-yellow}
La generazione dei documenti può richiedere parecchio tempo e necessita di molte risorse del server: questo può
comportare che il servizio di _hosting_ blocchi improvvisamente la procedura mostrando un messaggio di
errore, o anche una pagina completamente bianca.
In tal caso, per evitare problemi, si proceda selezionando solo un elemento alla volta.

Nel registro sono presenti anche altri documenti che vengono caricati direttamente dai docenti attraverso le
apposite funzionalità del menu **DOCUMENTI**: piani di lavoro, programmi e relazioni finali, documento del 15 maggio,
documenti (cifrati) degli alunni BES.


## Scaricare i documenti

I documenti sono generati sul server, per cui sarà necessario scaricarli sul proprio computer
con un software come **Filezilla**.

Tutti i documenti si trovano nella cartella: `FILES/archivio`.

In particolare, la cartella è suddivisa nel modo seguente:
- `circolari`: che contiene tutti documenti delle circolari;
- `classi`: che, suddivisa a sua volta tra le classi esistenti, contiene i piani di lavoro, i programmi e
    le relazioni finali, il documento del 15 maggio, i documenti (cifrati) degli alunni BES;
- `registri`: che contiene, in tre cartelle separate, i registri dei docenti, di sostegno e delle classi;
- `scrutini`: che, suddivisa per periodo e classe, contiene i documenti degli scrutini.
