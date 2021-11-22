---
product: adobe campaign
title: Utilizzo di azioni personalizzate
description: Informazioni sulle attività di azione
feature: Journeys
role: User
level: Intermediate
exl-id: 9996d1eb-ddef-46dd-aaa9-c37fa9deb2f9
source-git-commit: e71d641888caa9385d078d9c85e073b5f1ed743f
workflow-type: tm+mt
source-wordcount: '295'
ht-degree: 9%

---

# Utilizzo di azioni personalizzate {#section_f2c_hbg_nhb}

Il riquadro di configurazione dell’attività mostra i parametri di configurazione dell’URL e i parametri di autenticazione configurati per l’azione personalizzata. [Ulteriori informazioni](../action/about-custom-action-configuration.md).

>[!NOTE]
>
>Non puoi passare una raccolta semplice nei parametri delle azioni personalizzate. Campi di raccolta più complessi (array di oggetti) non supportati.  Tieni presente che i parametri hanno un formato previsto (ad esempio: (stringa, decimale, ecc.). Devi fare attenzione a rispettare questi formati previsti.

## Configurazione URL

### Percorso dinamico

Se l’URL include un percorso dinamico, specifica il percorso nel **[!UICONTROL Path]** campo .

>[!NOTE]
>
>Non puoi impostare la parte statica dell’URL nel percorso, ma nella configurazione globale dell’azione personalizzata. [Ulteriori informazioni](../action/about-custom-action-configuration.md).

Per concatenare campi e stringhe di testo normale, utilizza le funzioni Stringa o il segno Più (+) nell’editor di espressioni avanzate. Racchiudere le stringhe di testo normale tra virgolette singole (&#39;) o tra virgolette doppie (&quot;). [Ulteriori informazioni](../expression/expressionadvanced.md).

Questa tabella mostra un esempio di configurazione:

| Campo | Valore |
| --- | --- |
| URL | `https://xxx.yyy.com:8080/somethingstatic/` |
| Path | `The id of marketingCampaign + '/messages'` |

L’URL concatenato ha questo modulo:

`https://xxx.yyy.com:8080/somethingstatic/`\&lt;campaign id=&quot;&quot;>`/messages`

![](../assets/journey-custom-action-url.png)

### Intestazioni

La **[!UICONTROL URL Configuration]** La sezione mostra i campi di intestazione dinamici, ma non i campi di intestazione costanti. I campi di intestazione dinamica sono campi di intestazione HTTP il cui valore è configurato come variabile. [Ulteriori informazioni](../action/about-custom-action-configuration.md).

Se necessario, specifica il valore dei campi di intestazione dinamici:

1. Seleziona l’azione personalizzata nel percorso.
1. Nel riquadro di configurazione, fai clic sull’icona a forma di matita accanto al campo di intestazione nel **[!UICONTROL URL Configuration]** sezione .

   ![](../assets/journey-dynamicheaderfield.png)

1. Seleziona un campo e fai clic su **[!UICONTROL OK]**.

## Parametri azione

In **[!UICONTROL Action parameters]** vedrai i parametri del messaggio definiti come _&quot;Variabile&quot;_. Per questi parametri, puoi definire dove ottenere queste informazioni (ad esempio: eventi, origini dati), passa i valori manualmente o utilizza l’editor di espressioni avanzate per casi d’uso avanzati. I casi di utilizzo avanzati possono essere di manipolazione dati e di altro utilizzo di funzioni. [Ulteriori informazioni](../expression/expressionadvanced.md).

**Argomenti correlati**

[Configurare un’azione](../action/about-custom-action-configuration.md)
