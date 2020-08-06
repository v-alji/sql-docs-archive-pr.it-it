---
title: Cerca InfoObject | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
ms.assetid: e7f4c132-a5ec-49d8-a964-45775432731f
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 1616b4fcb368afc9e3f1157a3fc2511d4a7e8cce
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87715607"
---
# <a name="look-up-infoobject"></a><span data-ttu-id="276c5-102">Cerca InfoObject</span><span class="sxs-lookup"><span data-stu-id="276c5-102">Look Up InfoObject</span></span>
  <span data-ttu-id="276c5-103">Utilizzare la finestra di dialogo **Cerca InfoObject** per cercare un InfoObject definito nel sistema SAP Netweaver BW.</span><span class="sxs-lookup"><span data-stu-id="276c5-103">Use the **Look Up InfoObject** dialog box to look up an InfoObject that is defined in the SAP Netweaver BW system.</span></span> <span data-ttu-id="276c5-104">Quando viene visualizzato l'elenco degli InfoObject disponibili, selezionare l'InfoObject desiderato e le opzioni associate verranno compilate con i valori richiesti dalla destinazione SAP BW.</span><span class="sxs-lookup"><span data-stu-id="276c5-104">When the list of available InfoObjects appears, select the InfoObject that you want, and the SAP BW destination will populate the associated options with the required values.</span></span>  
  
 <span data-ttu-id="276c5-105">La destinazione SAP BW di [!INCLUDE[msCoName](../../includes/msconame-md.md)] Connector 1.1 for SAP BW utilizza la finestra di dialogo **Cerca InfoObject** .</span><span class="sxs-lookup"><span data-stu-id="276c5-105">The SAP BW destination of the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Connector 1.1 for SAP BW uses the **Look Up InfoObject** dialog box.</span></span> <span data-ttu-id="276c5-106">Per ulteriori informazioni sulla destinazione SAP BW, vedere [SAP BW Destination](sap-bw-destination.md).</span><span class="sxs-lookup"><span data-stu-id="276c5-106">To learn more about the SAP BW destination, see [SAP BW Destination](sap-bw-destination.md).</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="276c5-107">La documentazione per Microsoft Connector 1.1 for SAP BW presuppone la conoscenza dell'ambiente SAP Netweaver BW.</span><span class="sxs-lookup"><span data-stu-id="276c5-107">The documentation for the Microsoft Connector 1.1 for SAP BW assumes familiarity with the SAP Netweaver BW environment.</span></span> <span data-ttu-id="276c5-108">Per ulteriori informazioni su SAP Netweaver BW o per informazioni su come configurare oggetti e processi di SAP Netweaver BW, vedere la documentazione SAP.</span><span class="sxs-lookup"><span data-stu-id="276c5-108">For more information about SAP Netweaver BW, or for information about how to configure SAP Netweaver BW objects and processes, see your SAP documentation.</span></span>  
  
 <span data-ttu-id="276c5-109">**Per aprire la finestra di dialogo Cerca InfoObject**</span><span class="sxs-lookup"><span data-stu-id="276c5-109">**To open the Look Up InfoObject dialog box**</span></span>  
  
1.  <span data-ttu-id="276c5-110">In [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)]aprire il pacchetto [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] che contiene la destinazione SAP BW.</span><span class="sxs-lookup"><span data-stu-id="276c5-110">In [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], open the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] package that contains the SAP BW destination.</span></span>  
  
2.  <span data-ttu-id="276c5-111">Nella scheda **Flusso di dati** fare doppio clic sulla destinazione SAP BW.</span><span class="sxs-lookup"><span data-stu-id="276c5-111">On the **Data Flow** tab, double-click the SAP BW destination.</span></span>  
  
3.  <span data-ttu-id="276c5-112">Nell' **Editor destinazione SAP BW**fare clic su **Gestione connessione** per aprire la pagina **Gestione connessione** dell'editor.</span><span class="sxs-lookup"><span data-stu-id="276c5-112">In the **SAP BW Destination Editor**, click **Connection Manager** to open the **Connection Manager** page of the editor.</span></span>  
  
