---
title: getBestSendTime
description: Scopri la funzione getBestSendTime
page-status-flag: never-activated
uuid: 269d590c-5a6d-40b9-a879-02f5033863fc
contentOwner: sauviat
audience: rns
content-type: reference
topic-tags: journeys
discoiquuid: 5df34f55-135a-4ea8-afc2-f9427ce5ae7b
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: d6360d616199d597255610959432c7b93fd4e25c

---


# getBestSendTime {#getBestSendTime}

Fornisce un orario predittivo del momento migliore per la consegna di un&#39;e-mail a un singolo utente.

Questa funzione utilizza un punteggio calcolato nella piattaforma. La valutazione calcola la propensione a fare clic o aprire un messaggio e-mail in futuro in base al comportamento passato. L&#39;algoritmo che calcola il punteggio richiede una certa quantità di dati per funzionare. Di conseguenza, quando non dispone di dati sufficienti, si applica il tempo predefinito. Per ulteriori informazioni, vedi [](../building-journeys/wait-activity.md).

Per utilizzare questa funzione, è necessario uno [spazio dei nomi](../event/selecting-the-namespace.md) .

>[!NOTE]
>
>Il punteggio di tempo di invio migliore non può essere disponibile se non sono presenti dati sufficienti per eseguire il calcolo. In questo caso, al momento della pubblicazione verrà comunicato che si applica l&#39;ora predefinita.

## Categoria

Adobe Experience Platform

## Sintassi funzione

`getBestSendTime(<parameters>)`

## Parametri

| Parametro | Descrizione | Tipo |
|--- |--- |--- |
| quantità di tempo | Numero di ore da considerare dall&#39;ora corrente (max: 168) per ottimizzare l&#39;invio di e-mail | `<integer>` |
| tipo di ottimizzazione | &quot;open&quot; o &quot;click&quot; | `<string>` |
| tempo predefinito in ore di attesa | Se i punteggi del tempo di invio predittivo non sono disponibili | `<integer>` |

## Firma e tipo restituito

`getBestSendTime(<integer>,<string>,<integer>)`

Restituisce un dateTime.

## Esempio

getBestSendTime(12,&quot;open&quot;,8)

Spiegazione:

La funzione restituirà il tempo migliore per inviare un messaggio nelle prossime 12 ore, al fine di ottimizzare la probabilità che l&#39;utente nell&#39;istanza del viaggio lo apra. Se i dati non sono sufficienti per eseguire il calcolo, il tempo restituito è compreso tra 8 ore dall&#39;ora corrente.
