---
product: adobe campaign
solution: Journey Orchestration
title: Informazioni sugli eventi
description: Informazioni sugli eventi
translation-type: tm+mt
source-git-commit: 3dd7cd4dc4e4398b029dd1becd11c8dd7e7c3542
workflow-type: tm+mt
source-wordcount: '0'
ht-degree: 0%

---


# Principio generale {#concept_gfj_fqt_52b}

>[!CONTEXTUALHELP]
>id="jo_events"
>title="Informazioni sugli eventi"
>abstract="Un evento è collegato a una persona e si riferisce al suo comportamento: ad esempio, se ha acquistato un prodotto, se ha visitato un negozio, se è uscita da un sito web, e così via. Oppure, indica qualcosa che si verifica in relazione a una persona, che può ad esempio aver raggiunto 10.000 punti fedeltà. Nell’ambito dei percorsi, [!DNL Journey Orchestration] farà da listener a questi dati, in modo da orchestrare le migliori azioni da eseguire successivamente."

Un evento è collegato a una persona e si riferisce al suo comportamento: ad esempio, se ha acquistato un prodotto, se ha visitato un negozio, se è uscita da un sito web, e così via. Oppure, indica qualcosa che si verifica in relazione a una persona, che può ad esempio aver raggiunto 10.000 punti fedeltà. Nell’ambito dei percorsi, [!DNL Journey Orchestration] farà da listener a questi dati, in modo da orchestrare le migliori azioni da eseguire successivamente.

Tale configurazione è **obbligatoria**[!DNL Journey Orchestration], in quanto è progettata per fare da listener agli eventi ed è sempre eseguita da un **utente tecnico**.

La configurazione dell’evento consente di definire le informazioni che [!DNL Journey Orchestration] riceverà sotto forma di eventi. All’interno dei vari di un percorso puoi utilizzare numerosi eventi, mentre più percorsi possono sfruttare il medesimo evento.

Se modifichi un evento utilizzato in una bozza di percorso o in un percorso live, puoi cambiare solo il nome e la descrizione oppure aggiungere i campi payload. Al fine di evitare l’interruzione dei percorsi, limitiamo rigorosamente la modifica delle bozze di percorso o dei percorsi live.

È possibile definire due tipi di eventi:

* **Eventi** di base delle regole: questo tipo di evento non genera un eventID. Utilizzando l&#39;editor di espressioni semplici, è sufficiente definire una regola che verrà utilizzata dal sistema per identificare gli eventi rilevanti che attiveranno i viaggi. Questa regola può essere basata su qualsiasi campo disponibile nel payload dell&#39;evento, ad esempio la posizione del profilo o il numero di elementi aggiunti al carrello del profilo.

   >[!CAUTION]
   >
   >Per gli eventi basati su regole viene definita una regola di capping. Limita il numero di eventi qualificati che un viaggio può elaborare a 5000 al secondo per una determinata organizzazione (ORG). Corrisponde agli SLA Journey Orchestration. Vedere questa [pagina](https://helpx.adobe.com/legal/product-descriptions/journey-orchestration.html).

* **Sviluppatori** di sistemi: questi eventi richiedono un eventID. Questo campo eventID viene generato automaticamente al momento della creazione dell’evento. Il sistema che preme l’evento non deve generare un ID, ma deve passare quello disponibile nell’anteprima del payload.

Per informazioni su come creare un evento, fare riferimento a questa [pagina](../event/about-creating.md).

