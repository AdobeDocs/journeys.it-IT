---
product: adobe campaign
title: Aggiunta di una condizione
description: Scopri come aggiungere una condizione
feature: Journeys
role: User
level: Intermediate
exl-id: 09cda689-6953-4ea6-a446-cb4e1d8ad8e4
source-git-commit: 185c2296a51f58e2092787edcc35ee9e4242bec8
workflow-type: tm+mt
source-wordcount: '205'
ht-degree: 4%

---

# Aggiunta di una condizione {#concept_rbg_gqt_52b}

Per gli eventi generati dal sistema, puoi definire una condizione di evento che consente al sistema di filtrare l’elaborazione degli eventi. Se la condizione è true, l’evento viene elaborato. Se la condizione non è vera, l’evento viene ignorato.

La condizione relativa agli eventi può essere basata solo sui dati passati nel payload dell’evento. La condizione definita a livello di evento non può essere modificata nell’area di lavoro da un addetto al marketing. Lo scopo è quello di indurire questa condizione quando viene utilizzato questo evento. Ad esempio, se non vuoi che gli esperti di marketing utilizzino eventi di abbandono carrello se il valore del carrello è troppo piccolo, puoi creare una condizione sul campo evento &quot;valore del carrello&quot; e imporre un valore superiore a 100 dollari.

Puoi utilizzare l’editor di espressioni semplici o l’editor di espressioni avanzate per impostare le condizioni sugli eventi. Consulta [questa pagina](../expression/expressionadvanced.md).

Ad esempio, puoi definire una condizione per elaborare solo gli eventi di un tipo di evento specifico e ignorare gli altri tipi. Oppure, se l’evento è un abbandono del carrello e il payload include il campo del valore del carrello, puoi definire una condizione di evento per elaborare gli eventi solo se il valore del carrello è maggiore di 100 dollari.

![](../assets/journey78.png)
