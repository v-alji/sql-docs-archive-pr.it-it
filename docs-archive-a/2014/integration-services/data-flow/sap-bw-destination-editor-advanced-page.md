---
title: Editor destinazione SAP BW (pagina Avanzate) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
ms.assetid: 862957db-bbc6-4dda-bc0e-591457f1baa7
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 0c5ca943b804ad39cc391cb1cf7f06e056ddbe56
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87629522"
---
# <a name="sap-bw-destination-editor-advanced-page"></a><span data-ttu-id="d0709-102">Editor destinazione SAP BW (pagina Avanzate)</span><span class="sxs-lookup"><span data-stu-id="d0709-102">SAP BW Destination Editor (Advanced Page)</span></span>
  <span data-ttu-id="d0709-103">Usare la pagina **Avanzate** dell' **Editor destinazione SAP BW** per definire le impostazioni avanzate quali dimensioni del pacchetto e informazioni sul timeout.</span><span class="sxs-lookup"><span data-stu-id="d0709-103">Use the **Advanced** page of the **SAP BW Destination Editor** to set advanced settings such as package size and time-out information.</span></span>  
  
 <span data-ttu-id="d0709-104">Per altre informazioni sulla destinazione SAP BW di [!INCLUDE[msCoName](../../includes/msconame-md.md)] Connector 1.1 for SAP BW, vedere [Destinazione SAP BW](sap-bw-destination.md).</span><span class="sxs-lookup"><span data-stu-id="d0709-104">To learn more about the SAP BW destination of the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Connector 1.1 for SAP BW, see [SAP BW Destination](sap-bw-destination.md).</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="d0709-105">La documentazione per Microsoft Connector 1.1 for SAP BW presuppone la conoscenza dell'ambiente SAP Netweaver BW.</span><span class="sxs-lookup"><span data-stu-id="d0709-105">The documentation for the Microsoft Connector 1.1 for SAP BW assumes familiarity with the SAP Netweaver BW environment.</span></span> <span data-ttu-id="d0709-106">Per ulteriori informazioni su SAP Netweaver BW o per informazioni su come configurare oggetti e processi di SAP Netweaver BW, vedere la documentazione SAP.</span><span class="sxs-lookup"><span data-stu-id="d0709-106">For more information about SAP Netweaver BW, or for information about how to configure SAP Netweaver BW objects and processes, see your SAP documentation.</span></span>  
  
 <span data-ttu-id="d0709-107">**Per aprire la pagina Avanzate**</span><span class="sxs-lookup"><span data-stu-id="d0709-107">**To open the Advanced page**</span></span>  
  
1.  <span data-ttu-id="d0709-108">In [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)]aprire il pacchetto [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] che contiene la destinazione SAP BW.</span><span class="sxs-lookup"><span data-stu-id="d0709-108">In [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], open the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] package that contains the SAP BW destination.</span></span>  
  
2.  <span data-ttu-id="d0709-109">Nella scheda **Flusso di dati** fare doppio clic sulla destinazione SAP BW.</span><span class="sxs-lookup"><span data-stu-id="d0709-109">On the **Data Flow** tab, double-click the SAP BW destination.</span></span>  
  
3.  <span data-ttu-id="d0709-110">Nell' **Editor destinazione SAP BW**fare clic su **Avanzate** per aprire la pagina **Avanzate** dell'editor.</span><span class="sxs-lookup"><span data-stu-id="d0709-110">In the **SAP BW Destination Editor**, click **Advanced** to open the **Advanced** page of the editor.</span></span>  
  
