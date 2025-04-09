---
product: adobe campaign
solution: Journey Orchestration
title: Integrazione con sistemi esterni
description: Scopri le best practice per l’integrazione di sistemi esterni
feature: Journeys
role: User
level: Beginner
exl-id: e39218bd-fa6e-443f-9843-92b7a07070fa
source-git-commit: 69471a36b113e04a7bb0953a90977ad4020299e4
workflow-type: tm+mt
source-wordcount: '1084'
ht-degree: 5%

---

# Integrazione con sistemi esterni {#external-systems}


>[!CAUTION]
>
>**Ricerca di Adobe Journey Optimizer**? Fai clic [qui](https://experienceleague.adobe.com/it/docs/journey-optimizer/using/ajo-home){target="_blank"} per la documentazione di Journey Optimizer.
>
>
>_Questa documentazione fa riferimento ai materiali Journey Orchestration legacy che sono stati sostituiti da Journey Optimizer. Contatta il team del tuo account in caso di domande sull&#39;accesso a Journey Orchestration o Journey Optimizer._



Questa pagina presenta i diversi guardrail forniti da Journey Orchestration durante l’integrazione di un sistema esterno, nonché le best practice: come ottimizzare la protezione del sistema esterno utilizzando l’API di limitazione di utilizzo, come configurare il timeout del percorso e come funzionano i nuovi tentativi.

Journey Orchestration consente di configurare connessioni a sistemi esterni tramite origini dati e azioni personalizzate. Ciò ti consente, ad esempio, di arricchire i tuoi percorsi con dati provenienti da un sistema di prenotazione esterno o di inviare messaggi utilizzando un sistema di terze parti come Epsilon o Facebook.

Quando si integra un sistema esterno, è possibile riscontrare diversi problemi, il sistema può essere lento, può smettere di rispondere o potrebbe non essere in grado di gestire un volume di grandi dimensioni. Journey Orchestration offre diversi guardrail per proteggere il sistema dal sovraccarico.

Tutti i sistemi esterni sono diversi in termini di prestazioni. Devi adattare la configurazione ai tuoi casi d’uso.

Quando Journey Orchestration esegue una chiamata a un’API esterna, i guardrail tecnici vengono eseguiti come segue:

1. Vengono applicate le regole di limite: se viene raggiunta la tariffa massima, le chiamate rimanenti vengono scartate.

2. Timeout e riprova: se la regola di limite viene soddisfatta, Journey Orchestration tenta di eseguire la chiamata fino al raggiungimento della fine della durata del timeout.

## Limiti{#capping}

L’API Capping integrata offre un guardrail tecnico a monte che aiuta a proteggere il sistema esterno.

Per le origini dati esterne, il numero massimo di chiamate al secondo è impostato su 15. Se il numero di chiamate supera 15 al secondo, le chiamate rimanenti vengono scartate. Puoi aumentare questo limite per le origini dati esterne private. Contatta Adobe per includere l’endpoint nel inserisco nell&#39;elenco Consentiti di. Questo non è possibile per le origini dati esterne pubbliche.

Per le azioni personalizzate, devi valutare la capacità dell’API esterna. Ad esempio, se Journey Optimizer invia 1000 chiamate al secondo e il sistema supporta solo 100 chiamate al secondo, devi definire una regola di limite in modo che il sistema non si saturi.

Le regole di limitazione di utilizzo sono definite a livello di sandbox per un endpoint specifico (URL denominato). In fase di runtime, Journey Orchestration verifica se è stata definita una regola di limite e applica la tariffa definita durante le chiamate all’endpoint. Se il numero di chiamate supera il tasso definito, le chiamate rimanenti vengono scartate e conteggiate come errori nella generazione dei rapporti.

Una regola di limite è specifica per un endpoint, ma globale per tutti i percorsi di una sandbox. Ciò significa che gli slot di limitazione sono condivisi tra tutti i percorsi di una sandbox.

Ad esempio, supponiamo che tu abbia definito una regola di limitazione di 100 chiamate al secondo per il sistema esterno. Il sistema viene chiamato da un’azione personalizzata in 10 percorsi diversi. Se un percorso riceve 200 chiamate al secondo, utilizza i 100 slot disponibili ed elimina i 100 slot rimanenti. Poiché il limite massimo è stato superato, gli altri 9 percorsi non avranno più alcuno slot. Questa granularità aiuta a proteggere il sistema esterno da sovraccarichi e arresti anomali.

Per ulteriori informazioni sull&#39;API per la limitazione di utilizzo e su come configurare le regole per la limitazione di utilizzo, vedere [questa pagina](../api/capping.md).

## Timeout e nuovi tentativi{#timeout}

Se la regola di limite è soddisfatta, viene applicata la regola di timeout.

In ogni percorso, puoi definire una durata di timeout. Questo consente di impostare una durata massima quando si chiama un sistema esterno. La durata del timeout è configurata nelle proprietà di un percorso. Consulta [questa pagina](../building-journeys/changing-properties.md#timeout_and_error).

Questo timeout è globale per tutte le chiamate esterne (chiamate API esterne nelle azioni personalizzate e nelle origini dati personalizzate). Per impostazione predefinita è impostato su 5 secondi.

Durante la durata di timeout definita, Journey Orchestration tenta di chiamare il sistema esterno. Dopo la prima chiamata, è possibile eseguire un massimo di tre tentativi fino al raggiungimento della durata di timeout finale. Impossibile modificare il numero di tentativi.

Ogni nuovo tentativo utilizza uno slot. Se hai un limite massimo di 100 chiamate al secondo e ciascuna chiamata richiede due tentativi, la frequenza scende a 30 chiamate al secondo (ogni chiamata utilizza 3 slot: la prima chiamata e due tentativi).

Il valore della durata del timeout dipende dal caso d’uso. Se desideri inviare il messaggio rapidamente, ad esempio quando il client entra nell’archivio, non impostare un timeout prolungato. Inoltre, più è lungo il timeout, più elementi saranno messi in coda. Questo può avere un notevole impatto sulle prestazioni. Se Journey Orchestration esegue 1000 chiamate al secondo, la conservazione di 5 o 15 secondi di dati può sopraffare rapidamente il sistema.

Prendiamo un esempio per un timeout di 5 secondi.

* La prima chiamata dura meno di 5 secondi: la chiamata ha esito positivo e non viene eseguito un nuovo tentativo.
* La prima chiamata dura più di 5 secondi: la chiamata viene annullata e non è possibile riprovare. Viene conteggiato come errore di timeout nel reporting.
* La prima chiamata non riesce dopo 2 secondi (il sistema esterno restituisce un errore): rimangono 3 secondi per i nuovi tentativi, se sono disponibili slot di limitazione.
   * Se uno dei tre tentativi ha esito positivo prima della fine dei 5 secondi, la chiamata viene eseguita e non si verifica alcun errore.
   * Se durante i nuovi tentativi viene raggiunta la fine della durata del timeout, la chiamata viene annullata e conteggiata come un errore di timeout nel reporting.

## Domande frequenti{#faq}

**Come si configura una regola di limitazione di utilizzo? Esiste una regola di limite predefinita?**

Per impostazione predefinita, non esiste alcuna regola di limite. Le regole di limitazione di utilizzo sono definite a livello di sandbox per un endpoint specifico (l’URL denominato), utilizzando l’API di limitazione di utilizzo. Consulta [questa sezione](../about/external-systems.md#capping) e [questa pagina](../api/capping.md).

**Quanti tentativi vengono eseguiti? Posso cambiare il numero di tentativi o definire un periodo di attesa minimo tra un nuovo tentativo e l&#39;altro?**

Per una determinata chiamata, è possibile eseguire un massimo di tre tentativi dopo la prima chiamata, fino al raggiungimento della durata di timeout finale. Non è possibile modificare il numero di tentativi e l’intervallo tra un tentativo e l’altro. Fai riferimento a [questa sezione](../about/external-systems.md#timeout).

**Dove posso configurare il timeout? Esiste un valore massimo?**

In ogni percorso, puoi definire una durata di timeout. La durata del timeout è configurata nelle proprietà di un percorso. La durata del timeout deve essere compresa tra 1 e 30 secondi. Consulta [questa sezione](../about/external-systems.md#timeout) e [questa pagina](../building-journeys/changing-properties.md#timeout_and_error).
