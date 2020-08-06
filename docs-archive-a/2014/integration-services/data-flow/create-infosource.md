---
title: Crea InfoSource | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
ms.assetid: e7db233b-5464-43de-9d26-6dd24c7ac1b7
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 9620d3170310322c79679e8298ffe465067ae7d8
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87712232"
---
# <a name="create-infosource"></a><span data-ttu-id="ebcd5-102">Crea InfoSource</span><span class="sxs-lookup"><span data-stu-id="ebcd5-102">Create InfoSource</span></span>
  <span data-ttu-id="ebcd5-103">Usare la finestra di dialogo **Crea InfoSource** per creare un nuovo InfoSource.</span><span class="sxs-lookup"><span data-stu-id="ebcd5-103">Use the **Create InfoSource** dialog box to create a new InfoSource.</span></span> <span data-ttu-id="ebcd5-104">Per creare il nuovo InfoSource, usare la finestra di dialogo **Crea InfoSource per dati transazione** o **Crea InfoSource per dati master** .</span><span class="sxs-lookup"><span data-stu-id="ebcd5-104">To create the new InfoSource, you use either the **Create InfoSource for Transaction Data** or the **Create InfoSource for Master Data** dialog box.</span></span>  
  
 <span data-ttu-id="ebcd5-105">È possibile aprire la finestra di dialogo **Crea InfoSource** dalla pagina **Gestione connessione** dell' **Editor destinazione SAP BW**.</span><span class="sxs-lookup"><span data-stu-id="ebcd5-105">You can open the **Create InfoSource** dialog box from the **Connection Manager** page of the **SAP BW Destination Editor**.</span></span> <span data-ttu-id="ebcd5-106">Per ulteriori informazioni sulla destinazione SAP BW, vedere [SAP BW Destination](sap-bw-destination.md).</span><span class="sxs-lookup"><span data-stu-id="ebcd5-106">To learn more about the SAP BW destination, see [SAP BW Destination](sap-bw-destination.md).</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="ebcd5-107">La documentazione per Microsoft Connector 1.1 for SAP BW presuppone la conoscenza dell'ambiente SAP Netweaver BW.</span><span class="sxs-lookup"><span data-stu-id="ebcd5-107">The documentation for the Microsoft Connector 1.1 for SAP BW assumes familiarity with the SAP Netweaver BW environment.</span></span> <span data-ttu-id="ebcd5-108">Per ulteriori informazioni su SAP Netweaver BW o per informazioni su come configurare oggetti e processi di SAP Netweaver BW, vedere la documentazione SAP.</span><span class="sxs-lookup"><span data-stu-id="ebcd5-108">For more information about SAP Netweaver BW, or for information about how to configure SAP Netweaver BW objects and processes, see your SAP documentation.</span></span>  
  
 <span data-ttu-id="ebcd5-109">**Per aprire la finestra di dialogo Crea InfoSource**</span><span class="sxs-lookup"><span data-stu-id="ebcd5-109">**To open the Create InfoSource dialog box**</span></span>  
  
1.  <span data-ttu-id="ebcd5-110">In [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)]aprire il pacchetto [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] che contiene la destinazione SAP BW.</span><span class="sxs-lookup"><span data-stu-id="ebcd5-110">In [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], open the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] package that contains the SAP BW destination.</span></span>  
  
2.  <span data-ttu-id="ebcd5-111">Nella scheda **Flusso di dati** fare doppio clic sulla destinazione SAP BW.</span><span class="sxs-lookup"><span data-stu-id="ebcd5-111">On the **Data Flow** tab, double-click the SAP BW destination.</span></span>  
  
3.  <span data-ttu-id="ebcd5-112">Nell' **Editor destinazione SAP BW**fare clic su **Gestione connessione** per aprire la pagina **Gestione connessione** dell'editor.</span><span class="sxs-lookup"><span data-stu-id="ebcd5-112">In the **SAP BW Destination Editor**, click **Connection Manager** to open the **Connection Manager** page of the editor.</span></span>  
  
