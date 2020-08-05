---
title: Creazione di un percorso
description: Scopri come creare il percorso del caso d’uso semplice
page-status-flag: never-activated
uuid: 269d590c-5a6d-40b9-a879-02f5033863fc
contentOwner: sauviat
audience: rns
content-type: reference
topic-tags: journeys
discoiquuid: 5df34f55-135a-4ea8-afc2-f9427ce5ae7b
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 017d502e21605b3e0b8c61e5fea0b4f6a65d4470
workflow-type: tm+mt
source-wordcount: '391'
ht-degree: 4%

---


# Creazione di un percorso{#concept_eyw_mcy_w2b}

L&#39;utente **** aziendale ora può costruire il percorso. Il nostro viaggio includerà solo un percorso con le seguenti attività:

* &quot;SpaBeacon&quot; **[!UICONTROL Event]**: quando una persona cammina vicino al beacon termale, il sistema riceverà un evento e il viaggio inizierà per quella persona.
* un&#39; **[!UICONTROL Condition]** attività per verificare che la persona sia una donna
* un&#39; **[!UICONTROL Email]** attività (utilizzando  Adobe Campaign Standard)
* an **[!UICONTROL End]** activity

>[!NOTE]
>
>Le attività **[!UICONTROL Push]** e **[!UICONTROL Email]** sono disponibili nella palette solo se si dispone  Adobe Campaign Standard.

Per ulteriori informazioni su come costruire un viaggio, consulta [](../building-journeys/journey.md).

1. Nel menu superiore, fai clic sulla **[!UICONTROL Home]** scheda e **[!UICONTROL Create]** crea un nuovo percorso.

   ![](../assets/journey31.png)

1. Modifica le proprietà del viaggio nel riquadro di configurazione visualizzato sul lato destro. Lo chiamiamo &quot;Spa&quot; e lo mettiamo a durare un mese, dal 1 al 31 dicembre.

   ![](../assets/journeyuc1_8.png)

1. Iniziate a progettare il viaggio trascinando e rilasciando l&#39;evento &quot;SpaBeacon&quot; dalla palette al quadro. È inoltre possibile fare doppio clic sull&#39;evento nella palette per aggiungerlo al quadro.

   ![](../assets/journeyuc1_9.png)

1. Aggiungiamo ora una condizione per verificare che la persona sia una donna. Trascina e rilascia un’attività di condizione nel percorso.

   ![](../assets/journeyuc1_10.png)

1. Scegliete il **[!UICONTROL Data Source Condition]** tipo e fate clic nel **[!UICONTROL Expression]** campo. È inoltre possibile definire un&#39;etichetta di condizione che verrà visualizzata sulla freccia, nel quadro.

   ![](../assets/journeyuc1_11.png)

1. Utilizzando l’editor di espressioni semplici, cercate il campo genere (_persona > genere_) e rilasciatelo a destra per creare la seguente condizione: &quot;genere è uguale a &quot;femmina&quot;.

   ![](../assets/journeyuc1_12.png)

1. Rilascia un&#39; **[!UICONTROL Email]** attività e seleziona il modello di messaggi transazionali &quot;Spa sconto&quot;. Questo modello è stato progettato utilizzando  Adobe Campaign. Fare riferimento a questa [pagina](https://docs.adobe.com/content/help/it-IT/campaign-standard/using/communication-channels/transactional-messaging/about-transactional-messaging.translate.html).

   ![](../assets/journeyuc1_13.png)

1. Fare clic all&#39;interno del **[!UICONTROL Email]** campo e selezionare l&#39;indirizzo e-mail dall&#39;origine dati.

   ![](../assets/journeyuc1_14.png)

1. Allo stesso modo, definisci i campi di personalizzazione del nome e del cognome dall&#39;origine dati.

   ![](../assets/journeyuc1_15.png)

1. Rilasciate un&#39; **[!UICONTROL End]** attività.

   ![](../assets/journeyuc1_17.png)

1. Fai clic sull’ **[!UICONTROL Test]** interruttore e verifica il percorso utilizzando i profili di prova. In caso di errore, disattivate la modalità di prova, modificate il percorso e verificatene di nuovo il funzionamento. Per ulteriori informazioni sulla modalità di prova, vedere [](../building-journeys/testing-the-journey.md).

   ![](../assets/journeyuc1_18bis.png)

1. Quando il test è conclusivo, potete pubblicare il viaggio dal menu a discesa in alto a destra.

   ![](../assets/journeyuc1_18.png)

La prossima volta che una donna cammina vicino al beacon termale, riceverà immediatamente un &quot;Spa sconto&quot; e-mail personalizzata.
