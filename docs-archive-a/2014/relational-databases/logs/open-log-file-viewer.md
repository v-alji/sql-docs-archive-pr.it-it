---
title: Aprire il Visualizzatore File di Log | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- Log File Viewer, opening
ms.assetid: a86b89cb-0432-4648-895a-05ecc5450e45
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 269ff10275f7463a8a85249a2a0f06fe9bde364a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87627239"
---
# <a name="open-log-file-viewer"></a><span data-ttu-id="bc2ac-102">Aprire il visualizzatore file di log</span><span class="sxs-lookup"><span data-stu-id="bc2ac-102">Open Log File Viewer</span></span>
  <span data-ttu-id="bc2ac-103">È possibile utilizzare il Visualizzatore file di log in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] per accedere alle informazioni relative a errori ed eventi acquisite nei log seguenti:</span><span class="sxs-lookup"><span data-stu-id="bc2ac-103">You can use Log File Viewer in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] to access information about errors and events that are captured in the following logs:</span></span>  
  
-   <span data-ttu-id="bc2ac-104">Raccolta controlli</span><span class="sxs-lookup"><span data-stu-id="bc2ac-104">Audit Collection</span></span>  
  
-   <span data-ttu-id="bc2ac-105">Raccolta di dati</span><span class="sxs-lookup"><span data-stu-id="bc2ac-105">Data Collection</span></span>  
  
-   <span data-ttu-id="bc2ac-106">Posta elettronica database</span><span class="sxs-lookup"><span data-stu-id="bc2ac-106">Database Mail</span></span>  
  
-   <span data-ttu-id="bc2ac-107">Cronologia processi</span><span class="sxs-lookup"><span data-stu-id="bc2ac-107">Job History</span></span>  
  
-   <span data-ttu-id="bc2ac-108">SQL Server</span><span class="sxs-lookup"><span data-stu-id="bc2ac-108">SQL Server</span></span>  
  
-   <span data-ttu-id="bc2ac-109">SQL Server Agent</span><span class="sxs-lookup"><span data-stu-id="bc2ac-109">SQL Server Agent</span></span>  
  
-   <span data-ttu-id="bc2ac-110">Eventi di Windows. È possibile accedere a tali eventi anche dal Visualizzatore eventi.</span><span class="sxs-lookup"><span data-stu-id="bc2ac-110">Windows events (These Windows events can also be accessed from Event Viewer.)</span></span>  
  
 <span data-ttu-id="bc2ac-111">A partire da [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)], è possibile utilizzare Server registrati per visualizzare file di log di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] da istanze locali o remote di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="bc2ac-111">Beginning in [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)], you can use Registered Servers to view [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] log files from local or remote instances of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="bc2ac-112">Usando Server registrati, è possibile visualizzare i file di log quando le istanze sono online o offline.</span><span class="sxs-lookup"><span data-stu-id="bc2ac-112">By using Registered Servers, you can view the log files when the instances are either online or offline.</span></span> <span data-ttu-id="bc2ac-113">Per altre informazioni sull'accesso online, vedere la procedura "Per visualizzare file di log online dalla finestra Server registrati" più avanti in questo argomento.</span><span class="sxs-lookup"><span data-stu-id="bc2ac-113">For more information about online access, see the procedure "To view online log files from Registered Servers" later in this topic.</span></span> <span data-ttu-id="bc2ac-114">Per altre informazioni su come accedere offline a file di log di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , vedere [Visualizzare file di log offline](view-offline-log-files.md).</span><span class="sxs-lookup"><span data-stu-id="bc2ac-114">For more information about how to access offline [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] log files, see [View Offline Log Files](view-offline-log-files.md).</span></span>  
  
 <span data-ttu-id="bc2ac-115">È possibile aprire il Visualizzatore file di log in diversi modi, a seconda delle informazioni che si desidera visualizzare.</span><span class="sxs-lookup"><span data-stu-id="bc2ac-115">You can open Log File Viewer in several ways, depending on the information that you want to view.</span></span>  
  
