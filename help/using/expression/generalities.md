---
title: Generalità
description: Informazioni sulle generalità di espressione avanzate
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

---


# Generalità {#concept_rcy_qj5_dgb}

## Parentesi e priorità espressione{#section_edf_fks_bgb}

Le parentesi possono essere utilizzate per rendere più leggibile un&#39;espressione complessa. _(&lt;espressione>)_ è l&#39;equivalente di _&lt;espressione>_. Le parentesi possono essere utilizzate anche per definire l&#39;ordine di valutazione e l&#39;associatività.

Le espressioni vengono valutate da sinistra a destra. L&#39;associatività sugli operatori aritmetici deve essere applicata: le moltiplicazioni e le divisioni hanno la priorità su aggiunte e sottrazioni. Per imporre un ordine specifico, è necessario aggiungere parentesi per delimitare le operazioni. Ad esempio:

<!--```5 + 2 * 10 = 25, and (5 + 2) * 10 = 70```-->

| Espressione | Valutazione |
|--- |--- |
| `4 + 2 * 10` | <ul><li>&#39;*&#39; ha la priorità su &#39;+&#39;: 2 * 10 è valutato → 20</li><li>4 + 20 → 24</li></ul> |
| `(4 + 2) * 10` | <ul><li>Le parentesi cambiano la priorità: (4 + 2) viene valutato → 6</li><li> 6 * 10 → 60</li></ul> |

## Sensibilità delle maiuscole{#section_lrb_xh5_dgb}

Di seguito sono riportate le diverse regole di distinzione tra maiuscole e minuscole:

* Tutti gli operatori (e, o, ecc.) Deve essere scritto in lettere minuscole. Ad esempio, _`<expression1>`ed`<expression2>`_è un&#39;espressione valida mentre l&#39;espressione_`<expression1>` AND `<expression2>`_ non lo è.
* Tutti i nomi delle funzioni sono con distinzione tra maiuscole e minuscole. Ad esempio, _getBestSendTime()_ è valido, mentre la funzione _GETBESTSENDTIME()_ non lo è.
* I riferimenti ai campi e i valori costanti fanno distinzione tra maiuscole e minuscole: non sono elementi incorporati della lingua (a differenza di operatori e funzioni), sono creati dall&#39;utente finale.

## Tipo di espressione restituito{#section_gyc_435_53b}

A seconda del contesto di utilizzo, l&#39;editor di espressioni può restituire valori diversi.

| Utilizzo avanzato dell&#39;editor di espressioni | Tipo di espressione restituito previsto |
|--- |--- |
| Condizione (condizione origine dati, condizione data) | boolean |
| Timer personalizzato | dateTimeOnly |
| Fuso orario personalizzato | timeZone o stringa (ad esempio Europa/Parigi) |
| Mappatura parametri azione | Qualsiasi |
