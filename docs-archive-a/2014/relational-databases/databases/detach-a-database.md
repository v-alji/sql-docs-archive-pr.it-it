---
title: Scollegare un database | Microsoft Docs
ms.custom: ''
ms.date: 03/08/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
f1_keywords:
- sql12.swb.detachdatabase.f1
helpviewer_keywords:
- database detaching [SQL Server]
- detaching databases [SQL Server]
ms.assetid: f63d4107-13e4-4bfe-922d-5e4f712e472d
author: stevestein
ms.author: sstein
ms.openlocfilehash: b8acc809b881012d18f78995bb8e521337fb02ee
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87637879"
---
# <a name="detach-a-database"></a><span data-ttu-id="faed8-102">Scollegare un database</span><span class="sxs-lookup"><span data-stu-id="faed8-102">Detach a Database</span></span>
  <span data-ttu-id="faed8-103">In questo argomento viene descritto come scollegare un database in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] utilizzando [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] o [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="faed8-103">This topic describes how to detach a database in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span> <span data-ttu-id="faed8-104">I file scollegati non vengono eliminati e possono essere ricollegati tramite CREATE DATABASE con l'opzione FOR ATTACH o FOR ATTACH_REBUILD_LOG.</span><span class="sxs-lookup"><span data-stu-id="faed8-104">The detached files remain and can be reattached by using CREATE DATABASE with the FOR ATTACH or FOR ATTACH_REBUILD_LOG option.</span></span> <span data-ttu-id="faed8-105">È possibile spostare e quindi collegare tali file in un altro server.</span><span class="sxs-lookup"><span data-stu-id="faed8-105">The files can be moved to another server and attached there.</span></span>  
  
 <span data-ttu-id="faed8-106">**Contenuto dell'articolo**</span><span class="sxs-lookup"><span data-stu-id="faed8-106">**In This Topic**</span></span>  
  
-   <span data-ttu-id="faed8-107">**Prima di iniziare:**</span><span class="sxs-lookup"><span data-stu-id="faed8-107">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="faed8-108">Limitazioni e restrizioni</span><span class="sxs-lookup"><span data-stu-id="faed8-108">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="faed8-109">Sicurezza</span><span class="sxs-lookup"><span data-stu-id="faed8-109">Security</span></span>](#Security)  
  
-   <span data-ttu-id="faed8-110">**Per scollegare un database utilizzando:**</span><span class="sxs-lookup"><span data-stu-id="faed8-110">**To detach a database, using:**</span></span>  
  
     [<span data-ttu-id="faed8-111">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="faed8-111">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="faed8-112">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="faed8-112">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="faed8-113">Prima di iniziare</span><span class="sxs-lookup"><span data-stu-id="faed8-113">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="faed8-114">Limitazioni e restrizioni</span><span class="sxs-lookup"><span data-stu-id="faed8-114">Limitations and Restrictions</span></span>  
 <span data-ttu-id="faed8-115">Per un elenco delle limitazioni e restrizioni, vedere [Collegamento e scollegamento di un database &#40;SQL Server&#41;](database-detach-and-attach-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="faed8-115">For a list of limitations and restrictions, see [Database Detach and Attach &#40;SQL Server&#41;](database-detach-and-attach-sql-server.md).</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="faed8-116">Sicurezza</span><span class="sxs-lookup"><span data-stu-id="faed8-116">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="faed8-117">Autorizzazioni</span><span class="sxs-lookup"><span data-stu-id="faed8-117">Permissions</span></span>  
 <span data-ttu-id="faed8-118">Richiede l'appartenenza al ruolo predefinito del database db_owner.</span><span class="sxs-lookup"><span data-stu-id="faed8-118">Requires membership in the db_owner fixed database role.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="faed8-119">Utilizzo di SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="faed8-119">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-detach-a-database"></a><span data-ttu-id="faed8-120">Per scollegare un database</span><span class="sxs-lookup"><span data-stu-id="faed8-120">To detach a database</span></span>  
  
1.  <span data-ttu-id="faed8-121">In Esplora oggetti di [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] connettersi all'istanza del [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] e quindi espanderla.</span><span class="sxs-lookup"><span data-stu-id="faed8-121">In [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] Object Explorer, connect to the instance of the [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] and then expand the instance.</span></span>  
  
2.  <span data-ttu-id="faed8-122">Espandere **Database**e selezionare il nome del database utente che si desidera scollegare.</span><span class="sxs-lookup"><span data-stu-id="faed8-122">Expand **Databases**, and select the name of the user database you want to detach.</span></span>  
  
3.  <span data-ttu-id="faed8-123">Fare clic con il pulsante destro del mouse sul nome di database, scegliere **Attività**e quindi fare clic su **Scollega**.</span><span class="sxs-lookup"><span data-stu-id="faed8-123">Right-click the database name, point to **Tasks**, and then click **Detach**.</span></span> <span data-ttu-id="faed8-124">Verrà visualizzata la finestra di dialogo **Scollega database** .</span><span class="sxs-lookup"><span data-stu-id="faed8-124">The **Detach Database** dialog box appears.</span></span>  
  
     <span data-ttu-id="faed8-125">**Database da scollegare**</span><span class="sxs-lookup"><span data-stu-id="faed8-125">**Databases to detach**</span></span>  
     <span data-ttu-id="faed8-126">Consente di visualizzare i database da scollegare.</span><span class="sxs-lookup"><span data-stu-id="faed8-126">Lists the databases to detach.</span></span>  
  
     <span data-ttu-id="faed8-127">**Nome database**</span><span class="sxs-lookup"><span data-stu-id="faed8-127">**Database Name**</span></span>  
     <span data-ttu-id="faed8-128">Consente di visualizzare il nome del database da scollegare.</span><span class="sxs-lookup"><span data-stu-id="faed8-128">Displays the name of the database to be detached.</span></span>  
  
     <span data-ttu-id="faed8-129">**Interrompi connessioni**</span><span class="sxs-lookup"><span data-stu-id="faed8-129">**Drop Connections**</span></span>  
     <span data-ttu-id="faed8-130">Consente di interrompere le connessioni al database specificato.</span><span class="sxs-lookup"><span data-stu-id="faed8-130">Disconnect connections to the specified database.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="faed8-131">Non è possibile scollegare un database con connessioni attive.</span><span class="sxs-lookup"><span data-stu-id="faed8-131">You cannot detach a database with active connections.</span></span>  
  
     <span data-ttu-id="faed8-132">**Aggiorna statistiche**</span><span class="sxs-lookup"><span data-stu-id="faed8-132">**Update Statistics**</span></span>  
     <span data-ttu-id="faed8-133">Per impostazione predefinita, con l'operazione di scollegamento è possibile mantenere eventuali statistiche di ottimizzazione non aggiornate prima di scollegare il database. Per aggiornare le statistiche di ottimizzazione esistenti, fare clic su questa casella di controllo.</span><span class="sxs-lookup"><span data-stu-id="faed8-133">By default, the detach operation retains any out-of-date optimization statistics when detaching the database; to update the existing optimization statistics, click this check box.</span></span>  
  
     <span data-ttu-id="faed8-134">**Mantieni cataloghi full-text**</span><span class="sxs-lookup"><span data-stu-id="faed8-134">**Keep Full-Text Catalogs**</span></span>  
     <span data-ttu-id="faed8-135">Per impostazione predefinita, con l'operazione di scollegamento è possibile mantenere eventuali cataloghi full-text associati al database.</span><span class="sxs-lookup"><span data-stu-id="faed8-135">By default, the detach operation keeps any full-text catalogs that are associated with the database.</span></span> <span data-ttu-id="faed8-136">Per rimuoverli, deselezionare la casella di controllo **Mantieni cataloghi full-text** .</span><span class="sxs-lookup"><span data-stu-id="faed8-136">To remove them, clear the **Keep Full-Text Catalogs** check box.</span></span> <span data-ttu-id="faed8-137">Questa opzione è visualizzata solo quando si aggiorna un database da [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)].</span><span class="sxs-lookup"><span data-stu-id="faed8-137">This option appears only when you are upgrading a database from [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)].</span></span>  
  
     <span data-ttu-id="faed8-138">**Status**</span><span class="sxs-lookup"><span data-stu-id="faed8-138">**Status**</span></span>  
     <span data-ttu-id="faed8-139">Consente di visualizzare uno degli stati seguenti: **Pronto** o **Non pronto**.</span><span class="sxs-lookup"><span data-stu-id="faed8-139">Displays one of the following states: **Ready** or **Not ready**.</span></span>  
  
     <span data-ttu-id="faed8-140">**Messaggio**</span><span class="sxs-lookup"><span data-stu-id="faed8-140">**Message**</span></span>  
     <span data-ttu-id="faed8-141">Nella colonna **Messaggio** possono essere visualizzate informazioni sul database simili alle seguenti:</span><span class="sxs-lookup"><span data-stu-id="faed8-141">The **Message** column may display information about the database, as follows:</span></span>  
  
    -   <span data-ttu-id="faed8-142">Quando un database è coinvolto nella replica, lo **Stato** è **Non pronto** e nella colonna **Messaggio** viene visualizzato **Database replicato**.</span><span class="sxs-lookup"><span data-stu-id="faed8-142">When a database is involved with replication, the **Status** is **Not ready** and the **Message** column displays **Database replicated**.</span></span>  
  
    -   <span data-ttu-id="faed8-143">Quando per un database esistono una o più connessioni attive, il valore di **Stato** è **Non pronto** e la colonna **Messaggio** visualizza _<number_of_active_connections>_ **Connessioni attive**, ad esempio: **Connessioni attive: 1**.</span><span class="sxs-lookup"><span data-stu-id="faed8-143">When a database has one or more active connections, the **Status** is **Not ready** and the **Message** column displays _<number_of_active_connections>_**Active connection(s)** - for example: **1 Active connection(s)**.</span></span> <span data-ttu-id="faed8-144">Prima di poter scollegare il database è necessario disconnettere tutte le connessioni attive selezionando **Interrompi connessioni**.</span><span class="sxs-lookup"><span data-stu-id="faed8-144">Before you can detach the database, you need to disconnect any active connections by selecting **Drop Connections**.</span></span>  
  
     <span data-ttu-id="faed8-145">Per ottenere ulteriori informazioni su un messaggio, fare clic sul testo del collegamento ipertestuale per aprire Monitoraggio attività.</span><span class="sxs-lookup"><span data-stu-id="faed8-145">To obtain more information about a message, click the hyperlinked text to open Activity Monitor.</span></span>  
  
4.  <span data-ttu-id="faed8-146">Quando si è pronti per scollegare il database, fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="faed8-146">When you are ready to detach the database, click **OK**.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="faed8-147">Il database scollegato rimarrà visibile nel nodo **Database** di Esplora oggetti fino all'aggiornamento della vista.</span><span class="sxs-lookup"><span data-stu-id="faed8-147">The newly detached database will remain visible in the **Databases** node of Object Explorer until the view is refreshed.</span></span> <span data-ttu-id="faed8-148">È possibile aggiornare la vista in qualsiasi momento: Fare clic nel riquadro Esplora oggetti, scegliere **Vista** dalla barra dei menu, quindi **Aggiorna**.</span><span class="sxs-lookup"><span data-stu-id="faed8-148">You can refresh the view at any time: Click in the Object Explorer pane, and from the menu bar select **View** and then **Refresh**.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="faed8-149">Uso di Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="faed8-149">Using Transact-SQL</span></span>  
  
#### <a name="to-detach-a-database"></a><span data-ttu-id="faed8-150">Per scollegare un database</span><span class="sxs-lookup"><span data-stu-id="faed8-150">To detach a database</span></span>  
  
1.  <span data-ttu-id="faed8-151">Connettersi al [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="faed8-151">Connect to the [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="faed8-152">Dalla barra Standard fare clic su **Nuova query**.</span><span class="sxs-lookup"><span data-stu-id="faed8-152">From the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="faed8-153">Copiare e incollare l'esempio seguente nella finestra Query, quindi fare clic su **Esegui**.</span><span class="sxs-lookup"><span data-stu-id="faed8-153">Copy and paste the following example into the query window and click **Execute**.</span></span> <span data-ttu-id="faed8-154">Nell'esempio seguente viene scollegato il database AdventureWorks2012 con skipchecks impostato su true.</span><span class="sxs-lookup"><span data-stu-id="faed8-154">This example detaches the AdventureWorks2012 database with skipchecks set to true.</span></span>  
  
```  
EXEC sp_detach_db 'AdventureWorks2012', 'true';  
```  
  
## <a name="see-also"></a><span data-ttu-id="faed8-155">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="faed8-155">See Also</span></span>  
 <span data-ttu-id="faed8-156">[Collegamento e scollegamento di un database &#40;SQL Server&#41;](database-detach-and-attach-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="faed8-156">[Database Detach and Attach &#40;SQL Server&#41;](database-detach-and-attach-sql-server.md) </span></span>  
 [<span data-ttu-id="faed8-157">sp_detach_db &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="faed8-157">sp_detach_db &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-detach-db-transact-sql)  
  
  
