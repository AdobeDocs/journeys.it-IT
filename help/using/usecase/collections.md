---
product: adobe campaign
solution: Journey Orchestration
title: Trasmettere dinamicamente le raccolte utilizzando azioni personalizzate
description: Invio di un messaggio tramite Campaign v7/v8
exl-id: 8832d306-5842-4be5-9fb9-509050fcbb01
source-git-commit: 358fddd8e5c2ca80532ff2b74dc9627ffdc8837e
workflow-type: tm+mt
source-wordcount: '424'
ht-degree: 4%

---


# Trasmettere dinamicamente le raccolte utilizzando azioni personalizzate{#passing-collection}

Puoi passare una raccolta in parametri di azioni personalizzati che verranno compilati dinamicamente in fase di esecuzione. Sono supportati due tipi di raccolte:

* raccolte semplici: array di tipi di dati semplici, ad esempio con listString:

   ```
   {
    "deviceTypes": [
        "android",
        "ios"
    ]
   }
   ```

* raccolte di oggetti: un array di oggetti JSON, ad esempio:

   ```
   {
   "products":[
      {
         "id":"productA",
         "name":"A",
         "price":20.1
      },
      {
         "id":"productB",
         "name":"B",
         "price":10.0
      },
      {
         "id":"productC",
         "name":"C",
         "price":5.99
      }
    ]
   }
   ```

## Limitazioni  {#limitations}

* Le matrici nidificate di oggetti all&#39;interno di un array di oggetti non sono attualmente supportate. Esempio:

   ```
   {
   "products":[
     {
        "id":"productA",
        "name":"A",
        "price":20,
        "locations": [{"name": "Paris"}, {"name": "London"}]
     },
    ]
   }
   ```
* Per testare le raccolte utilizzando la modalità di test, è necessario utilizzare la modalità di visualizzazione del codice. La modalità di visualizzazione del codice non è attualmente supportata per gli eventi aziendali. Puoi inviare una raccolta solo con un singolo elemento.

## Procedura generale {#general-procedure}

In questa sezione utilizzeremo il seguente esempio di payload JSON. Matrice di oggetti con un campo costituito da una raccolta semplice.

```
{
  "ctxt": {
    "products": [
      {
        "id": "productA",
        "name": "A",
        "price": 20.1,
        "color":"blue",
        "locations": [
          "Paris",
          "London"
        ]
      },
      {
        "id": "productB",
        "name": "B",
        "price": 10.99
      }
    ]
  }
}
```

È possibile vedere che &quot;products&quot; è una matrice di due oggetti. È necessario disporre di almeno un oggetto.

1. Crea l&#39;azione personalizzata. Consulta [questa pagina](../action/about-custom-action-configuration.md).

1. In **[!UICONTROL Action parameters]** incolla l’esempio JSON. La struttura visualizzata è statica: quando si incolla il payload, tutti i campi sono definiti come costanti.

   ![](../assets/uc-collection-1.png)

1. Se necessario, regola i tipi di campo. I seguenti tipi di campi sono supportati per le raccolte: listString, listInteger, listDecimal, listBoolean, listDateTime, listDateTimeOnly, listDateOnly, listObject

   >[!NOTE]
   >
   >Il tipo di campo viene dedotto automaticamente in base all’esempio di payload.

1. Se si desidera passare gli oggetti in modo dinamico, è necessario impostarli come variabili. In questo esempio impostiamo &quot;products&quot; come variabile. Tutti i campi oggetto inclusi nell’oggetto vengono impostati automaticamente sulle variabili.

   >[!NOTE]
   >
   >Il primo oggetto dell’esempio di payload viene utilizzato per definire i campi.

1. Per ciascun campo, definisci l’etichetta che verrà visualizzata nell’area di lavoro del percorso.

   ![](../assets/uc-collection-2.png)

1. Crea il percorso e aggiungi l’azione personalizzata creata. Consulta [questa pagina](../building-journeys/using-custom-actions.md).

1. In **[!UICONTROL Action parameters]** definisci il parametro array (&quot;products&quot; nel nostro esempio) utilizzando l’editor di espressioni avanzate.

   ![](../assets/uc-collection-3.png)

1. Per ciascuno dei campi oggetto seguenti, digitare il nome di campo corrispondente dallo schema XDM di origine. Se i nomi sono identici, ciò non è necessario. Nel nostro esempio, dobbiamo solo definire &quot;product id&quot; e &quot;color&quot;.

   ![](../assets/uc-collection-4.png)

Per il campo array, è inoltre possibile utilizzare l’editor di espressioni avanzate per eseguire la manipolazione dei dati. Nell’esempio seguente, utilizziamo il [filter](../functions/functionfilter.md) e [intersecare](../functions/functionintersect.md) funzioni:

![](../assets/uc-collection-5.png)

## Casi particolari{#examples}

Per tipi e array eterogenei di array, l&#39;array viene definito con il tipo listAny. È possibile mappare solo singoli elementi, ma non è possibile modificare la matrice in variabili.

![](../assets/uc-collection-heterogeneous.png)

Esempio di tipo eterogeneo:

```
{
    "data_mixed-types": [
        "test",
        "test2",
        null,
        0
    ]
}
```

Esempio di array:

```
{
    "data_multiple-arrays": [
        [
            "test",
            "test1",
            "test2"
        ]
    ]
}
```

**Argomenti correlati**

[Utilizzare azioni personalizzate](../building-journeys/using-custom-actions.md)
