---
title: Editor origine SAP BW (pagina Avanzate) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
ms.assetid: 44f3c991-9e8f-4126-a9a2-2d9da779fb11
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 7c78d40555a30031bf39abda18048fda9c648d01
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87724027"
---
# <a name="sap-bw-source-editor-advanced-page"></a><span data-ttu-id="82c96-102">Editor origine SAP BW (pagina Avanzate)</span><span class="sxs-lookup"><span data-stu-id="82c96-102">SAP BW Source Editor (Advanced Page)</span></span>
  <span data-ttu-id="82c96-103">Usare la pagina **Avanzate** dell' **Editor origine SAP BW** per specificare la regola per la conversione di stringhe e il periodo di timeout, nonché per reimpostare lo stato di un ID richiesta specifico.</span><span class="sxs-lookup"><span data-stu-id="82c96-103">Use the **Advanced** page of the **SAP BW Source Editor** to specify the string conversion rule and the time-out period, and also to reset the status of a particular Request ID.</span></span>  
  
 <span data-ttu-id="82c96-104">Per altre informazioni sul componente di origine SAP BW di [!INCLUDE[msCoName](../../includes/msconame-md.md)] Connector 1.1 for SAP BW, vedere [Origine SAP BW](sap-bw-source.md).</span><span class="sxs-lookup"><span data-stu-id="82c96-104">To learn more about the SAP BW source component of the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Connector 1.1 for SAP BW, see [SAP BW Source](sap-bw-source.md).</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="82c96-105">La documentazione per Microsoft Connector 1.1 for SAP BW presuppone la conoscenza dell'ambiente SAP Netweaver BW.</span><span class="sxs-lookup"><span data-stu-id="82c96-105">The documentation for the Microsoft Connector 1.1 for SAP BW assumes familiarity with the SAP Netweaver BW environment.</span></span> <span data-ttu-id="82c96-106">Per ulteriori informazioni su SAP Netweaver BW o per informazioni su come configurare oggetti e processi di SAP Netweaver BW, vedere la documentazione SAP.</span><span class="sxs-lookup"><span data-stu-id="82c96-106">For more information about SAP Netweaver BW, or for information about how to configure SAP Netweaver BW objects and processes, see your SAP documentation.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="82c96-107">L'estrazione di dati da SAP Netweaver BW richiede licenze SAP aggiuntive.</span><span class="sxs-lookup"><span data-stu-id="82c96-107">Extracting data from SAP Netweaver BW requires additional SAP licensing.</span></span> <span data-ttu-id="82c96-108">Contattare SAP per verificare questi requisiti.</span><span class="sxs-lookup"><span data-stu-id="82c96-108">Check with SAP to verify these requirements.</span></span>  
  
 <span data-ttu-id="82c96-109">**Per aprire la pagina Gestione connessione**</span><span class="sxs-lookup"><span data-stu-id="82c96-109">**To open the Connection Manager page**</span></span>  
  
1.  <span data-ttu-id="82c96-110">In [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)]aprire il pacchetto [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] che contiene l'origine SAP BW.</span><span class="sxs-lookup"><span data-stu-id="82c96-110">In [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], open the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] package that contains the SAP BW source.</span></span>  
  
2.  <span data-ttu-id="82c96-111">Nella scheda **Flusso di dati** fare doppio clic sull'origine SAP BW.</span><span class="sxs-lookup"><span data-stu-id="82c96-111">On the **Data Flow** tab, double-click the SAP BW source.</span></span>  
  
3.  <span data-ttu-id="82c96-112">Nell' **Editor origine SAP BW**fare clic su **Avanzate** per aprire la pagina **Avanzate** dell'editor.</span><span class="sxs-lookup"><span data-stu-id="82c96-112">In the **SAP BW Source Editor**, click **Advanced** to open the **Advanced** page of the editor.</span></span>  
  
## <a name="options"></a><span data-ttu-id="82c96-113">Opzioni</span><span class="sxs-lookup"><span data-stu-id="82c96-113">Options</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="82c96-114">Se non si conoscono tutti i valori richiesti per configurare l'origine, può essere necessario consultare l'amministratore SAP.</span><span class="sxs-lookup"><span data-stu-id="82c96-114">If you do not know all the values that are required to configure the source, you might have to ask your SAP administrator.</span></span>  
  
 <span data-ttu-id="82c96-115">**Conversione stringhe**</span><span class="sxs-lookup"><span data-stu-id="82c96-115">**String Conversion**</span></span>  
 <span data-ttu-id="82c96-116">Specificare la regola da applicare per la conversione di stringhe.</span><span class="sxs-lookup"><span data-stu-id="82c96-116">Specify the rule to apply for string conversion.</span></span>  
  
