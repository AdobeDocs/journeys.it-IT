---
product: adobe campaign
solution: Journey Orchestration
title: Campi di identità dell’evento di journeyStep
description: Campi di identità dell’evento di journeyStep
translation-type: tm+mt
source-git-commit: 57dc86d775bf8860aa09300cf2432d70c62a2993
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