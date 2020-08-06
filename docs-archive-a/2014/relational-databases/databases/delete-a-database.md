---
title: Eliminare un database | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- database removal [SQL Server], SQL Server Management Studio
- removing databases
- deleting databases
- dropping databases
- databases [SQL Server], dropping
- database removal [SQL Server]
ms.assetid: 1fd8c0f5-03e1-449a-af45-b8cacb479d9c
author: stevestein
ms.author: sstein
ms.openlocfilehash: 633d97815cf69da12f1aa67fd8ef626a2d46e0b0
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87725879"
---
# <a name="delete-a-database"></a><span data-ttu-id="41cf3-102">Eliminare un database</span><span class="sxs-lookup"><span data-stu-id="41cf3-102">Delete a Database</span></span>
  <span data-ttu-id="41cf3-103">In questo argomento si descrive come eliminare un database definito dall'utente in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] di [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] utilizzando [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] o [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="41cf3-103">This topic describes how to delete a user-defined database in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span>  
  
 <span data-ttu-id="41cf3-104">**Contenuto dell'articolo**</span><span class="sxs-lookup"><span data-stu-id="41cf3-104">**In This Topic**</span></span>  
  
-   <span data-ttu-id="41cf3-105">**Prima di iniziare:**</span><span class="sxs-lookup"><span data-stu-id="41cf3-105">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="41cf3-106">Limitazioni e restrizioni</span><span class="sxs-lookup"><span data-stu-id="41cf3-106">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="41cf3-107">Prerequisiti</span><span class="sxs-lookup"><span data-stu-id="41cf3-107">Prerequisites</span></span>](#Prerequisites)  
  
     [<span data-ttu-id="41cf3-108">Indicazioni</span><span class="sxs-lookup"><span data-stu-id="41cf3-108">Recommendations</span></span>](#Recommendations)  
  
     [<span data-ttu-id="41cf3-109">Sicurezza</span><span class="sxs-lookup"><span data-stu-id="41cf3-109">Security</span></span>](#Security)  
  
-   <span data-ttu-id="41cf3-110">**Per eliminare un database tramite:**</span><span class="sxs-lookup"><span data-stu-id="41cf3-110">**To delete a database, using:**</span></span>  
  
     [<span data-ttu-id="41cf3-111">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="41cf3-111">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="41cf3-112">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="41cf3-112">Transact-SQL</span></span>](#TsqlProcedure)  
  
-   <span data-ttu-id="41cf3-113">**Completamento:**  [Dopo l'eliminazione di un database](#FollowUp)</span><span class="sxs-lookup"><span data-stu-id="41cf3-113">**Follow Up:**  [After deleting a database](#FollowUp)</span></span>  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="41cf3-114">Prima di iniziare</span><span class="sxs-lookup"><span data-stu-id="41cf3-114">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="41cf3-115">Limitazioni e restrizioni</span><span class="sxs-lookup"><span data-stu-id="41cf3-115">Limitations and Restrictions</span></span>  
  
-   <span data-ttu-id="41cf3-116">I database di sistema non possono essere eliminati.</span><span class="sxs-lookup"><span data-stu-id="41cf3-116">System databases cannot be deleted.</span></span>  
  
###  <a name="prerequisites"></a><a name="Prerequisites"></a> <span data-ttu-id="41cf3-117">Prerequisiti</span><span class="sxs-lookup"><span data-stu-id="41cf3-117">Prerequisites</span></span>  
  
-   <span data-ttu-id="41cf3-118">Eliminare qualsiasi snapshot di database presente nel database.</span><span class="sxs-lookup"><span data-stu-id="41cf3-118">Delete any database snapshots that exist on the database.</span></span> <span data-ttu-id="41cf3-119">Per altre informazioni, vedere [Eliminare uno snapshot del database &#40;Transact-SQL&#41;](drop-a-database-snapshot-transact-sql.md)o a un'istanza diversa.</span><span class="sxs-lookup"><span data-stu-id="41cf3-119">For more information, see [Drop a Database Snapshot &#40;Transact-SQL&#41;](drop-a-database-snapshot-transact-sql.md).</span></span>  
  
-   <span data-ttu-id="41cf3-120">Se il database è coinvolto nel log shipping, rimuovere quest'ultimo.</span><span class="sxs-lookup"><span data-stu-id="41cf3-120">If the database is involved in log shipping, remove log shipping.</span></span>  
  
-   <span data-ttu-id="41cf3-121">Se il database viene pubblicato per la replica transazionale oppure viene pubblicato o sottoscritto per la replica di tipo merge, rimuovere la replica dal database.</span><span class="sxs-lookup"><span data-stu-id="41cf3-121">If the database is published for transactional replication, or published or subscribed to merge replication, remove replication from the database.</span></span>  
  
###  <a name="recommendations"></a><a name="Recommendations"></a> <span data-ttu-id="41cf3-122">Indicazioni</span><span class="sxs-lookup"><span data-stu-id="41cf3-122">Recommendations</span></span>  
  
-   <span data-ttu-id="41cf3-123">Valutare l'opportunità di eseguire un backup completo del database.</span><span class="sxs-lookup"><span data-stu-id="41cf3-123">Consider taking a full backup of the database.</span></span> <span data-ttu-id="41cf3-124">È possibile ricreare un database eliminato solo tramite il ripristino di un backup.</span><span class="sxs-lookup"><span data-stu-id="41cf3-124">A deleted database can be re-created only by restoring a backup.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="41cf3-125">Sicurezza</span><span class="sxs-lookup"><span data-stu-id="41cf3-125">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="41cf3-126">Autorizzazioni</span><span class="sxs-lookup"><span data-stu-id="41cf3-126">Permissions</span></span>  
 <span data-ttu-id="41cf3-127">Per eseguire DROP DATABASE, un utente deve disporre almeno dell'autorizzazione CONTROL per il database.</span><span class="sxs-lookup"><span data-stu-id="41cf3-127">To execute DROP DATABASE, at a minimum, a user must have CONTROL permission on the database.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="41cf3-128">Utilizzo di SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="41cf3-128">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-delete-a-database"></a><span data-ttu-id="41cf3-129">Per eliminare un database</span><span class="sxs-lookup"><span data-stu-id="41cf3-129">To delete a database</span></span>  
  
1.  <span data-ttu-id="41cf3-130">In **Esplora oggetti**connettersi a un'istanza del [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)], quindi espandere questa istanza.</span><span class="sxs-lookup"><span data-stu-id="41cf3-130">In **Object Explorer**, connect to an instance of the [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)], and then expand that instance.</span></span>  
  
2.  <span data-ttu-id="41cf3-131">Espandere **Database**, fare clic con il pulsante destro del mouse sul database che si vuole eliminare e quindi scegliere **Elimina**.</span><span class="sxs-lookup"><span data-stu-id="41cf3-131">Expand **Databases**, right-click the database to delete, and then click **Delete**.</span></span>  
  
3.  <span data-ttu-id="41cf3-132">Confermare che è stato selezionato il database corretto, quindi fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="41cf3-132">Confirm the correct database is selected, and then click **OK**.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="41cf3-133">Uso di Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="41cf3-133">Using Transact-SQL</span></span>  
  
#### <a name="to-delete-a-database"></a><span data-ttu-id="41cf3-134">Per eliminare un database</span><span class="sxs-lookup"><span data-stu-id="41cf3-134">To delete a database</span></span>  
  
1.  <span data-ttu-id="41cf3-135">Connettersi al [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="41cf3-135">Connect to the [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="41cf3-136">Dalla barra Standard fare clic su **Nuova query**.</span><span class="sxs-lookup"><span data-stu-id="41cf3-136">From the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="41cf3-137">Copiare e incollare l'esempio seguente nella finestra Query, quindi fare clic su **Esegui**.</span><span class="sxs-lookup"><span data-stu-id="41cf3-137">Copy and paste the following example into the query window and click **Execute**.</span></span> <span data-ttu-id="41cf3-138">Nell'esempio si rimuovono i database `Sales` e `NewSales` .</span><span class="sxs-lookup"><span data-stu-id="41cf3-138">The example removes the `Sales` and `NewSales` databases.</span></span>  
  
```sql  
USE master ;  
GO  
DROP DATABASE Sales, NewSales ;  
GO  
```  
  
##  <a name="follow-up-after-deleting-a-database"></a><a name="FollowUp"></a> <span data-ttu-id="41cf3-139">Completamento: Dopo l'eliminazione di un database</span><span class="sxs-lookup"><span data-stu-id="41cf3-139">Follow Up: After deleting a database</span></span>  
 <span data-ttu-id="41cf3-140">Eseguire il backup del database **master** .</span><span class="sxs-lookup"><span data-stu-id="41cf3-140">Back up the **master** database.</span></span> <span data-ttu-id="41cf3-141">Se è necessario ripristinare il database **master** , per qualsiasi database eliminato dopo l'ultimo backup del database **master** saranno ancora disponibili riferimenti nelle viste del catalogo di sistema, pertanto potranno essere generati messaggi di errore.</span><span class="sxs-lookup"><span data-stu-id="41cf3-141">If **master** must be restored, any database that has been deleted since the last backup of **master** will still have references in the system catalog views and may cause error messages to be raised.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="41cf3-142">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="41cf3-142">See Also</span></span>  
 <span data-ttu-id="41cf3-143">[CREATE DATABASE &#40;SQL Server Transact-SQL&#41;](/sql/t-sql/statements/create-database-sql-server-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="41cf3-143">[CREATE DATABASE &#40;SQL Server Transact-SQL&#41;](/sql/t-sql/statements/create-database-sql-server-transact-sql) </span></span>  
 [<span data-ttu-id="41cf3-144">ALTER DATABASE &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="41cf3-144">ALTER DATABASE &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/alter-database-transact-sql)  
  
  
