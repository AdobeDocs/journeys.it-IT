---
product: adobe campaign
title: Operatori
description: Informazioni sugli operatori nelle espressioni avanzate
feature: Journeys
role: Data Engineer
level: Experienced
exl-id: fd86b6ab-76cf-4b35-9e87-f441e914f20b
source-git-commit: a0b6ab595bc16a75aa5a56a858900418e2381ab9
workflow-type: tm+mt
source-wordcount: '457'
ht-degree: 7%

---

# Operatori {#concept_wd5_pj5_dgb}

Esistono due tipi di operatori: operatori unari e operatori binari. Ci sono operatori unari a sinistra e operatori unari a destra.

```json
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

## Note importanti{#important-notes}

* Quando si utilizza una moltiplicazione (`*`), entrambi i campi operazione devono avere lo stesso tipo, intero o decimale. Esempio :
   * l&#39;esempio seguente è corretto: `3.0 * 4.0`
   * `3 * 4.0` porterà a un errore

## Logica  {#logical}

### e

```json
<expression1> and <expression2>
```

Entrambi &lt;expression1> e &lt;expression2> deve essere booleano. Il risultato è booleano.

Esempio:

```json
3.14 > 2 and 3.15 < 1
```

### oppure



```json
<expression1> or <expression2>
```

Entrambi &lt;expression1> e &lt;expression2> deve essere booleano. Il risultato è booleano.

Esempio:

```json
3.14 > 2 or 3.15 < 1
```

### not



```json
not <expression>
```

&lt;expression> deve essere booleano. Il risultato è booleano.

Esempio:

```json
not 3.15 < 1
```

## Confronto {#comparison}

### è nullo



```json
<expression> is null
```

Il risultato è booleano.

Il valore null indica che l&#39;espressione non ha alcun valore valutato.

Esempio:

```json
@{BarBeacon.location} is null
```

### non è null



```json
<expression> is not null
```

Il risultato è booleano.

Il valore null indica che l&#39;espressione non ha alcun valore valutato.

Esempio:

```json
@ is not null
```

### ha null



```json
<expression> has null
```

&lt;expression> deve essere un elenco. Il risultato è booleano.

Utile per identificare che un elenco contiene almeno un valore null.

Esempio:

```json
["foo", "bar", null] has null --  returns true.
```

```json
["foo", "bar", ""] has null -- returns false because "" is not considered as null.
```

### ==



```json
<expression1> == <expression2>
```

Entrambi &lt;expression1> e &lt;expression2> deve avere lo stesso tipo di dati. Il risultato è booleano.

Esempio:

```json
3.14 == 42
```

```json
"foo" == "bar"
```

### !=



```json
<expression1> != <expression2>
```

Entrambi &lt;expression1> e &lt;expression2> deve avere lo stesso tipo di dati. Il risultato è booleano.

Esempio:

```json
3.14 != 42
```

```json
"foo" != "bar"
```

### >



```json
<expression1> > <expression2>
```

Datetime può essere confrontato con Datetime.

Datetimeonly può essere confrontato con Datetimeonly.

È possibile confrontare sia un numero intero che un decimale con un numero intero o decimale.

Qualsiasi altra combinazione è vietata.

Il risultato è booleano.

Esempio:

```json
3.14 > 42
```

### >=



```json
<expression1> >= <expression2>
```

Datetime può essere confrontato con Datetime.

Datetimeonly può essere confrontato con Datetimeonly.

È possibile confrontare sia un numero intero che un decimale con un numero intero o decimale.

Qualsiasi altra combinazione è vietata.

Il risultato è booleano.

Esempio:

```json
42 >= 3.14
```

### &lt;



```json
<expression1> < <expression2>
```

Datetime può essere confrontato con Datetime.

Datetimeonly può essere confrontato con Datetimeonly.

È possibile confrontare sia un numero intero che un decimale con un numero intero o decimale.

Qualsiasi altra combinazione è vietata.

Il risultato è booleano.

Esempio:

```json
42 < 3.14
```

### &lt;=



```json
<expression1> <= <expression2>
```

Datetime può essere confrontato con Datetime.

Datetimeonly può essere confrontato con Datetimeonly.

È possibile confrontare sia un numero intero che un decimale con un numero intero o decimale.

Qualsiasi altra combinazione è vietata.

Il risultato è booleano.

Esempio:

```json
42 <= 3.14
```

## Aritmetica {#arithmetic}

### +



```json
<expression1> + <expression2>
```

Entrambe le espressioni devono essere numeriche (integer o decimali).

Il risultato è anche numerico.

Esempio:

```json
1 + 2 -- returns 3
```

### -



```json
<expression1> - <expression2>
```

Entrambe le espressioni devono essere numeriche (integer o decimali).

Il risultato è anche numerico.

Esempio:

```json
2 - 1 -- returns 1
```

### /



```json
<expression1> / <expression2>
```

Entrambe le espressioni devono essere numeriche (integer o decimali).

Il risultato è anche numerico.

&lt;expression2> deve essere diverso da 0 (restituisce 0).

Esempio:

```json
4 / 2 -- returns 2
```

### *



```json
<expression1> * <expression2>
```

Entrambe le espressioni devono essere numeriche (integer o decimali).

Il risultato è anche numerico.

Esempio:

```json
3 * 4 -- returns 12
```

### %



```json
<expression1> % <expression2>
```

Entrambe le espressioni devono essere numeriche (integer o decimali).

Il risultato è anche numerico.

Esempio:

```json
3 % 2 -- returns 1.
```

## Matematica {#math}

### è numerico



```json
<expression> is numeric
```

Il tipo di espressione è integer o decimale.

Esempio:

```json
@ is numeric
```

### è un numero intero



```json
<expression> is integer
```

Il tipo di espressione è integer.

Esempio:

```json
@ is integer
```

### è decimale



```json
<expression> is decimal
```

Il tipo di espressione è decimale.

Esempio:

```json
@ is decimal
```

## Stringa {#string}

### +



```json
<string> + <expression>
```

```json
<expression> + <string>
```

Conconcatena due espressioni.

Un&#39;espressione deve essere una stringa concatenata.

Esempio:

```json
"the current time is " + (now()) -- returns "the current time is 2019-09-23T09:30:06.693Z"
```

```json
(now()) + " is the current time" -- returns "2019-09-23T09:30:06.693Z is the current time"
```

```json
"a" + "b" + "c" + 1234 -- returns "abc1234".
```

## Data {#date}

### +



```json
<expression> + <duration>
```

Aggiungi una durata a un dateTime, a un dateTimeOnly o a una durata.

Esempio:

```json
toDateTime("2011-12-03T15:15:30Z") + toDuration("PT15M") -- returns 2011-12-03T15:30:30Z
```

```json
toDateTimeOnly("2011-12-03T15:15:30") + toDuration("PT15M") -- returns 2011-12-03T15:30:30
```

```json
now() + toDuration("PT1H") -- returns a dateTime (with UTC time zone) one hour later from current time
```

```json
toDuration("PT1H") + toDuration("PT1H") -- returns  PT2H
```
