---
product: adobe campaign
solution: Journey Orchestration
title: Configurazione URL
description: Informazioni sulla configurazione URL
translation-type: tm+mt
source-git-commit: 57dc86d775bf8860aa09300cf2432d70c62a2993
workflow-type: tm+mt
source-wordcount: '126'
ht-degree: 9%

---


# Configurazione URL {#concept_gbg_1f1_2gb}

Durante la configurazione di un&#39;azione personalizzata, è necessario definire i seguenti parametri **[!UICONTROL URL Configuration]**:

![](../assets/journeyurlconfiguration.png)

1. Aggiungete la **[!UICONTROL URL]** del servizio esterno.

   >[!NOTE]
   >
   >Per motivi di sicurezza, è consigliabile utilizzare HTTPS. Non consentiamo l&#39;uso di indirizzi  Adobe non pubblici e l&#39;uso di indirizzi IP.

1. Seleziona la chiamata **[!UICONTROL Method]**: può essere **[!UICONTROL POST]** o **[!UICONTROL PUT]**.
1. Nella sezione **[!UICONTROL Headers]**, fare clic su **[!UICONTROL Add a header field]** per definire una nuova coppia chiave/valore. Corrispondono alle intestazioni HTTP della richiesta effettuata al servizio esterno. Per eliminare coppie chiave/valore, posizionate il cursore sul campo **[!UICONTROL Headers]** e fate clic sull&#39;icona **[!UICONTROL Delete]**.

   **[!UICONTROL Content-Type]** e  **[!UICONTROL Charset]** sono impostati per impostazione predefinita e non possono essere eliminati o sovrascritti.

   >[!NOTE]
   >
   >Le intestazioni vengono convalidate in base alle seguenti [regole di analisi](https://tools.ietf.org/html/rfc7230#section-3.2.4).
