---
product: adobe campaign
solution: Journey Orchestration
title: Creazione di un profilo di test
description: 'Scopri la creazione del profilo di test '
translation-type: tm+mt
source-git-commit: 8c7c7d85d4e7835721b70faa7b3b6166796e79c4
workflow-type: tm+mt
source-wordcount: '968'
ht-degree: 1%

---


# Creare profili di test {#create-test-profiles}

![](../assets/do-not-localize/badge.png)

I profili di test sono necessari quando si utilizza la modalità di test in un percorso. Puoi trasformare un [profilo esistente](../building-journeys/creating-test-profiles.md#turning-profile-into-test) in un profilo di test oppure [creare un profilo di test](../building-journeys/creating-test-profiles.md#create-test-profiles-csv). Per informazioni su come utilizzare la modalità di test, consulta [questa sezione](../building-journeys/testing-the-journey.md).

Esistono diversi modi per creare un profilo di test in Adobe Experience Platform. In questa documentazione sono disponibili due metodi: caricamento di un [file csv](../building-journeys/creating-test-profiles.md#create-test-profiles-csv) e utilizzo di [chiamate API](../building-journeys/creating-test-profiles.md#create-test-profiles-api). Puoi anche caricare un file json in un set di dati, consulta la [documentazione sull’acquisizione dei dati](https://experienceleague.adobe.com/docs/experience-platform/ingestion/tutorials/ingest-batch-data.html#add-data-to-dataset)

La creazione di un profilo di test è simile alla creazione di profili normali in Adobe Experience Platform. Per ulteriori informazioni, consulta la [documentazione Profilo cliente in tempo reale](https://experienceleague.adobe.com/docs/experience-platform/profile/home.html).

## Prerequisiti{#test-profile-prerequisites}

Per poter creare profili, devi innanzitutto creare uno schema e un set di dati in Adobe Experience Platform.

Innanzitutto, devi **creare uno schema**. Segui questi passaggi:

1. In Adobe Experience Platform, fai clic su **Schemi** nel menu a sinistra.
   ![](../assets/test-profiles-0.png)
1. Fai clic su **Crea schema**, in alto a destra, quindi seleziona un tipo di schema, ad esempio **Profilo individuale XDM**.
   ![](../assets/test-profiles-1.png)
1. Scegli un nome per lo schema.
1. Nella sezione **Mixins**, fai clic su **Aggiungi**.
   ![](../assets/test-profiles-1-bis.png)
1. Selezionare i mixin appropriati. Assicurati di aggiungere il mixin **Dettagli test profilo** . Fare clic su **Aggiungi mixin**.
   ![](../assets/test-profiles-1-ter.png)
L’elenco dei mixin viene visualizzato nella schermata di panoramica dello schema.

   ![](../assets/test-profiles-2.png)
1. Nell’elenco dei campi, fai clic sul campo da definire come identità principale.
   ![](../assets/test-profiles-3.png)
1. Nel pannello a destra **Proprietà campo**, seleziona le opzioni **Identità** e **Identità principale** e seleziona uno spazio dei nomi. Se desideri che l’identità principale sia un indirizzo e-mail, scegli lo spazio dei nomi **Email** . Fare clic su **Applica**.
   ![](../assets/test-profiles-4.png)
1. Seleziona lo schema e abilita l&#39;opzione **Profilo** nelle proprietà **Schema**.
   ![](../assets/test-profiles-5.png)
1. Fai clic su **Salva**.

>[!NOTE]
>
>Per ulteriori informazioni sulla creazione dello schema, consulta la [documentazione XDM](https://experienceleague.adobe.com/docs/experience-platform/xdm/ui/resources/schemas.html#prerequisites).

Quindi devi **creare il set di dati** in cui i profili verranno importati. Segui questi passaggi:

1. In Adobe Experience Platform, fai clic su **Set di dati**, nel menu a sinistra, quindi fai clic su **Crea set di dati**.
   ![](../assets/test-profiles-6.png)
1. Scegli **Crea set di dati da schema**.
   ![](../assets/test-profiles-7.png)
1. Seleziona lo schema creato in precedenza e fai clic su **Avanti**.
   ![](../assets/test-profiles-8.png)
1. Scegli un nome e fai clic su **Fine**.
   ![](../assets/test-profiles-9.png)
1. Abilita l’opzione **Profilo** .
   ![](../assets/test-profiles-10.png)

>[!NOTE]
>
> Per ulteriori informazioni sulla creazione dei set di dati, consulta la [documentazione Servizio catalogo](https://experienceleague.adobe.com/docs/experience-platform/catalog/datasets/user-guide.html#getting-started).

## Trasformazione di un profilo in un profilo di test{#turning-profile-into-test}

Puoi trasformare un profilo esistente in un profilo di test. In Adobe Experience Platform, puoi aggiornare gli attributi dei profili nello stesso modo in cui crei un profilo.

Un modo più semplice per farlo è utilizzare un&#39;attività di azione **Aggiorna profilo** in un percorso e cambiare il campo booleano testProfile da false a true.

Il percorso sarà composto da un&#39;attività **Leggi segmento** e da un&#39;attività **Aggiorna profilo**. Devi innanzitutto creare un segmento che esegue il targeting dei profili che desideri trasformare in profili di test.

>[!NOTE]
>
> Poiché stai aggiornando il campo **testProfile**, i profili selezionati devono includere questo campo. Lo schema correlato deve avere il mixin **Dettagli test profilo** . Vedi [questa sezione](../building-journeys/creating-test-profiles.md#test-profiles-prerequisites).

1. In Gestione dei Percorsi cliente, fai clic su **Segmenti** dal menu a sinistra, quindi **Crea segmento**, in alto a destra.
   ![](../assets/test-profiles-22.png)
1. Definisci un nome per il segmento e crea il segmento: scegli i campi e i valori per eseguire il targeting dei profili desiderati.
   ![](../assets/test-profiles-23.png)
1. Fai clic su **Salva** e verifica che il targeting dei profili sia corretto per il segmento.
   ![](../assets/test-profiles-24.png)

   >[!NOTE]
   >
   > Il calcolo del segmento può richiedere del tempo. Ulteriori informazioni sui segmenti in [questa sezione](../segment/about-segments.md).

1. Ora crea un nuovo percorso e inizia con un&#39;attività di orchestrazione **Read segment** .
1. Scegli il segmento creato in precedenza e lo spazio dei nomi utilizzato dai profili.
   ![](../assets/test-profiles-25.png)
1. Aggiungi un&#39;attività di azione **Aggiorna profilo**.
1. Seleziona lo schema, il campo **testProfiles**, il set di dati e imposta il valore su &quot;true&quot;.
   ![](../assets/test-profiles-26.png)
1. Aggiungi un&#39;attività **End** e fai clic su **Pubblica**.
   ![](../assets/test-profiles-27.png)
1. In Adobe Experience Platform, verifica che i profili siano stati aggiornati correttamente.
   ![](../assets/test-profiles-28.png)

   >[!NOTE]
   >
   > Per ulteriori informazioni sull&#39;attività **Aggiorna profilo**, consulta [questa sezione](../building-journeys/update-profiles.md).

## Creazione di un profilo di test tramite un file csv{#create-test-profiles-csv}

In Adobe Experience Platform, puoi creare profili caricando un file csv contenente i diversi campi di profilo nel set di dati. Questo è il metodo più semplice.

1. Crea un file csv semplice utilizzando un foglio di calcolo.
1. Aggiungi una colonna per ogni campo necessario. Assicurati di aggiungere il campo di identità principale (&quot;personID&quot; nel nostro esempio sopra) e il campo &quot;testProfile&quot; impostato su &quot;true&quot;.
   ![](../assets/test-profiles-11.png)
1. Aggiungi una riga per profilo e compila i valori per ciascun campo.
   ![](../assets/test-profiles-12.png)
1. Salva il foglio di calcolo come file csv. Assicurati che le virgole siano utilizzate come separatori.
1. In Adobe Experience Platform, fai clic su **Flussi di lavoro** nel menu a sinistra.
   ![](../assets/test-profiles-14.png)
1. Scegli **Mappa CSV su schema XDM**, quindi fai clic su **Launch**.
   ![](../assets/test-profiles-16.png)
1. Seleziona il set di dati in cui desideri importare i profili. Fare clic su **Avanti**.
   ![](../assets/test-profiles-17.png)
1. Fai clic su **Scegli i file** e seleziona il file CSV. Quando il file viene caricato, fai clic su **Avanti**.
   ![](../assets/test-profiles-18.png)
1. Mappa i campi csv di origine ai campi dello schema, quindi fai clic su **Fine**.
   ![](../assets/test-profiles-19.png)
1. Inizia l’importazione dei dati. Lo stato verrà spostato da **Elaborazione** a **Success**. Fai clic su **Anteprima set di dati** in alto a destra.
   ![](../assets/test-profiles-20.png)
1. Verifica che i profili di test siano stati aggiunti correttamente.
   ![](../assets/test-profiles-21.png)

I profili di test vengono aggiunti e possono ora essere utilizzati durante il test di un percorso. Fai riferimento a [questa sezione](../building-journeys/testing-the-journey.md).
>[!NOTE]
>
> Per ulteriori informazioni sulle importazioni CSV, consulta la [documentazione sull’ acquisizione dei dati](https://experienceleague.adobe.com/docs/experience-platform/ingestion/tutorials/map-a-csv-file.html#tutorials).

## Creazione di profili di test utilizzando le chiamate API{#create-test-profiles-api}

Puoi anche creare profili di test tramite chiamate API. Vedere questa [pagina](https://docs.adobe.com/content/help/it-IT/experience-platform/profile/home.html).

Devi utilizzare uno schema di profilo contenente il mixin &quot;Dettagli del test di profilo&quot;. Il flag testProfile fa parte di questo mixin.

Quando crei un profilo, accertati di trasmettere il valore: testProfile = true.

Tieni presente che puoi anche aggiornare un profilo esistente per modificare il relativo flag testProfile in &quot;true&quot;.

Ecco un esempio di chiamata API per creare un profilo di test:

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

