---
product: adobe campaign
title: Configurazione URL
description: Scopri la configurazione dell’URL
feature: Journeys
role: User
level: Intermediate
exl-id: e7cba6c4-a231-44f9-927a-10115e7ab1dd
source-git-commit: 2a93bce42ea9f1f21d70c68da3dbc36844dafd1b
workflow-type: tm+mt
source-wordcount: '328'
ht-degree: 4%

---

# Configurazione URL {#concept_gbg_1f1_2gb}

Quando configuri un’azione personalizzata, devi definire i seguenti parametri **[!UICONTROL URL Configuration]**:

![](../assets/journeyurlconfiguration.png)

1. Nel campo **[!UICONTROL URL]** , specifica l’URL del servizio esterno:

   * Se l’URL è statico, immetti l’URL in questo campo.

   * Se l’URL include un percorso dinamico, immetti solo la parte statica dell’URL, ovvero lo schema, l’host, la porta e, facoltativamente, una parte statica del percorso.

      Esempio: `https://xxx.yyy.com/somethingstatic/`

      Quando aggiungi l’azione personalizzata a un percorso, specificerai il percorso dinamico dell’URL. [Ulteriori informazioni](../building-journeys/using-custom-actions.md).
   >[!NOTE]
   >
   >Per motivi di sicurezza, si consiglia vivamente di utilizzare lo schema HTTPS per l’URL. Non consentiamo l’uso di indirizzi di Adobe che non sono pubblici e l’uso di indirizzi IP.
   >
   >Quando definisci un’azione personalizzata sono consentite solo le porte predefinite: 80 per http e 443 per https.

1. Seleziona la chiamata **[!UICONTROL Method]**: può essere **[!UICONTROL POST]** o **[!UICONTROL PUT]**.
1. Nella sezione **[!UICONTROL Headers]** , definisci le intestazioni HTTP del messaggio di richiesta da inviare al servizio esterno:
   1. Per aggiungere un campo di intestazione, fare clic su **[!UICONTROL Add a header field]**.
   1. Immetti la chiave del campo intestazione.
   1. Per impostare un valore dinamico per la coppia chiave-valore, selezionare **[!UICONTROL Variable]**. In caso contrario, selezionare **[!UICONTROL Constant]**.

      Ad esempio, per una marca temporale, è possibile impostare un valore dinamico.

   1. Se hai selezionato **[!UICONTROL Constant]**, immetti il valore costante.

      Se hai selezionato **[!UICONTROL Variable]**, specificerai questa variabile quando aggiungi l’azione personalizzata a un percorso. [Ulteriori informazioni](../building-journeys/using-custom-actions.md).

      ![](../assets/journeyurlconfiguration2.png)

   1. Per eliminare un campo di intestazione, puntare al campo di intestazione e fare clic sull&#39;icona **[!UICONTROL Delete]**.
   I campi di intestazione **[!UICONTROL Content-Type]** e **[!UICONTROL Charset]** sono impostati per impostazione predefinita. Non è possibile modificare o eliminare questi campi.

   Dopo aver aggiunto l’azione personalizzata a un percorso, puoi comunque aggiungergli dei campi di intestazione se il percorso è in stato di bozza. Se non desideri che le modifiche alla configurazione interessino il percorso, duplica l’azione personalizzata e aggiungi i campi di intestazione alla nuova azione personalizzata.

   >[!NOTE]
   >
   >Le intestazioni vengono convalidate in base alle regole di analisi dei campi. [Ulteriori informazioni](https://tools.ietf.org/html/rfc7230#section-3.2.4).
