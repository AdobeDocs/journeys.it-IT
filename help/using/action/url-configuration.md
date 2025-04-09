---
product: adobe campaign
title: Configurazione URL
description: Informazioni sulla configurazione URL
feature: Journeys
role: User
level: Intermediate
exl-id: e7cba6c4-a231-44f9-927a-10115e7ab1dd
source-git-commit: 69471a36b113e04a7bb0953a90977ad4020299e4
workflow-type: tm+mt
source-wordcount: '371'
ht-degree: 3%

---

# Configurazione URL {#concept_gbg_1f1_2gb}



>[!CAUTION]
>
>**Ricerca di Adobe Journey Optimizer**? Fai clic [qui](https://experienceleague.adobe.com/it/docs/journey-optimizer/using/ajo-home){target="_blank"} per la documentazione di Journey Optimizer.
>
>
>_Questa documentazione fa riferimento ai materiali Journey Orchestration legacy che sono stati sostituiti da Journey Optimizer. Contatta il team del tuo account in caso di domande sull&#39;accesso a Journey Orchestration o Journey Optimizer._


Durante la configurazione di un&#39;azione personalizzata, è necessario definire i seguenti **[!UICONTROL URL Configuration]** parametri:

![](../assets/journeyurlconfiguration.png)

1. Nel campo **[!UICONTROL URL]**, specificare l&#39;URL del servizio esterno:

   * Se l’URL è statico, inseriscilo in questo campo.

   * Se l&#39;URL include un percorso dinamico, immettere solo la parte statica dell&#39;URL, ovvero lo schema, l&#39;host, la porta e, facoltativamente, una parte statica del percorso.

     Esempio: `https://xxx.yyy.com/somethingstatic/`

     Specificherai il percorso dinamico dell’URL quando aggiungi l’azione personalizzata a un percorso. [Ulteriori informazioni](../building-journeys/using-custom-actions.md).

   >[!NOTE]
   >
   >Per motivi di sicurezza, si consiglia vivamente di utilizzare lo schema HTTPS per l’URL. Non consentiamo l’uso di indirizzi Adobe non pubblici e l’uso di indirizzi IP.
   >
   >Durante la definizione di un’azione personalizzata sono consentite solo le porte predefinite: 80 per http e 443 per https.

1. Selezionare la chiamata **[!UICONTROL Method]**: può essere **[!UICONTROL POST]** o **[!UICONTROL PUT]**.
1. Nella sezione **[!UICONTROL Headers]**, definisci le intestazioni HTTP del messaggio di richiesta da inviare al servizio esterno:
   1. Per aggiungere un campo intestazione, fare clic su **[!UICONTROL Add a header field]**.
   1. Immetti la chiave del campo dell’intestazione.
   1. Per impostare un valore dinamico per la coppia chiave-valore, selezionare **[!UICONTROL Variable]**. In caso contrario, selezionare **[!UICONTROL Constant]**.

      Ad esempio, per una marca temporale, puoi impostare un valore dinamico.

   1. Se hai selezionato **[!UICONTROL Constant]**, immetti il valore costante.

      Se hai selezionato **[!UICONTROL Variable]**, specificherai questa variabile quando aggiungi l&#39;azione personalizzata a un percorso. [Ulteriori informazioni](../building-journeys/using-custom-actions.md).

      ![](../assets/journeyurlconfiguration2.png)

   1. Per eliminare un campo intestazione, posizionare il puntatore del mouse sul campo intestazione e fare clic sull&#39;icona **[!UICONTROL Delete]**.

   I campi di intestazione **[!UICONTROL Content-Type]** e **[!UICONTROL Charset]** sono impostati per impostazione predefinita. Non è possibile modificare o eliminare questi campi.

   Dopo aver aggiunto l’azione personalizzata a un percorso, puoi comunque aggiungervi campi di intestazione se il percorso è in stato di bozza. Se non vuoi che le modifiche alla configurazione influiscano sul percorso, duplica l’azione personalizzata e aggiungi i campi dell’intestazione alla nuova azione personalizzata.

   >[!NOTE]
   >
   >Le intestazioni vengono convalidate in base alle regole di analisi dei campi. [Ulteriori informazioni](https://tools.ietf.org/html/rfc7230#section-3.2.4).
