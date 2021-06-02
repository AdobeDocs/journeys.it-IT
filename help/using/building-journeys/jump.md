---
product: adobe campaign
title: Passaggio da un percorso a un altro
description: Passaggio da un percorso a un altro
feature: Journeys
role: Business Practitioner
level: Intermediate
exl-id: 520376aa-2cb5-46d6-8f21-3e03544f5da1
source-git-commit: 712f66b2715bac0af206755e59728c95499fa110
workflow-type: tm+mt
source-wordcount: '792'
ht-degree: 3%

---

# Passaggio da un percorso a un altro {#jump}

L’attività di azione **[!UICONTROL Jump]** ti consente di inviare singoli utenti da un percorso all’altro. Questa funzione consente di:

* semplificare la progettazione di percorsi molto complessi suddividendoli in più
* creare percorsi basati su modelli di percorso comuni e riutilizzabili

Nel percorso di origine, è sufficiente aggiungere un’attività **[!UICONTROL Jump]** e selezionare un percorso di destinazione. Quando l’utente accede al passaggio **[!UICONTROL Jump]** , viene inviato un evento interno al primo evento del percorso di destinazione. Se l’azione **[!UICONTROL Jump]** ha esito positivo, l’utente continua a progredire nel percorso. Il comportamento è simile ad altre azioni.

Nel percorso di destinazione, il primo evento attivato internamente dall’attività **[!UICONTROL Jump]** farà sì che il singolo flusso nel percorso.

>[!NOTE]
>
>Fai riferimento anche al video tutorial [qui](https://experienceleague.adobe.com/docs/journey-orchestration-learn/tutorials/building-a-journey/jumping-to-another-journey.html)

## Ciclo di vita

Supponiamo che tu abbia aggiunto un&#39;attività **[!UICONTROL Jump]** in un percorso A a un percorso B. Il Percorso A è il **percorso di origine** e il percorso B, il **percorso di destinazione**.
Di seguito sono riportati i diversi passaggi del processo di esecuzione:

**L’** Ais del percorso viene attivato da un evento esterno:

1. Il percorso A riceve un evento esterno relativo a un individuo.
1. L’utente raggiunge il passaggio **[!UICONTROL Jump]** .
1. L’utente viene inviato al Percorso B e passa ai passaggi successivi nel Percorso A, dopo il passaggio **[!UICONTROL Jump]** .

Nel percorso B, il primo evento viene attivato internamente, tramite l&#39;attività **[!UICONTROL Jump]** dal percorso A:

1. Il percorso B ha ricevuto un evento interno dal Percorso A.
1. L&#39;individuo inizia a fluire nel Percorso B.

>[!NOTE]
>
>Il percorso B può essere attivato anche tramite un evento esterno.

## Best practice e limitazioni

### Authoring

* L’attività **[!UICONTROL Jump]** è disponibile solo nei percorsi che utilizzano uno spazio dei nomi.
* Puoi passare solo a un percorso che utilizza lo stesso namespace del percorso di origine.
* Non puoi passare a un percorso che inizia con un evento **Qualificazione del segmento** .
* Non puoi avere un&#39;attività **[!UICONTROL Jump]** e un evento **Qualificazione del segmento** nello stesso percorso.
* Puoi includere in un percorso tutte le attività **[!UICONTROL Jump]** necessarie. Dopo un **[!UICONTROL Jump]**, puoi aggiungere qualsiasi attività necessaria.
* Puoi avere tutti i livelli di salto necessari. Ad esempio, il Percorso A passa al percorso B, che passa al percorso C e così via.
* Il percorso di destinazione può anche includere tutte le attività **[!UICONTROL Jump]** necessarie.
* I pattern di loop non sono supportati. Non c&#39;è modo di collegare due o più percorsi che creerebbero un ciclo infinito. La schermata di configurazione dell’attività **[!UICONTROL Jump]** ti impedisce di eseguire questa operazione.

### Execution

* Quando l’attività **[!UICONTROL Jump]** viene eseguita, viene attivata la versione più recente del percorso di destinazione.
* Come al solito, un individuo unico può essere presente solo una volta nello stesso percorso. Di conseguenza, se l’individuo inviato dal percorso di origine è già nel percorso di destinazione, l’utente non entrerà nel percorso di destinazione. Nell’attività **[!UICONTROL Jump]** non verrà segnalato alcun errore, in quanto si tratta di un comportamento normale.

## Configurazione dell’attività Jump

1. Progetta il tuo **percorso di origine**.

   ![](../assets/jump1.png)

1. In qualsiasi fase del percorso, aggiungi un’attività **[!UICONTROL Jump]** dalla categoria **[!UICONTROL ACTIONS]** . Aggiungi un’etichetta e una descrizione.

   ![](../assets/jump2.png)

1. Fai clic all&#39;interno del campo **percorso di destinazione** .
Nell’elenco sono visualizzate tutte le versioni di percorso 2D, live o in modalità di test. I percorsi che utilizzano un namespace diverso o che iniziano con un evento **Qualificazione del segmento** non sono disponibili. Vengono inoltre filtrati i percorsi di destinazione che creerebbero un pattern di ciclo.

   ![](../assets/jump3.png)

   >[!NOTE]
   >
   >Fai clic sull&#39;icona **Apri percorso di destinazione** a destra per aprire il percorso di destinazione in una nuova scheda.

1. Seleziona il percorso di destinazione a cui desideri passare.
Il campo **Primo evento** è precompilato con il nome del primo evento del percorso di destinazione. Se il percorso di destinazione include più eventi, il **[!UICONTROL Jump]** è consentito solo sul primo evento.

   ![](../assets/jump4.png)

1. La sezione **Parametri azione** visualizza tutti i campi dell&#39;evento di destinazione. Allo stesso modo degli altri tipi di azioni, mappa ogni campo con campi dell’evento di origine o dell’origine dati. Queste informazioni verranno trasmesse al percorso di destinazione in fase di esecuzione.
1. Aggiungi le attività successive per completare il percorso di origine.

   ![](../assets/jump5.png)


   >[!NOTE]
   >
   >L&#39;identità dell&#39;individuo viene mappata automaticamente. Queste informazioni non sono visibili nell’interfaccia.

L’attività **[!UICONTROL Jump]** è configurata. Non appena il percorso è attivo o in modalità di test, i singoli utenti che raggiungono il passaggio **[!UICONTROL Jump]** verranno inviati dal al percorso di destinazione.

Quando un&#39;attività **[!UICONTROL Jump]** viene configurata in un percorso, all&#39;inizio del percorso di destinazione viene aggiunta automaticamente un&#39;icona di ingresso **[!UICONTROL Jump]** . Questo ti aiuta a identificare che il percorso può essere attivato esternamente ma anche internamente da un&#39;attività **[!UICONTROL Jump]**.

![](../assets/jump7.png)

## Risoluzione dei problemi

Quando il percorso viene pubblicato o in modalità di test, si verificano degli errori se:
* il percorso di destinazione non esiste più
* il percorso di destinazione è bozza, chiuso o interrotto
* se il primo evento del percorso di destinazione è cambiato e la mappatura è interrotta

![](../assets/jump6.png)
