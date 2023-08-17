---
product: adobe campaign
title: Configurazione URL
description: Informazioni sulla configurazione URL
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

Durante la configurazione di un’azione personalizzata, devi definire quanto segue **[!UICONTROL URL Configuration]** parametri:

![](../assets/journeyurlconfiguration.png)

1. In **[!UICONTROL URL]** , specifica l’URL del servizio esterno:

   * Se l’URL è statico, inseriscilo in questo campo.

   * Se l&#39;URL include un percorso dinamico, immettere solo la parte statica dell&#39;URL, ovvero lo schema, l&#39;host, la porta e, facoltativamente, una parte statica del percorso.

     Esempio: `https://xxx.yyy.com/somethingstatic/`

     Specificherai il percorso dinamico dell’URL quando aggiungi l’azione personalizzata a un percorso. [Ulteriori informazioni](../building-journeys/using-custom-actions.md).

   >[!NOTE]
   >
   >Per motivi di sicurezza, si consiglia vivamente di utilizzare lo schema HTTPS per l’URL. Non consentiamo l’uso di indirizzi Adobe non pubblici e l’uso di indirizzi IP.
   >
   >Durante la definizione di un’azione personalizzata sono consentite solo le porte predefinite: 80 per http e 443 per https.

1. Seleziona la chiamata **[!UICONTROL Method]**: può essere **[!UICONTROL POST]** o **[!UICONTROL PUT]**.
1. In **[!UICONTROL Headers]** , definisci le intestazioni HTTP del messaggio di richiesta da inviare al servizio esterno:
   1. Per aggiungere un campo intestazione, fai clic su **[!UICONTROL Add a header field]**.
   1. Immetti la chiave del campo dell’intestazione.
   1. Per impostare un valore dinamico per la coppia chiave-valore, seleziona **[!UICONTROL Variable]**. In caso contrario, seleziona **[!UICONTROL Constant]**.

      Ad esempio, per una marca temporale, puoi impostare un valore dinamico.

   1. Se hai selezionato **[!UICONTROL Constant]**, quindi immettere il valore costante.

      Se hai selezionato **[!UICONTROL Variable]**, quindi specificherai questa variabile quando aggiungi l’azione personalizzata a un percorso. [Ulteriori informazioni](../building-journeys/using-custom-actions.md).

      ![](../assets/journeyurlconfiguration2.png)

   1. Per eliminare un campo intestazione, posizionare il puntatore del mouse sul campo intestazione e fare clic sul pulsante **[!UICONTROL Delete]** icona.

   Il **[!UICONTROL Content-Type]** e **[!UICONTROL Charset]** i campi dell’intestazione sono impostati per impostazione predefinita. Non è possibile modificare o eliminare questi campi.

   Dopo aver aggiunto l’azione personalizzata a un percorso, puoi comunque aggiungervi campi di intestazione se il percorso è in stato di bozza. Se non vuoi che le modifiche alla configurazione influiscano sul percorso, duplica l’azione personalizzata e aggiungi i campi dell’intestazione alla nuova azione personalizzata.

   >[!NOTE]
   >
   >Le intestazioni vengono convalidate in base alle regole di analisi dei campi. [Ulteriori informazioni](https://tools.ietf.org/html/rfc7230#section-3.2.4).
