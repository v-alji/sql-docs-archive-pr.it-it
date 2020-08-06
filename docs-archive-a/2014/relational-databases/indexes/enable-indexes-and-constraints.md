---
title: Abilitare indici e vincoli | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: table-view-index
ms.topic: conceptual
helpviewer_keywords:
- indexes [SQL Server], enabling
- nonclustered indexes [SQL Server], enabling a disabled index
- index enabling [SQL Server]
- disabled indexes [SQL Server], how to enable
- constraints [SQL Server], enabling
- clustered indexes, enabling disabled indexes
ms.assetid: c55c8865-322e-4ab0-ba04-ea1f56735353
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 4d4e79689b80a40d00958fa557fe51df2adf9c14
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87637316"
---
# <a name="enable-indexes-and-constraints"></a><span data-ttu-id="c0197-102">Abilitazione di indici e vincoli</span><span class="sxs-lookup"><span data-stu-id="c0197-102">Enable Indexes and Constraints</span></span>
  <span data-ttu-id="c0197-103">In questo argomento si descrive come abilitare un indice disabilitato in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] tramite [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] o [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="c0197-103">This topic describes how to enable a disabled index in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span> <span data-ttu-id="c0197-104">Dopo la disabilitazione, un indice rimane nello stato disabilitato finché non viene ricompilato o rimosso.</span><span class="sxs-lookup"><span data-stu-id="c0197-104">After an index is disabled, it remains in a disabled state until it is rebuilt or dropped</span></span>  
  
 <span data-ttu-id="c0197-105">**Contenuto dell'articolo**</span><span class="sxs-lookup"><span data-stu-id="c0197-105">**In This Topic**</span></span>  
  
-   <span data-ttu-id="c0197-106">**Prima di iniziare:**</span><span class="sxs-lookup"><span data-stu-id="c0197-106">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="c0197-107">Limitazioni e restrizioni</span><span class="sxs-lookup"><span data-stu-id="c0197-107">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="c0197-108">Sicurezza</span><span class="sxs-lookup"><span data-stu-id="c0197-108">Security</span></span>](#Security)  
  
-   <span data-ttu-id="c0197-109">**Per abilitare un indice disabilitato utilizzando:**</span><span class="sxs-lookup"><span data-stu-id="c0197-109">**To enable a disabled index, using:**</span></span>  
  
     [<span data-ttu-id="c0197-110">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="c0197-110">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="c0197-111">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="c0197-111">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="c0197-112">Prima di iniziare</span><span class="sxs-lookup"><span data-stu-id="c0197-112">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="c0197-113">Limitazioni e restrizioni</span><span class="sxs-lookup"><span data-stu-id="c0197-113">Limitations and Restrictions</span></span>  
  
-   <span data-ttu-id="c0197-114">Dopo la ricompilazione dell'indice, sarà necessario abilitare manualmente tutti i vincoli disabilitati in seguito alla disabilitazione dell'indice.</span><span class="sxs-lookup"><span data-stu-id="c0197-114">After rebuilding the index, any constraints that were disabled because of disabling the index must be manually enabled.</span></span> <span data-ttu-id="c0197-115">Per abilitare i vincoli PRIMARY KEY e UNIQUE, è necessario ricompilare l'indice associato.</span><span class="sxs-lookup"><span data-stu-id="c0197-115">PRIMARY KEY and UNIQUE constraints are enabled by rebuilding the associated index.</span></span> <span data-ttu-id="c0197-116">Ricompilare e abilitare questo indice prima di abilitare i vincoli FOREIGN KEY che fanno riferimento al vincolo PRIMARY KEY o UNIQUE.</span><span class="sxs-lookup"><span data-stu-id="c0197-116">This index must be rebuilt (enabled) before you can enable FOREIGN KEY constraints that reference the PRIMARY KEY or UNIQUE constraint.</span></span> <span data-ttu-id="c0197-117">Per abilitare i vincoli FOREIGN KEY, utilizzare l'istruzione ALTER TABLE CHECK CONSTRAINT.</span><span class="sxs-lookup"><span data-stu-id="c0197-117">FOREIGN KEY constraints are enabled by using the ALTER TABLE CHECK CONSTRAINT statement.</span></span>  
  
-   <span data-ttu-id="c0197-118">Non è possibile ricompilare un indice cluster disabilitato se l'opzione ONLINE è impostata su ON.</span><span class="sxs-lookup"><span data-stu-id="c0197-118">Rebuilding a disabled clustered index cannot be performed when the ONLINE option is set to ON.</span></span>  
  
-   <span data-ttu-id="c0197-119">Se l'indice cluster è abilitato o disabilitato e l'indice non cluster è disabilitato, l'operazione sull'indice cluster ha l'effetto seguente sull'indice non cluster disabilitato.</span><span class="sxs-lookup"><span data-stu-id="c0197-119">When the clustered index is disabled or enabled and the nonclustered index is disabled, the clustered index action has the following results on the disabled nonclustered index.</span></span>  
  
    |<span data-ttu-id="c0197-120">Operazione sull'indice cluster</span><span class="sxs-lookup"><span data-stu-id="c0197-120">Clustered Index Action</span></span>|<span data-ttu-id="c0197-121">Indice non cluster disabilitato...</span><span class="sxs-lookup"><span data-stu-id="c0197-121">Disabled Nonclustered Index ...</span></span>|  
    |----------------------------|-----------------------------------|  
    |<span data-ttu-id="c0197-122">ALTER INDEX REBUILD.</span><span class="sxs-lookup"><span data-stu-id="c0197-122">ALTER INDEX REBUILD.</span></span>|<span data-ttu-id="c0197-123">Rimane disabilitato.</span><span class="sxs-lookup"><span data-stu-id="c0197-123">Remains disabled.</span></span>|  
    |<span data-ttu-id="c0197-124">ALTER INDEX ALL REBUILD.</span><span class="sxs-lookup"><span data-stu-id="c0197-124">ALTER INDEX ALL REBUILD.</span></span>|<span data-ttu-id="c0197-125">Viene ricompilato e abilitato.</span><span class="sxs-lookup"><span data-stu-id="c0197-125">Is rebuilt and enabled.</span></span>|  
    |<span data-ttu-id="c0197-126">DROP INDEX.</span><span class="sxs-lookup"><span data-stu-id="c0197-126">DROP INDEX.</span></span>|<span data-ttu-id="c0197-127">Rimane disabilitato.</span><span class="sxs-lookup"><span data-stu-id="c0197-127">Remains disabled.</span></span>|  
    |<span data-ttu-id="c0197-128">CREATE INDEX WITH DROP_EXISTING.</span><span class="sxs-lookup"><span data-stu-id="c0197-128">CREATE INDEX WITH DROP_EXISTING.</span></span>|<span data-ttu-id="c0197-129">Rimane disabilitato.</span><span class="sxs-lookup"><span data-stu-id="c0197-129">Remains disabled.</span></span>|  
  
     <span data-ttu-id="c0197-130">La creazione di un nuovo indice cluster produce lo stesso risultato dell'istruzione ALTER INDEX ALL REBUILD.</span><span class="sxs-lookup"><span data-stu-id="c0197-130">Creating a new clustered index, behaves the same as ALTER INDEX ALL REBUILD.</span></span>  
  
-   <span data-ttu-id="c0197-131">Le operazioni consentite su indici non cluster associati a un indice cluster dipendono dallo stato, disabilitato o abilitato, di entrambi i tipi di indice.</span><span class="sxs-lookup"><span data-stu-id="c0197-131">Allowed actions on nonclustered indexes associated with a clustered index depend on the state, whether disabled or enabled, of both index types.</span></span> <span data-ttu-id="c0197-132">Nella tabella seguente sono riepilogate le operazioni consentite sugli indici non cluster.</span><span class="sxs-lookup"><span data-stu-id="c0197-132">The following table summarizes the allowed actions on nonclustered indexes.</span></span>  
  
    |<span data-ttu-id="c0197-133">Operazione sull'indice non cluster</span><span class="sxs-lookup"><span data-stu-id="c0197-133">Nonclustered Index Action</span></span>|<span data-ttu-id="c0197-134">Indici cluster e non cluster disabilitati</span><span class="sxs-lookup"><span data-stu-id="c0197-134">When both the clustered and nonclustered indexes are disabled.</span></span>|<span data-ttu-id="c0197-135">Indice cluster abilitato e indice non cluster in entrambi gli stati</span><span class="sxs-lookup"><span data-stu-id="c0197-135">When the clustered index is enabled and the nonclustered index is in either state.</span></span>|  
    |-------------------------------|--------------------------------------------------------------------|----------------------------------------------------------------------------------------|  
    |<span data-ttu-id="c0197-136">ALTER INDEX REBUILD.</span><span class="sxs-lookup"><span data-stu-id="c0197-136">ALTER INDEX REBUILD.</span></span>|<span data-ttu-id="c0197-137">Operazione non eseguita.</span><span class="sxs-lookup"><span data-stu-id="c0197-137">The action fails.</span></span>|<span data-ttu-id="c0197-138">Operazione eseguita.</span><span class="sxs-lookup"><span data-stu-id="c0197-138">The action succeeds.</span></span>|  
    |<span data-ttu-id="c0197-139">DROP INDEX.</span><span class="sxs-lookup"><span data-stu-id="c0197-139">DROP INDEX.</span></span>|<span data-ttu-id="c0197-140">Operazione eseguita.</span><span class="sxs-lookup"><span data-stu-id="c0197-140">The action succeeds.</span></span>|<span data-ttu-id="c0197-141">Operazione eseguita.</span><span class="sxs-lookup"><span data-stu-id="c0197-141">The action succeeds.</span></span>|  
    |<span data-ttu-id="c0197-142">CREATE INDEX WITH DROP_EXISTING.</span><span class="sxs-lookup"><span data-stu-id="c0197-142">CREATE INDEX WITH DROP_EXISTING.</span></span>|<span data-ttu-id="c0197-143">Operazione non eseguita.</span><span class="sxs-lookup"><span data-stu-id="c0197-143">The action fails.</span></span>|<span data-ttu-id="c0197-144">Operazione eseguita.</span><span class="sxs-lookup"><span data-stu-id="c0197-144">The action succeeds.</span></span>|  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="c0197-145">Sicurezza</span><span class="sxs-lookup"><span data-stu-id="c0197-145">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="c0197-146">Autorizzazioni</span><span class="sxs-lookup"><span data-stu-id="c0197-146">Permissions</span></span>  
 <span data-ttu-id="c0197-147">È richiesta l'autorizzazione ALTER per la tabella o la vista.</span><span class="sxs-lookup"><span data-stu-id="c0197-147">Requires ALTER permission on the table or view.</span></span> <span data-ttu-id="c0197-148">Se si usa DBCC DBREINDEX, l'utente deve essere il proprietario della tabella oppure un membro del ruolo predefinito del server **sysadmin** o dei ruoli predefiniti del database **db_ddladmin** e **db_owner** .</span><span class="sxs-lookup"><span data-stu-id="c0197-148">If using DBCC DBREINDEX, eser must either own the table or be a member of the **sysadmin** fixed server role or the **db_ddladmin** and **db_owner** fixed database roles.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="c0197-149">Utilizzo di SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="c0197-149">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-enable-a-disabled-index"></a><span data-ttu-id="c0197-150">Per abilitare un indice disabilitato</span><span class="sxs-lookup"><span data-stu-id="c0197-150">To enable a disabled index</span></span>  
  
1.  <span data-ttu-id="c0197-151">In Esplora oggetti fare clic sul segno più per espandere il database contenente la tabella in cui si desidera abilitare un indice.</span><span class="sxs-lookup"><span data-stu-id="c0197-151">In Object Explorer, click the plus sign to expand the database that contains the table on which you want to enable an index.</span></span>  
  
2.  <span data-ttu-id="c0197-152">Fare clic sul segno più per espandere la cartella **Tabelle** .</span><span class="sxs-lookup"><span data-stu-id="c0197-152">Click the plus sign to expand the **Tables** folder.</span></span>  
  
3.  <span data-ttu-id="c0197-153">Fare clic sul segno più per espandere la tabella in cui si desidera abilitare un indice.</span><span class="sxs-lookup"><span data-stu-id="c0197-153">Click the plus sign to expand the table on which you want to enable an index.</span></span>  
  
4.  <span data-ttu-id="c0197-154">Fare clic sul segno più per espandere la cartella **Indici** .</span><span class="sxs-lookup"><span data-stu-id="c0197-154">Click the plus sign to expand the **Indexes** folder.</span></span>  
  
5.  <span data-ttu-id="c0197-155">Fare clic con il pulsante destro del mouse sull'indice che si vuole abilitare e selezionare **Ricompila**.</span><span class="sxs-lookup"><span data-stu-id="c0197-155">Right-click the index you want to enable and select **Rebuild**.</span></span>  
  
6.  <span data-ttu-id="c0197-156">Nella finestra di dialogo **Ricompila indici** verificare che nella griglia **Indici da ricompilare** sia presente l'indice corretto e fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="c0197-156">In the **Rebuild Indexes** dialog box, verify that the correct index is in the **Indexes to rebuild** grid and click **OK**.</span></span>  
  
#### <a name="to-enable-all-indexes-on-a-table"></a><span data-ttu-id="c0197-157">Per abilitare tutti gli indici in una tabella</span><span class="sxs-lookup"><span data-stu-id="c0197-157">To enable all indexes on a table</span></span>  
  
1.  <span data-ttu-id="c0197-158">In Esplora oggetti fare clic sul segno più per espandere il database contenente la tabella in cui si desidera abilitare gli indici.</span><span class="sxs-lookup"><span data-stu-id="c0197-158">In Object Explorer, click the plus sign to expand the database that contains the table on which you want to enable the indexes.</span></span>  
  
2.  <span data-ttu-id="c0197-159">Fare clic sul segno più per espandere la cartella **Tabelle** .</span><span class="sxs-lookup"><span data-stu-id="c0197-159">Click the plus sign to expand the **Tables** folder.</span></span>  
  
3.  <span data-ttu-id="c0197-160">Fare clic sul segno più per espandere la tabella in cui si desidera abilitare gli indici.</span><span class="sxs-lookup"><span data-stu-id="c0197-160">Click the plus sign to expand the table on which you want to enable the indexes.</span></span>  
  
4.  <span data-ttu-id="c0197-161">Fare clic con il pulsante destro del mouse sulla cartella **Indici** e selezionare **Ricompila tutto**.</span><span class="sxs-lookup"><span data-stu-id="c0197-161">Right-click the **Indexes** folder and select **Rebuild All**.</span></span>  
  
5.  <span data-ttu-id="c0197-162">Nella finestra di dialogo **Ricompila indici** verificare che nella griglia **Indici da ricompilare** siano presenti gli indici corretti e fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="c0197-162">In the **Rebuild Indexes** dialog box, verify that the correct indexes are in the **Indexes to rebuild** grid and click **OK**.</span></span> <span data-ttu-id="c0197-163">Per rimuovere un indice dalla griglia **Indici da ricompilare** , selezionare l'indice desiderato, quindi premere il tasto CANC.</span><span class="sxs-lookup"><span data-stu-id="c0197-163">To remove an index from the **Indexes to rebuild** grid, select the index and then press the Delete key.</span></span>  
  
 <span data-ttu-id="c0197-164">Le informazioni seguenti sono disponibili nella finestra di dialogo **Ricompila indici** :</span><span class="sxs-lookup"><span data-stu-id="c0197-164">The following information is available in the **Rebuild Indexes** dialog box:</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="c0197-165">Uso di Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="c0197-165">Using Transact-SQL</span></span>  
  
#### <a name="to-enable-a-disabled-index-using-alter-index"></a><span data-ttu-id="c0197-166">Per abilitare un indice disabilitato utilizzando ALTER INDEX</span><span class="sxs-lookup"><span data-stu-id="c0197-166">To enable a disabled index using ALTER INDEX</span></span>  
  
1.  <span data-ttu-id="c0197-167">In **Esplora oggetti**connettersi a un'istanza del [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="c0197-167">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="c0197-168">Sulla barra Standard fare clic su **Nuova query**.</span><span class="sxs-lookup"><span data-stu-id="c0197-168">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="c0197-169">Copiare e incollare l'esempio seguente nella finestra Query, quindi fare clic su **Esegui**.</span><span class="sxs-lookup"><span data-stu-id="c0197-169">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```  
    USE AdventureWorks2012;  
    GO  
    -- Enables the IX_Employee_OrganizationLevel_OrganizationNode index  
    -- on the HumanResources.Employee table.  
  
    ALTER INDEX IX_Employee_OrganizationLevel_OrganizationNode ON HumanResources.Employee  
    REBUILD;   
    GO  
    ```  
  
#### <a name="to-enable-a-disabled-index-using-create-index"></a><span data-ttu-id="c0197-170">Per abilitare un indice disabilitato utilizzando CREATE INDEX</span><span class="sxs-lookup"><span data-stu-id="c0197-170">To enable a disabled index using CREATE INDEX</span></span>  
  
1.  <span data-ttu-id="c0197-171">In **Esplora oggetti**connettersi a un'istanza del [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="c0197-171">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="c0197-172">Sulla barra Standard fare clic su **Nuova query**.</span><span class="sxs-lookup"><span data-stu-id="c0197-172">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="c0197-173">Copiare e incollare l'esempio seguente nella finestra Query, quindi fare clic su **Esegui**.</span><span class="sxs-lookup"><span data-stu-id="c0197-173">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```  
    USE AdventureWorks2012;  
    GO  
    -- re-creates the IX_Employee_OrganizationLevel_OrganizationNode index  
    -- on the HumanResources.Employee table  
    -- using the OrganizationLevel and OrganizationNode columns  
    -- and then deletes the existing IX_Employee_OrganizationLevel_OrganizationNode index  
    CREATE INDEX IX_Employee_OrganizationLevel_OrganizationNode ON HumanResources.Employee  
       (OrganizationLevel, OrganizationNode)  
    WITH (DROP_EXISTING = ON);  
    GO  
    ```  
  
#### <a name="to-enable-a-disabled-index-using-dbcc-dbreindex"></a><span data-ttu-id="c0197-174">Per abilitare un indice disabilitato utilizzando DBCC DBREINDEX</span><span class="sxs-lookup"><span data-stu-id="c0197-174">To enable a disabled index using DBCC DBREINDEX</span></span>  
  
1.  <span data-ttu-id="c0197-175">In **Esplora oggetti**connettersi a un'istanza del [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="c0197-175">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="c0197-176">Sulla barra Standard fare clic su **Nuova query**.</span><span class="sxs-lookup"><span data-stu-id="c0197-176">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="c0197-177">Copiare e incollare l'esempio seguente nella finestra Query, quindi fare clic su **Esegui**.</span><span class="sxs-lookup"><span data-stu-id="c0197-177">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```  
    USE AdventureWorks2012;   
    GO  
    -- enables the IX_Employee_OrganizationLevel_OrganizationNode index  
    -- on the HumanResources.Employee table  
    DBCC DBREINDEX ("HumanResources.Employee", IX_Employee_OrganizationLevel_OrganizationNode);  
    GO  
    ```  
  
#### <a name="to-enable-all-indexes-on-a-table-using-alter-index"></a><span data-ttu-id="c0197-178">Per abilitare tutti gli indici in una tabella utilizzando ALTER INDEX</span><span class="sxs-lookup"><span data-stu-id="c0197-178">To enable all indexes on a table using ALTER INDEX</span></span>  
  
1.  <span data-ttu-id="c0197-179">In **Esplora oggetti**connettersi a un'istanza del [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="c0197-179">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="c0197-180">Sulla barra Standard fare clic su **Nuova query**.</span><span class="sxs-lookup"><span data-stu-id="c0197-180">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="c0197-181">Copiare e incollare l'esempio seguente nella finestra Query, quindi fare clic su **Esegui**.</span><span class="sxs-lookup"><span data-stu-id="c0197-181">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```  
    USE AdventureWorks2012;  
    GO  
    -- enables all indexes  
    -- on the HumanResources.Employee table  
    ALTER INDEX ALL ON HumanResources.Employee  
    REBUILD;  
    GO  
    ```  
  
#### <a name="to-enable-all-indexes-on-a-table-using-dbcc-dbreindex"></a><span data-ttu-id="c0197-182">Per abilitare tutti gli indici in una tabella utilizzando DBCC DBREINDEX</span><span class="sxs-lookup"><span data-stu-id="c0197-182">To enable all indexes on a table using DBCC DBREINDEX</span></span>  
  
1.  <span data-ttu-id="c0197-183">In **Esplora oggetti**connettersi a un'istanza del [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="c0197-183">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="c0197-184">Sulla barra Standard fare clic su **Nuova query**.</span><span class="sxs-lookup"><span data-stu-id="c0197-184">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="c0197-185">Copiare e incollare l'esempio seguente nella finestra Query, quindi fare clic su **Esegui**.</span><span class="sxs-lookup"><span data-stu-id="c0197-185">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```  
    USE AdventureWorks2012;   
    GO  
    -- enables all indexes  
    -- on the HumanResources.Employee table  
    DBCC DBREINDEX ("HumanResources.Employee", " ");  
    GO  
    ```  
  
 <span data-ttu-id="c0197-186">Per altre informazioni, vedere [ALTER INDEX &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-index-transact-sql), [CREATE INDEX &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-index-transact-sql) e [DBCC DBREINDEX &#40;Transact-SQL&#41;](/sql/t-sql/database-console-commands/dbcc-dbreindex-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="c0197-186">For more information, see [ALTER INDEX &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-index-transact-sql), [CREATE INDEX &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-index-transact-sql), and [DBCC DBREINDEX &#40;Transact-SQL&#41;](/sql/t-sql/database-console-commands/dbcc-dbreindex-transact-sql).</span></span>  
  
  
