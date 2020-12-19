---
product: adobe campaign
solution: Journey Orchestration
title: Definizione dei parametri del messaggio
description: Scopri come definire i parametri dei messaggi
translation-type: tm+mt
source-git-commit: 57dc86d775bf8860aa09300cf2432d70c62a2993
workflow-type: tm+mt
source-wordcount: '210'
ht-degree: 3%

---


# Definizione dei parametri del messaggio {#concept_wy4_bf1_2gb}

![](../assets/messageparameterssection.png)

Nella sezione **[!UICONTROL Message parameters]**, incollate un esempio del payload JSON da inviare al servizio esterno.

![](../assets/customactionpayloadmessage.png)

Sarà possibile definire il tipo di parametro (ad es.: stringa, numero intero, ecc.).

È inoltre possibile specificare se un parametro è una costante o una variabile:

* Costante indica che il valore del parametro è definito nel riquadro di configurazione dell&#39;azione da un utente tecnico. Il valore sarà sempre lo stesso per tutti i viaggi. Non varia e l’esperto di marketing non lo vedrà quando utilizza l’azione personalizzata nel percorso. Potrebbe trattarsi, ad esempio, di un ID previsto dal sistema di terze parti. In tal caso, il campo a destra della costante/variabile di attivazione/disattivazione è il valore passato.
* Variabile indica che il valore del parametro varia. L’esperto di marketing che utilizza questa azione personalizzata in un viaggio sarà libero di passare il valore desiderato o di specificare dove recuperare il valore per questo parametro (ad esempio dall’evento, dall’Adobe Experience Platform, ecc.). In tal caso, il campo a destra della costante/variabile di attivazione è l’etichetta che l’esperto di marketing vedrà durante il percorso per denominare questo parametro.

![](../assets/customactionpayloadmessage2.png)
