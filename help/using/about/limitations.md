---
product: adobe campaign
title: Limitazioni di Journey Orchestration
description: Ulteriori informazioni sulle limitazioni di Journey Orchestration
feature: Journeys
role: User
level: Beginner
exl-id: fef039ae-c04d-4198-a082-4be27710255f
source-git-commit: 69471a36b113e04a7bb0953a90977ad4020299e4
workflow-type: tm+mt
source-wordcount: '637'
ht-degree: 60%

---

# Limitazioni {#limitations}


>[!CAUTION]
>
>**Stai cercando Adobe Journey Optimizer**? Fai clic [qui](https://experienceleague.adobe.com/it/docs/journey-optimizer/using/ajo-home){target="_blank"} per la documentazione di Journey Optimizer.
>
>
>_Questa documentazione fa riferimento ai precedenti materiali su Journey Orchestration, che è stato sostituito da Journey Optimizer. In caso di domande sull’accesso a Journey Orchestration o Journey Optimizer, contatta il team del tuo account._



Di seguito sono riportate le limitazioni relative all’utilizzo di Journey Orchestration.

## Guardrail di percorso generale {#journeys-guardrails-journeys}

* Il numero di attività in un percorso è limitato a 50. Il numero di attività viene visualizzato nella sezione in alto a sinistra dell’area di lavoro del percorso.
* Il numero di **percorsi live** in un’organizzazione è limitato a 100 per sandbox. Una volta raggiunto questo limite, non puoi più pubblicare un nuovo percorso.

## Limitazioni delle azioni generali

* In caso di errore vengono eseguiti sistematicamente tre tentativi. Non è possibile regolare il numero di tentativi in base al messaggio di errore ricevuto. 
* L&#39;evento predefinito **Reaction** ti consente di reagire alle azioni predefinite (vedi questa [pagina](../building-journeys/reaction-events.md)). Se desideri reagire a un messaggio inviato tramite un’azione personalizzata, devi configurare un evento dedicato. 

## Limitazioni delle versioni di percorso {#journey-versions-limitations}

* Un percorso che inizia con un’attività evento nella versione v1, nelle altre versioni non può iniziare con un elemento diverso. Non è possibile avviare un percorso con un evento **Qualificazione segmento**.
* Un percorso che inizia con un’attività **Qualificazione segmento** nella versione v1 deve sempre iniziare con un’attività **Qualificazione segmento** nelle altre versioni.
* Il segmento e lo spazio dei nomi scelti nella **Qualificazione del segmento** (primo nodo) non possono essere modificati nelle nuove versioni.
* La regola di reingresso deve essere la stessa in tutte le versioni del percorso.

## Qualificazione segmento {#segment-qualification}

* L&#39;attività **Qualificazione del segmento** non può essere utilizzata in combinazione con Adobe Campaign Standard Transactional Messaging a causa di vincoli di velocità effettiva. Vedi [Descrizione del prodotto Adobe Campaign Standard](https://helpx.adobe.com/it/legal/product-descriptions/campaign-standard.html). 
 
## Limitazioni delle azioni personalizzate

* L’URL dell’azione personalizzata non supporta i parametri dinamici. 
* Sono supportati solo i metodi di chiamata POST e PUT. 
* Il nome del parametro o dell’intestazione della query non deve iniziare con “.” o “$”. 
* Gli indirizzi IP non sono consentiti. 
* Indirizzi interni di Adobe (.adobe.) non sono consentiti.
 
## Limitazioni delle azioni di Adobe Campaign

* La messaggistica transazionale di Adobe Campaign Standard ha una scala massima di 50.000 messaggi all’ora sui canali per una determinata istanza. Vedi [Descrizione del prodotto Adobe Campaign Standard](https://helpx.adobe.com/it/legal/product-descriptions/campaign-standard.html). 
 
## Limitazioni degli eventi

* Per gli eventi generati dal sistema, i dati in streaming utilizzati per avviare un percorso di clienti devono essere configurati prima in Journey Orchestration per ottenere un ID di orchestrazione univoco. Questo ID di orchestrazione deve essere aggiunto al payload di streaming in Adobe Experience Platform. Questa limitazione non si applica agli eventi basati su regole.
 
## Limitazioni delle origini dati

* Le origini dati esterne possono essere sfruttate all’interno di un percorso di clienti per ricercare dati esterni in tempo reale. Queste origini devono essere utilizzabili tramite API REST, supportare JSON ed essere in grado di gestire il volume delle richieste.

## Percorsi che iniziano contemporaneamente alla creazione di un profilo {#journeys-limitation-profile-creation}

In Adobe Experience Platform si verifica un ritardo associato alla creazione/aggiornamento dei profili basati su API. Il target livello di servizio (Service Level Target, SLT) in termini di latenza è &lt; di 1 minuto dall’acquisizione al profilo unificato per il 95° percentile delle richieste, con un volume di 20.000 richieste al secondo (RPS).

Se un Percorso viene attivato simultaneamente per la creazione di un profilo e immediatamente controlla/recupera le informazioni dal servizio profili, potrebbe non funzionare correttamente.

Puoi scegliere una delle due soluzioni seguenti:

* Aggiungi un’attività di attesa dopo il primo evento, per dare ad Adobe Experience Platform il tempo necessario per eseguire l’acquisizione nel servizio profilo.

* Impostare un percorso che non sfrutta immediatamente il profilo. Ad esempio, se il percorso è progettato per confermare la creazione di un account, l’evento esperienza potrebbe contenere le informazioni necessarie per inviare il primo messaggio di conferma (nome, cognome, indirizzo e-mail, ecc.).
