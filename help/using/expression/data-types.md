---
product: adobe campaign
solution: Journey Orchestration
title: Tipi di dati
description: Informazioni sui tipi di dati nelle espressioni avanzate
translation-type: tm+mt
source-git-commit: 57dc86d775bf8860aa09300cf2432d70c62a2993
workflow-type: tm+mt
source-wordcount: '675'
ht-degree: 3%

---


# Tipi di dati {#concept_gp3_rj5_dgb}

Tecnicamente, una costante contiene sempre un tipo di dati. Nell&#39;espressione letterale viene specificato solo il valore. Il tipo di dati può essere ricavato dal valore (ad esempio stringa, numero intero, decimale ecc.). Per casi specifici come l&#39;ora della data, utilizziamo funzioni dedicate per la rappresentazione.

Di seguito è illustrata la rappresentazione delle espressioni dei tipi di dati:

<table>
    <thead>
        <tr>
        <td>Tipo di dati</td>
        <td>Descrizione</td>
        <td>Rappresentazione letterale</td>
        <td>Esempio</td>
        </tr>
    </thead>
    <tbody>
    <tr>
        <td>string</td>
        <td><p>Sequenza comune di caratteri.</p><p>Non ha dimensioni specifiche, tranne quella implicita che proviene dall'ambiente, come la quantità di memoria disponibile.</p><p>Formato JSON: Stringa</p><p>Formato di serializzazione: UTF-8</p></td>
        <td><p>"&lt;value&gt;"</p><p>'&lt;value&gt;'</p></td>
        <td><p><pre>"hello world"</pre></p><p><pre>'hello world'</pre></p></td>
    </tr>
    <tr>
        <td>integer</td>
        <td><p>Valore intero compreso tra -2^63 e 2^63-1.</p><p>Formato JSON: Numero</p></td>
        <td>&lt;valore intero&gt;</td>
        <td><p><pre>42</pre></p></td>
    </tr>
    <tr>
        <td>decimal</td>
        <td><p>Numero decimale.</p><p>Rappresenta un valore mobile:</p>
        <p>- valore finito positivo maggiore di tipo doppio, (2-2^-52)x2^1023</p>
        <p> - valore normale positivo minimo di tipo doppio, 2-1022</p>
        <p> - valore positivo minore diverso da zero di tipo doppio, 2 p-1074</p><p>Formato JSON: Numero</p><p>Formato di serializzazione: utilizzo di '.' come separatore decimale.</p></td>
        <td>&lt;valore intero&gt;.&lt;valore intero&gt;</td>
        <td><p><pre>3.14</pre></p></td>
    </tr>
    <tr>
        <td>boolean</td>
        <td><p>Valore booleano scritto in lettere minuscole: true o false</p><p>Formato JSON: Booleano</p></td>
        <td><p>true</p><p>false</p></td>
        <td><p><pre>true</pre></p></td>
    </tr>
    <tr>
        <td>dateTimeOnly</td>
        <td><p>Rappresenta un'ora data senza un fuso orario, visualizzata come anno-mese-giorno-ora-minuto-secondo-millisecondo.</p><p>Non memorizza né rappresenta un fuso orario.</p><p>Al contrario, è una descrizione della data, come utilizzato per i compleanni, combinato con l'ora locale come visto su un orologio a muro.</p><p>Non può rappresentare un istante sulla linea temporale senza informazioni aggiuntive, ad esempio un offset o un fuso orario.</p><p>Formato di serializzazione: Formato data-ora offset esteso ISO-8601.</p><p>Utilizza DateTimeForsubject.</p><p>ISO_LOCAL_DATE_TIME per deserializzare e serializzare il valore.</p> <a href="https://docs.oracle.com/javase/8/docs/api/java/time/format/DateTimeFormatter.html#ISO_LOCAL_DATE_TIME">Ulteriori informazioni</a>.</td>
        <td><p>toDateTimeOnly("&lt;dateTimeOnly nel formato ISO-8601&gt;")</p></td>
        <td></td>
    </tr>
    <tr>
        <td>dateTime</td>
        <td><p>Costante data e ora che considera anche il fuso orario.</p><p>Rappresenta una data-ora con un offset dall'UTC. Può essere visualizzato come un istante nel tempo con le informazioni aggiuntive dell'offset. </p><p>È un modo per rappresentare un "momento" specifico in un certo luogo del mondo.</p><p>Formato JSON: Stringa.</p><p> Deve essere racchiuso in una funzione toDateTime.</p><p>
        Formato di serializzazione: Formato data-ora offset esteso ISO-8601.</p><p> Utilizza DateTimeForsubject.ISO_OFFSET_DATE_TIME per deserializzare e serializzare il valore.</p> <a href="https://docs.oracle.com/javase/8/docs/api/java/time/format/DateTimeFormatter.html#ISO_OFFSET_DATE_TIME">Ulteriori informazioni</a>. 
        <p>È inoltre possibile passare un numero intero che passa un valore epoch.</p> <a href="https://www.epochconverter.com/">Ulteriori informazioni</a>.</p>
        <p>Il fuso orario può essere specificato mediante un offset o un codice del fuso orario (ad esempio: Europa/Parigi, Z - significato UTC).</p></td>
        <td><p>toDateTime("&lt;dateTime in formato ISO-8601&gt;")</p>
        <p>toDateTime(&lt;valore intero di un'epoch in millisecondi&gt;)</p></td>
        <td><p><pre>toDateTime("1977-04-22T06:00:00Z")</pre></p><p><pre>toDateTime</pre></p><p><pre>("2011-12-03T15:15:30Z")</pre></p><p><pre>toDateTime</pre></p><p><pre>("2011-12-03T15:15:30.123Z")</pre></p><p><pre>toDateTime</pre></p><p><pre>("2011-12-03T15:15:30.123+02:00")</pre></p>
        <p><pre>toDateTime</pre></p><p><pre>("2011-12-03T15:15:30.123-00:20")</pre></p><p><pre>toDateTime(1560762190189)</pre></p></td>
    </tr>
    <tr>
        <td>length</td>
        <td><p>Rappresenta una quantità di tempo basata sul tempo, ad esempio '34,5 secondi'.</p><p> Il modello mostra una quantità o quantità di tempo in millisecondi.</p><p>Le unità temporali supportate sono: millisecondi, secondi, minuti, ore, giorni in cui un giorno equivale a 24 ore.</p><p> Gli anni e i mesi non sono supportati perché non sono un periodo di tempo fisso.</p><p>Formato JSON: Stringa. Deve essere racchiuso in una funzione toDuration.</p><p>Formato di serializzazione: Per deserializzare l’ID di un fuso orario, utilizza la funzione Java java.time.</p><p>Duration.parse: i formati accettati si basano sul formato di durata ISO-8601 PnDTnHnMn.nS con giorni considerati esattamente 24 ore.</p><a href="https://docs.oracle.com/javase/8/docs/api/java/time/Duration.html#parse-java.lang.CharSequence-">Ulteriori informazioni</a>.</td>
        <td><p>toDuration("&lt;durata in formato ISO-8601&gt;")</p><p>toDuration(&lt;durata in millisecondi&gt;)</p></td>
        <td><p><pre>toDuration("PT5S") // 5 secondi</pre></p>
        <p><pre>toDuration(500) // </pre></p>
        <p><pre>500ms</pre></p>
        <p><pre>toDuration("PT20.345S") </pre></p>
        <p><pre>— viene analizzato come "20.345 secondi"</pre></p>
        <p><pre>toDuration("PT15M") </pre></p>
        <p><pre> — analizza come "15 minuti"</pre></p>
        <p><pre>(dove un minuto è 60 secondi)</pre></p>
        <p><pre>toDuration("PT10H") </pre></p>
        <p><pre>— analizza come "10 ore"</pre></p>
        <p><pre>(dove un'ora è 3600 secondi)</pre></p>
        <p><pre>toDuration("P2D") </pre></p>
        <p><pre>— analizza come "2 giorni"</pre></p>
        <p><pre>(dove un giorno è </pre></p>
        <p><pre>24 ore o 86400 secondi)</pre></p>
        <p><pre>toDuration("P2DT3H4M") </pre></p>
        <p><pre>— analisi come</pre></p>
        <p><pre>"2 giorni, 3 ore e 4 minuti"</pre></p>
        <p><pre>toDuration("P-6H3M") </pre></p>
        <p><pre>— analisi come</pre></p>
        <p><pre>"-6 ore e +3 minuti"</pre></p>
        <p><pre>toDuration("-P6H3M") </pre></p>
        <p><pre>— analisi come</pre></p>
        <p><pre>"-6 ore e -3 minuti"</pre></p>
        <p><pre>toDuration("-P-6H+3M") </pre></p>
        <p><pre>— analisi come</pre></p>
        <p><pre>"+6 ore e -3 minuti"</pre></p></td>
    </tr>
    <tr>
        <td>list</td>
        <td>Elenco separato da virgole di espressioni utilizzando le parentesi quadre come delimitatori. Il polimorfismo non è supportato, pertanto tutte le espressioni contenute nell'elenco devono avere lo stesso tipo.</td>
        <td>[&lt;espressione&gt;, &lt;espressione&gt;, ... ]</td>
        <td><p><pre>["value1","value2"]</pre></p><p><pre>[3,5]</pre></p><p><pre>[toDuration(500),toDuration(800)]</pre></p></td>
    </tr>
    </tbody>
</table>
