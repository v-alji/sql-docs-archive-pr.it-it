---
title: Sospendere o riprendere una sessione di mirroring del database (SQL Server) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: high-availability
ms.topic: conceptual
helpviewer_keywords:
- resuming database mirroring
- database mirroring [SQL Server], sessions
- database mirroring [SQL Server], pausing
- database mirroring [SQL Server], resuming
- pausing database mirroring
ms.assetid: 05ede3b4-6abe-4442-abb7-9f5aee1d6bc0
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: b8a9e30bed3ff268fcfdc6e352ad15ebedfe4e8e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87716795"
---
# <a name="pause-or-resume-a-database-mirroring-session-sql-server"></a><span data-ttu-id="48cf8-102">Sospendere o riprendere una sessione di mirroring del database (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="48cf8-102">Pause or Resume a Database Mirroring Session (SQL Server)</span></span>
  <span data-ttu-id="48cf8-103">In questo argomento viene descritto come sospendere o riprendere il mirroring del database in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] utilizzando [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] o [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="48cf8-103">This topic describes how to pause or resume database mirroring in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span>  
  
 <span data-ttu-id="48cf8-104">**Contenuto dell'articolo**</span><span class="sxs-lookup"><span data-stu-id="48cf8-104">**In This Topic**</span></span>  
  
-   <span data-ttu-id="48cf8-105">**Prima di iniziare:**</span><span class="sxs-lookup"><span data-stu-id="48cf8-105">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="48cf8-106">Sicurezza</span><span class="sxs-lookup"><span data-stu-id="48cf8-106">Security</span></span>](#Security)  
  
-   <span data-ttu-id="48cf8-107">**Per eseguire ReplaceThisText utilizzando:**</span><span class="sxs-lookup"><span data-stu-id="48cf8-107">**To ReplaceThisText, using:**</span></span>  
  
     [<span data-ttu-id="48cf8-108">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="48cf8-108">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="48cf8-109">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="48cf8-109">Transact-SQL</span></span>](#TsqlProcedure)  
  
-   <span data-ttu-id="48cf8-110">**Completamento:**  [Dopo la sospensione o ripresa del mirroring del database](#FollowUp)</span><span class="sxs-lookup"><span data-stu-id="48cf8-110">**Follow Up:**  [After Pausing or Resuming Database Mirroring](#FollowUp)</span></span>  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="48cf8-111">Prima di iniziare</span><span class="sxs-lookup"><span data-stu-id="48cf8-111">Before You Begin</span></span>  
 <span data-ttu-id="48cf8-112">È possibile sospendere una sessione di mirroring del database in qualsiasi momento. Questa operazione potrebbe migliorare le prestazioni in caso di colli di bottiglia. Inoltre, la sessione può essere ripresa in qualsiasi momento.</span><span class="sxs-lookup"><span data-stu-id="48cf8-112">At any time, you can suspend a database mirroring session, which might improve performance during bottlenecks, and you can resume a suspended session at any time.</span></span>  
  
> [!CAUTION]  
>  <span data-ttu-id="48cf8-113">Dopo un servizio forzato, quando il server principale originale esegue nuovamente la connessione, il mirroring viene sospeso.</span><span class="sxs-lookup"><span data-stu-id="48cf8-113">After a forced service, when the original principal server reconnects, mirroring is suspended.</span></span> <span data-ttu-id="48cf8-114">Se si riprende il mirroring in questa situazione, è possibile che si verifichi una perdita di dati nel server principale originale.</span><span class="sxs-lookup"><span data-stu-id="48cf8-114">Resuming mirroring in this situation could possibly cause data loss on the original principal server.</span></span> <span data-ttu-id="48cf8-115">Per informazioni sulla gestione della potenziale perdita di dati, vedere [Cambio di ruolo durante una sessione di mirroring del database &#40;SQL Server&#41;](role-switching-during-a-database-mirroring-session-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="48cf8-115">For information about managing the potential data loss, see [Role Switching During a Database Mirroring Session &#40;SQL Server&#41;](role-switching-during-a-database-mirroring-session-sql-server.md).</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="48cf8-116">Sicurezza</span><span class="sxs-lookup"><span data-stu-id="48cf8-116">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="48cf8-117">Autorizzazioni</span><span class="sxs-lookup"><span data-stu-id="48cf8-117">Permissions</span></span>  
 <span data-ttu-id="48cf8-118">È richiesta l'autorizzazione ALTER per il database.</span><span class="sxs-lookup"><span data-stu-id="48cf8-118">Requires ALTER permission on the database.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="48cf8-119">Utilizzo di SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="48cf8-119">Using SQL Server Management Studio</span></span>  
 <span data-ttu-id="48cf8-120">Per sospendere o riprendere una sessione di mirroring del database, utilizzare la pagina **Proprietà database - Mirroring** .</span><span class="sxs-lookup"><span data-stu-id="48cf8-120">To pause or resume a database mirroring session use the **Database Properties Mirroring** page.</span></span>  
  
#### <a name="to-pause-or-resume-database-mirroring"></a><span data-ttu-id="48cf8-121">Per sospendere o riprendere il mirroring del database</span><span class="sxs-lookup"><span data-stu-id="48cf8-121">To pause or resume database mirroring</span></span>  
  
1.  <span data-ttu-id="48cf8-122">Durante una sessione di mirroring del database, connettersi all'istanza del server principale e in Esplora oggetti fare clic sul nome del server per espanderne l'albero.</span><span class="sxs-lookup"><span data-stu-id="48cf8-122">During a database mirroring session, connect to the principal server instance, in Object Explorer, click the server name to expand the server tree.</span></span>  
  
2.  <span data-ttu-id="48cf8-123">Espandere **Database**e selezionare il database.</span><span class="sxs-lookup"><span data-stu-id="48cf8-123">Expand **Databases**, and select the database.</span></span>  
  
3.  <span data-ttu-id="48cf8-124">Fare clic con il pulsante destro del mouse sul database, scegliere **Attività**e quindi fare clic su **Server mirror**.</span><span class="sxs-lookup"><span data-stu-id="48cf8-124">Right-click the database, select **Tasks**, and then click **Mirror**.</span></span> <span data-ttu-id="48cf8-125">Viene visualizzata la pagina **Mirroring** della finestra di dialogo **Proprietà database** .</span><span class="sxs-lookup"><span data-stu-id="48cf8-125">This opens the **Mirroring** page of the **Database Properties** dialog box.</span></span>  
  
4.  <span data-ttu-id="48cf8-126">Per sospendere la sessione, scegliere **Sospendi**.</span><span class="sxs-lookup"><span data-stu-id="48cf8-126">To pause the session, click **Pause**.</span></span>  
  
     <span data-ttu-id="48cf8-127">Verrà richiesta una conferma. Se si fa clic su **Sì**la sessione viene sospesa e il pulsante diventa **Riprendi**.</span><span class="sxs-lookup"><span data-stu-id="48cf8-127">A prompt asks for confirmation; if you click **Yes**, the session is paused, and the button changes to **Resume**.</span></span>  
  
     <span data-ttu-id="48cf8-128">Per altre informazioni sull'impatto della sospensione di una sessione, vedere [Sospensione e ripresa del mirroring del database &#40;SQL Server&#41;](database-mirroring-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="48cf8-128">For more information about the impact of pausing a session, see [Pausing and Resuming Database Mirroring &#40;SQL Server&#41;](database-mirroring-sql-server.md).</span></span>  
  
5.  <span data-ttu-id="48cf8-129">Per riprendere la sessione fare clic su **Riprendi**.</span><span class="sxs-lookup"><span data-stu-id="48cf8-129">To resume the session, click **Resume**.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="48cf8-130">Uso di Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="48cf8-130">Using Transact-SQL</span></span>  
  
#### <a name="to-pause-database-mirroring"></a><span data-ttu-id="48cf8-131">Per sospendere il mirroring del database</span><span class="sxs-lookup"><span data-stu-id="48cf8-131">To pause database mirroring</span></span>  
  
1.  <span data-ttu-id="48cf8-132">Connettersi al [!INCLUDE[ssDE](../../includes/ssde-md.md)] per qualsiasi partner.</span><span class="sxs-lookup"><span data-stu-id="48cf8-132">Connect to the [!INCLUDE[ssDE](../../includes/ssde-md.md)] for either partner.</span></span>  
  
2.  <span data-ttu-id="48cf8-133">Dalla barra Standard fare clic su **Nuova query**.</span><span class="sxs-lookup"><span data-stu-id="48cf8-133">From the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="48cf8-134">Eseguire l'istruzione [!INCLUDE[tsql](../../includes/tsql-md.md)] riportata di seguito.</span><span class="sxs-lookup"><span data-stu-id="48cf8-134">Issue the following [!INCLUDE[tsql](../../includes/tsql-md.md)] statement:</span></span>  
  
     <span data-ttu-id="48cf8-135">ALTER DATABASE *nome_database* SET PARTNER SUSPEND</span><span class="sxs-lookup"><span data-stu-id="48cf8-135">ALTER DATABASE *database_name* SET PARTNER SUSPEND</span></span>  
  
     <span data-ttu-id="48cf8-136">dove *nome_database* è il database con mirroring di cui si vuole sospendere la sessione.</span><span class="sxs-lookup"><span data-stu-id="48cf8-136">where *database_name* is the mirrored database whose session you want to you want to suspend.</span></span>  
  
     <span data-ttu-id="48cf8-137">Nell'esempio seguente viene sospeso il database di esempio [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="48cf8-137">The following example pauses the [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] sample database.</span></span>  
  
    ```  
    ALTER DATABASE AdventureWorks2012 SET PARTNER SUSPEND;  
    ```  
  
##### <a name="to-resume-database-mirroring"></a><span data-ttu-id="48cf8-138">Per riprendere il mirroring del database</span><span class="sxs-lookup"><span data-stu-id="48cf8-138">To resume database mirroring</span></span>  
  
1.  <span data-ttu-id="48cf8-139">Connettersi al [!INCLUDE[ssDE](../../includes/ssde-md.md)] per qualsiasi partner.</span><span class="sxs-lookup"><span data-stu-id="48cf8-139">Connect to the [!INCLUDE[ssDE](../../includes/ssde-md.md)] for either partner.</span></span>  
  
2.  <span data-ttu-id="48cf8-140">Dalla barra Standard fare clic su **Nuova query**.</span><span class="sxs-lookup"><span data-stu-id="48cf8-140">From the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="48cf8-141">Eseguire l'istruzione Transact-SQL seguente:</span><span class="sxs-lookup"><span data-stu-id="48cf8-141">Issue the following Transact-SQL statement:</span></span>  
  
     <span data-ttu-id="48cf8-142">ALTER DATABASE *nome_database* SET PARTNER RESUME</span><span class="sxs-lookup"><span data-stu-id="48cf8-142">ALTER DATABASE *database_name* SET PARTNER RESUME</span></span>  
  
     <span data-ttu-id="48cf8-143">dove *nome_database* è il database con mirroring di cui si vuole riprendere la sessione.</span><span class="sxs-lookup"><span data-stu-id="48cf8-143">where *database_name* is the mirrored database whose session you want to resume.</span></span>  
  
     <span data-ttu-id="48cf8-144">Nell'esempio seguente viene sospeso il database di esempio [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="48cf8-144">The following example pauses the [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] sample database.</span></span>  
  
    ```  
    ALTER DATABASE AdventureWorks2012 SET PARTNER RESUME;  
    ```  
  
##  <a name="follow-up-after-pausing-or-resuming-database-mirroring"></a><a name="FollowUp"></a><span data-ttu-id="48cf8-145">Completamento: dopo la sospensione o la ripresa del mirroring del database</span><span class="sxs-lookup"><span data-stu-id="48cf8-145">Follow Up: After Pausing or Resuming Database Mirroring</span></span>  
  
-   <span data-ttu-id="48cf8-146">**Dopo la sospensione del mirroring del database**</span><span class="sxs-lookup"><span data-stu-id="48cf8-146">**After pausing database mirroring**</span></span>  
  
     <span data-ttu-id="48cf8-147">Nel database primario adottare le precauzioni per evitare un log delle transazioni pieno.</span><span class="sxs-lookup"><span data-stu-id="48cf8-147">On the primary database, take precautions to avoid a full transaction log.</span></span> <span data-ttu-id="48cf8-148">Per altre informazioni, vedere [Log delle transazioni &#40;SQL Server&#41;](../../relational-databases/logs/the-transaction-log-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="48cf8-148">For more information, see [The Transaction Log &#40;SQL Server&#41;](../../relational-databases/logs/the-transaction-log-sql-server.md).</span></span>  
  
-   <span data-ttu-id="48cf8-149">**Dopo la ripresa del mirroring del database**</span><span class="sxs-lookup"><span data-stu-id="48cf8-149">**After resuming database mirroring**</span></span>  
  
     <span data-ttu-id="48cf8-150">Quando si riprende una sessione di mirroring del database, il database con mirroring viene posto in stato SYNCHRONIZING.</span><span class="sxs-lookup"><span data-stu-id="48cf8-150">Resuming database mirroring places the mirror database in the SYNCHRONIZING state.</span></span> <span data-ttu-id="48cf8-151">Se il livello di sicurezza corrisponde a FULL, il database mirror viene aggiornato in base al database principale e lo stato del database mirror diventa SYNCHRONIZED.</span><span class="sxs-lookup"><span data-stu-id="48cf8-151">If the safety level is FULL, the mirror catches up with the principal and the mirror database enters the SYNCHRONIZED state.</span></span> <span data-ttu-id="48cf8-152">A questo punto è possibile che si verifichi un failover.</span><span class="sxs-lookup"><span data-stu-id="48cf8-152">At this point, failover becomes possible.</span></span> <span data-ttu-id="48cf8-153">Se il server di controllo del mirroring è presente e in stato ON, è possibile che si verifichi un failover automatico.</span><span class="sxs-lookup"><span data-stu-id="48cf8-153">If the witness is present and ON, automatic failover is possible.</span></span> <span data-ttu-id="48cf8-154">Se invece tale server non è presente, è possibile che si verifichi un failover manuale.</span><span class="sxs-lookup"><span data-stu-id="48cf8-154">In the absence of a witness, manual failover is possible.</span></span>  
  
##  <a name="related-tasks"></a><a name="RelatedTasks"></a> <span data-ttu-id="48cf8-155">Attività correlate</span><span class="sxs-lookup"><span data-stu-id="48cf8-155">Related Tasks</span></span>  
  
-   [<span data-ttu-id="48cf8-156">Rimuovere il mirroring del database &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="48cf8-156">Remove Database Mirroring &#40;SQL Server&#41;</span></span>](remove-database-mirroring-sql-server.md)  
  
## <a name="see-also"></a><span data-ttu-id="48cf8-157">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="48cf8-157">See Also</span></span>  
 [<span data-ttu-id="48cf8-158">Mirroring del database &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="48cf8-158">Database Mirroring &#40;SQL Server&#41;</span></span>](database-mirroring-sql-server.md)  
  
  
