---
title: Editor destinazione SAP BW (pagina Output degli errori) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
ms.assetid: a543d811-0bd2-4890-a0d3-f5fdcd4524b8
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 9ffd58580865a71626252aa2d177530e41156537
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87712223"
---
# <a name="sap-bw-destination-editor-error-output-page"></a><span data-ttu-id="d7026-102">Editor destinazione SAP BW (pagina Output degli errori)</span><span class="sxs-lookup"><span data-stu-id="d7026-102">SAP BW Destination Editor (Error Output Page)</span></span>
  <span data-ttu-id="d7026-103">Usare la pagina **Output degli errori** dell' **Editor destinazione SAP BW** per specificare le opzioni di gestione degli errori.</span><span class="sxs-lookup"><span data-stu-id="d7026-103">Use the **Error Output** page of the **SAP BW Destination Editor** to specify error handling options.</span></span>  
  
 <span data-ttu-id="d7026-104">Per altre informazioni sulla destinazione SAP BW di [!INCLUDE[msCoName](../../includes/msconame-md.md)] Connector 1.1 for SAP BW, vedere [Destinazione SAP BW](sap-bw-destination.md).</span><span class="sxs-lookup"><span data-stu-id="d7026-104">To learn more about the SAP BW destination of the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Connector 1.1 for SAP BW, see [SAP BW Destination](sap-bw-destination.md).</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="d7026-105">La documentazione per Microsoft Connector 1.1 for SAP BW presuppone la conoscenza dell'ambiente SAP Netweaver BW.</span><span class="sxs-lookup"><span data-stu-id="d7026-105">The documentation for the Microsoft Connector 1.1 for SAP BW assumes familiarity with the SAP Netweaver BW environment.</span></span> <span data-ttu-id="d7026-106">Per ulteriori informazioni su SAP Netweaver BW o per informazioni su come configurare oggetti e processi di SAP Netweaver BW, vedere la documentazione SAP.</span><span class="sxs-lookup"><span data-stu-id="d7026-106">For more information about SAP Netweaver BW, or for information about how to configure SAP Netweaver BW objects and processes, see your SAP documentation.</span></span>  
  
 <span data-ttu-id="d7026-107">**Per aprire la pagina Output errori**</span><span class="sxs-lookup"><span data-stu-id="d7026-107">**To open the Error Output page**</span></span>  
  
1.  <span data-ttu-id="d7026-108">In [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)]aprire il pacchetto [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] che contiene la destinazione SAP BW.</span><span class="sxs-lookup"><span data-stu-id="d7026-108">In [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], open the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] package that contains the SAP BW destination.</span></span>  
  
2.  <span data-ttu-id="d7026-109">Nella scheda **Flusso di dati** fare doppio clic sulla destinazione SAP BW.</span><span class="sxs-lookup"><span data-stu-id="d7026-109">On the **Data Flow** tab, double-click the SAP BW destination.</span></span>  
  
3.  <span data-ttu-id="d7026-110">Nell' **Editor destinazione SAP BW**fare clic su **Output degli errori** per aprire la pagina **Output degli errori** dell'editor.</span><span class="sxs-lookup"><span data-stu-id="d7026-110">In the **SAP BW Destination Editor**, click **Error Output** to open the **Error Output** page of the editor.</span></span>  
  