4.  <span data-ttu-id="276c5-113">Nella casella di gruppo **Crea oggetti SAP BW** della pagina **Gestione connessione** selezionare una delle seguenti opzioni:</span><span class="sxs-lookup"><span data-stu-id="276c5-113">On the **Connection Manager** page, in the **Create SAP BW Objects** group box, select one of the following options:</span></span>  
  
    1.  <span data-ttu-id="276c5-114">Selezionare **InfoCube**.</span><span class="sxs-lookup"><span data-stu-id="276c5-114">Select **InfoCube**.</span></span> <span data-ttu-id="276c5-115">Scegliere quindi **Crea**.</span><span class="sxs-lookup"><span data-stu-id="276c5-115">Then, click **Create**.</span></span> <span data-ttu-id="276c5-116">Nella finestra di dialogo **Crea InfoCube per dati transazione** fare clic su **Cerca** nella colonna **IObject** per una delle righe nell'elenco.</span><span class="sxs-lookup"><span data-stu-id="276c5-116">In the **Create InfoCube for Transaction Data** dialog box, click **Search** in the **IObject** column for one of the rows in the list.</span></span> <span data-ttu-id="276c5-117">Ogni riga rappresenta una colonna nel flusso di dati del pacchetto.</span><span class="sxs-lookup"><span data-stu-id="276c5-117">Each row represents a column in the data flow of the package.</span></span>  
  
    2.  <span data-ttu-id="276c5-118">Selezionare **InfoSource**.</span><span class="sxs-lookup"><span data-stu-id="276c5-118">Select **InfoSource**.</span></span> <span data-ttu-id="276c5-119">Fare quindi clic su **Crea**.</span><span class="sxs-lookup"><span data-stu-id="276c5-119">Then click **Create**.</span></span> <span data-ttu-id="276c5-120">Nella finestra di dialogo **Crea InfoSource** selezionare **Dati transazione**.</span><span class="sxs-lookup"><span data-stu-id="276c5-120">In the **Create InfoSource** dialog box, select **Transaction data**.</span></span> <span data-ttu-id="276c5-121">Nella finestra di dialogo **Crea InfoSource per dati transazione** fare clic su **Cerca** nella colonna **IObject** per una delle righe nell'elenco.</span><span class="sxs-lookup"><span data-stu-id="276c5-121">In the **Create InfoSource for Transaction Data** dialog box, click **Search** in the **IObject** column for one of the rows in the list.</span></span> <span data-ttu-id="276c5-122">Ogni riga rappresenta una colonna nel flusso di dati del pacchetto.</span><span class="sxs-lookup"><span data-stu-id="276c5-122">Each row represents a column in the data flow of the package.</span></span>  
  
    3.  <span data-ttu-id="276c5-123">Selezionare **InfoSource**.</span><span class="sxs-lookup"><span data-stu-id="276c5-123">Select **InfoSource**.</span></span> <span data-ttu-id="276c5-124">Fare quindi clic su **Crea**.</span><span class="sxs-lookup"><span data-stu-id="276c5-124">Then click **Create**.</span></span> <span data-ttu-id="276c5-125">Nella finestra di dialogo **Crea InfoSource** selezionare **Dati master**.</span><span class="sxs-lookup"><span data-stu-id="276c5-125">In the **Create InfoSource** dialog box, select **Master data**.</span></span> <span data-ttu-id="276c5-126">Nella finestra di dialogo **Crea InfoSource per dati master** scegliere **Cerca**.</span><span class="sxs-lookup"><span data-stu-id="276c5-126">In the **Create InfoSource for Master Data** dialog box, click **Look up**.</span></span>  
  
 <span data-ttu-id="276c5-127">È inoltre possibile aprire la finestra di dialogo **Cerca InfoObject** facendo clic su **Aggiungi** nella sezione **Attributi** della finestra di dialogo **Crea nuovo InfoObject** .</span><span class="sxs-lookup"><span data-stu-id="276c5-127">You can also open the **Look Up InfoObject** dialog box by clicking **Add** in the **Attributes** section of the **Create New InfoObject** dialog box.</span></span>  
  
