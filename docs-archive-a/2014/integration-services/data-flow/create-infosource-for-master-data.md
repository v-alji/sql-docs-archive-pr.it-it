---
title: Crea InfoSource per dati master | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
ms.assetid: b52a9a89-8380-4a02-8a83-dcfb46ae860e
author: chugugrace
ms.author: chugu
ms.openlocfilehash: bb90bc5cf27f37dc89df236b765db98088a5804a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87712244"
---
# <a name="create-infosource-for-master-data"></a><span data-ttu-id="af6a4-102">Crea InfoSource per dati master</span><span class="sxs-lookup"><span data-stu-id="af6a4-102">Create InfoSource for Master Data</span></span>
  <span data-ttu-id="af6a4-103">Usare la finestra di dialogo **Crea InfoSource per dati master** per creare un nuovo InfoSource per i dati master nel sistema SAP Netweaver BW.</span><span class="sxs-lookup"><span data-stu-id="af6a4-103">Use the **Create InfoSource for Master Data** dialog box to create a new InfoSource for master data in the SAP Netweaver BW system.</span></span>  
  
 <span data-ttu-id="af6a4-104">È possibile aprire la finestra di dialogo **Crea InfoSource per dati master** dalla pagina **Gestione connessione** dell' **Editor destinazione SAP BW**.</span><span class="sxs-lookup"><span data-stu-id="af6a4-104">You can open the **Create InfoSource for Master Data** dialog box from the **Connection Manager** page of the **SAP BW Destination Editor**.</span></span> <span data-ttu-id="af6a4-105">Per ulteriori informazioni sulla destinazione SAP BW, vedere [SAP BW Destination](sap-bw-destination.md).</span><span class="sxs-lookup"><span data-stu-id="af6a4-105">To learn more about the SAP BW destination, see [SAP BW Destination](sap-bw-destination.md).</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="af6a4-106">La documentazione per Microsoft Connector 1.1 for SAP BW presuppone la conoscenza dell'ambiente SAP Netweaver BW.</span><span class="sxs-lookup"><span data-stu-id="af6a4-106">The documentation for the Microsoft Connector 1.1 for SAP BW assumes familiarity with the SAP Netweaver BW environment.</span></span> <span data-ttu-id="af6a4-107">Per ulteriori informazioni su SAP Netweaver BW o per informazioni su come configurare oggetti e processi di SAP Netweaver BW, vedere la documentazione SAP.</span><span class="sxs-lookup"><span data-stu-id="af6a4-107">For more information about SAP Netweaver BW, or for information about how to configure SAP Netweaver BW objects and processes, see your SAP documentation.</span></span>  
  
 <span data-ttu-id="af6a4-108">**Per aprire la finestra di dialogo Crea InfoSource per dati master**</span><span class="sxs-lookup"><span data-stu-id="af6a4-108">**To open the Create InfoSource for Master Data dialog box**</span></span>  
  
1.  <span data-ttu-id="af6a4-109">In [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)]aprire il pacchetto [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] che contiene la destinazione SAP BW.</span><span class="sxs-lookup"><span data-stu-id="af6a4-109">In [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], open the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] package that contains the SAP BW destination.</span></span>  
  
2.  <span data-ttu-id="af6a4-110">Nella scheda **Flusso di dati** fare doppio clic sulla destinazione SAP BW.</span><span class="sxs-lookup"><span data-stu-id="af6a4-110">On the **Data Flow** tab, double-click the SAP BW destination.</span></span>  
  
3.  <span data-ttu-id="af6a4-111">Nell' **Editor destinazione SAP BW**fare clic su **Gestione connessione** per aprire la pagina **Gestione connessione** dell'editor.</span><span class="sxs-lookup"><span data-stu-id="af6a4-111">In the **SAP BW Destination Editor**, click **Connection Manager** to open the **Connection Manager** page of the editor.</span></span>  
  
4.  <span data-ttu-id="af6a4-112">Nella casella di gruppo **Crea oggetti SAP BW** della pagina **Gestione connessione** selezionare **InfoSource**, quindi fare clic su **Crea**.</span><span class="sxs-lookup"><span data-stu-id="af6a4-112">On the **Connection Manager** page, in the **Create SAP BW Objects** group box, select **InfoSource**, and then click **Create**.</span></span>  
  
5.  <span data-ttu-id="af6a4-113">Nella finestra di dialogo **Crea InfoSource** selezionare **Dati master**, quindi fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="af6a4-113">In the **Create InfoSource** dialog box, select **Master data**, and then click **OK**.</span></span>  
  
