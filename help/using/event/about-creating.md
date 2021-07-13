---
product: adobe campaign
title: Creazione di un evento
description: Scopri come creare un evento
feature: Percorsi
role: User
level: Intermediate
exl-id: 2ae8854a-c3e7-469d-9f89-25b54bc3e894
source-git-commit: 185c2296a51f58e2092787edcc35ee9e4242bec8
workflow-type: tm+mt
source-wordcount: '554'
ht-degree: 63%

---

# Creazione di un nuovo evento {#section_tbk_5qt_pgb}

Di seguito sono riportati i passaggi principali per la configurazione di un nuovo evento:

1. Nel menu principale, fai clic sulla scheda **[!UICONTROL Events]**. Viene visualizzato l’elenco degli eventi. Per ulteriori informazioni sull&#39;interfaccia, consulta [questa pagina](../about/user-interface.md) .

   ![](../assets/journey5.png)

1. Per creare un nuovo evento, fai clic su **[!UICONTROL Add]**. Il riquadro di configurazione dell’evento si apre sul lato destro dello schermo. Inserisci un nome per l’evento. Puoi anche aggiungere una descrizione.

   ![](../assets/journey6.png)

   >[!NOTE]
   >
   >Non utilizzare spazi o caratteri speciali. Non usare più di 30 caratteri.

1. Nel campo **[!UICONTROL Event ID type]** , seleziona il tipo di evento da utilizzare.

   ![](../assets/journey6bis.png)

   * **Eventi basati sulle regole**: questo tipo di evento non genera un eventID. Nel campo **Condizione ID evento** , definisci semplicemente una regola che verrà utilizzata dal sistema per identificare gli eventi rilevanti che attiveranno i tuoi percorsi. Questa regola può essere basata su qualsiasi campo disponibile nel payload dell’evento, ad esempio la posizione del profilo o il numero di elementi aggiunti al carrello del profilo.

   * **Sviluppatori** di sistema: questo tipo richiede un eventID. Questo campo eventID viene generato automaticamente durante la creazione dell’evento e aggiunto all’anteprima del payload. Il sistema che trasmette l’evento non deve generare un ID, deve trasmettere quello disponibile nell’anteprima del payload. Vedi [questa sezione](../event/previewing-the-payload.md).
   >[!NOTE]
   >
   >Ulteriori informazioni sui tipi di evento in [questa sezione](../event/about-events.md).
1. Il numero di percorsi che utilizzano questo evento viene visualizzato nel campo **[!UICONTROL Used in]**. Puoi fare clic sull’icona **[!UICONTROL View journeys]** per visualizzare l’elenco dei percorsi che utilizzano questo evento.
1. Definisci i campi dello schema e del payload: in questo punto è possibile selezionare le informazioni sull’evento, solitamente denominato payload, che [!DNL Journey Orchestration] prevede di ricevere. Potrai quindi utilizzare queste informazioni nel tuo percorso. Consulta [questa pagina](../event/defining-the-payload-fields.md).
   >[!NOTE]
   >
   >Quando selezioni il tipo **[!UICONTROL System Generated]** , sono disponibili solo gli schemi con il mixin del tipo eventID. Quando selezioni il tipo **[!UICONTROL Rule Based]** , sono disponibili tutti gli schemi Experience Event .

1. Per gli eventi basati su regole, fai clic all’interno del campo **[!UICONTROL Event ID condition]** . Utilizzando l’editor di espressioni semplici, definisci la condizione che verrà utilizzata dal sistema per identificare gli eventi che attiveranno il percorso.
   ![](../assets/alpha-event6.png)

   Nel nostro esempio, abbiamo scritto una condizione basata sulla città del profilo. Ciò significa che ogni volta che il sistema riceve un evento che corrisponde a questa condizione (**[!UICONTROL City]** field e **[!UICONTROL Paris]** value), lo trasmette al Journey Orchestration.

   >[!NOTE]
   >
   >L’editor di espressioni avanzate non è disponibile quando si definisce **[!UICONTROL Event ID condition]**.

1. Aggiungi uno spazio dei nomi. Questo passaggio è facoltativo ma consigliato, poiché l’aggiunta di uno spazio dei nomi consente di sfruttare le informazioni memorizzate nel servizio Profilo cliente in tempo reale, definendo il tipo di chiave di cui dispone l’evento. Consulta [questa pagina](../event/selecting-the-namespace.md).
1. Definisci la chiave: scegli un campo di payload o specifica una formula per identificare la persona associata all’evento. Se selezioni uno spazio dei nomi, questa chiave viene impostata automaticamente, ma può essere comunque modificata. In effetti, [!DNL Journey Orchestration] seleziona la chiave che deve corrispondere allo spazio dei nomi, ad esempio, se scegli uno spazio dei nomi e-mail, opterà per la chiave e-mail. Consulta [questa pagina](../event/defining-the-event-key.md).
1. Per gli eventi generati dal sistema, puoi aggiungere una condizione . Questo passaggio è facoltativo. In tal modo, consenti al sistema di elaborare solo gli eventi che soddisfano la condizione specifica. Tale condizione può essere basata solo sulle informazioni contenute nell’evento. Consulta [questa pagina](../event/adding-a-condition.md).
1. Fai clic su **[!UICONTROL Save]**.

   ![](../assets/journey7.png)

   L’evento è ora configurato e pronto per essere rilasciato in un percorso. Per poter ricevere gli eventi sono necessari ulteriori passaggi di configurazione. Consulta [questa pagina](../event/additional-steps-to-send-events-to-journey-orchestration.md).
