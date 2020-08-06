---
title: Configurazione delle opzioni di avvio del server (Gestione configurazione SQL Server) | Microsoft Docs
ms.custom: ''
ms.date: 01/07/2016
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
helpviewer_keywords:
- parameters [SQL Server], startup options
- SQL Server, startup options
- single-user mode [SQL Server], starting in
- startup options [SQL Server]
- SQL Server services, setting startup options
ms.assetid: 7a94643c-6460-4baf-bb31-0cb99eaf970d
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 405a96208c774a6326a69cf9826a14ca3552eae1
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87713476"
---
# <a name="configure-server-startup-options-sql-server-configuration-manager"></a><span data-ttu-id="d6550-102">Configurazione delle opzioni di avvio del server (Gestione configurazione SQL Server)</span><span class="sxs-lookup"><span data-stu-id="d6550-102">Configure Server Startup Options (SQL Server Configuration Manager)</span></span>
  <span data-ttu-id="d6550-103">Questo argomento illustra come configurare le opzioni di avvio da usare ogni volta che il [!INCLUDE[ssDE](../../includes/ssde-md.md)] viene avviato in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] tramite [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Configuration Manager.</span><span class="sxs-lookup"><span data-stu-id="d6550-103">This topic describes how to configure startup options that will be used every time the [!INCLUDE[ssDE](../../includes/ssde-md.md)] starts in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Configuration Manager.</span></span> <span data-ttu-id="d6550-104">Per un elenco delle opzioni di avvio, vedere [Opzioni di avvio del servizio del motore di database](database-engine-service-startup-options.md).</span><span class="sxs-lookup"><span data-stu-id="d6550-104">For a list of startup options, see [Database Engine Service Startup Options](database-engine-service-startup-options.md).</span></span>  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="d6550-105">Prima di iniziare</span><span class="sxs-lookup"><span data-stu-id="d6550-105">Before You Begin</span></span>  
  
### <a name="limitations-and-restrictions"></a><span data-ttu-id="d6550-106">Limitazioni e restrizioni</span><span class="sxs-lookup"><span data-stu-id="d6550-106">Limitations and Restrictions</span></span>  
 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="d6550-107">, i parametri di avvio vengono scritti nel Registro di sistema</span><span class="sxs-lookup"><span data-stu-id="d6550-107">Configuration Manager writes startup parameters to the registry.</span></span> <span data-ttu-id="d6550-108">e vengono applicati al successivo avvio del [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="d6550-108">They take effect upon the next startup of the [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
 <span data-ttu-id="d6550-109">In un cluster le modifiche devono essere eseguite sul server attivo quando [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] è online e verranno applicate al riavvio di [!INCLUDE[ssDE](../../includes/ssde-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="d6550-109">On a cluster, changes must be made on the active server when [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] is online, and will take effect when the [!INCLUDE[ssDE](../../includes/ssde-md.md)] is restarted.</span></span> <span data-ttu-id="d6550-110">L'aggiornamento delle opzioni di avvio nel Registro di sistema per l'altro nodo verrà eseguito al successivo failover.</span><span class="sxs-lookup"><span data-stu-id="d6550-110">The registry update of the startup options on the other node will occur upon the next failover.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="d6550-111">Sicurezza</span><span class="sxs-lookup"><span data-stu-id="d6550-111">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="d6550-112">Autorizzazioni</span><span class="sxs-lookup"><span data-stu-id="d6550-112">Permissions</span></span>  
 <span data-ttu-id="d6550-113">La configurazione delle opzioni di avvio del server è limitata a utenti che possono modificare le voci correlate nel Registro di sistema.</span><span class="sxs-lookup"><span data-stu-id="d6550-113">Configuring server startup options is restricted to users who can change the related entries in the registry.</span></span> <span data-ttu-id="d6550-114">Sono inclusi gli utenti indicati di seguito.</span><span class="sxs-lookup"><span data-stu-id="d6550-114">This includes the following users.</span></span>  
  
-   <span data-ttu-id="d6550-115">Membri del gruppo Administrators locale.</span><span class="sxs-lookup"><span data-stu-id="d6550-115">Members of the local administrators group.</span></span>  
  
-   <span data-ttu-id="d6550-116">Account di dominio utilizzato da [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], se il [!INCLUDE[ssDE](../../includes/ssde-md.md)] è configurato per essere in esecuzione in un account di dominio.</span><span class="sxs-lookup"><span data-stu-id="d6550-116">The domain account that is used by [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], if the [!INCLUDE[ssDE](../../includes/ssde-md.md)] is configured to run under a domain account.</span></span>  
  
##  <a name="using-sql-server-configuration-manager"></a><a name="SSMSProcedure"></a> <span data-ttu-id="d6550-117">Utilizzo di Gestione configurazione SQL Server</span><span class="sxs-lookup"><span data-stu-id="d6550-117">Using SQL Server Configuration Manager</span></span>  
  
#### <a name="to-configure-startup-options"></a><span data-ttu-id="d6550-118">Per configurare le opzioni di avvio</span><span class="sxs-lookup"><span data-stu-id="d6550-118">To configure startup options</span></span>  
  
1.  <span data-ttu-id="d6550-119">In Gestione configurazione [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] fare clic su **Servizi di SQL Server**.</span><span class="sxs-lookup"><span data-stu-id="d6550-119">In [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Configuration Manager, click **SQL Server Services**.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="d6550-120">Poiché Gestione configurazione [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] è uno snap-in per il programma [!INCLUDE[msCoName](../../includes/msconame-md.md)] Management Console e non un programma autonomo, Gestione configurazione [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] non viene visualizzato come applicazione nelle versioni più recenti di Windows.</span><span class="sxs-lookup"><span data-stu-id="d6550-120">Because [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Configuration Manager is a snap-in for the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Management Console program and not a stand-alone program, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Configuration Manager does not appear as an application in newer versions of Windows.</span></span>  
    >   
    >  -   <span data-ttu-id="d6550-121">**Windows 10**:</span><span class="sxs-lookup"><span data-stu-id="d6550-121">**Windows 10**:</span></span>  
    >          <span data-ttu-id="d6550-122">Per aprire [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Configuration Manager, nella **pagina iniziale**digitare SQLServerManager12. msc (per [!INCLUDE[ssSQL14](../../includes/sssql14-md.md)] ).</span><span class="sxs-lookup"><span data-stu-id="d6550-122">To open [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Configuration Manager, on the **Start Page**, type SQLServerManager12.msc (for [!INCLUDE[ssSQL14](../../includes/sssql14-md.md)]).</span></span> <span data-ttu-id="d6550-123">Per le versioni precedenti di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , sostituire 12 con un numero inferiore.</span><span class="sxs-lookup"><span data-stu-id="d6550-123">For previous versions of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] replace 12 with a smaller number.</span></span> <span data-ttu-id="d6550-124">Se si fa clic su SQLServerManager12.msc, viene aperto Gestione configurazione.</span><span class="sxs-lookup"><span data-stu-id="d6550-124">Clicking SQLServerManager12.msc opens the Configuration Manager.</span></span> <span data-ttu-id="d6550-125">Per aggiungere la Configuration Manager alla pagina iniziale o alla barra delle applicazioni, fare clic con il pulsante destro del mouse su SQLServerManager12. msc, quindi scegliere **Apri percorso file**.</span><span class="sxs-lookup"><span data-stu-id="d6550-125">To pin the Configuration Manager to the Start Page or Task Bar, right-click SQLServerManager12.msc, and then click **Open file location**.</span></span> <span data-ttu-id="d6550-126">In Esplora file di Windows fare clic con il pulsante destro del mouse su SQLServerManager12. msc, quindi scegliere **Aggiungi a Start** o **Aggiungi alla barra delle applicazioni**.</span><span class="sxs-lookup"><span data-stu-id="d6550-126">In the Windows File Explorer, right-click SQLServerManager12.msc, and then click **Pin to Start** or **Pin to taskbar**.</span></span>  
    > -   <span data-ttu-id="d6550-127">**Windows 8**:</span><span class="sxs-lookup"><span data-stu-id="d6550-127">**Windows 8**:</span></span>  
    >          <span data-ttu-id="d6550-128">Per aprire [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Configuration Manager, nell'accesso alla **ricerca** , in **app**digitare **SQLServerManager \<version> . msc** , ad esempio `SQLServerManager12.msc` , quindi premere **invio**.</span><span class="sxs-lookup"><span data-stu-id="d6550-128">To open [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Configuration Manager, in the **Search** charm, under **Apps**, type **SQLServerManager\<version>.msc** such as `SQLServerManager12.msc`, and then press **Enter**.</span></span>  
  
2.  <span data-ttu-id="d6550-129">Nel riquadro destro fare clic con il pulsante destro del mouse su **SQL Server (***<instance_name>***)**, quindi scegliere **proprietà**.</span><span class="sxs-lookup"><span data-stu-id="d6550-129">In the right pane, right-click **SQL Server (***<instance_name>***)**, and then click **Properties**.</span></span>  
  
3.  <span data-ttu-id="d6550-130">Nella scheda **Parametri di avvio** della casella **Specificare un parametro di avvio** digitare il parametro e quindi fare clic su **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="d6550-130">On the **Startup Parameters** tab, in the **Specify a startup parameter** box, type the parameter, and then click **Add**.</span></span>  
  
     <span data-ttu-id="d6550-131">Ad esempio, per avviare in modalità utente singolo, digitare `-m` nella casella **specificare un parametro di avvio** e quindi fare clic su **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="d6550-131">For example, to start in single-user mode, type `-m` in the **Specify a startup parameter** box and then click **Add**.</span></span> <span data-ttu-id="d6550-132">Al riavvio di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] in modalità utente singolo, arrestare [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent.</span><span class="sxs-lookup"><span data-stu-id="d6550-132">(When you restart [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] in single-user mode, stop the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent.</span></span> <span data-ttu-id="d6550-133">In caso contrario, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent potrebbe eseguire per primo la connessione impedendo la connessione come secondo utente.</span><span class="sxs-lookup"><span data-stu-id="d6550-133">Otherwise, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent might connect first and prevent you from connecting as a second user.)</span></span>  
  
4.  [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
5.  <span data-ttu-id="d6550-134">Riavviare il [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="d6550-134">Restart the [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
    > [!WARNING]  
    >  <span data-ttu-id="d6550-135">Al termine dell'utilizzo della modalità utente singolo, nella casella parametri di avvio selezionare il `-m` parametro nella casella **parametri esistenti** , quindi fare clic su **Rimuovi**.</span><span class="sxs-lookup"><span data-stu-id="d6550-135">After you are finished using single-user mode, in the Startup Parameters box, select the `-m` parameter in the **Existing Parameters** box, and then click **Remove**.</span></span> <span data-ttu-id="d6550-136">Riavviare [!INCLUDE[ssDE](../../includes/ssde-md.md)] per ripristinare [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] nella modalità tipica multiutente.</span><span class="sxs-lookup"><span data-stu-id="d6550-136">Restart the [!INCLUDE[ssDE](../../includes/ssde-md.md)] to restore [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] to the typical multi-user mode.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d6550-137">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d6550-137">See Also</span></span>  
 <span data-ttu-id="d6550-138">[Avvio di SQL Server in modalità utente singolo](start-sql-server-in-single-user-mode.md) </span><span class="sxs-lookup"><span data-stu-id="d6550-138">[Start SQL Server in Single-User Mode](start-sql-server-in-single-user-mode.md) </span></span>  
 <span data-ttu-id="d6550-139">[Connettersi a SQL Server se gli amministratori di sistema sono bloccati](connect-to-sql-server-when-system-administrators-are-locked-out.md) </span><span class="sxs-lookup"><span data-stu-id="d6550-139">[Connect to SQL Server When System Administrators Are Locked Out](connect-to-sql-server-when-system-administrators-are-locked-out.md) </span></span>  
 [<span data-ttu-id="d6550-140">Avvio, arresto o sospensione del servizio SQL Server Agent</span><span class="sxs-lookup"><span data-stu-id="d6550-140">Start, Stop, or Pause the SQL Server Agent Service</span></span>](../../ssms/agent/start-stop-or-pause-the-sql-server-agent-service.md)  
  
  