4.  <span data-ttu-id="ebcd5-113">Nella casella di gruppo **Crea oggetti SAP BW** della pagina **Gestione connessione** selezionare **InfoSource**, quindi fare clic su **Crea**.</span><span class="sxs-lookup"><span data-stu-id="ebcd5-113">On the **Connection Manager** page, in the **Create SAP BW Objects** group box, select **InfoSource**, and then click **Create**.</span></span>  
  
## <a name="options"></a><span data-ttu-id="ebcd5-114">Opzioni</span><span class="sxs-lookup"><span data-stu-id="ebcd5-114">Options</span></span>  
 <span data-ttu-id="ebcd5-115">**Dati transazione**</span><span class="sxs-lookup"><span data-stu-id="ebcd5-115">**Transaction data**</span></span>  
 <span data-ttu-id="ebcd5-116">Creare un nuovo InfoSource per i dati della transazione.</span><span class="sxs-lookup"><span data-stu-id="ebcd5-116">Create a new InfoSource for transaction data.</span></span>  
  
 <span data-ttu-id="ebcd5-117">Se si seleziona questa opzione, viene visualizzata la finestra di dialogo **Crea InfoSource per dati transazione** .</span><span class="sxs-lookup"><span data-stu-id="ebcd5-117">If you select this option, the **Create InfoSource for Transaction Data** dialog box opens.</span></span> <span data-ttu-id="ebcd5-118">Usare la finestra di dialogo **Crea InfoSource per dati transazione** per creare il nuovo InfoSource.</span><span class="sxs-lookup"><span data-stu-id="ebcd5-118">You use the **Create InfoSource for Transaction Data** dialog box to create the new InfoSource.</span></span> <span data-ttu-id="ebcd5-119">Per altre informazioni su questa finestra di dialogo, vedere [Crea InfoSource per dati transazione](create-infosource-for-transaction-data.md).</span><span class="sxs-lookup"><span data-stu-id="ebcd5-119">For more information about this dialog box, see [Create InfoSource for Transaction Data](create-infosource-for-transaction-data.md).</span></span>  
  
 <span data-ttu-id="ebcd5-120">**Dati master**</span><span class="sxs-lookup"><span data-stu-id="ebcd5-120">**Master data**</span></span>  
 <span data-ttu-id="ebcd5-121">Creare un nuovo InfoSource per i dati master.</span><span class="sxs-lookup"><span data-stu-id="ebcd5-121">Create a new InfoSource for master data.</span></span>  
  
 <span data-ttu-id="ebcd5-122">Se si seleziona questa opzione, viene visualizzata la finestra di dialogo **Crea InfoSource per dati master** .</span><span class="sxs-lookup"><span data-stu-id="ebcd5-122">If you select this option, the **Create InfoSource for Master Data** dialog box opens.</span></span> <span data-ttu-id="ebcd5-123">Usare la finestra di dialogo **Crea InfoSource per dati master** per creare il nuovo InfoSource.</span><span class="sxs-lookup"><span data-stu-id="ebcd5-123">You use the **Create InfoSource for Master Data** dialog box to create the new InfoSource.</span></span> <span data-ttu-id="ebcd5-124">Per altre informazioni su questa finestra di dialogo, vedere [Crea InfoSource per dati master](create-infosource-for-master-data.md).</span><span class="sxs-lookup"><span data-stu-id="ebcd5-124">For more information about this dialog box, see [Create InfoSource for Master Data](create-infosource-for-master-data.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ebcd5-125">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ebcd5-125">See Also</span></span>  
 [<span data-ttu-id="ebcd5-126">Guida (F1) di Microsoft Connector 1.1 for SAP BW</span><span class="sxs-lookup"><span data-stu-id="ebcd5-126">Microsoft Connector 1.1 for SAP BW F1 Help</span></span>](../microsoft-connector-for-sap-bw-f1-help.md)  
  
  
