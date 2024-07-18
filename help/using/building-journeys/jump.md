---
product: adobe campaign
title: Passaggio da un percorso a un altro
description: Passaggio da un percorso a un altro
feature: Journeys
role: User
level: Intermediate
exl-id: 520376aa-2cb5-46d6-8f21-3e03544f5da1
source-git-commit: 185c2296a51f58e2092787edcc35ee9e4242bec8
workflow-type: tm+mt
source-wordcount: '785'
ht-degree: 6%

---

# Passaggio da un percorso a un altro {#jump}

L&#39;attività Azione **[!UICONTROL Jump]** consente di inviare singoli utenti da un percorso all&#39;altro. Questa funzione consente di:

* semplificare la progettazione di percorsi molto complessi suddividendoli in diversi percorsi più semplici;
* creare percorsi basati su pattern di percorso comuni e riutilizzabili.

Nel percorso di origine, è sufficiente aggiungere un&#39;attività **[!UICONTROL Jump]** e selezionare un percorso di destinazione. Quando l&#39;utente accede al passaggio **[!UICONTROL Jump]**, un evento interno viene inviato al primo evento del percorso di destinazione. Se l&#39;azione **[!UICONTROL Jump]** ha esito positivo, l&#39;utente continua ad avanzare nel percorso. Il comportamento è simile ad altre azioni.

Nel percorso di destinazione, il primo evento attivato internamente dall&#39;attività **[!UICONTROL Jump]** genererà il singolo flusso nel percorso.

>[!NOTE]
>
>Fai riferimento anche al video tutorial [qui](https://experienceleague.adobe.com/docs/journey-orchestration-learn/tutorials/building-a-journey/jumping-to-another-journey.html?lang=it)

## Ciclo di vita

Si supponga di aver aggiunto un&#39;attività **[!UICONTROL Jump]** in un percorso A a un percorso B. Il Percorso A è il **percorso di origine** e il percorso B, il **percorso di destinazione**.
Di seguito sono riportati i diversi passaggi del processo di esecuzione:

**Il Percorso A** è attivato da un evento esterno:

1. Il percorso A riceve un evento esterno correlato a un individuo.
1. L&#39;utente raggiunge il passaggio **[!UICONTROL Jump]**.
1. L&#39;utente viene inviato al Percorso B e passa ai passaggi successivi nel Percorso A, dopo il passaggio **[!UICONTROL Jump]**.

Nel percorso B, il primo evento viene attivato internamente, tramite l&#39;attività **[!UICONTROL Jump]** dal percorso A:

1. Il percorso B ha ricevuto un evento interno dal Percorso A.
1. L&#39;individuo inizia a fluire nel Percorso B.

>[!NOTE]
>
>Il percorso B può essere attivato anche tramite un evento esterno.

## Best practice e limitazioni

### Authoring

* L&#39;attività **[!UICONTROL Jump]** è disponibile solo nei percorsi che utilizzano uno spazio dei nomi.
* È possibile passare solo a un percorso che utilizza lo stesso spazio dei nomi del percorso di origine.
* Non puoi passare a un percorso che inizia con un evento di **qualificazione del segmento**.
* Non puoi avere un&#39;attività **[!UICONTROL Jump]** e un evento di qualificazione del segmento **nello stesso percorso.**
* Puoi includere in un percorso tutte le **[!UICONTROL Jump]** attività necessarie. Dopo **[!UICONTROL Jump]**, puoi aggiungere qualsiasi attività necessaria.
* Puoi avere tutti i livelli di salto necessari. Il Percorso A, ad esempio, passa al percorso B, che passa al percorso C e così via.
* Il percorso di destinazione può inoltre includere tutte le attività **[!UICONTROL Jump]** necessarie.
* I pattern di loop non sono supportati. Non è possibile collegare due o più percorsi per creare un ciclo infinito. La schermata di configurazione dell&#39;attività **[!UICONTROL Jump]** impedisce di eseguire questa operazione.

### Execution

* Quando l&#39;attività **[!UICONTROL Jump]** viene eseguita, viene attivata la versione più recente del percorso di destinazione.
* Come sempre, un individuo può essere presente solo una volta nello stesso percorso. Di conseguenza, se l’individuo inviato dal percorso di origine è già nel percorso target, non entrerà in tale percorso. Non verrà segnalato alcun errore nell&#39;attività **[!UICONTROL Jump]** perché si tratta di un comportamento normale.

## Configurazione dell’attività Salta

1. Progetta il tuo **percorso di origine**.

   ![](../assets/jump1.png)

1. In qualsiasi passaggio del percorso, aggiungere un&#39;attività **[!UICONTROL Jump]** dalla categoria **[!UICONTROL ACTIONS]**. Aggiungi un’etichetta e una descrizione.

   ![](../assets/jump2.png)

1. Fai clic nel campo **percorso di destinazione**.
L’elenco mostra tutte le versioni del percorso che sono bozza, live o in modalità di test. I percorsi che utilizzano uno spazio dei nomi diverso o che iniziano con un evento di **qualificazione del segmento** non sono disponibili. Anche i percorsi target che creerebbero un pattern di loop vengono filtrati.

   ![](../assets/jump3.png)

   >[!NOTE]
   >
   >Puoi fare clic sull&#39;icona **Apri percorso di destinazione**, a destra, per aprire il percorso di destinazione in una nuova scheda.

1. Selezionare il percorso di destinazione in cui si desidera passare.
Il campo **Primo evento** è precompilato con il nome del primo evento del percorso di destinazione. Se il percorso di destinazione include più eventi, **[!UICONTROL Jump]** è consentito solo per il primo evento.

   ![](../assets/jump4.png)

1. La sezione **Parametri azione** visualizza tutti i campi dell&#39;evento di destinazione. Come per altri tipi di azioni, mappa ogni campo con i campi dell’evento di origine o dell’origine dati. Queste informazioni verranno passate al percorso target in fase di runtime.
1. Aggiungi le attività successive per completare il percorso di origine.

   ![](../assets/jump5.png)


   >[!NOTE]
   >
   >L’identità dell’individuo viene mappata automaticamente. Queste informazioni non sono visibili nell’interfaccia.

L&#39;attività **[!UICONTROL Jump]** è configurata. Non appena il percorso è attivo o in modalità di test, i singoli utenti che raggiungono il passaggio **[!UICONTROL Jump]** verranno inviati dal al percorso di destinazione.

Quando un&#39;attività **[!UICONTROL Jump]** è configurata in un percorso, viene aggiunta automaticamente un&#39;icona di voce **[!UICONTROL Jump]** all&#39;inizio del percorso di destinazione. Questo consente di identificare che il percorso può essere attivato esternamente ma anche internamente da un&#39;attività **[!UICONTROL Jump]**.

![](../assets/jump7.png)

## Risoluzione dei problemi

Quando il percorso viene pubblicato o in modalità di test, si verificano degli errori se:
* il percorso target non esiste più
* il percorso di destinazione è bozza, chiuso o interrotto
* se il primo evento del percorso target è stato modificato e la mappatura è interrotta

![](../assets/jump6.png)
