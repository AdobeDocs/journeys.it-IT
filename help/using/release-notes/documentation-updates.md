---
product: adobe campaign
title: Aggiornamenti alla documentazione
description: Scopri gli aggiornamenti della documentazione
feature: Journeys
role: User
level: Beginner
exl-id: ac5d2cec-0b48-4863-afe3-19ac5f61c9fd
source-git-commit: 77fcc4ba02a855d4d584627625a08abb4af0da2f
workflow-type: tm+mt
source-wordcount: '992'
ht-degree: 100%

---

# Aggiornamenti alla documentazione

Questa pagina elenca tutti gli aggiornamenti alla documentazione di [!DNL Journey Orchestration].
È inoltre possibile consultare le [!DNL Journey Orchestration][Note sulla versione](../release-notes/release-notes.md).

## Luglio 2022 {#july-2022}

* Nelle proprietà del percorso, l’opzione **Fuso orario del profilo** è disabilitata per impostazione predefinita. [Ulteriori informazioni](../building-journeys/timezone-management.md#timezone-from-profiles)
* Nell’attività **Attendi** l’opzione **Data fissa** non è più disponibile. [Ulteriori informazioni](../building-journeys/wait-activity.md)

## Giugno 2022 {#june-2022}

* Sono stati aggiunti nuovi esempi di query in questa [pagina](../building-journeys/query-examples.md).

## Marzo 2022 {#march-2022}

* Nell’editor espressioni è stato aggiunto un esempio su come aggiungere un’espressione come valore predefinito. [Ulteriori informazioni](../expression/field-references.md#default-value)

## Febbraio 2022 {#feb-2022}

* Le pagine della documentazione sulle funzioni [replace](../functions/functionreplace.md#example_2) e [replaceAll](../functions/functionreplaceall.md#example) sono state aggiornate con ulteriori informazioni ed esempi relativi al parametro di destinazione.
* Sono state aggiunte delle best practice alla pagina [Operatori](../expression/operators.md#important-notes).

## Settembre 2021

* Sono state aggiornate le pagine delle seguenti funzioni: [sethours](../functions/functionsethours.md), [getListItem](../functions/functiongetlistitem.md), [inSegment](../functions/functioninsegment.md)

* Sono state aggiunte le seguenti funzioni: [filter](../functions/functionfilter.md), [intersect](../functions/functionintersect.md), [toDateOnly](../functions/functiontodateonly.md)

* Nella documentazione dell’editor di espressioni è stato aggiunto il tipo di data dateOnly. [Ulteriori informazioni](../expression/data-types.md)

* Sono stati aggiunti dettagli sulla durata della cache delle azioni personalizzate. [Ulteriori informazioni](../datasource/external-data-sources.md#section_wjp_nl5_nhb)

* Sono state aggiunte informazioni sulle porte predefinite per le azioni personalizzate. [Ulteriori informazioni](../action/url-configuration.md)

* Sono stati aggiunti alcuni esempi di uso comune per eseguire query sugli eventi dei passaggi del percorso in Data Lake. [Ulteriori informazioni](../building-journeys/query-examples.md)

## Agosto 2021

* È stata aggiornata la procedura di configurazione per le azioni personalizzate con percorsi URL dinamici e intestazioni dinamiche. [Ulteriori informazioni](../action/url-configuration.md)
* È stata aggiunta una sezione sulle funzioni di accessibilità. [Ulteriori informazioni](../about/user-interface.md#accessibility)
* È stata aggiunta una sezione sui metodi di valutazione dei segmenti. [Ulteriori informazioni](../segment/about-segments.md#evaluation-method-in-journey-orchestration)

## Marzo 2021 {#march-2021}

* Abbiamo descritto la procedura completa per creare profili di test in Adobe Experience Platform. [Ulteriori informazioni](../building-journeys/creating-test-profiles.md).

## Gennaio 2021 {#january-2021}

* Sono state aggiunte le best practice per attivare un percorso contemporaneamente alla creazione di un profilo. [Ulteriori informazioni](../about/limitations.md#journeys-limitation-profile-creation).

## Ottobre 2020 {#october-2020}

* Sono state aggiunte informazioni su come configurare un timeout per un evento. [Ulteriori informazioni](../building-journeys/event-activities.md#listening-to-events-during-a-specific-time).

## Settembre 2020 {#september-2020}

* La sezione che descrive l’interfaccia è stata aggiornata per riflettere il nuovo menu del **selettore Tutto**. [Ulteriori informazioni](../about/user-interface.md)
* È stata aggiunta una nota sulle nuove versioni non ricorrenti dei percorsi basati su segmenti.

## Agosto 2020 {#august-2020}

* Sono state aggiunte informazioni su come ordinare e scegliere le colonne da visualizzare nell’elenco dei segmenti. [Ulteriori informazioni](../building-journeys/segment-qualification-events.md)
* Sono state aggiunte informazioni su come copiare il nome e l’ID di un segmento dopo averlo selezionato. [Ulteriori informazioni](../building-journeys/segment-qualification-events.md)
* Le occorrenze di Experience Platform sono state armonizzate tra le diverse pagine.

## Luglio 2020 {#july-2020}

* È stato aggiunto un collegamento a un nuovo video di esercitazione sugli eventi dei passaggi che inviano rapporti ad Adobe Experience Platform. [Ulteriori informazioni](../building-journeys/sharing-overview.md)
* La sezione delle attività eventi è stata riorganizzata in sottosezioni dedicate per ciascun tipo di evento. [Ulteriori informazioni](../building-journeys/event-activities.md)
* Sono state aggiunte le best practice per evitare il sovraccarico con la qualificazione dei segmenti. [Ulteriori informazioni](../building-journeys/segment-qualification-events.md#speed-segment-qualification)
* È stata aggiunta una nota per spiegare come fare in modo che un percorso continui dopo un errore in un’azione o in una condizione. [Ulteriori informazioni](../about/troubleshooting.md#section_h3q_kqk_fhb)
* È stata aggiunta una nuova sezione sulle funzioni alfa testate da un gruppo limitato di clienti.
* È stata aggiunta una nuova sezione sull’integrazione con Intelligent Services. [Ulteriori informazioni](../ai-services/ai-services-overview.md)
* È stata aggiunta una nuova sezione sulla creazione del profilo di test. [Ulteriori informazioni](../building-journeys/testing-the-journey.md)
* Sono state aggiunte informazioni su come utilizzare il nodo **[!UICONTROL SegmentQualification]** in una condizione o azione di percorso. [Ulteriori informazioni](../building-journeys/segment-qualification-events.md)
* È stata aggiunta una nota al messaggio transazionale di Campaign e alla pubblicazione dell’evento. Consulta [Utilizzo di Adobe Campaign](../action/working-with-adobe-campaign.md) e [Utilizzo delle azioni di Adobe Campaign](../building-journeys/using-adobe-campaign-actions.md).
* Sono state aggiunte informazioni sui controlli eseguiti durante il test dell’URL dell’istanza di Campaign Standard. [Ulteriori informazioni](../action/working-with-adobe-campaign.md)
* Sono state aggiunte informazioni sulla compatibilità degli eventi di reazione con le istanze di Campaign Standard ospitate su server AWS o Azure. [Ulteriori informazioni](../building-journeys/reaction-events.md)
* È stata aggiunta una nota sulla necessità di impostare una regola di limitazione di utilizzo nelle operazioni di messaggistica transazionale di Campaign Standard. [Ulteriori informazioni](../action/working-with-adobe-campaign.md)
* È stata aggiunta una nota sulla generazione di eventi reali quando si attivano gli eventi utilizzando la modalità di test. [Ulteriori informazioni](../building-journeys/testing-the-journey.md#firing_events)

## Giugno 2020 {#june-2020}

* Sono state aggiunte informazioni su come modificare la durata della cache del token per un’origine dati di autenticazione personalizzata. [Ulteriori informazioni](../datasource/external-data-sources.md#section_wjp_nl5_nhb)
* Le schermate e il testo sono stati aggiornati per riflettere la ridenominazione dello stato del percorso **[!UICONTROL Finished]** che è stato modificato in **[!UICONTROL Closed (no entrance)]**.
* Sono state aggiunte informazioni sulla definizione della lingua per l’interfaccia. [Ulteriori informazioni](../about/user-interface.md)
* L’elenco degli stati del percorso di un individuo è stato spostato nella sezione dei [registri della modalità di prova](../building-journeys/testing-the-journey.md#viewing_logs).

## Aprile 2020 {#april-2020}

* È stata aggiunta una nuova sezione sulla definizione dello schema evento esperienza per aiutare gli utenti a configurare il loro primo evento. [Ulteriori informazioni](../event/experience-event-schema.md)
* La pagina principale della documentazione di [!DNL Journey Orchestration] è stata aggiornata con altri collegamenti utili. [Ulteriori informazioni](../../journey-orchestration-home.md)

## Marzo 2020 {#march-2020}

* Nella sezione dei registri di test sono state aggiunte le descrizioni dei parametri per _actionExecutionErrors_ e _fetchErrors_. [Ulteriori informazioni](../building-journeys/testing-the-journey.md#viewing_logs)
* Sono state aggiornate le limitazioni alle azioni personalizzate utilizzate in un percorso. Puoi anche modificare il campo **[!UICONTROL URL]** e i parametri di **[!UICONTROL Authentication]**. [Ulteriori informazioni](../action/about-custom-action-configuration.md)
* Sono state aggiunte nuove voci di aiuto contestuali. In azioni e origini dati, il riquadro del payload di autenticazione personalizzata adesso include un’icona di aiuto che collega a questa [sezione](../datasource/external-data-sources.md#section_wjp_nl5_nhb).
* Ora è possibile interrompere i percorsi chiusi. [Ulteriori informazioni](../building-journeys/using-the-journey-designer.md)
* È stata riorganizzata la sezione relativa alla descrizione dell’interfaccia. [Ulteriori informazioni](../about/user-interface.md)
* È stata aggiunta l’attivazione di più eventi alla sezione Modalità di test [Ulteriori informazioni](../building-journeys/testing-the-journey.md#firing_events)
* La sezione Modalità di test è stata aggiornata per quanto riguarda il nuovo parametro **[!UICONTROL Wait time in test]** (Tempo di attesa nel test). [Ulteriori informazioni](../building-journeys/testing-the-journey.md)
* La sezione del registro dei test è stata aggiornata con i codici di errore e le risposte della chiamata esterna. [Ulteriori informazioni](../building-journeys/testing-the-journey.md#viewing_logs)
* La gestione del fuso orario è ora centralizzata nel pannello delle proprietà del percorso. Per ulteriori informazioni, consulta [questa](../building-journeys/changing-properties.md#timezone) e [questa sezione](../building-journeys/timezone-management.md).
* La sezione designer del percorso è stata aggiornata per riflettere i miglioramenti più recenti. [Ulteriori informazioni](../building-journeys/using-the-journey-designer.md)
* La descrizione dell’interfaccia è stata aggiornata con le informazioni sull’aiuto contestuale. [Ulteriori informazioni](../about/user-interface.md#section_ksq_zr1_ffb)
* Quando esplori i **campi XDM**, ora viene visualizzato il nome descrittivo. Le sezioni correlate sono state aggiornate. [Ulteriori informazioni](../about/user-interface.md#friendly-names-display)

## Febbraio 2020 {#february-2020}

* La sezione dei collegamenti è stata aggiornata. La scelta rapida da tastiera **C** consente di creare una nuova voce in tutte le schermate dell’elenco. [Ulteriori informazioni](../about/user-interface.md#section_ksq_zr1_ffb)
* Sono state migliorate le pagine di panoramica di [origine dati](../datasource/about-data-sources.md) e delle [azioni](../action/action.md).

## Gennaio 2020 {#january-2020}

* Sono state aggiunte limitazioni per acquisire gli [eventi di esperienza](../datasource/adobe-experience-platform-data-source.md) e i [segmenti](../functions/functioninsegment.md).
   <!--* The [getBestSendTime documentation](../functions/functiongetbestsendtime.md) has been updated.-->

## Dicembre 2019 {#december-2019}

* Tutte le schermate sono state aggiornate per riflettere le modifiche all’interfaccia.
* La sezione della modalità di test è stata aggiornata. [Ulteriori informazioni](../building-journeys/testing-the-journey.md)
   <!--* A warning has been added in the [email send time optimization](../building-journeys/wait-activity.md) and [predictive fatigue scores](../ai-services/leveraging-fatigue-scores.md) sections. These capabilities are only available to customers who use the [Adobe Experience Platform Data Connector](https://experienceleague.adobe.com/docs/campaign-standard/using/integrating-with-adobe-cloud/adobe-experience-platform/data-connector/aep-about-data-connector.html).-->
* I percorsi interrotti ora possono essere eliminati. Sono state aggiornate le pagine correlate della documentazione.
* Quando si rilevano problemi in un percorso, ora vengono visualizzati due colori: il rosso indica gli errori e l’arancione gli avvisi. [Ulteriori informazioni](../about/troubleshooting.md)
* È stata aggiornata la sezione dell’editor di espressioni avanzate. [Ulteriori informazioni](../expression/expressionadvanced.md).
* Sono state spostate e aggiornate le sezioni relative alle [istruzioni condizionali](../expression/conditional-instruction.md) e alla [gestione della raccolta](../expression/collection-management-functions.md).
* La sezione delle [funzioni](../expression/functions.md) è stata aggiornata con nuovi esempi.
* La documentazione della [funzione toDateTime](../functions/functiontodatetime.md) è stata aggiornata per riflettere le modifiche della sintassi del fuso orario.
