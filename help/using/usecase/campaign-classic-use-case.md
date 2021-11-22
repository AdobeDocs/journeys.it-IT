---
product: adobe campaign
solution: Journey Orchestration
title: Invio di un messaggio tramite Campaign v7/v8
description: Invio di un messaggio tramite Campaign v7/v8
exl-id: 8832d306-5842-4be5-9fb9-509050fcbb01
source-git-commit: 3e78e429bbdfc95bfef74e0f2e2b92f8ff17cfdb
workflow-type: tm+mt
source-wordcount: '394'
ht-degree: 6%

---

# Invio di un messaggio tramite Campaign v7/v8 {#campaign-classic-use-case}

Questo caso d’uso illustra tutti i passaggi necessari per inviare un’e-mail utilizzando l’integrazione con Adobe Campaign Classic v7 e Adobe Campaign v8.

Innanzitutto, creeremo un modello e-mail transazionale in Campaign. Poi, al Journey Orchestration, creeremo l&#39;evento, l&#39;azione e progetteremo il percorso.

Per ulteriori informazioni sull’integrazione di Campaign, consulta le seguenti pagine:

* [Creazione di un’azione Campaign](../action/acc-action.md)
* [Utilizzo dell’azione in un percorso](../building-journeys/using-adobe-campaign-classic.md).

**Adobe Campaign**

È necessario eseguire il provisioning dell’istanza Campaign per questa integrazione. È necessario configurare la funzione Messaggistica transazionale.

1. Accedi alla tua istanza di controllo Campaign.

1. Sotto **Amministrazione** > **Piattaforma** > **Enumerazioni**, seleziona **Tipo evento** Enumerazione (eventType). Crea un nuovo tipo di evento (&quot;percorso-evento&quot;, nel nostro esempio). Sarà necessario utilizzare il nome interno del tipo di evento quando si scriverà il file JSON in un secondo momento.

   ![](../assets/accintegration-uc-1.png)

1. Disconnetti e ricollegati all’istanza per rendere effettiva la creazione.

1. Sotto **Centro messaggi** > **Modelli di messaggio transazionali**, crea un nuovo modello e-mail in base al tipo di evento creato in precedenza.

   ![](../assets/accintegration-uc-2.png)

1. Progetta il tuo modello. In questo esempio, utilizziamo la personalizzazione sul nome del profilo e sul numero dell’ordine. Il nome si trova nell’origine dati Adobe Experience Platform e il numero dell’ordine è un campo dell’evento Journey Orchestration. Assicurati di utilizzare i nomi di campo corretti in Campaign.

   ![](../assets/accintegration-uc-3.png)

1. Pubblica il modello transazionale.

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

1. Innanzitutto, devi creare un evento. Accertati di includere il campo &quot;purchaseOrderNumber&quot;.

   ![](../assets/accintegration-uc-5.png)

1. Devi quindi creare, in Journey Orchestration, un’azione corrispondente al modello di Campaign. In **Tipo di azione** a discesa, seleziona **Adobe Campaign Classic**.

   ![](../assets/accintegration-uc-6.png)

1. Fai clic sul pulsante **Campo payload** e incolla il JSON creato in precedenza.

   ![](../assets/accintegration-uc-7.png)

1. Per l’indirizzo e-mail e i due campi di personalizzazione, modifica **Costante** a **Variabile**.

   ![](../assets/accintegration-uc-8.png)

1. Ora crea un nuovo percorso e inizia con l’evento creato in precedenza.

   ![](../assets/accintegration-uc-9.png)

1. Aggiungi l’azione e mappa ogni campo nel campo corretto del Journey Orchestration.

   ![](../assets/accintegration-uc-10.png)

1. Aggiungi un **Fine** e verifica il percorso.

   ![](../assets/accintegration-uc-11.png)

1. Ora puoi pubblicare il tuo percorso.
