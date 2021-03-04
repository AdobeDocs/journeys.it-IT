---
product: adobe campaign
solution: Journey Orchestration
title: Limitazioni di Journey Orchestration
description: Ulteriori informazioni sulle limitazioni di Journey Orchestration
translation-type: tm+mt
source-git-commit: a0b6f54e37abded690dc200bc3a901a8e0f04f79
workflow-type: tm+mt
source-wordcount: '527'
ht-degree: 2%

---


# Limitazioni {#limitations}

Di seguito sono riportate alcune limitazioni relative all’utilizzo di Journey Orchestration.

## Limiti generali delle azioni

* Non esiste alcuna limitazione di invio. 
* In caso di errore vengono eseguiti sistematicamente due tentativi. Non è possibile regolare il numero di tentativi in base al messaggio di errore ricevuto. 
* L&#39;evento incorporato **Reaction** consente di reagire alle azioni predefinite (consulta questa [pagina](../building-journeys/reaction-events.md)). Se desideri reagire a un messaggio inviato tramite un’azione personalizzata, devi configurare un evento dedicato. 
* Non esiste un’integrazione con i prodotti Adobe Campaign Classic.

## Limitazioni delle versioni del percorso {#journey-versions-limitations}

* un percorso che inizia con un’attività evento nella versione v1 non può iniziare con un elemento diverso da un evento in ulteriori versioni. Non puoi avviare un percorso con un evento **Qualificazione del segmento** .
* un percorso che inizia con un&#39;attività **Qualifica segmento** in v1 deve sempre iniziare con una **Qualificazione segmento** in ulteriori versioni.
* Il segmento e lo spazio dei nomi scelti in **Qualificazione del segmento** (primo nodo) non possono essere modificati nelle nuove versioni.
* La regola di rientro deve essere la stessa in tutte le versioni del percorso.

## Qualificazione del segmento {#segment-qualification}

* L’attività **Qualificazione del segmento** non può essere utilizzata insieme alla messaggistica transazionale Adobe Campaign Standard a causa di vincoli di throughput. Consulta [Descrizione del prodotto Adobe Campaign Standard](https://helpx.adobe.com/it/legal/product-descriptions/campaign-standard.html). 
 

## Limitazioni delle azioni personalizzate

* L&#39;URL dell&#39;azione personalizzata non supporta i parametri dinamici. 
* Sono supportati solo i metodi di chiamata POST e PUT . 
* Il nome del parametro o dell&#39;intestazione della query non deve iniziare con &quot;.&quot; o &quot;$&quot;. 
* Gli indirizzi IP non sono consentiti. 
* Indirizzi Adobe interni (.adobe). non sono consentiti.
 

## Limiti delle azioni di Adobe Campaign

* I messaggi transazionali di Adobe Campaign Standard hanno una scala massima di 50.000 messaggi all’ora su tutti i canali per una determinata istanza. Consulta [Descrizione del prodotto Adobe Campaign Standard](https://helpx.adobe.com/legal/product-descriptions/campaign-standard.html). 
 

## Limiti degli eventi

* Per gli eventi generati dal sistema, i dati in streaming utilizzati per avviare un percorso del cliente devono prima essere configurati in Customer Journey Management per ottenere un ID di orchestrazione univoco. Questo ID di orchestrazione deve essere aggiunto al payload di streaming in Adobe Experience Platform. Questa limitazione non si applica agli eventi basati su regole.
 

## Limiti delle origini dati

* Le origini dati esterne possono essere utilizzate all’interno del percorso del cliente per cercare dati esterni in tempo reale. Queste sorgenti devono essere utilizzabili tramite API REST, supportare JSON e poter gestire il volume di richieste.

## Percorsi che iniziano contemporaneamente alla creazione di un profilo {#journeys-limitation-profile-creation}

In Adobe Experience Platform si verifica un ritardo associato alla creazione/aggiornamento di profili basati su API. L’obiettivo a livello di servizio (SLT) in termini di latenza è &lt; 1 minuto dall’acquisizione al profilo unificato per il 95° percentile delle richieste, con un volume di 20.000 richieste al secondo (RPS).

Se un percorso viene attivato simultaneamente per la creazione di un profilo e controlla/recupera immediatamente le informazioni dal servizio profili, potrebbe non funzionare correttamente.

Puoi scegliere una delle due soluzioni seguenti:

* Aggiungi un’attività di attesa dopo il primo evento, per dare ad Adobe Experience Platform il tempo necessario per eseguire l’acquisizione nel servizio profili.

* Imposta un percorso che non sfrutta immediatamente il profilo. Ad esempio, se il percorso è progettato per confermare la creazione di un account, l’evento esperienza potrebbe contenere le informazioni necessarie per inviare il primo messaggio di conferma (nome, cognome, indirizzo e-mail, ecc.).