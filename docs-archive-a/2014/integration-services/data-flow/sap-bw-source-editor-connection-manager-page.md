---
title: Editor origine SAP BW (pagina Gestione connessione) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
ms.assetid: 2a6dc531-85ca-43c5-a65f-3ad3f7d537c4
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 8c6b1782daf8c00b3b3d3a7d13b5ffa00adeeba2
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87712219"
---
# <a name="sap-bw-source-editor-connection-manager-page"></a><span data-ttu-id="c1a2f-102">Editor origine SAP BW (pagina Gestione connessione)</span><span class="sxs-lookup"><span data-stu-id="c1a2f-102">SAP BW Source Editor (Connection Manager Page)</span></span>
  <span data-ttu-id="c1a2f-103">Usare la pagina **Gestione connessione** della finestra di dialogo **Editor origine SAP BW** per selezionare la gestione connessione SAP BW per l'origine SAP BW.</span><span class="sxs-lookup"><span data-stu-id="c1a2f-103">Use the **Connection Manager** page of the **SAP BW Source Editor** to select the SAP BW connection manager for the SAP BW source.</span></span> <span data-ttu-id="c1a2f-104">In questa pagina vengono inoltre selezionati la modalità di esecuzione e i parametri per estrarre i dati dal sistema SAP Netweaver BW.</span><span class="sxs-lookup"><span data-stu-id="c1a2f-104">On this page, you also select the execution mode and the parameters for extracting the data from the SAP Netweaver BW system.</span></span>  
  
 <span data-ttu-id="c1a2f-105">Per altre informazioni sul componente di origine SAP BW di [!INCLUDE[msCoName](../../includes/msconame-md.md)] Connector 1.1 for SAP BW, vedere [Origine SAP BW](sap-bw-source.md).</span><span class="sxs-lookup"><span data-stu-id="c1a2f-105">To learn more about the SAP BW source component of the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Connector 1.1 for SAP BW, see [SAP BW Source](sap-bw-source.md).</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="c1a2f-106">La documentazione per Microsoft Connector 1.1 for SAP BW presuppone la conoscenza dell'ambiente SAP Netweaver BW.</span><span class="sxs-lookup"><span data-stu-id="c1a2f-106">The documentation for the Microsoft Connector 1.1 for SAP BW assumes familiarity with the SAP Netweaver BW environment.</span></span> <span data-ttu-id="c1a2f-107">Per ulteriori informazioni su SAP Netweaver BW o per informazioni su come configurare oggetti e processi di SAP Netweaver BW, vedere la documentazione SAP.</span><span class="sxs-lookup"><span data-stu-id="c1a2f-107">For more information about SAP Netweaver BW, or for information about how to configure SAP Netweaver BW objects and processes, see your SAP documentation.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="c1a2f-108">L'estrazione di dati da SAP Netweaver BW richiede licenze SAP aggiuntive.</span><span class="sxs-lookup"><span data-stu-id="c1a2f-108">Extracting data from SAP Netweaver BW requires additional SAP licensing.</span></span> <span data-ttu-id="c1a2f-109">Contattare SAP per verificare questi requisiti.</span><span class="sxs-lookup"><span data-stu-id="c1a2f-109">Check with SAP to verify these requirements.</span></span>  
  
 <span data-ttu-id="c1a2f-110">**Per aprire la pagina Gestione connessione**</span><span class="sxs-lookup"><span data-stu-id="c1a2f-110">**To open the Connection Manager page**</span></span>  
  
1.  <span data-ttu-id="c1a2f-111">In [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)]aprire il pacchetto [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] che contiene l'origine SAP BW.</span><span class="sxs-lookup"><span data-stu-id="c1a2f-111">In [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], open the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] package that contains the SAP BW source.</span></span>  
  
2.  <span data-ttu-id="c1a2f-112">Nella scheda **Flusso di dati** fare doppio clic sull'origine SAP BW.</span><span class="sxs-lookup"><span data-stu-id="c1a2f-112">On the **Data Flow** tab, double-click the SAP BW source.</span></span>  
  
