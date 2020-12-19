---
product: adobe campaign
solution: Journey Orchestration
title: Passaggi aggiuntivi per l'invio di eventi al Journey Orchestration
description: Ulteriori informazioni sui passaggi per l'invio di eventi al Journey Orchestration
translation-type: tm+mt
source-git-commit: 57dc86d775bf8860aa09300cf2432d70c62a2993
workflow-type: tm+mt
source-wordcount: '323'
ht-degree: 7%

---



# Passaggi aggiuntivi per l&#39;invio di eventi a [!DNL Journey Orchestration] {#concept_xrz_n1q_y2b}

>[!NOTE]
>
>Durante la creazione di un evento, [!DNL Journey Orchestration] genera automaticamente un ID per questo evento. Il sistema che preme l&#39;evento non deve generare un ID, ma deve utilizzare quello disponibile nell&#39;anteprima del payload. Consulta [questa pagina](../event/previewing-the-payload.md).

Per configurare gli eventi da inviare a **[!UICONTROL Streaming Ingestion APIs]** e da utilizzare in [!DNL Journey Orchestration], è necessario eseguire la procedura seguente:

1. Ottenete l&#39;URL di ingresso dalle API Adobe Experience Platform (consultate [Streaming Ingestion APIs](https://docs.adobe.com/content/help/it-IT/experience-platform/ingestion/streaming/overview.html)).
1. Copiate il payload dall&#39;anteprima del payload nel menu **[!UICONTROL Event]**. Consulta [questa pagina](../event/defining-the-payload-fields.md).

Quindi devi configurare il sistema di dati che invia gli eventi alle API Streaming Ingestion utilizzando il payload copiato:

1. Configurate una chiamata API POST all&#39;URL delle API di ingestione dello streaming (chiamata ingresso).
1. Utilizzate il payload copiato da [!DNL Journey Orchestration] nel corpo (&quot;sezione dati&quot;) della chiamata API alle API di ingestione in streaming. Vedere di seguito un esempio
1. Determinare dove ottenere tutte le variabili presenti nel payload. Esempio: se l’evento deve trasmettere l’indirizzo, il payload incollato mostrerà &quot;address&quot;: &quot;string&quot;. &quot;string&quot; deve essere sostituito dalla variabile che popolerà automaticamente il valore corretto, l&#39;e-mail della persona a cui inviare un messaggio. Nell&#39;anteprima del payload, nella sezione **[!UICONTROL Header]**, vengono automaticamente compilati molti valori che dovrebbero facilitare il lavoro.
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

Per facilitare l&#39;identificazione del luogo in cui incollare la parte &quot;dati&quot;, potete utilizzare uno strumento di visualizzazione JSON come [https://jsonformatter.curiousconcept.com](https://jsonformatter.curiousconcept.com)

Per risolvere i problemi relativi alle API di ingestione in streaming, fare riferimento a questa [pagina](https://docs.adobe.com/content/help/it-IT/experience-platform/ingestion/streaming/troubleshooting.html).
