---
product: adobe campaign
solution: Journey Orchestration
title: Operatori
description: Informazioni sugli operatori nelle espressioni avanzate
translation-type: tm+mt
source-git-commit: 062b4648e2eb3a4270f9c09e4478d541209e1247
workflow-type: tm+mt
source-wordcount: '435'
ht-degree: 6%

---



# Operatori {#concept_wd5_pj5_dgb}

Esistono due tipi di operatori: operatori unari e operatori binari. Ci sono operatori unari a sinistra e operatori unari a destra.

```
    // left-hand unary operators
    <operator> <operand> // operand is an expression
    not (@{LobbyBeacon.endUserIDs._experience.emailid.id}=="example@adobe.com")

    // right-hand unary operators
    <operand> <operator> // operand is an expression
    @{LobbyBeacon.endUserIDs._experience.emailid.id} is not null

    // binary operators
    <operand1> <operator> <operand2>
    (@{LobbyBeacon.endUserIDs._experience.emailid.id}=="example1@adobe.com") or
    (@{LobbyBeacon.endUserIDs._experience.emailid.id}=="example2@adobe.com")
```

Elenco degli operatori supportati:

## Logica {#logical}

### e

```
<expression1> and <expression2>
```

&lt;espressione1> e &lt;espressione2> devono essere entrambi booleani. Il risultato è booleano.

Esempio:

```
3.14 > 2 and 3.15 < 1
```

### o



```
<expression1> or <expression2>
```

&lt;espressione1> e &lt;espressione2> devono essere entrambi booleani. Il risultato è booleano.

Esempio:

```
3.14 > 2 or 3.15 < 1
```

### not



```
not <expression>
```

&lt;expression> deve essere booleano. Il risultato è booleano.

Esempio:

```
not 3.15 < 1
```

## Confronto {#comparison}

### è null



```
<expression> is null
```

Il risultato è booleano.

Il valore null indica che l&#39;espressione non ha alcun valore valutato.

Esempio:

```
@{BarBeacon.location} is null
```

### non è null



```
<expression> is not null
```

Il risultato è booleano.

Il valore null indica che l&#39;espressione non ha alcun valore valutato.

Esempio:

```
@ is not null
```

### ha valore null



```
<expression> has null
```

&lt;expression> deve essere un elenco. Il risultato è booleano.

Utile per identificare che un elenco contiene almeno un valore null.

Esempio:

```
["foo", "bar", null] has null --  returns true.
```

```
["foo", "bar", ""] has null -- returns false because "" is not considered as null.
```

### ==



```
<expression1> == <expression2>
```

&lt;espressione1> e &lt;espressione2> devono avere lo stesso tipo di dati. Il risultato è booleano.

Esempio:

```
3.14 == 42
```

```
"foo" == "bar"
```

### !=



```
<expression1> != <expression2>
```

&lt;espressione1> e &lt;espressione2> devono avere lo stesso tipo di dati. Il risultato è booleano.

Esempio:

```
3.14 != 42
```

```
"foo" != "bar"
```

### >



```
<expression1> > <expression2>
```

È possibile confrontare datetime con Datetime.

Datetimeonly può essere confrontato con Datetimeonly.

È possibile confrontare numeri interi o decimali con numeri interi o decimali.

Qualsiasi altra combinazione è vietata.

Il risultato è booleano.

Esempio:

```
3.14 > 42
```

### >=



```
<expression1> >= <expression2>
```

È possibile confrontare datetime con Datetime.

Datetimeonly può essere confrontato con Datetimeonly.

È possibile confrontare numeri interi o decimali con numeri interi o decimali.

Qualsiasi altra combinazione è vietata.

Il risultato è booleano.

Esempio:

```
42 >= 3.14
```

### &lt;>



```
<expression1> < <expression2>
```

È possibile confrontare datetime con Datetime.

Datetimeonly può essere confrontato con Datetimeonly.

È possibile confrontare numeri interi o decimali con numeri interi o decimali.

Qualsiasi altra combinazione è vietata.

Il risultato è booleano.

Esempio:

```
42 < 3.14
```

### &lt;>



```
<expression1> <= <expression2>
```

È possibile confrontare datetime con Datetime.

Datetimeonly può essere confrontato con Datetimeonly.

È possibile confrontare numeri interi o decimali con numeri interi o decimali.

Qualsiasi altra combinazione è vietata.

Il risultato è booleano.

Esempio:

```
42 <= 3.14
```

## Aritmetica {#arithmetic}

### +



```
<expression1> + <expression2>
```

Entrambe le espressioni devono essere numeriche (numero intero o decimale).

Il risultato è anche numerico.

Esempio:

```
1 + 2 -- returns 3
```

### -



```
<expression1> - <expression2>
```

Entrambe le espressioni devono essere numeriche (numero intero o decimale).

Il risultato è anche numerico.

Esempio:

```
2 - 1 -- returns 1
```

### /



```
<expression1> / <expression2>
```

Entrambe le espressioni devono essere numeriche (numero intero o decimale).

Il risultato è anche numerico.

&lt;expression2> non deve essere uguale a 0 (restituisce 0).

Esempio:

```
4 / 2 -- returns 2
```

### *



```
<expression1> * <expression2>
```

Entrambe le espressioni devono essere numeriche (numero intero o decimale).

Il risultato è anche numerico.

Esempio:

```
3 * 4 -- returns 12
```

### %



```
<expression1> % <expression2>
```

Entrambe le espressioni devono essere numeriche (numero intero o decimale).

Il risultato è anche numerico.

Esempio:

```
3 % 2 -- returns 1.
```

## Matematica {#math}

### è numerico



```
<expression> is numeric
```

Il tipo di espressione è integer o decimal.

Esempio:

```
@ is numeric
```

### is integer



```
<expression> is integer
```

Il tipo di espressione è integer.

Esempio:

```
@ is integer
```

### è decimal



```
<expression> is decimal
```

Il tipo di espressione è decimale.

Esempio:

```
@ is decimal
```

## Stringa {#string}

### +



```
<string> + <expression>
```

```
<expression> + <string>
```

Conconcatenano due espressioni.

Un&#39;espressione deve essere una stringa concatenata.

Esempio:

```
"the current time is " + (now()) -- returns "the current time is 2019-09-23T09:30:06.693Z"
```

```
(now()) + " is the current time" -- returns "2019-09-23T09:30:06.693Z is the current time"
```

```
"a" + "b" + "c" + 1234 -- returns "abc1234".
```

## Data {#date}

### +



```
<expression + <duration>
```

Aggiungi una durata a dateTime, dateTimeOnly o a una durata.

Esempio:

```
toDateTime("2011-12-03T15:15:30Z") + toDuration("PT15M") -- returns 2011-12-03T15:30:30Z
```

```
toDateTimeOnly("2011-12-03T15:15:30") + toDuration("PT15M") -- returns 2011-12-03T15:30:30
```

```
now() + toDuration("PT1H") -- returns a dateTime (with UTC time zone) one hour later from current time
```

```
toDuration("PT1H") + toDuration("PT1H") -- returns  PT2H
```
