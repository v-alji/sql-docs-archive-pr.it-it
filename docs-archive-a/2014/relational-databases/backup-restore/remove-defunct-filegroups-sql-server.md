---
title: Rimuovere filegroup inattivi (SQL Server) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: backup-restore
ms.topic: conceptual
helpviewer_keywords:
- piecemeal restores [SQL Server], defunct filegroups
- defunct filegroups
- restoring filegroups [SQL Server]
- deferred transactions
- filegroups [SQL Server], defunct
- unrestored filegroups
ms.assetid: 055f9c6a-5c18-4942-98e7-ec918f0ff975
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: a2bcba095d668c5c1ab317269a18af4dc996f63b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87721516"
---
# <a name="remove-defunct-filegroups-sql-server"></a><span data-ttu-id="c6436-102">Rimozione di filegroup inattivi (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="c6436-102">Remove Defunct Filegroups (SQL Server)</span></span>
  <span data-ttu-id="c6436-103">In questo argomento viene descritto come rimuovere filegroup inattivi in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] utilizzando [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] o [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="c6436-103">This topic describes how to remove defunct filegroups in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span>  
  
 <span data-ttu-id="c6436-104">**Contenuto dell'articolo**</span><span class="sxs-lookup"><span data-stu-id="c6436-104">**In This Topic**</span></span>  
  
-   <span data-ttu-id="c6436-105">**Prima di iniziare:**</span><span class="sxs-lookup"><span data-stu-id="c6436-105">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="c6436-106">Limitazioni e restrizioni</span><span class="sxs-lookup"><span data-stu-id="c6436-106">Limitations and Restrictions</span></span>](#Restrictions)  
  
-   [<span data-ttu-id="c6436-107">Indicazioni</span><span class="sxs-lookup"><span data-stu-id="c6436-107">Recommendations</span></span>](#Recommendations)  
  
     [<span data-ttu-id="c6436-108">Sicurezza</span><span class="sxs-lookup"><span data-stu-id="c6436-108">Security</span></span>](#Security)  
  
-   <span data-ttu-id="c6436-109">**Per rimuovere filegroup inattivi utilizzando:**</span><span class="sxs-lookup"><span data-stu-id="c6436-109">**To remove defunct filegroups, using:**</span></span>  
  
     [<span data-ttu-id="c6436-110">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="c6436-110">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="c6436-111">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="c6436-111">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="c6436-112">Prima di iniziare</span><span class="sxs-lookup"><span data-stu-id="c6436-112">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="c6436-113">Limitazioni e restrizioni</span><span class="sxs-lookup"><span data-stu-id="c6436-113">Limitations and Restrictions</span></span>  
  
-   <span data-ttu-id="c6436-114">Le informazioni in questo argomento sono rilevanti per database di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] che contengono più file o filegroup nonché, nel modello con registrazione minima, solo per i filegroup di sola lettura.</span><span class="sxs-lookup"><span data-stu-id="c6436-114">This topic is relevant for [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] databases that contain multiple files or filegroups; and, under the simple model, only for read-only filegroups.</span></span>  
  
-   <span data-ttu-id="c6436-115">Lo stato di tutti i file di un filegroup è defunct quando si rimuove un filegroup offline.</span><span class="sxs-lookup"><span data-stu-id="c6436-115">All files in a filegroup become defunct when an offline filegroup is removed.</span></span>  
  
###  <a name="recommendations"></a><a name="Recommendations"></a> <span data-ttu-id="c6436-116">Indicazioni</span><span class="sxs-lookup"><span data-stu-id="c6436-116">Recommendations</span></span>  
  
-   <span data-ttu-id="c6436-117">Se non sarà mai necessario ripristinare un filegroup non ripristinato, è possibile rendere il filegroup *inattivo* rimuovendolo dal database.</span><span class="sxs-lookup"><span data-stu-id="c6436-117">If an unrestored filegroup will never have to be restored, you can make the filegroup *defunct* by removing it from the database.</span></span> <span data-ttu-id="c6436-118">Il filegroup inattivo non potrà mai essere ripristinato in questo database, ma i relativi metadati verranno mantenuti.</span><span class="sxs-lookup"><span data-stu-id="c6436-118">The defunct filegroup can never be restored to this database, but its metadata remains.</span></span> <span data-ttu-id="c6436-119">Dopo che il filegroup è reso inattivo, è possibile riavviare il database. Il recupero renderà il database consistente rispetto ai filegroup ripristinati.</span><span class="sxs-lookup"><span data-stu-id="c6436-119">After the filegroup is defunct, the database can be restarted, and recovery will make the database consistent across the restored filegroups.</span></span>  
  
     <span data-ttu-id="c6436-120">Ad esempio, rendere un filegroup inattivo è un'opzione per risolvere le transazioni posticipate causate da un filegroup offline che si desidera escludere dal database.</span><span class="sxs-lookup"><span data-stu-id="c6436-120">For example, making a filegroup defunct is an option for resolving deferred transactions that were caused by an offline filegroup that you no longer want in the database.</span></span> <span data-ttu-id="c6436-121">Quando il filegroup in questione diventa offline, lo stato di transazione posticipata viene annullato.</span><span class="sxs-lookup"><span data-stu-id="c6436-121">Transactions that were deferred because the filegroup was offline are moved out of the deferred state after the filegroup becomes defunct.</span></span> <span data-ttu-id="c6436-122">Per altre informazioni, vedere [Transazioni posticipate &#40;SQL Server&#41;](deferred-transactions-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="c6436-122">For more information, see [Deferred Transactions &#40;SQL Server&#41;](deferred-transactions-sql-server.md).</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="c6436-123">Sicurezza</span><span class="sxs-lookup"><span data-stu-id="c6436-123">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="c6436-124">Autorizzazioni</span><span class="sxs-lookup"><span data-stu-id="c6436-124">Permissions</span></span>  
 <span data-ttu-id="c6436-125">È richiesta l'autorizzazione ALTER per il database.</span><span class="sxs-lookup"><span data-stu-id="c6436-125">Requires ALTER permission on the database.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="c6436-126">Utilizzo di SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="c6436-126">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-remove-defunct-filegroups"></a><span data-ttu-id="c6436-127">Per rimuovere filegroup inattivi</span><span class="sxs-lookup"><span data-stu-id="c6436-127">To remove defunct filegroups</span></span>  
  
1.  <span data-ttu-id="c6436-128">In **Esplora oggetti**connettersi a un'istanza del [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] , quindi espandere questa istanza.</span><span class="sxs-lookup"><span data-stu-id="c6436-128">In **Object Explorer**, connect to an instance of the [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] and then expand that instance.</span></span>  
  
2.  <span data-ttu-id="c6436-129">Espandere **Database**, fare clic con il pulsante destro del mouse sul database da cui eliminare il file e quindi scegliere **Proprietà**.</span><span class="sxs-lookup"><span data-stu-id="c6436-129">Expand **Databases**, right-click the database from which to delete the file, and then click **Properties**.</span></span>  
  
3.  <span data-ttu-id="c6436-130">Selezionare la pagina **File** .</span><span class="sxs-lookup"><span data-stu-id="c6436-130">Select the **Files** page.</span></span>  
  
4.  <span data-ttu-id="c6436-131">Nella griglia **File di database** selezionare i file da eliminare, fare clic su **Rimuovi**e quindi su **OK**.</span><span class="sxs-lookup"><span data-stu-id="c6436-131">In the **Database files** grid, select the files to delete, click **Remove**, and then click **OK**.</span></span>  
  
5.  <span data-ttu-id="c6436-132">Fare clic sulla pagina **Filegroup** .</span><span class="sxs-lookup"><span data-stu-id="c6436-132">Select the **Filegroups** page.</span></span>  
  
6.  <span data-ttu-id="c6436-133">Nella griglia **Righe** selezionare il filegroup da eliminare, fare clic su **Rimuovi**e quindi su **OK**.</span><span class="sxs-lookup"><span data-stu-id="c6436-133">In the **Rows** grid, select the filegroup to delete, click **Remove**, and then click **OK**.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="c6436-134">Uso di Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="c6436-134">Using Transact-SQL</span></span>  
  
#### <a name="to-remove-defunct-filegroups"></a><span data-ttu-id="c6436-135">Per rimuovere filegroup inattivi</span><span class="sxs-lookup"><span data-stu-id="c6436-135">To remove defunct filegroups</span></span>  
  
1.  <span data-ttu-id="c6436-136">Connettersi al [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="c6436-136">Connect to the [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="c6436-137">Dalla barra Standard fare clic su **Nuova query**.</span><span class="sxs-lookup"><span data-stu-id="c6436-137">From the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="c6436-138">Copiare e incollare l'esempio seguente nella finestra Query, quindi fare clic su **Esegui**.</span><span class="sxs-lookup"><span data-stu-id="c6436-138">Copy and paste the following example into the query window and click **Execute**.</span></span> <span data-ttu-id="c6436-139">**Nota:** in questo esempio si presuppone che i file e il filegroup siano già presenti.</span><span class="sxs-lookup"><span data-stu-id="c6436-139">(**Note:** This example assumes that the files and filegroup already exist.</span></span> <span data-ttu-id="c6436-140">Per creare questi oggetti, vedere l'esempio B nell'argomento [Opzioni per file e filegroup ALTER DATABASE](/sql/t-sql/statements/alter-database-transact-sql-file-and-filegroup-options). Nel primo esempio vengono rimossi i file `test1dat3` e `test1dat4` dal filegroup inattivo tramite l'istruzione `ALTER DATABASE` con la clausola `REMOVE FILE`.</span><span class="sxs-lookup"><span data-stu-id="c6436-140">To create these objects, see example B in the [ALTER DATABASE File and Filegroup Options](/sql/t-sql/statements/alter-database-transact-sql-file-and-filegroup-options) topic.) The first example removes the `test1dat3` and `test1dat4` files from the defunct filegroup by using the `ALTER DATABASE` statement with the `REMOVE FILE` clause.</span></span> <span data-ttu-id="c6436-141">Nel secondo esempio viene rimosso il filegroup `Test1FG1`inattivo tramite la clausola `REMOVE FILEGROUP` .</span><span class="sxs-lookup"><span data-stu-id="c6436-141">The second example removes the defunct filegroup `Test1FG1`by using the `REMOVE FILEGROUP` clause.</span></span>  
  
```sql  
USE master;  
GO  
ALTER DATABASE AdventureWorks2012  
REMOVE FILE test1dat3 ;  
ALTER DATABASE AdventureWorks2012  
REMOVE FILE test1dat4 ;  
GO  
  
```  
  
```sql  
USE master;  
GO  
ALTER DATABASE AdventureWorks2012  
REMOVE FILEGROUP Test1FG1 ;  
GO  
  
```  
  
## <a name="see-also"></a><span data-ttu-id="c6436-142">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c6436-142">See Also</span></span>  
 <span data-ttu-id="c6436-143">[Opzioni per file e filegroup ALTER DATABASE &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-database-transact-sql-file-and-filegroup-options) </span><span class="sxs-lookup"><span data-stu-id="c6436-143">[ALTER DATABASE File and Filegroup Options &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-database-transact-sql-file-and-filegroup-options) </span></span>  
 <span data-ttu-id="c6436-144">[Transazioni posticipate &#40;SQL Server&#41;](deferred-transactions-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="c6436-144">[Deferred Transactions &#40;SQL Server&#41;](deferred-transactions-sql-server.md) </span></span>  
 <span data-ttu-id="c6436-145">[Ripristini di file &#40;modello di recupero con registrazione completa&#41;](file-restores-full-recovery-model.md) </span><span class="sxs-lookup"><span data-stu-id="c6436-145">[File Restores &#40;Full Recovery Model&#41;](file-restores-full-recovery-model.md) </span></span>  
 <span data-ttu-id="c6436-146">[Ripristini di file &#40;modello di recupero con registrazione minima&#41;](file-restores-simple-recovery-model.md) </span><span class="sxs-lookup"><span data-stu-id="c6436-146">[File Restores &#40;Simple Recovery Model&#41;](file-restores-simple-recovery-model.md) </span></span>  
 <span data-ttu-id="c6436-147">[Ripristino online &#40;SQL Server&#41;](online-restore-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="c6436-147">[Online Restore &#40;SQL Server&#41;](online-restore-sql-server.md) </span></span>  
 <span data-ttu-id="c6436-148">[Ripristino di pagine &#40;SQL Server&#41;](restore-pages-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="c6436-148">[Restore Pages &#40;SQL Server&#41;](restore-pages-sql-server.md) </span></span>  
 [<span data-ttu-id="c6436-149">Ripristini a fasi &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="c6436-149">Piecemeal Restores &#40;SQL Server&#41;</span></span>](piecemeal-restores-sql-server.md)  
  
  