##  <a name="permissions"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="bc2ac-116">Autorizzazioni</span><span class="sxs-lookup"><span data-stu-id="bc2ac-116">Permissions</span></span>  
 <span data-ttu-id="bc2ac-117">Per accedere ai file di log per le istanze di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] online, è necessaria l'appartenenza al ruolo predefinito del server securityadmin.</span><span class="sxs-lookup"><span data-stu-id="bc2ac-117">To access log files for instances of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] that are online, this requires membership in the securityadmin fixed server role.</span></span>  
  
 <span data-ttu-id="bc2ac-118">Per accedere a file di log per istanze di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] offline, è necessario avere accesso in lettura sia allo spazio dei nomi WMI **Root\Microsoft\SqlServer\ComputerManagement10** sia alla cartella in cui sono archiviati i file di log.</span><span class="sxs-lookup"><span data-stu-id="bc2ac-118">To access log files for instances of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] that are offline, you must have read access to both the **Root\Microsoft\SqlServer\ComputerManagement10** WMI namespace, and to the folder where the log files are stored.</span></span> <span data-ttu-id="bc2ac-119">Per altre informazioni, vedere la sezione Autorizzazioni dell'argomento [Visualizzare file di log offline](view-offline-log-files.md).</span><span class="sxs-lookup"><span data-stu-id="bc2ac-119">For more information, see the Security section of the topic [View Offline Log Files](view-offline-log-files.md).</span></span>  
  
### <a name="security"></a><span data-ttu-id="bc2ac-120">Sicurezza</span><span class="sxs-lookup"><span data-stu-id="bc2ac-120">Security</span></span>  
 <span data-ttu-id="bc2ac-121">È necessaria l'appartenenza al ruolo predefinito del server securityadmin.</span><span class="sxs-lookup"><span data-stu-id="bc2ac-121">Requires membership in the securityadmin fixed server role.</span></span>  
  
### <a name="view-log-files"></a><span data-ttu-id="bc2ac-122">Visualizzare file di log</span><span class="sxs-lookup"><span data-stu-id="bc2ac-122">View Log Files</span></span>  
  
##### <a name="to-view-logs-that-are-related-to-general-sql-server-activity"></a><span data-ttu-id="bc2ac-123">Per visualizzare log relativi all'attività generale di SQL Server</span><span class="sxs-lookup"><span data-stu-id="bc2ac-123">To view logs that are related to general SQL Server activity</span></span>  
  
1.  <span data-ttu-id="bc2ac-124">In Esplora oggetti espandere **Gestione**.</span><span class="sxs-lookup"><span data-stu-id="bc2ac-124">In Object Explorer, expand **Management**.</span></span>  
  
2.  <span data-ttu-id="bc2ac-125">Effettuare una delle operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="bc2ac-125">Do either of the following:</span></span>  
  
    -   <span data-ttu-id="bc2ac-126">Fare clic con il pulsante destro del mouse su **Log di SQL Server**, scegliere **Visualizza**, quindi fare clic su **Log di SQL Server** o su **Log di SQL Server e di Windows**.</span><span class="sxs-lookup"><span data-stu-id="bc2ac-126">Right-click **SQL Server Logs**, point to **View**, and then click either **SQL Server Log** or **SQL Server and Windows Log**.</span></span>  
  
    -   <span data-ttu-id="bc2ac-127">Espandere **Log di SQL Server**, fare clic con il pulsante destro del mouse su un file di log, quindi scegliere **Visualizza log di SQL Server**.</span><span class="sxs-lookup"><span data-stu-id="bc2ac-127">Expand **SQL Server Logs**, right-click any log file, and then click **View SQL Server Log**.</span></span> <span data-ttu-id="bc2ac-128">È anche possibile fare doppio clic su un file di log.</span><span class="sxs-lookup"><span data-stu-id="bc2ac-128">You can also double-click any log file.</span></span>  
  
     <span data-ttu-id="bc2ac-129">I log includono **Posta elettronica database**, **SQL Server**, **SQL Server Agent**e **Windows NT**.</span><span class="sxs-lookup"><span data-stu-id="bc2ac-129">The logs include **Database Mail**, **SQL Server**, **SQL Server Agent**, and **Windows NT**.</span></span>  
  
