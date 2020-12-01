---
product: adobe campaign
solution: Journey Orchestration
title: Aggiunta di una condizione
description: Scopri come aggiungere una condizione
translation-type: tm+mt
source-git-commit: bf371ef7f2f69cf610c6644db648d304dc9ba525
workflow-type: tm+mt
source-wordcount: '205'
ht-degree: 4%

---



# Aggiunta di una condizione {#concept_rbg_gqt_52b}

Per gli eventi generati dal sistema, potete definire una condizione di evento che consenta al sistema di filtrare l&#39;elaborazione degli eventi. Se la condizione è true, l&#39;evento viene elaborato. Se la condizione non è vera, l&#39;evento viene ignorato.

La condizione relativa agli eventi può essere basata solo sui dati passati nel payload dell&#39;evento. La condizione definita a livello di evento non può essere modificata nel quadro da un esperto di marketing. Lo scopo è quello di rendere più difficile questa condizione quando l&#39;evento viene utilizzato. Ad esempio, se non si desidera mai che gli esperti di marketing utilizzino eventi di abbandono del carrello se il valore del carrello è troppo piccolo, è possibile creare una condizione per il campo evento &quot;valore del carrello&quot; e imporre un valore superiore a 100 dollari.

È possibile utilizzare l&#39;editor di espressioni semplici o l&#39;editor di espressioni avanzate per impostare le condizioni relative agli eventi. Consulta [questa pagina](../expression/expressionadvanced.md).

Ad esempio, è possibile definire una condizione per elaborare solo gli eventi di un tipo specifico di evento e ignorare gli altri tipi. Oppure, se l&#39;evento è un abbandono del carrello e il payload include il campo del valore del carrello, puoi definire una condizione dell&#39;evento per elaborare gli eventi solo se il valore del carrello è maggiore di 100 dollari.

![](../assets/journey78.png)
