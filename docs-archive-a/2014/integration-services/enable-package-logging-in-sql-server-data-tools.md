---
title: Abilitare la registrazione di pacchetti in SQL Server Data Tools | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- logs [Integration Services], enabling
ms.assetid: b69a8593-5bb0-4f04-87d2-f8e7bd7eb4fc
author: chugugrace
ms.author: chugu
ms.openlocfilehash: d73dbca034047e853669dd503a62e105d1dd7b45
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87629519"
---
# <a name="enable-package-logging-in-sql-server-data-tools"></a><span data-ttu-id="5917c-102">Abilitare la registrazione di pacchetti in SQL Server Data Tools</span><span class="sxs-lookup"><span data-stu-id="5917c-102">Enable Package Logging in SQL Server Data Tools</span></span>
  <span data-ttu-id="5917c-103">In questo argomento viene descritta la procedura per aggiungere log in un pacchetto, configurare la registrazione a livello di pacchetto e salvare la configurazione di registrazione in un file XML.</span><span class="sxs-lookup"><span data-stu-id="5917c-103">This procedure describes how to add logs to a package, configure package-level logging, and save the logging configuration to an XML file.</span></span> <span data-ttu-id="5917c-104">È possibile aggiungere log solo a livello di pacchetto. Il pacchetto, tuttavia, non deve eseguire necessariamente la registrazione per consentire la registrazione nei contenitori del pacchetto.</span><span class="sxs-lookup"><span data-stu-id="5917c-104">You can add logs only at the package level, but the package does not have to perform logging to enable logging in the containers that the package includes.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="5917c-105">Se si distribuisce il progetto [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] nel server [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] , il livello di registrazione impostato per l'esecuzione del pacchetto esegue l'override della registrazione del pacchetto configurata mediante [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="5917c-105">If you deploy the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] project to the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] server, the logging level that you set for the package execution overrides the package logging that you configure using [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)].</span></span>  
  
 <span data-ttu-id="5917c-106">Per impostazione predefinita, i contenitori del pacchetto utilizzano la stessa configurazione di registrazione del contenitore padre.</span><span class="sxs-lookup"><span data-stu-id="5917c-106">By default, the containers in the package use the same logging configuration as their parent container.</span></span> <span data-ttu-id="5917c-107">Per informazioni sull'impostazione delle opzioni di registrazione per singoli contenitori, vedere [Configurazione della registrazione tramite un file di configurazione salvato](../../2014/integration-services/configure-logging-by-using-a-saved-configuration-file.md).</span><span class="sxs-lookup"><span data-stu-id="5917c-107">For information about setting logging options for individual containers, see [Configure Logging by Using a Saved Configuration File](../../2014/integration-services/configure-logging-by-using-a-saved-configuration-file.md).</span></span>  
  
### <a name="to-enable-logging-in-a-package"></a><span data-ttu-id="5917c-108">Per abilitare la registrazione in un pacchetto</span><span class="sxs-lookup"><span data-stu-id="5917c-108">To enable logging in a package</span></span>  
  
1.  <span data-ttu-id="5917c-109">In [!INCLUDE[ssBIDevStudio](../includes/ssbidevstudio-md.md)]aprire il progetto di [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] che contiene il pacchetto desiderato.</span><span class="sxs-lookup"><span data-stu-id="5917c-109">In [!INCLUDE[ssBIDevStudio](../includes/ssbidevstudio-md.md)], open the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] project that contains the package you want.</span></span>  
  
2.  <span data-ttu-id="5917c-110">Scegliere **Registrazione** dal menu **SSIS**.</span><span class="sxs-lookup"><span data-stu-id="5917c-110">On the **SSIS** menu, click **Logging**.</span></span>  
  
3.  <span data-ttu-id="5917c-111">Selezionare un provider di log nell'elenco **Tipo provider** e quindi fare clic su **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="5917c-111">Select a log provider in the **Provider type** list, and then click **Add**.</span></span>  
  
