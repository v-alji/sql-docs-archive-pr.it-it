---
title: Cerca InfoPackage | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
ms.assetid: 7c0cb7a4-cd07-44cc-85cb-eb1ad91f85fd
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 1e45477e8faeed07faa114850e10a3bc4bbcf170
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87715604"
---
# <a name="look-up-infopackage"></a><span data-ttu-id="f8c96-102">Cerca InfoPackage</span><span class="sxs-lookup"><span data-stu-id="f8c96-102">Look Up InfoPackage</span></span>
  <span data-ttu-id="f8c96-103">Utilizzare la finestra di dialogo **Cerca InfoPackage** per cercare un InfoPackage definito nel sistema SAP Netweaver BW.</span><span class="sxs-lookup"><span data-stu-id="f8c96-103">Use the **Look Up InfoPackage** dialog box to look up an InfoPackage that is defined in the SAP Netweaver BW system.</span></span> <span data-ttu-id="f8c96-104">Quando viene visualizzato l'elenco di InfoPackage, selezionare l'InfoPackage desiderato e le opzioni associate verranno compilate con i valori richiesti dalla destinazione.</span><span class="sxs-lookup"><span data-stu-id="f8c96-104">When the list of InfoPackages appears, select the InfoPackage that you want, and the destination will populate the associated options with the required values.</span></span>  
  
 <span data-ttu-id="f8c96-105">La destinazione SAP BW di [!INCLUDE[msCoName](../../includes/msconame-md.md)] Connector 1.1 for SAP BW utilizza la finestra di dialogo **Cerca ProcessChain** .</span><span class="sxs-lookup"><span data-stu-id="f8c96-105">The SAP BW destination of the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Connector 1.1 for SAP BW uses the **Look Up Process Chain** dialog box.</span></span> <span data-ttu-id="f8c96-106">Per ulteriori informazioni sulla destinazione SAP BW, vedere [SAP BW Destination](sap-bw-destination.md).</span><span class="sxs-lookup"><span data-stu-id="f8c96-106">To learn more about the SAP BW destination, see [SAP BW Destination](sap-bw-destination.md).</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="f8c96-107">La documentazione per Microsoft Connector 1.1 for SAP BW presuppone la conoscenza dell'ambiente SAP Netweaver BW.</span><span class="sxs-lookup"><span data-stu-id="f8c96-107">The documentation for the Microsoft Connector 1.1 for SAP BW assumes familiarity with the SAP Netweaver BW environment.</span></span> <span data-ttu-id="f8c96-108">Per ulteriori informazioni su SAP Netweaver BW o per informazioni su come configurare oggetti e processi di SAP Netweaver BW, vedere la documentazione SAP.</span><span class="sxs-lookup"><span data-stu-id="f8c96-108">For more information about SAP Netweaver BW, or for information about how to configure SAP Netweaver BW objects and processes, see your SAP documentation.</span></span>  
  
 <span data-ttu-id="f8c96-109">**Per aprire la finestra di dialogo Cerca InfoPackage**</span><span class="sxs-lookup"><span data-stu-id="f8c96-109">**To open the Look Up InfoPackage dialog box**</span></span>  
  
1.  <span data-ttu-id="f8c96-110">In [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)]aprire il pacchetto [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] che contiene la destinazione SAP BW.</span><span class="sxs-lookup"><span data-stu-id="f8c96-110">In [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], open the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] package that contains the SAP BW destination.</span></span>  
  
2.  <span data-ttu-id="f8c96-111">Nella scheda **Flusso di dati** fare doppio clic sulla destinazione SAP BW.</span><span class="sxs-lookup"><span data-stu-id="f8c96-111">On the **Data Flow** tab, double-click the SAP BW destination.</span></span>  
  
3.  <span data-ttu-id="f8c96-112">Nell' **Editor destinazione SAP BW**fare clic su **Gestione connessione** per aprire la pagina **Gestione connessione** dell'editor.</span><span class="sxs-lookup"><span data-stu-id="f8c96-112">In the **SAP BW Destination Editor**, click **Connection Manager** to open the **Connection Manager** page of the editor.</span></span>  
  
4.  <span data-ttu-id="f8c96-113">Nella pagina **Gestione connessione** , nella casella di gruppo **InfoPackage/InfoSource** fare clic su **Ricerca** per visualizzare la finestra di dialogo **Cerca InfoPackage** .</span><span class="sxs-lookup"><span data-stu-id="f8c96-113">On the **Connection Manager** page, in the **InfoPackage/InfoSource** group box, click **Look up** to display the **Look Up InfoPackage** dialog box.</span></span>  
  
