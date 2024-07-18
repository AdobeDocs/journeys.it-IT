---
product: adobe campaign
user-guide-title: Journey Orchestration
title: Guida di Journey Orchestration
user-guide-description: Istruzioni per l’implementazione e la creazione dei percorsi dei clienti.
index: true
feature: Journeys
source-git-commit: 137637a753ba44cc4f8e397b77c3fc076ec3de3f
workflow-type: tm+mt
source-wordcount: '446'
ht-degree: 100%

---


# Guida di [!DNL Journey Orchestration] {#using}

+ [Documentazione del prodotto](journey-orchestration-home.md)
+ Novità {#release-notes}
   + [Note sulla versione](using/release-notes/release-notes.md)
   + [Aggiornamenti alla documentazione](using/release-notes/documentation-updates.md)
   + [Aggiornamento a Journey Optimizer](using/release-notes/upgrade-to-ajo.md)
+ Primi passi con [!DNL Journey Orchestration] {#starting-with-journeys}
   + [Informazioni su [!DNL Journey Orchestration]](using/about/about-journey-orchestration.md)
   + [Limitazioni ](using/about/limitations.md)
   + [Introduzione](using/about/get-started.md)
   + [Interfaccia utente](using/about/user-interface.md)
   + [Gestione degli accessi](using/about/access-management.md)
   + [Risoluzione dei problemi](using/about/troubleshooting.md)
   + [Integrazione con sistemi esterni](using/about/external-systems.md)
+ Configurazione di un evento {#events-journeys}
   + Informazioni sugli eventi {#about-events}
      + [Principio generale](using/event/about-events.md)
      + [Ciclo dei dati](using/event/about-data-cycle.md)
      + [Creazione di un evento](using/event/about-creating.md)
      + [Utilizzo di Adobe Analytics](using/event/about-analytics.md)
      + [Informazioni sugli schemi ExperienceEvent](using/event/experience-event-schema.md)
      + [Passaggi aggiuntivi per l’invio di eventi](using/event/additional-steps-to-send-events-to-journey-orchestration.md)
   + [Definizione dei campi payload](using/event/defining-the-payload-fields.md)
   + [Selezione dello spazio dei nomi](using/event/selecting-the-namespace.md)
   + [Definizione del codice evento](using/event/defining-the-event-key.md)
   + [Anteprima del payload](using/event/previewing-the-payload.md)
+ Configurazione di un’origine dati {#data-source-journeys}
   + [Informazioni sulle origini dati](using/datasource/about-data-sources.md)
   + [Gruppi di campi](using/datasource/field-groups.md)
   + [Origine dati Adobe Experience Platform](using/datasource/adobe-experience-platform-data-source.md)
   + [Origini dati esterne](using/datasource/external-data-sources.md)
+ Configurazione di un’azione {#action-journeys}
   + [Informazioni sulle azioni](using/action/action.md)
   + [Utilizzo di Adobe Campaign Standard](using/action/working-with-adobe-campaign.md)
   + [Utilizzo di Adobe Campaign v7/v8](using/action/acc-action.md)
   + Utilizzo di un sistema di terze parti {#action-third-party}
      + [Informazioni sulla configurazione delle azioni personalizzata](using/action/about-custom-action-configuration.md)
      + [Configurazione URL](using/action/url-configuration.md)
      + [Definizione dei parametri dell’azione](using/action/defining-the-message-parameters.md)
+ Utilizzo dei segmenti {#configuring-segment}
   + [Informazioni sui segmenti](using/segment/about-segments.md)
   + [Creazione di un segmento](using/segment/creating-a-segment.md)
   + [Utilizzo di segmenti nelle condizioni](using/segment/using-a-segment.md)
+ Creare un percorso {#building-journeys}
   + Informazioni sulla creazione di percorsi {#about-journey-building}
      + [Creazione di un percorso](using/building-journeys/journey.md)
      + [Utilizzo del designer del percorso](using/building-journeys/using-the-journey-designer.md)
      + [Modifica delle proprietà](using/building-journeys/changing-properties.md)
      + [Versioni del percorso](using/building-journeys/journey-versions.md)
      + [Conclusione di un percorso](using/building-journeys/terminating-a-journey.md)
      + [Gestione del fuso orario](using/building-journeys/timezone-management.md)
      + [Profili di test](using/building-journeys/creating-test-profiles.md)
   + Attività {#about-journey-building}
      + Attività eventi {#events-activities}
         + [Informazioni sulle attività eventi](using/building-journeys/event-activities.md)
         + [Eventi generali](using/building-journeys/general-events.md)
         + [Eventi di reazione](using/building-journeys/reaction-events.md)
         + [Eventi di qualificazione dei segmenti](using/building-journeys/segment-qualification-events.md)
      + Attività di orchestrazione {#orchestration-activities}
         + [Informazioni sulle attività di orchestrazione](using/building-journeys/about-orchestration-activities.md)
         + [Attività Condizione](using/building-journeys/condition-activity.md)
         + [Attività Fine](using/building-journeys/end-activity.md)
         + [Attività Attendi](using/building-journeys/wait-activity.md)
      + Attività di azione {#action-activities}
         + [Informazioni sulle attività di azione](using/building-journeys/about-action-activities.md)
         + [Utilizzo di Adobe Campaign Standard](using/building-journeys/using-adobe-campaign-actions.md)
         + [Utilizzo di Adobe Campaign v7/v8](using/building-journeys/using-adobe-campaign-classic.md)
         + [Utilizzo di azioni personalizzate](using/building-journeys/using-custom-actions.md)
         + [Passaggio da un percorso a un altro](using/building-journeys/jump.md)
         + [Aggiorna il profilo](using/building-journeys/update-profiles.md)
   + [Verifica del percorso](using/building-journeys/testing-the-journey.md)
   + [Pubblicazione del percorso](using/building-journeys/publishing-the-journey.md)
   + Condivisione di passaggi del percorso con Adobe Experience Platform {#sharing-journey-steps}
      + [Panoramica sulla condivisione delle fasi del percorso](using/building-journeys/sharing-overview.md)
      + [Elenco dei campi evento del passaggio](using/building-journeys/sharing-field-list.md)
      + Campi di eventi passaggio legacy{#legacy-step-event-fields}
         + [Informazioni sui campi legacy](using/building-journeys/sharing-legacy-fields.md)
         + [Campi comuni degli eventi journeySteps](using/building-journeys/sharing-common-fields.md)
         + [Campi di esecuzione dell’azione eventi journeyStep](using/building-journeys/sharing-execution-fields.md)
         + [Campi di recupero dati di eventi journeyStep](using/building-journeys/sharing-fetch-fields.md)
         + [Campi di identità dell’evento journeyStep](using/building-journeys/sharing-identity-fields.md)
         + [campi del percorso](using/building-journeys/sharing-journey-fields.md)
      + [Esempi di query](using/building-journeys/query-examples.md)
+ Creare espressioni {#building-advanced-conditions-journeys}
   + [Panoramica](using/expression/expressionadvanced.md)
   + Sintassi {#syntax}
      + [Generalità](using/expression/generalities.md)
      + [Istruzione condizionale](using/expression/conditional-instruction.md)
      + [Tipi di dati](using/expression/data-types.md)
      + [Riferimenti campo](using/expression/field-references.md)
      + [Funzioni di gestione delle raccolte](using/expression/collection-management-functions.md)
      + [Operatori](using/expression/operators.md)
      + [Proprietà del percorso](using/expression/journey-properties.md)
      + [Esempi](using/expression/advanced-editor-use-cases.md)
   + Funzioni {#main-functions-journey}
      + [Funzioni principali](using/expression/functions.md)
      + Adobe Experience Platform {#adobe-experience-platform}
         + [inSegment](using/functions/functioninsegment.md)
      + Aggregazione {#aggregation}
         + [avg](using/functions/functionavg.md)
         + [conteggio](using/functions/functioncount.md)
         + [countOnlyNull](using/functions/functioncountonlynull.md)
         + [countWithNull](using/functions/functioncountwithnull.md)
         + [distinctCount](using/functions/functiondistinctcount.md)
         + [distinctCountWithNull](using/functions/functiondistinctcountwithnull.md)
         + [max](using/functions/functionmax.md)
         + [min](using/functions/functionmin.md)
         + [sum](using/functions/functionsum.md)
      + Conversione {#conversion}
         + [toBool](using/functions/functiontobool.md)
         + [toDateOnly](using/functions/functiontodateonly.md)
         + [toDateTime](using/functions/functiontodatetime.md)
         + [toDateTimeOnly](using/functions/functiontodatetimeonly.md)
         + [toDecimal](using/functions/functiontodecimal.md)
         + [toDuration](using/functions/functiontoduration.md)
         + [toInteger](using/functions/functiontointeger.md)
         + [toString](using/functions/functiontostring.md)
      + Data {#date}
         + [currentTimeInMillis](using/functions/functioncurrenttimeinmillis.md)
         + [inLastDays](using/functions/functioninlastdays.md)
         + [inLastHours](using/functions/functioninlasthours.md)
         + [inLastMonths](using/functions/functioninlastmonths.md)
         + [inLastYears](using/functions/functioninlastyears.md)
         + [inNextDays](using/functions/functioninnextdays.md)
         + [inNextHours](using/functions/functioninnexthours.md)
         + [inNextMonths](using/functions/functioninnextmonths.md)
         + [inNextYears](using/functions/functioninnextyears.md)
         + [now](using/functions/functionnow.md)
         + [nowWithDelta](using/functions/functionnowwithdelta.md)
         + [setHours](using/functions/functionsethours.md)
         + [setDays](using/functions/functionsetdays.md)
         + [updateTimeZone](using/functions/functionupdatetimezone.md)
      + Elenco {#list}
         + [distinct](using/functions/functiondistinct.md)
         + [distinctWithNull](using/functions/functiondistinctwithnull.md)
         + [filter](using/functions/functionfilter.md)
         + [getListItem](using/functions/functiongetlistitem.md)
         + [in](using/functions/functionin.md)
         + [intersect](using/functions/functionintersect.md)
         + [limit](using/functions/functionlimit.md)
         + [listSize](using/functions/functionlistsize.md)
         + [serializeList](using/functions/functionserializelist.md)
         + [ordina](using/functions/functionsort.md)
      + Matematica {#math}
         + [random](using/functions/functionrandom.md)
         + [round](using/functions/functionround.md)
      + Stringa {#string}
         + [concatena](using/functions/functionconcat.md)
         + [contain](using/functions/functioncontain.md)
         + [containIgnoreCase](using/functions/functioncontainwithignorecase.md)
         + [endWith](using/functions/functionendwith.md)
         + [endWithIgnorecase](using/functions/functionendwithignorecase.md)
         + [equalIgnoreCase](using/functions/functionequalignorecase.md)
         + [indexOf](using/functions/functionindexof.md)
         + [IsEmpty](using/functions/functionisempty.md)
         + [isNotEmpty](using/functions/functionisnotempty.md)
         + [lastIndexOf](using/functions/functionlastindexof.md)
         + [lunghezza](using/functions/functionlength.md)
         + [lower](using/functions/functionlower.md)
         + [matchRegExp](using/functions/functionmatchregexp.md)
         + [notequalIgnoreCase](using/functions/functionnotequalignorecase.md)
         + [replace](using/functions/functionreplace.md)
         + [replaceAll](using/functions/functionreplaceall.md)
         + [split](using/functions/functionsplit.md)
         + [startWith](using/functions/functionstartwith.md)
         + [startWithIgnoreCase](using/functions/functionstartwithignorecase.md)
         + [substr](using/functions/functionsubstr.md)
         + [trim](using/functions/functiontrim.md)
         + [upper](using/functions/functionupper.md)
         + [uuid](using/functions/functionuuid.md)
+ Creazione dei rapporti{#journey-reports}
   + [Informazioni sui rapporti sui percorsi](using/reporting/about-journey-reports.md)
   + [Creazione dei rapporti sui percorsi](using/reporting/creating-your-journey-reports.md)
   + [Metriche e dimensioni](using/reporting/metrics-and-dimensions.md)
+ Integrazione con Intelligent Services{#use-case-advanced}
   + [Informazioni sull’integrazione con l’intelligenza artificiale](using/ai-services/ai-services-overview.md)
   + [Sfruttare IA per l&#39;analisi dei clienti](using/ai-services/leveraging-customer-ai.md)
+ Casi d’uso{#use-cases-journeys}
   + Invio di un’e-mail personalizzata{#use-case-simple}
      + [Informazioni sul caso d’uso semplice](using/usecase/about-the-simple-use-case.md)
      + [Configurazione dell’evento](using/usecase/configuring-the-event.md)
      + [Configurazione dell’origine dati](using/usecase/configuring-the-data-source.md)
      + [Creazione di un percorso](using/usecase/simple-uc-building-the-journey.md)
   + Creazione di un percorso cross-channel{#use-case-advanced}
      + [Informazioni sul caso d’uso avanzato](using/usecase/about-the-advanced-use-case.md)
      + [Configurazione degli eventi](using/usecase/configuring-the-events.md)
      + [Configurazione delle origini dati](using/usecase/configuring-the-data-sources.md)
      + [Creazione di un percorso](using/usecase/building-the-journey.md)
   + [Invio di un messaggio tramite Campaign v7/v8](using/usecase/campaign-classic-use-case.md)
   + [Passaggio dinamico delle raccolte tramite azioni personalizzate](using/usecase/collections.md)
+ Utilizzo delle API{#working-with-apis}
   + [Introduzione alle API dei percorsi](using/api/journeys-apis.md)
   + [API di limitazione di utilizzo](using/api/capping.md)
   + [API di limitazione](using/api/throttling.md)
