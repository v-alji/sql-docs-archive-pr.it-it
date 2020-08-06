---
title: Visualizzare gli eventi per il servizio Integration Services | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- events [Integration Services]
- service [Integration Services], events
- Integration Services service, events
ms.assetid: 37e23946-10d1-4116-8568-8fd24067102e
author: chugugrace
ms.author: chugu
ms.openlocfilehash: a513c8fc917da2987f3619c8eb9011e1170f7dcf
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87636265"
---
# <a name="view-events-for-the-integration-services-service"></a><span data-ttu-id="d4fe4-102">Visualizzare eventi per il servizio Integration Services</span><span class="sxs-lookup"><span data-stu-id="d4fe4-102">View Events for the Integration Services Service</span></span>
  <span data-ttu-id="d4fe4-103">Sono disponibili due strumenti nei quali è possibile visualizzare eventi per il servizio [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] :</span><span class="sxs-lookup"><span data-stu-id="d4fe4-103">There are two tools in which you can view events for the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] service:</span></span>  
  
-   <span data-ttu-id="d4fe4-104">La finestra di dialogo **Visualizzatore file di log** in [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="d4fe4-104">The **Log File Viewer** dialog box in [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)].</span></span> <span data-ttu-id="d4fe4-105">Nella finestra di dialogo **Visualizzatore file di log** sono disponibili opzioni per l'esportazione, l'applicazione di filtri e l'esecuzione di ricerche nel log.</span><span class="sxs-lookup"><span data-stu-id="d4fe4-105">The **Log File Viewer** dialog box includes options to export, filter, and search the log.</span></span> <span data-ttu-id="d4fe4-106">Per altre informazioni sulle opzioni della finestra di dialogo **Visualizzatore file di log**, vedere [Guida sensibile al contesto del Visualizzatore file di log](../relational-databases/logs/log-file-viewer-f1-help.md).</span><span class="sxs-lookup"><span data-stu-id="d4fe4-106">For more information about the options in the **Log File Viewer**, see [Log File Viewer F1 Help](../relational-databases/logs/log-file-viewer-f1-help.md).</span></span>  
  
-   <span data-ttu-id="d4fe4-107">Visualizzatore eventi di Windows.</span><span class="sxs-lookup"><span data-stu-id="d4fe4-107">The Windows Event Viewer.</span></span>  
  
 <span data-ttu-id="d4fe4-108">Per descrizioni degli eventi registrati dal servizio [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] , vedere [Eventi registrati dal servizio Integration Services](service/events-logged-by-the-integration-services-service.md).</span><span class="sxs-lookup"><span data-stu-id="d4fe4-108">For descriptions of the events logged by the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] service, see [Events Logged by the Integration Services Service](service/events-logged-by-the-integration-services-service.md).</span></span>  
  
### <a name="to-view-service-events-for-integration-services-in-sql-server-management-studio"></a><span data-ttu-id="d4fe4-109">Per visualizzare gli eventi del servizio per Integration Services in SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="d4fe4-109">To view service events for Integration Services in SQL Server Management Studio</span></span>  
  
1.  <span data-ttu-id="d4fe4-110">Aprire [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="d4fe4-110">Open [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)].</span></span>  
  
2.  <span data-ttu-id="d4fe4-111">Scegliere **Connetti Esplora oggetti** dal menu **File**.</span><span class="sxs-lookup"><span data-stu-id="d4fe4-111">On the **File** menu, click **Connect Object Explorer**.</span></span>  
  
3.  <span data-ttu-id="d4fe4-112">Nella finestra di dialogo **Connetti al server** selezionare il tipo di server [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] , selezionare o individuare il server a cui connettersi e quindi fare clic su **Connetti**.</span><span class="sxs-lookup"><span data-stu-id="d4fe4-112">In the **Connect to Server** dialog box, select the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] server type, select or locate the server to connect to, and then click **Connect**.</span></span>  
  
4.  <span data-ttu-id="d4fe4-113">In Esplora oggetti fare clic con il pulsante destro del mouse su [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] e quindi scegliere **Visualizza log**.</span><span class="sxs-lookup"><span data-stu-id="d4fe4-113">In Object Explorer, right-click [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] and click **View Logs**.</span></span>  
  
