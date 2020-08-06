---
title: Crea InfoPackage | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
ms.assetid: 9cd4a848-409f-4681-a390-1c49a2aadbd7
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 95f6ddce4e97c0c21d9f77c432231d414770dbce
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87712248"
---
# <a name="create-infopackage"></a><span data-ttu-id="ac1f0-102">Crea InfoPackage</span><span class="sxs-lookup"><span data-stu-id="ac1f0-102">Create InfoPackage</span></span>
  <span data-ttu-id="ac1f0-103">Usare la finestra di dialogo **Crea InfoPackage** per creare un nuovo InfoPackage nel sistema SAP Netweaver BW.</span><span class="sxs-lookup"><span data-stu-id="ac1f0-103">Use the **Create InfoPackage** dialog box to create a new InfoPackage in the SAP Netweaver BW system.</span></span>  
  
 <span data-ttu-id="ac1f0-104">È possibile aprire la finestra di dialogo **Crea InfoPackage** dalla pagina **Gestione connessione** dell' **Editor destinazione SAP BW**.</span><span class="sxs-lookup"><span data-stu-id="ac1f0-104">You can open the **Create InfoPackage** dialog box from the **Connection Manager** page of the **SAP BW Destination Editor**.</span></span> <span data-ttu-id="ac1f0-105">Per ulteriori informazioni sulla destinazione SAP BW, vedere [SAP BW Destination](sap-bw-destination.md).</span><span class="sxs-lookup"><span data-stu-id="ac1f0-105">To learn more about the SAP BW destination, see [SAP BW Destination](sap-bw-destination.md).</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="ac1f0-106">La documentazione per Microsoft Connector 1.1 for SAP BW presuppone la conoscenza dell'ambiente SAP Netweaver BW.</span><span class="sxs-lookup"><span data-stu-id="ac1f0-106">The documentation for the Microsoft Connector 1.1 for SAP BW assumes familiarity with the SAP Netweaver BW environment.</span></span> <span data-ttu-id="ac1f0-107">Per ulteriori informazioni su SAP Netweaver BW o per informazioni su come configurare oggetti e processi di SAP Netweaver BW, vedere la documentazione SAP.</span><span class="sxs-lookup"><span data-stu-id="ac1f0-107">For more information about SAP Netweaver BW, or for information about how to configure SAP Netweaver BW objects and processes, see your SAP documentation.</span></span>  
  
 <span data-ttu-id="ac1f0-108">**Per aprire la finestra di dialogo Crea InfoPackage**</span><span class="sxs-lookup"><span data-stu-id="ac1f0-108">**To open the Create InfoPackage dialog box**</span></span>  
  
1.  <span data-ttu-id="ac1f0-109">In [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)]aprire il pacchetto [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] che contiene la destinazione SAP BW.</span><span class="sxs-lookup"><span data-stu-id="ac1f0-109">In [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], open the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] package that contains the SAP BW destination.</span></span>  
  
2.  <span data-ttu-id="ac1f0-110">Nella scheda **Flusso di dati** fare doppio clic sulla destinazione SAP BW.</span><span class="sxs-lookup"><span data-stu-id="ac1f0-110">On the **Data Flow** tab, double-click the SAP BW destination.</span></span>  
  
3.  <span data-ttu-id="ac1f0-111">Nell' **Editor destinazione SAP BW**fare clic su **Gestione connessione** per aprire la pagina **Gestione connessione** dell'editor.</span><span class="sxs-lookup"><span data-stu-id="ac1f0-111">In the **SAP BW Destination Editor**, click **Connection Manager** to open the **Connection Manager** page of the editor.</span></span>  
  
4.  <span data-ttu-id="ac1f0-112">Nella casella di gruppo **Crea oggetti SAP BW** della pagina **Gestione connessione** selezionare **InfoPackage**e quindi fare clic su **Crea**.</span><span class="sxs-lookup"><span data-stu-id="ac1f0-112">On the **Connection Manager** page, in the **Create SAP BW Objects** group box, select **InfoPackage**, and then click **Create**.</span></span>  
  
## <a name="options"></a><span data-ttu-id="ac1f0-113">Opzioni</span><span class="sxs-lookup"><span data-stu-id="ac1f0-113">Options</span></span>  
 <span data-ttu-id="ac1f0-114">**InfoSource**</span><span class="sxs-lookup"><span data-stu-id="ac1f0-114">**InfoSource**</span></span>  
 <span data-ttu-id="ac1f0-115">Immettere il nome dell'InfoSource su cui deve essere basato il nuovo InfoPackage.</span><span class="sxs-lookup"><span data-stu-id="ac1f0-115">Enter the name of the InfoSource on which the new InfoPackage should be based.</span></span>  
  
 <span data-ttu-id="ac1f0-116">**Descrizione breve**</span><span class="sxs-lookup"><span data-stu-id="ac1f0-116">**Short description**</span></span>  
 <span data-ttu-id="ac1f0-117">Immettere una descrizione per il nuovo InfoPackage.</span><span class="sxs-lookup"><span data-stu-id="ac1f0-117">Enter a description for the new InfoPackage.</span></span>  
  
 <span data-ttu-id="ac1f0-118">**Sistema di origine**</span><span class="sxs-lookup"><span data-stu-id="ac1f0-118">**Source system**</span></span>  
 <span data-ttu-id="ac1f0-119">Selezionare il sistema di origine con cui deve essere associato il nuovo InfoPackage.</span><span class="sxs-lookup"><span data-stu-id="ac1f0-119">Select the source system with which the new InfoPackage should be associated.</span></span>  
  
 <span data-ttu-id="ac1f0-120">**Attributes (Attributi)**</span><span class="sxs-lookup"><span data-stu-id="ac1f0-120">**Attributes**</span></span>  
 <span data-ttu-id="ac1f0-121">Indica che l'InfoPackage caricherà i dati dell'attributo.</span><span class="sxs-lookup"><span data-stu-id="ac1f0-121">Indicates that the InfoPackage will load attribute data.</span></span>  
  
 <span data-ttu-id="ac1f0-122">**Testi**</span><span class="sxs-lookup"><span data-stu-id="ac1f0-122">**Texts**</span></span>  
 <span data-ttu-id="ac1f0-123">Indica che l'InfoPackage caricherà i dati del testo.</span><span class="sxs-lookup"><span data-stu-id="ac1f0-123">Indicates that the InfoPackage will load text data.</span></span>  
  
 <span data-ttu-id="ac1f0-124">**Transazione**</span><span class="sxs-lookup"><span data-stu-id="ac1f0-124">**Transaction**</span></span>  
 <span data-ttu-id="ac1f0-125">Indica che l'InfoPackage caricherà i dati della transazione.</span><span class="sxs-lookup"><span data-stu-id="ac1f0-125">Indicates that the InfoPackage will load transaction data.</span></span>  
  
 <span data-ttu-id="ac1f0-126">**Salva e attiva**</span><span class="sxs-lookup"><span data-stu-id="ac1f0-126">**Save & Activate**</span></span>  
 <span data-ttu-id="ac1f0-127">Salvare e attivare il nuovo InfoPackage.</span><span class="sxs-lookup"><span data-stu-id="ac1f0-127">Save and activate the new InfoPackage.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ac1f0-128">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ac1f0-128">See Also</span></span>  
 [<span data-ttu-id="ac1f0-129">Guida (F1) di Microsoft Connector 1.1 for SAP BW</span><span class="sxs-lookup"><span data-stu-id="ac1f0-129">Microsoft Connector 1.1 for SAP BW F1 Help</span></span>](../microsoft-connector-for-sap-bw-f1-help.md)  
  
  
