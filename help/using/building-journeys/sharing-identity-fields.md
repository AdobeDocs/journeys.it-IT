---
product: adobe campaign
solution: Journey Orchestration
title: Campi di identità dell’evento di journeyStep
description: Campi di identità dell’evento di journeyStep
feature: Journeys
role: Business Practitioner
level: Intermediate
translation-type: tm+mt
source-git-commit: ab19cc5a3d998d1178984c5028b1ba650d3e1292
workflow-type: tm+mt
source-wordcount: '63'
ht-degree: 19%

---


# Campi di identità dell’evento di journeyStep {#sharing-identity-fields}

Questo mixin è specifico per journeyStepEvent: questo evento è in relazione al percorso e non ha identityMap che descrive l&#39;eventuale identità del profilo.

Per journeyStepEvent, è inoltre necessario aggiungere campi relativi all’identità:

## profileID

Identificatore profilo

Tipo: string

## profileNamespace

Spazio dei nomi dell’identificatore del profilo

Tipo: string