---
product: adobe campaign
solution: Journey Orchestration
title: Terminazione di un percorso
description: Scopri come terminare un percorso
feature: Journeys
role: Professionista
level: Intermedio
translation-type: tm+mt
source-git-commit: 7755822065eb0bcc44f78e0e36c53ce73ac60ada
workflow-type: tm+mt
source-wordcount: '359'
ht-degree: 5%

---


# Terminazione di un percorso

Le opzioni **[!UICONTROL Stop]** e **[!UICONTROL Close to new entrances]** consentono di terminare i percorsi **live**. La chiusura di un percorso implica **che l&#39;arrivo di nuovi clienti nel percorso è bloccato** e che i clienti che sono già entrati nel percorso sono in grado di sperimentarlo fino alla fine. Questo è il modo più consigliato per mettere fine a un percorso in quanto offre la migliore esperienza per i clienti. Arrestare un percorso implica che le persone che sono già entrate in un percorso vengono tutte fermate nel loro progresso. Il percorso è fondamentalmente spento.

>[!NOTE]
>
>Non è possibile riprendere un percorso chiuso o interrotto.
>
>Il concetto di fine percorso è descritto in questa sezione [sezione](../building-journeys/journey.md#ending_a_journey).

## Chiusura di un percorso

È possibile chiudere manualmente un percorso per garantire che i clienti che sono già entrati nel percorso possano completare il loro percorso ma i nuovi utenti non siano in grado di accedere al percorso.

Una volta chiuso, un percorso avrà lo stato **[!UICONTROL Closed (no entrance)]**. Dopo il timeout globale predefinito di 30 giorni, il percorso passa allo stato **Finished** . Vedere questa sezione [](../building-journeys/changing-properties.md#entrance).

Impossibile riavviare o eliminare una versione di un percorso chiuso. Puoi crearne una nuova versione o duplicarla. È possibile eliminare solo i percorsi finiti.

Per chiudere un percorso, fai clic su **[!UICONTROL Close to new entrances]** mentre passi il mouse su un percorso nell’elenco dei percorsi.

![](../assets/do-not-localize/journey-finish-quick-action.png)

Puoi inoltre:

1. In **[!UICONTROL Home]**, fai clic sul percorso da chiudere.
1. In alto a destra, fai clic sulla freccia giù.

   ![](../assets/finish_drop_down_list.png)

1. Fai clic su **[!UICONTROL Close to new entrances]**. Viene visualizzata una finestra di dialogo.
1. Fai clic su **[!UICONTROL Close to new entrances]** per confermare.

## Arresto di un percorso

È possibile interrompere un percorso quando si è verificata un&#39;emergenza e tutte le operazioni di elaborazione devono essere terminate immediatamente su un percorso.

Impossibile riavviare una versione di percorso interrotta.

Quando viene arrestato, un percorso avrà lo stato **[!UICONTROL Stopped]**.

È possibile arrestare un percorso (ad esempio se un addetto al marketing si rende conto che il percorso esegue il targeting del pubblico errato o che un&#39;azione personalizzata che dovrebbe inviare i messaggi non funziona correttamente) facendo clic su **[!UICONTROL Stop]** mentre si passa il mouse su un percorso nell&#39;elenco dei percorsi.

![](../assets/do-not-localize/journey-stop-quick-action.png)

Puoi inoltre:

1. In **[!UICONTROL Home]**, fai clic sul percorso da interrompere.
1. In alto a destra, fai clic sulla freccia giù.

![](../assets/finish_drop_down_list.png)

1. Fai clic su **[!UICONTROL Stop]**. Viene visualizzata una finestra di dialogo.
1. Fai clic su **[!UICONTROL Stop]** per confermare.
