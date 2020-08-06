---
title: Destinazione SAP BW | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
ms.assetid: a612ed91-b89b-4173-a0b1-0bce381e1e28
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 8a0d7c5b75da89e665dbe60bbd7e29ce74da67db
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87635191"
---
# <a name="sap-bw-destination"></a><span data-ttu-id="673f1-102">Destinazione SAP BW</span><span class="sxs-lookup"><span data-stu-id="673f1-102">SAP BW Destination</span></span>
  <span data-ttu-id="673f1-103">La destinazione SAP BW è il componente di destinazione di [!INCLUDE[msCoName](../../includes/msconame-md.md)] Connector 1.1 for SAP BW.</span><span class="sxs-lookup"><span data-stu-id="673f1-103">The SAP BW destination is the destination component of the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Connector 1.1 for SAP BW.</span></span> <span data-ttu-id="673f1-104">Pertanto, la destinazione SAP BW carica i dati dal flusso di dati in un pacchetto di [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] in un sistema SAP Netweaver BW versione 7.</span><span class="sxs-lookup"><span data-stu-id="673f1-104">Thus, the SAP BW destination loads data from the data flow in an [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] package into an SAP Netweaver BW version 7 system.</span></span>  
  
 <span data-ttu-id="673f1-105">Questa destinazione include un input e un output degli errori.</span><span class="sxs-lookup"><span data-stu-id="673f1-105">This destination has one input and one error output.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="673f1-106">La documentazione per Microsoft Connector 1.1 for SAP BW presuppone la conoscenza dell'ambiente SAP Netweaver BW.</span><span class="sxs-lookup"><span data-stu-id="673f1-106">The documentation for the Microsoft Connector 1.1 for SAP BW assumes familiarity with the SAP Netweaver BW environment.</span></span> <span data-ttu-id="673f1-107">Per ulteriori informazioni su SAP Netweaver BW o per informazioni su come configurare oggetti e processi di SAP Netweaver BW, vedere la documentazione SAP.</span><span class="sxs-lookup"><span data-stu-id="673f1-107">For more information about SAP Netweaver BW, or for information about how to configure SAP Netweaver BW objects and processes, see your SAP documentation.</span></span>  
  
 <span data-ttu-id="673f1-108">Per utilizzare la destinazione SAP BW, effettuare le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="673f1-108">To use the SAP BW destination, you have to do the following tasks:</span></span>  
  
