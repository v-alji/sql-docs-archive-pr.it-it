---
title: Creare una sessione eventi estesi utilizzando la procedura guidata (Esplora oggetti) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
f1_keywords:
- Sql12.ssms.XeWizard.Summary.f1
- Sql12.ssms.XeWizard.SetSessionProperties.f1
- Sql12.ssms.XeWizard.CaptureAddFields.f1
- Sql12.ssms.XeWizard.SelectEvents.f1
- Sql12.ssms.XeWizard.SpecifySessionTargets.f1
- Sql12.ssms.XeWizard.Welcome.f1
- sql12.ssms.XeWizard.Welcome.f1
- Sql12.ssms.XeWizard.ChooseTemplate.f1
- Sql12.ssms.XeWizard.SetSessionEventFilters.f1
- Sql12.ssms.XeWizard.Results.f1
helpviewer_keywords:
- Sql11.ssms.XeWizard.CaptureAddFields.f1
- Sql11.ssms.XeWizard.SetSessionEventFilters.f1
- Sql11.ssms.XeWizard.SpecifySessionTargets.f1
- Sql11.ssms.XeWizard.Results.f1
- Sql11.ssms.XeWizard.ChooseTemplate.f1
- Sql11.ssms.XeWizard.SetSessionProperties.f1
- Sql11.ssms.XeWizard.Welcome.f1
- Sql11.ssms.XeWizard.Summary.f1
- Sql11.ssms.XeWizard.SelectEvents.f1
ms.assetid: 80c0456f-17c0-41d8-b2aa-502a2f3bb6de
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: cdfc9141b0b99d5b06fc73044b8f4fae623922b7
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87628960"
---
# <a name="create-an-extended-events-session-using-the-wizard-object-explorer"></a><span data-ttu-id="80d01-102">Creare una sessione Eventi estesi utilizzando la procedura guidata (Esplora oggetti)</span><span class="sxs-lookup"><span data-stu-id="80d01-102">Create an Extended Events Session Using the Wizard (Object Explorer)</span></span>
  <span data-ttu-id="80d01-103">Per consentire di selezionare e acquisire gli eventi nel server, gli eventi estesi includono una Creazione guidata nuova sessione, che consente di eseguire in modo semplificato i passaggi per la creazione di una sessione Eventi estesi.</span><span class="sxs-lookup"><span data-stu-id="80d01-103">To help you select and capture events on your server, Extended Events includes a New Session Wizard that guides you through the steps to create an Extended Events session.</span></span> <span data-ttu-id="80d01-104">Creazione guidata nuova sessione espone la maggior parte della funzionalità di Eventi estesi.</span><span class="sxs-lookup"><span data-stu-id="80d01-104">The New Session Wizard exposes most of the Extended Events functionality.</span></span> <span data-ttu-id="80d01-105">La [finestra di dialogo Nuova sessione](../../2014/database-engine/create-an-extended-events-session-using-the-new-session-dialog.md) consente inoltre di definire una sessione di Eventi estesi che acquisisce, visualizza e analizza i dati.</span><span class="sxs-lookup"><span data-stu-id="80d01-105">The [New Session dialog](../../2014/database-engine/create-an-extended-events-session-using-the-new-session-dialog.md) also lets you define an Extended Events session that captures, displays, and analyzes your data.</span></span> <span data-ttu-id="80d01-106">La finestra di dialogo Nuova sessione espone tutta la funzionalità di Eventi estesi.</span><span class="sxs-lookup"><span data-stu-id="80d01-106">The New Session dialog exposes all Extended Events functionality.</span></span>  
  
### <a name="to-open-the-new-session-wizard"></a><span data-ttu-id="80d01-107">Per aprire la Creazione guidata nuova sessione</span><span class="sxs-lookup"><span data-stu-id="80d01-107">To open the New Session Wizard</span></span>  
  
1.  <span data-ttu-id="80d01-108">In Esplora oggetti espandere il nodo **Gestione** , quindi espandere **Eventi estesi**.</span><span class="sxs-lookup"><span data-stu-id="80d01-108">In Object Explorer, expand the **Management** node, and then expand **Extended Events**.</span></span>  
  
2.  <span data-ttu-id="80d01-109">Fare clic con il pulsante destro del mouse su **Sessione**, quindi scegliere **Creazione guidata nuova sessione**.</span><span class="sxs-lookup"><span data-stu-id="80d01-109">Right-click **Sessions**, and then click **New Session Wizard**.</span></span>  
  