5.  <span data-ttu-id="d4fe4-114">Per visualizzare gli eventi di [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] , selezionare **SQL Server Integration Services**.</span><span class="sxs-lookup"><span data-stu-id="d4fe4-114">To view [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] events, select **SQL Server Integration Services**.</span></span> <span data-ttu-id="d4fe4-115">L'opzione **Eventi NT** , selezionata automaticamente, viene deselezionata quando si seleziona l'opzione **SQL Server Integration Services** .</span><span class="sxs-lookup"><span data-stu-id="d4fe4-115">The **NT Events** option is automatically selected and cleared with the **SQL Server Integration Services** option.</span></span>  
  
### <a name="to-view-service-events-for-integration-services-in-windows-event-viewer"></a><span data-ttu-id="d4fe4-116">Per visualizzare gli eventi del servizio per Integration Services in Windows nel Visualizzatore eventi</span><span class="sxs-lookup"><span data-stu-id="d4fe4-116">To view service events for Integration Services in Windows Event Viewer</span></span>  
  
1.  <span data-ttu-id="d4fe4-117">Nel **Pannello di controllo**fare clic su **Strumenti di amministrazione**nella visualizzazione classica oppure su **Prestazioni e manutenzione** e quindi su **Strumenti di amministrazione**nella visualizzazione per categorie.</span><span class="sxs-lookup"><span data-stu-id="d4fe4-117">In **Control Panel**, if you are using Classic View, click **Administrative Tools**, or, if you are using Category View, click **Performance and Maintenance** and then click **Administrative Tools**.</span></span>  
  
2.  <span data-ttu-id="d4fe4-118">Fare clic su **Visualizzatore eventi**.</span><span class="sxs-lookup"><span data-stu-id="d4fe4-118">Click **Event Viewer**.</span></span>  
  
3.  <span data-ttu-id="d4fe4-119">Nella finestra di dialogo **Visualizzatore eventi** fare clic su **Applicazione**.</span><span class="sxs-lookup"><span data-stu-id="d4fe4-119">In the **Event Viewer** dialog box, click **Application**.</span></span>  
  
4.  <span data-ttu-id="d4fe4-120">Nello snap-in **Applicazione** individuare nella colonna **Origine** la voce con valore **SQLISService**, fare clic con il pulsante destro del mouse sulla voce e quindi scegliere **Proprietà**.</span><span class="sxs-lookup"><span data-stu-id="d4fe4-120">In the **Application** snap-in, locate an entry in the **Source** column that has the value **SQLISService**, right-click the entry, and then click **Properties**.</span></span>  
  
5.  <span data-ttu-id="d4fe4-121">Facoltativamente, fare clic sulla freccia SU o freccia GIÙ per visualizzare l'evento precedente o successivo.</span><span class="sxs-lookup"><span data-stu-id="d4fe4-121">Optionally, click the up or down arrow to show the previous or next event.</span></span>  
  
6.  <span data-ttu-id="d4fe4-122">Facoltativamente, fare clic sul pulsante Copia negli Appunti per copiare le informazioni sugli eventi.</span><span class="sxs-lookup"><span data-stu-id="d4fe4-122">Optionally, click the Copy to Clipboard icon to copy the event information.</span></span>  
  
7.  <span data-ttu-id="d4fe4-123">Impostare la visualizzazione dei dati degli eventi in base a byte o parole.</span><span class="sxs-lookup"><span data-stu-id="d4fe4-123">Choose to display event data using bytes or words.</span></span>  
  
8.  <span data-ttu-id="d4fe4-124">Fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="d4fe4-124">Click **OK**.</span></span>  
  
9. <span data-ttu-id="d4fe4-125">Scegliere **Esci** dal menu **File** per chiudere la finestra di dialogo **Visualizzatore eventi** .</span><span class="sxs-lookup"><span data-stu-id="d4fe4-125">On the **File** menu, click **Exit** to close the **Event Viewer** dialog box.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d4fe4-126">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d4fe4-126">See Also</span></span>  
 <span data-ttu-id="d4fe4-127">[Gestire il servizio Integration Services](../../2014/integration-services/manage-the-integration-services-service.md) </span><span class="sxs-lookup"><span data-stu-id="d4fe4-127">[Manage the Integration Services Service](../../2014/integration-services/manage-the-integration-services-service.md) </span></span>  
 [<span data-ttu-id="d4fe4-128">Aggiunta di un registro per i contatori delle prestazioni del flusso di dati</span><span class="sxs-lookup"><span data-stu-id="d4fe4-128">Add a Log for Data Flow Performance Counters</span></span>](performance/performance-counters.md)  
  
  
