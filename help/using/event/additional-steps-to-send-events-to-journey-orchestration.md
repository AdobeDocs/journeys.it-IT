---
title: Passaggi aggiuntivi per l'invio di eventi all'orchestrazione del percorso
description: Ulteriori informazioni sui passaggi per l'invio di eventi all'orchestrazione del percorso
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
source-git-commit: 017d502e21605b3e0b8c61e5fea0b4f6a65d4470

---



# Passaggi aggiuntivi per l&#39;invio di eventi all&#39;orchestrazione del percorso {#concept_xrz_n1q_y2b}

>[!NOTE]
>
>Quando create un evento, l&#39;orchestrazione del percorso genera automaticamente un ID per l&#39;evento. Il sistema che preme l&#39;evento non deve generare un ID, ma deve utilizzare quello disponibile nell&#39;anteprima del payload. Vedere [](../event/previewing-the-payload.md).

Per configurare gli eventi da inviare a **[!UICONTROL Streaming Ingestion APIs]**e da utilizzare nell&#39;orchestrazione del percorso, è necessario eseguire la procedura seguente:

1. Ottenete l&#39;URL di ingresso dalle API Data Platform (consultate [Streaming Ingestion API](https://www.adobe.io/apis/cloudplatform/dataservices/data-ingestion/data-ingestion-services.html#!api-specification/markdown/narrative/technical_overview/streaming_ingest/getting_started_with_platform_streaming_ingestion.md)).
1. Copiate il payload dall’anteprima del payload nel **[!UICONTROL Event]**menu. Vedere[](../event/defining-the-payload-fields.md).

Quindi devi configurare il sistema di dati che invia gli eventi alle API Streaming Ingestion utilizzando il payload copiato:

1. Configurate una chiamata POST API all’URL delle API di ingestione dello streaming (chiamata ingresso).
1. Utilizzate il payload copiato dall&#39;orchestrazione del percorso nel corpo (&quot;sezione di dati&quot;) della chiamata API alle API di ingestione dello streaming. Vedere di seguito un esempio
1. Determinare dove ottenere tutte le variabili presenti nel payload. Esempio: se l’evento deve trasmettere l’indirizzo, il payload incollato mostrerà &quot;address&quot;: &quot;string&quot;. &quot;string&quot; deve essere sostituito dalla variabile che popolerà automaticamente il valore corretto, l&#39;e-mail della persona a cui inviare un messaggio. Nell’anteprima del payload, nella **[!UICONTROL Header]**sezione, vengono automaticamente compilati molti valori che dovrebbero facilitare il lavoro.
1. Selezionate &quot;application/json&quot; come tipo di corpo.
1. Trasferite il vostro ID ORG IMS nell&#39;intestazione utilizzando la chiave &quot;x-gw-ims-org-id&quot;. Per il valore, usate il vostro ID ORG IMS (&quot;XXX@AdobeOrg&quot;).

Di seguito è riportato un esempio di evento Streaming Ingestion APIs:

```
{
    "header": {
        "msgType": "xdmEntityCreate",
        "msgId": "c25585b9-252e-431d-b562-e73da70c04e7",
        "msgVersion": "1.0",
        "xactionId": "f5995abe-c49d-4848-9577-a7a4fc2996fb",
        "datasetId": "string - required if you want the data to land in a specific dataset - not mandatory",
        "imsOrgId": "XXX@AdobeOrg",
        "schemaRef": {
            "id": "XXX",
            "contentType": "application/vnd.adobe.xed-full+json;version=1"
        },
        "source": {
            "name": "Journeys"
        }
    },
    "body": {
        "xdmMeta": {
            "schemaRef": {
                "id": "XXX",
                "contentType": "application/vnd.adobe.xed-full+json;version=1"
            }
        },
        "xdmEntity": {
            "_instance_name": {
                "person": {
                    "firstName": "string",
                    "lastName": "string",
                    "gender": "string",
                    "birthYear": 10,
                    "emailAddress": "string"
                }
            },
            "identityMap": {
                "Email": [
                {
                    "id": "string"
                    }
                ]
            },
            "_id": "string",
            "timestamp": "2018-05-29T00:00:00.000Z",
            "_experience": {
                "campaign": {
                    "orchestration": {
                    "eventID": "XXX"
                    }
                }
            }
        }
    }
}
```

Per facilitare l’identificazione del luogo in cui incollare la parte &quot;dati&quot;, potete utilizzare uno strumento di visualizzazione JSON come [https://jsonformatter.curiousconcept.com](https://jsonformatter.curiousconcept.com)

Per risolvere eventuali problemi relativi alle API di inserimento in streaming, consultate questa [pagina](https://www.adobe.io/apis/experienceplatform/home/data-ingestion/data-ingestion-services.html#!api-specification/markdown/narrative/technical_overview/streaming_ingest/streaming_ingestion_FAQ.md).