### <a name="use-the-following-new-session-wizard-pages-to-create-an-event-session"></a><span data-ttu-id="80d01-110">Utilizzare le pagine seguenti della Creazione guidata nuova sessione per creare una sessione eventi</span><span class="sxs-lookup"><span data-stu-id="80d01-110">Use the following New Session Wizard pages to create an event session</span></span>  
  
-   [<span data-ttu-id="80d01-111">Introduzione</span><span class="sxs-lookup"><span data-stu-id="80d01-111">Introduction</span></span>](#BKMK_Welcome)  
  
-   [<span data-ttu-id="80d01-112">Imposta proprietà sessione</span><span class="sxs-lookup"><span data-stu-id="80d01-112">Set Session Properties</span></span>](#BKMK_SetSessionProperties)  
  
-   [<span data-ttu-id="80d01-113">Scegli modello</span><span class="sxs-lookup"><span data-stu-id="80d01-113">Choose Template</span></span>](#BKMK_ChooseTemplate)  
  
-   [<span data-ttu-id="80d01-114">Seleziona eventi da acquisire</span><span class="sxs-lookup"><span data-stu-id="80d01-114">Select Events to Capture</span></span>](#BKMK_SelectEventsToCapture)  
  
-   [<span data-ttu-id="80d01-115">Acquisisci campi globali</span><span class="sxs-lookup"><span data-stu-id="80d01-115">Capture Global Fields</span></span>](#BKMK_CaptureGlobalFields)  
  
-   [<span data-ttu-id="80d01-116">Imposta filtri di eventi di sessione</span><span class="sxs-lookup"><span data-stu-id="80d01-116">Set Session Event Filters</span></span>](#BKMK_SetSessionEventFilters)  
  
-   [<span data-ttu-id="80d01-117">Specifica l'archiviazione dei dati di sessione</span><span class="sxs-lookup"><span data-stu-id="80d01-117">Specify Session Data Storage</span></span>](#BKMK_SpecifySessionDataOutput)  
  
-   [<span data-ttu-id="80d01-118">Summary</span><span class="sxs-lookup"><span data-stu-id="80d01-118">Summary</span></span>](#BKMK_Summary)  
  
-   [<span data-ttu-id="80d01-119">Crea sessione eventi</span><span class="sxs-lookup"><span data-stu-id="80d01-119">Create Event Session</span></span>](#BKMK_CreateEventSession)  
  
##  <a name="introduction"></a><a name="BKMK_Welcome"></a><span data-ttu-id="80d01-120">Introduzione</span><span class="sxs-lookup"><span data-stu-id="80d01-120">Introduction</span></span>  
 <span data-ttu-id="80d01-121">Nella pagina **Introduzione** eseguire queste operazioni:</span><span class="sxs-lookup"><span data-stu-id="80d01-121">On the **Introduction** page, do the following:</span></span>  
  
-   <span data-ttu-id="80d01-122">Nella pagina **Introduzione** della Creazione guidata nuova sessione fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="80d01-122">On the **Introduction** page of the New Session Wizard, click **Next**.</span></span>  
  
     <span data-ttu-id="80d01-123">Selezionare la casella di controllo **Non visualizzare più questa pagina** se si prevede di utilizzare la procedura guidata più volte e non si desidera leggere l'introduzione a ogni avvio della procedura.</span><span class="sxs-lookup"><span data-stu-id="80d01-123">Select the **Do not show this page again** check box if you will be using the wizard more than once and do not want to read the introduction each time the wizard is launched.</span></span>  
  
##  <a name="set-session-properties"></a><a name="BKMK_SetSessionProperties"></a><span data-ttu-id="80d01-124">Impostare le proprietà della sessione</span><span class="sxs-lookup"><span data-stu-id="80d01-124">Set Session Properties</span></span>  
 <span data-ttu-id="80d01-125">Nella pagina **Imposta proprietà sessione** eseguire queste operazioni:</span><span class="sxs-lookup"><span data-stu-id="80d01-125">On the **Set Session Properties** page, do the following:</span></span>  
  
-   <span data-ttu-id="80d01-126">Nella casella **Nome sessione** digitare un nome significativo per la sessione eventi.</span><span class="sxs-lookup"><span data-stu-id="80d01-126">In the **Session name** box, type a meaningful name for the event session.</span></span>  
  
     <span data-ttu-id="80d01-127">Se si vuole avviare la sessione quando si avvia il server, selezionare la casella di controllo **Avviare la sessione eventi all'avvio del server** , quindi fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="80d01-127">If you want to start the session when you start the server, select the **Start the event session at server startup** check box, and then click **Next**.</span></span>  
  
##  <a name="choose-template"></a><a name="BKMK_ChooseTemplate"></a><span data-ttu-id="80d01-128">Scegli modello</span><span class="sxs-lookup"><span data-stu-id="80d01-128">Choose Template</span></span>  
 <span data-ttu-id="80d01-129">Nella pagina **Scegli modello** eseguire queste operazioni:</span><span class="sxs-lookup"><span data-stu-id="80d01-129">On the **Choose Template** page, do the following:</span></span>  
  
-   <span data-ttu-id="80d01-130">Selezionare l'opzione **Usa questo modello di sessione eventi** per eseguire una selezione da un set di modelli preconfigurati progettati per i problemi comuni.</span><span class="sxs-lookup"><span data-stu-id="80d01-130">Select the **Use this event session template** option to select from a set of pre-configured templates designed for common problems.</span></span> <span data-ttu-id="80d01-131">Selezionare il modello che si vuole usare dall'elenco a discesa, quindi fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="80d01-131">Select the template you want to use from the drop-down list, and then click **Next**.</span></span>  
  
     <span data-ttu-id="80d01-132">-OPPURE-</span><span class="sxs-lookup"><span data-stu-id="80d01-132">-OR-</span></span>  
  
-   <span data-ttu-id="80d01-133">Selezionare l'opzione **Non usare un modello** se non si vuole usare un modello preconfigurato, quindi fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="80d01-133">Select the **Do not use a template** option if you do not want to use any pre-configured template, and then click **Next**.</span></span>  
  
##  <a name="select-events-to-capture"></a><a name="BKMK_SelectEventsToCapture"></a><span data-ttu-id="80d01-134">Selezionare gli eventi da acquisire</span><span class="sxs-lookup"><span data-stu-id="80d01-134">Select Events to Capture</span></span>  
 <span data-ttu-id="80d01-135">Nella pagina **Seleziona eventi da acquisire** eseguire queste operazioni:</span><span class="sxs-lookup"><span data-stu-id="80d01-135">On the **Select Events to Capture** page, do the following:</span></span>  
  
1.  <span data-ttu-id="80d01-136">Selezionare gli eventi che si vuole acquisire in **Libreria di eventi**, quindi fare clic sulla freccia rivolta verso destra.</span><span class="sxs-lookup"><span data-stu-id="80d01-136">Select the events you want to capture from the **Event library**, and then click the right arrow.</span></span> <span data-ttu-id="80d01-137">È possibile selezionare più eventi in Libreria di eventi utilizzando MAIUSC+clic CTRL+clic.</span><span class="sxs-lookup"><span data-stu-id="80d01-137">You can select multiple events in the Event Library by using either Shift+Click or Ctrl+Click.</span></span>  
  
     <span data-ttu-id="80d01-138">È possibile scegliere come si desidera eseguire la ricerca degli eventi da acquisire nell'elenco a discesa.</span><span class="sxs-lookup"><span data-stu-id="80d01-138">You can select how you want to search for the events you want to capture from the drop-down list box.</span></span> <span data-ttu-id="80d01-139">È ad esempio possibile cercare i nomi di evento oppure i nomi di evento e le relative descrizioni.</span><span class="sxs-lookup"><span data-stu-id="80d01-139">For example, you can search for event names or event names and their descriptions.</span></span> <span data-ttu-id="80d01-140">È possibile cercare qualsiasi parola nella tabella immettendo il testo da cercare nella casella **Libreria di eventi** .</span><span class="sxs-lookup"><span data-stu-id="80d01-140">You can search for any word in the table by entering the text you want to search for in the **Event library** box.</span></span> <span data-ttu-id="80d01-141">Se, ad esempio, si desidera trovare l'evento **lock_acquired** , è possibile immettere **Lock**o **Lock Acquire**.</span><span class="sxs-lookup"><span data-stu-id="80d01-141">For example, if you want to find the **lock_acquired** event, you can enter **lock**, or **lock acquire**.</span></span>  
  
     <span data-ttu-id="80d01-142">Gli eventi selezionati vengono visualizzati nella casella **Eventi selezionati** .</span><span class="sxs-lookup"><span data-stu-id="80d01-142">The events you select appear in the **Selected events** box.</span></span> <span data-ttu-id="80d01-143">Per rimuovere gli eventi dalla casella **Eventi selezionati** , fare clic sulla freccia rivolta verso sinistra.</span><span class="sxs-lookup"><span data-stu-id="80d01-143">To remove events from the **Selected events** box, click the left arrow.</span></span>  
  
2.  <span data-ttu-id="80d01-144">Dopo avere selezionato gli eventi che si vuole acquisire, fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="80d01-144">After you select the events you want to capture, click **Next**.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="80d01-145">Gli eventi del canale **Debug** sono nascosti per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="80d01-145">Events from the **Debug** channel are hidden by default.</span></span> <span data-ttu-id="80d01-146">Per visualizzare gli eventi di debug, selezionare **Debug** dall'elenco a discesa **Canale** .</span><span class="sxs-lookup"><span data-stu-id="80d01-146">To display debug events, select **Debug** from the **Channel** drop-down list.</span></span>  
  
##  <a name="capture-global-fields"></a><a name="BKMK_CaptureGlobalFields"></a><span data-ttu-id="80d01-147">Acquisisci campi globali</span><span class="sxs-lookup"><span data-stu-id="80d01-147">Capture Global Fields</span></span>  
 <span data-ttu-id="80d01-148">I campi globali (anche definiti azioni) vengono utilizzati per associare singole azioni o più azioni per gli eventi selezionati.</span><span class="sxs-lookup"><span data-stu-id="80d01-148">You use global fields (also referred to as actions) to associate single or multiple actions for your selected events.</span></span> <span data-ttu-id="80d01-149">Se è stato selezionato un modello nella pagina **Scegli modello** , tutti i campi globali definiti nel modello vengono visualizzati in questa pagina.</span><span class="sxs-lookup"><span data-stu-id="80d01-149">If you selected a template on the **Choose Template** page, all of the global fields that are defined in the template are displayed on this page.</span></span>  
  
 <span data-ttu-id="80d01-150">Nella pagina **Acquisisci campi globali** eseguire queste operazioni:</span><span class="sxs-lookup"><span data-stu-id="80d01-150">On the **Capture Global Fields** page, do the following:</span></span>  
  
-   <span data-ttu-id="80d01-151">Selezionare i campi globali che si vuole acquisire per la sessione eventi, quindi fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="80d01-151">Select the global fields that you want to capture for the event session, and then click **Next**.</span></span>  
  
     <span data-ttu-id="80d01-152">È possibile rimuovere o aggiungere campi globali, selezionando o deselezionando la casella di controllo corrispondente.</span><span class="sxs-lookup"><span data-stu-id="80d01-152">You can remove or add global fields by selecting or clearing the check box next to the global field.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="80d01-153">Le azioni selezionate vengono ordinate in base al campo **Nome** , per consentire la visualizzazione delle azioni associate in ordine alfabetico.</span><span class="sxs-lookup"><span data-stu-id="80d01-153">The selected actions are sorted by **Name** enabling you to view the associated actions in alphabetical order.</span></span> <span data-ttu-id="80d01-154">È possibile eseguire l'ordinamento in base alla descrizione o allo stato di abilitazione/disabilitazione facendo clic sull'intestazione di colonna accanto al nome del campo.</span><span class="sxs-lookup"><span data-stu-id="80d01-154">You can sort by description or by the enable/disable status by clicking the column heading next to the field name.</span></span>  
  
##  <a name="set-session-event-filters"></a><a name="BKMK_SetSessionEventFilters"></a><span data-ttu-id="80d01-155">Imposta filtri eventi sessione</span><span class="sxs-lookup"><span data-stu-id="80d01-155">Set Session Event Filters</span></span>  
 <span data-ttu-id="80d01-156">È possibile applicare filtri (detti anche predicati) per limitare gli eventi che si desidera acquisire.</span><span class="sxs-lookup"><span data-stu-id="80d01-156">You can apply filters (also called predicates) to limit the events that you want to capture.</span></span> <span data-ttu-id="80d01-157">Nella pagina **Imposta filtri di eventi di sessione** eseguire queste operazioni:</span><span class="sxs-lookup"><span data-stu-id="80d01-157">On the **Set Session Event Filters** page, do the following:</span></span>  
  
1.  <span data-ttu-id="80d01-158">Se non si usa un modello preconfigurato, creare i criteri di filtro personalizzati, quindi fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="80d01-158">If you are not using a pre-configured template, create your filter criteria, and then click **Next**.</span></span>  
  
     <span data-ttu-id="80d01-159">Se si usa un modello preconfigurato, nella sezione **Filtri nel modello (sola lettura)** vengono visualizzati i filtri già creati dal modello.</span><span class="sxs-lookup"><span data-stu-id="80d01-159">If you are using a pre-configured template, in the **Filters from template (read-only)** section, the New Session Wizard lists filters already created from the template.</span></span>  
  
2.  <span data-ttu-id="80d01-160">Nella sezione **Filtri aggiuntivi** è possibile configurare altri filtri per la sessione eventi.</span><span class="sxs-lookup"><span data-stu-id="80d01-160">In the **Additional filters** section, you can configure additional filters for the event session.</span></span>  
  
     <span data-ttu-id="80d01-161">I filtri configurati si applicano a tutti gli eventi selezionati.</span><span class="sxs-lookup"><span data-stu-id="80d01-161">The filters you configure apply to all selected events.</span></span> <span data-ttu-id="80d01-162">La Creazione guidata nuova sessione non supporta la configurazione di filtri per ogni singolo evento.</span><span class="sxs-lookup"><span data-stu-id="80d01-162">The New Session Wizard does not support configuring filters for each event.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="80d01-163">Quando si configura una clausola group per il filtro, le parentesi ridondanti vengono rimosse dal filtro dopo che il risultato è stato salvato.</span><span class="sxs-lookup"><span data-stu-id="80d01-163">When you configure a group clause for your filter, redundant parentheses are removed from the filter after the result is saved.</span></span> <span data-ttu-id="80d01-164">Se, ad esempio, si crea un filtro che raggruppa **Clausola 1** e **Clausola 2**, le clausole vengono racchiuse tra parentesi.</span><span class="sxs-lookup"><span data-stu-id="80d01-164">For example, if you create a filter grouping **Clause 1** and **Clause 2**, parentheses will appear around the clauses.</span></span> <span data-ttu-id="80d01-165">Dopo avere salvato il filtro, le parentesi ridondanti vengono rimosse.</span><span class="sxs-lookup"><span data-stu-id="80d01-165">After you save the filter, the redundant parentheses are removed.</span></span> <span data-ttu-id="80d01-166">La rimozione delle parentesi non influisce sulla logica di filtro.</span><span class="sxs-lookup"><span data-stu-id="80d01-166">The removal of the parentheses does not affect the filter logic.</span></span>  
  
##  <a name="specify-session-data-storage"></a><a name="BKMK_SpecifySessionDataOutput"></a><span data-ttu-id="80d01-167">Specificare l'archiviazione dei dati della sessione</span><span class="sxs-lookup"><span data-stu-id="80d01-167">Specify Session Data Storage</span></span>  
 <span data-ttu-id="80d01-168">La pagina **Specifica l'archiviazione dei dati di sessione** consente di specificare la modalità di raccolta dei dati per l'analisi.</span><span class="sxs-lookup"><span data-stu-id="80d01-168">You use the **Specify Session Data Storage** page to specify how you want to collect your data for analysis.</span></span> <span data-ttu-id="80d01-169">Gli eventi estesi di SQL Server prevedono l'utilizzo di destinazioni per l'output dei dati.</span><span class="sxs-lookup"><span data-stu-id="80d01-169">SQL Server Extended Events uses targets for data output.</span></span> <span data-ttu-id="80d01-170">Le destinazioni consentono di archiviare i dati degli eventi ed eseguire azioni come la scrittura in un file e l'aggregazione dei dati degli eventi.</span><span class="sxs-lookup"><span data-stu-id="80d01-170">Targets store event data and can perform actions such as writing to a file and aggregating event data.</span></span> <span data-ttu-id="80d01-171">Dopo avere stabilito la modalità di raccolta dei dati per l'analisi, nella pagina **Specifica l'archiviazione dei dati di sessione** eseguire queste operazioni:</span><span class="sxs-lookup"><span data-stu-id="80d01-171">Decide how you want to collect your data for analysis, and on the **Specify Session Data Storage** page, do the following:</span></span>  
  
1.  <span data-ttu-id="80d01-172">Per set di dati di grandi dimensioni e per la creazione di record cronologici, selezionare la casella di controllo **Salva i dati in un file per l'analisi successiva** , quindi eseguire queste operazioni:</span><span class="sxs-lookup"><span data-stu-id="80d01-172">For large data sets and creating historical records, select the **Save data to a file for later analysis** check box, and then do the following:</span></span>  
  
    1.  <span data-ttu-id="80d01-173">Nella casella **Nome file sul server** immettere il percorso e il nome del file oppure fare clic su **Sfoglia** per specificare la directory del file nel server in cui si vuole salvare i dati.</span><span class="sxs-lookup"><span data-stu-id="80d01-173">In the **File name on server** box, enter the path and file name, or click **Browse** to specify the file directory on the server where you want to save the data.</span></span>  
  
    2.  <span data-ttu-id="80d01-174">Nella casella **Dimensioni massime file** specificare le dimensioni massime del file da usare per la destinazione file.</span><span class="sxs-lookup"><span data-stu-id="80d01-174">In the **Maximum file size** box, specify the maximum file size to be used for the file target.</span></span> <span data-ttu-id="80d01-175">Se non si specifica un valore massimo, le dimensioni del file aumenteranno fino a quando il disco non è pieno.</span><span class="sxs-lookup"><span data-stu-id="80d01-175">If you do not specify the maximum file size, the file will grow until the disk is full.</span></span> <span data-ttu-id="80d01-176">Le dimensioni predefinite del file sono di 1 gigabyte (GB).</span><span class="sxs-lookup"><span data-stu-id="80d01-176">The default file size is 1 gigabyte (GB).</span></span>  
  
    3.  <span data-ttu-id="80d01-177">Selezionare la casella di controllo **Consenti rollover dei file** per abilitare il rollover dei file per la destinazione file.</span><span class="sxs-lookup"><span data-stu-id="80d01-177">Select the **Enable file rollover** check box to enable file rollover for the file target.</span></span>  
  
    4.  <span data-ttu-id="80d01-178">Nella casella **Numero massimo di file** specificare il numero massimo di file che si vuole mantenere nel file system.</span><span class="sxs-lookup"><span data-stu-id="80d01-178">In the **Maximum number of files** box, specify the maximum number of files you want to retain in the file system.</span></span>  
  
2.  <span data-ttu-id="80d01-179">Per la raccolta di dati recenti, selezionare la casella di controllo **Utilizzare solo i dati più recenti (destinazione ring_buffer)** , quindi eseguire queste operazioni:</span><span class="sxs-lookup"><span data-stu-id="80d01-179">For collecting recent data, select the **Work with only the most recent data (ring buffer target)** check box, and then do the following:</span></span>  
  
    1.  <span data-ttu-id="80d01-180">Nella casella **Numero di eventi da mantenere** immettere o selezionare il numero di eventi che si vuole mantenere usando le frecce rivolte verso l'alto e verso il basso.</span><span class="sxs-lookup"><span data-stu-id="80d01-180">In the **Number of events to keep** box, enter or select the number of events you want to keep by using the up and down arrows.</span></span>  
  
    2.  <span data-ttu-id="80d01-181">Nella casella **Dimensioni massime memoria buffer** specificare la quantità massima di memoria buffer da usare.</span><span class="sxs-lookup"><span data-stu-id="80d01-181">In the **Maximum buffer memory size** box, specify the maximum amount of buffer memory to use.</span></span> <span data-ttu-id="80d01-182">Quando questo valore viene raggiunto, gli eventi esistenti vengono eliminati.</span><span class="sxs-lookup"><span data-stu-id="80d01-182">The existing events are dropped when this value is reached.</span></span>  
  
    3.  <span data-ttu-id="80d01-183">Se si vuole mantenere un numero specifico di eventi di ogni tipo nel buffer, selezionare la casella di controllo **Mantenere un numero specificato di eventi (per tipo) quando il buffer è pieno** .</span><span class="sxs-lookup"><span data-stu-id="80d01-183">If you want to keep a specific number of events of each type in the buffer, select the **Keep a specified number of events (per type) when the buffer is full** check box.</span></span>  
  
    4.  <span data-ttu-id="80d01-184">Nella casella **Numero di eventi da mantenere (per tipo)** immettere o selezionare il numero di eventi (per tipo) che si vuole mantenere usando le frecce rivolte verso l'alto e verso il basso.</span><span class="sxs-lookup"><span data-stu-id="80d01-184">In the **Number of events to keep (per type)** box, enter or select the number of events (per type) that you want to keep by using the up and down arrows.</span></span>  
  
##  <a name="summary"></a><a name="BKMK_Summary"></a> <span data-ttu-id="80d01-185">Riepilogo</span><span class="sxs-lookup"><span data-stu-id="80d01-185">Summary</span></span>  
 <span data-ttu-id="80d01-186">Nella pagina **Riepilogo** eseguire queste operazioni:</span><span class="sxs-lookup"><span data-stu-id="80d01-186">On the **Summary** page, do the following:</span></span>  
  
1.  <span data-ttu-id="80d01-187">Verificare che le selezioni siano corrette.</span><span class="sxs-lookup"><span data-stu-id="80d01-187">Make sure that your selections are correct.</span></span> <span data-ttu-id="80d01-188">Espandere i nodi della sessione eventi per verificare che tutte le selezioni verranno incluse nella sessione eventi.</span><span class="sxs-lookup"><span data-stu-id="80d01-188">Expand the event session nodes to verify that all of your selections will be included in the event session.</span></span>  
  
2.  <span data-ttu-id="80d01-189">Fare clic su **Script** per esportare lo script di creazione della sessione in una nuova finestra dell'editor di query.</span><span class="sxs-lookup"><span data-stu-id="80d01-189">Click **Script** to export the session creation script to a new Query Editor window.</span></span>  
  
3.  <span data-ttu-id="80d01-190">Fare clic su **Fine** per creare la sessione eventi.</span><span class="sxs-lookup"><span data-stu-id="80d01-190">Click **Finish** to create the event session.</span></span>  
  
##  <a name="create-event-session"></a><a name="BKMK_CreateEventSession"></a><span data-ttu-id="80d01-191">Crea sessione eventi</span><span class="sxs-lookup"><span data-stu-id="80d01-191">Create Event Session</span></span>  
 <span data-ttu-id="80d01-192">Dopo la creazione della sessione eventi, nella pagina **Crea sessione eventi** eseguire queste operazioni:</span><span class="sxs-lookup"><span data-stu-id="80d01-192">On the **Create Event Session** page, after your event session has been successfully created, do the following:</span></span>  
  
1.  <span data-ttu-id="80d01-193">Fare clic su **Avviare la sessione eventi subito dopo la creazione della sessione** per avviare la sessione dopo la chiusura della procedura guidata.</span><span class="sxs-lookup"><span data-stu-id="80d01-193">Click **Start the event session immediately after session creation** to start the session after you close the wizard.</span></span> <span data-ttu-id="80d01-194">Per poter visualizzare i dati dinamici, è necessario avviare la sessione eventi subito dopo la creazione della sessione.</span><span class="sxs-lookup"><span data-stu-id="80d01-194">You must start the event session immediately after you create the session to be able to watch live data.</span></span>  
  
2.  <span data-ttu-id="80d01-195">Fare clic su **Controllare i dati dinamici sullo schermo al momento dell'acquisizione** per visualizzare i dati dinamici per la sessione eventi.</span><span class="sxs-lookup"><span data-stu-id="80d01-195">Click **Watch live data on screen as it is captured** to view live data for your event session.</span></span> <span data-ttu-id="80d01-196">La traccia dei dati dinamici inizierà a essere visualizzata subito dopo la creazione della sessione.</span><span class="sxs-lookup"><span data-stu-id="80d01-196">The live data will start displaying tracing immediately after the session is created.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="80d01-197">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="80d01-197">See Also</span></span>  
 [<span data-ttu-id="80d01-198">Creare una sessione Eventi estesi utilizzando la finestra di dialogo Nuova sessione</span><span class="sxs-lookup"><span data-stu-id="80d01-198">Create an Extended Events Session Using the New Session Dialog</span></span>](../../2014/database-engine/create-an-extended-events-session-using-the-new-session-dialog.md)  
  
  
