---
product: adobe campaign
title: Informazioni sugli eventi
description: Scopri gli eventi
feature: Journeys
role: User
level: Intermediate
exl-id: 2115ab1d-1084-4429-8315-0357c8525c47
source-git-commit: 69471a36b113e04a7bb0953a90977ad4020299e4
workflow-type: ht
source-wordcount: '446'
ht-degree: 100%

---

# Principio generale {#concept_gfj_fqt_52b}


>[!CAUTION]
>
>**Stai cercando Adobe Journey Optimizer**? Fai clic [qui](https://experienceleague.adobe.com/it/docs/journey-optimizer/using/ajo-home){target="_blank"} per la documentazione di Journey Optimizer.
>
>
>_Questa documentazione fa riferimento ai precedenti materiali su Journey Orchestration, che è stato sostituito da Journey Optimizer. In caso di domande sull’accesso a Journey Orchestration o Journey Optimizer, contatta il team del tuo account._



>[!CONTEXTUALHELP]
>id="jo_events"
>title="Informazioni sugli eventi"
>abstract="Un evento è collegato a una persona. e si riferisce al comportamento di una persona o a qualcosa che si verifica in relazione a una persona. Nell’ambito dei percorsi, [!DNL Journey Orchestration] farà da listener per questi dati, in modo da orchestrare le migliori azioni successive da eseguire."

Un evento è collegato a una persona. Riguarda il comportamento di una persona (ad esempio una persona che ha acquistato un prodotto, visitato un negozio, che è uscita da un sito web, ecc.) o qualcosa che accade in relazione a una persona (ad esempio, una persona che ha raggiunto 10.000 punti fedeltà). Nell’ambito dei percorsi, [!DNL Journey Orchestration] farà da listener per questi dati, in modo da orchestrare le migliori azioni successive da eseguire.

Tale configurazione è **obbligatoria**[!DNL Journey Orchestration], in quanto è progettata per fare da listener agli eventi ed è sempre eseguita da un **utente tecnico**.

La configurazione dell’evento consente di definire le informazioni che [!DNL Journey Orchestration] riceverà sotto forma di eventi. All’interno dei vari di un percorso puoi utilizzare numerosi eventi, mentre più percorsi possono sfruttare il medesimo evento.

Se modifichi un evento utilizzato in una bozza di percorso o in un percorso live, puoi cambiare solo il nome e la descrizione oppure aggiungere i campi payload. Al fine di evitare l’interruzione dei percorsi, limitiamo rigorosamente la modifica delle bozze di percorso o dei percorsi live.

Puoi definire due tipi di eventi:

* **Eventi basati sulle regole**: questo tipo di evento non genera un eventID. Utilizzando l’editor di espressioni semplici, puoi semplicemente definire una regola che verrà utilizzata dal sistema per identificare gli eventi rilevanti che attiveranno i percorsi. Questa regola può essere basata su qualsiasi campo disponibile nel payload dell’evento, ad esempio la posizione del profilo o il numero di elementi aggiunti al carrello del profilo.

  >[!CAUTION]
  >
  >Per gli eventi basati su regole viene definita una regola di quota limite. Questa limita a 5000 al secondo il numero di eventi qualificati che un percorso può elaborare per una determinata organizzazione (ORG). Corrisponde agli SLA di Journey Orchestration. Consulta questa [pagina](https://helpx.adobe.com/it/legal/product-descriptions/journey-orchestration.html).

* Eventi **generati dal sistema**: questi eventi richiedono un eventID. Questo campo eventID viene generato automaticamente durante la creazione dell’evento. Il sistema che trasmette l’evento non deve generare un ID, deve trasmettere quello disponibile nell’anteprima del payload.

Journey Orchestration richiede che gli eventi vengano inviati in streaming o in batch ad Adobe Experience Platform. Questi dati non devono necessariamente andare al Profilo in tempo reale. Se desideri utilizzare gli eventi per la segmentazione o la ricerca in un percorso diverso, ti consigliamo di abilitare il set di dati per il profilo.

Per scoprire come creare un evento, consulta questa [pagina](../event/about-creating.md).
