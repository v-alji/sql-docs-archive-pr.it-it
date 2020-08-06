---
title: Modificare uno schema di partizione | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
ms.assetid: 515de63f-dfc5-434d-9adb-f3b5992f745a
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: d57984228e23143d2061df6bf447f978f9bd3c46
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87635001"
---
# <a name="modify-a-partition-scheme"></a><span data-ttu-id="2c7b2-102">Modificare uno schema di partizione</span><span class="sxs-lookup"><span data-stu-id="2c7b2-102">Modify a Partition Scheme</span></span>
  <span data-ttu-id="2c7b2-103">È possibile modificare uno schema di partizione in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] designando un filegroup in cui sia inclusa la partizione successiva aggiunta a una tabella partizionata utilizzando [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] o [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="2c7b2-103">You can modify a partition scheme in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by designating a filegroup to hold the next partition that is added to a partitioned table using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span> <span data-ttu-id="2c7b2-104">A tale scopo, è necessario assegnare la proprietà NEXT USED a un filegroup.</span><span class="sxs-lookup"><span data-stu-id="2c7b2-104">You do this by assigning the NEXT USED property to a filegroup.</span></span> <span data-ttu-id="2c7b2-105">È possibile assegnare la proprietà NEXT USED a un filegroup vuoto o a uno che contiene già una partizione.</span><span class="sxs-lookup"><span data-stu-id="2c7b2-105">You can assign the NEXT USED property to an empty filegroup or to one that already holds a partition.</span></span> <span data-ttu-id="2c7b2-106">In altri termini, in un filegroup possono essere incluse più partizioni.</span><span class="sxs-lookup"><span data-stu-id="2c7b2-106">In other words, a filegroup can hold more than one partition.</span></span>  
  
 <span data-ttu-id="2c7b2-107">**Contenuto dell'articolo**</span><span class="sxs-lookup"><span data-stu-id="2c7b2-107">**In This Topic**</span></span>  
  
-   <span data-ttu-id="2c7b2-108">**Prima di iniziare:**</span><span class="sxs-lookup"><span data-stu-id="2c7b2-108">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="2c7b2-109">Limitazioni e restrizioni</span><span class="sxs-lookup"><span data-stu-id="2c7b2-109">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="2c7b2-110">Sicurezza</span><span class="sxs-lookup"><span data-stu-id="2c7b2-110">Security</span></span>](#Security)  
  
-   <span data-ttu-id="2c7b2-111">**Per creare una tabella o un indice partizionato tramite:**</span><span class="sxs-lookup"><span data-stu-id="2c7b2-111">**To create a partitioned table or index, using:**</span></span>  
  
     [<span data-ttu-id="2c7b2-112">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="2c7b2-112">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="2c7b2-113">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="2c7b2-113">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="2c7b2-114">Prima di iniziare</span><span class="sxs-lookup"><span data-stu-id="2c7b2-114">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="2c7b2-115">Limitazioni e restrizioni</span><span class="sxs-lookup"><span data-stu-id="2c7b2-115">Limitations and Restrictions</span></span>  
 <span data-ttu-id="2c7b2-116">Tutti i filegroup a cui viene applicata l'istruzione ALTER PARTITION SCHEME devono essere online.</span><span class="sxs-lookup"><span data-stu-id="2c7b2-116">Any filegroup affected by ALTER PARTITION SCHEME must be online.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="2c7b2-117">Sicurezza</span><span class="sxs-lookup"><span data-stu-id="2c7b2-117">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="2c7b2-118">Autorizzazioni</span><span class="sxs-lookup"><span data-stu-id="2c7b2-118">Permissions</span></span>  
 <span data-ttu-id="2c7b2-119">Per eseguire l'istruzione ALTER PARTITION SCHEME, è possibile utilizzare le autorizzazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="2c7b2-119">The following permissions can be used to execute ALTER PARTITION SCHEME:</span></span>  
  
-   <span data-ttu-id="2c7b2-120">Autorizzazione ALTER ANY DATASPACE.</span><span class="sxs-lookup"><span data-stu-id="2c7b2-120">ALTER ANY DATASPACE permission.</span></span> <span data-ttu-id="2c7b2-121">Questa autorizzazione viene concessa per impostazione predefinita al ruolo predefinito del server **sysadmin** e ai ruoli predefiniti del database **db_owner** e **db_ddladmin** .</span><span class="sxs-lookup"><span data-stu-id="2c7b2-121">This permission defaults to members of the **sysadmin** fixed server role and the **db_owner** and **db_ddladmin** fixed database roles.</span></span>  
  
-   <span data-ttu-id="2c7b2-122">Autorizzazione CONTROL o ALTER per il database nel quale viene creato lo schema di partizione.</span><span class="sxs-lookup"><span data-stu-id="2c7b2-122">CONTROL or ALTER permission on the database in which the partition scheme was created.</span></span>  
  
-   <span data-ttu-id="2c7b2-123">Autorizzazione CONTROL SERVER o ALTER ANY DATABASE per il server del database nel quale è stato creato lo schema di partizione.</span><span class="sxs-lookup"><span data-stu-id="2c7b2-123">CONTROL SERVER or ALTER ANY DATABASE permission on the server of the database in which the partition scheme was created.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="2c7b2-124">Con SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="2c7b2-124">Using SQL Server Management Studio</span></span>  
 <span data-ttu-id="2c7b2-125">**Per modificare uno schema di partizione:**</span><span class="sxs-lookup"><span data-stu-id="2c7b2-125">**To modify a partition scheme:**</span></span>  
  
 <span data-ttu-id="2c7b2-126">Non è possibile eseguire questa azione specifica tramite [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="2c7b2-126">This specific action cannot be performed using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span></span> <span data-ttu-id="2c7b2-127">Per modificare uno schema di partizione, è innanzitutto necessario eliminare lo schema e crearne quindi uno nuovo con le proprietà desiderate tramite la Creazione guidata partizione.</span><span class="sxs-lookup"><span data-stu-id="2c7b2-127">In order to modify a partition scheme, you must first delete the scheme and then create a new one with the desired properties using the Create Partition Wizard.</span></span> <span data-ttu-id="2c7b2-128">Per altre informazioni, vedere [creare tabelle e indici partizionati usando SQL Server Management Studio](create-partitioned-tables-and-indexes.md#SSMSProcedure) in **creare tabelle e indici partizionati**.</span><span class="sxs-lookup"><span data-stu-id="2c7b2-128">For more information, see [Create Partitioned Tables and Indexes Using SQL Server Management Studio](create-partitioned-tables-and-indexes.md#SSMSProcedure) under **Create Partitioned Tables and Indexes**.</span></span>  
  
#### <a name="to-delete-a-partition-scheme"></a><span data-ttu-id="2c7b2-129">Per eliminare uno schema di partizione</span><span class="sxs-lookup"><span data-stu-id="2c7b2-129">To delete a partition scheme</span></span>  
  
1.  <span data-ttu-id="2c7b2-130">Fare clic sul segno più per espandere il database in cui si desidera eliminare lo schema di partizione.</span><span class="sxs-lookup"><span data-stu-id="2c7b2-130">Click the plus sign to expand the database where you want to delete the partition scheme.</span></span>  
  
2.  <span data-ttu-id="2c7b2-131">Fare clic sul segno più per espandere la cartella **Archiviazione** .</span><span class="sxs-lookup"><span data-stu-id="2c7b2-131">Click the plus sign to expand the **Storage** folder.</span></span>  
  
3.  <span data-ttu-id="2c7b2-132">Fare clic sul segno più per espandere la cartella **Schemi di partizione** .</span><span class="sxs-lookup"><span data-stu-id="2c7b2-132">Click the plus sign to expand the **Partition Schemes** folder.</span></span>  
  
4.  <span data-ttu-id="2c7b2-133">Fare clic con il pulsante destro del mouse sullo schema di partizione che si vuole eliminare e scegliere **Elimina**.</span><span class="sxs-lookup"><span data-stu-id="2c7b2-133">Right-click the partition scheme you want to delete and select **Delete**.</span></span>  
  
5.  <span data-ttu-id="2c7b2-134">Nella finestra di dialogo **Elimina oggetto** verificare che sia selezionato lo schema di partizione corretto, quindi fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="2c7b2-134">In the **Delete Object** dialog box, ensure that the correct partition scheme is selected, and then click **OK**.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="2c7b2-135">Con Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="2c7b2-135">Using Transact-SQL</span></span>  
  
#### <a name="to-modify-a-partition-scheme"></a><span data-ttu-id="2c7b2-136">Per modificare uno schema di partizione</span><span class="sxs-lookup"><span data-stu-id="2c7b2-136">To modify a partition scheme</span></span>  
  
1.  <span data-ttu-id="2c7b2-137">In **Esplora oggetti**connettersi a un'istanza del [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="2c7b2-137">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="2c7b2-138">Sulla barra Standard fare clic su **Nuova query**.</span><span class="sxs-lookup"><span data-stu-id="2c7b2-138">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="2c7b2-139">Copiare e incollare l'esempio seguente nella finestra Query, quindi fare clic su **Esegui**.</span><span class="sxs-lookup"><span data-stu-id="2c7b2-139">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```  
    USE AdventureWorks2012;  
    GO  
    -- add five new filegroups to the AdventureWorks2012 database  
    ALTER DATABASE AdventureWorks2012  
    ADD FILEGROUP test1fg;  
    GO  
    ALTER DATABASE AdventureWorks2012  
    ADD FILEGROUP test2fg;  
    GO  
    ALTER DATABASE AdventureWorks2012  
    ADD FILEGROUP test3fg;  
    GO  
    ALTER DATABASE AdventureWorks2012  
    ADD FILEGROUP test4fg;  
    GO  
    ALTER DATABASE AdventureWorks2012  
    ADD FILEGROUP test5fg;  
    GO  
    -- if the "myRangePF1" partition function and the "myRangePS1" partition scheme exist,  
    -- drop them from the AdventureWorks2012 database  
    IF EXISTS (SELECT * FROM sys.partition_functions  
        WHERE name = 'myRangePF1')  
    DROP PARTITION FUNCTION myRangePF1;  
    GO  
    IF EXISTS (SELECT * FROM sys.partition_schemes  
        WHERE name = 'myRangePS1')  
    DROP PARTITION SCHEME myRangePS1;  
    GO  
    -- create the new partition function "myRangePF1" with four partition groups  
    CREATE PARTITION FUNCTION myRangePF1 (int)  
    AS RANGE LEFT FOR VALUES ( 1, 100, 1000 );  
    GO  
    -- create the new partition scheme "myRangePS1"that will use   
    -- the "myRangePF1" partition function with five file groups.  
    -- The last filegroup, "test5fg," will be kept empty but marked  
    -- as the next used filegroup in the partition scheme.  
    CREATE PARTITION SCHEME myRangePS1  
    AS PARTITION myRangePF1  
    TO (test1fg, test2fg, test3fg, test4fg, test5fg);  
    GO  
    --Split "myRangePS1" between boundary_values 100 and 1000  
    --to create two partitions between boundary_values 100 and 500  
    --and between boundary_values 500 and 1000.  
    ALTER PARTITION FUNCTION myRangePF1 ()  
    SPLIT RANGE (500);  
    GO  
    -- Allow the "myRangePS1" partition scheme to use the filegroup "test5fg"  
    -- for the partition with boundary_values of 100 and 500  
    ALTER PARTITION SCHEME myRangePS1  
    NEXT USED test5fg;  
    GO  
    ```  
  
 <span data-ttu-id="2c7b2-140">Per altre informazioni, vedere [ALTER PARTITION SCHEME &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-partition-scheme-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="2c7b2-140">For more information, see [ALTER PARTITION SCHEME &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-partition-scheme-transact-sql).</span></span>  
  
  
