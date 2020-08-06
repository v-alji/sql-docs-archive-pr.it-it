---
title: Editor destinazione SAP BW (pagina Gestione connessione) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
ms.assetid: 04ae38f8-5287-45a3-826a-8aac5dd15a91
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 0dd628f1a0fec09490e0d3720610d1232882ed92
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87712231"
---
# <a name="sap-bw-destination-editor-connection-manager-page"></a><span data-ttu-id="d8ca1-102">Editor destinazione SAP BW (pagina Gestione connessione)</span><span class="sxs-lookup"><span data-stu-id="d8ca1-102">SAP BW Destination Editor (Connection Manager Page)</span></span>
  <span data-ttu-id="d8ca1-103">Usare la pagina **Gestione connessione** della finestra di dialogo **Editor destinazione SAP BW** per selezionare la gestione connessione SAP BW che verrà usata dalla destinazione SAP BW.</span><span class="sxs-lookup"><span data-stu-id="d8ca1-103">Use the **Connection Manager** page of the **SAP BW Destination Editor** to select the SAP BW connection manager that the SAP BW destination will use.</span></span> <span data-ttu-id="d8ca1-104">In questa pagina vengono inoltre selezionati i parametri per il caricamento dei dati nel sistema SAP Netweaver BW.</span><span class="sxs-lookup"><span data-stu-id="d8ca1-104">On this page, you also select the parameters for loading the data into the SAP Netweaver BW system.</span></span>  
  
 <span data-ttu-id="d8ca1-105">Per altre informazioni sulla destinazione SAP BW di [!INCLUDE[msCoName](../../includes/msconame-md.md)] Connector 1.1 for SAP BW, vedere [Destinazione SAP BW](sap-bw-destination.md).</span><span class="sxs-lookup"><span data-stu-id="d8ca1-105">To learn more about the SAP BW destination of the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Connector 1.1 for SAP BW, see [SAP BW Destination](sap-bw-destination.md).</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="d8ca1-106">La documentazione per Microsoft Connector 1.1 for SAP BW presuppone la conoscenza dell'ambiente SAP Netweaver BW.</span><span class="sxs-lookup"><span data-stu-id="d8ca1-106">The documentation for the Microsoft Connector 1.1 for SAP BW assumes familiarity with the SAP Netweaver BW environment.</span></span> <span data-ttu-id="d8ca1-107">Per ulteriori informazioni su SAP Netweaver BW o per informazioni su come configurare oggetti e processi di SAP Netweaver BW, vedere la documentazione SAP.</span><span class="sxs-lookup"><span data-stu-id="d8ca1-107">For more information about SAP Netweaver BW, or for information about how to configure SAP Netweaver BW objects and processes, see your SAP documentation.</span></span>  
  
 <span data-ttu-id="d8ca1-108">**Per aprire la pagina Gestione connessione**</span><span class="sxs-lookup"><span data-stu-id="d8ca1-108">**To open the Connection Manager page**</span></span>  
  
1.  <span data-ttu-id="d8ca1-109">In [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)]aprire il pacchetto [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] che contiene la destinazione SAP BW.</span><span class="sxs-lookup"><span data-stu-id="d8ca1-109">In [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], open the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] package that contains the SAP BW destination.</span></span>  
  
2.  <span data-ttu-id="d8ca1-110">Nella scheda **Flusso di dati** fare doppio clic sulla destinazione SAP BW.</span><span class="sxs-lookup"><span data-stu-id="d8ca1-110">On the **Data Flow** tab, double-click the SAP BW destination.</span></span>  
  
3.  <span data-ttu-id="d8ca1-111">Nell' **Editor destinazione SAP BW**fare clic su **Gestione connessione** per aprire la pagina **Gestione connessione** dell'editor.</span><span class="sxs-lookup"><span data-stu-id="d8ca1-111">In the **SAP BW Destination Editor**, click **Connection Manager** to open the **Connection Manager** page of the editor.</span></span>  
  
