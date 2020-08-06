---
title: Cerca ProcessChain | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
ms.assetid: f6303ea4-fbbf-4cba-bc60-828df62be8c2
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 2e0d3743071d018a8a82f60eeaf04fd86dec3e63
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87715603"
---
# <a name="look-up-process-chain"></a><span data-ttu-id="87204-102">Cerca ProcessChain</span><span class="sxs-lookup"><span data-stu-id="87204-102">Look Up Process Chain</span></span>
  <span data-ttu-id="87204-103">Utilizzare la finestra di dialogo **Cerca ProcessChain** per cercare una catena di processi definita nel sistema SAP Netweaver BW.</span><span class="sxs-lookup"><span data-stu-id="87204-103">Use the **Look Up Process Chain** dialog box to look up a process chain that is defined in the SAP Netweaver BW system.</span></span> <span data-ttu-id="87204-104">Quando viene visualizzato l'elenco delle catene di processi disponibili, selezionare la catena desiderata e le opzioni associate verranno compilate con i valori richiesti dall'origine.</span><span class="sxs-lookup"><span data-stu-id="87204-104">When the list of available process chains appears, select the chain that you want, and the source will populate the associated options with the required values.</span></span>  
  
 <span data-ttu-id="87204-105">L'origine SAP BW di [!INCLUDE[msCoName](../../includes/msconame-md.md)] Connector 1.1 for SAP BW utilizza la finestra di dialogo **Cerca ProcessChain** .</span><span class="sxs-lookup"><span data-stu-id="87204-105">The SAP BW source of the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Connector 1.1 for SAP BW uses the **Look Up Process Chain** dialog box.</span></span> <span data-ttu-id="87204-106">Per ulteriori informazioni sull'origine SAP BW, vedere [SAP BW Source](sap-bw-source.md).</span><span class="sxs-lookup"><span data-stu-id="87204-106">To learn more about the SAP BW source, see [SAP BW Source](sap-bw-source.md).</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="87204-107">La documentazione per Microsoft Connector 1.1 for SAP BW presuppone la conoscenza dell'ambiente SAP Netweaver BW.</span><span class="sxs-lookup"><span data-stu-id="87204-107">The documentation for the Microsoft Connector 1.1 for SAP BW assumes familiarity with the SAP Netweaver BW environment.</span></span> <span data-ttu-id="87204-108">Per ulteriori informazioni su SAP Netweaver BW o per informazioni su come configurare oggetti e processi di SAP Netweaver BW, vedere la documentazione SAP.</span><span class="sxs-lookup"><span data-stu-id="87204-108">For more information about SAP Netweaver BW, or for information about how to configure SAP Netweaver BW objects and processes, see your SAP documentation.</span></span>  
  
 <span data-ttu-id="87204-109">**Per aprire la finestra di dialogo Cerca ProcessChain**</span><span class="sxs-lookup"><span data-stu-id="87204-109">**To open the Look Up Process Chain dialog box**</span></span>  
  
1.  <span data-ttu-id="87204-110">In [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)]aprire il pacchetto [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] che contiene l'origine SAP BW.</span><span class="sxs-lookup"><span data-stu-id="87204-110">In [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], open the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] package that contains the SAP BW source.</span></span>  
  
2.  <span data-ttu-id="87204-111">Nella scheda **Flusso di dati** fare doppio clic sull'origine SAP BW.</span><span class="sxs-lookup"><span data-stu-id="87204-111">On the **Data Flow** tab, double-click the SAP BW source.</span></span>  
  
3.  <span data-ttu-id="87204-112">Nell' **Editor origine SAP BW**fare clic su **Gestione connessione** per aprire la pagina **Gestione connessione** dell'editor.</span><span class="sxs-lookup"><span data-stu-id="87204-112">In the **SAP BW Source Editor**, click **Connection Manager** to open the **Connection Manager** page of the editor.</span></span>  
  
4.  <span data-ttu-id="87204-113">Nella casella di gruppo **Catena di processi** fare clic su **Ricerca** per visualizzare la finestra di dialogo **Cerca ProcessChain** .</span><span class="sxs-lookup"><span data-stu-id="87204-113">In the **Process Chain** group box, click **Look up** to display the **Look Up Process Chain** dialog box.</span></span>  
  
     <span data-ttu-id="87204-114">La casella di gruppo **Catena di processi** viene visualizzata solo se il valore di **Modalità di esecuzione** è **P - Attivazione catena di processi**.</span><span class="sxs-lookup"><span data-stu-id="87204-114">The **Process Chain** group box appears only if the value for **Execution mode** is **P - Trigger process chain**.</span></span>  
  