|<span data-ttu-id="82c96-117">Opzione</span><span class="sxs-lookup"><span data-stu-id="82c96-117">Option</span></span>|<span data-ttu-id="82c96-118">Descrizione</span><span class="sxs-lookup"><span data-stu-id="82c96-118">Description</span></span>|  
|------------|-----------------|  
|<span data-ttu-id="82c96-119">**Conversione automatica stringhe**</span><span class="sxs-lookup"><span data-stu-id="82c96-119">**Automatic string conversion**</span></span>|<span data-ttu-id="82c96-120">Convertire tutte le stringhe in `nvarchar` quando il sistema SAP Netweaver BW è un sistema Unicode.</span><span class="sxs-lookup"><span data-stu-id="82c96-120">Convert all strings to `nvarchar` when the SAP Netweaver BW system is a Unicode system.</span></span> <span data-ttu-id="82c96-121">In caso contrario, convertire tutte le stringhe in `varchar`.</span><span class="sxs-lookup"><span data-stu-id="82c96-121">Otherwise, convert all strings to `varchar`.</span></span>|  
|<span data-ttu-id="82c96-122">**Converti stringhe in varchar**</span><span class="sxs-lookup"><span data-stu-id="82c96-122">**Convert strings to varchar**</span></span>|<span data-ttu-id="82c96-123">Convertire tutte le stringhe in `varchar`.</span><span class="sxs-lookup"><span data-stu-id="82c96-123">Convert all strings to `varchar`.</span></span>|  
|<span data-ttu-id="82c96-124">**Converti stringhe in nvarchar**</span><span class="sxs-lookup"><span data-stu-id="82c96-124">**Convert strings to nvarchar**</span></span>|<span data-ttu-id="82c96-125">Convertire tutte le stringhe in `nvarchar`.</span><span class="sxs-lookup"><span data-stu-id="82c96-125">Convert all strings to `nvarchar`.</span></span>|  
  
 <span data-ttu-id="82c96-126">**Timeout (secondi)**</span><span class="sxs-lookup"><span data-stu-id="82c96-126">**Timeout (seconds)**</span></span>  
 <span data-ttu-id="82c96-127">Specificare il numero massimo di secondi di attesa da parte dell'origine.</span><span class="sxs-lookup"><span data-stu-id="82c96-127">Specify the maximum number of seconds that the source should wait.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="82c96-128">Questa opzione è valida solo se è stato selezionato **W - Attesa notifica** come valore di **Modalità di esecuzione** nella pagina **Gestione connessione** dell'editor.</span><span class="sxs-lookup"><span data-stu-id="82c96-128">This option is only valid if you have selected **W - Wait for Notify** as the value of **Execution Mode** on the **Connection Manager** page of the editor.</span></span> <span data-ttu-id="82c96-129">Per altre informazioni, vedere [Editor origine SAP BW &#40;pagina Gestione connessione&#41;](sap-bw-source-editor-connection-manager-page.md).</span><span class="sxs-lookup"><span data-stu-id="82c96-129">For more information, see [SAP BW Source Editor &#40;Connection Manager Page&#41;](sap-bw-source-editor-connection-manager-page.md).</span></span>  
  
 <span data-ttu-id="82c96-130">**ID richiesta**</span><span class="sxs-lookup"><span data-stu-id="82c96-130">**Request ID**</span></span>  
 <span data-ttu-id="82c96-131">Specificare l'ID richiesta di cui reimpostare lo stato su "G - Green" quando si fa clic su **Reimposta**.</span><span class="sxs-lookup"><span data-stu-id="82c96-131">Specify the Request ID whose status you want to reset to "G - Green" when you click **Reset**.</span></span>  
  
 <span data-ttu-id="82c96-132">**Reimpostazione**</span><span class="sxs-lookup"><span data-stu-id="82c96-132">**Reset**</span></span>  
 <span data-ttu-id="82c96-133">Consente di reimpostare lo stato dell'ID richiesta specificato su "G - Green", dopo la richiesta di conferma.</span><span class="sxs-lookup"><span data-stu-id="82c96-133">Lets you reset the status of the specified Request ID to "G - Green", after prompting you for confirmation.</span></span> <span data-ttu-id="82c96-134">Ciò risulta utile quando si verifica un problema e il sistema SAP Netweaver BW contrassegna la richiesta con uno stato giallo o rosso.</span><span class="sxs-lookup"><span data-stu-id="82c96-134">This can be useful when a problem has occurred, and the SAP Netweaver BW system has flagged the request with a yellow or red status.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="82c96-135">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="82c96-135">See Also</span></span>  
 <span data-ttu-id="82c96-136">[Editor origine SAP BW &#40;pagina Gestione connessione&#41;](sap-bw-source-editor-connection-manager-page.md) </span><span class="sxs-lookup"><span data-stu-id="82c96-136">[SAP BW Source Editor &#40;Connection Manager Page&#41;](sap-bw-source-editor-connection-manager-page.md) </span></span>  
 <span data-ttu-id="82c96-137">[Editor origine SAP BW &#40;pagina Colonne&#41;](sap-bw-source-editor-columns-page.md) </span><span class="sxs-lookup"><span data-stu-id="82c96-137">[SAP BW Source Editor &#40;Columns Page&#41;](sap-bw-source-editor-columns-page.md) </span></span>  
 <span data-ttu-id="82c96-138">[Editor origine SAP BW &#40;pagina Output degli errori&#41;](sap-bw-source-editor-error-output-page.md) </span><span class="sxs-lookup"><span data-stu-id="82c96-138">[SAP BW Source Editor &#40;Error Output Page&#41;](sap-bw-source-editor-error-output-page.md) </span></span>  
 [<span data-ttu-id="82c96-139">Guida (F1) di Microsoft Connector 1.1 for SAP BW</span><span class="sxs-lookup"><span data-stu-id="82c96-139">Microsoft Connector 1.1 for SAP BW F1 Help</span></span>](../microsoft-connector-for-sap-bw-f1-help.md)  
  
  
