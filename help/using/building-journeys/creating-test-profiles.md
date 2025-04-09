---
product: adobe campaign
title: Creazione di un profilo di test
description: Scopri come creare il profilo di test
exl-id: f1be46a8-04b9-4f40-b18e-9099099d2e1c
source-git-commit: 69471a36b113e04a7bb0953a90977ad4020299e4
workflow-type: tm+mt
source-wordcount: '681'
ht-degree: 3%

---

# Creare profili di test {#create-test-profiles}


>[!CAUTION]
>
>**Ricerca di Adobe Journey Optimizer**? Fai clic [qui](https://experienceleague.adobe.com/it/docs/journey-optimizer/using/ajo-home){target="_blank"} per la documentazione di Journey Optimizer.
>
>
>_Questa documentazione fa riferimento ai materiali Journey Orchestration legacy che sono stati sostituiti da Journey Optimizer. Contatta il team del tuo account in caso di domande sull&#39;accesso a Journey Orchestration o Journey Optimizer._


I profili di test sono necessari quando si utilizza la modalità di test in un percorso. Per informazioni su come utilizzare la modalità di test, consulta [questa sezione](../building-journeys/testing-the-journey.md).

Esistono diversi modi per creare un profilo di test in Adobe Experience Platform. In questa documentazione, ci concentriamo su due metodi: il caricamento di un file [csv](../building-journeys/creating-test-profiles.md#create-test-profiles-csv) e l&#39;utilizzo di [chiamate API](../building-journeys/creating-test-profiles.md#create-test-profiles-api). Puoi anche caricare un file json in un set di dati, consulta la [documentazione sull&#39;acquisizione dei dati](https://experienceleague.adobe.com/docs/experience-platform/ingestion/tutorials/ingest-batch-data.html#add-data-to-dataset).

Questi metodi di importazione consentono inoltre di aggiornare gli attributi del profilo. In questo modo, puoi trasformare un profilo esistente in un profilo di test. È sufficiente utilizzare un file o una chiamata API simile e includere solo il campo &quot;testProfile&quot; con il valore &quot;true&quot;.

La creazione di un profilo di test è simile alla creazione di profili regolari in Adobe Experience Platform. Per ulteriori informazioni, consulta la [documentazione del profilo cliente in tempo reale](https://experienceleague.adobe.com/docs/experience-platform/profile/home.html?lang=it).

## Prerequisiti{#test-profile-prerequisites}

Per poter creare profili, devi innanzitutto creare uno schema e un set di dati in Adobe Experience Platform.

Innanzitutto, devi **creare uno schema**. Segui questi passaggi:

1. In Adobe Experience Platform, fare clic su **[!UICONTROL Schemas]** nel menu a sinistra.
   ![](../assets/test-profiles-0.png)
1. Fai clic su **[!UICONTROL Create schema]**, in alto a destra, quindi seleziona un tipo di schema, ad esempio **[!UICONTROL XDM Individual Profile]**.
   ![](../assets/test-profiles-1.png)
1. Scegli un nome per lo schema.
1. Nella sezione **[!UICONTROL Mixins]**, fare clic su **[!UICONTROL Add]**.
   ![](../assets/test-profiles-1-bis.png)
1. Selezionare i mixin appropriati. Assicurarsi di aggiungere il mixin **[!UICONTROL Profile test details]**. Fai clic su **[!UICONTROL Add mixin]**.
   ![](../assets/test-profiles-1-ter.png)
L’elenco dei mixin viene visualizzato nella schermata di panoramica dello schema.
   ![](../assets/test-profiles-2.png)
1. Nell’elenco dei campi, fai clic sul campo che desideri definire come identità primaria.
   ![](../assets/test-profiles-3.png)
1. Nel pannello di destra **[!UICONTROL Field properties]**, seleziona le opzioni **[!UICONTROL Identity]** e **[!UICONTROL Primary Identity]** e seleziona uno spazio dei nomi. Se desideri che l&#39;identità primaria sia un indirizzo e-mail, scegli lo spazio dei nomi **[!UICONTROL Email]**. Fai clic su **[!UICONTROL Apply]**.
   ![](../assets/test-profiles-4.png)
1. Selezionare lo schema e abilitare l&#39;opzione **[!UICONTROL Profile]** in **[!UICONTROL Schema properties]**.
   ![](../assets/test-profiles-5.png)
1. Fai clic su **[!UICONTROL Save]**.

>[!NOTE]
>
>Per ulteriori informazioni sulla creazione dello schema, consulta la [documentazione XDM](https://experienceleague.adobe.com/docs/experience-platform/xdm/ui/resources/schemas.html#prerequisites).

Quindi devi **creare il set di dati** in cui verranno importati i profili. Segui questi passaggi:

1. In Adobe Experience Platform, fai clic su **[!UICONTROL Datasets]**, nel menu a sinistra, quindi fai clic su **[!UICONTROL Create dataset]**.
   ![](../assets/test-profiles-6.png)
1. Scegli **[!UICONTROL Create dataset from schema]**.
   ![](../assets/test-profiles-7.png)
1. Selezionare lo schema creato in precedenza, quindi fare clic su **[!UICONTROL Next]**.
   ![](../assets/test-profiles-8.png)
1. Scegli un nome e fai clic su **[!UICONTROL Finish]**.
   ![](../assets/test-profiles-9.png)
1. Abilitare l&#39;opzione **[!UICONTROL Profile]**.
   ![](../assets/test-profiles-10.png)

>[!NOTE]
>
> Per ulteriori informazioni sulla creazione di set di dati, consulta la [documentazione di Catalog Service](https://experienceleague.adobe.com/docs/experience-platform/catalog/datasets/user-guide.html#getting-started).

## Creazione di un profilo di test utilizzando un file CSV{#create-test-profiles-csv}

In Adobe Experience Platform, puoi creare profili caricando un file csv contenente i diversi campi del profilo nel set di dati. Questo è il metodo più semplice.

1. Creare un semplice file CSV utilizzando un software per fogli di calcolo.
1. Aggiungi una colonna per ogni campo richiesto. Assicurati di aggiungere il campo dell’identità primaria (&quot;personID&quot; nell’esempio precedente) e il campo &quot;testProfile&quot; impostato su &quot;true&quot;.
   ![](../assets/test-profiles-11.png)
1. Aggiungi una riga per profilo e compila i valori per ciascun campo.
   ![](../assets/test-profiles-12.png)
1. Salva il foglio di calcolo come file csv. Assicurati che le virgole siano utilizzate come separatori.
1. In Adobe Experience Platform, fare clic su **[!UICONTROL Workflows]** nel menu a sinistra.
   ![](../assets/test-profiles-14.png)
1. Scegli **[!UICONTROL Map CSV to XDM schema]**, quindi fai clic su **[!UICONTROL Launch]**.
   ![](../assets/test-profiles-16.png)
1. Seleziona il set di dati in cui desideri importare i profili. Fai clic su **[!UICONTROL Next]**.
   ![](../assets/test-profiles-17.png)
1. Fai clic su **[!UICONTROL Choose files]** e seleziona il file CSV. Al caricamento del file, fare clic su **[!UICONTROL Next]**.
   ![](../assets/test-profiles-18.png)
1. Mappare i campi csv di origine ai campi dello schema, quindi fare clic su **[!UICONTROL Finish]**.
   ![](../assets/test-profiles-19.png)
1. Viene avviata l’importazione dei dati. Lo stato verrà spostato da **[!UICONTROL Processing]** a **[!UICONTROL Success]**. Fai clic su **[!UICONTROL Preview data set]**, in alto a destra.
   ![](../assets/test-profiles-20.png)
1. Verifica che i profili di test siano stati aggiunti correttamente.
   ![](../assets/test-profiles-21.png)

Vengono aggiunti i profili di test, che ora possono essere utilizzati durante il test di un percorso. Fai riferimento a [questa sezione](../building-journeys/testing-the-journey.md).
>[!NOTE]
>
> Per ulteriori informazioni sulle importazioni CSV, consulta la [documentazione sull&#39;acquisizione dei dati](https://experienceleague.adobe.com/docs/experience-platform/ingestion/tutorials/map-a-csv-file.html#tutorials).

## Creazione di profili di test tramite chiamate API{#create-test-profiles-api}

Puoi anche creare profili di test tramite chiamate API. Consulta questa [pagina](https://experienceleague.adobe.com/docs/experience-platform/profile/home.html?lang=it).

Devi utilizzare uno schema di profilo che contiene il mixin &quot;Dettagli del test di profilo&quot;. Il flag testProfile fa parte di questo mixin.

Quando crei un profilo, accertati di trasmettere il valore: testProfile = true.

Puoi anche aggiornare un profilo esistente per modificare il flag testProfile in &quot;true&quot;.

Di seguito è riportato un esempio di chiamata API per creare un profilo di test:

```
curl -X POST \
'https://dcs.adobedc.net/collection/xxxxxxxxxxxxxx' \
-H 'Cache-Control: no-cache' \
-H 'Content-Type: application/json' \
-H 'Postman-Token: xxxxx' \
-H 'cache-control: no-cache' \
-H 'x-api-key: xxxxx' \
-H 'x-gw-ims-org-id: xxxxx' \
-d '{
"header": {
"msgType": "xdmEntityCreate",
"msgId": "xxxxx",
"msgVersion": "xxxxx",
"xactionid":"xxxxx",
"datasetId": "xxxxx",
"imsOrgId": "xxxxx",
"source": {
"name": "Postman"
},
"schemaRef": {
"id": "https://example.adobe.com/mobile/schemas/xxxxx",
"contentType": "application/vnd.adobe.xed-full+json;version=1"
}
},
"body": {
"xdmMeta": {
"schemaRef": {
"contentType": "application/vnd.adobe.xed-full+json;version=1"
}
},
"xdmEntity": {
"_id": "xxxxx",
"_mobile":{
"ECID": "xxxxx"
},
"testProfile":true
}
}
}'
```
