---
product: adobe campaign
solution: Journey Orchestration
title: Operatori
description: Informazioni sugli operatori nelle espressioni avanzate
translation-type: tm+mt
source-git-commit: 20498e89eb9c95dd19a11e42150a0bbf67024f67
workflow-type: tm+mt
source-wordcount: '531'
ht-degree: 5%

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

## Logica  {#logical}

### e

**Espressione letterale**

```<expression1> and <expression2>```

&lt;espressione1> e &lt;espressione2> devono essere entrambi booleani. Il risultato è booleano.

**Esempio**

```3.14 > 2 and 3.15 < 1```

### o

**Espressione letterale**

```<expression1> or <expression2>```

&lt;espressione1> e &lt;espressione2> devono essere entrambi booleani. Il risultato è booleano.

**Esempio**

```3.14 > 2 or 3.15 < 1```

### not

**Espressione letterale**

```not <expression>```

&lt;espressione> deve essere booleana. Il risultato è booleano.

**Esempio**

```not 3.15 < 1```

## Confronto {#comparison}

### è null

**Espressione letterale**

```<expression> is null```

Il risultato è booleano.

Il valore null indica che l&#39;espressione non ha alcun valore valutato.

**Esempio**

```@{BarBeacon.location} is null```

### non è null

**Espressione letterale**

```<expression> is not null```

Il risultato è booleano.

Il valore null indica che l&#39;espressione non ha alcun valore valutato.

**Esempio**

```@ is not null```

### ha valore null

**Espressione letterale**

```<expression> has null```

&lt;espressione> deve essere un elenco. Il risultato è booleano.

Utile per identificare che un elenco contiene almeno un valore null.

**Esempio**

```["foo", "bar", null] has null``` restituisce true.

```["foo", "bar", ""] has null``` restituisce false perché &quot;&quot; non è considerato come null.

### ==

**Espressione letterale**

```<expression1> == <expression2>```

&lt;espressione1> e &lt;espressione2> devono avere lo stesso tipo di dati. Il risultato è booleano.

**Esempio**

```3.14 == 42```

```"foo" == "bar"```

### !=

**Espressione letterale**

```<expression1> != <expression2>```

&lt;espressione1> e &lt;espressione2> devono avere lo stesso tipo di dati. Il risultato è booleano.

**Esempio**

```3.14 != 42```

```"foo" != "bar"```

### >

**Espressione letterale**

```<expression1> > <expression2>```

È possibile confrontare datetime con Datetime.

Datetimeonly può essere confrontato con Datetimeonly.

È possibile confrontare numeri interi o decimali con numeri interi o decimali.

Qualsiasi altra combinazione è vietata.

Il risultato è booleano.

**Esempio**

```3.14 > 42```

### >=

**Espressione letterale**

```<expression1> >= <expression2>```

È possibile confrontare datetime con Datetime.

Datetimeonly può essere confrontato con Datetimeonly.

È possibile confrontare numeri interi o decimali con numeri interi o decimali.

Qualsiasi altra combinazione è vietata.

Il risultato è booleano.

**Esempio**

```42 >= 3.14```

### &lt;

**Espressione letterale**

```<expression1> < <expression2>```

È possibile confrontare datetime con Datetime.

Datetimeonly può essere confrontato con Datetimeonly.

È possibile confrontare numeri interi o decimali con numeri interi o decimali.

Qualsiasi altra combinazione è vietata.

Il risultato è booleano.

**Esempio**

```42 < 3.14```

### &lt;=

**Espressione letterale**

```<expression1> <= <expression2>```

È possibile confrontare datetime con Datetime.

Datetimeonly può essere confrontato con Datetimeonly.

È possibile confrontare numeri interi o decimali con numeri interi o decimali.

Qualsiasi altra combinazione è vietata.

Il risultato è booleano.

**Esempio**

```42 <= 3.14```

## Aritmetica {#arithmetic}

### +

**Espressione letterale**

```<expression1> + <expression2>```

Entrambe le espressioni devono essere numeriche (numero intero o decimale).

Il risultato è anche numerico.

**Esempio**

```1 + 2``` return 3

### -

**Espressione letterale**

```<expression1> - <expression2>```

Entrambe le espressioni devono essere numeriche (numero intero o decimale).

Il risultato è anche numerico.

**Esempio**

```2 - 1``` return 1

### /

**Espressione letterale**

```<expression1> / <expression2>```

Entrambe le espressioni devono essere numeriche (numero intero o decimale).

Il risultato è anche numerico.

&lt;espressione2> non deve essere uguale a 0 (restituisce 0).

**Esempio**

```4 / 2``` return 2

### *

**Espressione letterale**

```<expression1> * <expression2>```

Entrambe le espressioni devono essere numeriche (numero intero o decimale).

Il risultato è anche numerico.

**Esempio**

```3 * 4``` return 12

### %

**Espressione letterale**

```<expression1> % <expression2>```

Entrambe le espressioni devono essere numeriche (numero intero o decimale).

Il risultato è anche numerico.

**Esempio**

```3 % 2``` restituisce 1.

## Matematica {#math}

### è numerico

**Espressione letterale**

```<expression> is numeric```

Il tipo di espressione è integer o decimal.

**Esempio**

```@ is numeric```

### is integer

**Espressione letterale**

```<expression> is integer```

Il tipo di espressione è integer.

**Esempio**

```@ is integer```

### è decimal

**Espressione letterale**

```<expression> is decimal```

Il tipo di espressione è decimale.

**Esempio**

```@ is decimal```

## Stringa {#string}

### +

**Espressione letterale**

```<string> + <expression>```

```<expression> + <string>```

Conconcatenano due espressioni.

Un&#39;espressione deve essere una stringa concatenata.

**Esempio**

```"the current time is " + (now())``` restituisce &quot;l&#39;ora corrente è 2019-09-23T09:30:06.693Z&quot;

```(now()) + " is the current time"``` restituisce &quot;2019-09-23T09:30:06.693Z è l&#39;ora corrente&quot;

```"a" + "b" + "c" + 1234``` restituisce &quot;abc1234&quot;.

## Data {#date}

### +

**Espressione letterale**

```<expression + <duration>```

Aggiungi una durata a dateTime, dateTimeOnly o a una durata.

**Esempio**

```toDateTime("2011-12-03T15:15:30Z") + toDuration("PT15M")``` restituisce 2011-12-03T15:30:30Z

```toDateTimeOnly("2011-12-03T15:15:30") + toDuration("PT15M")``` restituisce 2011-12-03T15:30:30

```now() + toDuration("PT1H")``` restituisce un dataTime (con fuso orario UTC) un&#39;ora dopo dall&#39;ora corrente

```toDuration("PT1H") + toDuration("PT1H")``` restituisce PT2H
