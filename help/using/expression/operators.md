---
product: adobe campaign
title: Operatori
description: Scopri gli operatori nelle espressioni avanzate
feature: Journeys
role: Data Engineer
level: Experienced
exl-id: fd86b6ab-76cf-4b35-9e87-f441e914f20b
source-git-commit: a0b6ab595bc16a75aa5a56a858900418e2381ab9
workflow-type: tm+mt
source-wordcount: '459'
ht-degree: 6%

---

# Operatori {#concept_wd5_pj5_dgb}

Esistono due tipi di operatori: operatori unari e operatori binari. Sono disponibili operatori unari di sinistra e operatori unari di destra.

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

* Quando si utilizza una moltiplicazione (`*`), entrambi i campi dell&#39;operazione devono avere lo stesso tipo, intero o decimale. Esempio:
   * l&#39;esempio seguente è corretto: `3.0 * 4.0`
   * `3 * 4.0` genererà un errore

## Logico  {#logical}

### e

```json
<expression1> and <expression2>
```

Sia &lt;espressione1> che &lt;espressione2> devono essere booleani. Il risultato è booleano.

Esempio:

```json
3.14 > 2 and 3.15 < 1
```

### oppure



```json
<expression1> or <expression2>
```

Sia &lt;espressione1> che &lt;espressione2> devono essere booleani. Il risultato è booleano.

Esempio:

```json
3.14 > 2 or 3.15 < 1
```

### non



```json
not <expression>
```

&lt;espressione> deve essere booleano. Il risultato è booleano.

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

Nullo significa che l’espressione non ha un valore valutato.

Esempio:

```json
@{BarBeacon.location} is null
```

### non è nullo



```json
<expression> is not null
```

Il risultato è booleano.

Nullo significa che l’espressione non ha un valore valutato.

Esempio:

```json
@ is not null
```

### ha valore null



```json
<expression> has null
```

&lt;espressione> deve essere un elenco. Il risultato è booleano.

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

Sia &lt;espressione1> che &lt;espressione2> devono avere lo stesso tipo di dati. Il risultato è booleano.

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

Sia &lt;espressione1> che &lt;espressione2> devono avere lo stesso tipo di dati. Il risultato è booleano.

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

Sia il numero intero che il numero decimale possono essere confrontati con il numero intero o il numero decimale.

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

Sia il numero intero che il numero decimale possono essere confrontati con il numero intero o il numero decimale.

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

Sia il numero intero che il numero decimale possono essere confrontati con il numero intero o il numero decimale.

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

Sia il numero intero che il numero decimale possono essere confrontati con il numero intero o il numero decimale.

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

Entrambe le espressioni devono essere numeriche (numero intero o decimale).

Il risultato è anche numerico.

Esempio:

```json
1 + 2 -- returns 3
```

### -



```json
<expression1> - <expression2>
```

Entrambe le espressioni devono essere numeriche (numero intero o decimale).

Il risultato è anche numerico.

Esempio:

```json
2 - 1 -- returns 1
```

### /



```json
<expression1> / <expression2>
```

Entrambe le espressioni devono essere numeriche (numero intero o decimale).

Il risultato è anche numerico.

&lt;espressione2> non deve essere uguale a 0 (restituisce 0).

Esempio:

```json
4 / 2 -- returns 2
```

### *



```json
<expression1> * <expression2>
```

Entrambe le espressioni devono essere numeriche (numero intero o decimale).

Il risultato è anche numerico.

Esempio:

```json
3 * 4 -- returns 12
```

### %



```json
<expression1> % <expression2>
```

Entrambe le espressioni devono essere numeriche (numero intero o decimale).

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

Il tipo dell&#39;espressione è numero intero o decimale.

Esempio:

```json
@ is numeric
```

### è un numero intero



```json
<expression> is integer
```

Il tipo dell&#39;espressione è un numero intero.

Esempio:

```json
@ is integer
```

### è decimale



```json
<expression> is decimal
```

Il tipo dell&#39;espressione è decimal.

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

Concatena due espressioni.

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

Aggiungere una durata a un valore dateTime, dateTimeOnly o duration.

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
