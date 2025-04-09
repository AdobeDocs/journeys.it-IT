---
product: adobe campaign
title: Creazione di un evento
description: Scopri come creare un evento
feature: Journeys
role: User
level: Intermediate
exl-id: 2ae8854a-c3e7-469d-9f89-25b54bc3e894
source-git-commit: 69471a36b113e04a7bb0953a90977ad4020299e4
workflow-type: tm+mt
source-wordcount: '590'
ht-degree: 47%

---

# Creazione di un nuovo evento {#section_tbk_5qt_pgb}


>[!CAUTION]
>
>**Ricerca di Adobe Journey Optimizer**? Fai clic [qui](https://experienceleague.adobe.com/it/docs/journey-optimizer/using/ajo-home){target="_blank"} per la documentazione di Journey Optimizer.
>
>
>_Questa documentazione fa riferimento ai materiali Journey Orchestration legacy che sono stati sostituiti da Journey Optimizer. Contatta il team del tuo account in caso di domande sull&#39;accesso a Journey Orchestration o Journey Optimizer._


Di seguito sono riportati i passaggi principali per la configurazione di un nuovo evento:

1. Nel menu principale, fai clic sulla scheda **[!UICONTROL Events]**. Viene visualizzato l’elenco degli eventi. Per ulteriori informazioni sull&#39;interfaccia, consultare [questa pagina](../about/user-interface.md).

   ![](../assets/journey5.png)

1. Per creare un nuovo evento, fai clic su **[!UICONTROL Add]**. Il riquadro di configurazione dell’evento si apre sul lato destro dello schermo. Inserisci un nome per l’evento. Puoi anche aggiungere una descrizione.

   ![](../assets/journey6.png)

   >[!NOTE]
   >
   >Non utilizzare spazi o caratteri speciali. Non usare più di 30 caratteri.

1. Nel campo **[!UICONTROL Event ID type]** selezionare il tipo di evento che si desidera utilizzare.

   ![](../assets/journey6bis.png)

   * **Eventi basati sulle regole**: questo tipo di evento non genera un eventID. Nel campo **Condizione ID evento** è sufficiente definire una regola che verrà utilizzata dal sistema per identificare gli eventi rilevanti che attiveranno i percorsi. Questa regola può essere basata su qualsiasi campo disponibile nel payload dell’evento, ad esempio la posizione del profilo o il numero di elementi aggiunti al carrello del profilo.

   * **Eventi generati dal sistema**: questo tipo richiede un eventID. Questo campo eventID viene generato automaticamente durante la creazione dell’evento e aggiunto all’anteprima del payload. Il sistema che trasmette l’evento non deve generare un ID, deve trasmettere quello disponibile nell’anteprima del payload. Consulta [questa sezione](../event/previewing-the-payload.md).

   >[!NOTE]
   >
   >Ulteriori informazioni sui tipi di evento in [questa sezione](../event/about-events.md).
1. Il numero di percorsi che utilizzano questo evento viene visualizzato nel campo **[!UICONTROL Used in]**. Puoi fare clic sull’icona **[!UICONTROL View journeys]** per visualizzare l’elenco dei percorsi che utilizzano questo evento.
1. Definisci i campi dello schema e del payload: in questo punto è possibile selezionare le informazioni sull’evento, solitamente denominato payload, che [!DNL Journey Orchestration] prevede di ricevere. Potrai quindi utilizzare queste informazioni nel tuo percorso. Consulta [questa pagina](../event/defining-the-payload-fields.md).
   >[!NOTE]
   >
   >Quando selezioni il tipo **[!UICONTROL System Generated]**, sono disponibili solo gli schemi che hanno il tipo eventID mixin. Quando selezioni il tipo **[!UICONTROL Rule Based]**, sono disponibili tutti gli schemi Experience Event.

1. Per gli eventi basati su regole, fare clic nel campo **[!UICONTROL Event ID condition]**. Utilizzando l’editor di espressioni semplici, definisci la condizione che verrà utilizzata dal sistema per identificare gli eventi che attiveranno il percorso.
   ![](../assets/alpha-event6.png)

   Nel nostro esempio, abbiamo scritto una condizione basata sulla città del profilo. Ciò significa che ogni volta che il sistema riceve un evento che corrisponde a questa condizione (campo **[!UICONTROL City]** e valore **[!UICONTROL Paris]**), lo trasmetterà a Journey Orchestration.

   >[!NOTE]
   >
   >L&#39;editor di espressioni avanzate non è disponibile durante la definizione di **[!UICONTROL Event ID condition]**. Nell’editor delle espressioni semplici non tutti gli operatori sono disponibili, ma dipendono dal tipo di dati. Ad esempio, per un tipo di stringa di campo, puoi utilizzare &quot;contains&quot; o &quot;equal to&quot;.

1. Aggiungi uno spazio dei nomi. Questo passaggio è facoltativo ma consigliato, poiché l’aggiunta di uno spazio dei nomi consente di sfruttare le informazioni memorizzate nel servizio Profilo cliente in tempo reale, definendo il tipo di chiave di cui dispone l’evento. Consulta [questa pagina](../event/selecting-the-namespace.md).
1. Definisci la chiave: scegli un campo di payload o specifica una formula per identificare la persona associata all’evento. Se selezioni uno spazio dei nomi, questa chiave viene impostata automaticamente, ma può essere comunque modificata. In effetti, [!DNL Journey Orchestration] seleziona la chiave che deve corrispondere allo spazio dei nomi, ad esempio, se scegli uno spazio dei nomi e-mail, opterà per la chiave e-mail. Consulta [questa pagina](../event/defining-the-event-key.md).
1. Fai clic su **[!UICONTROL Save]**.

   ![](../assets/journey7.png)

   L’evento è ora configurato e pronto per essere rilasciato in un percorso. Per poter ricevere gli eventi sono necessari ulteriori passaggi di configurazione. Consulta [questa pagina](../event/additional-steps-to-send-events-to-journey-orchestration.md).