4.  <span data-ttu-id="5917c-112">Nella colonna **Configurazione** selezionare una gestione connessione oppure fare clic su **\<New connection>** per creare una nuova gestione connessione del tipo appropriato per il provider di log.</span><span class="sxs-lookup"><span data-stu-id="5917c-112">In the **Configuration** column, select a connection manager or click **\<New connection>** to create a new connection manager of the appropriate type for the log provider.</span></span> <span data-ttu-id="5917c-113">A seconda del provider selezionato, utilizzare una delle gestioni connessioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="5917c-113">Depending on the selected provider, use one of the following connection managers:</span></span>  
  
    -   <span data-ttu-id="5917c-114">Per file di testo utilizzare una gestione connessione file.</span><span class="sxs-lookup"><span data-stu-id="5917c-114">For Text files, use a File connection manager.</span></span> <span data-ttu-id="5917c-115">Per altre informazioni, vedere [File Connection Manager](connection-manager/file-connection-manager.md)</span><span class="sxs-lookup"><span data-stu-id="5917c-115">For more information, see [File Connection Manager](connection-manager/file-connection-manager.md)</span></span>  
  
    -   <span data-ttu-id="5917c-116">Per [!INCLUDE[ssSqlProfiler](../includes/sssqlprofiler-md.md)]usare una gestione connessione file.</span><span class="sxs-lookup"><span data-stu-id="5917c-116">For [!INCLUDE[ssSqlProfiler](../includes/sssqlprofiler-md.md)], use a File connection manager.</span></span>  
  
    -   <span data-ttu-id="5917c-117">Per [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)]utilizzare una gestione connessione OLE DB.</span><span class="sxs-lookup"><span data-stu-id="5917c-117">For [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)], use an OLE DB connection manager.</span></span> <span data-ttu-id="5917c-118">Per altre informazioni, vedere [Gestione connessione OLE DB](connection-manager/ole-db-connection-manager.md).</span><span class="sxs-lookup"><span data-stu-id="5917c-118">For more information, see [OLE DB Connection Manager](connection-manager/ole-db-connection-manager.md).</span></span>  
  
    -   <span data-ttu-id="5917c-119">Per il Registro eventi di Windows, non eseguire alcuna operazione.</span><span class="sxs-lookup"><span data-stu-id="5917c-119">For Windows Event Log, do nothing.</span></span> [!INCLUDE[ssIS](../includes/ssis-md.md)] <span data-ttu-id="5917c-120">crea automaticamente il registro.</span><span class="sxs-lookup"><span data-stu-id="5917c-120">automatically creates the log.</span></span>  
  
    -   <span data-ttu-id="5917c-121">Per file XML utilizzare una gestione connessione file.</span><span class="sxs-lookup"><span data-stu-id="5917c-121">For XML files, use a File connection manager.</span></span>  
  
5.  <span data-ttu-id="5917c-122">Ripetere i passaggi 3 e 4 per ogni log da utilizzare nel pacchetto.</span><span class="sxs-lookup"><span data-stu-id="5917c-122">Repeat steps 3 and 4 for each log to use in the package.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="5917c-123">In un pacchetto possono venire utilizzati più log di ognuno dei tipi di log.</span><span class="sxs-lookup"><span data-stu-id="5917c-123">A package can use more than one log of each type.</span></span>  
  
6.  <span data-ttu-id="5917c-124">Facoltativamente, selezionare la casella di controllo a livello di pacchetto, selezionare i log da usare per la registrazione a livello di pacchetto e quindi fare clic sulla scheda **Dettagli** .</span><span class="sxs-lookup"><span data-stu-id="5917c-124">Optionally, select the package-level check box, select the logs to use for package-level logging, and then click the **Details** tab.</span></span>  
  
7.  <span data-ttu-id="5917c-125">Nella scheda **Dettagli** selezionare **Eventi** per registrare tutte le voci di log oppure deselezionare l'opzione **Eventi** se si desidera selezionare singoli eventi.</span><span class="sxs-lookup"><span data-stu-id="5917c-125">On the **Details** tab, select **Events** to log all log entries, or clear **Events** to select individual events.</span></span>  
  
8.  <span data-ttu-id="5917c-126">Facoltativamente, fare clic su **Avanzate** per specificare le informazioni da registrare.</span><span class="sxs-lookup"><span data-stu-id="5917c-126">Optionally, click **Advanced** to specify which information to log.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="5917c-127">Per impostazione predefinita vengono registrate tutte le informazioni.</span><span class="sxs-lookup"><span data-stu-id="5917c-127">By default, all information is logged.</span></span>  
  
9. <span data-ttu-id="5917c-128">Nella scheda **Dettagli** fare clic su **Salva**.</span><span class="sxs-lookup"><span data-stu-id="5917c-128">On the **Details** tab, click **Save.**</span></span> <span data-ttu-id="5917c-129">Verrà visualizzata la finestra di dialogo **Salva con nome** .</span><span class="sxs-lookup"><span data-stu-id="5917c-129">The **Save As** dialog box appears.</span></span> <span data-ttu-id="5917c-130">Individuare la cartella in cui salvare la configurazione di registrazione, digitare un nome di file per la nuova configurazione e quindi fare clic su **Salva**.</span><span class="sxs-lookup"><span data-stu-id="5917c-130">Locate the folder in which to save the logging configuration, type a file name for the new log configuration, and then click **Save**.</span></span>  
  
10. <span data-ttu-id="5917c-131">Fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="5917c-131">Click **OK**.</span></span>  
  
11. <span data-ttu-id="5917c-132">Per salvare il pacchetto aggiornato, scegliere **Salva elementi selezionati** dal menu **File** .</span><span class="sxs-lookup"><span data-stu-id="5917c-132">To save the updated package, click **Save Selected Items** on the **File** menu.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5917c-133">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="5917c-133">See Also</span></span>  
 <span data-ttu-id="5917c-134">[Integration Services &#40;la registrazione&#41; SSIS](performance/integration-services-ssis-logging.md) </span><span class="sxs-lookup"><span data-stu-id="5917c-134">[Integration Services &#40;SSIS&#41; Logging](performance/integration-services-ssis-logging.md) </span></span>  
 [<span data-ttu-id="5917c-135">Registrazione di Integration Services &#40;SSIS&#41;</span><span class="sxs-lookup"><span data-stu-id="5917c-135">Integration Services &#40;SSIS&#41; Logging</span></span>](performance/integration-services-ssis-logging.md)  
  
  
