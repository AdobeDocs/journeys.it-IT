---
product: adobe campaign
title: Tipi di dati
description: Informazioni sui tipi di dati nelle espressioni avanzate
feature: Journeys
role: Data Engineer
level: Experienced
exl-id: 343f61b8-2315-4971-8b2b-6aa815bd9ced
source-git-commit: 5225045f02fb1b2a8505756d9d7f6f60a32b3ed6
workflow-type: tm+mt
source-wordcount: '637'
ht-degree: 6%

---

# Tipi di dati {#concept_gp3_rj5_dgb}

Tecnicamente, una costante contiene sempre un tipo di dati. Nell’espressione letterale viene specificato solo il valore . Il tipo di dati può essere dedotto dal valore (ad esempio stringa, numero intero, decimale e così via). Per casi specifici, come l’ora della data, utilizziamo funzioni dedicate per la rappresentazione.

Le sezioni seguenti forniscono informazioni sulle diverse espressioni del tipo di dati e sulla relativa rappresentazione.

## string {#string}

**Descrizione**

Sequenza comune di caratteri. Non ha dimensioni specifiche, tranne quella implicita che proviene dall&#39;ambiente, come la quantità di memoria disponibile.

Formato JSON: Stringa

Formato di serializzazione: UTF-8

**Rappresentanza letterale**

```json
"<value>"
```

```json
'<value>'
```

**Esempio**

```json
"hello world"
```

```json
'hello world'
```

## numero intero {#integer}

**Descrizione**

Valore intero da -2^63 a 2^63-1.

Formato JSON: Numero

**Rappresentanza letterale**

```json
<integer value>
```

**Esempio**

```json
42
```

## decimal {#decimal}

**Descrizione**

Numero decimale. Rappresenta un valore mobile:

* valore finito positivo maggiore di tipo doppio, (2-2^-52)x2^1023
* valore normale positivo più piccolo del tipo doppio, 2-1022
* valore positivo minore diverso da zero di tipo doppio, 2 p-1074

Formato JSON: Numero

Formato di serializzazione: utilizzo di &#39;.&#39; come separatore decimale.

**Rappresentanza letterale**

```json
<integer value>.<integer value>
```

**Esempio**

```json
3.14
```

## booleano {#boolean}

**Descrizione**

Valore booleano scritto in minuscolo: true o false

Formato JSON: Booleano

**Rappresentanza letterale**

```json
true
```

```json
false
```

**Esempio**

```json
true
```

## dateOnly {#date-only}

**Descrizione**

Rappresenta una data senza un fuso orario, visualizzata come un giorno di un mese per un anno.

È una descrizione della data, come utilizzata per i compleanni.

Formato JSON: Stringa.

Il formato è: AAAA-MM-GG (ISO-8601), ad esempio: &quot;2021-03-11&quot;.

Può essere incapsulato in una funzione toDateOnly.