## <a name="lookup-options"></a><span data-ttu-id="276c5-128">Opzioni di ricerca</span><span class="sxs-lookup"><span data-stu-id="276c5-128">Lookup Options</span></span>  
 <span data-ttu-id="276c5-129">Nelle caselle di testo dei campi di ricerca è possibile filtrare i risultati tramite il carattere jolly asterisco (\*) oppure utilizzando una stringa parziale in combinazione con il carattere jolly asterisco.</span><span class="sxs-lookup"><span data-stu-id="276c5-129">In the lookup field text boxes, you can filter results by using the asterisk wildcard character (\*), or by using a partial string in combination with the asterisk wildcard character.</span></span> <span data-ttu-id="276c5-130">Tuttavia, se si lascia un campo di ricerca vuoto, il processo di ricerca restituirà solo stringhe vuote in tale campo.</span><span class="sxs-lookup"><span data-stu-id="276c5-130">However, if you leave a lookup field empty, the lookup process will only match empty strings in that field.</span></span>  
  
 <span data-ttu-id="276c5-131">**Caratteristiche**</span><span class="sxs-lookup"><span data-stu-id="276c5-131">**Characteristics**</span></span>  
 <span data-ttu-id="276c5-132">Cercare InfoObject che rappresentino le caratteristiche.</span><span class="sxs-lookup"><span data-stu-id="276c5-132">Look up InfoObjects that represent characteristics.</span></span>  
  
 <span data-ttu-id="276c5-133">**Unità**</span><span class="sxs-lookup"><span data-stu-id="276c5-133">**Units**</span></span>  
 <span data-ttu-id="276c5-134">Cercare InfoObject che rappresentino le unità.</span><span class="sxs-lookup"><span data-stu-id="276c5-134">Look up InfoObjects that represent units.</span></span>  
  
 <span data-ttu-id="276c5-135">**Cifre chiave**</span><span class="sxs-lookup"><span data-stu-id="276c5-135">**Key figures**</span></span>  
 <span data-ttu-id="276c5-136">Cercare InfoObject che rappresentino le cifre chiave.</span><span class="sxs-lookup"><span data-stu-id="276c5-136">Look up InfoObjects that represent key figures.</span></span>  
  
 <span data-ttu-id="276c5-137">**Caratteristiche ora**</span><span class="sxs-lookup"><span data-stu-id="276c5-137">**Time characteristics**</span></span>  
 <span data-ttu-id="276c5-138">Cercare InfoObject che rappresentino le caratteristiche orarie.</span><span class="sxs-lookup"><span data-stu-id="276c5-138">Look up InfoObjects that represent time characteristics.</span></span>  
  
 <span data-ttu-id="276c5-139">**Nome**</span><span class="sxs-lookup"><span data-stu-id="276c5-139">**Name**</span></span>  
 <span data-ttu-id="276c5-140">Immettere il nome dell'InfoObject da cercare oppure un nome parziale con il carattere jolly asterisco (\*).</span><span class="sxs-lookup"><span data-stu-id="276c5-140">Enter the name of the InfoObject that you want to look up, or a partial name with the asterisk wildcard character (\*).</span></span> <span data-ttu-id="276c5-141">In alternativa, utilizzare il carattere jolly asterisco da solo per includere tutti gli InfoObject.</span><span class="sxs-lookup"><span data-stu-id="276c5-141">Or, use the asterisk wildcard character alone to include all InfoObjects.</span></span>  
  
 <span data-ttu-id="276c5-142">**Descrizione**</span><span class="sxs-lookup"><span data-stu-id="276c5-142">**Description**</span></span>  
 <span data-ttu-id="276c5-143">Immettere la descrizione o una descrizione parziale con il carattere jolly asterisco (\*).</span><span class="sxs-lookup"><span data-stu-id="276c5-143">Enter the description, or a partial description with the asterisk wildcard character (\*).</span></span> <span data-ttu-id="276c5-144">In alternativa, utilizzare il carattere jolly asterisco da solo per includere tutti gli InfoObject indipendentemente dalla descrizione.</span><span class="sxs-lookup"><span data-stu-id="276c5-144">Or, use the asterisk wildcard character alone to include all InfoObjects regardless of description.</span></span>  
  
 <span data-ttu-id="276c5-145">**Cerca**</span><span class="sxs-lookup"><span data-stu-id="276c5-145">**Look up**</span></span>  
 <span data-ttu-id="276c5-146">Cercare gli InfoObject corrispondenti definiti nel sistema SAP Netweaver BW.</span><span class="sxs-lookup"><span data-stu-id="276c5-146">Look up matching InfoObjects that are defined in the SAP Netweaver BW system.</span></span>  
  
