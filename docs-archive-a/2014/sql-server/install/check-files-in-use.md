---
title: Controllare i file in uso | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
ms.assetid: ccd65867-d4c0-43b2-8361-7fd41c6f79ac
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: 51505b0dece146b7f6fcdf982e6f88a5715357e1
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87628218"
---
# <a name="check-files-in-use"></a><span data-ttu-id="d0a76-102">Controllo file in uso</span><span class="sxs-lookup"><span data-stu-id="d0a76-102">Check Files In Use</span></span>
  <span data-ttu-id="d0a76-103">Per evitare il riavvio di Windows dopo l'installazione degli aggiornamenti di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , utilizzare la pagina Controllo file in uso per identificare i processi che bloccano i file necessari per il programma di installazione degli aggiornamenti di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="d0a76-103">To avoid restarting Windows after you install [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] updates, use the Check Files in Use page to identify processes that are locking files required by the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] update Setup program.</span></span>  
  
 <span data-ttu-id="d0a76-104">Arrestare tutti i servizi e le applicazioni che si connettono alle istanze di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] da aggiornare,</span><span class="sxs-lookup"><span data-stu-id="d0a76-104">Stop all applications and services that make connections to the instances of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] that are being updated.</span></span> <span data-ttu-id="d0a76-105">Arrestare anche [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] e [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="d0a76-105">This includes stopping [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] and [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)].</span></span>  
  
 <span data-ttu-id="d0a76-106">Se vengono rilevati file bloccati durante l'installazione, potrebbe essere necessario riavviare il computer al termine dell'installazione.</span><span class="sxs-lookup"><span data-stu-id="d0a76-106">If Setup determines that files are locked during installation, you might have to restart your computer after installation is completed.</span></span> <span data-ttu-id="d0a76-107">In questo caso, verrà richiesto di riavviare il computer.</span><span class="sxs-lookup"><span data-stu-id="d0a76-107">If necessary, Setup prompts you to restart your computer.</span></span> <span data-ttu-id="d0a76-108">Se durante l'installazione degli aggiornamenti è necessario arrestare un determinato servizio, al termine dell'installazione tale servizio verrà riavviato automaticamente.</span><span class="sxs-lookup"><span data-stu-id="d0a76-108">If the Setup program must stop a service during installation, it will restart the service after installation is completed.</span></span>  
  
 <span data-ttu-id="d0a76-109">Per eliminare la necessità di riavviare il computer dopo l'installazione, verrà visualizzato un elenco dei processi che bloccano i file necessari.</span><span class="sxs-lookup"><span data-stu-id="d0a76-109">To eliminate the requirement to restart your computer after installation, Setup displays a list of processes that are locking files.</span></span> <span data-ttu-id="d0a76-110">Arrestare o terminare i processi e le applicazioni elencati.</span><span class="sxs-lookup"><span data-stu-id="d0a76-110">Stop or end the processes and applications in the list.</span></span> <span data-ttu-id="d0a76-111">Fare clic su **Aggiorna controllo** per ripetere il controllo.</span><span class="sxs-lookup"><span data-stu-id="d0a76-111">Then click **Refresh check** to rerun the check.</span></span> <span data-ttu-id="d0a76-112">Per arrestare un controllo in esecuzione, fare clic su **Arresta controllo** .</span><span class="sxs-lookup"><span data-stu-id="d0a76-112">Click **Stop check** to end a check that is running.</span></span> <span data-ttu-id="d0a76-113">Se non vengono rilevati file bloccati, la tabella risulta vuota.</span><span class="sxs-lookup"><span data-stu-id="d0a76-113">If locked files are not found, the table is empty.</span></span> <span data-ttu-id="d0a76-114">Dopo la chiusura o l'arresto di tutti i processi bloccati, fare clic su **Avanti** per continuare.</span><span class="sxs-lookup"><span data-stu-id="d0a76-114">When all locked processes have been closed or stopped, click **Next** to continue.</span></span>  
  
 <span data-ttu-id="d0a76-115">Le informazioni verranno registrate nei file di log.</span><span class="sxs-lookup"><span data-stu-id="d0a76-115">Setup logs the information in the log files.</span></span> <span data-ttu-id="d0a76-116">Per altre informazioni sulla visualizzazione dei file di log, vedere [Visualizzare e leggere i file di log del programma di installazione di SQL Server](../../database-engine/install-windows/view-and-read-sql-server-setup-log-files.md) e [Procedura: Lettura di un file di log del programma di installazione di SQL Server](https://go.microsoft.com/fwlink/?LinkID=134490).</span><span class="sxs-lookup"><span data-stu-id="d0a76-116">For more information about how to view the log files, see [View and Read SQL Server Setup Log Files](../../database-engine/install-windows/view-and-read-sql-server-setup-log-files.md) and [How to: Read a SQL Server Setup Log File](https://go.microsoft.com/fwlink/?LinkID=134490).</span></span>  
  
 <span data-ttu-id="d0a76-117">Nel file di log sono incluse le seguenti informazioni:</span><span class="sxs-lookup"><span data-stu-id="d0a76-117">The following information is included in the log file:</span></span>  
  
-   <span data-ttu-id="d0a76-118">Nome del processo</span><span class="sxs-lookup"><span data-stu-id="d0a76-118">Name of the process</span></span>  
  
-   <span data-ttu-id="d0a76-119">Nome della caratteristica di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d0a76-119">Name of the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] feature</span></span>  
  
-   <span data-ttu-id="d0a76-120">Tipo di processo</span><span class="sxs-lookup"><span data-stu-id="d0a76-120">Process type</span></span>  
  
-   <span data-ttu-id="d0a76-121">Account con il quale viene eseguito il processo</span><span class="sxs-lookup"><span data-stu-id="d0a76-121">Account under which the process is running</span></span>  
  
-   <span data-ttu-id="d0a76-122">ID di processo</span><span class="sxs-lookup"><span data-stu-id="d0a76-122">Process ID</span></span>  
  
-   <span data-ttu-id="d0a76-123">Nome del file bloccato</span><span class="sxs-lookup"><span data-stu-id="d0a76-123">Name of the file that is locked</span></span>  
  
## <a name="ui-element-list"></a><span data-ttu-id="d0a76-124">Elenco di elementi dell'interfaccia utente</span><span class="sxs-lookup"><span data-stu-id="d0a76-124">UI element list</span></span>  
  
|<span data-ttu-id="d0a76-125">Nome</span><span class="sxs-lookup"><span data-stu-id="d0a76-125">Name</span></span>|<span data-ttu-id="d0a76-126">Descrizione</span><span class="sxs-lookup"><span data-stu-id="d0a76-126">Description</span></span>|  
|----------|-----------------|  
|<span data-ttu-id="d0a76-127">Process</span><span class="sxs-lookup"><span data-stu-id="d0a76-127">Process</span></span>|<span data-ttu-id="d0a76-128">Indica il nome completo del processo che utilizza i file da aggiornare.</span><span class="sxs-lookup"><span data-stu-id="d0a76-128">Displays the full name of the process that is using the files to be updated.</span></span>|  
|<span data-ttu-id="d0a76-129">Type</span><span class="sxs-lookup"><span data-stu-id="d0a76-129">Type</span></span>|<span data-ttu-id="d0a76-130">Indica il tipo di processo.</span><span class="sxs-lookup"><span data-stu-id="d0a76-130">Displays the type of process.</span></span>|  
|<span data-ttu-id="d0a76-131">Account</span><span class="sxs-lookup"><span data-stu-id="d0a76-131">Account</span></span>|<span data-ttu-id="d0a76-132">Indica l'account con il quale viene eseguito il processo.</span><span class="sxs-lookup"><span data-stu-id="d0a76-132">Displays the account under which the process is running.</span></span>|  
|<span data-ttu-id="d0a76-133">ID di processo</span><span class="sxs-lookup"><span data-stu-id="d0a76-133">Process ID</span></span>|<span data-ttu-id="d0a76-134">Indica l'ID del processo.</span><span class="sxs-lookup"><span data-stu-id="d0a76-134">Displays the process ID.</span></span>|  
  
  