## <a name="lookup-options"></a><span data-ttu-id="f8c96-114">Opzioni di ricerca</span><span class="sxs-lookup"><span data-stu-id="f8c96-114">Lookup Options</span></span>  
 <span data-ttu-id="f8c96-115">Nei campi di ricerca è possibile filtrare i risultati tramite il carattere jolly asterisco (\*) oppure utilizzando una stringa parziale in combinazione con il carattere jolly asterisco.</span><span class="sxs-lookup"><span data-stu-id="f8c96-115">In the lookup fields, you can filter results by using the asterisk wildcard character (\*), or by using a partial string in combination with the asterisk wildcard character.</span></span> <span data-ttu-id="f8c96-116">Tuttavia, se si lascia un campo di ricerca vuoto, l'operazione di ricerca restituirà solo stringhe vuote in tale campo.</span><span class="sxs-lookup"><span data-stu-id="f8c96-116">However, if you leave a lookup field empty, the lookup operation will only match empty strings in that field.</span></span>  
  
 <span data-ttu-id="f8c96-117">**InfoPackage**</span><span class="sxs-lookup"><span data-stu-id="f8c96-117">**InfoPackage**</span></span>  
 <span data-ttu-id="f8c96-118">Immettere il nome dell'InfoPackage da cercare oppure un nome parziale con il carattere jolly asterisco (\*).</span><span class="sxs-lookup"><span data-stu-id="f8c96-118">Enter the name of the InfoPackage that you want to look up, or a partial name with the asterisk wildcard character (\*).</span></span> <span data-ttu-id="f8c96-119">In alternativa, utilizzare il carattere jolly asterisco da solo per includere tutti gli InfoPackage.</span><span class="sxs-lookup"><span data-stu-id="f8c96-119">Or, use the asterisk wildcard character alone to include all InfoPackages.</span></span>  
  
 <span data-ttu-id="f8c96-120">**InfoSource**</span><span class="sxs-lookup"><span data-stu-id="f8c96-120">**InfoSource**</span></span>  
 <span data-ttu-id="f8c96-121">Immettere il nome dell'InfoSource oppure un nome parziale con il carattere jolly asterisco (\*).</span><span class="sxs-lookup"><span data-stu-id="f8c96-121">Enter the name of the InfoSource, or a partial name with the asterisk wildcard character (\*).</span></span> <span data-ttu-id="f8c96-122">In alternativa, utilizzare il carattere jolly asterisco da solo per includere tutti gli InfoPackage indipendentemente dall'InfoSource.</span><span class="sxs-lookup"><span data-stu-id="f8c96-122">Or, use the asterisk wildcard character alone to include all InfoPackages regardless of InfoSource.</span></span>  
  
 <span data-ttu-id="f8c96-123">**Sistema di origine**</span><span class="sxs-lookup"><span data-stu-id="f8c96-123">**Source system**</span></span>  
 <span data-ttu-id="f8c96-124">Immettere il nome del sistema di origine o un nome parziale con il carattere jolly asterisco (\*).</span><span class="sxs-lookup"><span data-stu-id="f8c96-124">Enter the name of the source system, or a partial name with the asterisk wildcard character (\*).</span></span> <span data-ttu-id="f8c96-125">In alternativa, utilizzare il carattere jolly asterisco da solo per includere tutti gli InfoPackage indipendentemente dai sistemi di origine.</span><span class="sxs-lookup"><span data-stu-id="f8c96-125">Or, use the asterisk wildcard character alone to include all InfoPackages regardless of source systems.</span></span>  
  
 <span data-ttu-id="f8c96-126">**Cerca**</span><span class="sxs-lookup"><span data-stu-id="f8c96-126">**Look up**</span></span>  
 <span data-ttu-id="f8c96-127">Cercare gli InfoPackage corrispondenti definiti nel sistema SAP Netweaver BW.</span><span class="sxs-lookup"><span data-stu-id="f8c96-127">Look up matching InfoPackages that are defined in the SAP Netweaver BW system.</span></span>  
  
