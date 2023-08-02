---
product: adobe campaign
title: Limitazioni del Journey Orchestration
description: Ulteriori informazioni sulle limitazioni del Journey Orchestration
feature: Journeys
role: User
level: Beginner
exl-id: fef039ae-c04d-4198-a082-4be27710255f
source-git-commit: 861c6bd8ce65793b6009e220d88f105c75ea3008
workflow-type: tm+mt
source-wordcount: '567'
ht-degree: 66%

---

# Limitazioni  {#limitations}

Di seguito sono riportate le limitazioni relative all’utilizzo del Journey Orchestration.

## Guardrail di percorso generale {#journeys-guardrails-journeys}

* Il numero di attività in un percorso è limitato a 50. Il numero di attività viene visualizzato nella sezione in alto a sinistra dell’area di lavoro del percorso.
* Il numero di **percorsi live** in un’organizzazione è limitato a 100 per sandbox. Una volta raggiunto questo limite, non puoi più pubblicare un nuovo percorso.

## Limitazioni delle azioni generali

* In caso di errore vengono eseguiti sistematicamente tre tentativi. Non è possibile regolare il numero di tentativi in base al messaggio di errore ricevuto. 
* Il sistema integrato **Reazione** consente di reagire alle azioni predefinite (vedi questo [pagina](../building-journeys/reaction-events.md)). Se desideri reagire a un messaggio inviato tramite un’azione personalizzata, devi configurare un evento dedicato. 

## Limitazioni delle versioni di percorso {#journey-versions-limitations}

* Un percorso che inizia con un’attività evento nella versione v1, nelle altre versioni non può iniziare con un elemento diverso. Non è possibile avviare un percorso con un evento **Qualificazione del segmento**.
* Un percorso che inizia con un’attività di **Qualificazione del segmento** nella versione v1 deve sempre iniziare con una **Qualificazione del segmento** nelle altre versioni.
* Segmento e spazio dei nomi scelti in **Qualificazione del segmento** (primo nodo) non può essere modificato nelle nuove versioni.
* La regola di rientro deve essere la stessa in tutte le versioni del percorso.

## Qualificazione del segmento {#segment-qualification}

* Il **Qualificazione del segmento** L’attività non può essere utilizzata insieme a Adobe Campaign Standard Transactional Messaging a causa di vincoli di velocità effettiva. Consulta [Descrizione del prodotto Adobe Campaign Standard](https://helpx.adobe.com/it/legal/product-descriptions/campaign-standard.html). 
 
## Limitazioni delle azioni personalizzate

* L’URL dell’azione personalizzata non supporta i parametri dinamici. 
* Sono supportati solo i metodi di chiamata POST e PUT. 
* Il nome del parametro o dell’intestazione della query non deve iniziare con “.” oppure “$”. 
* Gli indirizzi IP non sono consentiti. 
* Gli indirizzi interni di Adobe (.adobe.) non sono consentiti.
 
## Limitazioni delle azioni di Adobe Campaign

* La messaggistica transazionale di Adobe Campaign Standard ha una scala massima di 50.000 messaggi all’ora sui canali per una determinata istanza. Consulta [Descrizione del prodotto Adobe Campaign Standard](https://helpx.adobe.com/it/legal/product-descriptions/campaign-standard.html). 
 
## Limitazioni degli eventi

* Per gli eventi generati dal sistema, i dati in streaming utilizzati per avviare un percorso di clienti devono essere configurati prima all’interno del Journey Orchestration per ottenere un ID di orchestrazione univoco. Questo ID di orchestrazione deve essere aggiunto al payload di streaming in Adobe Experience Platform. Questa limitazione non si applica agli eventi basati su regole.
 
## Limitazioni delle origini dati

* Le origini dati esterne possono essere sfruttate all’interno di un percorso di clienti per ricercare dati esterni in tempo reale. Queste origini devono essere utilizzabili tramite API REST, supportare JSON ed essere in grado di gestire il volume delle richieste.

## Percorsi che iniziano contemporaneamente alla creazione di un profilo {#journeys-limitation-profile-creation}

In Adobe Experience Platform si verifica un ritardo associato alla creazione/aggiornamento dei profili basati su API. Il target livello di servizio (Service Level Target, SLT) in termini di latenza è &lt; di 1 minuto dall’acquisizione al profilo unificato per il 95° percentile delle richieste, con un volume di 20.000 richieste al secondo (RPS).

Se un Percorso viene attivato simultaneamente per la creazione di un profilo e immediatamente controlla/recupera le informazioni dal servizio profili, potrebbe non funzionare correttamente.

Puoi scegliere una delle due soluzioni seguenti:

* Aggiungi un’attività di attesa dopo il primo evento, per dare ad Adobe Experience Platform il tempo necessario per eseguire l’acquisizione nel servizio profilo.

* Impostare un percorso che non sfrutta immediatamente il profilo. Ad esempio, se il percorso è progettato per confermare la creazione di un account, l’evento esperienza potrebbe contenere le informazioni necessarie per inviare il primo messaggio di conferma (nome, cognome, indirizzo e-mail, ecc).
