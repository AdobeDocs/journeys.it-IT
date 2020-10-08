---
title: Istruzione condizionale (if, then, else)
description: Informazioni sulle istruzioni condizionali
page-status-flag: never-activated
uuid: 269d590c-5a6d-40b9-a879-02f5033863fc
contentOwner: sauviat
audience: rns
content-type: reference
topic-tags: journeys
discoiquuid: 5df34f55-135a-4ea8-afc2-f9427ce5ae7b
translation-type: tm+mt
source-git-commit: b852c08a488a1bec02b8b31a1fccf1a8773b99af
workflow-type: tm+mt
source-wordcount: '161'
ht-degree: 0%

---


# Istruzione condizionale (if, then, else) {#section_cdz_lsk_w3b}

L&#39;istruzione condizionale (se, quindi, else) è supportata nell&#39;editor avanzato. Consente di definire espressioni più complesse. È composta dai seguenti elementi:

* **[!UICONTROL if]**: la condizione da valutare per prima.
* **[!UICONTROL then]**: l&#39;espressione da valutare nel caso in cui il risultato della valutazione della condizione sia vero.
* **[!UICONTROL else]**: l&#39;espressione da valutare nel caso in cui il risultato della valutazione della condizione sia falso.

>[!NOTE]
>
>Le parentesi sono richieste intorno a tutte le espressioni.

```
if  (<expression1>)
then
   (<expression2>)
else
   (<expression3>)
```

`<expression1>` deve restituire un **valore booleano**.

`<expression2>` e `<expression3>` devono avere lo stesso tipo o tipi compatibili. Le firme supportate e i tipi restituiti sono:

```
boolean,boolean : boolean
dateTime,dateTime : dateTime
dateTimeOnly,dateTimeOnly : dateTimeOnly
decimal,integer : decimal
integer,decimal : integer
integer,decimal : decimal
duration,duration : duration
string,string : string
listBoolean,listBoolean : listBoolean
listDateTime,listDateTime : listDateTime
listDateTimeOnly,listDateTimeOnly : listDateTimeOnly
listDecimal,listDecimal : listDecimal
listInteger,listInteger : listInteger
listString,listString : listString
```

**Utilizzo**

L&#39;istruzione condizionale consente di ottimizzare il flusso di lavoro del viaggio riducendo il numero di attività delle condizioni. Ad esempio, all&#39;interno della stessa attività di azione, è possibile specificare due alternative per una definizione di campo utilizzando una sola espressione di condizione.

Esempio di un&#39;attività di azione (per un campo che prevede una stringa come risultato dell&#39;istruzione condizionale):

```
if (startWithIgnoreCase(@{eventiOSPushPermissionAllowed.device.model}, 'iPad') or startWithIgnoreCase(@{eventiOSPushPermissionAllowed.device.model}, 'iOS'))
then
   ('apns')
else
   ('fcm')
```
