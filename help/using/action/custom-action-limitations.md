---
title: Limitazioni delle azioni personalizzate
description: Informazioni sulle limitazioni delle azioni personalizzate
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
source-git-commit: 2a55139697347ade80959f60bf52bfde39e43eb9
workflow-type: tm+mt
source-wordcount: '125'
ht-degree: 5%

---


# Limitazioni delle azioni personalizzate {#concept_lh2_df1_2gb}

Di seguito sono riportati alcuni limiti relativi all&#39;utilizzo di azioni personalizzate:

* Nessun buffer/levigamento del volume di invio.
* In caso di errore vengono eseguiti sistematicamente due tentativi. Non è possibile regolare il numero di tentativi in base al messaggio di errore ricevuto.
* L&#39; **[!UICONTROL Reaction]** evento incorporato consente di reagire alle azioni pronte all&#39;uso (vedere [](../building-journeys/reaction-events.md)). Per reagire a un messaggio inviato tramite un&#39;azione personalizzata, è necessario configurare un evento dedicato.
* L&#39;URL azione personalizzata non supporta i parametri dinamici.
* Sono supportati solo i metodi di chiamata POST e PUT.
* Il nome del parametro o dell&#39;intestazione della query non deve iniziare con &quot;.&quot; o &quot;$&quot;.
* Gli indirizzi IP non sono consentiti.
* Indirizzi  Adobe interni (.adobe). non sono consentiti.