3.  <span data-ttu-id="c1a2f-113">Nell' **Editor origine SAP BW**fare clic su **Gestione connessione** per aprire la pagina **Gestione connessione** dell'editor.</span><span class="sxs-lookup"><span data-stu-id="c1a2f-113">In the **SAP BW Source Editor**, click **Connection Manager** to open the **Connection Manager** page of the editor.</span></span>  
  
## <a name="static-options"></a><span data-ttu-id="c1a2f-114">Opzioni statiche</span><span class="sxs-lookup"><span data-stu-id="c1a2f-114">Static Options</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="c1a2f-115">Se non si conoscono tutti i valori richiesti per configurare l'origine, può essere necessario consultare l'amministratore SAP.</span><span class="sxs-lookup"><span data-stu-id="c1a2f-115">If you do not know all the values that are required to configure the source, you might have to ask your SAP administrator.</span></span>  
  
 <span data-ttu-id="c1a2f-116">**Gestione connessione SAP BW**</span><span class="sxs-lookup"><span data-stu-id="c1a2f-116">**SAP BW connection manager**</span></span>  
 <span data-ttu-id="c1a2f-117">Selezionare una gestione connessione esistente nell'elenco o crearne una nuova facendo clic su **Nuova**.</span><span class="sxs-lookup"><span data-stu-id="c1a2f-117">Select an existing connection manager from the list, or create a new connection by clicking **New**.</span></span>  
  
 <span data-ttu-id="c1a2f-118">**Nuovo**</span><span class="sxs-lookup"><span data-stu-id="c1a2f-118">**New**</span></span>  
 <span data-ttu-id="c1a2f-119">Creare una nuova gestione connessione usando la finestra di dialogo **Gestione connessione SAP BW** .</span><span class="sxs-lookup"><span data-stu-id="c1a2f-119">Create a new connection manager by using the **SAP BW Connection Manager** dialog box.</span></span>  
  
 <span data-ttu-id="c1a2f-120">Per altre informazioni sulla questa finestra di dialogo, vedere [Editor gestione connessione SAP BW](../sap-bw-connection-manager-editor.md).</span><span class="sxs-lookup"><span data-stu-id="c1a2f-120">For more information about this dialog box, see [SAP BW Connection Manager Editor](../sap-bw-connection-manager-editor.md).</span></span>  
  
 <span data-ttu-id="c1a2f-121">**Destinazione OHS**</span><span class="sxs-lookup"><span data-stu-id="c1a2f-121">**OHS destination**</span></span>  
 <span data-ttu-id="c1a2f-122">Selezionare la destinazione OHS (Open Hub Service) da utilizzare per estrarre i dati dall'origine.</span><span class="sxs-lookup"><span data-stu-id="c1a2f-122">Select the Open Hub Service (OHS) destination to use to extract data from the source.</span></span>  
  
 <span data-ttu-id="c1a2f-123">**Modalità di esecuzione**</span><span class="sxs-lookup"><span data-stu-id="c1a2f-123">**Execution mode**</span></span>  
 <span data-ttu-id="c1a2f-124">Specificare il metodo per l'estrazione dei dati dall'origine.</span><span class="sxs-lookup"><span data-stu-id="c1a2f-124">Specify the method for extracting data from the source.</span></span>  
  
