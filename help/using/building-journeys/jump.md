---
product: adobe campaign
solution: Journey Orchestration
title: Passaggio da un percorso a un altro
description: Passaggio da un percorso a un altro
translation-type: tm+mt
source-git-commit: 9d8c3a2cf79f2b861aad61089a263a6a33a747b4
workflow-type: tm+mt
source-wordcount: '791'
ht-degree: 3%

---


# Passaggio da un percorso a un altro {#jump}

L&#39;attività di azione **[!UICONTROL Jump]** consente di inviare singoli utenti da un percorso all&#39;altro. Questa funzione consente di:

* semplificare la progettazione di percorsi molto complessi suddividendoli in più
* creare percorsi basati su pattern di percorso comuni e riutilizzabili

Nel percorso di origine, aggiungete semplicemente un&#39;attività **[!UICONTROL Jump]** e selezionate un percorso di destinazione. Quando l&#39;individuo entra nel passaggio **[!UICONTROL Jump]**, un evento interno viene inviato al primo evento del percorso di destinazione. Se l&#39;azione **[!UICONTROL Jump]** ha esito positivo, l&#39;utente continua a progredire nel percorso. Il comportamento è simile ad altre azioni.

Nel percorso di destinazione, il primo evento attivato internamente dall&#39;attività **[!UICONTROL Jump]** renderà il singolo flusso nel percorso.

>[!NOTE]
>
>Consultare anche il video di esercitazione [here](https://experienceleague.adobe.com/docs/journey-orchestration-learn/tutorials/building-a-journey/jumping-to-another-journey.html)

## Ciclo

Supponiamo che sia stata aggiunta un&#39;attività **[!UICONTROL Jump]** in un percorso A a un percorso B. Il percorso A è il **percorso di origine** e percorsi B, il **percorso di destinazione**.
Di seguito sono riportati i diversi passaggi del processo di esecuzione:

**Percorso** Ais attivato da un evento esterno:

1. Il percorso A riceve un evento esterno relativo a un individuo.
1. L&#39;individuo raggiunge il passaggio **[!UICONTROL Jump]**.
1. L&#39;individuo viene spinto al Percorso B e passa ai passi successivi del Percorso A, dopo il passaggio **[!UICONTROL Jump]**.

Nel percorso B, il primo evento viene attivato internamente, attraverso l&#39;attività **[!UICONTROL Jump]** dal percorso A:

1. Il percorso B ha ricevuto un evento interno dal Percorso A.
1. Il singolo inizia a scorrere nel Percorso B.

>[!NOTE]
>
>Il percorso B può essere attivato anche attraverso un evento esterno.

## Best practice e limitazioni

### Authoring

* L&#39;attività **[!UICONTROL Jump]** è disponibile solo nei percorsi che utilizzano uno spazio dei nomi.
* È possibile passare a un percorso che utilizza lo stesso spazio nomi del percorso di origine.
* Non è possibile passare a un percorso che inizia con un evento **Qualificazione segmento**.
* Non è possibile avere un&#39;attività **[!UICONTROL Jump]** e un evento **Qualificazione segmento** nello stesso percorso.
* Potete includere in un percorso tutte le attività **[!UICONTROL Jump]** necessarie. Dopo un **[!UICONTROL Jump]**, potete aggiungere qualsiasi attività necessaria.
* Puoi avere tutti i livelli di salto necessari. Ad esempio, l&#39;Percorso A passa all&#39;percorso B, che passa all&#39;percorsi C, e così via.
* Il percorso di destinazione può includere anche tutte le attività **[!UICONTROL Jump]** necessarie.
* I pattern di loop non sono supportati. Non esiste un modo per collegare due o più percorsi e creare un ciclo infinito. La schermata di configurazione dell&#39;attività **[!UICONTROL Jump]** vi impedisce di eseguire questa operazione.

### Execution

* Quando l&#39;attività **[!UICONTROL Jump]** viene eseguita, viene attivata l&#39;ultima versione del percorso di destinazione.
* Come al solito, un individuo unico può essere presente solo una volta nello stesso percorso. Di conseguenza, se il singolo push dal percorso di origine è già nel percorso di destinazione, l&#39;individuo non entrerà nel percorsi di destinazione. Nessun errore verrà segnalato nell&#39;attività **[!UICONTROL Jump]** perché si tratta di un comportamento normale.

## Configurazione dell&#39;attività Jump

1. Progettare il percorso **di origine**.

   ![](../assets/jump1.png)

1. In qualsiasi fase del percorso, aggiungete un&#39;attività **[!UICONTROL Jump]** dalla categoria **[!UICONTROL ACTIONS]**. Aggiungete un&#39;etichetta e una descrizione.

   ![](../assets/jump2.png)

1. Fare clic all&#39;interno del campo **percorso di destinazione**.
Nell&#39;elenco sono visualizzate tutte le versioni di percorso in bozza, live o in modalità di prova. Non sono disponibili percorsi che utilizzano uno spazio nomi diverso o che iniziano con un evento **Qualificazione segmento**. Vengono inoltre filtrati gli percorsi di destinazione che creerebbero un pattern di ciclo.

   ![](../assets/jump3.png)

   >[!NOTE]
   >
   >Potete fare clic sull&#39;icona **Apri percorso di destinazione** a destra per aprire il percorso di destinazione in una nuova scheda.

1. Selezionate il percorso di destinazione a cui desiderate passare.
Nel campo **Primo evento** viene precompilato il nome del percorso di destinazione  primo evento. Se il percorso di destinazione include più eventi, l&#39; **[!UICONTROL Jump]** è consentito solo per il primo evento.

   ![](../assets/jump4.png)

1. La sezione **Parametri azione** visualizza tutti i campi dell&#39;evento di destinazione. Allo stesso modo degli altri tipi di azioni, mappare ogni campo con campi dell&#39;evento di origine o dell&#39;origine dati. Queste informazioni verranno trasmesse al percorso di destinazione in fase di esecuzione.
1. Aggiungete le attività successive per completare il percorso di origine.

   ![](../assets/jump5.png)


   >[!NOTE]
   >
   >L&#39;identità dell&#39;individuo viene mappata automaticamente. Queste informazioni non sono visibili nell&#39;interfaccia.

L&#39;attività **[!UICONTROL Jump]** è configurata. Non appena il percorso è attivo o in modalità di prova, gli utenti che raggiungono il passaggio **[!UICONTROL Jump]** verranno spinti dal percorso di destinazione.

Quando un&#39;attività **[!UICONTROL Jump]** è configurata in un percorso, all&#39;inizio del percorso di destinazione viene automaticamente aggiunta un&#39;icona di voce **[!UICONTROL Jump]**. Questo consente di identificare che il percorso può essere attivato esternamente ma anche internamente da un&#39;attività **[!UICONTROL Jump]**.

![](../assets/jump7.png)

## Risoluzione dei problemi

Quando l’percorso viene pubblicato o in modalità di prova, si verificano degli errori se:
* il percorso di destinazione non esiste più
* il percorso di destinazione è bozza, chiuso o arrestato
* se il primo evento del percorso di destinazione è cambiato e la mappatura è interrotta

![](../assets/jump6.png)
