---
product: adobe campaign
solution: Journey Orchestration
title: Integrazione con sistemi esterni
description: Scopri le best practice per l’integrazione di sistemi esterni
feature: Journeys
role: Business Practitioner
level: Beginner
exl-id: 27859689-dc61-4f7a-b942-431cdf244455
source-git-commit: a25ff95e0b74d3a0693310179670c7fe7b0de51c
workflow-type: tm+mt
source-wordcount: '530'
ht-degree: 0%

---

# Integrazione con sistemi esterni {#external-systems}

Questa pagina presenta le diverse protezioni fornite dal Journey Orchestration durante l&#39;integrazione di un sistema esterno, nonché le best practice: come ottimizzare la protezione del sistema esterno con l’API di limitazione, come configurare il timeout del percorso e come funzionano i nuovi tentativi.

Il Journey Orchestration consente di configurare connessioni a sistemi esterni tramite origini dati personalizzate e azioni personalizzate. Questo ti consente, ad esempio, di arricchire i tuoi percorsi con i dati provenienti da un sistema di prenotazione esterno o di inviare messaggi utilizzando sistemi di terze parti come Epsilon o Facebook.

Quando si integra un sistema esterno, è possibile che si verifichino diversi problemi, il sistema può essere lento, può interrompere la risposta, o potrebbe non essere in grado di gestire un grande volume. Il Journey Orchestration offre diverse protezioni per proteggere il sistema dal sovraccarico.

Tutti i sistemi esterni sono diversi in termini di prestazioni. Devi adattare la configurazione a ogni caso d’uso.

Quando il Journey Orchestration esegue una chiamata a un’API esterna, le protezioni tecniche vengono eseguite come segue:

1. Limitazione: vengono applicate le regole di limitazione
2. Timeout e nuovo tentativo:

## Limitazione

L’API Capping integrata offre una protezione tecnica a monte che contribuirà a proteggere il sistema esterno. In precedenza, devi valutare la capacità dell’API esterna. Ad esempio, se Journey Orchestration invia 1000 chiamate al secondo e il sistema supporta solo 100 chiamate al secondo, devi definire una regola di limitazione in modo che il sistema non saturi.

Le regole di limitazione sono definite a livello di sanddox per un endpoint specifico (URL chiamato). In fase di runtime, il Journey Orchestration verifica se è definita una regola di limite e applica il tasso definito durante le chiamate a tale endpoint. Se il numero di chiamate supera il tasso definito, le chiamate rimanenti vengono scartate.

Una regola di limitazione è specifica per un endpoint ma globale per tutti i percorsi di una sandbox. Ciò significa che gli slot di chiamata sono condivisi tra tutti i percorsi di una sandbox. Ad esempio, supponiamo che il sistema esterno disponga di un limite definito di 100 chiamate al secondo ed è richiamato da un’azione personalizzata in 10 percorsi diversi. Se un percorso riceve 200 chiamate al secondo, manterrà disponibili i 100 slot e scarterà i 100 slot rimanenti. Poiché la tariffa massima è già superata, gli altri 9 percorsi non avranno alcun slot disponibile. Questa granularità aiuta a proteggere il sistema esterno da sovraccarichi e crash.

Una chiamata scartata a causa dei limiti massimi viene conteggiata come un errore nel reporting.

Per informazioni su come configurare le regole di limitazione, consulta [questa pagina](../api/timezone-management.md).

## Timeout e nuovi tentativi

Ensuite -> timeout defini, et qui definir le temps maximal qu&#39;on aloue a lappel au sys externe. Ciondolo ce temps là, su essaie de faire des appels. Su fait un appel, si l&#39;appel dure moinre longtemps que le timeout ca marche, si più longtemps su voit ca comme une timeout error, et coté reporting compabilisé comme une erreur. si l&#39;appel echoue, (planter sur 500 ou autre), riprovare. 3 tentativi max., pas configurabile. SI può superare le time outglobal (par esle 2 essais, mais depasse le timeout) erreur de timeout. plsu de temps que Necaire. Timeout durata max qu&#39;on alloue un appel et aux retry è un errore.

