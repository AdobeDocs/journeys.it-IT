---
product: adobe campaign
title: Configurazione URL
description: Scopri la configurazione dell’URL
feature: Journeys
role: Business Practitioner
level: Intermediate
exl-id: e7cba6c4-a231-44f9-927a-10115e7ab1dd
source-git-commit: 712f66b2715bac0af206755e59728c95499fa110
workflow-type: tm+mt
source-wordcount: '127'
ht-degree: 10%

---

# Configurazione URL {#concept_gbg_1f1_2gb}

Quando configuri un’azione personalizzata, devi definire i seguenti parametri **[!UICONTROL URL Configuration]**:

![](../assets/journeyurlconfiguration.png)

1. Aggiungi il **[!UICONTROL URL]** del servizio esterno.

   >[!NOTE]
   >
   >Per motivi di sicurezza, è consigliabile utilizzare HTTPS. Non consentiamo l’uso di indirizzi di Adobe che non sono pubblici e l’uso di indirizzi IP.

1. Seleziona la chiamata **[!UICONTROL Method]**: può essere **[!UICONTROL POST]** o **[!UICONTROL PUT]**.
1. Nella sezione **[!UICONTROL Headers]**, fai clic su **[!UICONTROL Add a header field]** per definire una nuova coppia chiave/valore. Corrispondono alle intestazioni HTTP della richiesta effettuata al servizio esterno. Per eliminare le coppie chiave/valore, posiziona il cursore sul campo **[!UICONTROL Headers]** e fai clic sull&#39;icona **[!UICONTROL Delete]**.

   **[!UICONTROL Content-Type]** e  **[!UICONTROL Charset]** sono impostati per impostazione predefinita e non possono essere eliminati o ignorati.

   >[!NOTE]
   >
   >Le intestazioni vengono convalidate in base alle seguenti [regole di analisi](https://tools.ietf.org/html/rfc7230#section-3.2.4).
