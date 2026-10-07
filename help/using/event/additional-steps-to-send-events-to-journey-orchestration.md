---
product: adobe campaign
title: Passaggi aggiuntivi per l’invio di eventi a Journey Orchestration
description: Scopri i passaggi aggiuntivi per l’invio di eventi a Journey Orchestration
feature: Journeys
role: User
level: Intermediate
exl-id: 11e337c6-5e05-4898-9953-b6b821af8fd1
product_v2:
  - id: cf67d108-ecf9-4fde-af49-3a3c39083bc8
    internal-label: Journey Orchestration
feature_v2:
  - id: 7de3230f-9523-5ba5-8d5c-2313288b27ef
    internal-label: Journeys
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
level_v2:
  - id: b5a62a22-46f7-4f0d-b151-3fc640bef588
    internal-label: Intermediate
source-git-commit: 255cd6677e7c9ebff63ea9a1028a042c19e63ecc
workflow-type: tm+mt
source-wordcount: '379'
ht-degree: 17%
---
# Passaggi aggiuntivi per inviare eventi a [!DNL Journey Orchestration] {#concept_xrz_n1q_y2b}



>[!CAUTION]
>
>**Stai cercando Adobe Journey Optimizer**? Fai clic [qui](https://experienceleague.adobe.com/it/docs/journey-optimizer/using/ajo-home){target="_blank"} per la documentazione di Journey Optimizer.
>
>
>_Questa documentazione fa riferimento ai precedenti materiali su Journey Orchestration, che è stato sostituito da Journey Optimizer. In caso di domande sull’accesso a Journey Orchestration o Journey Optimizer, contatta il team del tuo account._


>[!NOTE]
>
>Durante la creazione di un evento, [!DNL Journey Orchestration] genera automaticamente un ID per questo evento. Il sistema che trasmette l’evento non deve generare un ID, deve utilizzare quello disponibile nell’anteprima del payload. Consulta [questa pagina](../event/previewing-the-payload.md).

Per configurare gli eventi da inviare a **[!UICONTROL Streaming Ingestion APIs]** e utilizzare in [!DNL Journey Orchestration], è necessario eseguire la procedura seguente:

1. Ottieni l&#39;URL di ingresso dalle API di Adobe Experience Platform (vedi [API Streaming Ingestion](https://experienceleague.adobe.com/docs/experience-platform/ingestion/streaming/overview.html?lang=it)).
1. Copiare il payload dall&#39;anteprima del payload nel menu **[!UICONTROL Event]**. Consulta [questa pagina](../event/defining-the-payload-fields.md).

Quindi devi configurare il sistema di dati che invia gli eventi alle API Streaming Ingestion utilizzando il payload copiato:

1. Imposta una chiamata API POST all’URL delle API Streaming Ingestion (chiamata entrata).
1. Utilizza il payload copiato da [!DNL Journey Orchestration] nel corpo (&quot;sezione dati&quot;) della chiamata API alle API Streaming Ingestion. Vedi di seguito per un esempio
1. Determina dove ottenere tutte le variabili presenti nel payload. Esempio: se l’evento deve trasmettere l’indirizzo, il payload incollato mostrerà &quot;address&quot;: &quot;string&quot;. &quot;string&quot; deve essere sostituito dalla variabile che compilerà automaticamente il valore corretto, l’e-mail della persona a cui inviare un messaggio. Tieni presente che nell&#39;anteprima del payload, nella sezione **[!UICONTROL Header]**, vengono compilati automaticamente molti valori che dovrebbero facilitare il tuo lavoro.
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

Per facilitare l&#39;identificazione del punto in cui incollare la parte &quot;data&quot;, puoi utilizzare uno strumento di visualizzazione JSON come [https://jsonformatter.curiousconcept.com](https://jsonformatter.curiousconcept.com)

Per risolvere i problemi relativi alle API Streaming Ingestion, fai riferimento a questa [pagina](https://experienceleague.adobe.com/docs/experience-platform/ingestion/streaming/troubleshooting.html?lang=it).
