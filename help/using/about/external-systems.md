---
product: adobe campaign
solution: Journey Orchestration
title: Integrazione con sistemi esterni
description: Scopri le best practice per l’integrazione di sistemi esterni
feature: Journeys
role: User
level: Beginner
exl-id: 27859689-dc61-4f7a-b942-431cdf244455
source-git-commit: a32a208fcaef9a408c850c0ad74ab44e3eb44709
workflow-type: tm+mt
source-wordcount: '1014'
ht-degree: 1%

---

# Integrazione con sistemi esterni {#external-systems}

Questa pagina presenta le diverse protezioni fornite dal Journey Orchestration durante l&#39;integrazione di un sistema esterno, nonché le best practice: come ottimizzare la protezione del sistema esterno utilizzando l’API di limitazione dei tag, come configurare il timeout del percorso e come funzionano i nuovi tentativi.

Il Journey Orchestration consente di configurare connessioni a sistemi esterni tramite origini dati personalizzate e azioni personalizzate. Questo ti consente, ad esempio, di arricchire i tuoi percorsi con i dati provenienti da un sistema di prenotazione esterno, o di inviare messaggi utilizzando un sistema di terze parti come Epsilon o Facebook.

Quando si integra un sistema esterno, è possibile che si verifichino diversi problemi, il sistema può essere lento, può interrompere la risposta, o potrebbe non essere in grado di gestire un grande volume. Il Journey Orchestration offre diverse protezioni per proteggere il sistema dal sovraccarico.

Tutti i sistemi esterni sono diversi in termini di prestazioni. Devi adattare la configurazione ai tuoi casi d’uso.

Quando il Journey Orchestration esegue una chiamata a un’API esterna, le protezioni tecniche vengono eseguite come segue:

1. Vengono applicate le regole di limitazione: se viene raggiunto il tasso massimo, le chiamate rimanenti vengono scartate.

2. Timeout e nuovo tentativo: se la regola di limite viene soddisfatta, il Journey Orchestration tenta di eseguire la chiamata fino a quando non viene raggiunta la fine della durata del timeout.

## Limitazione{#capping}

L’API Capping integrata offre una protezione tecnica a monte che aiuta a proteggere il sistema esterno.

Per le origini dati esterne, il numero massimo di chiamate al secondo è impostato su 15. Se il numero di chiamate supera il 15 al secondo, le chiamate rimanenti vengono scartate. Puoi aumentare questo limite per le origini dati esterne private. Contatta l’Adobe per includere l’endpoint nell’inserire nell&#39;elenco Consentiti. Ciò non è possibile per le fonti di dati esterne pubbliche.

Per le azioni personalizzate, devi valutare la capacità dell’API esterna. Ad esempio, se Journey Optimizer invia 1000 chiamate al secondo e il sistema supporta solo 100 chiamate al secondo, è necessario definire una regola di limitazione in modo che il sistema non saturi.

Le regole di limitazione di utilizzo sono definite a livello di sandbox per un endpoint specifico (l’URL chiamato ). In fase di runtime, il Journey Orchestration verifica se è definita una regola di limite e applica il tasso definito durante le chiamate a tale endpoint. Se il numero di chiamate supera il tasso definito, le chiamate rimanenti vengono scartate e sono conteggiate come errori nel reporting.

Una regola di limitazione è specifica per un endpoint ma globale per tutti i percorsi di una sandbox. Ciò significa che gli slot di limitazione sono condivisi tra tutti i percorsi di una sandbox.

Ad esempio, supponiamo che tu abbia definito una regola di limitazione di 100 chiamate al secondo per il sistema esterno. Il sistema viene chiamato da un&#39;azione personalizzata in 10 percorsi diversi. Se un percorso riceve 200 chiamate al secondo, utilizzerà i 100 slot disponibili e scarterà i 100 slot rimanenti. Poiché la tariffa massima è stata superata, gli altri 9 percorsi non avranno più alcuna slot. Questa granularità aiuta a proteggere il sistema esterno da sovraccarichi e crash.

