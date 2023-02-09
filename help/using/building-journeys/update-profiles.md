---
product: adobe campaign
title: Aggiorna il profilo
description: Aggiorna il profilo
feature: Journeys
role: User
level: Intermediate
exl-id: eaf2c795-0920-4b9c-9f06-801e43c1844b
source-git-commit: 64f415f3a4120685b64a4b1dc15bf004e86b35d2
workflow-type: tm+mt
source-wordcount: '343'
ht-degree: 3%

---

# Aggiorna il profilo {#update-profile}

La **[!UICONTROL Update profile]** l’attività action ti consente di aggiornare un profilo Adobe Experience Platform esistente con informazioni provenienti dall’evento, da un’origine dati o utilizzando un valore specifico.

## Note importanti

* La **Aggiorna profilo** può essere utilizzata solo nei percorsi che iniziano con un evento con uno spazio dei nomi.
* L’azione aggiorna solo i campi esistenti e non crea nuovi campi di profilo.
* Non è possibile utilizzare il **Aggiorna profilo** azione per generare eventi di esperienza, ad esempio un acquisto.
* Come qualsiasi altra azione, puoi definire un percorso alternativo in caso di errore o timeout e non puoi eseguire due azioni in parallelo.
* La richiesta di aggiornamento inviata a Platform sarà rapida ma non immediata/entro un secondo. Normalmente ci vorranno alcuni secondi, ma a volte di più senza garanzia. Di conseguenza, ad esempio, se un’azione utilizza &quot;campo 1&quot; aggiornato da un’azione Aggiorna profilo posizionata in precedenza, non devi aspettarti che il &quot;campo 1&quot; venga aggiornato nell’azione .
* In modalità di test, l’aggiornamento del profilo non verrà simulato. L’aggiornamento viene eseguito sul profilo di test.
* La **Aggiorna profilo** l&#39;attività non supporta campi XDM definiti come enumerazione.

## Utilizzo dell’aggiornamento del profilo

1. Progetta il tuo percorso iniziando con un evento. Consulta questa [sezione](../building-journeys/journey.md).

1. In **Azione** della palette, rilascia la **Aggiorna profilo** nell’area di lavoro.

   ![](../assets/profileupdate0.png)

1. Selezionare uno schema dall&#39;elenco.

1. Fai clic su **Campi** per selezionare il campo da aggiornare. È possibile selezionare un solo campo.

   ![](../assets/profileupdate2.png)

1. Seleziona un set di dati dall’elenco.

   >[!NOTE]
   >
   >La **Aggiorna profilo** aggiorna i dati del profilo in tempo reale, ma non i set di dati. La selezione del set di dati è necessaria in quanto il profilo è un record relativo a un set di dati.

1. Fai clic sul pulsante **Valore** per definire il valore da utilizzare:

   * Utilizzando l’editor di espressioni semplici, puoi selezionare un campo da un’origine dati o dall’evento in arrivo.

      ![](../assets/profileupdate4.png)

   * Se desideri definire un valore specifico o sfruttare funzioni avanzate, fai clic su **Modalità avanzata**.

      ![](../assets/profileupdate3.png)

La **Aggiorna profilo** è ora configurato.

![](../assets/profileupdate1.png)
