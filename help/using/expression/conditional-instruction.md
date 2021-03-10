---
product: adobe campaign
solution: Journey Orchestration
title: Istruzione condizionale (if, then, else)
description: Scopri le istruzioni condizionali
feature: Percorsi
role: Ingegnere dati
level: Esperienza
translation-type: tm+mt
source-git-commit: ab19cc5a3d998d1178984c5028b1ba650d3e1292
workflow-type: tm+mt
source-wordcount: '165'
ht-degree: 0%

---


# Istruzione condizionale (if, then, else) {#section_cdz_lsk_w3b}

L’istruzione condizionale (se, then, else) è supportata nell’editor avanzato. Consente di definire espressioni più complesse. È composto dai seguenti elementi:

* **[!UICONTROL if]**: la condizione da valutare per prima.
* **[!UICONTROL then]**: l&#39;espressione da valutare nel caso in cui il risultato della valutazione della condizione sia vero.
* **[!UICONTROL else]**: l’espressione da valutare nel caso in cui il risultato della valutazione della condizione sia falso.

>[!NOTE]
>
>Sono necessarie parentesi intorno a tutte le espressioni.

```
if  (<expression1>)
then
   (<expression2>)
else
   (<expression3>)
```

`<expression1>` deve restituire un valore  **booleano**.

`<expression2>` e  `<expression3>` devono avere lo stesso tipo o tipi compatibili. Le firme supportate e i tipi restituiti sono:

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

L’istruzione condizionale ti consente di ottimizzare il flusso di lavoro del percorso riducendo il numero di attività di condizione. Ad esempio, all’interno della stessa attività di azione, puoi specificare due alternative per una definizione di campo utilizzando una sola espressione di condizione.

Esempio per un’attività di azione (per un campo che richiede una stringa come risultato dell’istruzione condizionale):

```
if (startWithIgnoreCase(@{eventiOSPushPermissionAllowed.device.model}, 'iPad') or startWithIgnoreCase(@{eventiOSPushPermissionAllowed.device.model}, 'iOS'))
then
   ('apns')
else
   ('fcm')
```
