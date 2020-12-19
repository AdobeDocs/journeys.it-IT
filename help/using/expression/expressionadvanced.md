---
product: adobe campaign
solution: Journey Orchestration
title: Informazioni sull’editor di espressioni avanzate
description: Scopri come creare espressioni avanzate
translation-type: tm+mt
source-git-commit: 57dc86d775bf8860aa09300cf2432d70c62a2993
workflow-type: tm+mt
source-wordcount: '501'
ht-degree: 96%

---


# Informazioni sull’editor di espressioni avanzate {#concept_uyj_trt_52b}

L’editor di espressioni avanzate ti consente di creare espressioni avanzate in varie schermate dell’interfaccia, ad esempio, quando definisci una condizione di origine dati.
È inoltre disponibile ogni volta che hai bisogno di definire parametri di azione che richiedono specifiche manipolazioni dei dati. Puoi sfruttare i dati provenienti dagli eventi o le informazioni aggiuntive recuperate dall’origine dati. In un percorso, l’elenco visualizzato dei campi dell’evento è contestuale e varia in base agli eventi aggiunti nel percorso.

L’editor di espressioni avanzate offre un set di funzioni e operatori incorporati che ti consente di manipolare i valori e definire un’espressione adatta alle tue esigenze. L’editor di espressioni avanzate ti consente inoltre di definire i valori del parametro dell’origine dati esterna, di manipolare i campi e le raccolte delle mappe, ad esempio gli eventi di esperienza.

![](../assets/journey65.png)

_Interfaccia dell’editor di espressioni avanzate_

L’editor di espressioni avanzate può essere utilizzato per:

* creare [condizioni avanzate](../building-journeys/condition-activity.md#about_condition) sulle origini dati e sulle informazioni sull’evento
* definire le [attività di attesa](../building-journeys/wait-activity.md#custom) personalizzate
* definire la mappatura dei parametri di azione

Ove possibile, puoi passare tra le due modalità utilizzando il pulsante **[!UICONTROL Advanced mode]**/**[!UICONTROL Simple mode]**. La modalità semplice è descritta [qui](../building-journeys/condition-activity.md#about_condition).

>[!NOTE]
>
>Le condizioni possono essere definite nell’editor di espressioni semplice o avanzato. Restituiscono sempre un tipo booleano.
>
>I parametri delle azioni possono essere definiti selezionando i campi o tramite l’editor di espressioni avanzate. I parametri restituiscono un tipo di dati specifico in base alla relativa espressione.

## Accesso all’editor di espressioni avanzate {#section_fdz_4nj_cjb}

Puoi accedere all’editor di espressioni avanzate con diverse modalità:

* Quando crei una condizione di origine dati, puoi accedere all’editor avanzato facendo clic su **[!UICONTROL Advanced mode]**.

   ![](../assets/journeyuc2_33.png)

* Quando crei un timer personalizzato, l’editor avanzato viene visualizzato direttamente.
* Quando mappi il parametro dell’azione, fai clic su **[!UICONTROL Advanced mode]**.

## Esplorazione dell’interfaccia{#section_otq_tnj_cjb}

Questa schermata ti consente di scrivere manualmente l’espressione.

![](../assets/journey70.png)

Nella parte sinistra dello schermo sono visualizzati i campi e le funzioni disponibili:

* **[!UICONTROL Events]**: scegli uno dei campi ricevuti dall’evento in entrata. L’elenco visualizzato dei campi dell’evento è contestuale e varia in base agli eventi aggiunti nel percorso.
* **[!UICONTROL Data Sources]**: scegli dall’elenco di campi disponibili nei gruppi di campi delle origini dati.
* **[!UICONTROL Functions]**: scegli dall’elenco di funzioni integrate che consentono di eseguire filtri complessi. Le funzioni sono organizzate per categorie.

![](../assets/journey65.png)

Un meccanismo di completamento automatico visualizza i suggerimenti contestuali.

![](../assets/journey68.png)

Un meccanismo di convalida della sintassi verifica l’integrità del tuo codice. Gli errori vengono visualizzati sopra l’editor.

![](../assets/journey69.png)

**Necessità di parametri per la creazione di condizioni con l’editor di espressioni avanzate**

Se si seleziona un campo da un&#39;origine dati esterna che richiede la chiamata di un parametro (vedere [questa pagina](../datasource/external-data-sources.md). Ad esempio, in un’origine dati correlata al meteo, un parametro utilizzato di frequente sarà “city”. Di conseguenza, devi selezionare il punto in cui vuoi ottenere questo parametro della città. Ai parametri è possibile applicare anche le funzioni, al fine di eseguire modifiche di formato o concatenazioni.

![](../assets/journeyuc2_19.png)

Per casi di utilizzo più complessi, se desideri includere i parametri dell’origine dati nell’espressione principale, puoi definirne i valori utilizzando la parola chiave “params”. Consulta [questa pagina](../expression/field-references.md).
