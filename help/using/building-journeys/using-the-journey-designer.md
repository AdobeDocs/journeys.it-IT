---
product: adobe campaign
title: Utilizzo del designer del percorso
description: Ulteriori informazioni sull'utilizzo di Progettazione percorsi
feature: Journeys
role: User
level: Intermediate
exl-id: 2f001e42-46dd-48aa-b3dd-23bfdf97e1c7
source-git-commit: 69471a36b113e04a7bb0953a90977ad4020299e4
workflow-type: tm+mt
source-wordcount: '1474'
ht-degree: 5%

---

# Utilizzo del designer del percorso {#concept_m1g_5qt_52b}


>[!CAUTION]
>
>**Ricerca di Adobe Journey Optimizer**? Fai clic [qui](https://experienceleague.adobe.com/it/docs/journey-optimizer/using/ajo-home){target="_blank"} per la documentazione di Journey Optimizer.
>
>
>_Questa documentazione fa riferimento ai materiali Journey Orchestration legacy che sono stati sostituiti da Journey Optimizer. Contatta il team del tuo account in caso di domande sull&#39;accesso a Journey Orchestration o Journey Optimizer._


Il menu Home percorso consente di visualizzare l&#39;elenco **dei percorsi**. Creare un nuovo percorso o fare clic su uno esistente per aprire l&#39;interfaccia di **Progettazione percorsi**. La finestra di progettazione è composta dalle seguenti aree: la palette, l’area di lavoro e il riquadro di configurazione dell’attività.

## Elenco percorsi {#journey_list}

L&#39;**elenco percorsi** ti consente di visualizzare tutti i tuoi percorsi contemporaneamente, di visualizzarne lo stato ed eseguire le azioni di base. Puoi duplicare, interrompere o eliminare i tuoi percorsi. A seconda del percorso, alcune azioni potrebbero non essere disponibili. Ad esempio, non puoi eliminare o riavviare un percorso terminato. Puoi crearne una nuova versione, duplicarla o interromperla. Puoi anche usare la barra di ricerca per cercare un percorso.

Per accedere a **[!UICONTROL Filters]**, fai clic sull’icona del filtro, in alto a sinistra nell’elenco. Il menu dei filtri ti consente di filtrare i percorsi visualizzati in base a criteri diversi (stato, quelli creati, quelli modificati negli ultimi 30 giorni, solo le versioni più recenti, ecc.). È inoltre possibile scegliere di visualizzare solo i percorsi che utilizzano un evento, un gruppo di campi o un&#39;azione particolare. Le colonne visualizzate nell’elenco possono essere configurate. Tutti i filtri e le colonne vengono salvati per utente.

![](../assets/journey74.png)

Tutte le versioni dei percorsi vengono visualizzate nell&#39;elenco con il numero di versione. Consulta [questa pagina](../building-journeys/journey-versions.md).

![](../assets/journey37.png)

>[!NOTE]
>
>Per aprire l&#39;area di lavoro di un percorso in un&#39;altra scheda del browser, tenere premuto il tasto **Control** o **Command** e fare clic sul percorso.

## La palette {#palette}

La **palette** si trova sul lato sinistro dello schermo. Tutte le attività disponibili sono ordinate in diverse categorie: **[!UICONTROL Events]**, **[!UICONTROL Orchestration]** e **[!UICONTROL Actions]**. Puoi espandere/comprimere le diverse categorie facendo clic sul loro nome. Per utilizzare un’attività nel percorso, trascinala dalla palette nell’area di lavoro. Puoi anche fare doppio clic su un’attività nella palette per aggiungerla all’area di lavoro, al passaggio successivo disponibile. Devi configurare ogni attività aggiunta dalla palette prima di pubblicare il percorso. Se rilasci un’attività nell’area di lavoro e non ne completi la configurazione, questa rimarrà nell’area di lavoro ma un avviso rosso indicherà che la configurazione non è terminata per questa attività.

>[!NOTE]
>
>Tieni presente che esistono regole durante la configurazione di un percorso. La configurazione non consentita verrà eliminata. Ad esempio, non puoi inserire azioni in parallelo, collegare un’attività a un passaggio precedente per creare un ciclo, avviare un percorso con qualcosa di diverso da un evento, ecc.

![](../assets/journey38.png)

L&#39;icona **[!UICONTROL Filter items]** nell&#39;angolo in alto a sinistra consente di visualizzare i filtri seguenti:

* **Mostra solo gli elementi disponibili**: nascondi o visualizza gli elementi non disponibili nella tavolozza, ad esempio gli eventi che utilizzano uno spazio dei nomi diverso rispetto a quelli utilizzati nel percorso. Per impostazione predefinita, gli elementi non disponibili sono nascosti. Se scegli di visualizzarli, appariranno in grigio.

* **Mostra solo elementi recenti**: questo filtro consente di visualizzare solo gli ultimi cinque eventi e azioni utilizzati, oltre a quelli predefiniti. Questo è specifico per ogni utente. Per impostazione predefinita, vengono visualizzati tutti gli elementi.

![](../assets/palette-filter.png)

È inoltre possibile utilizzare il campo **[!UICONTROL Search]**. Vengono filtrati solo gli eventi e le azioni.

## L’area di lavoro {#canvas}

L&#39;**area di lavoro** è l&#39;area centrale nella finestra di progettazione del percorso. È in quest’area che puoi rilasciare le attività e configurarle. Fai clic su un’attività nell’area di lavoro per configurarla. Questo apre il riquadro di configurazione dell’attività sul lato destro. È possibile ingrandire e ridurre utilizzando i tasti &quot;+&quot; e &quot;-&quot; in alto a destra. Nell&#39;area di lavoro, tutte le attività ti consentono di aggiungere un passaggio successivo, tranne **[!UICONTROL End]** attività (vedi [questa pagina](../building-journeys/end-activity.md)).

![](../assets/journey39.png)

## Riquadro di configurazione dell’attività {#configuration_pane}

Il **riquadro di configurazione attività** viene visualizzato quando si fa clic su un&#39;attività nella tavolozza. Compila i campi obbligatori. Fai clic sull&#39;icona **[!UICONTROL Delete]** per eliminare l&#39;attività. Fai clic su **[!UICONTROL Cancel]** per annullare le modifiche o su **[!UICONTROL Ok]** per confermare. Per eliminare delle attività, puoi anche selezionare una o più attività e premere il tasto backspace. Premendo il tasto Esc si chiude il riquadro di configurazione dell’attività.

Nell’area di lavoro, le attività di azione ed evento sono rappresentate da un’icona con il nome dell’evento o dell’azione visualizzato sotto. Nel riquadro di configurazione attività è possibile utilizzare il campo **[!UICONTROL Label]** per aggiungere un suffisso al nome dell&#39;attività. Queste etichette ti aiuteranno a contestualizzare l’utilizzo di eventi e azioni, soprattutto quando utilizzi lo stesso evento o azione più volte nel percorso. Potrai anche visualizzare le etichette aggiunte nel reporting [!DNL Journey Orchestration]. Puoi anche definire le etichette per le attività condizione.

Per impostazione predefinita, i campi di sola lettura sono nascosti. Per visualizzare i campi di sola lettura, fai clic sull&#39;icona **Mostra campi di sola lettura** in alto a sinistra nel riquadro di configurazione dell&#39;attività. Questa impostazione si applica a tutte le attività in tutti i percorsi.

![](../assets/journey59bis.png)

## Le azioni della barra superiore {#top_actions}

A seconda dello stato del percorso, puoi eseguire diverse azioni sul percorso utilizzando i pulsanti disponibili nell&#39;angolo in alto a destra: **[!UICONTROL Publish]**, **[!UICONTROL Duplicate]**, **[!UICONTROL Delete]**, **[!UICONTROL Journey properties]**, **[!UICONTROL Test]**. Questi pulsanti vengono visualizzati quando non è selezionata alcuna attività. Alcuni pulsanti vengono visualizzati contestualmente. Il pulsante di registro della modalità di test viene visualizzato quando la modalità di test è attivata (vedere [questa pagina](../building-journeys/testing-the-journey.md)). Il pulsante per la generazione di rapporti viene visualizzato quando il percorso è attivo, interrotto o chiuso.

![](../assets/journey41.png)

## Utilizzo dei percorsi nell’area di lavoro {#paths}

Diverse attività (**[!UICONTROL Condition]**, **[!UICONTROL Action]** attività) ti consentono di definire un&#39;azione di fallback in caso di errore o timeout. Nel riquadro di configurazione attività selezionare la casella: **[!UICONTROL Add an alternative path in case of a timeout or an error]**. Un altro percorso viene aggiunto dopo l’attività. La durata del timeout è definita nelle proprietà del percorso (vedi [questa pagina](../building-journeys/changing-properties.md) da un utente amministratore. Ad esempio, se un’e-mail richiede troppo tempo o è in errore, puoi decidere di inviare un SMS.

![](../assets/journey42.png)

Varie attività (evento, azione, attesa) ti consentono di aggiungere diversi percorsi dopo di essi. A questo scopo, posiziona il cursore sull’attività e fai clic sul simbolo &quot;+&quot;. Solo le attività event e wait possono essere impostate in parallelo. Se più eventi sono impostati in parallelo, il percorso scelto sarà quello del primo evento in corso.

Quando ascolti un evento, ti consigliamo di non attendere l’evento a tempo indefinito. Non è obbligatorio, è solo una best practice. Se desideri ascoltare uno o più eventi solo durante un certo periodo di tempo, inserirai uno o più eventi e un’attività Attendi in parallelo. Consulta [questa sezione](../building-journeys/event-activities.md#section_vxv_h25_pgb).

Per eliminare il percorso, posizionare il cursore e fare clic sull&#39;icona **[!UICONTROL Delete arrow]**.

![](../assets/journey42ter.png)

Quando due attività vengono disconnesse, nell’area di lavoro viene visualizzato un avviso. Posizionare il cursore sull&#39;icona di avviso per visualizzare il messaggio di errore. Per risolvere il problema, è sufficiente spostare l’attività disconnessa e collegarla all’attività precedente.

![](../assets/canvas-disconnected.png)

## Copiare e incollare attività {#copy-paste}

Puoi copiare una o più attività di un percorso e incollarle nello stesso percorso o in un altro. Questo ti consente di risparmiare tempo se desideri riutilizzare numerose attività già configurate in un percorso precedente.

**Note importanti**

* Puoi copiare e incollare in diverse schede e browser. Puoi copiare/incollare solo attività all’interno della stessa istanza.
* Non puoi copiare/incollare un evento se il percorso di destinazione ha un evento che utilizza uno spazio dei nomi diverso.
* Le attività incollate possono fare riferimento a dati che non esistono nel percorso di destinazione, ad esempio se si copiano o si incollano in sandbox diverse. Verificare sempre la presenza di errori e apportare le modifiche necessarie.
* Tieni presente che non puoi annullare un’azione. Per eliminare le attività incollate, devi selezionarle ed eliminarle. Accertati quindi di selezionare solo le attività necessarie prima di copiarle.
* Puoi copiare le attività da qualsiasi percorso, anche quelle in sola lettura.
* Puoi selezionare qualsiasi attività, anche quelle non collegate. Le attività collegate rimarranno collegate dopo essere state incollate.

Di seguito sono riportati i passaggi per copiare/incollare le attività:

1. Apri un percorso.
1. Seleziona le attività da copiare spostando il mouse mentre fai clic su. È inoltre possibile fare clic su ogni attività premendo il tasto **Ctrl/Comando**. Utilizzare **Ctrl/Comando + A** per selezionare tutte le attività.
   ![](../assets/copy-paste1.png)
1. Premere **Ctrl/Comando + C**.
Se desideri copiare solo un&#39;attività, puoi fare clic su di essa e utilizzare l&#39;icona **Copia** in alto a sinistra nel riquadro di configurazione dell&#39;attività.
   ![](../assets/copy-paste2.png)
1. In qualsiasi percorso, premere **Ctrl/Comando + V** per incollare le attività senza collegarle a un nodo esistente. Le attività incollate vengono inserite nello stesso ordine. Dopo essere state incollate, le attività rimangono selezionate in modo da poterle spostare facilmente. Puoi anche posizionare il cursore su un segnaposto vuoto e premere **Ctrl/Comando + V**. Le attività incollate verranno collegate al nodo.
   ![](../assets/copy-paste3.png)