## <a name="options"></a><span data-ttu-id="d8ca1-112">Opzioni</span><span class="sxs-lookup"><span data-stu-id="d8ca1-112">Options</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="d8ca1-113">Se non si conoscono tutti i valori richiesti per configurare la destinazione, può essere necessario consultare l'amministratore SAP.</span><span class="sxs-lookup"><span data-stu-id="d8ca1-113">If you do not know all the values that are required to configure the destination, you might have to ask your SAP administrator.</span></span>  
  
 <span data-ttu-id="d8ca1-114">**Gestione connessione SAP BW**</span><span class="sxs-lookup"><span data-stu-id="d8ca1-114">**SAP BW connection manager**</span></span>  
 <span data-ttu-id="d8ca1-115">Selezionare una gestione connessione esistente nell'elenco o crearne una nuova facendo clic su **Nuova**.</span><span class="sxs-lookup"><span data-stu-id="d8ca1-115">Select an existing connection manager from the list, or create a new connection by clicking **New**.</span></span>  
  
 <span data-ttu-id="d8ca1-116">**Nuovo**</span><span class="sxs-lookup"><span data-stu-id="d8ca1-116">**New**</span></span>  
 <span data-ttu-id="d8ca1-117">Creare una nuova gestione connessione usando la finestra di dialogo **Gestione connessione SAP BW** .</span><span class="sxs-lookup"><span data-stu-id="d8ca1-117">Create a new connection manager by using the **SAP BW Connection Manager** dialog box.</span></span>  
  
 <span data-ttu-id="d8ca1-118">**Test del carico**</span><span class="sxs-lookup"><span data-stu-id="d8ca1-118">**Test Load**</span></span>  
 <span data-ttu-id="d8ca1-119">Eseguire un test del processo di caricamento che utilizzi le impostazioni selezionate e carichi zero righe.</span><span class="sxs-lookup"><span data-stu-id="d8ca1-119">Perform a test of the loading process that uses the settings that you have selected and loads zero rows.</span></span>  
  
### <a name="infopackageinfosource-options"></a><span data-ttu-id="d8ca1-120">Opzioni di InfoPackage/InfoSource</span><span class="sxs-lookup"><span data-stu-id="d8ca1-120">InfoPackage/InfoSource Options</span></span>  
 <span data-ttu-id="d8ca1-121">Non è necessario conoscere e immettere questi valori in anticipo.</span><span class="sxs-lookup"><span data-stu-id="d8ca1-121">You do not have to know and enter these values in advance.</span></span> <span data-ttu-id="d8ca1-122">Usare il pulsante **Ricerca** per individuare e selezionare l'InfoPackage appropriato.</span><span class="sxs-lookup"><span data-stu-id="d8ca1-122">Use the **Look up** button to find and select the appropriate InfoPackage.</span></span> <span data-ttu-id="d8ca1-123">Dopo aver selezionato un InfoPackage, il componente inserisce i valori appropriati per queste opzioni.</span><span class="sxs-lookup"><span data-stu-id="d8ca1-123">After you select an InfoPackage, the component enters the appropriate values for these options.</span></span>  
  
 <span data-ttu-id="d8ca1-124">**InfoPackage**</span><span class="sxs-lookup"><span data-stu-id="d8ca1-124">**InfoPackage**</span></span>  
 <span data-ttu-id="d8ca1-125">Immettere il nome dell'InfoPackage.</span><span class="sxs-lookup"><span data-stu-id="d8ca1-125">Enter the name of the InfoPackage.</span></span>  
  
 <span data-ttu-id="d8ca1-126">**InfoSource**</span><span class="sxs-lookup"><span data-stu-id="d8ca1-126">**InfoSource**</span></span>  
 <span data-ttu-id="d8ca1-127">Immettere il nome dell'InfoSource.</span><span class="sxs-lookup"><span data-stu-id="d8ca1-127">Enter the name of the InfoSource.</span></span>  
  
 <span data-ttu-id="d8ca1-128">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="d8ca1-128">**Type**</span></span>  
 <span data-ttu-id="d8ca1-129">Immettere il carattere singolo che identifica il tipo di InfoSource.</span><span class="sxs-lookup"><span data-stu-id="d8ca1-129">Enter the single-character that identifies the type of the InfoSource.</span></span> <span data-ttu-id="d8ca1-130">Nella tabella seguente sono elencati i valori a carattere singolo accettabili.</span><span class="sxs-lookup"><span data-stu-id="d8ca1-130">The following table lists the acceptable single-character values.</span></span>  
  