Utilizza DateTimeForsubject ISO_LOCAL_DATE_TIME per deserializzare e serializzare il valore. [Ulteriori informazioni](https://datatracker.ietf.org/doc/html/rfc3339#section-5.6)

**Rappresentanza letterale**

```json
date("<dateOnly in ISO-8601 format>")  
```

**Esempio**

```json
date("2021-02-19")
```

## dateTimeOnly {#date-time-only}

**Descrizione**

Rappresenta un’ora di data senza un fuso orario, visualizzata come anno-mese-giorno-ora-minuto-secondo-millisecondi.

Formato JSON: Stringa.

Non memorizza o rappresenta un fuso orario. Invece, è una descrizione della data, come utilizzato per i compleanni, combinato con l&#39;ora locale come visto su un orologio a muro.

Non può rappresentare un istante sulla linea temporale senza informazioni aggiuntive, ad esempio un offset o un fuso orario.

Può essere incapsulato in una funzione toDateTimeOnly .

Formato di serializzazione: Formato data-ora offset esteso ISO-8601.

Utilizza DateTimeForsubject ISO_LOCAL_DATE_TIME per deserializzare e serializzare il valore. [Ulteriori informazioni](https://docs.oracle.com/javase/8/docs/api/java/time/format/DateTimeFormatter.html#ISO_LOCAL_DATE_TIME&quot;)

**Rappresentanza letterale**

```json
date("<dateTimeOnly in ISO-8601 format>")  
```

**Esempi**

```json
date("2021-02-19T00.00.000")
date("2021-02-19T00.00")
```

## dateTime {#date-time}

**Descrizione**

Costante di data che considera anche il fuso orario. Rappresenta una data-ora con un offset da UTC.

Può essere visualizzato come un istante nel tempo con le informazioni aggiuntive dell&#39;offset. È un modo per rappresentare un &quot;momento&quot; specifico in un certo luogo del mondo.

Formato JSON: Stringa.

Può essere incapsulato in una funzione toDateTime .

Formato di serializzazione: Formato data-ora offset esteso ISO-8601.

Utilizza DateTimeForsubject ISO_OFFSET_DATE_TIME per deserializzare e serializzare il valore. [Ulteriori informazioni](https://docs.oracle.com/javase/8/docs/api/java/time/format/DateTimeFormatter.html#ISO_OFFSET_DATE_TIME)

È inoltre possibile passare un numero intero che passa un valore epoch. [Maggiori informazioni](https://www.epochconverter.com)

Il fuso orario può essere specificato da un codice di offset o di fuso orario (ad esempio: Europa/Parigi, Z - significato UTC).

**Rappresentanza letterale**

```json
toDateTime("<dateTime in ISO-8601 format>")
```

```json
date("<dateTime in ISO-8601 format>")
```

```json
toDateTime(<integer value of an epoch in milliseconds>)
```

**Esempi**

```json
date("2021-02-19T00.00.000Z")
```

```json
toDateTime("1977-04-22T06:00:00Z")
```

```json
toDateTime("2011-12-03T15:15:30Z")
```

```json
toDateTime("2011-12-03T15:15:30.123Z")
```

```json
toDateTime("2011-12-03T15:15:30.123+02:00")
```

```json
toDateTime("2011-12-03T15:15:30.123-00:20")
```

```json
toDateTime(1560762190189)
```

## durata {#duration}

**Descrizione**

Rappresenta una quantità di tempo basata sul tempo, ad esempio &quot;34,5 secondi&quot;. Modella una quantità o una quantità di tempo in millisecondi.

Le unità temporali supportate sono: millisecondi, secondi, minuti, ore, giorni in cui un giorno è uguale a 24 ore. Gli anni e i mesi non sono supportati in quanto non rappresentano un periodo di tempo fisso.

Formato JSON: Stringa.

Deve essere incapsulato in una funzione toDuration.

Formato di serializzazione: Per deserializzare un ID di fuso orario, utilizza la funzione java java.time.

Duration.parse: i formati accettati sono basati sul formato di durata ISO-8601 PnDTnHnMn.nS con giorni considerati esattamente 24 ore. [Ulteriori informazioni](https://docs.oracle.com/javase/8/docs/api/java/time/Duration.html#parse-java.lang.CharSequence-)

**Rappresentanza letterale**

```json
toDuration("<duration in ISO-8601 format>")
```

```json
toDuration(<duration in milliseconds>)
```

**Esempio**

```json
toDuration("PT5S") -- parses as 5 seconds
```

```json
toDuration(500) -- parses as 500ms
```

```json
toDuration("PT20.345S") -- parses as "20.345 seconds"
```

```json
toDuration("PT15M") -- parses as "15 minutes" (where a minute is 60 seconds)
```

```json
toDuration("PT10H")  -- parses as "10 hours" (where an hour is 3600 seconds)
```

```json
toDuration("P2D") -- parses as "2 days" (where a day is 24 hours or 86400 seconds)
```

```json
toDuration("P2DT3H4M") -- parses as "2 days, 3 hours and 4 minutes"
```

```json
toDuration("P-6H3M") -- parses as "-6 hours and +3 minutes"
```

```json
toDuration("-P6H3M") -- parses as "-6 hours and -3 minutes"
```

```json
toDuration("-P-6H+3M") -- parses as "+6 hours and -3 minutes"
```

## list {#list}

**Descrizione**

Elenco di espressioni separate da virgola che utilizzano parentesi quadre come delimitatori.

Polimorfismo non supportato, pertanto tutte le espressioni contenute nell&#39;elenco devono avere lo stesso tipo.

**Rappresentanza letterale**

```json
[<expression>, <expression>, ... ]
```

**Esempio**

```json
["value1","value2"]
```

```json
[3,5]
```

```json
[toDuration(500),toDuration(800)]
```