|<span data-ttu-id="c1a2f-125">Opzione</span><span class="sxs-lookup"><span data-stu-id="c1a2f-125">Option</span></span>|<span data-ttu-id="c1a2f-126">Descrizione</span><span class="sxs-lookup"><span data-stu-id="c1a2f-126">Description</span></span>|  
|------------|-----------------|  
|<span data-ttu-id="c1a2f-127">**P - Attivazione catena processi**</span><span class="sxs-lookup"><span data-stu-id="c1a2f-127">**P - Trigger Process Chain**</span></span>|<span data-ttu-id="c1a2f-128">Attivare una catena di processi.</span><span class="sxs-lookup"><span data-stu-id="c1a2f-128">Trigger a process chain.</span></span> <span data-ttu-id="c1a2f-129">In questo caso, il pacchetto di [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] avvia il processo di estrazione.</span><span class="sxs-lookup"><span data-stu-id="c1a2f-129">In this case, the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] package starts the extraction process.</span></span>|  
|<span data-ttu-id="c1a2f-130">**W - Attesa notifica**</span><span class="sxs-lookup"><span data-stu-id="c1a2f-130">**W - Wait for Notify**</span></span>|<span data-ttu-id="c1a2f-131">Attendere la notifica dal sistema SAP Netweaver BW per avviare l'estrazione dei dati.</span><span class="sxs-lookup"><span data-stu-id="c1a2f-131">Wait for notification from the SAP Netweaver BW system to begin extracting the data.</span></span> <span data-ttu-id="c1a2f-132">In questo caso, il sistema SAP Netweaver BW avvia il processo di estrazione.</span><span class="sxs-lookup"><span data-stu-id="c1a2f-132">In this case, the SAP Netweaver BW system starts the extraction process.</span></span>|  
|<span data-ttu-id="c1a2f-133">**E - Solo estrazione**</span><span class="sxs-lookup"><span data-stu-id="c1a2f-133">**E - Extract Only**</span></span>|<span data-ttu-id="c1a2f-134">Recuperare i dati associati a un ID richiesta specifico.</span><span class="sxs-lookup"><span data-stu-id="c1a2f-134">Retrieve the data that is associated with a particular Request ID.</span></span> <span data-ttu-id="c1a2f-135">In questo caso, il sistema SAP Netweaver BW ha già estratto i dati in una tabella interna e il pacchetto di [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] legge solo i dati.</span><span class="sxs-lookup"><span data-stu-id="c1a2f-135">In this case, the SAP Netweaver BW system has already extracted the data into an internal table, and the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] package just reads the data.</span></span>|  
  
 <span data-ttu-id="c1a2f-136">**Anteprima**</span><span class="sxs-lookup"><span data-stu-id="c1a2f-136">**Preview**</span></span>  
 <span data-ttu-id="c1a2f-137">Aprire la finestra di dialogo **Anteprima** in cui è possibile visualizzare i risultati in anteprima.</span><span class="sxs-lookup"><span data-stu-id="c1a2f-137">Open the **Preview** dialog box in which you can preview results.</span></span> <span data-ttu-id="c1a2f-138">Per altre informazioni, vedere [Anteprima](preview.md).</span><span class="sxs-lookup"><span data-stu-id="c1a2f-138">For more information, see [Preview](preview.md).</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="c1a2f-139">Con l'opzione **Anteprima** , disponibile nella pagina **Gestione connessione** dell'Editor di origine SAP BW, vengono effettivamente estratti i dati.</span><span class="sxs-lookup"><span data-stu-id="c1a2f-139">The **Preview** option, that is available on the **Connection Manager** page of the SAP BW Source Editor, actually extracts data.</span></span> <span data-ttu-id="c1a2f-140">Se è stato configurato SAP Netweaver BW per estrarre solo i dati modificati dall'estrazione precedente, la selezione di **Anteprima** escluderà i dati visualizzati in anteprima dall'estrazione successiva.</span><span class="sxs-lookup"><span data-stu-id="c1a2f-140">If you have configured SAP Netweaver BW to extract only data that has changed since the previous extraction, selecting **Preview** will exclude the previewed data from the next extraction.</span></span>  
  
 <span data-ttu-id="c1a2f-141">Quando si fa clic su **Anteprima**, viene inoltre aperta la finestra di dialogo **Log richieste** .</span><span class="sxs-lookup"><span data-stu-id="c1a2f-141">When you click **Preview**, you also open the **Request Log** dialog box.</span></span> <span data-ttu-id="c1a2f-142">È possibile utilizzare questa finestra di dialogo per visualizzare gli eventi registrati durante la richiesta fatta al sistema SAP Netweaver BW per i dati di esempio.</span><span class="sxs-lookup"><span data-stu-id="c1a2f-142">You can use this dialog box to view the events that are logged during the request that is made to the SAP Netweaver BW system for sample data.</span></span> <span data-ttu-id="c1a2f-143">Per altre informazioni, vedere [Log richieste](request-log.md).</span><span class="sxs-lookup"><span data-stu-id="c1a2f-143">For more information, see [Request Log](request-log.md).</span></span>  
  