|<span data-ttu-id="d8ca1-131">valore</span><span class="sxs-lookup"><span data-stu-id="d8ca1-131">Value</span></span>|<span data-ttu-id="d8ca1-132">Descrizione</span><span class="sxs-lookup"><span data-stu-id="d8ca1-132">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="d8ca1-133">**D**</span><span class="sxs-lookup"><span data-stu-id="d8ca1-133">**D**</span></span>|<span data-ttu-id="d8ca1-134">Dati transazione</span><span class="sxs-lookup"><span data-stu-id="d8ca1-134">Transaction data</span></span>|  
|<span data-ttu-id="d8ca1-135">**M**</span><span class="sxs-lookup"><span data-stu-id="d8ca1-135">**M**</span></span>|<span data-ttu-id="d8ca1-136">Dati master</span><span class="sxs-lookup"><span data-stu-id="d8ca1-136">Master data</span></span>|  
|<span data-ttu-id="d8ca1-137">**T**</span><span class="sxs-lookup"><span data-stu-id="d8ca1-137">**T**</span></span>|<span data-ttu-id="d8ca1-138">Testi</span><span class="sxs-lookup"><span data-stu-id="d8ca1-138">Texts</span></span>|  
|<span data-ttu-id="d8ca1-139">**H**</span><span class="sxs-lookup"><span data-stu-id="d8ca1-139">**H**</span></span>|<span data-ttu-id="d8ca1-140">Dati gerarchia</span><span class="sxs-lookup"><span data-stu-id="d8ca1-140">Hierarchy data</span></span>|  
  
 <span data-ttu-id="d8ca1-141">**Sistema logico**</span><span class="sxs-lookup"><span data-stu-id="d8ca1-141">**Logical system**</span></span>  
 <span data-ttu-id="d8ca1-142">Immettere il nome del sistema logico associato all'InfoPackage.</span><span class="sxs-lookup"><span data-stu-id="d8ca1-142">Enter the name of the logical system that is associated with the InfoPackage.</span></span>  
  
 <span data-ttu-id="d8ca1-143">**Cerca**</span><span class="sxs-lookup"><span data-stu-id="d8ca1-143">**Look up**</span></span>  
 <span data-ttu-id="d8ca1-144">Individuare l'InfoPackage usando la finestra di dialogo **Cerca InfoPackage** .</span><span class="sxs-lookup"><span data-stu-id="d8ca1-144">Look up the InfoPackage by using the **Look Up InfoPackage** dialog box.</span></span> <span data-ttu-id="d8ca1-145">Per altre informazioni su questa finestra di dialogo, vedere [Cerca InfoPackage](look-up-infopackage.md).</span><span class="sxs-lookup"><span data-stu-id="d8ca1-145">For more information about this dialog box, see [Look Up InfoPackage](look-up-infopackage.md).</span></span>  
  
### <a name="rfc-destination-options"></a><span data-ttu-id="d8ca1-146">Opzioni della destinazione RFC</span><span class="sxs-lookup"><span data-stu-id="d8ca1-146">RFC Destination Options</span></span>  
 <span data-ttu-id="d8ca1-147">Non è necessario conoscere e immettere questi valori in anticipo.</span><span class="sxs-lookup"><span data-stu-id="d8ca1-147">You do not have to know and enter these values in advance.</span></span> <span data-ttu-id="d8ca1-148">Usare il pulsante **Ricerca** per individuare e selezionare la destinazione RFC appropriata.</span><span class="sxs-lookup"><span data-stu-id="d8ca1-148">Use the **Look up** button to find and select the appropriate RFC destination.</span></span> <span data-ttu-id="d8ca1-149">Dopo aver selezionato una destinazione RFC, il componente inserisce i valori appropriati per queste opzioni.</span><span class="sxs-lookup"><span data-stu-id="d8ca1-149">After you select an RFC destination, the component enters the appropriate values for these options.</span></span>  
  
 <span data-ttu-id="d8ca1-150">**Host gateway**</span><span class="sxs-lookup"><span data-stu-id="d8ca1-150">**Gateway host**</span></span>  
 <span data-ttu-id="d8ca1-151">Immettere il nome server o l'indirizzo IP dell'host gateway.</span><span class="sxs-lookup"><span data-stu-id="d8ca1-151">Enter the server name or IP address of the gateway host.</span></span> <span data-ttu-id="d8ca1-152">In genere, il nome o l'indirizzo IP è uguale a quello del server applicazioni SAP.</span><span class="sxs-lookup"><span data-stu-id="d8ca1-152">Usually, the name or IP address is the same as the SAP application server.</span></span>  
  
 <span data-ttu-id="d8ca1-153">**Servizio gateway**</span><span class="sxs-lookup"><span data-stu-id="d8ca1-153">**Gateway service**</span></span>  
 <span data-ttu-id="d8ca1-154">Immettere il nome del servizio gateway, nel formato `sapgwNN`, dove `NN` è il numero del sistema.</span><span class="sxs-lookup"><span data-stu-id="d8ca1-154">Enter the name of the gateway service, in the format `sapgwNN`, where `NN` is the system number.</span></span>  
  
 <span data-ttu-id="d8ca1-155">**ID programma**</span><span class="sxs-lookup"><span data-stu-id="d8ca1-155">**Program ID**</span></span>  
 <span data-ttu-id="d8ca1-156">Immettere l'ID programma associato alla destinazione RFC.</span><span class="sxs-lookup"><span data-stu-id="d8ca1-156">Enter the Program ID that is associated with the RFC destination.</span></span>  
  
 <span data-ttu-id="d8ca1-157">**Cerca**</span><span class="sxs-lookup"><span data-stu-id="d8ca1-157">**Look up**</span></span>  
 <span data-ttu-id="d8ca1-158">Individuare la destinazione RFC usando la finestra di dialogo **Cerca destinazione RFC** .</span><span class="sxs-lookup"><span data-stu-id="d8ca1-158">Look up the RFC destination by using the **Look Up RFC Destination** dialog box.</span></span> <span data-ttu-id="d8ca1-159">Per altre informazioni su questa finestra di dialogo, vedere [Cerca destinazione RFC](look-up-rfc-destination.md).</span><span class="sxs-lookup"><span data-stu-id="d8ca1-159">For more information about this dialog box, see [Look Up RFC Destination](look-up-rfc-destination.md).</span></span>  
  
