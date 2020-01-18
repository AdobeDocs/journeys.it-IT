---
title: Gestione degli accessi
description: Ulteriori informazioni sulla gestione degli accessi
page-status-flag: never-activated
uuid: 269d590c-5a6d-40b9-a879-02f5033863fc
contentOwner: sauviat
audience: rns
content-type: reference
topic-tags: journeys
discoiquuid: 5df34f55-135a-4ea8-afc2-f9427ce5ae7b
translation-type: tm+mt
source-git-commit: fed6fd8d8ee497ec47727f7297dc72f319fabe27

---


# Gestione degli accessi{#concept_rfj_wpt_52b}

## Informazioni sulla gestione degli accessi {#about-access-management}

I profili di prodotto sono assegnati a un set di utenti che condividono gli stessi diritti all&#39;interno dell&#39;organizzazione.

In Admin Console, puoi assegnare agli utenti uno dei seguenti profili di prodotto out-of-the-box:

* **[!UICONTROL Limited Access User]**: utente con accesso in sola lettura ai viaggi e ai rapporti. Questo profilo di prodotto include i seguenti diritti:
   * Lettura dei viaggi
   * Lettura dei rapporti

* **[!UICONTROL Administrators]**: utente con accesso ai menu di amministrazione con la possibilità di gestire viaggi, eventi e rapporti. Questo profilo di prodotto include i seguenti diritti:
   * Gestione ed esecuzione dei viaggi
   * Gestione di eventi, origini dati e azioni
   * Gestire i rapporti
   >[!NOTE]
   >
   >**[!UICONTROL Administrators]**è l&#39;unico profilo di prodotto che consente la creazione, l&#39;edizione e la pubblicazione di messaggi transazionali (o modelli di messaggistica) in Adobe Campaign Standard. Questo profilo di prodotto è necessario se usi Adobe Campaign Standard per inviare messaggi durante i tuoi viaggi.

* **[!UICONTROL Standard User]**: utente con accesso di base, ad esempio gestione del percorso. Questo profilo di prodotto include i seguenti diritti:
   * Gestione ed esecuzione dei viaggi
   * Gestire i rapporti

Puoi trovare [qui](../assets/do-not-localize/acs_rights_journeys.pdf) la compatibilità tra i diritti e le diverse funzionalità dell&#39;Orchestrazione del viaggio.

## Assegnazione di un profilo di prodotto {#assigning-product-profile}

I profili di prodotto vengono gestiti in Admin Console. Per ulteriori informazioni, consulta la documentazione [di](https://helpx.adobe.com/enterprise/managing/user-guide.html)Admin Console.

Per assegnare un profilo di prodotto a un utente per accedere all&#39;orchestrazione del percorso:

1. In Admin Console, seleziona **[!UICONTROL Journey orchestration]**.

   ![](../assets/user_management.png)

1. Selezionate il profilo di prodotto a cui verrà collegato il nuovo utente.

   ![](../assets/user_management_2.png)

1. Clic **[!UICONTROL Add user]**.

   Potete anche aggiungere il nuovo utente a un gruppo di utenti per ottimizzare il set di autorizzazioni condiviso. Per ulteriori informazioni, consultare questa [pagina](https://helpx.adobe.com/enterprise/using/user-groups.html).

   ![](../assets/user_management_3.png)

1. Digitate l&#39;indirizzo e-mail del nuovo utente e fate clic su **[!UICONTROL Save]**.

   ![](../assets/user_management_4.png)

L&#39;utente deve quindi ricevere un&#39;e-mail di reindirizzamento all&#39;istanza di Orchestrazione del viaggio.