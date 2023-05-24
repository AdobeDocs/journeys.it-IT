---
title: Aggiornamento a Adobe Journey Optimizer
description: Scopri come effettuare l’aggiornamento a Adobe Journey Optimizer
hide: true
hidefromtoc: true
exl-id: 887fd3bb-bcd3-4a6d-9817-43049c51ecba
source-git-commit: 3e9ff02cecfe85ea38cce4b0d241156f6209202f
workflow-type: tm+mt
source-wordcount: '753'
ht-degree: 2%

---

# Aggiornamento dell&#39;ambiente di Journey Orchestration a Adobe Journey Optimizer{#ugrade-ajo}

## Cos’è Adobe Journey Optimizer?

Adobe Journey Optimizer è un’applicazione agile e scalabile creata in modalità nativa su Adobe Experience Platform per orchestrare e distribuire percorsi di clienti personalizzati, connessi e tempestivi su qualsiasi app, dispositivo, schermo o canale&#x200B;

## Cos’è Journey Orchestration?

Journey Orchestration è un servizio basato su Adobe Experience Platform che consente di personalizzare singoli percorsi per ciascun cliente in base al comportamento e alle preferenze precedenti. Journey Orchestration è l&#39;applicazione precursore di Journey Optimizer.

## Perché dovrei passare a Adobe Journey Optimizer?

**Accesso a un’interfaccia semplificata** con funzionalità di Experience Platform che consentono di accedere rapidamente a percorsi, set di dati, profili, avvisi e altro ancora. Non è più necessario fare avanti e indietro tra Adobe Experience Platform e il Journey Orchestration per accedere a schemi o set di dati, tutto è direttamente disponibile da Adobe Journey Optimizer. Per ulteriori informazioni, consulta questa [pagina](https://experienceleague.adobe.com/docs/journey-optimizer/using/get-started/user-interface.html).

<table>
<tr>
<th>Prima</th>
<th>Dopo</th>
</tr>
<tr>
<td><img src="../assets/migration-ajo-1.png"><p>Accedi a Percorsi, Segmenti e sezione Amministratore (origini dati, eventi e azioni) in Journey Orchestration. Segmenti e set di dati sono accessibili in Adobe Experience Platform. </p></td>
<td><img src="../assets/migration-ajo-2.png"><p>Accesso a Percorsi, segmenti, amministratori, segmenti e set di dati <strong>tutto in Adobe Journey Optimizer</strong>. <strong>Funzionalità Adobe Experience Platform aggiuntive</strong> sono accessibili anche qui.</p></td>
</tr>
</table>

**Nuova interfaccia di reporting** e accesso a nuove funzioni di reporting:

<table>
<tr>
<th>Prima</th>
<th>Dopo</th>
</tr>
<tr>
<td><img src="../assets/migration-ajo-5.png"></td>
<td><img src="../assets/migration-ajo-6.png"><p><strong>Vista globale</strong> consente di misurare l’impatto di percorsi e consegne in un periodo di tempo selezionato. Per ulteriori metriche in tempo reale, puoi accedere alla sezione <strong>Vista live</strong>. Per ogni canale di consegna utilizzato nei percorsi (e-mail, SMS, push), una <strong>sezione dedicata</strong> è disponibile nel rapporto per visualizzare le metriche. Ciò si applica solo se si utilizza <strong>Funzionalità di messaggistica Adobe Journey Optimizer</strong>. Per ulteriori informazioni, rivolgiti al team del tuo account.</p></td>
</tr>
</table>

Qualsiasi evoluzione volta a migliorare l’esperienza di reporting o ad arricchirla in seguito alle nuove versioni di funzioni è disponibile solo nella nuova interfaccia di reporting. Inizia a utilizzarlo per un’esperienza Adobe Journey Optimizer più completa.

Ottieni il vantaggio di altri **Funzioni di Adobe Journey Optimizer** e ne verranno presentati di nuovi, come Field Level Access Control (Controllo dell’accesso a livello di campo) e Object Level Access Control (Controllo dell’accesso a livello di oggetto). Per ulteriori informazioni, rivolgiti al team del tuo account.

## Come aggiornare l&#39;ambiente di Journey Orchestration?

1. Rivolgiti al team del tuo account per aggiornare l’accordo con Adobe.

1. Attendi che il nostro team di progettazione completi la modifica.

1. Aggiorna le autorizzazioni utilizzando i profili di prodotto di Journey Optimizer. Fai riferimento a questo [pagina](https://experienceleague.adobe.com/docs/journey-optimizer/using/administration/ootb-product-profiles.html?lang=it).

1. Ora puoi accedere a Adobe Journey Optimizer.

## Domande frequenti

### Devo pianificare qualcosa per passare dal Journey Orchestration a Adobe Journey Optimizer?

No, non è necessaria alcuna migrazione, nessun lavoro da parte dell&#39;utente, nessun downtime e nessun investimento aggiuntivo. È sufficiente aggiornare l&#39;accordo con Adobe per eseguire le altre operazioni. Contatta il rappresentante del tuo account per istruzioni su come avviare questo processo.

### Perderò qualcosa dopo il cambiamento?

No, mantieni tutti gli oggetti Journey Orchestration e Adobe Experience Platform esistenti: schemi, set di dati, percorsi, eventi, origini dati, azioni. Non si perderà nulla, tutti i percorsi in diretta continueranno a funzionare senza interruzioni.

<table>
<tr>
<th>Prima</th>
<th>Dopo</th>
</tr>
<tr>
<td><img src="../assets/migration-ajo-7.png"></td>
<td><img src="../assets/migration-ajo-8.png"></td>
</tr>
</table>

### Vedo ancora il Journey Orchestration nel commutatore dell&#39;applicazione, è normale?

![](../assets/migration-ajo-9.png)

Sì, è normale. È possibile che l&#39;elemento Journey Orchestration venga visualizzato ancora per alcuni giorni dopo l&#39;aggiornamento. Per favore, usi quello di Journey Optimizer.

### Cosa succede se uso il Journey Orchestration con Adobe Campaign Standard oggi?

Passando a Adobe Journey Optimizer, potrai comunque utilizzare l’integrazione tra Percorsi e Adobe Campaign Standard progettando il percorso di clienti in Adobe Journey Optimizer e consentendo ad Adobe Campaign Standard di inviare la consegna.

Tuttavia, a causa del funzionamento dello stack di reporting di Adobe Journey Optimizer, il reporting non combinerà dati di Percorso e Campaign Standard. Le informazioni di percorso saranno disponibili nei rapporti di Adobe Journey Optimizer e nelle informazioni di consegna in Adobe Campaign Standard. È possibile effettuare una configurazione di Experience Platform per riportare i dati di Adobe Campaign Standard in Adobe Experience Platform, rendendoli disponibili per il Customer Journey Analytics ([ulteriori informazioni](https://business.adobe.com/products/experience-platform/customer-journey-analytics.html)) o altri strumenti di reporting di terze parti come Tableau o Power BI.

I rapporti di Adobe Journey Optimizer funzionano al meglio quando si utilizzano le funzionalità di messaggistica predefinite di Adobe Journey Optimizer (disponibili nelle offerte Adobe Journey Optimizer dedicate). Per ulteriori informazioni su come creare i messaggi nell’area di lavoro del percorso, consulta questa [pagina](https://experienceleague.adobe.com/docs/journey-optimizer/using/messages/messages-in-journeys.html).

Per ulteriori informazioni, rivolgiti al team del tuo account.
