---
title: Modificare una funzione di partizione | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
ms.assetid: ae5bfc09-f27a-4ea9-9518-485278b11674
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: bf14e633e62839b1abca7f38f833efab933c18f0
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87713100"
---
# <a name="modify-a-partition-function"></a><span data-ttu-id="4a24a-102">Modificare una funzione di partizione</span><span class="sxs-lookup"><span data-stu-id="4a24a-102">Modify a Partition Function</span></span>
  <span data-ttu-id="4a24a-103">È possibile modificare la modalità di partizionamento di una tabella o di un indice in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] aggiungendo o sottraendo, con incrementi di 1, il numero di partizioni specificate nella funzione di partizione della tabella o dell'indice partizionato tramite [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="4a24a-103">You can change the way a table or index is partitioned in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by adding or subtracting the number of partitions specified, in increments of 1, in the partition function of the partitioned table or index by using [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span> <span data-ttu-id="4a24a-104">L'aggiunta di una partizione consiste nel "suddividere" una partizione esistente in due partizioni e nel ridefinire i limiti delle nuove partizioni.</span><span class="sxs-lookup"><span data-stu-id="4a24a-104">When you add a partition, you do so by "splitting" an existing partition into two partitions and redefining the boundaries of the new partitions.</span></span> <span data-ttu-id="4a24a-105">L'eliminazione di una partizione consiste nell'"unire" i limiti di due partizioni in modo da ottenerne una.</span><span class="sxs-lookup"><span data-stu-id="4a24a-105">When you drop a partition, you do so by "merging" the boundaries of two partitions into one.</span></span> <span data-ttu-id="4a24a-106">L'ultima operazione consiste nel ripopolare una partizione lasciando l'altra non assegnata.</span><span class="sxs-lookup"><span data-stu-id="4a24a-106">This last action repopulates one partition and leaves the other partition unassigned.</span></span>  
  
> [!CAUTION]  
>  <span data-ttu-id="4a24a-107">La stessa funzione di partizione può essere utilizzata da più tabelle o indici.</span><span class="sxs-lookup"><span data-stu-id="4a24a-107">More than one table or index can use the same partition function.</span></span> <span data-ttu-id="4a24a-108">La modifica di una funzione di partizione viene applicata a tutti gli elementi in un'unica transazione.</span><span class="sxs-lookup"><span data-stu-id="4a24a-108">When you modify a partition function, you affect all of them in a single transaction.</span></span> <span data-ttu-id="4a24a-109">Controllare le dipendenze della funzione di partizione prima di modificarla.</span><span class="sxs-lookup"><span data-stu-id="4a24a-109">Check the partition function's dependencies before modifying it.</span></span>  
  
 <span data-ttu-id="4a24a-110">**Contenuto dell'articolo**</span><span class="sxs-lookup"><span data-stu-id="4a24a-110">**In This Topic**</span></span>  
  
