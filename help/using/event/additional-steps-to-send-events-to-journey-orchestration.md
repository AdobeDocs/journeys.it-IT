---
title: Passaggi aggiuntivi per l'invio di eventi al Journey Orchestration
description: Ulteriori informazioni sui passaggi per l'invio di eventi al Journey Orchestration
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
source-git-commit: eb4474313d3c0470448f9959ed757902ef0ecd2a
workflow-type: tm+mt
source-wordcount: '319'
ht-degree: 6%

---



# Additional steps to send events to [!DNL Journey Orchestration] {#concept_xrz_n1q_y2b}

>[!NOTE]
>
>Quando create un evento, genera [!DNL Journey Orchestration] automaticamente un ID per questo evento. Il sistema che preme l&#39;evento non deve generare un ID, ma deve utilizzare quello disponibile nell&#39;anteprima del payload. A questo proposito, consulta la sezione [](../event/previewing-the-payload.md).

Per configurare gli eventi a cui inviare **[!UICONTROL Streaming Ingestion APIs]** e in cui utilizzarli, [!DNL Journey Orchestration]è necessario effettuare le seguenti operazioni:

1. Ottenete l’URL di ingresso dalle API Adobe Experience Platform (consultate [Streaming Ingestion API](https://docs.adobe.com/content/help/it-IT/experience-platform/ingestion/streaming/overview.html)).
1. Copiate il payload dall’anteprima del payload nel **[!UICONTROL Event]** menu. A questo proposito, consulta la sezione [](../event/defining-the-payload-fields.md).

Quindi devi configurare il sistema di dati che invia gli eventi alle API Streaming Ingestion utilizzando il payload copiato:

1. Configurate una chiamata API POST all&#39;URL delle API di ingestione dello streaming (chiamata ingresso).
1. Utilizzate il payload copiato [!DNL Journey Orchestration] nel corpo (&quot;sezione dati&quot;) della chiamata API alle API di ingestione dello streaming. Vedere di seguito un esempio
1. Determinare dove ottenere tutte le variabili presenti nel payload. Esempio: se l’evento deve trasmettere l’indirizzo, il payload incollato mostrerà &quot;address&quot;: &quot;string&quot;. &quot;string&quot; deve essere sostituito dalla variabile che popolerà automaticamente il valore corretto, l&#39;e-mail della persona a cui inviare un messaggio. Nell’anteprima del payload, nella **[!UICONTROL Header]** sezione, vengono automaticamente compilati molti valori che dovrebbero facilitare il lavoro.
1. Selezionate &quot;application/json&quot; come tipo di corpo.
1. Passa l’ID organizzazione IMS nell’intestazione utilizzando la chiave &quot;x-gw-ims-org-id&quot;. Per questo valore, utilizzate il vostro ID organizzazione IMS (&quot;XXX@AdobeOrg&quot;).

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

Per facilitare l’identificazione del luogo in cui incollare la parte &quot;dati&quot;, potete utilizzare uno strumento di visualizzazione JSON, ad esempio [https://jsonformatter.curiousconcept.com](https://jsonformatter.curiousconcept.com)

Per risolvere eventuali problemi relativi alle API di inserimento in streaming, consultate questa [pagina](https://docs.adobe.com/content/help/it-IT/experience-platform/ingestion/streaming/troubleshooting.html).
