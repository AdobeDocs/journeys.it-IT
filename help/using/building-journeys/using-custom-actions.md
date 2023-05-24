---
product: adobe campaign
title: Utilizzo di azioni personalizzate
description: Scopri le attività di azione
feature: Journeys
role: User
level: Intermediate
exl-id: 9996d1eb-ddef-46dd-aaa9-c37fa9deb2f9
source-git-commit: 8980df5cc238a7195f01a1631e418a8de677fbea
workflow-type: tm+mt
source-wordcount: '253'
ht-degree: 11%

---

# Utilizzo di azioni personalizzate {#section_f2c_hbg_nhb}

Il riquadro di configurazione dell’attività mostra i parametri di configurazione dell’URL e i parametri di autenticazione configurati per l’azione personalizzata. [Maggiori informazioni](../action/about-custom-action-configuration.md).

## Configurazione URL

### Percorso dinamico

Se l’URL include un percorso dinamico, specifica il percorso in **[!UICONTROL Path]** campo.

>[!NOTE]
>
>Non è possibile impostare la parte statica dell’URL nel percorso, ma nella configurazione globale dell’azione personalizzata. [Maggiori informazioni](../action/about-custom-action-configuration.md).

Per concatenare campi e stringhe di testo normale, utilizza le funzioni Stringa o il segno più (+) nell’editor di espressioni avanzate. Racchiudere le stringhe di testo normale tra virgolette singole (&#39;) o doppie (&quot;). [Maggiori informazioni](../expression/expressionadvanced.md).

Questa tabella mostra un esempio di configurazione:

| Campo | Valore |
| --- | --- |
| URL | `https://xxx.yyy.com:8080/somethingstatic/` |
| Percorso | `The id of marketingCampaign + '/messages'` |

L’URL concatenato ha il seguente modulo:

`https://xxx.yyy.com:8080/somethingstatic/`\&lt;campaign id=&quot;&quot;>`/messages`

![](../assets/journey-custom-action-url.png)

### Intestazioni

Il **[!UICONTROL URL Configuration]** mostra i campi intestazione dinamici, ma non i campi intestazione costanti. I campi di intestazione dinamici sono campi di intestazione HTTP il cui valore è configurato come variabile. [Maggiori informazioni](../action/about-custom-action-configuration.md).

Se necessario, specifica il valore dei campi di intestazione dinamica:

1. Seleziona l’azione personalizzata nel percorso.
1. Nel riquadro di configurazione, fai clic sull’icona a forma di matita accanto al campo di intestazione nel **[!UICONTROL URL Configuration]** sezione.

   ![](../assets/journey-dynamicheaderfield.png)

1. Seleziona un campo e fai clic su **[!UICONTROL OK]**.

## Parametri azione

In **[!UICONTROL Action parameters]** , vedrai i parametri del messaggio definiti come _&quot;Variabile&quot;_. Per questi parametri, puoi definire dove ottenere queste informazioni (ad esempio: eventi, origini dati), passare i valori manualmente o utilizzare l’editor di espressioni avanzate per casi d’uso avanzati. I casi d’uso avanzati possono essere la manipolazione dei dati e altro utilizzo di funzioni. [Maggiori informazioni](../expression/expressionadvanced.md).

**Argomenti correlati**

[Configurare un’azione](../action/about-custom-action-configuration.md)
