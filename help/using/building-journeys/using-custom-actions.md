---
product: adobe campaign
title: Utilizzo di azioni personalizzate
description: Learn about action activities
feature: Journeys
role: User
level: Intermediate
exl-id: 9996d1eb-ddef-46dd-aaa9-c37fa9deb2f9
source-git-commit: 69471a36b113e04a7bb0953a90977ad4020299e4
workflow-type: tm+mt
source-wordcount: '298'
ht-degree: 9%

---

# Utilizzo di azioni personalizzate {#section_f2c_hbg_nhb}


>[!CAUTION]
>
>**Ricerca di Adobe Journey Optimizer**? Fai clic [qui](https://experienceleague.adobe.com/it/docs/journey-optimizer/using/ajo-home){target="_blank"} per la documentazione di Journey Optimizer.
>
>
>_Questa documentazione fa riferimento ai materiali Journey Orchestration legacy che sono stati sostituiti da Journey Optimizer. Contatta il team del tuo account in caso di domande sull&#39;accesso a Journey Orchestration o Journey Optimizer._


The activity configuration pane shows the URL configuration parameters and the authentication parameters that are configured for the custom action. [Ulteriori informazioni](../action/about-custom-action-configuration.md).

## Configurazione URL

### Percorso dinamico

If the URL includes a dynamic path, specify the path in the **[!UICONTROL Path]** field.

>[!NOTE]
>
>Non è possibile impostare la parte statica dell’URL nel percorso, ma nella configurazione globale dell’azione personalizzata. [Ulteriori informazioni](../action/about-custom-action-configuration.md).

Per concatenare campi e stringhe di testo normale, utilizza le funzioni Stringa o il segno più (+) nell’editor di espressioni avanzate. Racchiudere le stringhe di testo normale tra virgolette singole (&#39;) o doppie (&quot;). [Ulteriori informazioni](../expression/expressionadvanced.md).

Questa tabella mostra un esempio di configurazione:

| Campo | Valore |
| --- | --- |
| URL | `https://xxx.yyy.com:8080/somethingstatic/` |
| Percorso | `The id of marketingCampaign + '/messages'` |

L’URL concatenato ha il seguente modulo:

`https://xxx.yyy.com:8080/somethingstatic/`\&lt;campaign ID\>`/messages`

![](../assets/journey-custom-action-url.png)

### Intestazioni

The **[!UICONTROL URL Configuration]** section shows the dynamic header fields, but not the constant header fields. Dynamic header fields are HTTP header fields whose value is configured as a variable. [Ulteriori informazioni](../action/about-custom-action-configuration.md).

If required, specify the value of dynamic header fields:

1. Select the custom action in the journey.
1. In the configuration pane, click the pencil icon next to the header field in the **[!UICONTROL URL Configuration]** section.

   ![](../assets/journey-dynamicheaderfield.png)

1. Select a field and click **[!UICONTROL OK]**.

## Parametri azione

In the **[!UICONTROL Action parameters]** section, you&#39;ll see the message parameters defined as _&quot;Variable&quot;_. Per questi parametri, puoi definire dove ottenere queste informazioni (ad esempio: eventi, origini dati), passare i valori manualmente o utilizzare l’editor di espressioni avanzate per casi d’uso avanzati. I casi d’uso avanzati possono essere la manipolazione dei dati e altro utilizzo di funzioni. [Ulteriori informazioni](../expression/expressionadvanced.md).

**Argomenti correlati**

[Configurare un’azione](../action/about-custom-action-configuration.md)