## <a name="options"></a><span data-ttu-id="d0709-111">Opzioni</span><span class="sxs-lookup"><span data-stu-id="d0709-111">Options</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="d0709-112">Se non si conoscono tutti i valori richiesti per configurare la destinazione, può essere necessario consultare l'amministratore SAP.</span><span class="sxs-lookup"><span data-stu-id="d0709-112">If you do not know all the values that are required to configure the destination, you might have to ask your SAP administrator.</span></span>  
  
 <span data-ttu-id="d0709-113">**Dimensioni pacchetto**</span><span class="sxs-lookup"><span data-stu-id="d0709-113">**Package size**</span></span>  
 <span data-ttu-id="d0709-114">Specificare il numero di righe di dati che verranno trasferite contemporaneamente.</span><span class="sxs-lookup"><span data-stu-id="d0709-114">Specify how many rows of data will be transferred at a time.</span></span> <span data-ttu-id="d0709-115">Il valore ottimale per questo parametro dipende dal sistema SAP Netweaver BW e dall'ulteriore elaborazione dei dati che potrebbe verificarsi.</span><span class="sxs-lookup"><span data-stu-id="d0709-115">The optimal value for this parameter depends on the SAP Netweaver BW system and on additional processing of the data that might occur.</span></span> <span data-ttu-id="d0709-116">In genere, i valori compresi tra 2000 e 20000 offrono prestazioni ottimali.</span><span class="sxs-lookup"><span data-stu-id="d0709-116">Typically, values between 2000 and 20000 offer the best performance.</span></span>  
  
 <span data-ttu-id="d0709-117">**Attivazione catena di processi**</span><span class="sxs-lookup"><span data-stu-id="d0709-117">**Trigger process chain**</span></span>  
 <span data-ttu-id="d0709-118">(Facoltativo) Specificare il nome di una catena di processi da attivare dopo il completamento del caricamento dei dati.</span><span class="sxs-lookup"><span data-stu-id="d0709-118">(Optional) Specify the name of a process chain to be triggered after the loading of data is completed.</span></span>  
  
 <span data-ttu-id="d0709-119">**Timeout attesa InfoPackage**</span><span class="sxs-lookup"><span data-stu-id="d0709-119">**Timeout for waiting InfoPackage**</span></span>  
 <span data-ttu-id="d0709-120">Specificare il numero massimo di secondi di attesa del completamento dell'InfoPackage da parte della destinazione.</span><span class="sxs-lookup"><span data-stu-id="d0709-120">Specify the maximum number of seconds that the destination should wait for the InfoPackage to finish.</span></span>  
  
 <span data-ttu-id="d0709-121">**Attendi completamento trasferimento dati**</span><span class="sxs-lookup"><span data-stu-id="d0709-121">**Wait for data transfer to finish**</span></span>  
 <span data-ttu-id="d0709-122">Specificare se la destinazione deve attendere il completamento del caricamento dei dati da parte del sistema SAP Netweaver BW.</span><span class="sxs-lookup"><span data-stu-id="d0709-122">Specify whether the destination should wait until the SAP Netweaver BW system has finished loading the data.</span></span>  
  
 <span data-ttu-id="d0709-123">**Non avviare InfoPackage - solo attesa**</span><span class="sxs-lookup"><span data-stu-id="d0709-123">**No InfoPackage Start (Only Wait)**</span></span>  
 <span data-ttu-id="d0709-124">Specificare che la destinazione non attiva un InfoPackage, ma attende semplicemente la notifica dell'avvio del caricamento dei dati da parte del sistema SAP Netweaver BW.</span><span class="sxs-lookup"><span data-stu-id="d0709-124">Specify that the destination does not trigger an InfoPackage, but just waits for notification that the SAP Netweaver BW system has started loading the data.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d0709-125">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d0709-125">See Also</span></span>  
 <span data-ttu-id="d0709-126">[Editor destinazione SAP BW &#40;pagina Gestione connessione&#41;](sap-bw-destination-editor-connection-manager-page.md) </span><span class="sxs-lookup"><span data-stu-id="d0709-126">[SAP BW Destination Editor &#40;Connection Manager Page&#41;](sap-bw-destination-editor-connection-manager-page.md) </span></span>  
 <span data-ttu-id="d0709-127">[Editor destinazione SAP BW &#40;pagina Mapping&#41;](sap-bw-destination-editor-mappings-page.md) </span><span class="sxs-lookup"><span data-stu-id="d0709-127">[SAP BW Destination Editor &#40;Mappings Page&#41;](sap-bw-destination-editor-mappings-page.md) </span></span>  
 <span data-ttu-id="d0709-128">[Editor destinazione SAP BW &#40;pagina Output degli errori&#41;](sap-bw-destination-editor-error-output-page.md) </span><span class="sxs-lookup"><span data-stu-id="d0709-128">[SAP BW Destination Editor &#40;Error Output Page&#41;](sap-bw-destination-editor-error-output-page.md) </span></span>  
 [<span data-ttu-id="d0709-129">Guida (F1) di Microsoft Connector 1.1 for SAP BW</span><span class="sxs-lookup"><span data-stu-id="d0709-129">Microsoft Connector 1.1 for SAP BW F1 Help</span></span>](../microsoft-connector-for-sap-bw-f1-help.md)  
  
  
