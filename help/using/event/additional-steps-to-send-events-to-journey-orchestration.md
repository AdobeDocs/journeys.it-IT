---
product: adobe campaign
solution: Journey Orchestration
title: Passaggi aggiuntivi per l’invio di eventi al Journey Orchestration
description: Scopri ulteriori passaggi per l’invio di eventi al Journey Orchestration
feature: Percorsi
role: Professionista
level: Intermedio
translation-type: tm+mt
source-git-commit: ab19cc5a3d998d1178984c5028b1ba650d3e1292
workflow-type: tm+mt
source-wordcount: '327'
ht-degree: 7%

---



# Passaggi aggiuntivi per l’invio di eventi a [!DNL Journey Orchestration] {#concept_xrz_n1q_y2b}

>[!NOTE]
>
>Durante la creazione di un evento, [!DNL Journey Orchestration] genera automaticamente un ID per questo evento. Il sistema che preme l’evento non deve generare un ID, ma deve utilizzare quello disponibile nell’anteprima del payload. Consulta [questa pagina](../event/previewing-the-payload.md).

Per configurare gli eventi da inviare a **[!UICONTROL Streaming Ingestion APIs]** e da utilizzare in [!DNL Journey Orchestration], segui questi passaggi:

1. Ottieni l’URL di ingresso dalle API Adobe Experience Platform (consulta [API Streaming Ingestion](https://docs.adobe.com/content/help/it-IT/experience-platform/ingestion/streaming/overview.html)).
1. Copia il payload dall’anteprima del payload nel menu **[!UICONTROL Event]** . Consulta [questa pagina](../event/defining-the-payload-fields.md).

Devi quindi configurare il sistema di dati che invia gli eventi alle API Streaming Ingestion utilizzando il payload copiato:

1. Imposta una chiamata API di POST all’URL delle API Streaming Ingestion (chiamata ingresso).
1. Utilizza il payload copiato da [!DNL Journey Orchestration] nel corpo (&quot;sezione dati&quot;) della chiamata API alle API Streaming Ingestion. Vedi sotto per un esempio
1. Stabilisci dove ottenere tutte le variabili presenti nel payload. Esempio: se l’evento deve trasmettere l’indirizzo , il payload incollato mostrerà &quot;indirizzo&quot;: &quot;string&quot;. La &quot;stringa&quot; deve essere sostituita dalla variabile che popolerà automaticamente il valore corretto, l’e-mail della persona a cui inviare un messaggio. Nell’anteprima del payload, nella sezione **[!UICONTROL Header]** verranno compilati automaticamente molti valori che dovrebbero facilitare il lavoro dell’utente.
1. Seleziona &quot;application/json&quot; come tipo di corpo.
1. Passa il tuo ID organizzazione IMS nell’intestazione utilizzando la chiave &quot;x-gw-ims-org-id&quot;. Per il valore , utilizza il tuo ID organizzazione IMS (&quot;XXX@AdobeOrg&quot;).

Ecco un esempio di evento API Streaming Ingestion:

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

Per facilitare l’identificazione del punto in cui incollare la parte &quot;dati&quot;, puoi utilizzare uno strumento di visualizzazione JSON, ad esempio [https://jsonformatter.curiousconcept.com](https://jsonformatter.curiousconcept.com)

Per risolvere i problemi relativi alle API Streaming Ingestion, fai riferimento a questa [pagina](https://docs.adobe.com/content/help/it-IT/experience-platform/ingestion/streaming/troubleshooting.html).