-   [<span data-ttu-id="673f1-109">Preparare gli oggetti SAP Netweaver BW</span><span class="sxs-lookup"><span data-stu-id="673f1-109">Prepare the SAP Netweaver BW objects</span></span>](#bkmk_Prepare_Objects)  
  
-   [<span data-ttu-id="673f1-110">Connettersi al sistema SAP Netweaver BW</span><span class="sxs-lookup"><span data-stu-id="673f1-110">Connect to the SAP Netweaver BW system</span></span>](#bkmk_Connect_Database)  
  
-   [<span data-ttu-id="673f1-111">Configurare la destinazione SAP BW</span><span class="sxs-lookup"><span data-stu-id="673f1-111">Configure the SAP BW destination</span></span>](#bkmk_Configure_Destination)  
  
##  <a name="preparing-the-sap-netweaver-bw-objects-that-the-destination-requires"></a><a name="bkmk_Prepare_Objects"></a> <span data-ttu-id="673f1-112">Preparazione degli oggetti SAP Netweaver BW richiesti dalla destinazione</span><span class="sxs-lookup"><span data-stu-id="673f1-112">Preparing the SAP Netweaver BW Objects That the Destination Requires</span></span>  
 <span data-ttu-id="673f1-113">La destinazione SAP BW richiede la presenza di determinati oggetti nel sistema SAP Netweaver BW per funzionare.</span><span class="sxs-lookup"><span data-stu-id="673f1-113">The SAP BW destination requires that certain objects are in the SAP Netweaver BW system before the destination can function.</span></span> <span data-ttu-id="673f1-114">Se questi oggetti non esistono ancora, è necessario eseguire questi passaggi per crearli e configurarli nel sistema SAP Netweaver BW.</span><span class="sxs-lookup"><span data-stu-id="673f1-114">If these objects do not already exist, you have to follow these steps to create and configure these objects in the SAP Netweaver BW system.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="673f1-115">Per ulteriori dettagli sugli oggetti e sui passaggi di configurazione, vedere la documentazione di SAP Netweaver BW.</span><span class="sxs-lookup"><span data-stu-id="673f1-115">For additional details about these objects and these configuration steps, see the SAP Netweaver BW documentation.</span></span>  
  
1.  <span data-ttu-id="673f1-116">Creare un nuovo sistema di origine:</span><span class="sxs-lookup"><span data-stu-id="673f1-116">Create a new Source System:</span></span>  
  
    1.  <span data-ttu-id="673f1-117">Selezionare il tipo **"Third Party/Staging BAPIs"** (BAPI gestione temporanea/terze parti).</span><span class="sxs-lookup"><span data-stu-id="673f1-117">Select the type, **"Third Party/Staging BAPIs"**.</span></span>  
  
    2.  <span data-ttu-id="673f1-118">In **Communication Type with Target System**(Tipo di comunicazione con sistema di destinazione) selezionare **Non-Unicode (Inactive MDMP Settings)** (Non Unicode (Impostazioni MDMP inattive)).</span><span class="sxs-lookup"><span data-stu-id="673f1-118">For **Communication Type with Target System**, select **Non-Unicode (Inactive MDMP Settings)**.</span></span>  
  
    3.  <span data-ttu-id="673f1-119">Assegnare un ID programma appropriato.</span><span class="sxs-lookup"><span data-stu-id="673f1-119">Assign an appropriate Program ID.</span></span>  
  
2.  <span data-ttu-id="673f1-120">Assegnare il sistema di origine a un'InfoSource.</span><span class="sxs-lookup"><span data-stu-id="673f1-120">Assign the Source System to an InfoSource.</span></span>  
  
3.  <span data-ttu-id="673f1-121">Creare un InfoPackage.</span><span class="sxs-lookup"><span data-stu-id="673f1-121">Create an InfoPackage.</span></span>  
  
     <span data-ttu-id="673f1-122">L'InfoPackage è l'oggetto più importante richiesto dalla destinazione SAP BW.</span><span class="sxs-lookup"><span data-stu-id="673f1-122">The InfoPackage is the most important object that is required by the SAP BW destination.</span></span>  
  
 <span data-ttu-id="673f1-123">È inoltre possibile creare altri InfoObject, Infocube, InfoSource e InfoPackage necessari per supportare il caricamento di dati nel sistema SAP Netweaver BW.</span><span class="sxs-lookup"><span data-stu-id="673f1-123">You can also create additional InfoObjects, InfoCubes, InfoSources, and InfoPackages that are required to support loading data into the SAP Netweaver BW system.</span></span>  
  
##  <a name="connecting-to-the-sap-netweaver-bw-system"></a><a name="bkmk_Connect_Database"></a> <span data-ttu-id="673f1-124">Connessione al sistema SAP Netweaver BW</span><span class="sxs-lookup"><span data-stu-id="673f1-124">Connecting to the SAP Netweaver BW System</span></span>  
 <span data-ttu-id="673f1-125">Per connettersi al sistema SAP Netweaver BW versione 7, la destinazione SAP BW utilizza la gestione connessione SAP BW che fa parte di [!INCLUDE[msCoName](../../includes/msconame-md.md)] Connector 1.1 for SAP BW.</span><span class="sxs-lookup"><span data-stu-id="673f1-125">To connect to the SAP Netweaver BW version 7 system, the SAP BW destination uses the SAP BW connection manager that is part of the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Connector 1.1 for SAP BW package.</span></span> <span data-ttu-id="673f1-126">La gestione connessione SAP BW è l'unica gestione connessione di [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] che può essere utilizzata dalla destinazione SAP BW.</span><span class="sxs-lookup"><span data-stu-id="673f1-126">The SAP BW connection manager is the only [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] connection manager that the SAP BW destination can use.</span></span>  
  
 <span data-ttu-id="673f1-127">Per ulteriori informazioni sulla gestione connessione SAP BW, vedere [SAP BW Connection Manager](../connection-manager/sap-bw-connection-manager.md).</span><span class="sxs-lookup"><span data-stu-id="673f1-127">For more information about the SAP BW connection manager, see [SAP BW Connection Manager](../connection-manager/sap-bw-connection-manager.md).</span></span>  
  
##  <a name="configuring-the-sap-bw-destination"></a><a name="bkmk_Configure_Destination"></a> <span data-ttu-id="673f1-128">Configurazione della destinazione SAP BW</span><span class="sxs-lookup"><span data-stu-id="673f1-128">Configuring the SAP BW Destination</span></span>  
 <span data-ttu-id="673f1-129">È possibile configurare la destinazione SAP BW nei modi seguenti:</span><span class="sxs-lookup"><span data-stu-id="673f1-129">You can configure the SAP BW destination in the following ways:</span></span>  
  
-   <span data-ttu-id="673f1-130">Cercare e selezionare l'InfoPackage da utilizzare per caricare i dati.</span><span class="sxs-lookup"><span data-stu-id="673f1-130">Look up and select the InfoPackage to use to load data.</span></span>  
  
-   <span data-ttu-id="673f1-131">Eseguire il mapping di ogni colonna nel flusso di dati all'InfoObject appropriato nell'InfoPackage.</span><span class="sxs-lookup"><span data-stu-id="673f1-131">Map each column in the data flow to the appropriate InfoObject in the InfoPackage.</span></span>  
  
-   <span data-ttu-id="673f1-132">Specificare il numero di righe di dati che verranno trasferite contemporaneamente mediante la configurazione della proprietà `PackageSize`.</span><span class="sxs-lookup"><span data-stu-id="673f1-132">Specify how many rows of data will be transferred at a time by configuring the `PackageSize` property.</span></span>  
  
-   <span data-ttu-id="673f1-133">Scegliere di attendere il completamento del caricamento dei dati da parte del sistema SAP Netweaver BW.</span><span class="sxs-lookup"><span data-stu-id="673f1-133">Choose to wait until the loading of data is completed by the SAP Netweaver BW system.</span></span>  
  
-   <span data-ttu-id="673f1-134">Scegliere di non attivare l'InfoPackage, ma di attendere la notifica dell'avvio del caricamento dei dati da parte del sistema SAP Netweaver BW.</span><span class="sxs-lookup"><span data-stu-id="673f1-134">Choose not to trigger the InfoPackage, but to wait for notification that the SAP Netweaver BW system has started the loading of data.</span></span>  
  
-   <span data-ttu-id="673f1-135">Facoltativamente, attivare un'altra catena di processi al completamento del caricamento dei dati.</span><span class="sxs-lookup"><span data-stu-id="673f1-135">Optionally, trigger another process chain after the loading of data is completed.</span></span>  
  
-   <span data-ttu-id="673f1-136">Facoltativamente, creare gli oggetti SAP Netweaver BW richiesti dalla destinazione.</span><span class="sxs-lookup"><span data-stu-id="673f1-136">Optionally, create the SAP Netweaver BW objects that are required by the destination.</span></span> <span data-ttu-id="673f1-137">Ciò include la creazione di InfoObject, InfoCube, InfoSource e InfoPackage.</span><span class="sxs-lookup"><span data-stu-id="673f1-137">This includes creating InfoObjects, InfoCubes, InfoSources, and InfoPackages.</span></span>  
  
-   <span data-ttu-id="673f1-138">Verificare il caricamento dei dati con le opzioni selezionate.</span><span class="sxs-lookup"><span data-stu-id="673f1-138">Test the loading of data with the options that you have selected.</span></span>  
  
 <span data-ttu-id="673f1-139">È inoltre possibile abilitare la registrazione delle chiamate di funzioni RFC da parte della destinazione.</span><span class="sxs-lookup"><span data-stu-id="673f1-139">You can also enable logging of RFC function calls by the destination.</span></span> <span data-ttu-id="673f1-140">Tale registrazione è separata dalla registrazione facoltativa che è possibile abilitare nei pacchetti di [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] . Abilitare la registrazione delle chiamate di funzioni RFC quando si configura la gestione connessione SAP BW che verrà utilizzata dalla destinazione.</span><span class="sxs-lookup"><span data-stu-id="673f1-140">(This logging is separate from the optional logging that you can enable on [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] packages.) You enable logging of RFC function calls when you configure the SAP BW connection manager that the destination will use.</span></span> <span data-ttu-id="673f1-141">Per ulteriori informazioni sulla configurazione della gestione connessione SAP BW, vedere [SAP BW Connection Manager](../connection-manager/sap-bw-connection-manager.md).</span><span class="sxs-lookup"><span data-stu-id="673f1-141">For more information about how to configure the SAP BW connection manager, see [SAP BW Connection Manager](../connection-manager/sap-bw-connection-manager.md).</span></span>  
  
 <span data-ttu-id="673f1-142">Se non si conoscono tutti i valori richiesti per configurare la destinazione, può essere necessario consultare l'amministratore SAP.</span><span class="sxs-lookup"><span data-stu-id="673f1-142">If you do not know all the values that are required to configure the destination, you might have to ask your SAP administrator.</span></span>  
  
 <span data-ttu-id="673f1-143">Per una procedura dettagliata che illustra come configurare e utilizzare la gestione connessione, l'origine e la destinazione SAP BW, vedere il white paper [Utilizzo dei servizi di integrazione SQL Server 2008 con SAP BI 7.0](https://go.microsoft.com/fwlink/?LinkID=137090).</span><span class="sxs-lookup"><span data-stu-id="673f1-143">For a walkthrough that demonstrates how to configure and use the SAP BW connection manager, source, and destination, see the white paper, [Using SQL Server 2008 Integration Services with SAP BI 7.0](https://go.microsoft.com/fwlink/?LinkID=137090).</span></span> <span data-ttu-id="673f1-144">Nel white paper viene anche indicato come configurare gli oggetti necessari in SAP BW.</span><span class="sxs-lookup"><span data-stu-id="673f1-144">This white paper also shows how to configure the required objects in SAP BW.</span></span>  
  
### <a name="using-the-ssis-designer-to-configure-the-destination"></a><span data-ttu-id="673f1-145">Utilizzo di Progettazione SSIS per configurare la destinazione</span><span class="sxs-lookup"><span data-stu-id="673f1-145">Using the SSIS Designer to Configure the Destination</span></span>  
 <span data-ttu-id="673f1-146">Per ulteriori informazioni sulle proprietà della destinazione SAP BW che è possibile impostare in Progettazione [!INCLUDE[ssIS](../../includes/ssis-md.md)] , fare clic su uno degli argomenti seguenti:</span><span class="sxs-lookup"><span data-stu-id="673f1-146">For more information about the properties of the SAP BW destination that you can set in [!INCLUDE[ssIS](../../includes/ssis-md.md)] Designer, click one of the following topics:</span></span>  
  
-   [<span data-ttu-id="673f1-147">Editor destinazione SAP BW &#40;pagina Gestione connessione&#41;</span><span class="sxs-lookup"><span data-stu-id="673f1-147">SAP BW Destination Editor &#40;Connection Manager Page&#41;</span></span>](sap-bw-destination-editor-connection-manager-page.md)  
  
-   [<span data-ttu-id="673f1-148">Editor destinazione SAP BW &#40;pagina Mapping&#41;</span><span class="sxs-lookup"><span data-stu-id="673f1-148">SAP BW Destination Editor &#40;Mappings Page&#41;</span></span>](sap-bw-destination-editor-mappings-page.md)  
  
-   [<span data-ttu-id="673f1-149">Editor destinazione SAP BW &#40;pagina Output degli errori&#41;</span><span class="sxs-lookup"><span data-stu-id="673f1-149">SAP BW Destination Editor &#40;Error Output Page&#41;</span></span>](sap-bw-destination-editor-error-output-page.md)  
  
-   [<span data-ttu-id="673f1-150">Editor destinazione SAP BW &#40;pagina Avanzate&#41;</span><span class="sxs-lookup"><span data-stu-id="673f1-150">SAP BW Destination Editor &#40;Advanced Page&#41;</span></span>](sap-bw-destination-editor-advanced-page.md)  
  
 <span data-ttu-id="673f1-151">Quando si configura la destinazione SAP BW, è inoltre possibile utilizzare varie finestre di dialogo per cercare o creare gli oggetti SAP Netweaver BW.</span><span class="sxs-lookup"><span data-stu-id="673f1-151">While you are configuring the SAP BW destination, you can also use various dialog boxes to look up or to create SAP Netweaver BW objects.</span></span> <span data-ttu-id="673f1-152">Per ulteriori informazioni su queste finestre di dialogo, fare clic su uno degli argomenti seguenti:</span><span class="sxs-lookup"><span data-stu-id="673f1-152">For more information about these dialog boxes, click one of the following topics:</span></span>  
  
-   [<span data-ttu-id="673f1-153">Cerca InfoPackage</span><span class="sxs-lookup"><span data-stu-id="673f1-153">Look Up InfoPackage</span></span>](look-up-infopackage.md)  
  
-   [<span data-ttu-id="673f1-154">Crea nuovo InfoObject</span><span class="sxs-lookup"><span data-stu-id="673f1-154">Create New InfoObject</span></span>](create-new-infoobject.md)  
  
-   [<span data-ttu-id="673f1-155">Crea InfoCube per dati transazione</span><span class="sxs-lookup"><span data-stu-id="673f1-155">Create InfoCube for Transaction Data</span></span>](create-infocube-for-transaction-data.md)  
  
-   [<span data-ttu-id="673f1-156">Cerca InfoObject</span><span class="sxs-lookup"><span data-stu-id="673f1-156">Look Up InfoObject</span></span>](look-up-infoobject.md)  
  
-   [<span data-ttu-id="673f1-157">Crea InfoSource</span><span class="sxs-lookup"><span data-stu-id="673f1-157">Create InfoSource</span></span>](create-infosource.md)  
  
-   [<span data-ttu-id="673f1-158">Crea InfoSource per dati transazione</span><span class="sxs-lookup"><span data-stu-id="673f1-158">Create InfoSource for Transaction Data</span></span>](create-infosource-for-transaction-data.md)  
  
-   [<span data-ttu-id="673f1-159">Crea InfoSource per dati master</span><span class="sxs-lookup"><span data-stu-id="673f1-159">Create InfoSource for Master Data</span></span>](create-infosource-for-master-data.md)  
  
-   [<span data-ttu-id="673f1-160">Crea InfoPackage</span><span class="sxs-lookup"><span data-stu-id="673f1-160">Create InfoPackage</span></span>](create-infopackage.md)  
  
## <a name="see-also"></a><span data-ttu-id="673f1-161">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="673f1-161">See Also</span></span>  
 [<span data-ttu-id="673f1-162">Componenti di Microsoft Connector 1.1 for SAP BW</span><span class="sxs-lookup"><span data-stu-id="673f1-162">Microsoft Connector 1.1 for SAP BW Components</span></span>](../microsoft-connector-for-sap-bw-components.md)  
  
  