-   <span data-ttu-id="4a24a-111">**Prima di iniziare:**</span><span class="sxs-lookup"><span data-stu-id="4a24a-111">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="4a24a-112">Limitazioni e restrizioni</span><span class="sxs-lookup"><span data-stu-id="4a24a-112">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="4a24a-113">Sicurezza</span><span class="sxs-lookup"><span data-stu-id="4a24a-113">Security</span></span>](#Security)  
  
-   <span data-ttu-id="4a24a-114">**Per modificare una funzione di partizione utilizzando:**</span><span class="sxs-lookup"><span data-stu-id="4a24a-114">**To modify a partition function, using:**</span></span>  
  
     [<span data-ttu-id="4a24a-115">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="4a24a-115">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="4a24a-116">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="4a24a-116">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="4a24a-117">Prima di iniziare</span><span class="sxs-lookup"><span data-stu-id="4a24a-117">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="4a24a-118">Limitazioni e restrizioni</span><span class="sxs-lookup"><span data-stu-id="4a24a-118">Limitations and Restrictions</span></span>  
  
-   <span data-ttu-id="4a24a-119">L'istruzione ALTER PARTITION FUNCTION può essere utilizzata solo per suddividere una partizione in due o per unire due partizioni in una.</span><span class="sxs-lookup"><span data-stu-id="4a24a-119">ALTER PARTITION FUNCTION can only be used for splitting one partition into two, or for merging two partitions into one.</span></span> <span data-ttu-id="4a24a-120">Per modificare la modalità di partizionamento di una tabella o un indice, ad esempio da 10 partizioni a 5, è possibile utilizzare una delle opzioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="4a24a-120">To change the way a table or index is partitioned (from 10 partitions to 5, for example), you can use any one of the following options:</span></span>  
  
    -   <span data-ttu-id="4a24a-121">Creare una nuova tabella partizionata utilizzando la funzione di partizione desiderata e quindi inserire i dati della vecchia tabella in quella nuova utilizzando un'istruzione INSERT INTO ... SELECT FROM [!INCLUDE[tsql](../../includes/tsql-md.md)] o la **Gestione guidata partizione** in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="4a24a-121">Create a new partitioned table with the desired partition function, and then insert the data from the old table into the new table by using either an INSERT INTO ... SELECT FROM [!INCLUDE[tsql](../../includes/tsql-md.md)] statement or the **Manage Partition Wizard** in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span></span>  
  
    -   <span data-ttu-id="4a24a-122">Creazione di un indice cluster partizionato su un heap.</span><span class="sxs-lookup"><span data-stu-id="4a24a-122">Create a partitioned clustered index on a heap.</span></span>  
  
        > [!NOTE]  
        >  <span data-ttu-id="4a24a-123">L'eliminazione di un indice cluster partizionato ha come risultato un heap partizionato.</span><span class="sxs-lookup"><span data-stu-id="4a24a-123">Dropping a partitioned clustered index results in a partitioned heap.</span></span>  
  
    -   <span data-ttu-id="4a24a-124">Eliminazione e ricompilazione di un indice partizionato esistente mediante l'utilizzo dell'istruzione [!INCLUDE[tsql](../../includes/tsql-md.md)] CREATE INDEX con la clausola DROP EXISTING = ON.</span><span class="sxs-lookup"><span data-stu-id="4a24a-124">Drop and rebuild an existing partitioned index by using the [!INCLUDE[tsql](../../includes/tsql-md.md)] CREATE INDEX statement with the DROP EXISTING = ON clause.</span></span>  
  
    -   <span data-ttu-id="4a24a-125">Esecuzione di una sequenza di istruzioni ALTER PARTITION FUNCTION.</span><span class="sxs-lookup"><span data-stu-id="4a24a-125">Perform a sequence of ALTER PARTITION FUNCTION statements.</span></span>  
  
-   [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="4a24a-126">non fornisce il supporto di replica per la modifica di una funzione di partizione.</span><span class="sxs-lookup"><span data-stu-id="4a24a-126">does not provide replication support for modifying a partition function.</span></span> <span data-ttu-id="4a24a-127">Se si desidera apportare modifiche a una funzione di partizione nel database di pubblicazione, è necessario procedere manualmente nel database di sottoscrizione.</span><span class="sxs-lookup"><span data-stu-id="4a24a-127">If you want to make changes to a partition function in the publication database, you must do this manually in the subscription database.</span></span>  
  
-   <span data-ttu-id="4a24a-128">Tutti i filegroup interessati dall'istruzione ALTER PARTITION FUNCTION devono essere online.</span><span class="sxs-lookup"><span data-stu-id="4a24a-128">All filegroups that are affected by ALTER PARTITION FUNCTION must be online.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="4a24a-129">Sicurezza</span><span class="sxs-lookup"><span data-stu-id="4a24a-129">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="4a24a-130">Autorizzazioni</span><span class="sxs-lookup"><span data-stu-id="4a24a-130">Permissions</span></span>  
 <span data-ttu-id="4a24a-131">Per eseguire l'istruzione ALTER PARTITION FUNCTION, è necessario utilizzare le autorizzazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="4a24a-131">Any one of the following permissions can be used to execute ALTER PARTITION FUNCTION:</span></span>  
  
-   <span data-ttu-id="4a24a-132">Autorizzazione ALTER ANY DATASPACE.</span><span class="sxs-lookup"><span data-stu-id="4a24a-132">ALTER ANY DATASPACE permission.</span></span> <span data-ttu-id="4a24a-133">Questa autorizzazione viene concessa per impostazione predefinita al ruolo predefinito del server **sysadmin** e ai ruoli predefiniti del database **db_owner** e **db_ddladmin** .</span><span class="sxs-lookup"><span data-stu-id="4a24a-133">This permission defaults to members of the **sysadmin** fixed server role and the **db_owner** and **db_ddladmin** fixed database roles.</span></span>  
  
-   <span data-ttu-id="4a24a-134">Autorizzazione CONTROL o ALTER nel database in cui la funzione di partizione è stata creata.</span><span class="sxs-lookup"><span data-stu-id="4a24a-134">CONTROL or ALTER permission on the database in which the partition function was created.</span></span>  
  
-   <span data-ttu-id="4a24a-135">Autorizzazione CONTROL SERVER o ALTER ANY DATABASE nel server del database in cui la funzione di partizione è stata creata.</span><span class="sxs-lookup"><span data-stu-id="4a24a-135">CONTROL SERVER or ALTER ANY DATABASE permission on the server of the database in which the partition function was created.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="4a24a-136">Con SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="4a24a-136">Using SQL Server Management Studio</span></span>  
 <span data-ttu-id="4a24a-137">**Per modificare una funzione di partizione:**</span><span class="sxs-lookup"><span data-stu-id="4a24a-137">**To modify a partition function:**</span></span>  
  
 <span data-ttu-id="4a24a-138">Non è possibile eseguire questa azione specifica tramite [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="4a24a-138">This specific action cannot be performed using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span></span> <span data-ttu-id="4a24a-139">Per modificare una funzione di partizione, è innanzitutto necessario eliminare la funzione e crearne quindi una nuova con le proprietà desiderate tramite la Creazione guidata partizione.</span><span class="sxs-lookup"><span data-stu-id="4a24a-139">In order to modify a partition function, you must first delete the function and then create a new one with the desired properties using the Create Partition Wizard.</span></span> <span data-ttu-id="4a24a-140">Per ulteriori informazioni, vedere</span><span class="sxs-lookup"><span data-stu-id="4a24a-140">For more information, see</span></span>  
  
#### <a name="to-delete-a-partition-function"></a><span data-ttu-id="4a24a-141">Per eliminare una funzione di partizione</span><span class="sxs-lookup"><span data-stu-id="4a24a-141">To delete a partition function</span></span>  
  
1.  <span data-ttu-id="4a24a-142">Espandere il database in cui si desidera eliminare la funzione di partizione ed espandere quindi la cartella **Archiviazione** .</span><span class="sxs-lookup"><span data-stu-id="4a24a-142">Expand the database where you want to delete the partition function and then expand the **Storage** folder.</span></span>  
  
2.  <span data-ttu-id="4a24a-143">Espandere la cartella **Funzioni di partizione** .</span><span class="sxs-lookup"><span data-stu-id="4a24a-143">Expand the **Partition Functions** folder.</span></span>  
  
3.  <span data-ttu-id="4a24a-144">Fare clic con il pulsante destro del mouse sulla funzione di partizione che si vuole eliminare e scegliere **Elimina**.</span><span class="sxs-lookup"><span data-stu-id="4a24a-144">Right-click the partition function you want to delete and select **Delete**.</span></span>  
  
4.  <span data-ttu-id="4a24a-145">Nella finestra di dialogo **Elimina oggetto** verificare che venga selezionata la funzione di partizione corretta, quindi fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="4a24a-145">In the **Delete Object** dialog box, ensure that the correct partition function is selected, and then click **OK**.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="4a24a-146">Con Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="4a24a-146">Using Transact-SQL</span></span>  
  
#### <a name="to-split-a-single-partition-into-two-partitions"></a><span data-ttu-id="4a24a-147">Per suddividere una singola partizione in due partizioni</span><span class="sxs-lookup"><span data-stu-id="4a24a-147">To split a single partition into two partitions</span></span>  
  
1.  <span data-ttu-id="4a24a-148">In **Esplora oggetti**connettersi a un'istanza del [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="4a24a-148">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="4a24a-149">Sulla barra Standard fare clic su **Nuova query**.</span><span class="sxs-lookup"><span data-stu-id="4a24a-149">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="4a24a-150">Copiare e incollare l'esempio seguente nella finestra Query, quindi fare clic su **Esegui**.</span><span class="sxs-lookup"><span data-stu-id="4a24a-150">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```  
    -- Look for a previous version of the partition function "myRangePF1" and deletes it if it is found.  
    IF EXISTS (SELECT * FROM sys.partition_functions  
        WHERE name = 'myRangePF1')  
        DROP PARTITION FUNCTION myRangePF1;  
    GO  
    -- Create a new partition function called "myRangePF1" that partitions a table into four partitions.  
    CREATE PARTITION FUNCTION myRangePF1 (int)  
    AS RANGE LEFT FOR VALUES ( 1, 100, 1000 );  
    GO  
    --Split the partition between boundary_values 100 and 1000  
    --to create two partitions between boundary_values 100 and 500  
    --and between boundary_values 500 and 1000.  
    ALTER PARTITION FUNCTION myRangePF1 ()  
    SPLIT RANGE (500);  
    ```  
  
#### <a name="to-merge-two-partitions-into-one-partition"></a><span data-ttu-id="4a24a-151">Per unire due partizioni in una partizione</span><span class="sxs-lookup"><span data-stu-id="4a24a-151">To merge two partitions into one partition</span></span>  
  
1.  <span data-ttu-id="4a24a-152">In **Esplora oggetti**connettersi a un'istanza del [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="4a24a-152">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="4a24a-153">Sulla barra Standard fare clic su **Nuova query**.</span><span class="sxs-lookup"><span data-stu-id="4a24a-153">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="4a24a-154">Copiare e incollare l'esempio seguente nella finestra Query, quindi fare clic su **Esegui**.</span><span class="sxs-lookup"><span data-stu-id="4a24a-154">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```  
    -- Look for a previous version of the partition function "myRangePF1" and deletes it if it is found.  
    IF EXISTS (SELECT * FROM sys.partition_functions  
        WHERE name = 'myRangePF1')  
        DROP PARTITION FUNCTION myRangePF1;  
    GO  
    -- Create a new partition function called "myRangePF1" that partitions a table into four partitions.  
    CREATE PARTITION FUNCTION myRangePF1 (int)  
    AS RANGE LEFT FOR VALUES ( 1, 100, 1000 );  
    GO  
    --Merge the partitions between boundary_values 1 and 100  
    --and between boundary_values 100 and 1000 to create one partition  
    --between boundary_values 1 and 1000.  
    ALTER PARTITION FUNCTION myRangePF1 ()  
    MERGE RANGE (100);  
    ```  
  
 <span data-ttu-id="4a24a-155">Per altre informazioni, vedere [ALTER PARTITION FUNCTION &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-partition-function-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="4a24a-155">For more information, see [ALTER PARTITION FUNCTION &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-partition-function-transact-sql).</span></span>  
  
  