## <a name="execution-mode-dynamic-options"></a><span data-ttu-id="c1a2f-144">Opzioni dinamiche della modalità di esecuzione</span><span class="sxs-lookup"><span data-stu-id="c1a2f-144">Execution Mode Dynamic Options</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="c1a2f-145">Se non si conoscono tutti i valori richiesti per configurare l'origine, può essere necessario consultare l'amministratore SAP.</span><span class="sxs-lookup"><span data-stu-id="c1a2f-145">If you do not know all the values that are required to configure the source, you might have to ask your SAP administrator.</span></span>  
  
### <a name="execution-mode--p---trigger-process-chain"></a><span data-ttu-id="c1a2f-146">Modalità di esecuzione = P - Attivazione catena di processi</span><span class="sxs-lookup"><span data-stu-id="c1a2f-146">Execution Mode = P - Trigger Process Chain</span></span>  
  
#### <a name="rfc-destination-options"></a><span data-ttu-id="c1a2f-147">Opzioni della destinazione RFC</span><span class="sxs-lookup"><span data-stu-id="c1a2f-147">RFC Destination Options</span></span>  
 <span data-ttu-id="c1a2f-148">Non è necessario conoscere e immettere questi valori in anticipo.</span><span class="sxs-lookup"><span data-stu-id="c1a2f-148">You do not have to know and enter these values in advance.</span></span> <span data-ttu-id="c1a2f-149">Usare il pulsante **Ricerca** per individuare e selezionare la destinazione RFC appropriata.</span><span class="sxs-lookup"><span data-stu-id="c1a2f-149">Use the **Look up** button to find and select the appropriate RFC destination.</span></span> <span data-ttu-id="c1a2f-150">Dopo aver selezionato una destinazione RFC, il componente inserisce i valori appropriati per queste opzioni.</span><span class="sxs-lookup"><span data-stu-id="c1a2f-150">After you select an RFC destination, the component enters the appropriate values for these options.</span></span>  
  
 <span data-ttu-id="c1a2f-151">**Host gateway**</span><span class="sxs-lookup"><span data-stu-id="c1a2f-151">**Gateway host**</span></span>  
 <span data-ttu-id="c1a2f-152">Immettere il nome server o l'indirizzo IP dell'host gateway.</span><span class="sxs-lookup"><span data-stu-id="c1a2f-152">Enter the server name or IP address of the gateway host.</span></span> <span data-ttu-id="c1a2f-153">In genere, il nome o l'indirizzo IP è uguale a quello del server applicazioni SAP.</span><span class="sxs-lookup"><span data-stu-id="c1a2f-153">Usually, the name or IP address is the same as the SAP application server.</span></span>  
  
 <span data-ttu-id="c1a2f-154">**Servizio gateway**</span><span class="sxs-lookup"><span data-stu-id="c1a2f-154">**Gateway service**</span></span>  
 <span data-ttu-id="c1a2f-155">Immettere il nome del servizio gateway, nel formato `sapgwNN`, dove `NN` è il numero del sistema.</span><span class="sxs-lookup"><span data-stu-id="c1a2f-155">Enter the name of the gateway service, in the format `sapgwNN`, where `NN` is the system number.</span></span>  
  
 <span data-ttu-id="c1a2f-156">**ID programma**</span><span class="sxs-lookup"><span data-stu-id="c1a2f-156">**Program ID**</span></span>  
 <span data-ttu-id="c1a2f-157">Immettere l'ID programma associato alla destinazione RFC.</span><span class="sxs-lookup"><span data-stu-id="c1a2f-157">Enter the Program ID that is associated with the RFC destination.</span></span>  
  
 <span data-ttu-id="c1a2f-158">**Cerca**</span><span class="sxs-lookup"><span data-stu-id="c1a2f-158">**Look up**</span></span>  
 <span data-ttu-id="c1a2f-159">Individuare la destinazione RFC usando la finestra di dialogo **Cerca destinazione RFC** .</span><span class="sxs-lookup"><span data-stu-id="c1a2f-159">Look up the RFC destination by using the **Look Up RFC Destination** dialog box.</span></span> <span data-ttu-id="c1a2f-160">Per altre informazioni su questa finestra di dialogo, vedere [Cerca destinazione RFC](look-up-rfc-destination.md).</span><span class="sxs-lookup"><span data-stu-id="c1a2f-160">For more information about this dialog box, see [Look Up RFC Destination](look-up-rfc-destination.md).</span></span>  
  