## <a name="lookup-options"></a><span data-ttu-id="87204-115">Opzioni di ricerca</span><span class="sxs-lookup"><span data-stu-id="87204-115">Lookup Options</span></span>  
 <span data-ttu-id="87204-116">Nei campi di ricerca è possibile filtrare i risultati tramite il carattere jolly asterisco (\*) oppure utilizzando una stringa parziale in combinazione con il carattere jolly asterisco.</span><span class="sxs-lookup"><span data-stu-id="87204-116">In the lookup fields, you can filter results by using the asterisk wildcard character (\*), or by using a partial string in combination with the asterisk wildcard character.</span></span> <span data-ttu-id="87204-117">Tuttavia, se si lascia un campo di ricerca vuoto, l'operazione di ricerca restituirà solo stringhe vuote in tale campo.</span><span class="sxs-lookup"><span data-stu-id="87204-117">However, if you leave a lookup field empty, the lookup operation will only match empty strings in that field.</span></span>  
  
 <span data-ttu-id="87204-118">**Catena di processi**</span><span class="sxs-lookup"><span data-stu-id="87204-118">**Process chain**</span></span>  
 <span data-ttu-id="87204-119">Immettere il nome della catena di processi da cercare oppure un nome parziale con il carattere jolly asterisco (\*).</span><span class="sxs-lookup"><span data-stu-id="87204-119">Enter the name of the process chain that you want to look up, or enter a partial name with the asterisk wildcard character (\*).</span></span> <span data-ttu-id="87204-120">In alternativa, utilizzare il carattere jolly asterisco da solo per includere tutte le catene di processi.</span><span class="sxs-lookup"><span data-stu-id="87204-120">Or, use the asterisk wildcard character alone to include all process chains.</span></span>  
  
 <span data-ttu-id="87204-121">**Cerca**</span><span class="sxs-lookup"><span data-stu-id="87204-121">**Look up**</span></span>  
 <span data-ttu-id="87204-122">Cercare le catene di processi corrispondenti definiti nel sistema SAP Netweaver BW.</span><span class="sxs-lookup"><span data-stu-id="87204-122">Look up matching process chains that are defined in the SAP Netweaver BW system.</span></span>  
  
## <a name="lookup-results"></a><span data-ttu-id="87204-123">Risultati di ricerca</span><span class="sxs-lookup"><span data-stu-id="87204-123">Lookup Results</span></span>  
 <span data-ttu-id="87204-124">Dopo avere fatto clic sul pulsante Ricerca, viene visualizzato un elenco delle catene di processi nel sistema SAP Netweaver BW in una tabella con le intestazioni di colonna seguenti:</span><span class="sxs-lookup"><span data-stu-id="87204-124">After you click the Look up button, a list of the process chains in the SAP Netweaver BW system appears in a table with the following column headings:</span></span>  
  
 <span data-ttu-id="87204-125">**Catena di processi**</span><span class="sxs-lookup"><span data-stu-id="87204-125">**Process Chain**</span></span>  
 <span data-ttu-id="87204-126">Visualizza il nome della catena di processi definita nel sistema SAP Netweaver BW.</span><span class="sxs-lookup"><span data-stu-id="87204-126">Displays the name of the process chain that is defined in the SAP Netweaver BW system.</span></span>  
  
 <span data-ttu-id="87204-127">**Descrizione**</span><span class="sxs-lookup"><span data-stu-id="87204-127">**Description**</span></span>  
 <span data-ttu-id="87204-128">Visualizza la descrizione della catena di processi.</span><span class="sxs-lookup"><span data-stu-id="87204-128">Displays the description of the process chain.</span></span>  
  
 <span data-ttu-id="87204-129">Quando viene visualizzato l'elenco delle catene di processi disponibili, selezionare la catena desiderata e le opzioni associate verranno compilate con i valori richiesti dall'origine.</span><span class="sxs-lookup"><span data-stu-id="87204-129">When the list of available process chains appears, select the chain that you want, and the source will populate the associated options with the required values.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="87204-130">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="87204-130">See Also</span></span>  
 <span data-ttu-id="87204-131">[Editor origine SAP BW &#40;pagina Gestione connessione&#41;](sap-bw-source-editor-connection-manager-page.md) </span><span class="sxs-lookup"><span data-stu-id="87204-131">[SAP BW Source Editor &#40;Connection Manager Page&#41;](sap-bw-source-editor-connection-manager-page.md) </span></span>  
 [<span data-ttu-id="87204-132">Guida (F1) di Microsoft Connector 1.1 for SAP BW</span><span class="sxs-lookup"><span data-stu-id="87204-132">Microsoft Connector 1.1 for SAP BW F1 Help</span></span>](../microsoft-connector-for-sap-bw-f1-help.md)  
  
  
