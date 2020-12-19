---
product: adobe campaign
solution: Journey Orchestration
title: Tipi di dati
description: Informazioni sui tipi di dati nelle espressioni avanzate
translation-type: tm+mt
source-git-commit: a95b8311aff2d95402afa9b80488ced2a3e6fbba
workflow-type: tm+mt
source-wordcount: '558'
ht-degree: 4%

---


# Tipi di dati {#concept_gp3_rj5_dgb}

Tecnicamente, una costante contiene sempre un tipo di dati. Nell&#39;espressione letterale viene specificato solo il valore. Il tipo di dati può essere ricavato dal valore (ad esempio stringa, numero intero, decimale ecc.). Per casi specifici come l&#39;ora della data, utilizziamo funzioni dedicate per la rappresentazione.

Le sezioni seguenti forniscono informazioni sulle diverse espressioni dei tipi di dati e sulla relativa rappresentazione.

## stringa {#string}

**Descrizione**

Sequenza comune di caratteri. Non ha dimensioni specifiche, tranne quella implicita che proviene dall&#39;ambiente, come la quantità di memoria disponibile.

Formato JSON: Stringa

Formato di serializzazione: UTF-8

**Rappresentazione letterale**

```
"<value>"
```

```
'<value>'
```

**Esempio**

```
"hello world"
```

```
'hello world'
```

## integer {#integer}

**Descrizione**

Valore intero compreso tra -2^63 e 2^63-1.

Formato JSON: Numero

**Rappresentazione letterale**

```
<integer value>
```

**Esempio**

```
42
```

## decimal {#decimal}

**Descrizione**

Numero decimale. Rappresenta un valore mobile:

* valore finito positivo maggiore di tipo doppio, (2-2^-52)x2^1023
* valore normale positivo minimo di tipo doppio, 2-1022
* più piccolo valore positivo diverso da zero di tipo doppio, 2 p-1074

Formato JSON: Numero

Formato di serializzazione: utilizzo di &#39;.&#39; come separatore decimale.

**Rappresentazione letterale**

```
<integer value>.<integer value>
```

**Esempio**

```
3.14
```

## boolean {#boolean}

**Descrizione**

Valore booleano scritto in lettere minuscole: true o false

Formato JSON: Booleano

**Rappresentazione letterale**

```
true
```

```
false
```

**Esempio**

```
true
```

## dateTimeOnly {#date-time-only}

**Descrizione**

Rappresenta un&#39;ora data senza un fuso orario, visualizzata come anno-mese-giorno-ora-minuto-secondo-millisecondo.

Non memorizza né rappresenta un fuso orario. Al contrario, è una descrizione della data, come utilizzato per i compleanni, combinato con l&#39;ora locale come visto su un orologio a muro.

Non può rappresentare un istante sulla linea temporale senza informazioni aggiuntive, ad esempio un offset o un fuso orario.

Formato di serializzazione: Formato data-ora offset esteso ISO-8601.

Utilizza DateTimeForsubject ISO_LOCAL_DATE_TIME per deserializzare e serializzare il valore. [Ulteriori informazioni](https://docs.oracle.com/javase/8/docs/api/java/time/format/DateTimeFormatter.html#ISO_LOCAL_DATE_TIME&quot;)

**Rappresentazione letterale**

```
toDateTimeOnly("<dateTimeOnly in ISO-8601 format>")  
```

## dateTime {#date-time}

**Descrizione**

Costante data e ora che considera anche il fuso orario. Rappresenta una data-ora con un offset dall&#39;UTC.

Può essere visualizzato come un istante nel tempo con le informazioni aggiuntive dell&#39;offset. È un modo per rappresentare un &quot;momento&quot; specifico in un certo luogo del mondo.

Formato JSON: Stringa.

Deve essere racchiuso in una funzione toDateTime.

Formato di serializzazione: Formato data-ora offset esteso ISO-8601.

Utilizza DateTimeForsubject ISO_OFFSET_DATE_TIME per deserializzare e serializzare il valore. [Ulteriori informazioni](https://docs.oracle.com/javase/8/docs/api/java/time/format/DateTimeFormatter.html#ISO_OFFSET_DATE_TIME)

È inoltre possibile passare un numero intero che passa un valore epoch. [Leggi tutto](https://www.epochconverter.com)

Il fuso orario può essere specificato mediante un offset o un codice del fuso orario (ad esempio: Europa/Parigi, Z - significato UTC).

**Rappresentazione letterale**

```
toDateTime("<dateTime in ISO-8601 format>")
```

```
toDateTime(<integer value of an epoch in milliseconds>)
```

**Esempio**

```
toDateTime("1977-04-22T06:00:00Z")
```

```
toDateTime("2011-12-03T15:15:30Z")
```

```
toDateTime("2011-12-03T15:15:30.123Z")
```

```
toDateTime("2011-12-03T15:15:30.123+02:00")
```

```
toDateTime("2011-12-03T15:15:30.123-00:20")
```

```
toDateTime(1560762190189)
```

## durata {#duration}

**Descrizione**

Rappresenta una quantità di tempo basata sul tempo, ad esempio &#39;34,5 secondi&#39;. Il modello mostra una quantità o quantità di tempo in millisecondi.

Le unità temporali supportate sono: millisecondi, secondi, minuti, ore, giorni in cui un giorno equivale a 24 ore. Gli anni e i mesi non sono supportati perché non sono un periodo di tempo fisso.

Formato JSON: Stringa.

Deve essere racchiuso in una funzione toDuration.

Formato di serializzazione: Per deserializzare l’ID di un fuso orario, utilizza la funzione Java java.time.

Duration.parse: i formati accettati si basano sul formato di durata ISO-8601 PnDTnHnMn.nS con giorni considerati esattamente 24 ore. [Ulteriori informazioni](https://docs.oracle.com/javase/8/docs/api/java/time/Duration.html#parse-java.lang.CharSequence-)

**Rappresentazione letterale**

```
toDuration("<duration in ISO-8601 format>")
```

```
toDuration(<duration in milliseconds>)
```

**Esempio**

```
toDuration("PT5S") -- parses as 5 seconds
```

```
toDuration(500) -- parses as 500ms
```

```
toDuration("PT20.345S") -- parses as "20.345 seconds"
```

```
toDuration("PT15M") -- parses as "15 minutes" (where a minute is 60 seconds)
```

```
toDuration("PT10H")  -- parses as "10 hours" (where an hour is 3600 seconds)
```

```
toDuration("P2D") -- parses as "2 days" (where a day is 24 hours or 86400 seconds)
```

```
toDuration("P2DT3H4M") -- parses as "2 days, 3 hours and 4 minutes"
```

```
toDuration("P-6H3M") -- parses as "-6 hours and +3 minutes"
```

```
toDuration("-P6H3M") -- parses as "-6 hours and -3 minutes"
```

```
toDuration("-P-6H+3M") -- parses as "+6 hours and -3 minutes"
```

## elenco {#list}

**Descrizione**

Elenco separato da virgole di espressioni utilizzando le parentesi quadre come delimitatori.

Il polimorfismo non è supportato, pertanto tutte le espressioni contenute nell&#39;elenco devono avere lo stesso tipo.

**Rappresentazione letterale**

```
[<expression>, <expression>, ... ]
```

**Esempio**

```
["value1","value2"]
```

```
[3,5]
```

```
[toDuration(500),toDuration(800)]
```