#### <a name="process-chain-options"></a><span data-ttu-id="c1a2f-161">Opzioni della catena di processi</span><span class="sxs-lookup"><span data-stu-id="c1a2f-161">Process Chain Options</span></span>  
 <span data-ttu-id="c1a2f-162">Non è necessario conoscere e immettere questi valori in anticipo.</span><span class="sxs-lookup"><span data-stu-id="c1a2f-162">You do not have to know and enter these values in advance.</span></span> <span data-ttu-id="c1a2f-163">Usare il pulsante **Ricerca** per individuare e selezionare la catena di processi appropriata.</span><span class="sxs-lookup"><span data-stu-id="c1a2f-163">Use the **Look up** button to find and select the appropriate process chain.</span></span> <span data-ttu-id="c1a2f-164">Dopo aver selezionato una catena di processi, il componente inserisce il valore appropriato per l'opzione.</span><span class="sxs-lookup"><span data-stu-id="c1a2f-164">After you select a process chain, the component enters the appropriate value for the option.</span></span>  
  
 <span data-ttu-id="c1a2f-165">**Catena di processi**</span><span class="sxs-lookup"><span data-stu-id="c1a2f-165">**Process chain**</span></span>  
 <span data-ttu-id="c1a2f-166">Immettere il nome della catena di processi che verrà attivata da parte dell'origine.</span><span class="sxs-lookup"><span data-stu-id="c1a2f-166">Enter the name of the process chain to be triggered by the source.</span></span>  
  
 <span data-ttu-id="c1a2f-167">**Cerca**</span><span class="sxs-lookup"><span data-stu-id="c1a2f-167">**Look up**</span></span>  
 <span data-ttu-id="c1a2f-168">Individuare la catena di processi usando la finestra di dialogo **Cerca ProcessChain** .</span><span class="sxs-lookup"><span data-stu-id="c1a2f-168">Look up the process chain by using the **Look Up Process Chain** dialog box.</span></span> <span data-ttu-id="c1a2f-169">Per altre informazioni su questa finestra di dialogo, vedere [Cerca ProcessChain](look-up-process-chain.md).</span><span class="sxs-lookup"><span data-stu-id="c1a2f-169">For more information about this dialog box, see [Look Up Process Chain](look-up-process-chain.md).</span></span>  
  
### <a name="execution-mode--w---wait-for-notify"></a><span data-ttu-id="c1a2f-170">Modalità di esecuzione = W - Attesa notifica</span><span class="sxs-lookup"><span data-stu-id="c1a2f-170">Execution Mode = W - Wait for Notify</span></span>  
  
