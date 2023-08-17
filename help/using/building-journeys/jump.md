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
source-wordcount: '791'
ht-degree: 6%

---

# Passaggio da un percorso a un altro {#jump}

Il **[!UICONTROL Jump]** L’attività action ti consente di inviare singoli utenti da un percorso all’altro. Questa funzione consente di:

* semplificare la progettazione di percorsi molto complessi suddividendoli in diversi percorsi più semplici;
* creare percorsi basati su pattern di percorso comuni e riutilizzabili.

Nel percorso di origine, aggiungi semplicemente un **[!UICONTROL Jump]** e selezionare un percorso target. Quando l’individuo entra nel **[!UICONTROL Jump]** passaggio, un evento interno viene inviato al primo evento del percorso target. Se il **[!UICONTROL Jump]** l&#39;azione è riuscita, la persona continua a progredire nel percorso. Il comportamento è simile ad altre azioni.

Nel percorso di destinazione, il primo evento attivato internamente da **[!UICONTROL Jump]** L&#39;attività creerà il singolo flusso nel percorso.

>[!NOTE]
>
>Fai riferimento anche al video tutorial [qui](https://experienceleague.adobe.com/docs/journey-orchestration-learn/tutorials/building-a-journey/jumping-to-another-journey.html?lang=it)

## Ciclo di vita

Supponiamo che tu abbia aggiunto un **[!UICONTROL Jump]** attività in un percorso A a un percorso B. Il Percorso A è il **percorso di origine** e percorso B, **percorso target**.
Di seguito sono riportati i diversi passaggi del processo di esecuzione:

**PERCORSO A** viene attivato da un evento esterno:

1. Il percorso A riceve un evento esterno correlato a un individuo.
1. L’individuo raggiunge il **[!UICONTROL Jump]** passaggio.
1. L’individuo viene spinto al Percorso B e passa ai passaggi successivi nel Percorso A, dopo **[!UICONTROL Jump]** passaggio.

Nel percorso B, il primo evento viene attivato internamente tramite **[!UICONTROL Jump]** attività dal percorso A:

1. Il percorso B ha ricevuto un evento interno dal Percorso A.
1. L&#39;individuo inizia a fluire nel Percorso B.

>[!NOTE]
>
>Il percorso B può essere attivato anche tramite un evento esterno.

## Best practice e limitazioni

### Authoring

* Il **[!UICONTROL Jump]** L’attività è disponibile solo nei percorsi che utilizzano uno spazio dei nomi.
* È possibile passare solo a un percorso che utilizza lo stesso spazio dei nomi del percorso di origine.
* Non è possibile passare a un percorso che inizia con **Qualificazione del segmento** evento.
* Non è possibile avere **[!UICONTROL Jump]** attività e un **Qualificazione del segmento** nello stesso percorso.
* Puoi includere quanti più **[!UICONTROL Jump]** attività necessarie in un percorso. Dopo un **[!UICONTROL Jump]**, puoi aggiungere qualsiasi attività necessaria.
* Puoi avere tutti i livelli di salto necessari. Il Percorso A, ad esempio, passa al percorso B, che passa al percorso C e così via.
* Il percorso target può includere anche **[!UICONTROL Jump]** attività in base alle esigenze.
* I pattern di loop non sono supportati. Non è possibile collegare due o più percorsi per creare un ciclo infinito. Il **[!UICONTROL Jump]** impedisci questa operazione nella schermata di configurazione dell’attività.

### Esecuzione

* Quando **[!UICONTROL Jump]** viene eseguita l&#39;attività, viene attivata la versione più recente del percorso target.
* Come sempre, un individuo può essere presente solo una volta nello stesso percorso. Di conseguenza, se l’individuo inviato dal percorso di origine è già nel percorso target, non entrerà in tale percorso. Non verrà segnalato alcun errore in **[!UICONTROL Jump]** perché si tratta di un comportamento normale.

## Configurazione dell’attività Salta

1. Progettare **percorso di origine**.

   ![](../assets/jump1.png)

1. In qualsiasi passaggio del percorso, aggiungi un **[!UICONTROL Jump]** attività, da **[!UICONTROL ACTIONS]** categoria. Aggiungi un’etichetta e una descrizione.

   ![](../assets/jump2.png)

1. Fai clic all’interno del **Percorso di destinazione** campo.
L’elenco mostra tutte le versioni del percorso che sono bozza, live o in modalità di test. Percorsi che utilizzano uno spazio dei nomi diverso o che iniziano con un **Qualificazione del segmento** evento non sono disponibili. Anche i percorsi target che creerebbero un pattern di loop vengono filtrati.

   ![](../assets/jump3.png)

   >[!NOTE]
   >
   >Puoi fare clic su **Apri percorso di destinazione** sul lato destro, per aprire il percorso target in una nuova scheda.

1. Selezionare il percorso di destinazione in cui si desidera passare.
Il **Primo evento** viene precompilato con il nome del primo evento del percorso target. Se il percorso target include più eventi, il **[!UICONTROL Jump]** è consentito solo sul primo evento.

   ![](../assets/jump4.png)

1. Il **Parametri azione** mostra tutti i campi dell’evento target. Come per altri tipi di azioni, mappa ogni campo con i campi dell’evento di origine o dell’origine dati. Queste informazioni verranno passate al percorso target in fase di runtime.
1. Aggiungi le attività successive per completare il percorso di origine.

   ![](../assets/jump5.png)


   >[!NOTE]
   >
   >L’identità dell’individuo viene mappata automaticamente. Queste informazioni non sono visibili nell’interfaccia.

Il tuo **[!UICONTROL Jump]** attività è configurata. Non appena il percorso è attivo o in modalità di test, gli utenti che raggiungono **[!UICONTROL Jump]** il passaggio verrà inviato dal al percorso target.

Quando un **[!UICONTROL Jump]** l’attività è configurata in un percorso, un **[!UICONTROL Jump]** l&#39;icona di ingresso viene aggiunta automaticamente all&#39;inizio del percorso target. Questo consente di identificare che il percorso può essere attivato esternamente ma anche internamente da un **[!UICONTROL Jump]** attività.

![](../assets/jump7.png)

## Risoluzione dei problemi

Quando il percorso viene pubblicato o in modalità di test, si verificano degli errori se:
* il percorso target non esiste più
* il percorso di destinazione è bozza, chiuso o interrotto
* se il primo evento del percorso target è stato modificato e la mappatura è interrotta

![](../assets/jump6.png)