### <a name="create-sap-bw-objects-options"></a><span data-ttu-id="d8ca1-160">Opzioni di Crea oggetti SAP BW</span><span class="sxs-lookup"><span data-stu-id="d8ca1-160">Create SAP BW Objects Options</span></span>  
 <span data-ttu-id="d8ca1-161">**Seleziona il tipo di oggetto**</span><span class="sxs-lookup"><span data-stu-id="d8ca1-161">**Select object type**</span></span>  
 <span data-ttu-id="d8ca1-162">Selezionare il tipo di oggetto SAP Netweaver BW che si desidera creare.</span><span class="sxs-lookup"><span data-stu-id="d8ca1-162">Select the type of SAP Netweaver BW object that you want to create.</span></span> <span data-ttu-id="d8ca1-163">È possibile selezionare uno dei tipi seguenti:</span><span class="sxs-lookup"><span data-stu-id="d8ca1-163">You can select one of the following types:</span></span>  
  
-   <span data-ttu-id="d8ca1-164">InfoObject</span><span class="sxs-lookup"><span data-stu-id="d8ca1-164">InfoObject</span></span>  
  
-   <span data-ttu-id="d8ca1-165">InfoCube</span><span class="sxs-lookup"><span data-stu-id="d8ca1-165">InfoCube</span></span>  
  
-   <span data-ttu-id="d8ca1-166">InfoSource</span><span class="sxs-lookup"><span data-stu-id="d8ca1-166">InfoSource</span></span>  
  
-   <span data-ttu-id="d8ca1-167">InfoPackage</span><span class="sxs-lookup"><span data-stu-id="d8ca1-167">InfoPackage</span></span>  
  
 <span data-ttu-id="d8ca1-168">**Creare**</span><span class="sxs-lookup"><span data-stu-id="d8ca1-168">**Create**</span></span>  
 <span data-ttu-id="d8ca1-169">Creare il tipo selezionato di oggetto SAP Netweaver BW.</span><span class="sxs-lookup"><span data-stu-id="d8ca1-169">Create the selected type of SAP Netweaver BW object.</span></span>  
  