## <a name="lookup-results"></a><span data-ttu-id="276c5-147">Risultati di ricerca</span><span class="sxs-lookup"><span data-stu-id="276c5-147">Lookup Results</span></span>  
 <span data-ttu-id="276c5-148">Dopo avere fatto clic sul pulsante Ricerca, viene visualizzato un elenco di InfoObject nel sistema SAP Netweaver BW in una tabella con le intestazioni di colonna seguenti.</span><span class="sxs-lookup"><span data-stu-id="276c5-148">After you click the Look up button, a list of the InfoObjects in the SAP Netweaver BW system appears in a table with the following column headings.</span></span>  
  
 <span data-ttu-id="276c5-149">**InfoObject**</span><span class="sxs-lookup"><span data-stu-id="276c5-149">**InfoObject**</span></span>  
 <span data-ttu-id="276c5-150">Visualizza il nome dell'InfoObject definito nel sistema SAP Netweaver BW.</span><span class="sxs-lookup"><span data-stu-id="276c5-150">Displays the name of the InfoObject that is defined in the SAP Netweaver BW system.</span></span>  
  
 <span data-ttu-id="276c5-151">**Testo (breve)**</span><span class="sxs-lookup"><span data-stu-id="276c5-151">**Text (short)**</span></span>  
 <span data-ttu-id="276c5-152">Visualizza il testo breve associato all'InfoObject.</span><span class="sxs-lookup"><span data-stu-id="276c5-152">Displays the short text that is associated with the InfoObject.</span></span>  
  
 <span data-ttu-id="276c5-153">Quando viene visualizzato l'elenco degli InfoObject disponibili, selezionare l'InfoObject desiderato e le opzioni associate verranno compilate con i valori richiesti dalla destinazione.</span><span class="sxs-lookup"><span data-stu-id="276c5-153">When the list of available InfoObjects appears, select the InfoObject that you want, and the destination will populate the associated options with the required values.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="276c5-154">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="276c5-154">See Also</span></span>  
 <span data-ttu-id="276c5-155">[Crea InfoCube per dati transazione](create-infocube-for-transaction-data.md) </span><span class="sxs-lookup"><span data-stu-id="276c5-155">[Create InfoCube for Transaction Data](create-infocube-for-transaction-data.md) </span></span>  
 <span data-ttu-id="276c5-156">[Crea InfoSource](create-infosource.md) </span><span class="sxs-lookup"><span data-stu-id="276c5-156">[Create InfoSource](create-infosource.md) </span></span>  
 <span data-ttu-id="276c5-157">[Crea InfoSource per dati transazione](create-infosource-for-transaction-data.md) </span><span class="sxs-lookup"><span data-stu-id="276c5-157">[Create InfoSource for Transaction Data](create-infosource-for-transaction-data.md) </span></span>  
 <span data-ttu-id="276c5-158">[Crea InfoSource per dati master](create-infosource-for-master-data.md) </span><span class="sxs-lookup"><span data-stu-id="276c5-158">[Create InfoSource for Master Data](create-infosource-for-master-data.md) </span></span>  
 <span data-ttu-id="276c5-159">[Crea nuovo InfoObject](create-new-infoobject.md) </span><span class="sxs-lookup"><span data-stu-id="276c5-159">[Create New InfoObject](create-new-infoobject.md) </span></span>  
 <span data-ttu-id="276c5-160">[Editor destinazione SAP BW &#40;pagina Gestione connessione&#41;](sap-bw-destination-editor-connection-manager-page.md) </span><span class="sxs-lookup"><span data-stu-id="276c5-160">[SAP BW Destination Editor &#40;Connection Manager Page&#41;](sap-bw-destination-editor-connection-manager-page.md) </span></span>  
 [<span data-ttu-id="276c5-161">Guida (F1) di Microsoft Connector 1.1 for SAP BW</span><span class="sxs-lookup"><span data-stu-id="276c5-161">Microsoft Connector 1.1 for SAP BW F1 Help</span></span>](../microsoft-connector-for-sap-bw-f1-help.md)  
  
  
