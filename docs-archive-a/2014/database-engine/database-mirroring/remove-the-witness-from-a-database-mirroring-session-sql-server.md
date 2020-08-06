---
title: Rimuovere il server di controllo del mirroring da una sessione di mirroring del database (SQL Server) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: high-availability
ms.topic: conceptual
helpviewer_keywords:
- witness [SQL Server], turning off
- witness [SQL Server], removing
- database mirroring [SQL Server], witness
ms.assetid: f3ce7afc-8936-4d35-80ce-d0f8fbc318d3
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: d5ede54aca3588a6fcd7cee8759112b606eac752
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87716752"
---
# <a name="remove-the-witness-from-a-database-mirroring-session-sql-server"></a><span data-ttu-id="18d25-102">Rimuovere il server di controllo del mirroring da una sessione di mirroring del database (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="18d25-102">Remove the Witness from a Database Mirroring Session (SQL Server)</span></span>
  <span data-ttu-id="18d25-103">In questo argomento verrà descritto come rimuovere un server di controllo del mirroring da una sessione di mirroring del database in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] utilizzando [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] o [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="18d25-103">This topic describes how to remove a witness from a database mirroring session in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span> <span data-ttu-id="18d25-104">Durante una sessione di mirroring del database, il proprietario del database può disabilitare il server di controllo del mirroring in qualsiasi momento.</span><span class="sxs-lookup"><span data-stu-id="18d25-104">At any time during a database mirroring session, the database owner can turn off the witness for a database mirroring session.</span></span>  
  
 <span data-ttu-id="18d25-105">**Contenuto dell'articolo**</span><span class="sxs-lookup"><span data-stu-id="18d25-105">**In This Topic**</span></span>  
  
-   <span data-ttu-id="18d25-106">**Prima di iniziare:**</span><span class="sxs-lookup"><span data-stu-id="18d25-106">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="18d25-107">Sicurezza</span><span class="sxs-lookup"><span data-stu-id="18d25-107">Security</span></span>](#Security)  
  
-   <span data-ttu-id="18d25-108">**Per rimuovere il server di controllo del mirroring utilizzando:**</span><span class="sxs-lookup"><span data-stu-id="18d25-108">**To Replace remove the witness, using:**</span></span>  
  
     [<span data-ttu-id="18d25-109">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="18d25-109">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="18d25-110">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="18d25-110">Transact-SQL</span></span>](#TsqlProcedure)  
  
-   <span data-ttu-id="18d25-111">**Completamento:**  [Dopo la rimozione del server di controllo del mirroring](#FollowUp)</span><span class="sxs-lookup"><span data-stu-id="18d25-111">**Follow Up:**  [After Removing the Witness](#FollowUp)</span></span>  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="18d25-112">Prima di iniziare</span><span class="sxs-lookup"><span data-stu-id="18d25-112">Before You Begin</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="18d25-113">Sicurezza</span><span class="sxs-lookup"><span data-stu-id="18d25-113">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="18d25-114">Autorizzazioni</span><span class="sxs-lookup"><span data-stu-id="18d25-114">Permissions</span></span>  
 <span data-ttu-id="18d25-115">È richiesta l'autorizzazione ALTER per il database.</span><span class="sxs-lookup"><span data-stu-id="18d25-115">Requires ALTER permission on the database.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="18d25-116">Utilizzo di SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="18d25-116">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-remove-the-witness"></a><span data-ttu-id="18d25-117">Per rimuovere il server di controllo del mirroring</span><span class="sxs-lookup"><span data-stu-id="18d25-117">To remove the witness</span></span>  
  
1.  <span data-ttu-id="18d25-118">Connettersi all'istanza del server principale e fare clic sul nome del server per espandere l'albero di server nel riquadro **Esplora oggetti** .</span><span class="sxs-lookup"><span data-stu-id="18d25-118">Connect to the principal server instance and, in the **Object Explorer** pane, click the server name to expand the server tree.</span></span>  
  
2.  <span data-ttu-id="18d25-119">Espandere **Database**e selezionare il database di cui si desidera rimuovere il server di controllo del mirroring.</span><span class="sxs-lookup"><span data-stu-id="18d25-119">Expand **Databases**, and select the database whose witness you want to remove.</span></span>  
  
3.  <span data-ttu-id="18d25-120">Fare clic con il pulsante destro del mouse sul database, scegliere **Attività**e quindi fare clic su **Server mirror**.</span><span class="sxs-lookup"><span data-stu-id="18d25-120">Right-click the database, select **Tasks**, and then click **Mirror**.</span></span> <span data-ttu-id="18d25-121">Viene visualizzata la pagina **Mirroring** della finestra di dialogo **Proprietà database** .</span><span class="sxs-lookup"><span data-stu-id="18d25-121">This opens the **Mirroring** page of the **Database Properties** dialog box.</span></span>  
  
4.  <span data-ttu-id="18d25-122">Per rimuovere il server di controllo del mirroring, eliminare l'indirizzo di rete del server dal campo **Server di controllo del mirroring** .</span><span class="sxs-lookup"><span data-stu-id="18d25-122">To remove the witness, delete its server network address from the **Witness** field.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="18d25-123">Se si passa dalla modalità a protezione elevata con failover automatico alla modalità a prestazioni elevate, il contenuto del campo **Server di controllo del mirroring** viene automaticamente cancellato.</span><span class="sxs-lookup"><span data-stu-id="18d25-123">If you switch from high-safety mode with automatic failover to high-performance mode, the **Witness** field is automatically cleared.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="18d25-124">Uso di Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="18d25-124">Using Transact-SQL</span></span>  
  
#### <a name="to-remove-the-witness"></a><span data-ttu-id="18d25-125">Per rimuovere il server di controllo del mirroring</span><span class="sxs-lookup"><span data-stu-id="18d25-125">To remove the witness</span></span>  
  
1.  <span data-ttu-id="18d25-126">Connettersi al [!INCLUDE[ssDE](../../includes/ssde-md.md)] in qualsiasi istanza del server partner.</span><span class="sxs-lookup"><span data-stu-id="18d25-126">Connect to the [!INCLUDE[ssDE](../../includes/ssde-md.md)] on either partner server instance.</span></span>  
  
2.  <span data-ttu-id="18d25-127">Dalla barra Standard fare clic su **Nuova query**.</span><span class="sxs-lookup"><span data-stu-id="18d25-127">From the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="18d25-128">Eseguire l'istruzione seguente:</span><span class="sxs-lookup"><span data-stu-id="18d25-128">Issue the following statement:</span></span>  
  
     <span data-ttu-id="18d25-129">[ALTER DATABASE](/sql/t-sql/statements/alter-database-transact-sql-database-mirroring) *nome_database* SET WITNESS OFF</span><span class="sxs-lookup"><span data-stu-id="18d25-129">[ALTER DATABASE](/sql/t-sql/statements/alter-database-transact-sql-database-mirroring) *database_name* SET WITNESS OFF</span></span>  
  
     <span data-ttu-id="18d25-130">dove *nome_database* è il nome del database con mirroring.</span><span class="sxs-lookup"><span data-stu-id="18d25-130">where *database_name* is the name of the mirrored database.</span></span>  
  
     <span data-ttu-id="18d25-131">Nell'esempio seguente viene rimosso il server di controllo del mirroring dal database [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="18d25-131">The following example removes the witness from the [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] database.</span></span>  
  
    ```  
    ALTER DATABASE AdventureWorks2012 SET WITNESS OFF ;  
    ```  
  
##  <a name="follow-up-after-removing-the-witness"></a><a name="FollowUp"></a><span data-ttu-id="18d25-132">Completamento: dopo la rimozione del server di controllo del mirroring</span><span class="sxs-lookup"><span data-stu-id="18d25-132">Follow Up: After Removing the Witness</span></span>  
 <span data-ttu-id="18d25-133">La disattivazione del server di controllo del mirroring comporta la modifica della [modalità operativa](database-mirroring-operating-modes.md)in base all'impostazione del livello di protezione delle transazioni:</span><span class="sxs-lookup"><span data-stu-id="18d25-133">Turning off the witness changes the [operating mode](database-mirroring-operating-modes.md)in accordance with the transaction-safety setting:</span></span>  
  
-   <span data-ttu-id="18d25-134">Se il livello di protezione delle transazioni è impostato su FULL (impostazione predefinita), nella sessione viene utilizzata la modalità sincrona a protezione elevata senza failover automatico.</span><span class="sxs-lookup"><span data-stu-id="18d25-134">If transaction safety is set to FULL (the default), the session uses high-safety, synchronous mode without automatic failover.</span></span>  
  
-   <span data-ttu-id="18d25-135">Se la protezione delle transazioni è impostata su OFF, la sessione viene eseguita in modo asincrono (in modalità a prestazioni elevate) senza richiedere quorum.</span><span class="sxs-lookup"><span data-stu-id="18d25-135">If transaction safety is set to OFF, the session operates asynchronously (in high-performance mode) without requiring quorum.</span></span> <span data-ttu-id="18d25-136">Ogni volta che la protezione delle transazioni è disattivata, è consigliabile disattivare anche il server di controllo.</span><span class="sxs-lookup"><span data-stu-id="18d25-136">Whenever transaction safety is turned off, we strongly recommend also turning the witness off.</span></span>  
  
> [!TIP]  
>  <span data-ttu-id="18d25-137">L'impostazione della sicurezza delle transazioni per il database viene registrata per ogni partner nelle colonne **mirroring_safety_level** e **mirroring_safety_level_desc** della vista del catalogo [sys.database_mirroring](/sql/relational-databases/system-catalog-views/sys-database-mirroring-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="18d25-137">The transaction safety setting of the database is recorded on each partner in the [sys.database_mirroring](/sql/relational-databases/system-catalog-views/sys-database-mirroring-transact-sql) catalog view in the **mirroring_safety_level** and **mirroring_safety_level_desc** columns.</span></span>  
  
##  <a name="related-tasks"></a><a name="RelatedTasks"></a> <span data-ttu-id="18d25-138">Attività correlate</span><span class="sxs-lookup"><span data-stu-id="18d25-138">Related Tasks</span></span>  
  
-   [<span data-ttu-id="18d25-139">Aggiungere un server di controllo del mirroring del database tramite l'autenticazione di Windows &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="18d25-139">Add a Database Mirroring Witness Using Windows Authentication &#40;Transact-SQL&#41;</span></span>](add-a-database-mirroring-witness-using-windows-authentication-transact-sql.md)  
  
-   [<span data-ttu-id="18d25-140">Aggiunta o sostituzione di un server di controllo del mirroring del database &#40;SQL Server Management Studio&#41;</span><span class="sxs-lookup"><span data-stu-id="18d25-140">Add or Replace a Database Mirroring Witness &#40;SQL Server Management Studio&#41;</span></span>](../database-mirroring/add-or-replace-a-database-mirroring-witness-sql-server-management-studio.md)  
  
## <a name="see-also"></a><span data-ttu-id="18d25-141">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="18d25-141">See Also</span></span>  
 <span data-ttu-id="18d25-142">[Mirroring del database di ALTER DATABASE &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-database-transact-sql-database-mirroring) </span><span class="sxs-lookup"><span data-stu-id="18d25-142">[ALTER DATABASE Database Mirroring &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-database-transact-sql-database-mirroring) </span></span>  
 <span data-ttu-id="18d25-143">[Modificare la sicurezza delle transazioni in una sessione di mirroring del database &#40;Transact-SQL&#41;](change-transaction-safety-in-a-database-mirroring-session-transact-sql.md) </span><span class="sxs-lookup"><span data-stu-id="18d25-143">[Change Transaction Safety in a Database Mirroring Session &#40;Transact-SQL&#41;](change-transaction-safety-in-a-database-mirroring-session-transact-sql.md) </span></span>  
 <span data-ttu-id="18d25-144">[Aggiungere un server di controllo del mirroring del database utilizzando l'autenticazione di Windows &#40;Transact-SQL&#41;](add-a-database-mirroring-witness-using-windows-authentication-transact-sql.md) </span><span class="sxs-lookup"><span data-stu-id="18d25-144">[Add a Database Mirroring Witness Using Windows Authentication &#40;Transact-SQL&#41;](add-a-database-mirroring-witness-using-windows-authentication-transact-sql.md) </span></span>  
 [<span data-ttu-id="18d25-145">Server di controllo del mirroring del database</span><span class="sxs-lookup"><span data-stu-id="18d25-145">Database Mirroring Witness</span></span>](database-mirroring-witness.md)  
  
  
