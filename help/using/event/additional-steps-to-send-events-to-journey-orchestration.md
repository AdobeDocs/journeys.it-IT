---
product: adobe campaign
title: Passaggi aggiuntivi per inviare eventi al Journey Orchestration
description: Scopri i passaggi aggiuntivi per inviare eventi al Journey Orchestration
feature: Journeys
role: User
level: Intermediate
exl-id: 11e337c6-5e05-4898-9953-b6b821af8fd1
source-git-commit: 185c2296a51f58e2092787edcc35ee9e4242bec8
workflow-type: tm+mt
source-wordcount: '319'
ht-degree: 4%

---

# Passaggi aggiuntivi per l’invio di eventi a [!DNL Journey Orchestration] {#concept_xrz_n1q_y2b}

>[!NOTE]
>
>Durante la creazione di un evento, [!DNL Journey Orchestration] genera automaticamente un ID per questo evento. Il sistema che trasmette l’evento non deve generare un ID, deve utilizzare quello disponibile nell’anteprima del payload. Consulta [questa pagina](../event/previewing-the-payload.md).

Per configurare gli eventi da inviare a **[!UICONTROL Streaming Ingestion APIs]** e da utilizzare in [!DNL Journey Orchestration], è necessario seguire questi passaggi:

1. Ottieni l’URL di ingresso dalle API di Adobe Experience Platform (consulta [API Streaming Ingestion](https://experienceleague.adobe.com/docs/experience-platform/ingestion/streaming/overview.html?lang=it)).
1. Copiare il payload dall’anteprima del payload in **[!UICONTROL Event]** menu. Consulta [questa pagina](../event/defining-the-payload-fields.md).

Quindi devi configurare il sistema di dati che invia gli eventi alle API Streaming Ingestion utilizzando il payload copiato:

1. Imposta una chiamata API POST all’URL delle API Streaming Ingestion (chiamata entrata).
1. Utilizza il payload copiato da [!DNL Journey Orchestration] nel corpo (&quot;sezione dati&quot;) della chiamata API alle API Streaming Ingestion. Vedi di seguito per un esempio
1. Determina dove ottenere tutte le variabili presenti nel payload. Esempio: se l’evento deve trasmettere l’indirizzo, il payload incollato mostrerà &quot;address&quot;: &quot;string&quot;. &quot;string&quot; deve essere sostituito dalla variabile che compilerà automaticamente il valore corretto, l’e-mail della persona a cui inviare un messaggio. Nell’anteprima del payload, nella sezione **[!UICONTROL Header]** , vengono compilati automaticamente molti valori che dovrebbero facilitare il tuo lavoro.
1. Seleziona &quot;application/json&quot; come tipo di corpo.
1. Passa l’ID organizzazione IMS nell’intestazione utilizzando la chiave &quot;x-gw-ims-org-id&quot;. Per il valore, utilizza l’ID organizzazione IMS (&quot;XXX@AdobeOrg&quot;).

Ecco un esempio di evento Streaming Ingestion APIs:

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

Per facilitare l’identificazione del punto in cui incollare la parte &quot;dati&quot;, puoi utilizzare uno strumento di visualizzazione JSON come [https://jsonformatter.curiousconcept.com](https://jsonformatter.curiousconcept.com)

Per risolvere i problemi relativi alle API Streaming Ingestion, fai riferimento a [pagina](https://experienceleague.adobe.com/docs/experience-platform/ingestion/streaming/troubleshooting.html).
