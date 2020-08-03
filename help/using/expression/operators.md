---
title: Operatori
description: Informazioni sugli operatori nelle espressioni avanzate
page-status-flag: never-activated
uuid: 269d590c-5a6d-40b9-a879-02f5033863fc
contentOwner: sauviat
audience: rns
content-type: reference
topic-tags: journeys
discoiquuid: 5df34f55-135a-4ea8-afc2-f9427ce5ae7b
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 239efa9592b011c70e2fc331df8f33820301253d
workflow-type: tm+mt
source-wordcount: '618'
ht-degree: 2%

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

## Logica

<table>
<thead>
<tr ><th  >Operatore</th><th  >Espressione letterale</th><th  >Esempio</th></tr>
</thead>
<tbody>
<tr >&gt;<td>e</td><td><p><pre>&lt;espressione1&gt; e &lt;espressione2&gt;</pre></p>&lt;espressione1&gt; e &lt;espressione2&gt; devono essere entrambi booleani. Il risultato è booleano.</td><td><pre>3.14 &gt; 2 e 3.15 &lt; 1</pre></td></tr>
<tr ><td>o</td><td><p><pre>&lt;espressione1&gt; o &lt;espressione2&gt;</pre></p><p>&lt;espressione1&gt; e &lt;espressione2&gt; devono essere entrambi booleani.</p><p> Il risultato è booleano.</p></td><td><p><pre>3.14 &gt; 2 o 3.15 &lt; 1</pre></p></td></tr>
<tr ><td>not</td><td><p><pre>not &lt;espressione&gt;</pre></p><p>&lt;espressione&gt; deve essere booleana.</p><p> Il risultato è booleano.</p></td><td><pre>not 3.15 &lt; 1</pre></td></tr>
</tbody>
  </table>

## Confronto

<table>
<thead>
<tr ><th  >Operatore</th><th  >Espressione letterale </th><th  >Esempio</th></tr>
</thead>
<tbody><tr ><td>è null</td><td><p><pre>&lt;espressione&gt; è null</pre></p><p>Il risultato è booleano.</p><p>Il valore null indica che l'espressione non ha alcun valore valutato.</p></td><td><pre>@{BarBeacon.location} è null</pre></td></tr>
<tr ><td>non è null</td><td><p><pre>&lt;espressione&gt; non è null</pre></p><p>Il risultato è booleano.</p><p>Il valore null indica che l'espressione non ha alcun valore valutato.</p></td><td><pre>@ non è null</pre></td></tr>
<tr ><td>ha valore null</td><td><p><pre>&lt;espressione&gt; ha valore null</pre>&lt;espressione&gt; deve essere un elenco.</p><p>Il risultato è booleano.</p><p>Utile per identificare che un elenco contiene almeno un valore null.</p></td><td><p><pre>["foo", "bar", null] ha null</pre></p>return true<p><pre>["foo", "bar", ""] ha null</pre></p> restituisce false perché "" non è considerato come null.</td></tr>
<tr ><td>==</td><td><p><pre>&lt;espressione1&gt; == &lt;espressione2&gt;</pre></p><p>&lt;espressione1&gt; e &lt;espressione2&gt; devono avere lo stesso tipo di dati.</p><p> Il risultato è booleano.</p></td><td><pre>3.14 == 42</pre><br /><pre>"foo" == "bar"</pre></td></tr>
<tr ><td>!=</td><td><p><pre>&lt;espressione1&gt; != &lt;espressione2&gt;</pre></p><p> &lt;espressione1&gt; e &lt;espressione2&gt; devono avere lo stesso tipo di dati.</p><p> Il risultato è booleano.</p></td><td><pre>3.14 != 42</pre><br /><pre>"foo"!= "bar"</pre></td></tr>
<tr ><td>&gt;</td><td><p><pre>&lt;espressione1&gt; &gt; &lt;espressione2&gt;</pre></p><p>È possibile confrontare datetime con Datetime.</p><p>Datetimeonly può essere confrontato con Datetimeonly.</p><p>È possibile confrontare numeri interi o decimali con numeri interi o decimali.</p><p>Qualsiasi altra combinazione è vietata.</p><p>Il risultato è booleano.</p></td><td><pre>3.14 &gt; 42</pre></td></tr>
<tr ><td>&gt;=</td><td><p><pre>&lt;espressione1&gt; &gt;= &lt;espressione2&gt;</pre></p><p>È possibile confrontare datetime con Datetime.</p><p>Datetimeonly può essere confrontato con Datetimeonly.</p><p>È possibile confrontare numeri interi o decimali con numeri interi o decimali.</p><p>Qualsiasi altra combinazione è vietata.</p><p>Il risultato è booleano.</p></td><td><pre>42 &gt;= 3.14</pre></td></tr>
<tr ><td>&lt;</td><td><p><pre>&lt;espressione1&gt; &lt; &lt;espressione2&gt;</pre></p><p>È possibile confrontare datetime con Datetime.</p><p>Datetimeonly può essere confrontato con Datetimeonly.</p><p>È possibile confrontare numeri interi o decimali con numeri interi o decimali.</p><p>Qualsiasi altra combinazione è vietata.</p><p>Il risultato è booleano.</p></td><td><pre>42 &lt; 3.14</pre></td></tr>
<tr ><td>&lt;=</td><td><p><pre>&lt;espressione1&gt; &lt;= &lt;espressione2&gt;</pre></p><p>È possibile confrontare datetime con Datetime.</p><p>Datetimeonly può essere confrontato con Datetimeonly.</p><p>È possibile confrontare numeri interi o decimali con numeri interi o decimali.</p><p>Qualsiasi altra combinazione è vietata.</p><p>Il risultato è booleano.</p></td><td><pre>42 &lt;= 3.14</pre></td></tr>
</tbody>
</table>