##### <a name="to-view-logs-that-are-related-to-jobs"></a><span data-ttu-id="bc2ac-130">Per visualizzare log relativi ai processi</span><span class="sxs-lookup"><span data-stu-id="bc2ac-130">To view logs that are related to jobs</span></span>  
  
-   <span data-ttu-id="bc2ac-131">In Esplora oggetti espandere **SQL Server Agent**, fare clic con il pulsante destro del mouse su **Processi**, quindi scegliere **Visualizza cronologia**.</span><span class="sxs-lookup"><span data-stu-id="bc2ac-131">In Object Explorer, expand **SQL Server Agent**, right-click **Jobs**, and then click **View History**.</span></span>  
  
     <span data-ttu-id="bc2ac-132">I log includono **Posta elettronica database**, **Cronologia processi**e **SQL Server Agent**.</span><span class="sxs-lookup"><span data-stu-id="bc2ac-132">The logs include **Database Mail**, **Job History**, and **SQL Server Agent**.</span></span>  
  
##### <a name="to-view-logs-that-are-related-to-maintenance-plans"></a><span data-ttu-id="bc2ac-133">Per visualizzare log relativi ai piani di manutenzione</span><span class="sxs-lookup"><span data-stu-id="bc2ac-133">To view logs that are related to maintenance plans</span></span>  
  
-   <span data-ttu-id="bc2ac-134">In Esplora oggetti espandere **Gestione**, fare clic con il pulsante destro del mouse su **Piani di manutenzione**, quindi scegliere **Visualizza cronologia**.</span><span class="sxs-lookup"><span data-stu-id="bc2ac-134">In Object Explorer, expand **Management**, right-click **Maintenance Plans**, and then click **View History**.</span></span>  
  
     <span data-ttu-id="bc2ac-135">I log includono **Posta elettronica database**, **Cronologia processo**, **Piani di manutenzione**, **Piani di manutenzione remoti**e **SQL Server Agent**.</span><span class="sxs-lookup"><span data-stu-id="bc2ac-135">The logs include **Database Mail**, **Job History**, **Maintenance Plans**, **Remote Maintenance Plans**, and **SQL Server Agent**.</span></span>  
  
##### <a name="to-view-logs-that-are-related-to-data-collection"></a><span data-ttu-id="bc2ac-136">Per visualizzare log relativi alla raccolta dati</span><span class="sxs-lookup"><span data-stu-id="bc2ac-136">To view logs that are related to Data Collection</span></span>  
  
-   <span data-ttu-id="bc2ac-137">In Esplora oggetti espandere **Gestione**, fare clic con il pulsante destro del mouse su **Raccolta dati**, quindi scegliere **Visualizza log**.</span><span class="sxs-lookup"><span data-stu-id="bc2ac-137">In Object Explorer, expand **Management**, right-click **Data Collection**, and then click **View Logs**.</span></span>  
  
     <span data-ttu-id="bc2ac-138">I log includono **Raccolta dati**, **Cronologia processo**e **SQL Server Agent**.</span><span class="sxs-lookup"><span data-stu-id="bc2ac-138">The logs include **Data Collection**, **Job History**, and **SQL Server Agent**.</span></span>  
  
##### <a name="to-view-logs-that-are-related-to-database-mail"></a><span data-ttu-id="bc2ac-139">Per visualizzare log relativi a Posta elettronica database</span><span class="sxs-lookup"><span data-stu-id="bc2ac-139">To view logs that are related to Database Mail</span></span>  
  
