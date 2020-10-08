---
title: Campi di identità dell’evento di journeyStep
description: Campi di identità dell’evento di journeyStep
page-status-flag: never-activated
uuid: 269d590c-5a6d-40b9-a879-02f5033863fc
contentOwner: sauviat
audience: rns
content-type: reference
topic-tags: journeys
discoiquuid: 5df34f55-135a-4ea8-afc2-f9427ce5ae7b
translation-type: tm+mt
source-git-commit: b852c08a488a1bec02b8b31a1fccf1a8773b99af
workflow-type: tm+mt
source-wordcount: '59'
ht-degree: 20%

---


# Campi di identità dell’evento di journeyStep {#sharing-identity-fields}

Questo mixin è specifico per pathStepEvent: questo evento è correlato al viaggio e non dispone della mappa identità, che descrive l&#39;eventuale identità del profilo.

Per pathStepEvent, è inoltre necessario aggiungere campi correlati all&#39;identità:

## profileID

Identificatore profilo

Tipo: string

## profileNamespace

Spazio dei nomi degli identificatori del profilo

Tipo: string