## Aritmetica

<table>
<thead>
<tr ><th  >Operatore</th><th>Espressione letterale </th><th  >Esempio</th></tr>
</thead>
<tbody><tr ><td>+</td><td><p><pre>&lt;espressione1&gt; + &lt;espressione2&gt;</pre></p><p>Entrambe le espressioni devono essere numeriche (numero intero o decimale). </p><p>Il risultato è anche numerico.</p></td><td><p><p><pre>1 + 2</pre></p></p><br /><p>Restituisce 3</p></td></tr>
<tr ><td>-</td><td><p><pre>&lt;espressione1&gt; - &lt;espressione2&gt;</pre></p><p> Entrambe le espressioni devono essere numeriche (numero intero o decimale).</p><p> Il risultato è anche numerico.</p></td><td><p><pre>2 - 1</pre></p>Restituisce 1</td></tr>
<tr ><td>/</td><td><p><pre>&lt;espressione1&gt; / &lt;espressione2&gt;</pre></p><p>Entrambe le espressioni devono essere numeriche (numero intero o decimale). </p><p>Il risultato è anche numerico.</p><p>&lt;espressione2&gt; non deve essere uguale a 0 (restituisce 0).</p></td><td><p><pre>4 / 2</pre></p>Restituisce 2</td></tr>
<tr ><td>*</td><td><p><pre>&lt;espressione1&gt; * &lt;espressione2&gt;</pre></p><p> Entrambe le espressioni devono essere numeriche (numero intero o decimale). </p><p>Il risultato è anche numerico.</p></td><td><p><pre>3 * 4</pre></p>Restituisce 12</td></tr>
<tr ><td>%</td><td><p><pre>&lt;espressione1&gt; % &lt;espressione2&gt;</pre></p><p>Entrambe le espressioni devono essere numeriche (numero intero o decimale).</p><p> Il risultato è anche numerico.</p></td><td><p><pre>3 % 2</pre></p>Restituisce 1.</td></tr>
</tbody>
</table>

## Matematica

<table>
<thead>
<tr ><th  >Operatore</th><th  >Espressione letterale </th><th  >Esempio</th></tr>
</thead>
<tbody><tr ><td>è numerico</td><td><p><pre>&lt;espressione&gt; è numerica</pre></p><p>Il tipo di espressione è integer o decimal.</p></td><td><pre>@ è numerico</pre></td></tr>
<tr ><td>is integer</td><td><p><pre>&lt;espressione&gt; è un numero intero</pre></p><p>Il tipo di espressione è integer.</p></td><td><pre>@ è un numero intero</pre></td></tr>
<tr ><td>è decimal</td><td><p><pre>&lt;espressione&gt; è decimale</pre></p><p>Il tipo di espressione è decimale.</p></td><td><pre>@ è decimale</pre></td></tr>

## Stringa

<table>
<thead>
<tr ><th  >Operatore</th><th  >Espressione letterale </th><th  >Esempio</th></tr>
</thead>
<tbody><tr ><td>+</td><td><p><pre>&lt;stringa&gt; + &lt;espressione&gt;</pre></p><p><pre>&lt;espressione&gt; + &lt;stringa&gt;</pre></p><p>Conconcatenano due espressioni. </p><p>Un'espressione deve essere una stringa concatenata.</p></td><td><p><pre>"l'ora corrente è " + (now()</pre></p> Restituisce "l'ora corrente è 2019-09-23T09:30:06.693Z"<p><pre>(now()) + " è l'ora corrente"</pre></p>Restituisce "2019-09-23T09:30:06.693Z è l'ora corrente"<p><pre>"a" + "b" + "c" + 1234</pre></p> Restituisce "abc1234".</td></tr>
</tbody>
</table>

## Data

<table>
<thead>
<tr ><th  >Operatore</th><th  >Espressione letterale </th><th  >Esempio</th></tr>
</thead>
<tbody>
<tr ><td>+</td><td><p><pre>&lt;espressione + &lt;durata&gt;</pre></p><p>Aggiungi una durata a dateTime, dateTimeOnly o a una durata.</p></td><td><p><pre>toDateTime("2011-12-03T15:15:30Z")</pre></p><p><pre> + toDuration("PT15M")</pre></p><p>Restituisce 2011-12-03T15:30:30Z</p><p><pre>toDateTimeOnly("2011-12-03T15:15:30")</pre></p><p><pre> + toDuration("PT15M")</pre></p>Restituisce 2011-12-03T15:30:30<p><pre>now() + toDuration("PT1H")</pre></p><p>Restituisce un dataTime (con fuso orario UTC) un'ora dopo dall'ora corrente</p><p><pre>toDuration("PT1H") + toDuration("PT1H")</pre></p><p>Restituisce PT2H</p></td></tr>
</tbody>
</table>