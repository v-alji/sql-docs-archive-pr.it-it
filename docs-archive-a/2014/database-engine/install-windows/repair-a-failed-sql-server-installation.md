---
title: Ripristinare un'installazione di SQL Server 2014 | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: install
ms.topic: conceptual
ms.assetid: 90c11b28-892b-44d6-978e-0eee48c75b7d
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: f3e382137a971b3f8b23cf1d814bff9908f04150
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87716583"
---
# <a name="drop-a-sql-server-2014-installation"></a><span data-ttu-id="00e64-102">Rimuovere un'installazione di SQL Server 2014</span><span class="sxs-lookup"><span data-stu-id="00e64-102">Drop a SQL Server 2014 Installation</span></span>
  <span data-ttu-id="00e64-103">L'operazione di ripristino può essere utilizzata negli scenari seguenti:</span><span class="sxs-lookup"><span data-stu-id="00e64-103">Repair operation can be used in the following scenarios:</span></span>  
  
-   <span data-ttu-id="00e64-104">Ripristino di un'istanza di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] danneggiata dopo averla installata.</span><span class="sxs-lookup"><span data-stu-id="00e64-104">Repair an instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] that is corrupted after it was successfully installed.</span></span>  
  
-   <span data-ttu-id="00e64-105">Ripristino di un'istanza di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] se l'operazione di aggiornamento è stata annullata o non è riuscita dopo il mapping del nome dell'istanza all'istanza appena aggiornata.</span><span class="sxs-lookup"><span data-stu-id="00e64-105">Repair an instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] if the upgrade operation is cancelled or fails after the instance name is mapped to the newly-upgraded instance.</span></span>  
  
    -   <span data-ttu-id="00e64-106">Se nel log di riepilogo viene visualizzato il messaggio seguente, è possibile ripristinare l'istanza di aggiornamento non riuscita.</span><span class="sxs-lookup"><span data-stu-id="00e64-106">If you see the following message in the summary log, you can repair the failed upgrade instance:</span></span>  
  
         <span data-ttu-id="00e64-107">"Aggiornamento di[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] non riuscito.</span><span class="sxs-lookup"><span data-stu-id="00e64-107">"[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] upgrade failed.</span></span> <span data-ttu-id="00e64-108">Per continuare, individuare la causa dell'errore, correggere il problema, quindi ripristinare l'installazione."</span><span class="sxs-lookup"><span data-stu-id="00e64-108">To continue, investigate the reason for the failure, correct the problem, and then repair your installation."</span></span>  
  
    -   <span data-ttu-id="00e64-109">Se nel log di riepilogo viene visualizzato il messaggio seguente, è necessario disinstallare e reinstallare [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="00e64-109">If you see the following message in the summary log, you need to uninstall and reinstall [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="00e64-110">Non è possibile ripristinare l'istanza di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="00e64-110">You cannot repair the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instance.</span></span>  
  
         <span data-ttu-id="00e64-111">"Aggiornamento di[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] non riuscito.</span><span class="sxs-lookup"><span data-stu-id="00e64-111">"[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] upgrade failed.</span></span> <span data-ttu-id="00e64-112">Per continuare, individuare la causa dell'errore e correggere il problema."</span><span class="sxs-lookup"><span data-stu-id="00e64-112">To continue, investigate the reason for the failure, correct the problem."</span></span>  
  
 <span data-ttu-id="00e64-113">Quando si ripristina un'istanza di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]:</span><span class="sxs-lookup"><span data-stu-id="00e64-113">When you repair an instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]:</span></span>  
  
-   <span data-ttu-id="00e64-114">Vengono sostituiti tutti i file mancanti o danneggiati.</span><span class="sxs-lookup"><span data-stu-id="00e64-114">All missing or corrupt files are replaced.</span></span>  
  
-   <span data-ttu-id="00e64-115">Vengono sostituite tutte le chiavi del Registro di sistema mancanti o danneggiate.</span><span class="sxs-lookup"><span data-stu-id="00e64-115">All missing or corrupt registry keys are replaced.</span></span>  
  
-   <span data-ttu-id="00e64-116">Tutti i valori di configurazione mancanti o non validi vengono impostati su valori predefiniti.</span><span class="sxs-lookup"><span data-stu-id="00e64-116">All missing or invalid configuration values are set to default values.</span></span>  
  
 <span data-ttu-id="00e64-117">Prima di continuare, per i cluster di failover di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] rivedere le informazioni importanti seguenti:</span><span class="sxs-lookup"><span data-stu-id="00e64-117">Before you continue, for [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] failover clusters, review the following important information:</span></span>  
  
-   <span data-ttu-id="00e64-118">Il ripristino deve essere eseguito sui nodi di cluster singoli.</span><span class="sxs-lookup"><span data-stu-id="00e64-118">Repair must be run on individual cluster nodes.</span></span>  
  
-   <span data-ttu-id="00e64-119">Per ripristinare un nodo del cluster di failover dopo un'operazione di preparazione non riuscita, usare **Rimuovi nodo**, quindi eseguire nuovamente la procedura di preparazione.</span><span class="sxs-lookup"><span data-stu-id="00e64-119">To repair a failover cluster node after a failed Prepare operation, use **Remove node** and then perform the Prepare step again.</span></span> <span data-ttu-id="00e64-120">Per altre informazioni, vedere [Aggiungere o rimuovere nodi in un cluster di failover di SQL Server &#40;programma di installazione&#41;](../../sql-server/failover-clusters/install/add-or-remove-nodes-in-a-sql-server-failover-cluster-setup.md).</span><span class="sxs-lookup"><span data-stu-id="00e64-120">For more information, see [Add or Remove Nodes in a SQL Server Failover Cluster &#40;Setup&#41;](../../sql-server/failover-clusters/install/add-or-remove-nodes-in-a-sql-server-failover-cluster-setup.md).</span></span>  
  
### <a name="to-repair-a-failed-installation-of-ssnoversion-from-the-installation-center"></a><span data-ttu-id="00e64-121">Per ripristinare un'installazione non riuscita di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] dal Centro installazione</span><span class="sxs-lookup"><span data-stu-id="00e64-121">To repair a failed installation of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] from the Installation Center</span></span>  
  
1.  <span data-ttu-id="00e64-122">Avviare il programma di installazione di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] (file setup.exe) dai supporti di installazione per [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="00e64-122">Launch the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Setup program (setup.exe) from [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] installation media.</span></span>  
  
2.  <span data-ttu-id="00e64-123">Dopo la verifica del sistema e dei prerequisiti, nel programma di installazione verrà visualizzata la pagina Centro installazione [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="00e64-123">After prerequisites and system verification, the Setup program will display the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Installation Center page.</span></span>  
  
3.  <span data-ttu-id="00e64-124">Fare clic su **Manutenzione** nell'area di navigazione a sinistra, quindi fare clic su **Ripristina** per avviare l'operazione di ripristino.</span><span class="sxs-lookup"><span data-stu-id="00e64-124">Click **Maintenance** in the left-hand navigation area, and then click **Repair** to start the repair operation.</span></span>  
  
    > [!TIP]  
    >  <span data-ttu-id="00e64-125">Se Centro installazione è stato avviato utilizzando il menu Start, a questo punto sarà necessario fornire il percorso del supporto di installazione.</span><span class="sxs-lookup"><span data-stu-id="00e64-125">If the Installation Center was launched using the start menu, you will need to provide the location of the installation media at this time.</span></span>  
  
4.  <span data-ttu-id="00e64-126">Verranno eseguite la regola di supporto dell'installazione e le routine dei file per garantire che nel sistema siano installati i prerequisiti e che il computer passi le regole di convalida dell'installazione.</span><span class="sxs-lookup"><span data-stu-id="00e64-126">Setup support rule and file routines will run to ensure that your system has prerequisites installed and that the computer passes Setup validation rules.</span></span> <span data-ttu-id="00e64-127">Fare clic su **OK** o **Installa** per continuare.</span><span class="sxs-lookup"><span data-stu-id="00e64-127">Click **OK** or **Install** to continue.</span></span>  
  
5.  <span data-ttu-id="00e64-128">Nella pagina Seleziona istanza selezionare l'istanza da ripristinare, quindi fare clic su **Avanti** per continuare.</span><span class="sxs-lookup"><span data-stu-id="00e64-128">On the Select Instance page, select the instance to repair, and then click **Next** to continue.</span></span>  
  
6.  <span data-ttu-id="00e64-129">Verranno eseguite le regole di ripristino per convalidare l'operazione.</span><span class="sxs-lookup"><span data-stu-id="00e64-129">The repair rules will run to validate the operation.</span></span> <span data-ttu-id="00e64-130">Scegliere **Avanti**per continuare.</span><span class="sxs-lookup"><span data-stu-id="00e64-130">To continue, click **Next**.</span></span>  
  
7.  <span data-ttu-id="00e64-131">La pagina Ripristino indica che l'operazione può essere eseguita.</span><span class="sxs-lookup"><span data-stu-id="00e64-131">The Ready to Repair page indicates that the operation is ready to proceed.</span></span> <span data-ttu-id="00e64-132">Per continuare fare clic su **Ripristina**.</span><span class="sxs-lookup"><span data-stu-id="00e64-132">To continue, click **Repair**.</span></span>  
  
8.  <span data-ttu-id="00e64-133">Nella pagina Stato del ripristino viene mostrato lo stato dell'operazione di ripristino.</span><span class="sxs-lookup"><span data-stu-id="00e64-133">The Repair Progress page shows the status of the repair operation.</span></span> <span data-ttu-id="00e64-134">Nella pagina Operazione completata è indicato che l'operazione è stata completata.</span><span class="sxs-lookup"><span data-stu-id="00e64-134">The Complete page indicates that the operation is finished.</span></span>  
  
### <a name="to-repair-a-failed-installation-of-ssnoversion-using-command-prompt"></a><span data-ttu-id="00e64-135">Per ripristinare un'installazione non riuscita di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] utilizzando il prompt dei comandi</span><span class="sxs-lookup"><span data-stu-id="00e64-135">To repair a failed installation of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] using Command Prompt</span></span>  
  
1.  <span data-ttu-id="00e64-136">Al prompt dei comandi eseguire il comando seguente:</span><span class="sxs-lookup"><span data-stu-id="00e64-136">Run the following command at a command prompt:</span></span>  
  
    ```  
    Setup.exe /q /ACTION=Repair /INSTANCENAME=instancename  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="00e64-137">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="00e64-137">See Also</span></span>  
 <span data-ttu-id="00e64-138">[Visualizzare e leggere i file di log del programma di installazione di SQL Server](view-and-read-sql-server-setup-log-files.md) </span><span class="sxs-lookup"><span data-stu-id="00e64-138">[View and Read SQL Server Setup Log Files](view-and-read-sql-server-setup-log-files.md) </span></span>  
 [<span data-ttu-id="00e64-139">Procedure per l'installazione</span><span class="sxs-lookup"><span data-stu-id="00e64-139">Installation How-to Topics</span></span>](../../sql-server/install/installation-how-to-topics.md)  
  
  
