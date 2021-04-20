---
product: adobe campaign
solution: Journey Orchestration
title: Definizione dei parametri del messaggio
description: Scopri come definire i parametri del messaggio
feature: Journeys
role: Business Practitioner
level: Intermediate
translation-type: tm+mt
source-git-commit: ab19cc5a3d998d1178984c5028b1ba650d3e1292
workflow-type: tm+mt
source-wordcount: '214'
ht-degree: 3%

---


# Definizione dei parametri del messaggio {#concept_wy4_bf1_2gb}

![](../assets/messageparameterssection.png)

Nella sezione **[!UICONTROL Message parameters]** , incolla un esempio del payload JSON da inviare al servizio esterno.

![](../assets/customactionpayloadmessage.png)

Puoi definire il tipo di parametro (ad esempio: (stringa, numero intero, ecc.).

Puoi anche scegliere se specificare se un parametro è una costante o una variabile:

* Costante significa che il valore del parametro è definito nel riquadro di configurazione dell&#39;azione da un utente tecnico. Il valore sarà sempre lo stesso in tutti i percorsi. Non varia e l’addetto al marketing non lo vedrà quando utilizza l’azione personalizzata nel percorso. Potrebbe trattarsi, ad esempio, di un ID previsto dal sistema di terze parti. In tal caso, il valore passato è rappresentato dal campo a destra della costante/variabile di attivazione/disattivazione.
* Variabile indica che il valore del parametro varia. L’addetto al marketing che utilizza questa azione personalizzata in un percorso sarà libero di trasmettere il valore desiderato o di specificare dove recuperare il valore per questo parametro (ad esempio dall’evento, da Adobe Experience Platform, ecc.). In tal caso, il campo a destra della costante/variabile di attivazione è l’etichetta che l’addetto al marketing vedrà nel percorso per denominare questo parametro.

![](../assets/customactionpayloadmessage2.png)