Per ulteriori informazioni sull’API di limitazione di utilizzo e su come configurare le regole di limitazione di utilizzo, consulta [questa pagina](../api/capping.md).

## Timeout e nuovi tentativi{#timeout}

Se la regola di limitazione è soddisfatta, viene applicata la regola di timeout.

In ogni percorso, puoi definire una durata di timeout. Questo consente di impostare una durata massima quando si chiama un sistema esterno. La durata del timeout è configurata nelle proprietà di un percorso. Consulta [questa pagina](../building-journeys/changing-properties.md#timeout_and_error).

Questo timeout è globale per tutte le chiamate esterne (chiamate API esterne in azioni personalizzate e origini dati personalizzate). Per impostazione predefinita, è impostato su 5 secondi.

Durante la durata di timeout definita, il Journey Orchestration cerca di chiamare il sistema esterno. Dopo la prima chiamata, è possibile eseguire un massimo di tre tentativi fino al raggiungimento della fine della durata di timeout. Impossibile modificare il numero di tentativi.

Ogni nuovo tentativo utilizza uno slot. Se hai un limite di 100 chiamate al secondo e ciascuna di esse richiede due tentativi, la frequenza scende a 30 chiamate al secondo (ogni chiamata utilizza 3 slot: la prima chiamata e due tentativi).

Il valore della durata del timeout dipende dal caso d’uso. Se desideri inviare il messaggio rapidamente, ad esempio quando il cliente entra nello store, non vuoi impostare un timeout lungo. Inoltre, più il timeout è lungo, più elementi saranno messi in coda. Questo può avere un notevole impatto sulle prestazioni. Se il Journey Orchestration esegue 1000 chiamate al secondo, mantenere 5 o 15 secondi di dati può rapidamente superare il sistema.

Prendiamo ad esempio un timeout di 5 secondi.

* La prima chiamata dura meno di 5 secondi: la chiamata ha esito positivo, non viene eseguito alcun nuovo tentativo.
* La prima chiamata dura più di 5 secondi: la chiamata è annullata e non vi sono tentativi. Viene conteggiato come errore di timeout nel reporting.
* La prima chiamata non riesce dopo 2 secondi (il sistema esterno restituisce un errore): Se sono disponibili degli slot di tappatura, rimangono 3 secondi per i nuovi tentativi.
   * Se uno dei tre tentativi ha esito positivo prima della fine dei 5 secondi, la chiamata viene eseguita e non si verifica alcun errore.
   * Se durante i nuovi tentativi viene raggiunta la fine della durata del timeout, la chiamata viene annullata e conteggiata come errore di timeout nel reporting.

## Domande frequenti{#faq}

**Come posso configurare una regola di limitazione? Esiste una regola di limitazione predefinita?**

Per impostazione predefinita, non è presente alcuna regola di limitazione. Le regole di limitazione di utilizzo sono definite a livello di sandbox per un endpoint specifico (l’URL chiamato ), utilizzando l’API di limitazione di utilizzo. Fai riferimento a [questa sezione](../about/external-systems.md#capping) e [questa pagina](../api/capping.md).

**Quanti tentativi vengono eseguiti? Posso cambiare il numero di tentativi o definire un periodo di attesa minimo tra i tentativi?**

Per una determinata chiamata, è possibile eseguire un massimo di tre tentativi dopo la prima chiamata, fino a quando la durata di timeout non viene raggiunta. Impossibile modificare il numero di tentativi e l&#39;intervallo di tempo tra ogni nuovo tentativo. Fai riferimento a [questa sezione](../about/external-systems.md#timeout).

**Dove posso configurare il timeout? Esiste un valore massimo?**

In ogni percorso, puoi definire una durata di timeout. La durata del timeout è configurata nelle proprietà di un percorso. La durata del timeout deve essere compresa tra 1 secondo e 30 secondi. Fai riferimento a [questa sezione](../about/external-systems.md#timeout) e [questa pagina](../building-journeys/changing-properties.md#timeout_and_error).