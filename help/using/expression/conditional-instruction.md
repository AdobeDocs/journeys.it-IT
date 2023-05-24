---
product: adobe campaign
title: Istruzione condizionale (if, then, else)
description: Informazioni sull’istruzione condizionale
feature: Journeys
role: Data Engineer
level: Experienced
exl-id: 48fb4944-5b78-4ccd-9b9b-ffe0719e7c21
source-git-commit: 9c33474a72542b6ad1d1ae0854622dfd7575f2d9
workflow-type: tm+mt
source-wordcount: '161'
ht-degree: 0%

---

# Istruzione condizionale (if, then, else) {#section_cdz_lsk_w3b}

L’istruzione condizionale (if, then, else) è supportata nell’editor avanzato. Consente di definire espressioni più complesse. È composto dai seguenti elementi:

* **[!UICONTROL if]**: la condizione da valutare per prima.
* **[!UICONTROL then]**: l’espressione da valutare nel caso in cui il risultato della valutazione della condizione sia vero.
* **[!UICONTROL else]**: l’espressione da valutare se il risultato della valutazione della condizione è falso.

>[!NOTE]
>
>Sono necessarie parentesi intorno a tutte le espressioni.

```json
if  (<expression1>)
then
   (<expression2>)
else
   (<expression3>)
```

`<expression1>` deve restituire un **booleano**.

`<expression2>` e `<expression3>` deve avere lo stesso tipo o tipi compatibili. Le firme supportate e i tipi restituiti sono:

```json
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
listDateOnly,listDateOnly : listDateOnly
listDecimal,listDecimal : listDecimal
listInteger,listInteger : listInteger
listString,listString : listString
```

**Utilizzo**

L’istruzione condizionale ti consente di ottimizzare il flusso di lavoro del percorso riducendo il numero di attività relative alle condizioni. Ad esempio, all’interno della stessa attività di azione, puoi specificare due alternative per la definizione di un campo utilizzando una sola espressione di condizione.

Esempio per un’attività di azione (per un campo che prevede una stringa come risultato dell’istruzione condizionale):

```json
if (startWithIgnoreCase(@{eventiOSPushPermissionAllowed.device.model}, 'iPad') or startWithIgnoreCase(@{eventiOSPushPermissionAllowed.device.model}, 'iOS'))
then
   ('apns')
else
   ('fcm')
```
