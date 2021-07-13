---
product: adobe campaign
title: Limitazioni del Journey Orchestration
description: Ulteriori informazioni sui limiti dei Journey Orchestration
feature: Percorsi
role: User
level: Beginner
exl-id: 27859689-dc61-4f7a-b942-431cdf244455
source-git-commit: 185c2296a51f58e2092787edcc35ee9e4242bec8
workflow-type: tm+mt
source-wordcount: '519'
ht-degree: 2%

---

# Limitazioni  {#limitations}

Di seguito sono riportate le limitazioni relative all’utilizzo del Journey Orchestration.

## Limiti generali delle azioni

* Non esiste alcuna limitazione di invio. 
* In caso di errore vengono eseguiti sistematicamente tre tentativi. Non è possibile regolare il numero di tentativi in base al messaggio di errore ricevuto. 
* L&#39;evento incorporato **Reaction** consente di reagire alle azioni predefinite (consulta questa [pagina](../building-journeys/reaction-events.md)). Se desideri reagire a un messaggio inviato tramite un’azione personalizzata, devi configurare un evento dedicato. 

## Limitazioni delle versioni di percorso {#journey-versions-limitations}

* Un percorso che inizia con un’attività evento nella versione 1 non può iniziare con un elemento diverso da un evento in ulteriori versioni. Non è possibile avviare un percorso con un evento **Qualificazione del segmento**.
* Un percorso che inizia con un&#39;attività **Qualifica segmento** nella versione 1 deve sempre iniziare con una **Qualificazione segmento** in ulteriori versioni.
* Il segmento e lo spazio dei nomi scelti in **Qualificazione del segmento** (primo nodo) non possono essere modificati nelle nuove versioni.
* La regola di rientro deve essere la stessa in tutte le versioni del percorso.

## Qualificazione del segmento {#segment-qualification}

* L&#39;attività **Qualificazione del segmento** non può essere utilizzata insieme alla messaggistica transazionale Adobe Campaign Standard a causa di vincoli di throughput. Consulta [Descrizione del prodotto Adobe Campaign Standard](https://helpx.adobe.com/it/legal/product-descriptions/campaign-standard.html). 
 

## Limitazioni delle azioni personalizzate

* L&#39;URL dell&#39;azione personalizzata non supporta i parametri dinamici. 
* Sono supportati solo i metodi di chiamata POST e PUT. 
* Il nome del parametro o dell&#39;intestazione della query non deve iniziare con &quot;.&quot; oppure &quot;$&quot;. 
* Gli indirizzi IP non sono consentiti. 
* Indirizzi di Adobe interni (.adobe.) non sono consentiti.
 

## Limitazioni delle azioni Adobe Campaign

* I messaggi transazionali Adobe Campaign Standard hanno una scala massima di 50.000 messaggi all&#39;ora su tutti i canali per una determinata istanza. Consulta [Descrizione del prodotto Adobe Campaign Standard](https://helpx.adobe.com/legal/product-descriptions/campaign-standard.html). 
 

## Limiti degli eventi

* Per gli eventi generati dal sistema, i dati di streaming utilizzati per avviare un percorso cliente devono essere configurati prima all’interno del Journey Orchestration per ottenere un ID di orchestrazione univoco. Questo ID di orchestrazione deve essere aggiunto al payload di streaming in Adobe Experience Platform. Questa limitazione non si applica agli eventi basati su regole.
 

## Limiti delle origini dati

* Le origini dati esterne possono essere utilizzate all’interno di un percorso di clienti per cercare dati esterni in tempo reale. Queste sorgenti devono essere utilizzabili tramite API REST, supportare JSON e poter gestire il volume di richieste.

## Percorsi che iniziano contemporaneamente alla creazione di un profilo {#journeys-limitation-profile-creation}

In Adobe Experience Platform si verifica un ritardo associato alla creazione/aggiornamento dei profili basati su API. L’obiettivo a livello di servizio (SLT) in termini di latenza è &lt; 1 minuto dall’acquisizione al profilo unificato per il 95° percentile delle richieste, con un volume di 20.000 richieste al secondo (RPS).

Se un Percorso viene attivato simultaneamente per la creazione di un profilo e controlla/recupera immediatamente le informazioni dal Servizio profili, potrebbe non funzionare correttamente.

Puoi scegliere una delle due soluzioni seguenti:

* Aggiungi un’attività di attesa dopo il primo evento, per dare a Adobe Experience Platform il tempo necessario per eseguire l’acquisizione in Profile Service.

* Imposta un percorso che non sfrutta immediatamente il profilo. Ad esempio, se il percorso è progettato per confermare la creazione di un account, l’evento esperienza potrebbe contenere le informazioni necessarie per inviare il primo messaggio di conferma (nome, cognome, indirizzo e-mail, ecc.).
