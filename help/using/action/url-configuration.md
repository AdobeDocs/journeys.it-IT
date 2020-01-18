---
title: Configurazione URL
description: Informazioni sulla configurazione URL
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
source-git-commit: 1bc8d845716044671a11c200e4bab92302841994

---


# Configurazione URL {#concept_gbg_1f1_2gb}

Quando si configura un&#39;azione personalizzata, è necessario definire i seguenti **[!UICONTROL URL Configuration]**parametri:

![](../assets/journeyurlconfiguration.png)

1. Aggiungete il **[!UICONTROL URL]**contenuto del servizio esterno.

   >[!NOTE]
   >
   >È consigliabile utilizzare HTTPS per motivi di sicurezza. Non consentiamo l&#39;uso di indirizzi Adobe non pubblici e l&#39;uso di indirizzi IP.

1. Seleziona la chiamata **[!UICONTROL Method]**: può essere uno**[!UICONTROL POST]** o **[!UICONTROL PUT]**.
1. Nella **[!UICONTROL Headers]**sezione fare clic**[!UICONTROL Add a header field]** per definire una nuova coppia chiave/valore. Corrispondono alle intestazioni HTTP della richiesta effettuata al servizio esterno. Per eliminare coppie chiave/valore, posizionate il cursore sul **[!UICONTROL Headers]**campo e fate clic sull&#39;**[!UICONTROL Delete]** icona.

   **[!UICONTROL Content-Type]**e**[!UICONTROL Charset]** sono impostati per impostazione predefinita e non possono essere eliminati o sovrascritti.

   >[!NOTE]
   >
   >Le intestazioni vengono convalidate in base alle seguenti regole di [analisi](https://tools.ietf.org/html/rfc7230#section-3.2.4).
