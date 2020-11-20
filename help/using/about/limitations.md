---
product: adobe campaign
solution: Journey Orchestration
title: Limitazioni per i Journey Orchestration
description: Ulteriori informazioni sui limiti degli Journey Orchestration
translation-type: tm+mt
source-git-commit: 57dc86d775bf8860aa09300cf2432d70c62a2993
workflow-type: tm+mt
source-wordcount: '268'
ht-degree: 2%

---


# Limitazioni {#limitations}

Di seguito sono riportati i limiti relativi all&#39;uso del Journey Orchestration.

## Limiti generali delle azioni

* Non c&#39;è alcun limite di invio. 
* In caso di errore vengono eseguiti sistematicamente due tentativi. Non è possibile regolare il numero di tentativi in base al messaggio di errore ricevuto. 
* L&#39;evento **Reaction** integrato consente di reagire alle azioni pronte all&#39;uso (consultate questa [pagina](../building-journeys/reaction-events.md)). Per reagire a un messaggio inviato tramite un&#39;azione personalizzata, è necessario configurare un evento dedicato. 
* Non esiste alcuna integrazione con i prodotti Adobe Campaign Classic.
 
## Limitazioni delle azioni personalizzate

* L&#39;URL azione personalizzata non supporta i parametri dinamici. 
* Sono supportati solo i metodi di chiamata POST e PUT. 
* Il nome del parametro o dell&#39;intestazione della query non deve iniziare con &quot;.&quot; o &quot;$&quot;. 
* Gli indirizzi IP non sono consentiti. 
* Indirizzi  Adobe interni (.adobe). non sono consentiti.
 

##  limitazioni delle azioni Adobe Campaign

*  messaggi transazionali Adobe Campaign Standard ha una scala di 50 000 messaggi all&#39;ora al massimo tra i canali per una determinata istanza. Consultate [Descrizione](https://helpx.adobe.com/it/legal/product-descriptions/campaign-standard.html)del prodotto Adobe Campaign Standard. 
* L&#39;attività di qualificazione **del** segmento non deve essere utilizzata insieme  messaggi transazionali Adobe Campaign Standard a causa di vincoli di throughput.
 
## Limiti eventi

* I dati di streaming utilizzati per avviare un percorso cliente devono essere configurati prima all&#39;interno del Journey Orchestration per ottenere un ID orchestrazione univoco. Questo ID orchestrazione deve essere aggiunto al payload in streaming in Adobe Experience Platform.
 

## Limiti delle origini dati

* Le origini dati esterne possono essere sfruttate nell&#39;ambito di un percorso con il cliente per cercare dati esterni in tempo reale. Queste origini devono essere utilizzabili tramite REST API, supportare JSON e poter gestire il volume di richieste.