## <a name="lookup-results"></a><span data-ttu-id="f8c96-128">Risultati di ricerca</span><span class="sxs-lookup"><span data-stu-id="f8c96-128">Lookup Results</span></span>  
 <span data-ttu-id="f8c96-129">Dopo avere fatto clic sul pulsante Ricerca, viene visualizzato un elenco di InfoPackage nel sistema SAP Netweaver BW in una tabella con le intestazioni di colonna seguenti.</span><span class="sxs-lookup"><span data-stu-id="f8c96-129">After you click the Look up button, a list of the InfoPackages in the SAP Netweaver BW system appears in a table with the following column headings.</span></span>  
  
 <span data-ttu-id="f8c96-130">**InfoPackage**</span><span class="sxs-lookup"><span data-stu-id="f8c96-130">**InfoPackage**</span></span>  
 <span data-ttu-id="f8c96-131">Visualizza il nome dell'InfoPackage definito nel sistema SAP Netweaver BW.</span><span class="sxs-lookup"><span data-stu-id="f8c96-131">Displays the name of the InfoPackage that is defined in the SAP Netweaver BW system.</span></span>  
  
 <span data-ttu-id="f8c96-132">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="f8c96-132">**Type**</span></span>  
 <span data-ttu-id="f8c96-133">Visualizza il tipo di InfoPackage.</span><span class="sxs-lookup"><span data-stu-id="f8c96-133">Displays the type of the InfoPackage.</span></span> <span data-ttu-id="f8c96-134">Nella tabella seguente sono elencati i valori possibili per il tipo.</span><span class="sxs-lookup"><span data-stu-id="f8c96-134">The following table lists the possible values for the type.</span></span>  
  
|<span data-ttu-id="f8c96-135">valore</span><span class="sxs-lookup"><span data-stu-id="f8c96-135">Value</span></span>|<span data-ttu-id="f8c96-136">Descrizione</span><span class="sxs-lookup"><span data-stu-id="f8c96-136">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="f8c96-137">transazioni</span><span class="sxs-lookup"><span data-stu-id="f8c96-137">Trans.</span></span>|<span data-ttu-id="f8c96-138">Dati di transazione.</span><span class="sxs-lookup"><span data-stu-id="f8c96-138">Transaction data.</span></span>|  
|<span data-ttu-id="f8c96-139">Attr.</span><span class="sxs-lookup"><span data-stu-id="f8c96-139">Attr.</span></span>|<span data-ttu-id="f8c96-140">Dati dell'attributo.</span><span class="sxs-lookup"><span data-stu-id="f8c96-140">Attribute data.</span></span>|  
|<span data-ttu-id="f8c96-141">Testi</span><span class="sxs-lookup"><span data-stu-id="f8c96-141">Texts</span></span>|<span data-ttu-id="f8c96-142">Testi.</span><span class="sxs-lookup"><span data-stu-id="f8c96-142">Texts.</span></span>|  
  
 <span data-ttu-id="f8c96-143">**Descrizione**</span><span class="sxs-lookup"><span data-stu-id="f8c96-143">**Description**</span></span>  
 <span data-ttu-id="f8c96-144">Visualizza la descrizione dell'InfoPackage.</span><span class="sxs-lookup"><span data-stu-id="f8c96-144">Displays the description of the InfoPackage.</span></span>  
  
 <span data-ttu-id="f8c96-145">**InfoSource**</span><span class="sxs-lookup"><span data-stu-id="f8c96-145">**InfoSource**</span></span>  
 <span data-ttu-id="f8c96-146">Visualizza il nome dell'InfoSource, se esistente, associato all'InfoPackage.</span><span class="sxs-lookup"><span data-stu-id="f8c96-146">Displays the name of the InfoSource, if any, that is associated with the InfoPackage.</span></span>  
  
 <span data-ttu-id="f8c96-147">**Source System**</span><span class="sxs-lookup"><span data-stu-id="f8c96-147">**Source System**</span></span>  
 <span data-ttu-id="f8c96-148">Visualizza il nome del sistema di origine.</span><span class="sxs-lookup"><span data-stu-id="f8c96-148">Displays the name of the source system.</span></span>  
  
 <span data-ttu-id="f8c96-149">Quando viene visualizzato l'elenco di InfoPackage, selezionare l'InfoPackage desiderato e le opzioni associate verranno compilate con i valori richiesti dalla destinazione.</span><span class="sxs-lookup"><span data-stu-id="f8c96-149">When the list of InfoPackages appears, select the InfoPackage that you want, and the destination will populate the associated options with the required values.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f8c96-150">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f8c96-150">See Also</span></span>  
 <span data-ttu-id="f8c96-151">[Editor destinazione SAP BW &#40;pagina Gestione connessione&#41;](sap-bw-destination-editor-connection-manager-page.md) </span><span class="sxs-lookup"><span data-stu-id="f8c96-151">[SAP BW Destination Editor &#40;Connection Manager Page&#41;](sap-bw-destination-editor-connection-manager-page.md) </span></span>  
 [<span data-ttu-id="f8c96-152">Guida (F1) di Microsoft Connector 1.1 for SAP BW</span><span class="sxs-lookup"><span data-stu-id="f8c96-152">Microsoft Connector 1.1 for SAP BW F1 Help</span></span>](../microsoft-connector-for-sap-bw-f1-help.md)  
  
  
