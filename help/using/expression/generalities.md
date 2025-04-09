---
product: adobe campaign
title: Generalità
description: Scopri le generalità di espressioni avanzate
feature: Journeys
role: Data Engineer
level: Experienced
exl-id: ba474219-7c9e-4f93-8e9c-16c317131614
source-git-commit: 69471a36b113e04a7bb0953a90977ad4020299e4
workflow-type: tm+mt
source-wordcount: '269'
ht-degree: 3%

---

# Generalità {#concept_rcy_qj5_dgb}


>[!CAUTION]
>
>**Ricerca di Adobe Journey Optimizer**? Fai clic [qui](https://experienceleague.adobe.com/it/docs/journey-optimizer/using/ajo-home){target="_blank"} per la documentazione di Journey Optimizer.
>
>
>_Questa documentazione fa riferimento ai materiali Journey Orchestration legacy che sono stati sostituiti da Journey Optimizer. Contatta il team del tuo account in caso di domande sull&#39;accesso a Journey Orchestration o Journey Optimizer._


## Priorità tra parentesi ed espressione{#section_edf_fks_bgb}

Le parentesi possono essere utilizzate per rendere più leggibile un&#39;espressione complessa. _(&lt;espressione>)_ equivale a _&lt;espressione>_. Le parentesi possono essere utilizzate anche per definire l&#39;ordine di valutazione e l&#39;associatività.

Le espressioni verranno valutate da sinistra a destra. L&#39;associatività sugli operatori aritmetici deve essere applicata: le moltiplicazioni e le divisioni hanno priorità rispetto alle addizioni e alle sottrazioni. Per imporre un ordine specifico, è necessario aggiungere una parentesi per delimitare le operazioni. Ad esempio:

<!--```5 + 2 * 10 = 25, and (5 + 2) * 10 = 70```-->

| Espressione | Valutazione |
|--- |--- |
| `4 + 2 * 10` | <ul><li>&#39;*&#39; ha priorità su &#39;+&#39;: 2 * 10 viene valutato → 20</li><li>4 + 20 → 24</li></ul> |
| `(4 + 2) * 10` | <ul><li>Le parentesi modificano la priorità: (4 + 2) viene valutato → 6</li><li> 6 * 10 → 60</li></ul> |

## Distinzione tra maiuscole e minuscole{#section_lrb_xh5_dgb}

Di seguito sono riportate le diverse regole per la distinzione tra maiuscole e minuscole:

* Tutti gli operatori (e, o, ecc.) devono essere scritti in minuscolo. Ad esempio, _`<expression1>`e`<expression2>`_ sono espressioni valide, mentre l&#39;espressione _`<expression1>`AND`<expression2>`_ non lo è.
* Tutti i nomi di funzione fanno distinzione tra maiuscole e minuscole. Ad esempio, _inSegment()_ è valido, mentre la funzione _INSEGMENT()_ non lo è.
* I riferimenti ai campi e i valori costanti fanno distinzione tra maiuscole e minuscole: non sono elementi incorporati del linguaggio (al contrario di operatori e funzioni), ma vengono creati dall’utente finale.

## Tipo di espressione restituito{#section_gyc_435_53b}

A seconda del contesto di utilizzo, l’editor di espressioni può restituire valori diversi.

| Utilizzo avanzato dell’editor di espressioni | Tipo di espressione restituito previsto |
|--- |--- |
| Condizione (condizione origine dati, condizione data) | booleano |
| Timer personalizzato | dateTimeOnly |
| Mappatura dei parametri delle azioni | Qualsiasi |
