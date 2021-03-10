---
product: adobe campaign
solution: Journey Orchestration
title: Utilizzo del designer del percorso
description: Ulteriori informazioni sull'utilizzo del designer del percorso
feature: Percorsi
role: Professionista
level: Intermedio
translation-type: tm+mt
source-git-commit: ab19cc5a3d998d1178984c5028b1ba650d3e1292
workflow-type: tm+mt
source-wordcount: '1392'
ht-degree: 5%

---


# Utilizzo del designer del percorso {#concept_m1g_5qt_52b}

Il menu Home del percorso consente di visualizzare l&#39; **elenco di percorsi**. Crea un nuovo percorso o fai clic su uno esistente per aprire l&#39; **interfaccia di designer del percorso**. Il designer è costituito dalle seguenti zone: la palette, l’area di lavoro e il riquadro di configurazione dell’attività.

## Elenco dei percorsi {#journey_list}

L&#39; **elenco percorsi** consente di visualizzare tutti i percorsi contemporaneamente, visualizzarne lo stato ed eseguire le azioni di base. Puoi duplicare, interrompere o eliminare i tuoi percorsi. A seconda del percorso, alcune azioni potrebbero non essere disponibili. Ad esempio, non puoi eliminare o riavviare un percorso terminato. Puoi crearne una nuova versione, duplicarla o interromperla. Puoi anche usare la barra di ricerca per cercare un percorso.

Per accedere a **[!UICONTROL Filters]**, fai clic sull’icona del filtro posta in alto a sinistra nell’elenco. Il menu dei filtri ti consente di filtrare i percorsi visualizzati in base a diversi criteri (stato, quelli creati, quelli modificati negli ultimi 30 giorni, solo le versioni più recenti, ecc.). È inoltre possibile scegliere di visualizzare solo i percorsi che utilizzano un evento, un gruppo di campi o un’azione particolare. È possibile configurare le colonne visualizzate nell’elenco. Tutti i filtri e le colonne vengono salvati per utente.

![](../assets/journey74.png)

Tutte le versioni dei percorsi vengono visualizzate nell’elenco con il numero di versione. Consulta [questa pagina](../building-journeys/journey-versions.md).

![](../assets/journey37.png)

>[!NOTE]
>
>Per aprire un&#39;area di lavoro del percorso in una scheda del browser diversa, tieni premuto il tasto **Control** o **Comando** e fai clic sul percorso.

## La palette {#palette}

La **palette** si trova sul lato sinistro dello schermo. Tutte le attività disponibili sono suddivise in diverse categorie: **[!UICONTROL Events]**, **[!UICONTROL Orchestration]** e **[!UICONTROL Actions]**. È possibile espandere o comprimere le diverse categorie facendo clic sul loro nome. Per utilizzare un’attività nel percorso, trascinala dalla palette nell’area di lavoro. Puoi anche fare doppio clic su un’attività nella palette per aggiungerla all’area di lavoro, al passaggio successivo disponibile. Devi configurare ogni attività aggiunta dalla palette prima di pubblicare il percorso. Se rilasci un’attività nell’area di lavoro e non ne completi la configurazione, rimarrà nell’area di lavoro, ma un avviso rosso indica che la configurazione non è terminata per questa attività.

>[!NOTE]
>
>Tieni presente che sono presenti regole durante la configurazione di un percorso. La configurazione non consentita verrà scartata. Ad esempio, non è possibile inserire azioni in parallelo, collegare un&#39;attività a un passaggio precedente per creare un ciclo, avviare un percorso con un elemento diverso da un evento, ecc.

![](../assets/journey38.png)

L’icona **[!UICONTROL Filter items]** nell’angolo in alto a sinistra consente di visualizzare i seguenti filtri:

* **Mostra solo gli elementi** disponibili: nascondere o visualizzare gli elementi non disponibili nella palette, ad esempio gli eventi che utilizzano uno spazio dei nomi diverso da quelli utilizzati nel percorso. Per impostazione predefinita, gli elementi non disponibili sono nascosti. Se scegli di visualizzarli, verranno visualizzati in grigio.

* **Mostra solo gli elementi** recenti: questo filtro consente di visualizzare solo gli ultimi cinque eventi e azioni utilizzati, oltre a quelli predefiniti. Questo è specifico per ogni utente. Per impostazione predefinita, vengono visualizzati tutti gli elementi.

![](../assets/palette-filter.png)

Puoi inoltre utilizzare il campo **[!UICONTROL Search]** .

## Area di lavoro {#canvas}

La **area di lavoro** è la zona centrale nella finestra di progettazione del percorso. È in questa zona che puoi rilasciare le attività e configurarle. Fai clic su un’attività nell’area di lavoro per configurarla. Viene aperto il riquadro di configurazione dell’attività sul lato destro. È possibile ingrandire e ridurre utilizzando i pulsanti &quot;+&quot; e &quot;-&quot; in alto a destra. Nell’area di lavoro, tutte le attività ti consentono di aggiungere un passaggio successivo, ad eccezione delle attività **[!UICONTROL End]** (consulta [questa pagina](../building-journeys/end-activity.md)).

![](../assets/journey39.png)

## Riquadro di configurazione dell’attività {#configuration_pane}

Il **riquadro di configurazione dell&#39;attività** viene visualizzato quando si fa clic su un&#39;attività nella palette. Compila i campi richiesti. Fai clic sull’icona **[!UICONTROL Delete]** per eliminare l’attività. Fai clic su **[!UICONTROL Cancel]** per annullare le modifiche o su **[!UICONTROL Ok]** per confermare. Per eliminare le attività, puoi anche selezionare una (o più) attività e premere il tasto backspace. Premendo il tasto Esc si chiude il riquadro di configurazione dell’attività.

