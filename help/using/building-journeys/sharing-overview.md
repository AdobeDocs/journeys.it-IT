---
product: adobe campaign
title: Panoramica sulla condivisione delle fasi del percorso
description: Panoramica sulla condivisione delle fasi del percorso
feature: Journeys
role: User
level: Intermediate
exl-id: 95ca5fdb-38b7-47a0-b1a9-b1b26bf8e5f5
source-git-commit: 69471a36b113e04a7bb0953a90977ad4020299e4
workflow-type: tm+mt
source-wordcount: '518'
ht-degree: 3%

---

# Panoramica sulla condivisione delle fasi del percorso{#sharing-overview}


>[!CAUTION]
>
>**Ricerca di Adobe Journey Optimizer**? Fai clic [qui](https://experienceleague.adobe.com/it/docs/journey-optimizer/using/ajo-home){target="_blank"} per la documentazione di Journey Optimizer.
>
>
>_Questa documentazione fa riferimento ai materiali Journey Orchestration legacy che sono stati sostituiti da Journey Optimizer. Contatta il team del tuo account in caso di domande sull&#39;accesso a Journey Orchestration o Journey Optimizer._


[!DNL Journey Orchestration] invia automaticamente i dati sulle prestazioni del percorso a Adobe Experience Platform in modo che possano essere combinati con altri dati a scopo di analisi.

>[!NOTE]
>
>Questa funzione viene attivata per impostazione predefinita su tutte le istanze per gli eventi dei passaggi di percorso. Non è possibile modificare o aggiornare gli schemi e i set di dati creati durante il provisioning per gli eventi dei passaggi. Per impostazione predefinita, questi schemi e set di dati sono in modalità di sola lettura.

Ad esempio, hai impostato un percorso che invia più e-mail. Questa funzionalità consente di combinare i dati di [!DNL Journey Orchestration] con i dati di eventi a valle, ad esempio il numero di conversioni avvenute, il livello di coinvolgimento nel sito Web o il numero di transazioni avvenute nello store. Le informazioni sul percorso possono essere combinate con i dati presenti sul Adobe Experience Platform, provenienti da altre proprietà digitali o da proprietà offline, per offrire una visione più completa delle prestazioni.

[!DNL Journey Orchestration] crea automaticamente gli schemi e i flussi necessari nei set di dati in Adobe Experience Platform per ogni passaggio che un singolo utente compie in un percorso. Un evento di passaggio corrisponde a un singolo spostamento da un nodo all’altro in un percorso. Ad esempio, in un percorso che ha un evento, una condizione e un’azione, vengono inviati al Adobe Experience Platform tre eventi di passaggio.

L’elenco dei campi XDM passati è completo. Alcuni contengono codici generati dal sistema, altri nomi descrittivi leggibili dall&#39;utente. Alcuni esempi includono l’etichetta dell’attività del percorso o lo stato del passaggio: quante volte un’azione è scaduta o è terminata in errore.

>[!CAUTION]
>
>Non è possibile attivare i set di dati per il servizio profilo in tempo reale. Verificare che l&#39;interruttore **[!UICONTROL Profile]** sia disattivato.

I percorsi inviano i dati così come si verificano, in modo streaming. Puoi eseguire query su questi dati utilizzando Query Service. È possibile connettersi a Customer Journey Analytics o ad altri strumenti di business intelligence per visualizzare i dati relativi a questi passaggi.

Vengono creati i seguenti schemi:

* Schema evento passaggio percorso per [!DNL Journey Orchestration] - evento passaggio Percorso associato a un metadati Percorso.
* Schema percorso con campi Percorso per [!DNL Journey Orchestration] - Metadati Percorso per descrivere i Percorsi.

![](../assets/sharing1.png)

![](../assets/sharing2.png)

Vengono passati i seguenti set di dati:

* Eventi passaggio percorso
* Percorsi

![](../assets/sharing3.png)

Gli elenchi dei campi XDM passati a Adobe Experience Platform sono descritti qui:

* [Elenco dei campi evento del passaggio](../building-journeys/sharing-field-list.md)
* [Campi evento del passaggio precedente](../building-journeys/sharing-legacy-fields.md)


## Integrazione con Customer Percorsi Analysis{#integration-cja}

Gli eventi dei passaggi di Journey Orchestration possono essere collegati ad altri set di dati in [Adobe Customer Journey Analytics](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-overview/cja-overview.html?lang=it). Di seguito è riportato il flusso di lavoro generale:

* Customer Journey Analytics acquisisce il set di dati &quot;Evento passaggio Percorso&quot;.
* Il campo **profileID** nello &quot;Schema evento passaggio di Percorso per Journey Orchestration&quot; associato è definito come campo Identity. In Customer Journey Analytics, puoi quindi collegare questo set di dati a qualsiasi altro set di dati con lo stesso valore dell’identificatore basato su persona.
* Se desideri utilizzare questo set di dati in Customer Journey Analytics, per l&#39;analisi del percorso cross-channel, consulta questa [documentazione](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-usecases/cross-channel.html).
