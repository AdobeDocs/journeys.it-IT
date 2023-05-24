---
product: adobe campaign
title: Definizione dei parametri del messaggio
description: Scopri come definire i parametri dell’azione
feature: Journeys
role: User
level: Intermediate
exl-id: ea9cdb1d-dde6-4080-8f35-7f8cd3cf3644
source-git-commit: 7ce4ddec60f62662d67351b8ca70d7763e76b977
workflow-type: tm+mt
source-wordcount: '225'
ht-degree: 4%

---

# Definizione dei parametri del messaggio {#concept_wy4_bf1_2gb}

![](../assets/messageparameterssection.png)

In **[!UICONTROL Action parameters]** incolla un esempio del payload JSON da inviare al servizio esterno.

![](../assets/customactionpayloadmessage.png)

>[!NOTE]
>
>I nomi dei campi nel payload non possono contenere un &quot;.&quot; aggiuntivo. Non possono iniziare con il carattere &quot;$&quot;.

Potrai definire il tipo di parametro (ad esempio stringa, numero intero e così via).

Puoi anche scegliere se specificare se un parametro è una costante o una variabile:

* Costante significa che il valore del parametro è definito nel riquadro di configurazione dell’azione da un utente tecnico. Il valore sarà sempre lo stesso tra i percorsi. Non varia e l’addetto marketing non la vede quando utilizza l’azione personalizzata nel percorso. Potrebbe essere ad esempio un ID previsto dal sistema di terze parti. In tal caso, il campo a destra della costante/variabile di attivazione è il valore passato.
* Variabile significa che il valore del parametro varia. L’addetto marketing che utilizza questa azione personalizzata in un percorso sarà libero di trasmettere il valore desiderato o di specificare dove recuperare il valore per questo parametro (ad esempio dall’evento, dal Adobe Experience Platform, ecc.). In tal caso, il campo a destra della costante/variabile di attivazione è l’etichetta che l’addetto marketing vedrà nel percorso per denominare questo parametro.

![](../assets/customactionpayloadmessage2.png)
