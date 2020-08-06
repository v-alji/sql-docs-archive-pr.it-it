---
title: Configurare operazioni parallele sugli indici | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: table-view-index
ms.topic: conceptual
helpviewer_keywords:
- index parallel operations [SQL Server]
- processors [SQL Server], parallel index operations
- max degree of parallelism option
- MAXDOP index option, parallel index operations
- parallel index operations [SQL Server]
ms.assetid: 8ec8c71e-5fc1-443a-92da-136ee3fc7f88
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 8831aadae15af03a05f4ab03cfe514e54566df1f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87624145"
---
# <a name="configure-parallel-index-operations"></a><span data-ttu-id="6027b-102">Configurazione di operazioni parallele sugli indici</span><span class="sxs-lookup"><span data-stu-id="6027b-102">Configure Parallel Index Operations</span></span>
  <span data-ttu-id="6027b-103">In questo argomento viene definito il massimo grado di parallelismo e viene spiegato come modificare questa impostazione in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] tramite [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] o [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="6027b-103">This topic defines max degree of parallelism and explains how to modify this setting in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span> <span data-ttu-id="6027b-104">Nei computer multiprocessore che eseguono [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Enterprise Edition o versioni successive, le istruzioni per gli indici, proprio come le altre query, possono utilizzare più processori per eseguire le operazioni di analisi, ordinamento e indicizzazione associate all'istruzione.</span><span class="sxs-lookup"><span data-stu-id="6027b-104">On multiprocessor computers that are running [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Enterprise or higher, index statements may use multiple processors to perform the scan, sort, and index operations associated with the index statement just like other queries do.</span></span> <span data-ttu-id="6027b-105">Il numero di processori usati per eseguire una singola istruzione per gli indici è determinato dall'opzione di configurazione [max degree of parallelism](../../database-engine/configure-windows/configure-the-max-degree-of-parallelism-server-configuration-option.md) , dal carico di lavoro corrente e dalle statistiche dell'indice.</span><span class="sxs-lookup"><span data-stu-id="6027b-105">The number of processors used to run a single index statement is determined by the [max degree of parallelism](../../database-engine/configure-windows/configure-the-max-degree-of-parallelism-server-configuration-option.md) configuration option, the current workload, and the index statistics.</span></span> <span data-ttu-id="6027b-106">L'opzione max degree of parallelism determina il numero massimo di processori da utilizzare nell'esecuzione di piani paralleli.</span><span class="sxs-lookup"><span data-stu-id="6027b-106">The max degree of parallelism option determines the maximum number of processors to use in parallel plan execution.</span></span> <span data-ttu-id="6027b-107">Se in [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] viene rilevato che il sistema è occupato, il grado di parallelismo dell'operazione di indice viene automaticamente ridotto prima che l'esecuzione dell'istruzione venga avviata.</span><span class="sxs-lookup"><span data-stu-id="6027b-107">If the [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] detects that the system is busy, the degree of parallelism of the index operation is automatically reduced before statement execution starts.</span></span> <span data-ttu-id="6027b-108">Il [!INCLUDE[ssDE](../../includes/ssde-md.md)] consente inoltre di ridurre il grado di parallelismo se la colonna chiave iniziale di un indice non partizionato ha un numero limitato di valori distinti o se la frequenza di ciascun valore distinto varia in modo significativo.</span><span class="sxs-lookup"><span data-stu-id="6027b-108">The [!INCLUDE[ssDE](../../includes/ssde-md.md)] can also reduce the degree of parallelism if the leading key column of a non-partitioned index has a limited number of distinct values or the frequency of each distinct value varies significantly.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="6027b-109">Le operazioni parallele sugli indici sono disponibili solo in alcune edizioni di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="6027b-109">Parallel index operations are not available in every [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] edition.</span></span> <span data-ttu-id="6027b-110">Per ulteriori informazioni, vedere [Features Supported by the Editions of SQL Server 2014](../../getting-started/features-supported-by-the-editions-of-sql-server-2014.md).</span><span class="sxs-lookup"><span data-stu-id="6027b-110">For more information, see [Features Supported by the Editions of SQL Server 2014](../../getting-started/features-supported-by-the-editions-of-sql-server-2014.md).</span></span>  
  
 <span data-ttu-id="6027b-111">**Contenuto dell'articolo**</span><span class="sxs-lookup"><span data-stu-id="6027b-111">**In This Topic**</span></span>  
  
-   <span data-ttu-id="6027b-112">**Prima di iniziare:**</span><span class="sxs-lookup"><span data-stu-id="6027b-112">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="6027b-113">Limitazioni e restrizioni</span><span class="sxs-lookup"><span data-stu-id="6027b-113">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="6027b-114">Sicurezza</span><span class="sxs-lookup"><span data-stu-id="6027b-114">Security</span></span>](#Security)  
  
-   <span data-ttu-id="6027b-115">**Per configurare l'opzione max degree of parallelism utilizzando:**</span><span class="sxs-lookup"><span data-stu-id="6027b-115">**To set the max degree of parallelism, using:**</span></span>  
  
     [<span data-ttu-id="6027b-116">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="6027b-116">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="6027b-117">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="6027b-117">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="6027b-118">Prima di iniziare</span><span class="sxs-lookup"><span data-stu-id="6027b-118">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="6027b-119">Limitazioni e restrizioni</span><span class="sxs-lookup"><span data-stu-id="6027b-119">Limitations and Restrictions</span></span>  
  
-   <span data-ttu-id="6027b-120">Il numero di processori utilizzati da Query Optimizer implica normalmente le prestazioni ottimali.</span><span class="sxs-lookup"><span data-stu-id="6027b-120">The number of processors that are used by the query optimizer typically provides optimal performance.</span></span> <span data-ttu-id="6027b-121">Tuttavia, operazioni come la creazione, la ricompilazione o l'eliminazione di indici di grandi dimensioni utilizzano molte risorse e possono determinare una mancanza di risorse per le altre applicazioni e operazioni di database per la durata dell'operazione di indice.</span><span class="sxs-lookup"><span data-stu-id="6027b-121">However, operations such as creating, rebuilding, or dropping very large indexes are resource intensive and can cause insufficient resources for other applications and database operations for the duration of the index operation.</span></span> <span data-ttu-id="6027b-122">Quando si verifica questo problema, è possibile configurare manualmente il numero massimo di processori utilizzati per eseguire l'istruzione per l'indice limitando il numero di processori da utilizzare per l'operazione di indice.</span><span class="sxs-lookup"><span data-stu-id="6027b-122">When this problem occurs, you can manually configure the maximum number of processors that are used to run the index statement by limiting the number of processors to use for the index operation.</span></span>  
  
-   <span data-ttu-id="6027b-123">L'opzione di indice MAXDOP è prioritaria rispetto all'opzione di configurazione max degree of parallelism solo per la query che specifica tale opzione.</span><span class="sxs-lookup"><span data-stu-id="6027b-123">The MAXDOP index option overrides the max degree of parallelism configuration option only for the query specifying this option.</span></span> <span data-ttu-id="6027b-124">La tabella seguente elenca i valori integer validi che è possibile specificare con l'opzione di configurazione max degree of parallelism e l'opzione di indice MAXDOP.</span><span class="sxs-lookup"><span data-stu-id="6027b-124">The following table lists the valid integer values that can be specified with the max degree of parallelism configuration option and the MAXDOP index option.</span></span>  
  
    |<span data-ttu-id="6027b-125">Valore</span><span class="sxs-lookup"><span data-stu-id="6027b-125">Value</span></span>|<span data-ttu-id="6027b-126">Descrizione</span><span class="sxs-lookup"><span data-stu-id="6027b-126">Description</span></span>|  
    |-----------|-----------------|  
    |<span data-ttu-id="6027b-127">0</span><span class="sxs-lookup"><span data-stu-id="6027b-127">0</span></span>|<span data-ttu-id="6027b-128">Specifica che il server determina il numero di CPU utilizzate, a seconda del carico di lavoro del sistema corrente.</span><span class="sxs-lookup"><span data-stu-id="6027b-128">Specifies that the server determines the number of CPUs that are used, depending on the current system workload.</span></span> <span data-ttu-id="6027b-129">Si tratta del valore predefinito e dell'impostazione consigliata.</span><span class="sxs-lookup"><span data-stu-id="6027b-129">This is the default value and recommended setting.</span></span>|  
    |<span data-ttu-id="6027b-130">1</span><span class="sxs-lookup"><span data-stu-id="6027b-130">1</span></span>|<span data-ttu-id="6027b-131">Disattiva la generazione di piani paralleli.</span><span class="sxs-lookup"><span data-stu-id="6027b-131">Suppresses parallel plan generation.</span></span> <span data-ttu-id="6027b-132">L'operazione verrà eseguita in modo serializzato.</span><span class="sxs-lookup"><span data-stu-id="6027b-132">The operation will be executed serially.</span></span>|  
    |<span data-ttu-id="6027b-133">2-64</span><span class="sxs-lookup"><span data-stu-id="6027b-133">2-64</span></span>|<span data-ttu-id="6027b-134">Limita il numero di processori al valore specificato.</span><span class="sxs-lookup"><span data-stu-id="6027b-134">Limits the number of processors to the specified value.</span></span> <span data-ttu-id="6027b-135">È possibile che il numero possa essere ridotto in base al carico di lavoro corrente.</span><span class="sxs-lookup"><span data-stu-id="6027b-135">Fewer processors may be used depending on the current workload.</span></span> <span data-ttu-id="6027b-136">Se viene specificato un valore maggiore di quello delle CPU disponibili, viene utilizzato l'effettivo numero di CPU disponibili.</span><span class="sxs-lookup"><span data-stu-id="6027b-136">If a value larger than the number of available CPUs is specified, the actual number of available CPUs is used.</span></span>|  
  
-   <span data-ttu-id="6027b-137">L'esecuzione dell'indice in parallelo e l'opzione di indice MAXDOP si applicano alle istruzioni [!INCLUDE[tsql](../../includes/tsql-md.md)] seguenti:</span><span class="sxs-lookup"><span data-stu-id="6027b-137">Parallel index execution and the MAXDOP index option apply to the following [!INCLUDE[tsql](../../includes/tsql-md.md)] statements:</span></span>  
  
    -   <span data-ttu-id="6027b-138">CREATE INDEX</span><span class="sxs-lookup"><span data-stu-id="6027b-138">CREATE INDEX</span></span>  
  
    -   <span data-ttu-id="6027b-139">ALTER INDEX REBUILD</span><span class="sxs-lookup"><span data-stu-id="6027b-139">ALTER INDEX REBUILD</span></span>  
  
    -   <span data-ttu-id="6027b-140">DROP INDEX (si applica solo agli indici cluster).</span><span class="sxs-lookup"><span data-stu-id="6027b-140">DROP INDEX (This applies to clustered indexes only.)</span></span>  
  
    -   <span data-ttu-id="6027b-141">ALTER TABLE ADD (indice) CONSTRAINT</span><span class="sxs-lookup"><span data-stu-id="6027b-141">ALTER TABLE ADD (index) CONSTRAINT</span></span>  
  
    -   <span data-ttu-id="6027b-142">ALTER TABLE DROP (indice cluster) CONSTRAINT</span><span class="sxs-lookup"><span data-stu-id="6027b-142">ALTER TABLE DROP (clustered index) CONSTRAINT</span></span>  
  
-   <span data-ttu-id="6027b-143">L'opzione di indice MAXDOP non può essere specificata nell'istruzione ALTER INDEX REORGANIZE.</span><span class="sxs-lookup"><span data-stu-id="6027b-143">The MAXDOP index option cannot be specified in the ALTER INDEX REORGANIZE statement.</span></span>  
  
-   <span data-ttu-id="6027b-144">I requisiti di memoria per le operazioni di indice partizionato che richiedono l'ordinamento possono essere maggiori se Query Optimizer applica i gradi di parallelismo all'operazione di compilazione.</span><span class="sxs-lookup"><span data-stu-id="6027b-144">Memory requirements for partitioned index operations that require sorting can be greater if the query optimizer applies degrees of parallelism to the build operation.</span></span> <span data-ttu-id="6027b-145">Maggiori i gradi di parallelismo, maggiori i requisiti di memoria.</span><span class="sxs-lookup"><span data-stu-id="6027b-145">The higher the degrees of parallelism, the greater the memory requirement is.</span></span> <span data-ttu-id="6027b-146">Per ulteriori informazioni, vedere [Partitioned Tables and Indexes](../partitions/partitioned-tables-and-indexes.md).</span><span class="sxs-lookup"><span data-stu-id="6027b-146">For more information, see [Partitioned Tables and Indexes](../partitions/partitioned-tables-and-indexes.md).</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="6027b-147">Sicurezza</span><span class="sxs-lookup"><span data-stu-id="6027b-147">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="6027b-148">Autorizzazioni</span><span class="sxs-lookup"><span data-stu-id="6027b-148">Permissions</span></span>  
 <span data-ttu-id="6027b-149">È richiesta l'autorizzazione ALTER per la tabella o la vista.</span><span class="sxs-lookup"><span data-stu-id="6027b-149">Requires ALTER permission on the table or view.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="6027b-150">Utilizzo di SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="6027b-150">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-set-max-degree-of-parallelism-on-an-index"></a><span data-ttu-id="6027b-151">Per impostare l'opzione max degree of parallelism su un indice</span><span class="sxs-lookup"><span data-stu-id="6027b-151">To set max degree of parallelism on an index</span></span>  
  
1.  <span data-ttu-id="6027b-152">In Esplora oggetti fare clic sul segno più per espandere il database contenente la tabella in cui si desidera impostare l'opzione max degree of parallelism per un indice.</span><span class="sxs-lookup"><span data-stu-id="6027b-152">In Object Explorer, click the plus sign to expand the database that contains the table on which you want to set max degree of parallelism for an index.</span></span>  
  
2.  <span data-ttu-id="6027b-153">Espandere la cartella **Tabelle** .</span><span class="sxs-lookup"><span data-stu-id="6027b-153">Expand the **Tables** folder.</span></span>  
  
3.  <span data-ttu-id="6027b-154">Fare clic sul segno più per espandere la tabella in cui si desidera impostare l'opzione max degree of parallelism per un indice.</span><span class="sxs-lookup"><span data-stu-id="6027b-154">Click the plus sign to expand the table on which you want to set max degree of parallelism for an index.</span></span>  
  
4.  <span data-ttu-id="6027b-155">Espandere la cartella **Indici** .</span><span class="sxs-lookup"><span data-stu-id="6027b-155">Expand the **Indexes** folder.</span></span>  
  
5.  <span data-ttu-id="6027b-156">Fare clic con il pulsante destro del mouse sull'indice per cui si vuole impostare il massimo grado di parallelismo e scegliere **Proprietà**.</span><span class="sxs-lookup"><span data-stu-id="6027b-156">Right-click the index for which you want to set the max degree of parallelism and select **Properties**.</span></span>  
  
6.  <span data-ttu-id="6027b-157">In **Selezione pagina**selezionare **Opzioni**.</span><span class="sxs-lookup"><span data-stu-id="6027b-157">Under **Select a page**, select **Options**.</span></span>  
  
7.  <span data-ttu-id="6027b-158">Selezionare **Maximum degree of parallelism**e immettere un valore compreso tra 1 e 64.</span><span class="sxs-lookup"><span data-stu-id="6027b-158">Select **Maximum degree of parallelism**, and then enter some value between 1 and 64.</span></span>  
  
8.  <span data-ttu-id="6027b-159">Fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="6027b-159">Click **OK**.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="6027b-160">Uso di Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="6027b-160">Using Transact-SQL</span></span>  
  
#### <a name="to-set-max-degree-of-parallelism-on-an-existing-index"></a><span data-ttu-id="6027b-161">Per impostare l'opzione max degree of parallelism su un indice esistente</span><span class="sxs-lookup"><span data-stu-id="6027b-161">To set max degree of parallelism on an existing index</span></span>  
  
1.  <span data-ttu-id="6027b-162">In **Esplora oggetti**connettersi a un'istanza del [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="6027b-162">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="6027b-163">Sulla barra Standard fare clic su **Nuova query**.</span><span class="sxs-lookup"><span data-stu-id="6027b-163">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="6027b-164">Copiare e incollare l'esempio seguente nella finestra Query, quindi fare clic su **Esegui**.</span><span class="sxs-lookup"><span data-stu-id="6027b-164">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```  
    USE AdventureWorks2012;   
    GO  
    /*Alters the IX_ProductVendor_VendorID index on the Purchasing.ProductVendor table so that, if the server has eight or more processors, the Database Engine will limit the execution of the index operation to eight or fewer processors.  
    */  
    ALTER INDEX IX_ProductVendor_VendorID ON Purchasing.ProductVendor  
    REBUILD WITH (MAXDOP=8);   
    GO  
    ```  
  
 <span data-ttu-id="6027b-165">Per altre informazioni, vedere [ALTER INDEX &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-index-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="6027b-165">For more information, see [ALTER INDEX &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-index-transact-sql).</span></span>  
  
#### <a name="set-max-degree-of-parallelism-on-a-new-index"></a><span data-ttu-id="6027b-166">Impostare l'opzione max degree of parallelism su un nuovo indice</span><span class="sxs-lookup"><span data-stu-id="6027b-166">Set max degree of parallelism on a new index</span></span>  
  
1.  <span data-ttu-id="6027b-167">In **Esplora oggetti**connettersi a un'istanza del [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="6027b-167">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="6027b-168">Sulla barra Standard fare clic su **Nuova query**.</span><span class="sxs-lookup"><span data-stu-id="6027b-168">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="6027b-169">Copiare e incollare l'esempio seguente nella finestra Query, quindi fare clic su **Esegui**.</span><span class="sxs-lookup"><span data-stu-id="6027b-169">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```  
    USE AdventureWorks2012;  
    GO  
    CREATE INDEX IX_ProductVendor_NewVendorID   
    ON Purchasing.ProductVendor (BusinessEntityID)  
    WITH (MAXDOP=8);  
    GO  
    ```  
  
 <span data-ttu-id="6027b-170">Per altre informazioni, vedere [CREATE INDEX &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-index-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="6027b-170">For more information, see [CREATE INDEX &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-index-transact-sql).</span></span>  
  
  
