---
title: Visualizzare pacchetti di Integration Services in SQL Server Management Studio (servizio SSIS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- viewing packages
- connections [Integration Services], packages
ms.assetid: 783e653c-0f1f-45ed-b3ef-5ba07b019f27
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 4ba86320f1b1a685eab6e80399f3e8c21bd110eb
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87712123"
---
# <a name="view-integration-services-packages-in-sql-server-management-studio-ssis-service"></a><span data-ttu-id="13453-102">Visualizzare pacchetti di Integration Services in SQL Server Management Studio (servizio SSIS)</span><span class="sxs-lookup"><span data-stu-id="13453-102">View Integration Services Packages in SQL Server Management Studio (SSIS Service)</span></span>
    
> [!IMPORTANT]  
>  <span data-ttu-id="13453-103">In questo argomento viene illustrato il servizio [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] , un servizio Windows per la gestione dei pacchetti di [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="13453-103">This topic discusses the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] service, a Windows service for managing [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] packages.</span></span> [!INCLUDE[ssSQL11](../includes/sssql11-md.md)] <span data-ttu-id="13453-104">supporta il servizio per la compatibilità con le versioni precedenti di [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="13453-104">supports the service for backward compatibility with earlier releases of [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)].</span></span> <span data-ttu-id="13453-105">A partire da [!INCLUDE[ssSQL11](../includes/sssql11-md.md)], è possibile gestire oggetti come i pacchetti del server Integration Services.</span><span class="sxs-lookup"><span data-stu-id="13453-105">Starting in [!INCLUDE[ssSQL11](../includes/sssql11-md.md)], you can manage objects such as packages on the Integration Services server.</span></span>  
  
 <span data-ttu-id="13453-106">In questo argomento viene descritta la procedura per la connessione a [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] in [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] e la visualizzazione di un elenco dei pacchetti gestiti dal servizio [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="13453-106">This procedure describes how to connect to [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] in [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] and view a list of the packages that the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] service manages.</span></span>  
  
### <a name="to-connect-to-integration-services"></a><span data-ttu-id="13453-107">Per connettersi a Integration Services</span><span class="sxs-lookup"><span data-stu-id="13453-107">To connect to Integration Services</span></span>  
  
1.  <span data-ttu-id="13453-108">Fare clic sul pulsante **Start**, scegliere **Tutti i programmi**, **Microsoft SQL Server**, quindi **SQL Server Management Studio**.</span><span class="sxs-lookup"><span data-stu-id="13453-108">Click **Start**, point to **All Programs**, point to **Microsoft SQL Server**, and then click **SQL Server Management Studio**.</span></span>  
  
2.  <span data-ttu-id="13453-109">Nella finestra di dialogo **Connetti al server** selezionare **Integration Services** dall'elenco **Tipo server** , specificare il nome del server nella finestra di dialogo **Nome server** e quindi fare clic su **Connetti**.</span><span class="sxs-lookup"><span data-stu-id="13453-109">In the **Connect to Server** dialog box, select **Integration Services** in the **Server type** list, provide a server name in the **Server name** box, and then click **Connect**.</span></span>  
  
    > [!IMPORTANT]  
    >  <span data-ttu-id="13453-110">Se non è possibile stabilire la connessione con [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)], è probabile che il servizio [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] non sia in esecuzione.</span><span class="sxs-lookup"><span data-stu-id="13453-110">If you cannot connect to [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)], the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] service is likely not running.</span></span> <span data-ttu-id="13453-111">Per informazioni sullo stato del servizio, fare clic sul pulsante **Start**, scegliere **Tutti i programmi**, **Microsoft SQL Server**, **Strumenti di configurazione**, quindi fare clic su **Gestione configurazione SQL Server**.</span><span class="sxs-lookup"><span data-stu-id="13453-111">To learn the status of the service, click **Start**, point to **All Programs**, point to **Microsoft SQL Server**, point to **Configuration Tools**, and then click **SQL Server Configuration Manager**.</span></span> <span data-ttu-id="13453-112">Nel riquadro di sinistra fare clic su **Servizi di SQL Server**.</span><span class="sxs-lookup"><span data-stu-id="13453-112">In the left pane, click **SQL Server Services**.</span></span> <span data-ttu-id="13453-113">Nel riquadro di destra cercare il servizio [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="13453-113">In the right pane, find the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] service.</span></span> <span data-ttu-id="13453-114">Se non è già in esecuzione, avviare il servizio.</span><span class="sxs-lookup"><span data-stu-id="13453-114">Start the service if it is not already running.</span></span>  
  
     [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] <span data-ttu-id="13453-115">si apre.</span><span class="sxs-lookup"><span data-stu-id="13453-115">opens.</span></span> <span data-ttu-id="13453-116">Per impostazione predefinita, la finestra Esplora oggetti viene aperta e posizionata nell'angolo inferiore sinistro del programma.</span><span class="sxs-lookup"><span data-stu-id="13453-116">By default the Object Explorer window is open and positioned in the lower-left corner of the studio.</span></span> <span data-ttu-id="13453-117">Se Esplora oggetti non viene visualizzato, scegliere **Esplora oggetti** dal menu **Visualizza** .</span><span class="sxs-lookup"><span data-stu-id="13453-117">If Object Explorer is not open, click **Object Explorer** on the **View** menu.</span></span>  
  
### <a name="to-view-the-packages-that-integration-services-service-manages"></a><span data-ttu-id="13453-118">Per visualizzare i pacchetti gestiti da Integration Services</span><span class="sxs-lookup"><span data-stu-id="13453-118">To view the packages that Integration Services service manages</span></span>  
  
1.  <span data-ttu-id="13453-119">In Esplora oggetti espandere la cartella Pacchetti archiviati.</span><span class="sxs-lookup"><span data-stu-id="13453-119">In Object Explorer, expand the Stored Packages folder.</span></span>  
  
2.  <span data-ttu-id="13453-120">Espandere le sottocartelle di Pacchetti archiviati per visualizzare i pacchetti.</span><span class="sxs-lookup"><span data-stu-id="13453-120">Expand the Stored Packages subfolders to show packages.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="13453-121">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="13453-121">See Also</span></span>  
 <span data-ttu-id="13453-122">[Gestione pacchetti &#40;servizio SSIS&#41;](service/package-management-ssis-service.md) </span><span class="sxs-lookup"><span data-stu-id="13453-122">[Package Management &#40;SSIS Service&#41;](service/package-management-ssis-service.md) </span></span>  
 [<span data-ttu-id="13453-123">Utilizzo di SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="13453-123">Use SQL Server Management Studio</span></span>](../database-engine/use-sql-server-management-studio.md)  
  
  
