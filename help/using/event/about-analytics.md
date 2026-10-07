---
product: adobe campaign
title: Informazioni sui dati di Adobe Analytics
description: Scopri come sfruttare i dati di Adobe Analytics
feature: Journeys
role: User
level: Intermediate
exl-id: e9b128be-9411-4b68-935e-4cc09eae3ef6
product_v2:
  - id: cf67d108-ecf9-4fde-af49-3a3c39083bc8
    internal-label: Journey Orchestration
feature_v2:
  - id: 7de3230f-9523-5ba5-8d5c-2313288b27ef
    internal-label: Journeys
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
level_v2:
  - id: b5a62a22-46f7-4f0d-b151-3fc640bef588
    internal-label: Intermediate
source-git-commit: 255cd6677e7c9ebff63ea9a1028a042c19e63ecc
workflow-type: tm+mt
source-wordcount: '246'
ht-degree: 21%
---
# Utilizzo dei dati di Adobe Analytics{#analytics-data}


>[!CAUTION]
>
>**Stai cercando Adobe Journey Optimizer**? Fai clic [qui](https://experienceleague.adobe.com/it/docs/journey-optimizer/using/ajo-home){target="_blank"} per la documentazione di Journey Optimizer.
>
>
>_Questa documentazione fa riferimento ai precedenti materiali su Journey Orchestration, che è stato sostituito da Journey Optimizer. In caso di domande sull’accesso a Journey Orchestration o Journey Optimizer, contatta il team del tuo account._


>[!NOTE]
>
>Questa sezione si applica solo per gli eventi basati su regole e i clienti che devono utilizzare i dati di Adobe Analytics.

Puoi sfruttare tutti i dati dell’evento comportamentale di Adobe Analytics che già acquisisci e trasferisci in Platform per attivare i percorsi e automatizzare le esperienze per i clienti.

Affinché questo funzioni, devi attivare in Adobe Experience Platform la suite di rapporti che desideri sfruttare:

1. In Adobe Experience Platform, seleziona **[!UICONTROL Sources]** e quindi **[!UICONTROL Add data]** nella sezione Adobe Analytics. Viene visualizzato l’elenco delle suite di rapporti di Adobe Analytics disponibili.

1. Selezionare la suite di rapporti che si desidera abilitare, fare clic su **[!UICONTROL Next]** e quindi su **[!UICONTROL Finish]**.

1. Condividi l’ID dati sorgente con il punto di contatto del programma Alpha.

In questo modo viene attivato il connettore di origine di Analytics per quella suite di rapporti. Ogni volta che i dati vengono inseriti, vengono trasformati in un evento Experience e inviati in Adobe Experience Platform.

![](../assets/alpha-event9.png)

Per ulteriori informazioni sul connettore di origine di Adobe Analytics, consulta la [documentazione](https://experienceleague.adobe.com/docs/experience-platform/sources/connectors/adobe-applications/analytics.html) e la [esercitazione](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/create/adobe-applications/analytics.html).
