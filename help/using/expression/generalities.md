---
product: adobe campaign
title: Generalità
description: Scopri le generalità di espressioni avanzate
feature: Journeys
role: Developer
level: Experienced
exl-id: ba474219-7c9e-4f93-8e9c-16c317131614
product_v2:
  - id: cf67d108-ecf9-4fde-af49-3a3c39083bc8
    internal-label: Journey Orchestration
feature_v2:
  - id: 7de3230f-9523-5ba5-8d5c-2313288b27ef
    internal-label: Journeys
role_v2:
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
    internal-label: Developer
level_v2:
  - id: d378ca77-2da1-4f39-ad92-1917fe974a38
    internal-label: Experienced
source-git-commit: 255cd6677e7c9ebff63ea9a1028a042c19e63ecc
workflow-type: tm+mt
source-wordcount: '278'
ht-degree: 21%
---
# Generalità {#concept_rcy_qj5_dgb}


>[!CAUTION]
>
>**Stai cercando Adobe Journey Optimizer**? Fai clic [qui](https://experienceleague.adobe.com/it/docs/journey-optimizer/using/ajo-home){target="_blank"} per la documentazione di Journey Optimizer.
>
>
>_Questa documentazione fa riferimento ai precedenti materiali su Journey Orchestration, che è stato sostituito da Journey Optimizer. In caso di domande sull’accesso a Journey Orchestration o Journey Optimizer, contatta il team del tuo account._


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

* Tutti gli operatori (e, o, ecc.) devono essere scritte in minuscolo. Ad esempio, _`<expression1>`e`<expression2>`_ sono espressioni valide, mentre l&#39;espressione _`<expression1>`AND`<expression2>`_ non lo è.
* Tutti i nomi di funzione fanno distinzione tra maiuscole e minuscole. Ad esempio, _inSegment()_ è valido, mentre la funzione _INSEGMENT()_ non lo è.
* I riferimenti ai campi e i valori costanti fanno distinzione tra maiuscole e minuscole: non sono elementi incorporati del linguaggio (al contrario di operatori e funzioni), ma vengono creati dall’utente finale.

## Tipo di espressione restituito{#section_gyc_435_53b}

A seconda del contesto di utilizzo, l’editor di espressioni può restituire valori diversi.

| Utilizzo avanzato dell’editor di espressioni | Tipo di espressione restituito previsto |
|--- |--- |
| Condizione (condizione origine dati, condizione data) | booleano |
| Timer personalizzato | dateTimeOnly |
| Mappatura dei parametri delle azioni | Any |
