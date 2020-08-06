---
title: Log richieste | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
ms.assetid: 165d3833-0493-490c-9f63-8a134a7fafb8
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 024012878ae94c5ba6276648e289e6e6f7c93d7b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87626163"
---
# <a name="request-log"></a><span data-ttu-id="7d184-102">Log richieste</span><span class="sxs-lookup"><span data-stu-id="7d184-102">Request Log</span></span>
  <span data-ttu-id="7d184-103">Usare la finestra di dialogo **Log richieste** per visualizzare gli eventi registrati durante la richiesta fatta al sistema SAP Netweaver BW per i dati di esempio.</span><span class="sxs-lookup"><span data-stu-id="7d184-103">Use the **Request Log** dialog box to view the events that are logged during the request that is made to the SAP Netweaver BW system for sample data.</span></span> <span data-ttu-id="7d184-104">Queste informazioni possono essere utili se è necessario risolvere i problemi relativi alla configurazione dell'origine SAP BW.</span><span class="sxs-lookup"><span data-stu-id="7d184-104">This information can be useful if you have to troubleshoot your configuration of the SAP BW source.</span></span>  
  
 <span data-ttu-id="7d184-105">Per altre informazioni sul componente di origine SAP BW di [!INCLUDE[msCoName](../../includes/msconame-md.md)] Connector 1.1 for SAP BW, vedere [Origine SAP BW](sap-bw-source.md).</span><span class="sxs-lookup"><span data-stu-id="7d184-105">To learn more about the SAP BW source component of the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Connector 1.1 for SAP BW, see [SAP BW Source](sap-bw-source.md).</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="7d184-106">La documentazione per Microsoft Connector 1.1 for SAP BW presuppone la conoscenza dell'ambiente SAP Netweaver BW.</span><span class="sxs-lookup"><span data-stu-id="7d184-106">The documentation for the Microsoft Connector 1.1 for SAP BW assumes familiarity with the SAP Netweaver BW environment.</span></span> <span data-ttu-id="7d184-107">Per ulteriori informazioni su SAP Netweaver BW o per informazioni su come configurare oggetti e processi di SAP Netweaver BW, vedere la documentazione SAP.</span><span class="sxs-lookup"><span data-stu-id="7d184-107">For more information about SAP Netweaver BW, or for information about how to configure SAP Netweaver BW objects and processes, see your SAP documentation.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="7d184-108">L'estrazione di dati da SAP Netweaver BW richiede licenze SAP aggiuntive.</span><span class="sxs-lookup"><span data-stu-id="7d184-108">Extracting data from SAP Netweaver BW requires additional SAP licensing.</span></span> <span data-ttu-id="7d184-109">Contattare SAP per verificare questi requisiti.</span><span class="sxs-lookup"><span data-stu-id="7d184-109">Check with SAP to verify these requirements.</span></span>  
  
 <span data-ttu-id="7d184-110">**Per aprire la finestra di dialogo Log richieste**</span><span class="sxs-lookup"><span data-stu-id="7d184-110">**To open the Request Log dialog box**</span></span>  
  
1.  <span data-ttu-id="7d184-111">In [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)]aprire il pacchetto [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] che contiene l'origine SAP BW.</span><span class="sxs-lookup"><span data-stu-id="7d184-111">In [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], open the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] package that contains the SAP BW source.</span></span>  
  
2.  <span data-ttu-id="7d184-112">Nella scheda **Flusso di dati** fare doppio clic sull'origine SAP BW.</span><span class="sxs-lookup"><span data-stu-id="7d184-112">On the **Data Flow** tab, double-click the SAP BW source.</span></span>  
  
3.  <span data-ttu-id="7d184-113">Nell' **Editor origine SAP BW**fare clic su **Gestione connessione** per aprire la pagina **Gestione connessione** dell'editor.</span><span class="sxs-lookup"><span data-stu-id="7d184-113">In the **SAP BW Source Editor**, click **Connection Manager** to open the **Connection Manager** page of the editor.</span></span>  
  
4.  <span data-ttu-id="7d184-114">Dopo aver configurato l'origine SAP BW, fare clic su **Anteprima** per visualizzare gli eventi in anteprima nella finestra di dialogo **Log richieste** .</span><span class="sxs-lookup"><span data-stu-id="7d184-114">After you configure the SAP BW source, click **Preview** to preview the events in the **Request Log** dialog box.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="7d184-115">Quando si fa clic su **Anteprima** , inoltre, viene aperta la finestra di dialogo **Anteprima** .</span><span class="sxs-lookup"><span data-stu-id="7d184-115">Clicking **Preview** also opens the **Preview** dialog box.</span></span> <span data-ttu-id="7d184-116">Per altre informazioni su questa finestra di dialogo, vedere [Anteprima](preview.md).</span><span class="sxs-lookup"><span data-stu-id="7d184-116">For more information about this dialog box, see [Preview](preview.md).</span></span>  
  