#### <a name="rfc-destination-options"></a><span data-ttu-id="c1a2f-171">Opzioni della destinazione RFC</span><span class="sxs-lookup"><span data-stu-id="c1a2f-171">RFC Destination Options</span></span>  
 <span data-ttu-id="c1a2f-172">Non è necessario conoscere e immettere questi valori in anticipo.</span><span class="sxs-lookup"><span data-stu-id="c1a2f-172">You do not have to know and enter these values in advance.</span></span> <span data-ttu-id="c1a2f-173">Usare il pulsante **Ricerca** per individuare e selezionare la destinazione RFC appropriata.</span><span class="sxs-lookup"><span data-stu-id="c1a2f-173">Use the **Look up** button to find and select the appropriate RFC destination.</span></span> <span data-ttu-id="c1a2f-174">Dopo aver selezionato una destinazione RFC, il componente inserisce i valori appropriati per le opzioni.</span><span class="sxs-lookup"><span data-stu-id="c1a2f-174">After you select an RFC destination, the component enters the appropriate values for the options.</span></span>  
  
 <span data-ttu-id="c1a2f-175">**Host gateway**</span><span class="sxs-lookup"><span data-stu-id="c1a2f-175">**Gateway host**</span></span>  
 <span data-ttu-id="c1a2f-176">Immettere il nome server o l'indirizzo IP dell'host gateway.</span><span class="sxs-lookup"><span data-stu-id="c1a2f-176">Enter the server name or IP address of the gateway host.</span></span> <span data-ttu-id="c1a2f-177">In genere, il nome o l'indirizzo IP è uguale a quello del server applicazioni SAP.</span><span class="sxs-lookup"><span data-stu-id="c1a2f-177">Usually, the name or IP address is the same as the SAP application server.</span></span>  
  
 <span data-ttu-id="c1a2f-178">**Servizio gateway**</span><span class="sxs-lookup"><span data-stu-id="c1a2f-178">**Gateway service**</span></span>  
 <span data-ttu-id="c1a2f-179">Immettere il nome del servizio gateway, nel formato `sapgwNN`, dove `NN` è il numero del sistema.</span><span class="sxs-lookup"><span data-stu-id="c1a2f-179">Enter the name of the gateway service, in the format `sapgwNN`, where `NN` is the system number.</span></span>  
  
 <span data-ttu-id="c1a2f-180">**ID programma**</span><span class="sxs-lookup"><span data-stu-id="c1a2f-180">**Program ID**</span></span>  
 <span data-ttu-id="c1a2f-181">Immettere l'ID programma associato alla destinazione RFC.</span><span class="sxs-lookup"><span data-stu-id="c1a2f-181">Enter the Program ID that is associated with the RFC destination.</span></span>  
  
 <span data-ttu-id="c1a2f-182">**Cerca**</span><span class="sxs-lookup"><span data-stu-id="c1a2f-182">**Look up**</span></span>  
 <span data-ttu-id="c1a2f-183">Individuare la destinazione RFC usando la finestra di dialogo **Cerca destinazione RFC** .</span><span class="sxs-lookup"><span data-stu-id="c1a2f-183">Look up the RFC destination by using the **Look Up RFC Destination** dialog box.</span></span> <span data-ttu-id="c1a2f-184">Per altre informazioni su questa finestra di dialogo, vedere [Cerca destinazione RFC](look-up-rfc-destination.md).</span><span class="sxs-lookup"><span data-stu-id="c1a2f-184">For more information about this dialog box, see [Look Up RFC Destination](look-up-rfc-destination.md).</span></span>  
  
### <a name="execution-mode--e---extract-only"></a><span data-ttu-id="c1a2f-185">Modalità di esecuzione = E - Solo estrazione</span><span class="sxs-lookup"><span data-stu-id="c1a2f-185">Execution Mode = E - Extract Only</span></span>  
 <span data-ttu-id="c1a2f-186">**ID richiesta**</span><span class="sxs-lookup"><span data-stu-id="c1a2f-186">**Request ID**</span></span>  
 <span data-ttu-id="c1a2f-187">Immettere l'ID richiesta associato all'estrazione.</span><span class="sxs-lookup"><span data-stu-id="c1a2f-187">Enter the Request ID that is associated with the extraction.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c1a2f-188">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c1a2f-188">See Also</span></span>  
 <span data-ttu-id="c1a2f-189">[Editor origine SAP BW &#40;pagina Colonne&#41;](sap-bw-source-editor-columns-page.md) </span><span class="sxs-lookup"><span data-stu-id="c1a2f-189">[SAP BW Source Editor &#40;Columns Page&#41;](sap-bw-source-editor-columns-page.md) </span></span>  
 <span data-ttu-id="c1a2f-190">[Editor origine SAP BW &#40;pagina Output degli errori&#41;](sap-bw-source-editor-error-output-page.md) </span><span class="sxs-lookup"><span data-stu-id="c1a2f-190">[SAP BW Source Editor &#40;Error Output Page&#41;](sap-bw-source-editor-error-output-page.md) </span></span>  
 <span data-ttu-id="c1a2f-191">[Editor origine SAP BW &#40;pagina Avanzate&#41;](sap-bw-source-editor-advanced-page.md) </span><span class="sxs-lookup"><span data-stu-id="c1a2f-191">[SAP BW Source Editor &#40;Advanced Page&#41;](sap-bw-source-editor-advanced-page.md) </span></span>  
 [<span data-ttu-id="c1a2f-192">Guida (F1) di Microsoft Connector 1.1 for SAP BW</span><span class="sxs-lookup"><span data-stu-id="c1a2f-192">Microsoft Connector 1.1 for SAP BW F1 Help</span></span>](../microsoft-connector-for-sap-bw-f1-help.md)  
  
  
