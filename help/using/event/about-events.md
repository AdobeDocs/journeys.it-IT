---
product: adobe campaign
solution: Journey Orchestration
title: Informazioni sugli eventi
description: Informazioni sugli eventi
feature: Journeys
role: Business Practitioner
level: Intermediate
translation-type: tm+mt
source-git-commit: f73e357d8947997f7f5872efa6a5ef4f51bc63a9
workflow-type: tm+mt
source-wordcount: '357'
ht-degree: 49%

---


# Principio generale {#concept_gfj_fqt_52b}

>[!CONTEXTUALHELP]
>id="jo_events"
>title="Informazioni sugli eventi"
>abstract="Un evento è collegato a una persona Si riferisce al comportamento di una persona o qualcosa che si verifica in relazione a una persona. Nell’ambito dei percorsi, [!DNL Journey Orchestration] farà da listener a questi dati, in modo da orchestrare le migliori azioni da eseguire successivamente."

Un evento è collegato a una persona e si riferisce al suo comportamento: ad esempio, se ha acquistato un prodotto, se ha visitato un negozio, se è uscita da un sito web, e così via. Oppure, indica qualcosa che si verifica in relazione a una persona, che può ad esempio aver raggiunto 10.000 punti fedeltà. Nell’ambito dei percorsi, [!DNL Journey Orchestration] farà da listener a questi dati, in modo da orchestrare le migliori azioni da eseguire successivamente.

Tale configurazione è **obbligatoria**[!DNL Journey Orchestration], in quanto è progettata per fare da listener agli eventi ed è sempre eseguita da un **utente tecnico**.

La configurazione dell’evento consente di definire le informazioni che [!DNL Journey Orchestration] riceverà sotto forma di eventi. All’interno dei vari di un percorso puoi utilizzare numerosi eventi, mentre più percorsi possono sfruttare il medesimo evento.

Se modifichi un evento utilizzato in una bozza di percorso o in un percorso live, puoi cambiare solo il nome e la descrizione oppure aggiungere i campi payload. Al fine di evitare l’interruzione dei percorsi, limitiamo rigorosamente la modifica delle bozze di percorso o dei percorsi live.

Puoi definire due tipi di eventi:

* **Eventi** basati sulle regole: questo tipo di evento non genera un eventID. Utilizzando l’editor di espressioni semplici, puoi semplicemente definire una regola che verrà utilizzata dal sistema per identificare gli eventi rilevanti che attiveranno i tuoi percorsi. Questa regola può essere basata su qualsiasi campo disponibile nel payload dell’evento, ad esempio la posizione del profilo o il numero di elementi aggiunti al carrello del profilo.

   >[!CAUTION]
   >
   >Per gli eventi basati su regole viene definita una regola di limitazione. Limita il numero di eventi qualificati che un percorso può elaborare a 5000 al secondo per una determinata organizzazione (ORG). Corrisponde agli SLA di Journey Orchestration. Vedere questa [pagina](https://helpx.adobe.com/legal/product-descriptions/journey-orchestration.html).

* **Sviluppatori** di sistema: questi eventi richiedono un eventID. Questo campo eventID viene generato automaticamente durante la creazione dell’evento. Il sistema che preme l’evento non deve generare un ID, deve passare quello disponibile nell’anteprima del payload.

Per informazioni su come creare un evento, consulta questa [pagina](../event/about-creating.md).

