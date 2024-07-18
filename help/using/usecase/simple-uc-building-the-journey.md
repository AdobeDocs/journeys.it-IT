---
product: adobe campaign
title: Creazione del percorso - Semplice
description: Scopri come creare il percorso di casi d’uso semplice
feature: Journeys
role: User
level: Intermediate
exl-id: 22bcd7f4-03ee-4e4c-b221-9f14aeadded6
source-git-commit: 9db330405130b14d1d8a8cbed59f612fd1f6767b
workflow-type: tm+mt
source-wordcount: '387'
ht-degree: 30%

---

# Creazione di un percorso{#concept_eyw_mcy_w2b}

Ora l’**utente aziendale** può costruire il percorso. Il nostro percorso includerà un solo percorso con le seguenti attività:

* &quot;SpaBeacon&quot; **[!UICONTROL Event]**: quando una persona cammina vicino al beacon spa, il percorso riceverà un evento e il sistema inizierà per quella persona.
* un&#39;attività **[!UICONTROL Condition]** per verificare che la persona sia una donna
* un&#39;attività **[!UICONTROL Email]** (tramite Adobe Campaign Standard)
* un&#39;attività **[!UICONTROL End]**

>[!NOTE]
>
>Le attività **[!UICONTROL Push]** e **[!UICONTROL Email]** sono disponibili nel riquadro solo se si dispone di Adobe Campaign Standard.

Per ulteriori informazioni su come creare un percorso, fare riferimento a [questa pagina](../building-journeys/journey.md).

1. Nel menu principale, fai clic sulla scheda **[!UICONTROL Home]** e **[!UICONTROL Create]** per creare un nuovo percorso.

   ![](../assets/journey31.png)

1. Modifica le proprietà del percorso nel riquadro di configurazione visualizzato sul lato destro. Lo chiamiamo &quot;percorso termale&quot; e lo stabiliamo per durare un mese, dal 1° al 31 dicembre.

   ![](../assets/journeyuc1_8.png)

1. Inizia a progettare il percorso trascinando l’evento &quot;SpaBeacon&quot; dal riquadro all’area di lavoro. Puoi anche fare doppio clic sull’evento nel riquadro per aggiungerlo all’area di lavoro.

   ![](../assets/journeyuc1_9.png)

1. Aggiungiamo ora una condizione per verificare che la persona sia una donna. Trascina un’attività condizione nel percorso.

   ![](../assets/journeyuc1_10.png)

1. Scegli il tipo di **[!UICONTROL Data Source Condition]** e fai clic nel campo **[!UICONTROL Expression]**. Puoi anche definire un’etichetta di condizione che verrà visualizzata sulla freccia, nell’area di lavoro.

   ![](../assets/journeyuc1_11.png)

1. Utilizzando l&#39;editor di espressioni semplici, cerca il campo gender (_persona > gender_) e rilascialo a destra per creare la seguente condizione: &quot;gender is equal to &quot;Female&quot;.

   ![](../assets/journeyuc1_12.png)

1. Rilascia un&#39;attività **[!UICONTROL Email]** e seleziona il modello di messaggistica transazionale &quot;Sconto SPA&quot;. Questo modello è stato progettato con Adobe Campaign. Fai riferimento a questa [pagina](https://experienceleague.adobe.com/docs/campaign-standard/using/communication-channels/transactional-messaging/getting-started-with-transactional-msg.html?lang=it).

   ![](../assets/journeyuc1_13.png)

1. Fare clic all&#39;interno del campo **[!UICONTROL Email]** e selezionare l&#39;indirizzo di posta elettronica dall&#39;origine dati.

   ![](../assets/journeyuc1_14.png)

1. Allo stesso modo, definisci i campi di personalizzazione nome e cognome dall’origine dati.

   ![](../assets/journeyuc1_15.png)

1. Rilascia un&#39;attività **[!UICONTROL End]**.

   ![](../assets/journeyuc1_17.png)

1. Fai clic sull&#39;interruttore **[!UICONTROL Test]** e verifica il percorso utilizzando i profili di test. In caso di errori, disattiva la modalità di test, modifica il percorso e verificalo di nuovo. Per ulteriori informazioni sulla modalità di test, consulta [questa pagina](../building-journeys/testing-the-journey.md).

   ![](../assets/journeyuc1_18bis.png)

1. Quando il test va a buon fine, puoi pubblicare il percorso dal menu a discesa in alto a destra.

   ![](../assets/journeyuc1_18.png)

La prossima volta che una donna cammina vicino al beacon spa, riceverà immediatamente un &quot;Sconto Spa&quot; e-mail personalizzata.