## <a name="options"></a><span data-ttu-id="d7026-111">Opzioni</span><span class="sxs-lookup"><span data-stu-id="d7026-111">Options</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="d7026-112">Se non si conoscono tutti i valori richiesti per configurare la destinazione, può essere necessario consultare l'amministratore SAP.</span><span class="sxs-lookup"><span data-stu-id="d7026-112">If you do not know all the values that are required to configure the destination, you might have to ask your SAP administrator.</span></span>  
  
 <span data-ttu-id="d7026-113">**Input o output**</span><span class="sxs-lookup"><span data-stu-id="d7026-113">**Input or Output**</span></span>  
 <span data-ttu-id="d7026-114">Consente di visualizzare il nome dell'input.</span><span class="sxs-lookup"><span data-stu-id="d7026-114">View the name of the input.</span></span>  
  
 <span data-ttu-id="d7026-115">**Colonna**</span><span class="sxs-lookup"><span data-stu-id="d7026-115">**Column**</span></span>  
 <span data-ttu-id="d7026-116">Questa opzione non viene utilizzata.</span><span class="sxs-lookup"><span data-stu-id="d7026-116">This option is not used.</span></span>  
  
 <span data-ttu-id="d7026-117">**Error (Errore) (Error (Errore)e)**</span><span class="sxs-lookup"><span data-stu-id="d7026-117">**Error**</span></span>  
 <span data-ttu-id="d7026-118">Specificare quale azione dovrà essere eseguita dalla destinazione in caso di errore: ignorare l'errore, reindirizzare la riga o interrompere il componente.</span><span class="sxs-lookup"><span data-stu-id="d7026-118">Specify what the destination should do when an error occurs: ignore the failure, redirect the row, or fail the component.</span></span>  
  
 <span data-ttu-id="d7026-119">**Troncamento**</span><span class="sxs-lookup"><span data-stu-id="d7026-119">**Truncation**</span></span>  
 <span data-ttu-id="d7026-120">Questa opzione non viene utilizzata.</span><span class="sxs-lookup"><span data-stu-id="d7026-120">This option is not used.</span></span>  
  
 <span data-ttu-id="d7026-121">**Descrizione**</span><span class="sxs-lookup"><span data-stu-id="d7026-121">**Description**</span></span>  
 <span data-ttu-id="d7026-122">Consente di visualizzare la descrizione dell'operazione.</span><span class="sxs-lookup"><span data-stu-id="d7026-122">View the description of the operation.</span></span>  
  
 <span data-ttu-id="d7026-123">**Imposta questo valore nelle celle selezionate**</span><span class="sxs-lookup"><span data-stu-id="d7026-123">**Set this value to selected cells**</span></span>  
 <span data-ttu-id="d7026-124">Specificare l'azione che dovrà essere eseguita dalla destinazione su tutte le celle selezionate in caso di errore o troncamento: ignorare l'errore, reindirizzare la riga o interrompere il componente.</span><span class="sxs-lookup"><span data-stu-id="d7026-124">Specify what the destination should do to all the selected cells when an error or truncation occurs: ignore the failure, redirect the row, or fail the component.</span></span>  
  
 <span data-ttu-id="d7026-125">**Applica**</span><span class="sxs-lookup"><span data-stu-id="d7026-125">**Apply**</span></span>  
 <span data-ttu-id="d7026-126">Consente di applicare l'opzione di gestione degli errori alle celle selezionate.</span><span class="sxs-lookup"><span data-stu-id="d7026-126">Apply the error handling option to the selected cells.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d7026-127">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d7026-127">See Also</span></span>  
 <span data-ttu-id="d7026-128">[Editor destinazione SAP BW &#40;pagina Gestione connessione&#41;](sap-bw-destination-editor-connection-manager-page.md) </span><span class="sxs-lookup"><span data-stu-id="d7026-128">[SAP BW Destination Editor &#40;Connection Manager Page&#41;](sap-bw-destination-editor-connection-manager-page.md) </span></span>  
 <span data-ttu-id="d7026-129">[Editor destinazione SAP BW &#40;pagina Mapping&#41;](sap-bw-destination-editor-mappings-page.md) </span><span class="sxs-lookup"><span data-stu-id="d7026-129">[SAP BW Destination Editor &#40;Mappings Page&#41;](sap-bw-destination-editor-mappings-page.md) </span></span>  
 <span data-ttu-id="d7026-130">[Editor destinazione SAP BW &#40;pagina Avanzate&#41;](sap-bw-destination-editor-advanced-page.md) </span><span class="sxs-lookup"><span data-stu-id="d7026-130">[SAP BW Destination Editor &#40;Advanced Page&#41;](sap-bw-destination-editor-advanced-page.md) </span></span>  
 [<span data-ttu-id="d7026-131">Guida (F1) di Microsoft Connector 1.1 for SAP BW</span><span class="sxs-lookup"><span data-stu-id="d7026-131">Microsoft Connector 1.1 for SAP BW F1 Help</span></span>](../microsoft-connector-for-sap-bw-f1-help.md)  
  
  
