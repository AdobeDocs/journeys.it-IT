---
product: adobe campaign
solution: Journey Orchestration
title: Generalità
description: Scopri le generalità delle espressioni avanzate
feature: Journeys
role: Data Engineer
level: Experienced
translation-type: tm+mt
source-git-commit: ab19cc5a3d998d1178984c5028b1ba650d3e1292
workflow-type: tm+mt
source-wordcount: '218'
ht-degree: 2%

---


# Generalità {#concept_rcy_qj5_dgb}

## Parentesi ed espressione prioritarie{#section_edf_fks_bgb}

Le parentesi possono essere utilizzate per rendere più leggibile un’espressione complessa. _(&lt;expression>)_ è l’equivalente di  _&lt;expression>_. È inoltre possibile utilizzare le parentesi per definire l’ordine di valutazione e l’associatività.

Le espressioni verranno valutate da sinistra a destra. L&#39;associatività sugli operatori aritmetici deve essere applicata: le moltiplicazioni e le divisioni hanno la priorità su aggiunte e sottrazioni. Per imporre un ordine specifico, è necessario aggiungere parentesi per delimitare le operazioni. Ad esempio:

<!--```5 + 2 * 10 = 25, and (5 + 2) * 10 = 70```-->

| Espressione | Valutazione |
|--- |--- |
| `4 + 2 * 10` | <ul><li>&#39;*&#39; ha la priorità rispetto a &#39;+&#39;: 2 * 10 è valutato → 20</li><li>4 + 20 → 24</li></ul> |
| `(4 + 2) * 10` | <ul><li>Le parentesi cambiano la priorità: (4 + 2) è valutato → 6</li><li> 6 * 10 → 60</li></ul> |

## Sensibilità delle maiuscole/minuscole{#section_lrb_xh5_dgb}

Di seguito sono riportate le diverse regole di distinzione tra maiuscole e minuscole:

* Tutti gli operatori (e, o, ecc.) devono essere scritte in minuscolo. Ad esempio, _`<expression1>`e`<expression2>`_ è un’espressione valida, mentre l’espressione _`<expression1>`AND`<expression2>`_ non lo è.
* Tutti i nomi delle funzioni fanno distinzione tra maiuscole e minuscole. Ad esempio, _inSegment()_ è valido mentre la funzione _INSEGMENT()_ non lo è.
* I riferimenti ai campi e i valori costanti fanno distinzione tra maiuscole e minuscole: non sono elementi incorporati della lingua (a differenza degli operatori e delle funzioni), sono creati dall&#39;utente finale.

## Tipo di espressione restituito{#section_gyc_435_53b}

A seconda del contesto di utilizzo, l’editor di espressioni può restituire valori diversi.

| Utilizzo dell’editor di espressioni avanzate | Tipo di espressione restituito previsto |
|--- |--- |
| Condizione (condizione origine dati, condizione data) | booleano |
| Timer personalizzato | dateTimeOnly |
| Mappatura dei parametri delle azioni | Qualsiasi |
