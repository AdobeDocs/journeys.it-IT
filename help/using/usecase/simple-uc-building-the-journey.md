---
product: adobe campaign
title: Creazione di un percorso
description: Scopri come creare un percorso di casi d’uso semplice
feature: Journeys
role: Business Practitioner
level: Intermediate
exl-id: 22bcd7f4-03ee-4e4c-b221-9f14aeadded6
source-git-commit: e7c3dde02837d31c5eb7d170cae7f142ce376175
workflow-type: tm+mt
source-wordcount: '386'
ht-degree: 35%

---

# Creazione di un percorso{#concept_eyw_mcy_w2b}

Ora l’**utente aziendale** può costruire il percorso. Il nostro percorso includerà solo un percorso con le seguenti attività:

* &quot;SpaBeacon&quot; **[!UICONTROL Event]**: quando una persona cammina vicino al beacon spa, il sistema riceverà un evento e il percorso inizierà per quella persona.
* un&#39;attività **[!UICONTROL Condition]** per verificare che la persona sia una donna
* un&#39;attività **[!UICONTROL Email]** (utilizzando Adobe Campaign Standard)
* un&#39;attività **[!UICONTROL End]**

>[!NOTE]
>
>Le attività **[!UICONTROL Push]** e **[!UICONTROL Email]** sono disponibili nel riquadro solo se si dispone di Adobe Campaign Standard.

Per ulteriori informazioni su come generare un percorso, consulta [questa pagina](../building-journeys/journey.md).

1. Nel menu principale, fai clic sulla scheda **[!UICONTROL Home]** e **[!UICONTROL Create]** per creare un nuovo percorso.

   ![](../assets/journey31.png)

1. Modifica le proprietà del percorso nel riquadro di configurazione visualizzato sul lato destro. Lo chiamiamo &quot;percorso termale&quot; e lo mettiamo a durare un mese, dal 1 al 31 dicembre.

   ![](../assets/journeyuc1_8.png)

1. Inizia a progettare il percorso trascinando l’evento &quot;SpaBeacon&quot; dalla palette all’area di lavoro. Puoi anche fare doppio clic sull’evento nel riquadro per aggiungerlo all’area di lavoro.

   ![](../assets/journeyuc1_9.png)

1. Aggiungiamo ora una condizione per verificare che la persona sia una donna. Trascina un’attività condizione nel percorso.

   ![](../assets/journeyuc1_10.png)

1. Scegli il tipo di **[!UICONTROL Data Source Condition]** e fai clic nel campo **[!UICONTROL Expression]**. Puoi anche definire un’etichetta di condizione che verrà visualizzata sulla freccia nell’area di lavoro.

   ![](../assets/journeyuc1_11.png)

1. Utilizzando l’editor di espressioni semplici, cerca il campo genere (_persona > genere_) e rilascialo a destra per creare la seguente condizione: &quot;il genere è uguale a &quot;Femmina&quot;.

   ![](../assets/journeyuc1_12.png)

1. Rilascia un’attività **[!UICONTROL Email]** e seleziona il modello di messaggistica transazionale &quot;Spa discount&quot;. Questo modello è stato progettato utilizzando Adobe Campaign. Fai riferimento a questa [pagina]().

   ![](../assets/journeyuc1_13.png)

1. Fai clic all’interno del campo **[!UICONTROL Email]** e seleziona l’indirizzo e-mail dall’origine dati.

   ![](../assets/journeyuc1_14.png)

1. Allo stesso modo, definisci i campi di personalizzazione nome e cognome dall’origine dati.

   ![](../assets/journeyuc1_15.png)

1. Rilascia un’attività **[!UICONTROL End]** .

   ![](../assets/journeyuc1_17.png)

1. Fai clic sull’interruttore **[!UICONTROL Test]** e verifica il percorso utilizzando i profili di test. In caso di errori, disattiva la modalità di test, modifica il percorso e verificalo di nuovo. Per ulteriori informazioni sulla modalità di test, consulta [questa pagina](../building-journeys/testing-the-journey.md).

   ![](../assets/journeyuc1_18bis.png)

1. Quando il test va a buon fine, puoi pubblicare il percorso dal menu a discesa in alto a destra.

   ![](../assets/journeyuc1_18.png)

La prossima volta che una donna cammina vicino al beacon spa, riceverà immediatamente un &quot;Spa sconto&quot; e-mail personalizzata.