-   <span data-ttu-id="bc2ac-140">In Esplora oggetti espandere **Gestione**, fare clic con il pulsante destro del mouse su **Posta elettronica database**, quindi scegliere **Visualizza log Posta elettronica database**.</span><span class="sxs-lookup"><span data-stu-id="bc2ac-140">In Object Explorer, expand **Management**, right-click **Database Mail**, and then click **View Database Mail Log**.</span></span>  
  
     <span data-ttu-id="bc2ac-141">I log includono **Posta elettronica database, Cronologia processo**, **Piani di manutenzione**, **Piani di manutenzione remoti**, **SQL Server**, **SQL Server Agent**e **Windows NT**.</span><span class="sxs-lookup"><span data-stu-id="bc2ac-141">The logs include **Database Mail, Job History**, **Maintenance Plans**, **Remote Maintenance Plans**, **SQL Server**, **SQL Server Agent**, and **Windows NT**.</span></span>  
  
##### <a name="to-view-logs-that-are-related-to-audits-collections"></a><span data-ttu-id="bc2ac-142">Per visualizzare log relativi alle raccolte di controlli</span><span class="sxs-lookup"><span data-stu-id="bc2ac-142">To view logs that are related to audits collections</span></span>  
  
-   <span data-ttu-id="bc2ac-143">In Esplora oggetti espandere **Sicurezza**, espandere **Controlli**, fare clic con il pulsante destro del mouse su un controllo, quindi scegliere **Visualizza log di controllo**.</span><span class="sxs-lookup"><span data-stu-id="bc2ac-143">In Object Explorer, expand **Security**, expand **Audits**, right-click an audit, and then click **View Audit Logs**.</span></span>  
  
     <span data-ttu-id="bc2ac-144">I log includono **Raccolta controlli** e **Windows NT**.</span><span class="sxs-lookup"><span data-stu-id="bc2ac-144">The logs include **Audit Collection** and **Windows NT**.</span></span>  
  
##### <a name="to-view-logs-that-are-related-to-audits-collections"></a><span data-ttu-id="bc2ac-145">Per visualizzare log relativi alle raccolte di controlli</span><span class="sxs-lookup"><span data-stu-id="bc2ac-145">To view logs that are related to audits collections</span></span>  
  
-   <span data-ttu-id="bc2ac-146">In Esplora oggetti espandere **Sicurezza**, espandere **Controlli**, fare clic con il pulsante destro del mouse su un controllo, quindi scegliere **Visualizza log di controllo**.</span><span class="sxs-lookup"><span data-stu-id="bc2ac-146">In Object Explorer, expand **Security**, expand **Audits**, right-click an audit, and then click **View Audit Logs**.</span></span>  
  
     <span data-ttu-id="bc2ac-147">I log includono **Raccolta controlli** e **Windows NT**.</span><span class="sxs-lookup"><span data-stu-id="bc2ac-147">The logs include **Audit Collection** and **Windows NT**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bc2ac-148">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="bc2ac-148">See Also</span></span>  
 <span data-ttu-id="bc2ac-149">[Visualizzatore file di log](log-file-viewer.md) </span><span class="sxs-lookup"><span data-stu-id="bc2ac-149">[Log File Viewer](log-file-viewer.md) </span></span>  
 <span data-ttu-id="bc2ac-150">[SQL Server Audit &#40;Database Engine&#41;](../security/auditing/sql-server-audit-database-engine.md) </span><span class="sxs-lookup"><span data-stu-id="bc2ac-150">[SQL Server Audit &#40;Database Engine&#41;](../security/auditing/sql-server-audit-database-engine.md) </span></span>  
 [<span data-ttu-id="bc2ac-151">Visualizzare file di log offline</span><span class="sxs-lookup"><span data-stu-id="bc2ac-151">View Offline Log Files</span></span>](view-offline-log-files.md)  
  
  