|<span data-ttu-id="d8ca1-170">Tipo di oggetto</span><span class="sxs-lookup"><span data-stu-id="d8ca1-170">Object Type</span></span>|<span data-ttu-id="d8ca1-171">Risultato</span><span class="sxs-lookup"><span data-stu-id="d8ca1-171">Result</span></span>|  
|-----------------|------------|  
|<span data-ttu-id="d8ca1-172">**InfoObject**</span><span class="sxs-lookup"><span data-stu-id="d8ca1-172">**InfoObject**</span></span>|<span data-ttu-id="d8ca1-173">Creare un nuovo InfoObject usando la finestra di dialogo **Crea nuovo InfoObject** .</span><span class="sxs-lookup"><span data-stu-id="d8ca1-173">Create a new InfoObject by using the **Create New InfoObject** dialog box.</span></span> <span data-ttu-id="d8ca1-174">Per altre informazioni su questa finestra di dialogo, vedere [Crea nuovo InfoObject](create-new-infoobject.md).</span><span class="sxs-lookup"><span data-stu-id="d8ca1-174">For more information about this dialog box, see [Create New InfoObject](create-new-infoobject.md).</span></span>|  
|<span data-ttu-id="d8ca1-175">**InfoCube**</span><span class="sxs-lookup"><span data-stu-id="d8ca1-175">**InfoCube**</span></span>|<span data-ttu-id="d8ca1-176">Creare un nuovo InfoCube usando la finestra di dialogo **Crea InfoCube per dati transazione** .</span><span class="sxs-lookup"><span data-stu-id="d8ca1-176">Create a new InfoCube by using the **Create InfoCube for Transaction Data** dialog box.</span></span> <span data-ttu-id="d8ca1-177">Per altre informazioni su questa finestra di dialogo, vedere [Crea InfoCube per dati transazione](create-infocube-for-transaction-data.md).</span><span class="sxs-lookup"><span data-stu-id="d8ca1-177">For more information about this dialog box, see [Create InfoCube for Transaction Data](create-infocube-for-transaction-data.md).</span></span>|  
|<span data-ttu-id="d8ca1-178">**InfoSource**</span><span class="sxs-lookup"><span data-stu-id="d8ca1-178">**InfoSource**</span></span>|<span data-ttu-id="d8ca1-179">Creare un nuovo InfoSource usando la finestra di dialogo **Crea InfoSource** e quindi la finestra di dialogo **Crea InfoSource per dati transazione** o **Crea InfoSource per dati master** .</span><span class="sxs-lookup"><span data-stu-id="d8ca1-179">Create a new InfoSource by using the **Create InfoSource** dialog box, and then by using the **Create InfoSource for Transaction Data** or the **Create InfoSource for Master Data** dialog box.</span></span> <span data-ttu-id="d8ca1-180">Per altre informazioni su queste finestre di dialogo, vedere [Crea InfoSource](create-infosource.md), [Crea InfoSource per dati transazione](create-infosource-for-transaction-data.md) e [Crea InfoSource per dati master](create-infosource-for-master-data.md).</span><span class="sxs-lookup"><span data-stu-id="d8ca1-180">For more information about these dialog boxes, see [Create InfoSource](create-infosource.md), [Create InfoSource for Transaction Data](create-infosource-for-transaction-data.md) and [Create InfoSource for Master Data](create-infosource-for-master-data.md).</span></span>|  
|<span data-ttu-id="d8ca1-181">**InfoPackage**</span><span class="sxs-lookup"><span data-stu-id="d8ca1-181">**InfoPackage**</span></span>|<span data-ttu-id="d8ca1-182">Creare un nuovo InfoPackage usando la finestra di dialogo **Crea InfoPackage** .</span><span class="sxs-lookup"><span data-stu-id="d8ca1-182">Create a new InfoPackage by using the **Create InfoPackage** dialog box.</span></span> <span data-ttu-id="d8ca1-183">Per altre informazioni su questa finestra di dialogo, vedere [Crea InfoPackage](create-infopackage.md).</span><span class="sxs-lookup"><span data-stu-id="d8ca1-183">For more information about this dialog box, see [Create InfoPackage](create-infopackage.md).</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="d8ca1-184">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d8ca1-184">See Also</span></span>  
 <span data-ttu-id="d8ca1-185">[Editor destinazione SAP BW &#40;pagina Mapping&#41;](sap-bw-destination-editor-mappings-page.md) </span><span class="sxs-lookup"><span data-stu-id="d8ca1-185">[SAP BW Destination Editor &#40;Mappings Page&#41;](sap-bw-destination-editor-mappings-page.md) </span></span>  
 <span data-ttu-id="d8ca1-186">[Editor destinazione SAP BW &#40;pagina Output degli errori&#41;](sap-bw-destination-editor-error-output-page.md) </span><span class="sxs-lookup"><span data-stu-id="d8ca1-186">[SAP BW Destination Editor &#40;Error Output Page&#41;](sap-bw-destination-editor-error-output-page.md) </span></span>  
 <span data-ttu-id="d8ca1-187">[Editor destinazione SAP BW &#40;pagina Avanzate&#41;](sap-bw-destination-editor-advanced-page.md) </span><span class="sxs-lookup"><span data-stu-id="d8ca1-187">[SAP BW Destination Editor &#40;Advanced Page&#41;](sap-bw-destination-editor-advanced-page.md) </span></span>  
 [<span data-ttu-id="d8ca1-188">Guida (F1) di Microsoft Connector 1.1 for SAP BW</span><span class="sxs-lookup"><span data-stu-id="d8ca1-188">Microsoft Connector 1.1 for SAP BW F1 Help</span></span>](../microsoft-connector-for-sap-bw-f1-help.md)  
  
  