Nell’area di lavoro, le attività azione ed evento sono rappresentate da un’icona con il nome dell’evento o dell’azione visualizzato sotto di essa. Nel riquadro di configurazione dell’attività, puoi utilizzare il campo **[!UICONTROL Label]** per aggiungere un suffisso al nome dell’attività. Queste etichette consentono di contestualizzare l’utilizzo di eventi e azioni, soprattutto quando utilizzi più volte lo stesso evento o azione nel percorso. Potrai inoltre visualizzare le etichette aggiunte nel rapporto [!DNL Journey Orchestration] . Puoi anche definire le etichette per le attività di condizione.

![](../assets/journey59bis.png)

## Azioni barra superiore {#top_actions}

A seconda dello stato del percorso, è possibile eseguire diverse azioni sul percorso utilizzando i pulsanti disponibili nell’angolo in alto a destra: **[!UICONTROL Publish]**, **[!UICONTROL Duplicate]**, **[!UICONTROL Delete]**, **[!UICONTROL Journey properties]**, **[!UICONTROL Test]**. Questi pulsanti vengono visualizzati quando non è selezionata alcuna attività. Alcuni pulsanti vengono visualizzati contestualmente. Il pulsante del registro della modalità di prova viene visualizzato quando viene attivata la modalità di prova (vedere [questa pagina](../building-journeys/testing-the-journey.md)). Il pulsante di reporting viene visualizzato quando il percorso è attivo, arrestato o chiuso.

![](../assets/journey41.png)

## Utilizzo dei percorsi nell’area di lavoro {#paths}

Diverse attività (**[!UICONTROL Condition]**, **[!UICONTROL Action]**) ti consentono di definire un’azione di fallback in caso di errore o timeout. Nel riquadro di configurazione dell’attività, seleziona la casella: **[!UICONTROL Add an alternative path in case of a timeout or an error]**. Un altro percorso viene aggiunto dopo l’attività . La durata del timeout è definita nelle proprietà del percorso (consulta [questa pagina](../building-journeys/changing-properties.md) da un utente amministratore. Ad esempio, se l’invio di un’e-mail richiede troppo tempo o si verifica un errore, puoi decidere di inviare un SMS.

![](../assets/journey42.png)

Varie attività (evento, azione, attesa) ti consentono di aggiungere diversi percorsi dopo di essi. A questo scopo, posiziona il cursore sull’attività e fai clic sul simbolo &quot;+&quot;. Solo le attività evento e attesa possono essere impostate in parallelo. Se più eventi sono impostati in parallelo, il percorso scelto sarà quello del primo evento che si verifica.

Quando ascolti un evento, ti consigliamo di non attendere l’evento a tempo indefinito. Non è obbligatorio, è solo una buona pratica. Se desideri ascoltare uno o più eventi solo durante un certo periodo di tempo, inserirai uno o più eventi e un’attività di attesa in parallelo. Vedi [questa sezione](../building-journeys/event-activities.md#section_vxv_h25_pgb).

Per eliminare il percorso, posiziona il cursore su di esso e fai clic sull&#39;icona **[!UICONTROL Delete arrow]** .

![](../assets/journey42ter.png)

Nell’area di lavoro, quando due attività vengono disconnesse, viene visualizzato un avviso. Posiziona il cursore sull’icona di avviso per visualizzare il messaggio di errore. Per risolvere il problema, sposta semplicemente l’attività disconnessa e collegala all’attività precedente.

![](../assets/canvas-disconnected.png)

## Copia e incolla delle attività {#copy-paste}

Puoi copiare una o più attività di un percorso e incollarle nello stesso percorso o in un&#39;altra. Ciò ti consente di risparmiare tempo se desideri riutilizzare numerose attività già configurate in un percorso precedente.

**Note importanti**

* Puoi copiare/incollare diverse schede e browser. Puoi copiare/incollare solo le attività all’interno della stessa istanza.
* Non è possibile copiare/incollare un evento se il percorso di destinazione dispone di un evento che utilizza uno spazio dei nomi diverso.
* Le attività inviate possono fare riferimento a dati non esistenti nel percorso di destinazione, ad esempio se copi/incolla tra diverse sandbox. Controlla sempre gli errori e apporta le regolazioni necessarie.
* Non è possibile annullare un’azione. Per eliminare le attività incollate, dovrai selezionarle ed eliminarle. Pertanto, accertati di selezionare solo le attività necessarie prima di copiarle.
* Puoi copiare le attività da qualsiasi percorso, anche da quelli in sola lettura.
* Puoi selezionare qualsiasi attività, anche se non collegata. Le attività collegate resteranno collegate dopo essere state incollate.

Di seguito sono riportati i passaggi per copiare/incollare le attività:

1. Apri un percorso.
1. Seleziona le attività da copiare spostando il mouse mentre fai clic. Puoi anche fare clic su ogni attività premendo il tasto **Ctrl/Comando** . Utilizza **Ctrl/Comando + A** per selezionare tutte le attività.
   ![](../assets/copy-paste1.png)
1. Premere **Ctrl/Comando + C**.
Se desideri copiare una sola attività, puoi fare clic su di essa e utilizzare l&#39;icona **Copia** in alto a sinistra nel riquadro di configurazione dell&#39;attività.
   ![](../assets/copy-paste2.png)
1. In qualsiasi percorso, premi **Ctrl/Comando + V** per incollare le attività senza collegarle a un nodo esistente. Le attività inviate vengono collocate nello stesso ordine. Dopo essere state incollate, le attività rimangono selezionate in modo da poterle spostare facilmente. È inoltre possibile posizionare il cursore su un segnaposto vuoto e premere **Ctrl/Comando + V**. Le attività inviate saranno collegate al nodo .
   ![](../assets/copy-paste3.png)

