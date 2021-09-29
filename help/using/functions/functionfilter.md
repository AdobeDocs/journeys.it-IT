---
product: adobe campaign
title: filter
description: Scopri la funzione fister
feature: Journeys
role: Data Engineer
level: Experienced
exl-id: 19a4b7f8-5636-4b8f-b81f-28ff7da99671
source-git-commit: 729ee71e063ae73c7c10f20bb3a410c43cb75faf
workflow-type: tm+mt
source-wordcount: '109'
ht-degree: 10%

---

# filter{#filter}

Restituisce un listObject con oggetti con l’attributo chiave corrispondente a uno dei valori chiave specificati.

## Categoria

Elenco

## Sintassi della funzione

`filter(<parameters>)`

## Parametri

| Parametro | Tipo | Descrizione |
|-----------|------------------|------------------|
| listToFilter | listObject | elenco di oggetti da filtrare. Deve essere un riferimento di campo. |
| keyAttributeName | stringa | nome dell’attributo negli oggetti dell’elenco specificato, utilizzato come chiave per il filtraggio |
| keyValueList | list | array di valori chiave per il filtro |

## Firme e tipi restituiti

`filter(listObject, string, listString)`

`filter(listObject, string, listInteger)`

`filter(listObject, string, listDecimal)`

`filter(listObject, string, listDateTime)`

`filter(listObject, string, listDateTimeOnly)`

`filter(listObject, string, listDateOnly)`

`filter(listObject, string, listDuration)`

`filter(listObject, string, listBoolean)`

Restituisce un valore listObject.

## Esempi

Ecco un esempio di payload trasmesso in un evento in arrivo &quot;myevent&quot;:

```
"productListItems": [{
   "id": "product1",
   "name": "the product 1",
   "price": 20
},{
   "id": "product2",
   "name": "the product 2",
   "price": 30
},{
   "id": "product3",
   "name": "the product 3",
   "price": 50
}]
```

È possibile utilizzare la seguente espressione:

```
filter(
 @{myevent.productListItems},
 id", 
 ["product2", "product3", "product4"]
)
```

Restituisce un listObject contenente i due oggetti con &quot;product2&quot; e &quot;product3&quot; come id.