## <a name="options"></a><span data-ttu-id="7d184-117">Opzioni</span><span class="sxs-lookup"><span data-stu-id="7d184-117">Options</span></span>  
 <span data-ttu-id="7d184-118">**Time**</span><span class="sxs-lookup"><span data-stu-id="7d184-118">**Time**</span></span>  
 <span data-ttu-id="7d184-119">Visualizza l'ora di registrazione dell'evento.</span><span class="sxs-lookup"><span data-stu-id="7d184-119">Displays the time that the event that was logged.</span></span>  
  
 <span data-ttu-id="7d184-120">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="7d184-120">**Type**</span></span>  
 <span data-ttu-id="7d184-121">Visualizza il tipo dell'evento registrato.</span><span class="sxs-lookup"><span data-stu-id="7d184-121">Displays the type of the event that was logged.</span></span> <span data-ttu-id="7d184-122">Nella tabella seguente sono elencati i tipi di eventi possibili.</span><span class="sxs-lookup"><span data-stu-id="7d184-122">The following table lists the possible event types.</span></span>  
  
|<span data-ttu-id="7d184-123">valore</span><span class="sxs-lookup"><span data-stu-id="7d184-123">Value</span></span>|<span data-ttu-id="7d184-124">Descrizione</span><span class="sxs-lookup"><span data-stu-id="7d184-124">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="7d184-125">S</span><span class="sxs-lookup"><span data-stu-id="7d184-125">S</span></span>|<span data-ttu-id="7d184-126">Messaggio di operazione completata.</span><span class="sxs-lookup"><span data-stu-id="7d184-126">Success message.</span></span>|  
|<span data-ttu-id="7d184-127">E</span><span class="sxs-lookup"><span data-stu-id="7d184-127">E</span></span>|<span data-ttu-id="7d184-128">Messaggio di errore</span><span class="sxs-lookup"><span data-stu-id="7d184-128">Error message</span></span>|  
|<span data-ttu-id="7d184-129">W</span><span class="sxs-lookup"><span data-stu-id="7d184-129">W</span></span>|<span data-ttu-id="7d184-130">Messaggio di avviso.</span><span class="sxs-lookup"><span data-stu-id="7d184-130">Warning message.</span></span>|  
|<span data-ttu-id="7d184-131">I</span><span class="sxs-lookup"><span data-stu-id="7d184-131">I</span></span>|<span data-ttu-id="7d184-132">Messaggio informativo.</span><span class="sxs-lookup"><span data-stu-id="7d184-132">Informational message.</span></span>|  
|<span data-ttu-id="7d184-133">Una</span><span class="sxs-lookup"><span data-stu-id="7d184-133">A</span></span>|<span data-ttu-id="7d184-134">L'operazione è stata interrotta.</span><span class="sxs-lookup"><span data-stu-id="7d184-134">The operation was aborted.</span></span>|  
  
 <span data-ttu-id="7d184-135">**Messaggio**</span><span class="sxs-lookup"><span data-stu-id="7d184-135">**Message**</span></span>  
 <span data-ttu-id="7d184-136">Visualizza il testo del messaggio associato all'evento registrato.</span><span class="sxs-lookup"><span data-stu-id="7d184-136">Displays the message text that is associated with the logged event.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7d184-137">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="7d184-137">See Also</span></span>  
 <span data-ttu-id="7d184-138">[Editor origine SAP BW &#40;pagina Gestione connessione&#41;](sap-bw-source-editor-connection-manager-page.md) </span><span class="sxs-lookup"><span data-stu-id="7d184-138">[SAP BW Source Editor &#40;Connection Manager Page&#41;](sap-bw-source-editor-connection-manager-page.md) </span></span>  
 [<span data-ttu-id="7d184-139">Guida (F1) di Microsoft Connector 1.1 for SAP BW</span><span class="sxs-lookup"><span data-stu-id="7d184-139">Microsoft Connector 1.1 for SAP BW F1 Help</span></span>](../microsoft-connector-for-sap-bw-f1-help.md)  
  
  
