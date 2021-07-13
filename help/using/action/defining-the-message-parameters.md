---
product: adobe campaign
title: Definizione dei parametri del messaggio
description: Scopri come definire i parametri del messaggio
feature: Percorsi
role: User
level: Intermediate
exl-id: ea9cdb1d-dde6-4080-8f35-7f8cd3cf3644
source-git-commit: 185c2296a51f58e2092787edcc35ee9e4242bec8
workflow-type: tm+mt
source-wordcount: '220'
ht-degree: 4%

---

# Definizione dei parametri del messaggio {#concept_wy4_bf1_2gb}

![](../assets/messageparameterssection.png)

Nella sezione **[!UICONTROL Message parameters]** , incolla un esempio del payload JSON da inviare al servizio esterno.

![](../assets/customactionpayloadmessage.png)

>[!NOTE]
>
>I nomi di campo nel payload non possono contenere un &quot;.&quot; aggiuntivo.

Puoi definire il tipo di parametro (ad esempio: (stringa, numero intero, ecc.).

Puoi anche scegliere se specificare se un parametro è una costante o una variabile:

* Costante significa che il valore del parametro è definito nel riquadro di configurazione dell&#39;azione da un utente tecnico. Il valore sarà sempre lo stesso in tutti i percorsi. Non varia e l’addetto al marketing non lo vedrà quando utilizza l’azione personalizzata nel percorso. Potrebbe trattarsi, ad esempio, di un ID previsto dal sistema di terze parti. In tal caso, il valore passato è rappresentato dal campo a destra della costante/variabile di attivazione/disattivazione.
* Variabile indica che il valore del parametro varia. L’addetto al marketing che utilizza questa azione personalizzata in un percorso sarà libero di trasmettere il valore desiderato o di specificare dove recuperare il valore per questo parametro (ad esempio dall’evento, da Adobe Experience Platform, ecc.). In tal caso, il campo a destra della costante/variabile di attivazione è l’etichetta che l’addetto al marketing vedrà nel percorso per denominare questo parametro.

![](../assets/customactionpayloadmessage2.png)
