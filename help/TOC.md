---
product: Journeys
audience: end-user
user-guide-title: Guida di Journey Orchestration
index: true
translation-type: tm+mt
source-git-commit: ea891b40633378843a00a3ac56c6703f792d39e1

---


# Guida di Journey Orchestration {#using}

+ [Documentazione del prodotto](journey-orchestration-home.md)
+ Novità {#release-notes}
   + [Note sulla versione](using/release-notes/release-notes.md)
   + [Aggiornamenti alla documentazione](using/release-notes/documentation-updates.md)
+ Primi passi con Journey Orchestration {#starting-with-journeys}
   + [Informazioni su Journey Orchestration](using/about/about-journey-orchestration.md)
   + [Introduzione](using/about/get-started.md)
   + [Interfaccia utente](using/about/user-interface.md)
   + [Gestione degli accessi](using/about/access-management.md)
   + [Risoluzione dei problemi](using/about/troubleshooting.md)
+ Configurazione di un evento {#events-journeys}
   + [Informazioni sugli eventi](using/event/about-events.md)
   + [Informazioni sugli schemi ExperienceEvent](using/event/experience-event-schema.md)
   + [Definizione dei campi payload](using/event/defining-the-payload-fields.md)
   + [Selezione dello spazio dei nomi](using/event/selecting-the-namespace.md)
   + [Definizione del codice evento](using/event/defining-the-event-key.md)
   + [Aggiunta di una condizione](using/event/adding-a-condition.md)
   + [Anteprima del payload](using/event/previewing-the-payload.md)
   + [Passaggi aggiuntivi per l’invio di eventi](using/event/additional-steps-to-send-events-to-journey-orchestration.md)
+ Configurazione di un’origine dati {#data-source-journeys}
   + [Informazioni sulle origini dati](using/datasource/about-data-sources.md)
   + [Gruppi di campi](using/datasource/field-groups.md)
   + [Origine dati Adobe Experience Platform](using/datasource/adobe-experience-platform-data-source.md)
   + [Origini dati esterne](using/datasource/external-data-sources.md)
+ Configurazione di un’azione {#action-journeys}
   + [Informazioni sulle azioni](using/action/action.md)
   + [Utilizzo di Adobe Campaign](using/action/working-with-adobe-campaign.md)
   + Utilizzo di un sistema di terze parti {#action-third-party}
      + [Informazioni sulla configurazione delle azioni personalizzata](using/action/about-custom-action-configuration.md)
      + [Limitazioni delle azioni personalizzate](using/action/custom-action-limitations.md)
      + [Configurazione URL](using/action/url-configuration.md)
      + [Definizione dei parametri del messaggio](using/action/defining-the-message-parameters.md)
+ Creare un percorso {#building-journeys}
   + Informazioni sulla creazione di percorsi {#about-journey-building}
      + [Creazione di un percorso](using/building-journeys/journey.md)
      + [Utilizzo del designer del percorso](using/building-journeys/using-the-journey-designer.md)
      + [Modifica delle proprietà](using/building-journeys/changing-properties.md)
      + [Versioni del percorso](using/building-journeys/journey-versions.md)
      + [Terminazione di un percorso](using/building-journeys/terminating-a-journey.md)
      + [Gestione del fuso orario](using/building-journeys/timezone-management.md)
   + Attività {#about-journey-building}
      + [Eventi attività](using/building-journeys/event-activities.md)
      + Attività di orchestrazione {#orchestration-activities}
         + [Informazioni sulle attività di orchestrazione](using/building-journeys/about-orchestration-activities.md)
         + [Attività condizione](using/building-journeys/condition-activity.md)
         + [Attività fine](using/building-journeys/end-activity.md)
         + [Attività attendi](using/building-journeys/wait-activity.md)
      + Attività azione {#action-activities}
         + [Informazioni sulle attività azione](using/building-journeys/about-action-activities.md)
         + [Utilizzo delle azioni di Adobe Campaign](using/building-journeys/using-adobe-campaign-actions.md)
         + [Utilizzo di azioni personalizzate](using/building-journeys/using-custom-actions.md)
   + [Verifica del percorso](using/building-journeys/testing-the-journey.md)
   + [Pubblicazione del percorso](using/building-journeys/publishing-the-journey.md)
+ Utilizzo dell’editor di espressioni avanzate {#building-advanced-conditions-journeys}
   + [Informazioni sull’editor di espressioni avanzate](using/expression/expressionadvanced.md)
   + Sintassi {#syntax}
      + [Generalità](using/expression/generalities.md)
      + [Istruzione condizionale](using/expression/conditional-instruction.md)
      + [Tipi di dati](using/expression/data-types.md)
      + [Riferimenti campo](using/expression/field-references.md)
      + [Funzioni di gestione delle raccolte](using/expression/collection-management-functions.md)
      + [Operatori](using/expression/operators.md)
      + [Esempi](using/expression/advanced-editor-use-cases.md)
   + Funzioni {#main-functions-journey}
      + [Funzioni principali](using/expression/functions.md)
      + Adobe Experience Platform {#adobe-experience-platform}
         + [getBestSendTime](using/functions/functiongetbestsendtime.md)
         + [inSegment](using/functions/functioninsegment.md)
      + Aggregazione {#aggregation}
         + [avg](using/functions/functionavg.md)
         + [count](using/functions/functioncount.md)
         + [countOnlyNull](using/functions/functioncountonlynull.md)
         + [countWithNull](using/functions/functioncountwithnull.md)
         + [separateCount](using/functions/functiondistinctcount.md)
         + [distintoCountWithNull](using/functions/functiondistinctcountwithnull.md)
         + [max](using/functions/functionmax.md)
         + [min](using/functions/functionmin.md)
         + [sum](using/functions/functionsum.md)
      + Conversione {#conversion}
         + [toBool](using/functions/functiontobool.md)
         + [toDateTime](using/functions/functiontodatetime.md)
         + [toDateTimeOnly](using/functions/functiontodatetimeonly.md)
         + [toDecimal](using/functions/functiontodecimal.md)
         + [toDuration](using/functions/functiontoduration.md)
         + [toInteger](using/functions/functiontointeger.md)
         + [toString](using/functions/functiontostring.md)
      + Data {#date}
         + [currentTime&#x200B;InMillis](using/functions/functioncurrenttimeinmillis.md)
         + [inLastDays](using/functions/functioninlastdays.md)
         + [inLastHours](using/functions/functioninlasthours.md)
         + [inLastMonths](using/functions/functioninlastmonths.md)
         + [inLastYears](using/functions/functioninlastyears.md)
         + [inNextDays](using/functions/functioninnextdays.md)
         + [inNextHours](using/functions/functioninnexthours.md)
         + [inNextMonths](using/functions/functioninnextmonths.md)
         + [inNextYear](using/functions/functioninnextyears.md)
         + [now](using/functions/functionnow.md)
         + [nowWithDelta](using/functions/functionnowwithdelta.md)
         + [setHours](using/functions/functionsethours.md)
         + [setDays](using/functions/functionsetdays.md)
      + Elenco {#list}
         + [distinct](using/functions/functiondistinct.md)
         + [separateWithNull](using/functions/functiondistinctwithnull.md)
         + [in](using/functions/functionin.md)
         + [listSize](using/functions/functionlistsize.md)
         + [serializeList](using/functions/functionserializelist.md)
         + [sort](using/functions/functionsort.md)
      + Matematica {#math}
         + [random](using/functions/functionrandom.md)
         + [round](using/functions/functionround.md)
      + Stringa {#string}
         + [concat](using/functions/functionconcat.md)
         + [contain](using/functions/functioncontain.md)
         + [containWithIgnoreCase](using/functions/functioncontainwithignorecase.md)
         + [endWith](using/functions/functionendwith.md)
         + [endWithIgnorecase](using/functions/functionendwithignorecase.md)
         + [equalWithIgnoreCase](using/functions/functionequalignorecase.md)
         + [indexOf](using/functions/functionindexof.md)
         + [isEmpty](using/functions/functionisempty.md)
         + [isNotEmpty](using/functions/functionisnotempty.md)
         + [lastIndexOf](using/functions/functionlastindexof.md)
         + [length](using/functions/functionlength.md)
         + [Lower](using/functions/functionlower.md)
         + [matchRegExp](using/functions/functionmatchregexp.md)
         + [notEqualWithIgnoreCase](using/functions/functionnotequalignorecase.md)
         + [replace](using/functions/functionreplace.md)
         + [replaceAll](using/functions/functionreplaceall.md)
         + [startWith](using/functions/functionstartwith.md)
         + [startWithIgnoreCase](using/functions/functionstartwithignorecase.md)
         + [substr](using/functions/functionsubstr.md)
         + [trim](using/functions/functiontrim.md)
         + [top](using/functions/functionupper.md)
         + [uuid](using/functions/functionuuid.md)
+ Creazione dei rapporti{#journey-reports}
   + [Informazioni sui rapporti sui percorsi](using/reporting/about-journey-reports.md)
   + [Creazione dei rapporti sui percorsi](using/reporting/creating-your-journey-reports.md)
   + [Metriche e dimensioni](using/reporting/metrics-and-dimensions.md)
+ Casi d’uso{#use-cases-journeys}
   + Caso d’uso semplice{#use-case-simple}
      + [Informazioni sul caso d’uso semplice](using/usecase/about-the-simple-use-case.md)
      + [Configurazione dell’evento](using/usecase/configuring-the-event.md)
      + [Configurazione dell’origine dati](using/usecase/configuring-the-data-source.md)
      + [Creazione di un percorso](using/usecase/simple-uc-building-the-journey.md)
   + Caso d’uso avanzato{#use-case-advanced}
      + [Informazioni sul caso d’uso avanzato](using/usecase/about-the-advanced-use-case.md)
      + [Configurazione degli eventi](using/usecase/configuring-the-events.md)
      + [Configurazione delle origini dati](using/usecase/configuring-the-data-sources.md)
      + [Creazione di un percorso](using/usecase/building-the-journey.md)
   + [Sfruttare i punteggi di fatica](using/usecase/leveraging-fatigue-scores.md)

