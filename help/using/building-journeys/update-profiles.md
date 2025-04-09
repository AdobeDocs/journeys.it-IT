---
product: adobe campaign
title: Aggiorna il profilo
description: Aggiorna il profilo
feature: Journeys
role: User
level: Intermediate
exl-id: eaf2c795-0920-4b9c-9f06-801e43c1844b
source-git-commit: 69471a36b113e04a7bb0953a90977ad4020299e4
workflow-type: tm+mt
source-wordcount: '390'
ht-degree: 3%

---

# Aggiorna il profilo {#update-profile}


>[!CAUTION]
>
>**Ricerca di Adobe Journey Optimizer**? Fai clic [qui](https://experienceleague.adobe.com/it/docs/journey-optimizer/using/ajo-home){target="_blank"} per la documentazione di Journey Optimizer.
>
>
>_Questa documentazione fa riferimento ai materiali Journey Orchestration legacy che sono stati sostituiti da Journey Optimizer. Contatta il team del tuo account in caso di domande sull&#39;accesso a Journey Orchestration o Journey Optimizer._


L&#39;attività azione **[!UICONTROL Update profile]** consente di aggiornare un profilo Adobe Experience Platform esistente con informazioni provenienti dall&#39;evento, da un&#39;origine dati o utilizzando un valore specifico.

## Note importanti

* L&#39;azione **Aggiorna profilo** può essere utilizzata solo nei percorsi che iniziano con un evento con uno spazio dei nomi.
* L’azione aggiorna solo i campi esistenti, non crea nuovi campi profilo.
* Impossibile utilizzare l&#39;azione **Aggiorna profilo** per generare eventi di esperienza, ad esempio un acquisto.
* Proprio come qualsiasi altra azione, puoi definire un percorso alternativo in caso di errore o timeout e non puoi inserire due azioni in parallelo.
* La richiesta di aggiornamento inviata a Platform sarà veloce ma non immediata/entro un secondo. Ci vorrà normalmente qualche secondo, ma a volte di più senza alcuna garanzia. Di conseguenza, ad esempio, se un’azione utilizza &quot;campo 1&quot; aggiornato da un’azione Aggiorna profilo posizionata in precedenza, non è previsto che &quot;campo 1&quot; venga aggiornato nell’azione.
* In modalità di test, l’aggiornamento del profilo non verrà simulato. L’aggiornamento verrà eseguito sul profilo di test.
* L&#39;attività **Update profile** non supporta i campi XDM definiti come enumerazione.

## Utilizzo dell’aggiornamento del profilo

1. Progetta il percorso iniziando con un evento. Consulta questa [sezione](../building-journeys/journey.md).

1. Nella sezione **Azione** della palette, rilascia l&#39;attività **Aggiorna profilo** nell&#39;area di lavoro.

   ![](../assets/profileupdate0.png)

1. Seleziona uno schema dall’elenco.

1. Fai clic su **Campi** per selezionare il campo da aggiornare. È possibile selezionare un solo campo.

   ![](../assets/profileupdate2.png)

1. Seleziona un set di dati dall’elenco.

   >[!NOTE]
   >
   >L&#39;azione **Aggiorna profilo** aggiorna i dati del profilo in tempo reale, ma non i set di dati. La selezione del set di dati è necessaria in quanto il profilo è un record correlato a un set di dati.

1. Fai clic sul campo **Valore** per definire il valore da utilizzare:

   * Utilizzando l’editor di espressioni semplici, puoi selezionare un campo da un’origine dati o dall’evento in ingresso.

     ![](../assets/profileupdate4.png)

   * Per definire un valore specifico o sfruttare funzioni avanzate, fare clic su **Modalità avanzata**.

     ![](../assets/profileupdate3.png)

Il **profilo di aggiornamento** è ora configurato.

![](../assets/profileupdate1.png)