## <a name="options"></a><span data-ttu-id="af6a4-114">Opzioni</span><span class="sxs-lookup"><span data-stu-id="af6a4-114">Options</span></span>  
 <span data-ttu-id="af6a4-115">**Nome InfoObject**</span><span class="sxs-lookup"><span data-stu-id="af6a4-115">**InfoObject name**</span></span>  
 <span data-ttu-id="af6a4-116">Immettere il nome dell'InfoObject su cui deve essere basato il nuovo InfoSource.</span><span class="sxs-lookup"><span data-stu-id="af6a4-116">Enter the name of the InfoObject on which the new InfoSource should be based.</span></span>  
  
 <span data-ttu-id="af6a4-117">**Cerca**</span><span class="sxs-lookup"><span data-stu-id="af6a4-117">**Look up**</span></span>  
 <span data-ttu-id="af6a4-118">Cercare l'InfoObject.</span><span class="sxs-lookup"><span data-stu-id="af6a4-118">Look up the InfoObject.</span></span> <span data-ttu-id="af6a4-119">Tramite questa opzione viene visualizzata la finestra di dialogo **Cerca InfoObject** in cui è possibile selezionare l'InfoObject.</span><span class="sxs-lookup"><span data-stu-id="af6a4-119">This option opens the **Look Up InfoObject** dialog box in which you can select the InfoObject.</span></span> <span data-ttu-id="af6a4-120">Per altre informazioni su questa finestra di dialogo, vedere [Cerca InfoObject](look-up-infoobject.md).</span><span class="sxs-lookup"><span data-stu-id="af6a4-120">For more information about this dialog box, see [Look Up InfoObject](look-up-infoobject.md).</span></span>  
  
 <span data-ttu-id="af6a4-121">Dopo aver selezionato un InfoObject, la casella di testo **Nome InfoObject** viene compilata dal componente con il nome dell'InfoObject selezionato.</span><span class="sxs-lookup"><span data-stu-id="af6a4-121">After you select an InfoObject, the component populates the **InfoObject name** text box with the name of the selected InfoObject.</span></span>  
  
 <span data-ttu-id="af6a4-122">**Nuovo**</span><span class="sxs-lookup"><span data-stu-id="af6a4-122">**New**</span></span>  
 <span data-ttu-id="af6a4-123">Creare un nuovo InfoObject.</span><span class="sxs-lookup"><span data-stu-id="af6a4-123">Create a new InfoObject.</span></span> <span data-ttu-id="af6a4-124">Tramite questa opzione viene visualizzata la finestra di dialogo **Crea nuovo InfoObject** in cui è possibile creare il nuovo InfoObject.</span><span class="sxs-lookup"><span data-stu-id="af6a4-124">This option opens the **Create New InfoObject** dialog box in which you can create the new InfoObject.</span></span> <span data-ttu-id="af6a4-125">Per altre informazioni su questa finestra di dialogo, vedere [Crea nuovo InfoObject](create-new-infoobject.md).</span><span class="sxs-lookup"><span data-stu-id="af6a4-125">For more information about this dialog box, see [Create New InfoObject](create-new-infoobject.md).</span></span>  
  
 <span data-ttu-id="af6a4-126">Dopo aver creato un InfoObject, la casella di testo **Nome InfoObject** viene compilata dal componente con il nome del nuovo InfoObject.</span><span class="sxs-lookup"><span data-stu-id="af6a4-126">After you create an InfoObject, the component populates the **InfoObject name** text box with the name of the new InfoObject.</span></span>  
  
 <span data-ttu-id="af6a4-127">**Descrizione breve**</span><span class="sxs-lookup"><span data-stu-id="af6a4-127">**Short description**</span></span>  
 <span data-ttu-id="af6a4-128">Immettere una breve descrizione per il nuovo InfoSource.</span><span class="sxs-lookup"><span data-stu-id="af6a4-128">Enter a short description for the new InfoSource.</span></span>  
  
 <span data-ttu-id="af6a4-129">**Descrizione lunga**</span><span class="sxs-lookup"><span data-stu-id="af6a4-129">**Long description**</span></span>  
 <span data-ttu-id="af6a4-130">Immettere una descrizione lunga per il nuovo InfoSource.</span><span class="sxs-lookup"><span data-stu-id="af6a4-130">Enter a long description for the new InfoSource.</span></span>  
  
 <span data-ttu-id="af6a4-131">**Sistema di origine**</span><span class="sxs-lookup"><span data-stu-id="af6a4-131">**Source system**</span></span>  
 <span data-ttu-id="af6a4-132">Selezionare il sistema di origine da associare al nuovo InfoSource.</span><span class="sxs-lookup"><span data-stu-id="af6a4-132">Select the source system to be associated with the new InfoSource.</span></span>  
  
 <span data-ttu-id="af6a4-133">**Applicazione**</span><span class="sxs-lookup"><span data-stu-id="af6a4-133">**Application**</span></span>  
 <span data-ttu-id="af6a4-134">Immettere il nome dell'applicazione da associare al nuovo InfoSource.</span><span class="sxs-lookup"><span data-stu-id="af6a4-134">Enter the name of the application to be associated with the new InfoSource.</span></span>  
  
 <span data-ttu-id="af6a4-135">**Attributes (Attributi)**</span><span class="sxs-lookup"><span data-stu-id="af6a4-135">**Attributes**</span></span>  
 <span data-ttu-id="af6a4-136">Indica che i dati master sono costituiti da attributi.</span><span class="sxs-lookup"><span data-stu-id="af6a4-136">Indicates that the master data consists of attributes.</span></span>  
  
 <span data-ttu-id="af6a4-137">**Testi**</span><span class="sxs-lookup"><span data-stu-id="af6a4-137">**Texts**</span></span>  
 <span data-ttu-id="af6a4-138">Indica che i dati master sono costituiti da attributi.</span><span class="sxs-lookup"><span data-stu-id="af6a4-138">Indicates that the master data consists of attributes.</span></span>  
  
 <span data-ttu-id="af6a4-139">**Salva e attiva**</span><span class="sxs-lookup"><span data-stu-id="af6a4-139">**Save & Activate**</span></span>  
 <span data-ttu-id="af6a4-140">Salvare e attivare il nuovo InfoSource.</span><span class="sxs-lookup"><span data-stu-id="af6a4-140">Save and activate the new InfoSource.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="af6a4-141">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="af6a4-141">See Also</span></span>  
 <span data-ttu-id="af6a4-142">[Crea InfoSource](create-infosource.md) </span><span class="sxs-lookup"><span data-stu-id="af6a4-142">[Create InfoSource](create-infosource.md) </span></span>  
 [<span data-ttu-id="af6a4-143">Guida (F1) di Microsoft Connector 1.1 for SAP BW</span><span class="sxs-lookup"><span data-stu-id="af6a4-143">Microsoft Connector 1.1 for SAP BW F1 Help</span></span>](../microsoft-connector-for-sap-bw-f1-help.md)  
  
  
