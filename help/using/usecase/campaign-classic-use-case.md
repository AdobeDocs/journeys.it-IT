---
product: adobe campaign
solution: Journey Orchestration
title: Invio di un messaggio tramite Campaign v7/v8
description: Invio di un messaggio tramite Campaign v7/v8
exl-id: 717a927a-4357-4058-a626-1b69f4bb46bc
source-git-commit: a9a129b1949d64c4a412d3ea4002b32e3563ea96
workflow-type: tm+mt
source-wordcount: '394'
ht-degree: 6%

---

# Invio di un messaggio tramite Campaign v7/v8 {#campaign-classic-use-case}

Questo caso d’uso illustra tutti i passaggi necessari per inviare un’e-mail utilizzando l’integrazione con Adobe Campaign Classic v7 e Adobe Campaign v8.

Creeremo prima un modello e-mail transazionale in Campaign. Quindi, in Journey Orchestration, creeremo l&#39;evento, l&#39;azione e progetteremo il percorso.

Per ulteriori informazioni sull’integrazione di Campaign, consulta le seguenti pagine:

* [Creazione di un’azione Campaign](../action/acc-action.md)
* [Utilizzo dell&#39;azione in un percorso](../building-journeys/using-adobe-campaign-classic.md).

**Adobe Campaign**

È necessario eseguire il provisioning della tua istanza di Campaign per questa integrazione. È necessario configurare la funzione di messaggistica transazionale.

1. Accedi all’istanza di controllo Campaign.

1. In **Amministrazione** > **Piattaforma** > **Enumerazioni**, selezionare l&#39;enumerazione **Tipo evento** (eventType). Crea un nuovo tipo di evento (&quot;percorsi-event&quot;, nel nostro esempio). Sarà necessario utilizzare il nome interno del tipo di evento per scrivere il file JSON in un secondo momento.

   ![](../assets/accintegration-uc-1.png)

1. Disconnettiti e riconnettiti all’istanza per rendere effettiva la creazione.

1. In **Centro messaggi** > **Modelli di messaggi transazionali**, crea un nuovo modello di e-mail in base al tipo di evento creato in precedenza.

   ![](../assets/accintegration-uc-2.png)

1. Progetta il modello. In questo esempio, utilizziamo la personalizzazione sul nome del profilo e sul numero di ordine. Il nome si trova nell’origine dati Adobe Experience Platform e il numero di ordine è un campo del nostro evento di Journey Orchestration. Assicurati di utilizzare i nomi di campo corretti in Campaign.

   ![](../assets/accintegration-uc-3.png)

1. Publish il modello transazionale.

   ![](../assets/accintegration-uc-4.png)

1. Ora devi scrivere il payload JSON corrispondente al modello.

```
{
     "channel": "email",
     "eventType": "journey-event",
     "email": "Email address",
     "ctx": {
          "firstName": "First name", "purchaseOrderNumber": "Purchase order number"
     }
}
```

* Per il canale, devi digitare &quot;email&quot;.
* Per eventType, utilizza il nome interno del tipo di evento creato in precedenza.
* L’indirizzo e-mail sarà una variabile e potrai quindi digitare qualsiasi etichetta.
* In ctx, i campi di personalizzazione sono anche variabili.

**Journey Orchestration**

1. Innanzitutto, devi creare un evento. Assicurarsi di includere il campo &quot;purchaseOrderNumber&quot;.

   ![](../assets/accintegration-uc-5.png)

1. In seguito devi creare, nel Journey Orchestration, un’azione corrispondente al modello Campaign. Nell&#39;elenco a discesa **Tipo azione**, selezionare **Adobe Campaign Classic**.

   ![](../assets/accintegration-uc-6.png)

1. Fai clic sul campo **Payload** e incolla il JSON creato in precedenza.

   ![](../assets/accintegration-uc-7.png)

1. Per l&#39;indirizzo e-mail e i due campi di personalizzazione, modifica **Costante** in **Variabile**.

   ![](../assets/accintegration-uc-8.png)

1. Ora crea un nuovo percorso e inizia con l’evento creato in precedenza.

   ![](../assets/accintegration-uc-9.png)

1. Aggiungi l’azione e mappa ogni campo sul campo corretto nel Journey Orchestration.

   ![](../assets/accintegration-uc-10.png)

1. Aggiungi un&#39;attività **End** e verifica il percorso.

   ![](../assets/accintegration-uc-11.png)

1. Ora puoi pubblicare il percorso.
