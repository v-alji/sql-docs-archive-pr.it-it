---
title: Estensioni a AdventureWorks per illustrare OLTP in memoria | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: in-memory-oltp
ms.topic: conceptual
ms.assetid: 0186b7f2-cead-4203-8360-b6890f37cde8
author: stevestein
ms.author: sstein
ms.openlocfilehash: 73a87751aa6cd4734f81b60cdd87a62939ba4ead
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87724107"
---
# <a name="extensions-to-adventureworks-to-demonstrate-in-memory-oltp"></a><span data-ttu-id="ef1d4-102">Estensioni a AdventureWorks per illustrare OLTP in memoria</span><span class="sxs-lookup"><span data-stu-id="ef1d4-102">Extensions to AdventureWorks to Demonstrate In-Memory OLTP</span></span>
    
## <a name="overview"></a><span data-ttu-id="ef1d4-103">Panoramica</span><span class="sxs-lookup"><span data-stu-id="ef1d4-103">Overview</span></span>  
 <span data-ttu-id="ef1d4-104">In questo esempio viene illustrata la nuova funzionalità di [!INCLUDE[hek_2](../includes/hek-2-md.md)] , che fa parte di [!INCLUDE[ssSQL14](../includes/sssql14-md.md)].</span><span class="sxs-lookup"><span data-stu-id="ef1d4-104">This sample showcases the new [!INCLUDE[hek_2](../includes/hek-2-md.md)] feature, which is part of [!INCLUDE[ssSQL14](../includes/sssql14-md.md)].</span></span> <span data-ttu-id="ef1d4-105">Vengono mostrate le nuove tabelle ottimizzate per la memoria e le nuove stored procedure compilate in modo nativo, utilizzabili per illustrare i vantaggi a livello di prestazioni di [!INCLUDE[hek_2](../includes/hek-2-md.md)].</span><span class="sxs-lookup"><span data-stu-id="ef1d4-105">It shows the new memory-optimized tables and natively-compiled stored procedures, and can be used to demonstrate performance benefits of [!INCLUDE[hek_2](../includes/hek-2-md.md)].</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="ef1d4-106">Per visualizzare questo argomento per SQL Server 2016, vedere [Estensioni a AdventureWorks per illustrare OLTP in memoria](https://msdn.microsoft.com/library/mt465764.aspx)</span><span class="sxs-lookup"><span data-stu-id="ef1d4-106">To view this topic for SQL Server 2016, see [Extensions to AdventureWorks to Demonstrate In-Memory OLTP](https://msdn.microsoft.com/library/mt465764.aspx)</span></span>  
  
 <span data-ttu-id="ef1d4-107">Nell'esempio viene eseguita la migrazione di 5 tabelle del database AdventureWorks a tabelle ottimizzate per la memoria. Inoltre, è incluso un carico di lavoro dimostrativo di ordini vendita.</span><span class="sxs-lookup"><span data-stu-id="ef1d4-107">The sample migrates 5 tables in the AdventureWorks database to memory-optimized, and it includes a demo workload for sales order processing.</span></span> <span data-ttu-id="ef1d4-108">Questo carico di lavoro dimostrativo può essere utilizzato per verificare i vantaggi a livello di prestazioni di [!INCLUDE[hek_2](../includes/hek-2-md.md)] nel server.</span><span class="sxs-lookup"><span data-stu-id="ef1d4-108">You can use this demo workload to see the performance benefit of using [!INCLUDE[hek_2](../includes/hek-2-md.md)] on your server.</span></span>  
  
 <span data-ttu-id="ef1d4-109">Nella descrizione dell'esempio vengono discussi i compromessi raggiunti quando si esegue la migrazione delle tabelle a [!INCLUDE[hek_2](../includes/hek-2-md.md)] per tener conto delle funzionalità non (ancora) supportate per le tabelle ottimizzate per la memoria in [!INCLUDE[ssSQL14](../includes/sssql14-md.md)].</span><span class="sxs-lookup"><span data-stu-id="ef1d4-109">In the description of the sample we discuss the tradeoffs that were made in migrating the tables to [!INCLUDE[hek_2](../includes/hek-2-md.md)] to account for the features that are not (yet) supported for memory-optimized tables in [!INCLUDE[ssSQL14](../includes/sssql14-md.md)].</span></span>  
  
 <span data-ttu-id="ef1d4-110">La documentazione di questo esempio è strutturata come segue:</span><span class="sxs-lookup"><span data-stu-id="ef1d4-110">The documentation of this sample is structured as follows:</span></span>  
  
-   <span data-ttu-id="ef1d4-111">[Prerequisiti](#Prerequisites) per l'installazione dell'esempio e l'esecuzione del carico di lavoro dimostrativo</span><span class="sxs-lookup"><span data-stu-id="ef1d4-111">[Prerequisites](#Prerequisites) for installing the sample and running the demo workload</span></span>  
  
-   <span data-ttu-id="ef1d4-112">Istruzioni per [Installazione dell'esempio di In-Memory OLTP basato su AdventureWorks](#InstallingtheIn-MemoryOLTPsamplebasedonAdventureWorks)</span><span class="sxs-lookup"><span data-stu-id="ef1d4-112">Instructions for [Installing the In-Memory OLTP sample based on AdventureWorks](#InstallingtheIn-MemoryOLTPsamplebasedonAdventureWorks)</span></span>  
  
-   <span data-ttu-id="ef1d4-113">[Descrizione delle tabelle e delle procedure di esempio](#Descriptionofthesampletablesandprocedures) : include le descrizioni delle tabelle e delle procedure aggiunte a AdventureWorks dall' [!INCLUDE[hek_2](../includes/hek-2-md.md)] esempio, oltre a considerazioni sulla migrazione di alcune delle tabelle originali di AdventureWorks a ottimizzate per la memoria</span><span class="sxs-lookup"><span data-stu-id="ef1d4-113">[Description of the sample tables and procedures](#Descriptionofthesampletablesandprocedures) - this includes descriptions of the tables and procedures added to AdventureWorks by the [!INCLUDE[hek_2](../includes/hek-2-md.md)] sample, as well as considerations for migrating some of the original AdventureWorks tables to memory-optimized</span></span>  
  
-   <span data-ttu-id="ef1d4-114">Istruzioni per l'esecuzione di [misurazioni delle prestazioni con il carico di lavoro dimostrativo: sono](#PerformanceMeasurementsusingtheDemoWorkload) incluse le istruzioni per l'installazione e l'esecuzione di OSTRESS, uno strumento che consente di gestire il carico di lavoro e l'esecuzione del carico di lavoro</span><span class="sxs-lookup"><span data-stu-id="ef1d4-114">Instructions for performing [Performance Measurements using the Demo Workload](#PerformanceMeasurementsusingtheDemoWorkload) - this includes instructions for installing and running ostress, a tool using for driving the workload, as well as running the demo workload itself</span></span>  
  
-   [<span data-ttu-id="ef1d4-115">Utilizzo della memoria e dello spazio su disco nell'esempio</span><span class="sxs-lookup"><span data-stu-id="ef1d4-115">Memory and Disk Space Utilization in the Sample</span></span>](#MemoryandDiskSpaceUtilizationintheSample)  
  
##  <a name="prerequisites"></a><a name="Prerequisites"></a> <span data-ttu-id="ef1d4-116">Prerequisiti</span><span class="sxs-lookup"><span data-stu-id="ef1d4-116">Prerequisites</span></span>  
  
-   [!INCLUDE[ssSQL14](../includes/sssql14-md.md)]<span data-ttu-id="ef1d4-117">RTM-Evaluation, Developer o Enterprise Edition</span><span class="sxs-lookup"><span data-stu-id="ef1d4-117">RTM - Evaluation, Developer, or Enterprise edition</span></span>  
  
-   <span data-ttu-id="ef1d4-118">Per il test delle prestazioni, un server con specifiche simili all'ambiente di produzione.</span><span class="sxs-lookup"><span data-stu-id="ef1d4-118">For performance testing, a server with specifications similar to your production environment.</span></span> <span data-ttu-id="ef1d4-119">Per questo particolare esempio sono necessari almeno 16 GB di memoria disponibili per [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="ef1d4-119">For this particular sample you should have at least 16GB of memory available to [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="ef1d4-120">Per linee guida generali sull'hardware per [!INCLUDE[hek_2](../includes/hek-2-md.md)] , vedere il post di Blog seguente:[https://cloudblogs.microsoft.com/sqlserver/2013/08/01/hardware-considerations-for-in-memory-oltp-in-sql-server-2014/](https://cloudblogs.microsoft.com/sqlserver/2013/08/01/hardware-considerations-for-in-memory-oltp-in-sql-server-2014/)</span><span class="sxs-lookup"><span data-stu-id="ef1d4-120">For general guidelines on hardware for [!INCLUDE[hek_2](../includes/hek-2-md.md)], see the following blog post:[https://cloudblogs.microsoft.com/sqlserver/2013/08/01/hardware-considerations-for-in-memory-oltp-in-sql-server-2014/](https://cloudblogs.microsoft.com/sqlserver/2013/08/01/hardware-considerations-for-in-memory-oltp-in-sql-server-2014/)</span></span>  
  
##  <a name="installing-the-hek_2-sample-based-on-adventureworks"></a><a name="InstallingtheIn-MemoryOLTPsamplebasedonAdventureWorks"></a><span data-ttu-id="ef1d4-121">Installazione dell' [!INCLUDE[hek_2](../includes/hek-2-md.md)] esempio basato su AdventureWorks</span><span class="sxs-lookup"><span data-stu-id="ef1d4-121">Installing the [!INCLUDE[hek_2](../includes/hek-2-md.md)] sample based on AdventureWorks</span></span>  
 <span data-ttu-id="ef1d4-122">Per installare l'esempio, seguire i passaggi riportati di seguito.</span><span class="sxs-lookup"><span data-stu-id="ef1d4-122">Follow these steps to install the sample:</span></span>  
  
1.  <span data-ttu-id="ef1d4-123">Scaricare l'archivio per il backup completo del database AdventureWorks2014:</span><span class="sxs-lookup"><span data-stu-id="ef1d4-123">Download the archive for the full backup of the AdventureWorks2014 database:</span></span>  
  
    1.  <span data-ttu-id="ef1d4-124">Aprire il codice seguente: [https://msftdbprodsamples.codeplex.com/downloads/get/880661](https://msftdbprodsamples.codeplex.com/downloads/get/880661) .</span><span class="sxs-lookup"><span data-stu-id="ef1d4-124">Open the following: [https://msftdbprodsamples.codeplex.com/downloads/get/880661](https://msftdbprodsamples.codeplex.com/downloads/get/880661).</span></span>  
  
    2.  <span data-ttu-id="ef1d4-125">Quando richiesto, salvare il file in una cartella locale.</span><span class="sxs-lookup"><span data-stu-id="ef1d4-125">When prompted to save the file to a local folder.</span></span>  
  
2.  <span data-ttu-id="ef1d4-126">Estrarre il file **AdventureWorks2014.bak** in una cartella locale, ad esempio 'c:\temp'.</span><span class="sxs-lookup"><span data-stu-id="ef1d4-126">Extract the **AdventureWorks2014.bak** file to a local folder, for example 'c:\temp'.</span></span>  
  
3.  <span data-ttu-id="ef1d4-127">Ripristinare il backup del database usando [!INCLUDE[tsql](../includes/tsql-md.md)] o [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)]:</span><span class="sxs-lookup"><span data-stu-id="ef1d4-127">Restore the database backup using [!INCLUDE[tsql](../includes/tsql-md.md)] or [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)]:</span></span>  
  
    1.  <span data-ttu-id="ef1d4-128">Identificare la cartella di destinazione e il nome del file di dati, ad esempio</span><span class="sxs-lookup"><span data-stu-id="ef1d4-128">Identify the target folder and filename for the data file, for example</span></span>  
  
         <span data-ttu-id="ef1d4-129">'h:\DATA\AdventureWorks2014_Data.mdf'</span><span class="sxs-lookup"><span data-stu-id="ef1d4-129">'h:\DATA\AdventureWorks2014_Data.mdf'</span></span>  
  
    2.  <span data-ttu-id="ef1d4-130">Identificare la cartella di destinazione e il nome del file di log, ad esempio</span><span class="sxs-lookup"><span data-stu-id="ef1d4-130">Identify the target folder and filename for the log file, for example</span></span>  
  
         <span data-ttu-id="ef1d4-131">'i:\DATA\AdventureWorks2014_log.ldf'</span><span class="sxs-lookup"><span data-stu-id="ef1d4-131">'i:\DATA\AdventureWorks2014_log.ldf'</span></span>  
  
        1.  <span data-ttu-id="ef1d4-132">Il file di log deve essere posizionato in un'unità diversa dal file di dati, idealmente un'unità a bassa latenza, ad esempio l'archiviazione sull'unità SSD o PCIe, per prestazioni ottimali.</span><span class="sxs-lookup"><span data-stu-id="ef1d4-132">The log file should be placed on a different drive than the data file, ideally a low latency drive such as an SSD or PCIe storage, for maximum performance.</span></span>  
  
     <span data-ttu-id="ef1d4-133">Script T-SQL di esempio:</span><span class="sxs-lookup"><span data-stu-id="ef1d4-133">Example T-SQL script:</span></span>  
  
    ```  
    RESTORE DATABASE [AdventureWorks2014]   
      FROM DISK = N'C:\temp\AdventureWorks2014.bak'   
        WITH FILE = 1,    
      MOVE N'AdventureWorks2014_Data' TO N'h:\DATA\AdventureWorks2014_Data.mdf',    
      MOVE N'AdventureWorks2014_Log' TO N'i:\DATA\AdventureWorks2014_log.ldf'  
     GO  
    ```  
  
4.  <span data-ttu-id="ef1d4-134">Impostare il proprietario del database su un account di accesso nel server, eseguendo il comando riportato di seguito nella finestra Query di [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)]:</span><span class="sxs-lookup"><span data-stu-id="ef1d4-134">Change the database owner to a login on your server, by running the following command in the query window of [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)]:</span></span>  
  
    ```  
    ALTER AUTHORIZATION ON DATABASE::AdventureWorks2014 TO [<NewLogin>]  
    ```  
  
5.  <span data-ttu-id="ef1d4-135">Scaricare lo script di esempio " [!INCLUDE[ssSQL14](../includes/sssql14-md.md)] RTM [!INCLUDE[hek_2](../includes/hek-2-md.md)] Sample. SQL" dall' [esempio di OLTP In memoria SQL Server 2014 RTM](https://go.microsoft.com/fwlink/?LinkID=396372) in una cartella locale.</span><span class="sxs-lookup"><span data-stu-id="ef1d4-135">Download the sample script '[!INCLUDE[ssSQL14](../includes/sssql14-md.md)] RTM [!INCLUDE[hek_2](../includes/hek-2-md.md)] Sample.sql' from [SQL Server 2014 RTM In-Memory OLTP Sample](https://go.microsoft.com/fwlink/?LinkID=396372) to a local folder.</span></span>  
  
6.  <span data-ttu-id="ef1d4-136">Aggiornare il valore della variabile "checkpoint_files_location" nello script " [!INCLUDE[ssSQL14](../includes/sssql14-md.md)] RTM [!INCLUDE[hek_2](../includes/hek-2-md.md)] Sample. SQL" per puntare al percorso di destinazione per i [!INCLUDE[hek_2](../includes/hek-2-md.md)] file del checkpoint.</span><span class="sxs-lookup"><span data-stu-id="ef1d4-136">Update the value for the variable 'checkpoint_files_location' in the script '[!INCLUDE[ssSQL14](../includes/sssql14-md.md)] RTM [!INCLUDE[hek_2](../includes/hek-2-md.md)] Sample.sql', to point to the target location for the [!INCLUDE[hek_2](../includes/hek-2-md.md)] checkpoint files.</span></span> <span data-ttu-id="ef1d4-137">I file del checkpoint devono essere posizionati in un'unità con prestazioni di I/O sequenziali ottimali.</span><span class="sxs-lookup"><span data-stu-id="ef1d4-137">The checkpoint files should be placed on a drive with good sequential IO performance.</span></span>  
  
     <span data-ttu-id="ef1d4-138">Aggiornare il valore della variabile 'database_name' in modo da puntare al database AdventureWorks2014.</span><span class="sxs-lookup"><span data-stu-id="ef1d4-138">Update the value for the variable 'database_name' to point to the AdventureWorks2014 database.</span></span>  
  
    1.  <span data-ttu-id="ef1d4-139">Assicurarsi di includere la barra rovesciata " \' come parte del nome del percorso</span><span class="sxs-lookup"><span data-stu-id="ef1d4-139">Be sure to include the backslash '\' as part of the path name</span></span>  
  
    2.  <span data-ttu-id="ef1d4-140">Esempio:</span><span class="sxs-lookup"><span data-stu-id="ef1d4-140">Example:</span></span>  
  
        ```  
        :setvar checkpoint_files_location "d:\DBData\"  
        ...  
        :setvar database_name "AdventureWorks2014"  
        ```  
  
7.  <span data-ttu-id="ef1d4-141">Eseguire lo script di esempio in una delle due modalità riportate di seguito.</span><span class="sxs-lookup"><span data-stu-id="ef1d4-141">Execute the sample script, in one of two ways:</span></span>  
  
    1.  <span data-ttu-id="ef1d4-142">Utilizzando l'utilità della riga di comando sqlcmd.</span><span class="sxs-lookup"><span data-stu-id="ef1d4-142">Using the sqlcmd command-line utility.</span></span> <span data-ttu-id="ef1d4-143">Ad esempio, eseguendo il comando riportato di seguito dal prompt della riga di comando nella cartella contenente lo script:</span><span class="sxs-lookup"><span data-stu-id="ef1d4-143">For example, for example by running the following command from the command-line prompt in the folder containing the script:</span></span>  
  
        ```  
        sqlcmd -S . -E -i "ssSQL14 RTM hek_2 Sample.sql"  
        ```  
  
    2.  <span data-ttu-id="ef1d4-144">Utilizzando Management Studio:</span><span class="sxs-lookup"><span data-stu-id="ef1d4-144">Using Management Studio:</span></span>  
  
        1.  <span data-ttu-id="ef1d4-145">Aprire lo script " [!INCLUDE[ssSQL14](../includes/sssql14-md.md)] RTM [!INCLUDE[hek_2](../includes/hek-2-md.md)] Sample. SQL" in una finestra di query</span><span class="sxs-lookup"><span data-stu-id="ef1d4-145">Open the script '[!INCLUDE[ssSQL14](../includes/sssql14-md.md)] RTM [!INCLUDE[hek_2](../includes/hek-2-md.md)] Sample.sql' in a query window</span></span>  
  
        2.  <span data-ttu-id="ef1d4-146">Connettersi al server di destinazione contenente il database AdventureWorks2014</span><span class="sxs-lookup"><span data-stu-id="ef1d4-146">Connect to the target server that contains the database AdventureWorks2014</span></span>  
  
        3.  <span data-ttu-id="ef1d4-147">Abilitare la modalità SQLCMD, facendo clic su "query-> modalità SQLCMD"</span><span class="sxs-lookup"><span data-stu-id="ef1d4-147">Enable SQLCMD Mode, by clicking on 'Query -> SQLCMD Mode'</span></span>  
  
        4.  <span data-ttu-id="ef1d4-148">Fare clic sul pulsante ' Esegui ' per eseguire lo script</span><span class="sxs-lookup"><span data-stu-id="ef1d4-148">Click the button 'Execute' to run the script</span></span>  
  
##  <a name="description-of-the-sample-tables-and-procedures"></a><a name="Descriptionofthesampletablesandprocedures"></a> <span data-ttu-id="ef1d4-149">Descrizione delle tabelle e delle procedure di esempio</span><span class="sxs-lookup"><span data-stu-id="ef1d4-149">Description of the sample tables and procedures</span></span>  
 <span data-ttu-id="ef1d4-150">Nell'esempio vengono create nuove tabelle per i prodotti e gli ordini vendita, basate sulle tabelle esistenti in AdventureWorks.</span><span class="sxs-lookup"><span data-stu-id="ef1d4-150">The sample creates new tables for products and sales orders, based on existing tables in AdventureWorks.</span></span> <span data-ttu-id="ef1d4-151">Lo schema delle nuove tabelle è simile a quello delle tabelle esistenti, con alcune differenze, come illustrato di seguito.</span><span class="sxs-lookup"><span data-stu-id="ef1d4-151">The schema of the new tables is similar to the existing tables, with a few differences, as explained below.</span></span>  
  
 <span data-ttu-id="ef1d4-152">Nelle nuove tabelle ottimizzate per la memoria è incluso il suffisso '_inmem'.</span><span class="sxs-lookup"><span data-stu-id="ef1d4-152">The new memory-optimized tables carry the suffix '_inmem'.</span></span> <span data-ttu-id="ef1d4-153">Nell'esempio sono incluse anche tabelle corrispondenti con il suffisso "_ondisk". Queste tabelle possono essere usate per un confronto uno-a-uno tra le prestazioni delle tabelle ottimizzate per la memoria e quelle basate su disco nel sistema.</span><span class="sxs-lookup"><span data-stu-id="ef1d4-153">The sample also includes corresponding tables carrying the suffix '_ondisk' - these tables can be used to make a one-to-one comparison between the performance of memory-optimized tables and disk-based tables on your system..</span></span>  
  
 <span data-ttu-id="ef1d4-154">Si noti che le tabelle ottimizzate per la memoria utilizzate nel carico di lavoro per il confronto delle prestazioni sono completamente durevoli e con registrazione completa.</span><span class="sxs-lookup"><span data-stu-id="ef1d4-154">Note that the memory-optimized tables used in the workload for performance comparison are fully durable and fully logged.</span></span> <span data-ttu-id="ef1d4-155">Con queste tabelle non viene sacrificata la durabilità o l'affidabilità per ottenere un miglioramento delle prestazioni.</span><span class="sxs-lookup"><span data-stu-id="ef1d4-155">They do not sacrifice durability or reliability to attain the performance gain.</span></span>  
  
 <span data-ttu-id="ef1d4-156">Il carico di lavoro di destinazione per questo esempio è rappresentato dall'elaborazione degli ordini vendita, in cui vengono prese in considerazione anche le informazioni sui prodotti e sugli sconti.</span><span class="sxs-lookup"><span data-stu-id="ef1d4-156">The target workload for this sample is sales order processing, where we consider also information about products and discounts.</span></span> <span data-ttu-id="ef1d4-157">A questo scopo, vengono utilizzate le tabelle SalesOrderHeader, SalesOrderDetail, Product, SpecialOffer e SpecialOfferProduct.</span><span class="sxs-lookup"><span data-stu-id="ef1d4-157">To this end, the table SalesOrderHeader, SalesOrderDetail, Product, SpecialOffer, and SpecialOfferProduct.</span></span>  
  
 <span data-ttu-id="ef1d4-158">Per inserire gli ordini vendita e aggiornare le informazioni sulla spedizione di un determinato ordine vendita vengono utilizzate due nuove stored procedure: Sales.usp_InsertSalesOrder_inmem e Sales.usp_UpdateSalesOrderShipInfo_inmem.</span><span class="sxs-lookup"><span data-stu-id="ef1d4-158">Two new stored procedures, Sales.usp_InsertSalesOrder_inmem and Sales.usp_UpdateSalesOrderShipInfo_inmem, are used to insert sales orders and to update the shipping information of a given sales order.</span></span>  
  
 <span data-ttu-id="ef1d4-159">Nel nuovo schema "Demo" sono incluse stored procedure e tabelle helper per eseguire un carico di lavoro dimostrativo.</span><span class="sxs-lookup"><span data-stu-id="ef1d4-159">The new schema 'Demo' contains helper tables and stored procedures to execute a demo workload.</span></span>  
  
 <span data-ttu-id="ef1d4-160">In concreto, nell'esempio di [!INCLUDE[hek_2](../includes/hek-2-md.md)] vengono aggiunti ad AdventureWorks gli oggetti seguenti:</span><span class="sxs-lookup"><span data-stu-id="ef1d4-160">Concretely, the [!INCLUDE[hek_2](../includes/hek-2-md.md)] sample adds the following objects to AdventureWorks:</span></span>  
  
### <a name="tables-added-by-the-sample"></a><span data-ttu-id="ef1d4-161">Tabelle aggiunte con l'esempio</span><span class="sxs-lookup"><span data-stu-id="ef1d4-161">Tables added by the sample</span></span>  
  
#### <a name="the-new-tables"></a><span data-ttu-id="ef1d4-162">Nuove tabelle</span><span class="sxs-lookup"><span data-stu-id="ef1d4-162">The New Tables</span></span>  
 <span data-ttu-id="ef1d4-163">Sales.SalesOrderHeader_inmem</span><span class="sxs-lookup"><span data-stu-id="ef1d4-163">Sales.SalesOrderHeader_inmem</span></span>  
  
-   <span data-ttu-id="ef1d4-164">Informazioni di intestazione sugli ordini vendita.</span><span class="sxs-lookup"><span data-stu-id="ef1d4-164">Header information about sales orders.</span></span> <span data-ttu-id="ef1d4-165">Ogni ordine vendita è rappresentato da una riga nella tabella.</span><span class="sxs-lookup"><span data-stu-id="ef1d4-165">Each sales order has one row in this table.</span></span>  
  
 <span data-ttu-id="ef1d4-166">Sales.SalesOrderDetail_inmem</span><span class="sxs-lookup"><span data-stu-id="ef1d4-166">Sales.SalesOrderDetail_inmem</span></span>  
  
-   <span data-ttu-id="ef1d4-167">Dettagli degli ordini vendita.</span><span class="sxs-lookup"><span data-stu-id="ef1d4-167">Details of sales orders.</span></span> <span data-ttu-id="ef1d4-168">Ogni voce di un ordine vendita è rappresentato da una riga nella tabella.</span><span class="sxs-lookup"><span data-stu-id="ef1d4-168">Each line item of a sales order has one row in this table.</span></span>  
  
 <span data-ttu-id="ef1d4-169">Sales.SpecialOffer_inmem</span><span class="sxs-lookup"><span data-stu-id="ef1d4-169">Sales.SpecialOffer_inmem</span></span>  
  
-   <span data-ttu-id="ef1d4-170">Informazioni sulle offerte speciali, inclusa la percentuale di sconto associata a ogni offerta.</span><span class="sxs-lookup"><span data-stu-id="ef1d4-170">Information about special offers, including the discount percentage associated with each special offer.</span></span>  
  
 <span data-ttu-id="ef1d4-171">Sales.SpecialOfferProduct_inmem</span><span class="sxs-lookup"><span data-stu-id="ef1d4-171">Sales.SpecialOfferProduct_inmem</span></span>  
  
-   <span data-ttu-id="ef1d4-172">Tabella di riferimento tra offerte speciali e prodotti.</span><span class="sxs-lookup"><span data-stu-id="ef1d4-172">Reference table between special offers and products.</span></span> <span data-ttu-id="ef1d4-173">Ogni offerta speciale può includere zero o più prodotti e ogni prodotto può essere caratterizzato da zero o più offerte speciali.</span><span class="sxs-lookup"><span data-stu-id="ef1d4-173">Each special offer can feature zero or more products, and each product can be featured in zero or more special offers.</span></span>  
  
 <span data-ttu-id="ef1d4-174">Production.Product_inmem</span><span class="sxs-lookup"><span data-stu-id="ef1d4-174">Production.Product_inmem</span></span>  
  
-   <span data-ttu-id="ef1d4-175">Informazioni sui prodotti, tra cui il prezzo di listino.</span><span class="sxs-lookup"><span data-stu-id="ef1d4-175">Information about products, including their list price.</span></span>  
  
 <span data-ttu-id="ef1d4-176">Demo.DemoSalesOrderDetailSeed</span><span class="sxs-lookup"><span data-stu-id="ef1d4-176">Demo.DemoSalesOrderDetailSeed</span></span>  
  
-   <span data-ttu-id="ef1d4-177">Utilizzata nel carico di lavoro dimostrativo per creare ordini vendita di esempio.</span><span class="sxs-lookup"><span data-stu-id="ef1d4-177">Used in the demo workload to construct sample sales orders.</span></span>  
  
 <span data-ttu-id="ef1d4-178">Varianti basate su disco delle tabelle:</span><span class="sxs-lookup"><span data-stu-id="ef1d4-178">Disk-based variations of the tables:</span></span>  
  
-   <span data-ttu-id="ef1d4-179">Sales.SalesOrderHeader_ondisk</span><span class="sxs-lookup"><span data-stu-id="ef1d4-179">Sales.SalesOrderHeader_ondisk</span></span>  
  
-   <span data-ttu-id="ef1d4-180">Sales.SalesOrderDetail_ondisk</span><span class="sxs-lookup"><span data-stu-id="ef1d4-180">Sales.SalesOrderDetail_ondisk</span></span>  
  
-   <span data-ttu-id="ef1d4-181">Sales.SpecialOffer_ondisk</span><span class="sxs-lookup"><span data-stu-id="ef1d4-181">Sales.SpecialOffer_ondisk</span></span>  
  
-   <span data-ttu-id="ef1d4-182">Sales.SpecialOfferProduct_ondisk</span><span class="sxs-lookup"><span data-stu-id="ef1d4-182">Sales.SpecialOfferProduct_ondisk</span></span>  
  
-   <span data-ttu-id="ef1d4-183">Production.Product_ondisk</span><span class="sxs-lookup"><span data-stu-id="ef1d4-183">Production.Product_ondisk</span></span>  
  
#### <a name="differences-between-original-disk-based-and-the-and-new-memory-optimized-tables"></a><span data-ttu-id="ef1d4-184">Differenze tra le tabelle basate su disco originali e le nuove tabelle ottimizzate per la memoria</span><span class="sxs-lookup"><span data-stu-id="ef1d4-184">Differences between original disk-based and the and new memory-optimized tables</span></span>  
 <span data-ttu-id="ef1d4-185">In genere, nelle nuove tabelle introdotte con questo esempio vengono utilizzate le stesse colonne e gli stessi tipi di dati delle tabelle originali.</span><span class="sxs-lookup"><span data-stu-id="ef1d4-185">For the most part, the new tables introduced by this sample use the same columns and the same data types as the original tables.</span></span> <span data-ttu-id="ef1d4-186">Tuttavia, esistono alcune differenze</span><span class="sxs-lookup"><span data-stu-id="ef1d4-186">However, there are a few differences.</span></span> <span data-ttu-id="ef1d4-187">elencate di seguito, insieme a una spiegazione logica delle modifiche.</span><span class="sxs-lookup"><span data-stu-id="ef1d4-187">We list the differences below, along with a rationale for the changes.</span></span>  
  
 <span data-ttu-id="ef1d4-188">Sales.SalesOrderHeader_inmem</span><span class="sxs-lookup"><span data-stu-id="ef1d4-188">Sales.SalesOrderHeader_inmem</span></span>  
  
-   <span data-ttu-id="ef1d4-189">*Vincoli predefiniti*. Sono supportati per le tabelle ottimizzate per la memoria; inoltre, la migrazione della maggior parte di questi vincoli è stata eseguita senza apportarvi variazioni.</span><span class="sxs-lookup"><span data-stu-id="ef1d4-189">*Default constraints* are supported for memory-optimized tables, and most default constraints we migrated as is.</span></span> <span data-ttu-id="ef1d4-190">Tuttavia, nella tabella originale Sales.SalesOrderHeader sono contenuti due vincoli predefiniti tramite cui viene recuperata la data corrente per le colonne OrderDate e ModifiedDate.</span><span class="sxs-lookup"><span data-stu-id="ef1d4-190">However, the original table Sales.SalesOrderHeader contains two default constraints that retrieve the current date, for the columns OrderDate and ModifiedDate.</span></span> <span data-ttu-id="ef1d4-191">In un carico di lavoro di elaborazione dell'ordine a velocità effettiva elevata con molta concorrenza, qualsiasi risorsa globale può diventare un punto di contesa.</span><span class="sxs-lookup"><span data-stu-id="ef1d4-191">In a high throughput order processing workload with a lot of concurrency, any global resource can become a point of contention.</span></span> <span data-ttu-id="ef1d4-192">L'ora di sistema è un esempio di risorsa globale e si è notato che può costituire un collo di bottiglia quando si esegue un carico di lavoro di [!INCLUDE[hek_2](../includes/hek-2-md.md)] con ordini vendita, in particolare se l'ora di sistema deve essere recuperata per più colonne nell'intestazione degli ordini vendita, nonché per i dettagli degli ordini vendita.</span><span class="sxs-lookup"><span data-stu-id="ef1d4-192">System time is such a global resource, and we have observed that it can become a bottleneck when running an [!INCLUDE[hek_2](../includes/hek-2-md.md)] workload that inserts sales orders, in particular if the system time needs to be retrieved for multiple columns in the sales order header, as well as the sales order details.</span></span> <span data-ttu-id="ef1d4-193">In questo esempio il problema è stato risolto recuperando l'ora di sistema solo una volta per ogni ordine vendita inserito e il valore in questione viene utilizzato per le colonne di tipo datetime in SalesOrderHeader_inmem e in SalesOrderDetail_inmem, nella stored procedure Sales.usp_InsertSalesOrder_inmem.</span><span class="sxs-lookup"><span data-stu-id="ef1d4-193">The problem is addressed in this sample by retrieving the system time only once for each sales order that is inserted, and use that value for the datetime columns in SalesOrderHeader_inmem and SalesOrderDetail_inmem, in the stored procedure Sales.usp_InsertSalesOrder_inmem.</span></span>  
  
-   <span data-ttu-id="ef1d4-194">*Tipi definiti dall'utente (UDT) alias* . Nella tabella originale sono utilizzati due tipi di dati alias definiti dall'utente (UDT), dbo.OrderNumber e dbo.AccountNumber, rispettivamente per le colonne PurchaseOrderNumber e AccountNumber.</span><span class="sxs-lookup"><span data-stu-id="ef1d4-194">*Alias UDTs* - The original table uses two alias user-defined data types (UDTs) dbo.OrderNumber and dbo.AccountNumber, for the columns PurchaseOrderNumber and AccountNumber, respectively.</span></span> [!INCLUDE[ssSQL14](../includes/sssql14-md.md)] <span data-ttu-id="ef1d4-195">non supporta il tipo di dati alias definito dall'utente per le tabelle ottimizzate per la memoria, pertanto le nuove tabelle usano rispettivamente i tipi di dati di sistema nvarchar(25) e nvarchar(15).</span><span class="sxs-lookup"><span data-stu-id="ef1d4-195">does not support alias UDT for memory-optimized tables, thus the new tables use system data types nvarchar(25) and nvarchar(15), respectively.</span></span>  
  
-   <span data-ttu-id="ef1d4-196">*Colonne che ammettono i valori Null nelle chiavi di indice* . Nella tabella originale la colonna SalesPersonID ammette i valori Null, mentre nelle nuove tabelle non ammette i valori Null e prevede un vincolo predefinito con valore (-1).</span><span class="sxs-lookup"><span data-stu-id="ef1d4-196">*Nullable columns in index keys* - In the original table, the column SalesPersonID is nullable, while in the new tables the column is not nullable and has a default constraint with value (-1).</span></span> <span data-ttu-id="ef1d4-197">Ciò è dovuto al fatto che gli indici nelle tabelle ottimizzate per la memoria non possono disporre di colonne che ammettono i valori Null nella chiave di indice; -1 è un surrogato di NULL in questo caso.</span><span class="sxs-lookup"><span data-stu-id="ef1d4-197">This is because indexes on memory-optimized tables cannot have nullable columns in the index key; -1 is a surrogate for NULL in this case.</span></span>  
  
-   <span data-ttu-id="ef1d4-198">*Colonne calcolate*. Le colonne calcolate SalesOrderNumber e TotalDue vengono omesse, poiché in [!INCLUDE[ssSQL14](../includes/sssql14-md.md)] non sono supportate colonne calcolate nelle tabelle ottimizzate per la memoria.</span><span class="sxs-lookup"><span data-stu-id="ef1d4-198">*Computed columns* - The computed columns SalesOrderNumber and TotalDue are omitted, as [!INCLUDE[ssSQL14](../includes/sssql14-md.md)] does not support computed columns in memory-optimized tables.</span></span> <span data-ttu-id="ef1d4-199">La nuova vista Sales.vSalesOrderHeader_extended_inmem riflette le colonne SalesOrderNumber e TotalDue.</span><span class="sxs-lookup"><span data-stu-id="ef1d4-199">The new view Sales.vSalesOrderHeader_extended_inmem reflects the columns SalesOrderNumber and TotalDue.</span></span> <span data-ttu-id="ef1d4-200">Pertanto, può essere utilizzata qualora queste colonne fossero necessarie.</span><span class="sxs-lookup"><span data-stu-id="ef1d4-200">Therefore, you can use this view if these columns are needed.</span></span>  
  
-   <span data-ttu-id="ef1d4-201">*Vincoli di chiave esterna*. Non sono supportati per le tabelle ottimizzate per la memoria in [!INCLUDE[ssSQL14](../includes/sssql14-md.md)].</span><span class="sxs-lookup"><span data-stu-id="ef1d4-201">*Foreign key constraints* are not supported for memory-optimized tables in [!INCLUDE[ssSQL14](../includes/sssql14-md.md)].</span></span> <span data-ttu-id="ef1d4-202">Inoltre, SalesOrderHeader_inmem è una tabella attiva nel carico di lavoro di esempio e i vincoli di chiavi esterne comportano un'ulteriore elaborazione per tutte le operazioni DML, in quanto sono necessarie ricerche in tutte le altre tabelle a cui viene fatto riferimento in questi vincoli.</span><span class="sxs-lookup"><span data-stu-id="ef1d4-202">In addition, SalesOrderHeader_inmem is a hot table in the example workload, and foreign keys constraints require additional processing for all DML operations, as it requires lookups in all the other tables referenced in these constraints.</span></span> <span data-ttu-id="ef1d4-203">Pertanto, si presuppone che l'applicazione garantisca l'integrità referenziale e questa integrità non venga convalidata quando vengono inserite le righe.</span><span class="sxs-lookup"><span data-stu-id="ef1d4-203">Therefore, the assumption is that the app ensures referential integrity, and referential integrity is not validated when rows are inserted.</span></span> <span data-ttu-id="ef1d4-204">L'integrità referenziale per i dati di questa tabella può essere verificata utilizzando la stored procedure dbo.usp_ValidateIntegrity, tramite lo script seguente:</span><span class="sxs-lookup"><span data-stu-id="ef1d4-204">Referential integrity for the data in this table can be verified using the stored procedure dbo.usp_ValidateIntegrity, using the following script:</span></span>  
  
    ```  
    DECLARE @o int = object_id(N'Sales.SalesOrderHeader_inmem')  
    EXEC dbo.usp_ValidateIntegrity @o  
    ```  
  
-   <span data-ttu-id="ef1d4-205">*Vincoli CHECK*. Non sono supportati per le tabelle ottimizzate per la memoria in SQ Server 2014.</span><span class="sxs-lookup"><span data-stu-id="ef1d4-205">*Check constraints* are not supported for memory-optimized tables in SQ Server 2014.</span></span> <span data-ttu-id="ef1d4-206">L'integrità di dominio viene convalidata insieme all'integrità referenziale tramite questo script:</span><span class="sxs-lookup"><span data-stu-id="ef1d4-206">Domain integrity is validated along with referential integrity using this script:</span></span>  
  
    ```  
    DECLARE @o int = object_id(N'Sales.SalesOrderHeader_inmem')  
    EXEC dbo.usp_ValidateIntegrity @o  
    ```  
  
-   <span data-ttu-id="ef1d4-207">*Rowguid* . La colonna rowguid viene omessa.</span><span class="sxs-lookup"><span data-stu-id="ef1d4-207">*Rowguid* - The rowguid column is omitted.</span></span> <span data-ttu-id="ef1d4-208">Anche se uniqueidentifier è il supporto per le tabelle ottimizzate per la memoria, l'opzione ROWGUIDCOL non è supportata in [!INCLUDE[ssSQL14](../includes/sssql14-md.md)].</span><span class="sxs-lookup"><span data-stu-id="ef1d4-208">While uniqueidentifier is support for memory-optimized tables, the option ROWGUIDCOL is not supported in [!INCLUDE[ssSQL14](../includes/sssql14-md.md)].</span></span> <span data-ttu-id="ef1d4-209">Le colonne di questo tipo vengono in genere utilizzate per la replica di tipo merge o per le tabelle con colonne FILESTREAM.</span><span class="sxs-lookup"><span data-stu-id="ef1d4-209">Columns of this kind are typically used for either merge replication or tables that have filestream columns.</span></span> <span data-ttu-id="ef1d4-210">Nell'esempio sono escluse entrambe.</span><span class="sxs-lookup"><span data-stu-id="ef1d4-210">This sample includes neither.</span></span>  
  
 <span data-ttu-id="ef1d4-211">Sales.SalesOrderDetail</span><span class="sxs-lookup"><span data-stu-id="ef1d4-211">Sales.SalesOrderDetail</span></span>  
  
-   <span data-ttu-id="ef1d4-212">*Vincoli predefiniti*: analogamente a SalesOrderHeader, non viene eseguita la migrazione del vincolo predefinito per cui sono richieste data/ora del sistema. L'inserimento della data/ora di sistema corrente verrà eseguito dalla stored procedure tramite cui vengono inseriti gli ordini di vendita al primo inserimento.</span><span class="sxs-lookup"><span data-stu-id="ef1d4-212">*Default constraints* - similar to SalesOrderHeader, the default constraint requiring the system date/time is not migrated, instead the stored procedure inserting sales orders takes care of inserting the current system date/time on first insert.</span></span>  
  
-   <span data-ttu-id="ef1d4-213">*Colonne calcolate*: la migrazione della colonna calcolata LineTotal non è stata eseguita poiché le colonne di questo tipo non sono supportate con le tabelle ottimizzate per la memoria in [!INCLUDE[ssSQL14](../includes/sssql14-md.md)].</span><span class="sxs-lookup"><span data-stu-id="ef1d4-213">*Computed columns* - the computed column LineTotal was not migrated as computed columns are not supported with memory-optimized tables in [!INCLUDE[ssSQL14](../includes/sssql14-md.md)].</span></span> <span data-ttu-id="ef1d4-214">Per accedere a questa colonna, usare la vista Sales.vSalesOrderDetail_extended_inmem.</span><span class="sxs-lookup"><span data-stu-id="ef1d4-214">To access this column use the view Sales.vSalesOrderDetail_extended_inmem.</span></span>  
  
-   <span data-ttu-id="ef1d4-215">*Rowguid* . La colonna rowguid viene omessa.</span><span class="sxs-lookup"><span data-stu-id="ef1d4-215">*Rowguid* - The rowguid column is omitted.</span></span> <span data-ttu-id="ef1d4-216">Per informazioni dettagliate, vedere la descrizione della tabella SalesOrderHeader.</span><span class="sxs-lookup"><span data-stu-id="ef1d4-216">For details see the description for the table SalesOrderHeader.</span></span>  
  
-   <span data-ttu-id="ef1d4-217">Per i vincoli *CHECK* e di *chiave esterna* , vedere la descrizione di SalesOrderHeader.</span><span class="sxs-lookup"><span data-stu-id="ef1d4-217">For *check* and *foreign key* constraints see the description of SalesOrderHeader.</span></span> <span data-ttu-id="ef1d4-218">Lo script seguente può essere utilizzato per verificare le integrità di dominio e referenziale per la tabella:</span><span class="sxs-lookup"><span data-stu-id="ef1d4-218">The following script can be used to verify domain and referential integrity for this table:</span></span>  
  
    ```  
    DECLARE @o int = object_id(N'Sales.SalesOrderHeader_inmem')  
    EXEC dbo.usp_ValidateIntegrity @o  
    ```  
  
 <span data-ttu-id="ef1d4-219">Production.Product</span><span class="sxs-lookup"><span data-stu-id="ef1d4-219">Production.Product</span></span>  
  
-   <span data-ttu-id="ef1d4-220">*Tipi alias definiti dall'utente (UDT)* : nella tabella originale viene usato il tipo di dati definito dall'utente dbo.Flag, equivalente al bit del tipo di dati di sistema.</span><span class="sxs-lookup"><span data-stu-id="ef1d4-220">*Alias UDTs* - the original table uses the user-defined data type dbo.Flag, which is equivalent to the system data type bit.</span></span> <span data-ttu-id="ef1d4-221">Nella tabella migrata viene utilizzato, in alternativa, il tipo di dati bit.</span><span class="sxs-lookup"><span data-stu-id="ef1d4-221">The migrated table uses the bit data type instead.</span></span>  
  
-   <span data-ttu-id="ef1d4-222">*Regole di confronto di BIN2* : le colonne Name e ProductNumber sono incluse nelle chiavi di indice e devono quindi avere regole di confronto di BIN2 in [!INCLUDE[ssSQL14](../includes/sssql14-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="ef1d4-222">*BIN2 collation* - The columns Name and ProductNumber are included in index keys, and must thus have BIN2 collations in [!INCLUDE[ssSQL14](../includes/sssql14-md.md)].</span></span> <span data-ttu-id="ef1d4-223">In questo caso, si presuppone che l'applicazione non si basi sulle specifiche delle regole di confronto, quale l'esclusione della distinzione tra maiuscole e minuscole.</span><span class="sxs-lookup"><span data-stu-id="ef1d4-223">Here, the assumption is that the app does not rely on collation specifics, like case insensitivity.</span></span>  
  
-   <span data-ttu-id="ef1d4-224">*Rowguid* . La colonna rowguid viene omessa.</span><span class="sxs-lookup"><span data-stu-id="ef1d4-224">*Rowguid* - The rowguid column is omitted.</span></span> <span data-ttu-id="ef1d4-225">Per informazioni dettagliate, vedere la descrizione della tabella SalesOrderHeader.</span><span class="sxs-lookup"><span data-stu-id="ef1d4-225">For details see the description for the table SalesOrderHeader.</span></span>  
  
-   <span data-ttu-id="ef1d4-226">*Vincoli univoci*, *CHECK* e di *chiave esterna* . Vengono presi in considerazione in due modi: le stored procedure Product.usp_InsertProduct_inmem e Product.usp_DeleteProduct_inmem possono essere utilizzate per inserire ed eliminare i prodotti. Tramite queste stored procedure vengono convalidate le integrità di dominio e referenziale e si verificherà un errore in caso di violazione dell'integrità.</span><span class="sxs-lookup"><span data-stu-id="ef1d4-226">*Unique*, *Check* and *Foreign Key constraints* are accounted for in two ways: the stored procedures Product.usp_InsertProduct_inmem and Product.usp_DeleteProduct_inmem can be used to insert and delete products; these procedures validate domain and referential integrity, and will fail if integrity is violated.</span></span> <span data-ttu-id="ef1d4-227">Inoltre, lo script seguente può essere utilizzato per convalidare le integrità di dominio e referenziale senza apportarvi variazioni:</span><span class="sxs-lookup"><span data-stu-id="ef1d4-227">In addition, the follow script can be used to validate domain and referential integrity as is:</span></span>  
  
    ```  
    DECLARE @o int = object_id(N'Production.Product')  
    EXEC dbo.usp_ValidateIntegrity @o  
    ```  
  
    -   <span data-ttu-id="ef1d4-228">Si noti che nelle stored procedure usp_InsertProduct_inmem e usp_DeleteProduct_inmem vengono prese in considerazione solo le chiavi esterne tra le tabelle migrate.</span><span class="sxs-lookup"><span data-stu-id="ef1d4-228">Note that the store procedures usp_InsertProduct_inmem and usp_DeleteProduct_inmem consider only foreign keys between the migrated tables.</span></span> <span data-ttu-id="ef1d4-229">I riferimenti ad altre tabelle quali ProductModel, ProductSubcategory e UnitMeasure non vengono presi in considerazione.</span><span class="sxs-lookup"><span data-stu-id="ef1d4-229">References to other tables ProductModel, ProductSubcategory, and UnitMeasure are not considered.</span></span>  
  
 <span data-ttu-id="ef1d4-230">Sales.SpecialOffer</span><span class="sxs-lookup"><span data-stu-id="ef1d4-230">Sales.SpecialOffer</span></span>  
  
-   <span data-ttu-id="ef1d4-231">*Vincoli CHECK* e di *chiave esterna* . Vengono presi in considerazione in due modi: le stored procedure Sales.usp_InsertSpecialOffer_inmem e Sales.usp_DeleteSpecialOffer_inmem possono essere utilizzate per inserire ed eliminare le offerte speciali. Tramite queste stored procedure vengono convalidate le integrità di dominio e referenziale e si verificherà un errore in caso di violazione dell'integrità.</span><span class="sxs-lookup"><span data-stu-id="ef1d4-231">*Check* and *Foreign Key constraints* are accounted for in two ways: the stored procedures Sales.usp_InsertSpecialOffer_inmem and Sales.usp_DeleteSpecialOffer_inmem can be used to insert and delete special offers; these procedures validate domain and referential integrity, and will fail if integrity is violated.</span></span> <span data-ttu-id="ef1d4-232">Inoltre, lo script seguente può essere utilizzato per convalidare le integrità di dominio e referenziale senza apportarvi variazioni:</span><span class="sxs-lookup"><span data-stu-id="ef1d4-232">In addition, the follow script can be used to validate domain and referential integrity as is:</span></span>  
  
    ```  
    DECLARE @o int = object_id(N'Sales.SpecialOffer_inmem')  
    EXEC dbo.usp_ValidateIntegrity @o  
    ```  
  
-   <span data-ttu-id="ef1d4-233">*Rowguid* . La colonna rowguid viene omessa.</span><span class="sxs-lookup"><span data-stu-id="ef1d4-233">*Rowguid* - The rowguid column is omitted.</span></span> <span data-ttu-id="ef1d4-234">Per informazioni dettagliate, vedere la descrizione della tabella SalesOrderHeader.</span><span class="sxs-lookup"><span data-stu-id="ef1d4-234">For details see the description for the table SalesOrderHeader.</span></span>  
  
 <span data-ttu-id="ef1d4-235">Sales.SpecialOfferProduct</span><span class="sxs-lookup"><span data-stu-id="ef1d4-235">Sales.SpecialOfferProduct</span></span>  
  
-   <span data-ttu-id="ef1d4-236">*Vincoli di chiave esterna* . Vengono presi in considerazione in due modi: la stored procedure Sales.usp_InsertSpecialOfferProduct_inmem può essere utilizzata per definire le relazioni tra le offerte speciali e i prodotti. Tramite questa stored procedure viene convalidata l'integrità referenziale e si verificherà un errore qualora questa integrità venga violata.</span><span class="sxs-lookup"><span data-stu-id="ef1d4-236">*Foreign Key constraints* are accounted for in two ways: the stored procedure Sales.usp_InsertSpecialOfferProduct_inmem can be used to insert relationships between special offers and products; this procedures validates referential integrity, and will fail if integrity is violated.</span></span> <span data-ttu-id="ef1d4-237">Inoltre, lo script seguente può essere utilizzato per convalidare l'integrità referenziale senza apportarvi variazioni:</span><span class="sxs-lookup"><span data-stu-id="ef1d4-237">In addition, the follow script can be used to validate referential integrity as is:</span></span>  
  
    ```  
    DECLARE @o int = object_id(N'Sales.SpecialOfferProduct_inmem')  
    EXEC dbo.usp_ValidateIntegrity @o  
    ```  
  
-   <span data-ttu-id="ef1d4-238">*Rowguid* . La colonna rowguid viene omessa.</span><span class="sxs-lookup"><span data-stu-id="ef1d4-238">*Rowguid* - The rowguid column is omitted.</span></span> <span data-ttu-id="ef1d4-239">Per informazioni dettagliate, vedere la descrizione della tabella SalesOrderHeader.</span><span class="sxs-lookup"><span data-stu-id="ef1d4-239">For details see the description for the table SalesOrderHeader.</span></span>  
  
#### <a name="considerations-for-indexes-on-memory-optimized-tables"></a><span data-ttu-id="ef1d4-240">Considerazioni sugli indici nelle tabelle ottimizzate per la memoria</span><span class="sxs-lookup"><span data-stu-id="ef1d4-240">Considerations for indexes on memory-optimized tables</span></span>  
 <span data-ttu-id="ef1d4-241">L'indice di base per le tabelle ottimizzate per la memoria è l'indice NONCLUSTERED, che supporta le ricerche di punti (ricerca nell'indice nel predicato di uguaglianza), le analisi dell'intervallo (ricerca nell'indice nel predicato di disuguaglianza), analisi di indici completi e analisi ordinate.</span><span class="sxs-lookup"><span data-stu-id="ef1d4-241">The baseline index for memory-optimized tables is the NONCLUSTERED index, which supports point lookups (index seek on equality predicate), range scans (index seek in inequality predicate), full index scans, and ordered scans.</span></span> <span data-ttu-id="ef1d4-242">Inoltre, gli indici NONCLUSTERED supportano la ricerca nelle colonne iniziali della chiave di indice.</span><span class="sxs-lookup"><span data-stu-id="ef1d4-242">In addition, NONCLUSTERED indexes support searching on leading columns of the index key.</span></span> <span data-ttu-id="ef1d4-243">In realtà, gli indici NONCLUSTERED ottimizzati per la memoria supportano tutte le operazioni consentite dagli indici NONCLUSTERED basati su disco, con la sola eccezione che vengono eseguite analisi a ritroso.</span><span class="sxs-lookup"><span data-stu-id="ef1d4-243">In fact memory-optimized NONCLUSTERED indexes support all the operations supported by disk-based NONCLUSTERED indexes, with the only exception being backward scans.</span></span> <span data-ttu-id="ef1d4-244">Pertanto, l'utilizzo di indici NONCLUSTERED è una scelta sicura.</span><span class="sxs-lookup"><span data-stu-id="ef1d4-244">Therefore, using NONCLUSTERED indexes is a safe choice for your indexes.</span></span>  
  
 <span data-ttu-id="ef1d4-245">Per ottimizzare ulteriormente il carico di lavoro, è possibile usare gli indici HASH.</span><span class="sxs-lookup"><span data-stu-id="ef1d4-245">HASH indexes are can be used to further optimize the workload.</span></span> <span data-ttu-id="ef1d4-246">Vengono ottimizzati in particolare per le ricerche di punti e per gli inserimenti di righe.</span><span class="sxs-lookup"><span data-stu-id="ef1d4-246">They are particularly optimized for point lookups and row inserts.</span></span> <span data-ttu-id="ef1d4-247">Tuttavia, è necessario considerare che non supportano le analisi dell'intervallo, le analisi ordinate o la ricerca nelle colonne iniziali della chiave di indice.</span><span class="sxs-lookup"><span data-stu-id="ef1d4-247">However, one must consider that they do not support range scans, ordered scans, or search on leading index key columns.</span></span> <span data-ttu-id="ef1d4-248">Di conseguenza, prestare attenzione quando si utilizzano questi indici.</span><span class="sxs-lookup"><span data-stu-id="ef1d4-248">Therefore, care needs to be taken when using these indexes.</span></span> <span data-ttu-id="ef1d4-249">Inoltre, è necessario specificare il bucket_count al momento della creazione.</span><span class="sxs-lookup"><span data-stu-id="ef1d4-249">In addition, it is necessary to specify the bucket_count at create time.</span></span> <span data-ttu-id="ef1d4-250">In genere deve essere impostato su un valore compreso tra una e due volte il numero di valori di chiave di indice; tuttavia, un valore superiore non rappresenta di solito un problema.</span><span class="sxs-lookup"><span data-stu-id="ef1d4-250">It should usually be set at between one and two times the number of index key values, but overestimating is usually not a problem.</span></span>  
  
 <span data-ttu-id="ef1d4-251">Vedere la documentazione online per altre informazioni sulle [linee guida relative agli indici](https://technet.microsoft.com/library/dn133166\(v=sql.120\).aspx) e sulle linee guida per [scegliere il bucket_count corretto](https://technet.microsoft.com/library/dn494956\(v=sql.120\).aspx).</span><span class="sxs-lookup"><span data-stu-id="ef1d4-251">See Books Online for more details about [index guidelines](https://technet.microsoft.com/library/dn133166\(v=sql.120\).aspx) and guidelines for [choosing the right bucket_count](https://technet.microsoft.com/library/dn494956\(v=sql.120\).aspx).</span></span>  
  
 <span data-ttu-id="ef1d4-252">Gli indici nelle tabelle migrate sono stati ottimizzati per il carico di lavoro dimostrativo dell'elaborazione degli ordini vendita.</span><span class="sxs-lookup"><span data-stu-id="ef1d4-252">The indexes on the migrated tables have been tuned for the demo sales order processing workload.</span></span> <span data-ttu-id="ef1d4-253">Il carico di lavoro si basa sugli inserimenti e sulle ricerche di punti nelle tabelle Sales.SalesOrderHeader_inmem e Sales.SalesOrderDetail_inmem, nonché sulle ricerche di punti nelle colonne chiavi primarie nelle tabelle Production.Product_inmem e Sales.SpecialOffer_inmem.</span><span class="sxs-lookup"><span data-stu-id="ef1d4-253">The workload relies on inserts and point lookups in the tables Sales.SalesOrderHeader_inmem and Sales.SalesOrderDetail_inmem, and it also relies on point lookups on the primary key columns in the tables Production.Product_inmem and Sales.SpecialOffer_inmem.</span></span>  
  
 <span data-ttu-id="ef1d4-254">Sales.SalesOrderHeader_inmem prevede tre indici, che sono tutti di tipo HASH per motivi di prestazioni e perché per il carico di lavoro non sono necessarie analisi ordinate, né dell'intervallo.</span><span class="sxs-lookup"><span data-stu-id="ef1d4-254">Sales.SalesOrderHeader_inmem has three indexes, which are all HASH indexes for performance reasons, and because no ordered or range scans are needed for the workload.</span></span>  
  
-   <span data-ttu-id="ef1d4-255">Indice HASH in (SalesOrderID): il bucket_count viene ridimensionato a 10 milioni (arrotondato fino a 16 milione), poiché il numero previsto di ordini vendita è pari a 10 milioni.</span><span class="sxs-lookup"><span data-stu-id="ef1d4-255">HASH index on (SalesOrderID): bucket_count is sized at 10 million (rounded up to 16 million), because the expected number of sales orders is 10 million</span></span>  
  
-   <span data-ttu-id="ef1d4-256">Indice HASH in (SalesPersonID): il bucket_count è pari a 1 milione.</span><span class="sxs-lookup"><span data-stu-id="ef1d4-256">HASH index on (SalesPersonID): bucket_count is 1 million.</span></span> <span data-ttu-id="ef1d4-257">Il set di dati fornito non include molti venditori, ma tiene conto della crescita futura, nonché delle mancate conseguenze in termini di riduzione delle prestazioni per le ricerche di punti in caso di ridimensionamento eccessivo del bucket_count.</span><span class="sxs-lookup"><span data-stu-id="ef1d4-257">The data set provided does not have a lot of sales persons, but this allows for future growth, plus you don't pay a performance penalty for point lookups if the bucket_count is oversized.</span></span>  
  
-   <span data-ttu-id="ef1d4-258">Indice HASH in (CustomerID): il bucket_count è pari a 1 milione.</span><span class="sxs-lookup"><span data-stu-id="ef1d4-258">HASH index on (CustomerID): bucket_count is 1 million.</span></span> <span data-ttu-id="ef1d4-259">Il set di dati specificato non include molti clienti, ma tiene conto della crescita futura.</span><span class="sxs-lookup"><span data-stu-id="ef1d4-259">The data set provided does not have a lot of customers, but this allows for future growth.</span></span>  
  
 <span data-ttu-id="ef1d4-260">Sales.SalesOrderDetail_inmem prevede tre indici, che sono tutti di tipo HASH per motivi di prestazioni e perché per il carico di lavoro non sono necessarie analisi ordinate, né dell'intervallo.</span><span class="sxs-lookup"><span data-stu-id="ef1d4-260">Sales.SalesOrderDetail_inmem has three indexes, which are all HASH indexes for performance reasons, and because no ordered or range scans are needed for the workload.</span></span>  
  
-   <span data-ttu-id="ef1d4-261">Indice HASH in (SalesOrderID, SalesOrderDetailID): si tratta dell'indice di chiave primaria e, anche se le ricerche in (SalesOrderID, SalesOrderDetailID) saranno rare, l'utilizzo di un indice hash per la chiave rende più veloce gli inserimenti di riga.</span><span class="sxs-lookup"><span data-stu-id="ef1d4-261">HASH index on (SalesOrderID, SalesOrderDetailID): this is the primary key index, and even though lookups on (SalesOrderID, SalesOrderDetailID) will be infrequent, using a hash index for the key speeds up row inserts.</span></span> <span data-ttu-id="ef1d4-262">Il bucket_count viene ridimensionato a 50 milioni (arrotondato fino a 67 milioni); il numero previsto di ordini vendita è 10 milioni che viene ridimensionato per ottenere una media di 5 articoli per ordine.</span><span class="sxs-lookup"><span data-stu-id="ef1d4-262">The bucket_count is sized at 50 million (rounded up to 67 million): the expected number of sales orders is 10 million, and this is sized to have an average of 5 items per order</span></span>  
  
-   <span data-ttu-id="ef1d4-263">Indice HASH in (SalesOrderID): le ricerche in base all'ordine vendita sono frequenti. È possibile individuare tutte le voci corrispondenti a un singolo ordine.</span><span class="sxs-lookup"><span data-stu-id="ef1d4-263">HASH index on (SalesOrderID): lookups by sales order are frequent: you will want to find all the line items corresponding to a single order.</span></span>  <span data-ttu-id="ef1d4-264">Il bucket_count viene ridimensionato a 10 milioni (arrotondato fino a 16 milione), poiché il numero previsto di ordini vendita è pari a 10 milioni.</span><span class="sxs-lookup"><span data-stu-id="ef1d4-264">bucket_count is sized at 10 million (rounded up to 16 million), because the expected number of sales orders is 10 million</span></span>  
  
-   <span data-ttu-id="ef1d4-265">Indice HASH in (ProductID): il bucket_count è pari a 1 milione.</span><span class="sxs-lookup"><span data-stu-id="ef1d4-265">HASH index on (ProductID): bucket_count is 1 million.</span></span> <span data-ttu-id="ef1d4-266">Il set di dati specificato non include molti prodotti, ma tiene conto della crescita futura.</span><span class="sxs-lookup"><span data-stu-id="ef1d4-266">The data set provided does not have a lot of product, but this allows for future growth.</span></span>  
  
 <span data-ttu-id="ef1d4-267">Production.Product_inmem prevede tre indici</span><span class="sxs-lookup"><span data-stu-id="ef1d4-267">Production.Product_inmem has three indexes</span></span>  
  
-   <span data-ttu-id="ef1d4-268">Indice HASH in (ProductID): le ricerche in ProductID si trovano in un percorso critico del carico di lavoro dimostrativo, pertanto si tratta di un indice hash</span><span class="sxs-lookup"><span data-stu-id="ef1d4-268">HASH index on (ProductID): lookups on ProductID are in the critical path for the demo workload, therefore this is a hash index</span></span>  
  
-   <span data-ttu-id="ef1d4-269">Indice NONCLUSTERED in (Name): tramite esso saranno possibili analisi ordinate dei nomi dei prodotti</span><span class="sxs-lookup"><span data-stu-id="ef1d4-269">NONCLUSTERED index on (Name): this will allow ordered scans of product names</span></span>  
  
-   <span data-ttu-id="ef1d4-270">Indice NONCLUSTERED in (ProductNumber): tramite esso saranno possibili analisi ordinate dei numeri dei prodotti</span><span class="sxs-lookup"><span data-stu-id="ef1d4-270">NONCLUSTERED index on (ProductNumber): this will allow ordered scans of product numbers</span></span>  
  
 <span data-ttu-id="ef1d4-271">Sales.SpecialOffer_inmem con un indice HASH in (SpecialOfferID): le ricerche di punti delle offerte speciali si trovano nella parte essenziale del carico di lavoro dimostrativo.</span><span class="sxs-lookup"><span data-stu-id="ef1d4-271">Sales.SpecialOffer_inmem has one HASH index on (SpecialOfferID): point lookups of special offers are in the critical part of the demo workload.</span></span> <span data-ttu-id="ef1d4-272">Il bucket_count viene ridimensionato a 1 milione per tener conto della crescita futura.</span><span class="sxs-lookup"><span data-stu-id="ef1d4-272">The bucket_count is sized at 1 million to allow for future growth.</span></span>  
  
 <span data-ttu-id="ef1d4-273">Nel carico di lavoro dimostrativo non viene fatto riferimento a Sales.SpecialOfferProduct_inmem, di conseguenza non vi sono esigenze apparenti di usare indici hash in questa tabella per ottimizzare il carico di lavoro; gli indici in (SpecialOfferID, ProductID) e (ProductID) sono NONCLUSTERED.</span><span class="sxs-lookup"><span data-stu-id="ef1d4-273">Sales.SpecialOfferProduct_inmem is not referenced in the demo workload, and thus there is no apparent need to use hash indexes on this table to optimize the workload - the indexes on (SpecialOfferID, ProductID) and (ProductID) are NONCLUSTERED.</span></span>  
  
 <span data-ttu-id="ef1d4-274">Si noti che nelle indicazioni sopra riportate, ad alcuni dei bucket_counts è stato applicato un ridimensionamento eccessivo, ma non ai bucket_counts per gli indici in SalesOrderHeader_inmem e SalesOrderDetail_inmem che vengono ridimensionati solo a 10 milioni di ordini vendita.</span><span class="sxs-lookup"><span data-stu-id="ef1d4-274">Notice that in the above some of the bucket_counts are over-sized, but not the bucket_counts for the indexes on SalesOrderHeader_inmem and SalesOrderDetail_inmem: they are sized for just 10 million sales orders.</span></span> <span data-ttu-id="ef1d4-275">Questa operazione viene eseguita per consentire l'installazione dell'esempio nei sistemi con disponibilità di memoria insufficiente, anche se in quei casi il carico di lavoro dimostrativo non può essere completato.</span><span class="sxs-lookup"><span data-stu-id="ef1d4-275">This was done to allow installing the sample on systems with low memory availability, although in those cases the demo workload will fail with out-of-memory.</span></span> <span data-ttu-id="ef1d4-276">Se si desidera scalare di oltre 10 milioni di ordini vendita, è possibile aumentare i numeri di bucket di conseguenza.</span><span class="sxs-lookup"><span data-stu-id="ef1d4-276">If you do want to scale well beyond 10 million sales orders, feel free to increase the bucket counts accordingly.</span></span>  
  
#### <a name="considerations-for-memory-utilization"></a><span data-ttu-id="ef1d4-277">Considerazioni sull'utilizzo della memoria</span><span class="sxs-lookup"><span data-stu-id="ef1d4-277">Considerations for memory utilization</span></span>  
 <span data-ttu-id="ef1d4-278">L'utilizzo della memoria nel database di esempio, sia prima che dopo l'esecuzione del carico di lavoro dimostrativo, è descritto nella sezione [Utilizzo della memoria per le tabelle ottimizzate per la memoria](#Memoryutilizationforthememory-optimizedtables).</span><span class="sxs-lookup"><span data-stu-id="ef1d4-278">Memory utilization in the sample database, both before and after running the demo workload, is discussed in the Section [Memory utilization for the memory-optimized tables](#Memoryutilizationforthememory-optimizedtables).</span></span>  
  
### <a name="stored-procedures-added-by-the-sample"></a><span data-ttu-id="ef1d4-279">Stored procedure aggiunte nell'esempio</span><span class="sxs-lookup"><span data-stu-id="ef1d4-279">Stored Procedures added by the sample</span></span>  
 <span data-ttu-id="ef1d4-280">Di seguito sono riportate due stored procedure principali per l'inserimento dell'ordine vendita e l'aggiornamento dei dettagli sulla spedizione:</span><span class="sxs-lookup"><span data-stu-id="ef1d4-280">The two key stored procedures for inserting sales order and updating shipping details are as follows:</span></span>  
  
-   <span data-ttu-id="ef1d4-281">Sales.usp_InsertSalesOrder_inmem</span><span class="sxs-lookup"><span data-stu-id="ef1d4-281">Sales.usp_InsertSalesOrder_inmem</span></span>  
  
    -   <span data-ttu-id="ef1d4-282">Inserisce un nuovo ordine vendita nel database e restituisce SalesOrderID per questi ordini vendita.</span><span class="sxs-lookup"><span data-stu-id="ef1d4-282">Inserts a new sales order in the database and outputs the SalesOrderID for that sales order.</span></span> <span data-ttu-id="ef1d4-283">Come parametri di input accetta i dettagli dell'intestazione dell'ordine vendita e le voci dell'ordine.</span><span class="sxs-lookup"><span data-stu-id="ef1d4-283">As input parameters it takes details for the sales order header, as well as the line items in the order.</span></span>  
  
    -   <span data-ttu-id="ef1d4-284">Parametro di output:</span><span class="sxs-lookup"><span data-stu-id="ef1d4-284">Output parameter:</span></span>  
  
        -   <span data-ttu-id="ef1d4-285">@SalesOrderID int: SalesOrderID per l'ordine vendita appena inserito</span><span class="sxs-lookup"><span data-stu-id="ef1d4-285">@SalesOrderID int - the SalesOrderID for the sales order that was just inserted</span></span>  
  
    -   <span data-ttu-id="ef1d4-286">Parametri di input (obbligatori):</span><span class="sxs-lookup"><span data-stu-id="ef1d4-286">Input parameters (required):</span></span>  
  
        -   <span data-ttu-id="ef1d4-287">@DueDate datetime2</span><span class="sxs-lookup"><span data-stu-id="ef1d4-287">@DueDate datetime2</span></span>  
  
        -   <span data-ttu-id="ef1d4-288">@CustomerID int</span><span class="sxs-lookup"><span data-stu-id="ef1d4-288">@CustomerID int</span></span>  
  
        -   <span data-ttu-id="ef1d4-289">@BillToAddressID [int]</span><span class="sxs-lookup"><span data-stu-id="ef1d4-289">@BillToAddressID [int]</span></span>  
  
        -   <span data-ttu-id="ef1d4-290">@ShipToAddressID [int]</span><span class="sxs-lookup"><span data-stu-id="ef1d4-290">@ShipToAddressID [int]</span></span>  
  
        -   <span data-ttu-id="ef1d4-291">@ShipMethodID [int]</span><span class="sxs-lookup"><span data-stu-id="ef1d4-291">@ShipMethodID [int]</span></span>  
  
        -   <span data-ttu-id="ef1d4-292">@SalesOrderDetails Sales.SalesOrderDetailType_inmem: TVP contenente voci dell'ordine</span><span class="sxs-lookup"><span data-stu-id="ef1d4-292">@SalesOrderDetails Sales.SalesOrderDetailType_inmem - TVP that contains the line items of the order</span></span>  
  
    -   <span data-ttu-id="ef1d4-293">Parametri di input (facoltativi):</span><span class="sxs-lookup"><span data-stu-id="ef1d4-293">Input parameters (optional):</span></span>  
  
        -   <span data-ttu-id="ef1d4-294">@Status [tinyint]</span><span class="sxs-lookup"><span data-stu-id="ef1d4-294">@Status [tinyint]</span></span>  
  
        -   <span data-ttu-id="ef1d4-295">@OnlineOrderFlag [bit]</span><span class="sxs-lookup"><span data-stu-id="ef1d4-295">@OnlineOrderFlag [bit]</span></span>  
  
        -   <span data-ttu-id="ef1d4-296">@PurchaseOrderNumber [nvarchar](25\)</span><span class="sxs-lookup"><span data-stu-id="ef1d4-296">@PurchaseOrderNumber [nvarchar](25\)</span></span>  
  
        -   <span data-ttu-id="ef1d4-297">@AccountNumber [nvarchar](15\)</span><span class="sxs-lookup"><span data-stu-id="ef1d4-297">@AccountNumber [nvarchar](15\)</span></span>  
  
        -   <span data-ttu-id="ef1d4-298">@SalesPersonID [int]</span><span class="sxs-lookup"><span data-stu-id="ef1d4-298">@SalesPersonID [int]</span></span>  
  
        -   <span data-ttu-id="ef1d4-299">@TerritoryID [int]</span><span class="sxs-lookup"><span data-stu-id="ef1d4-299">@TerritoryID [int]</span></span>  
  
        -   <span data-ttu-id="ef1d4-300">@CreditCardID [int]</span><span class="sxs-lookup"><span data-stu-id="ef1d4-300">@CreditCardID [int]</span></span>  
  
        -   <span data-ttu-id="ef1d4-301">@CreditCardApprovalCode [varchar](15\)</span><span class="sxs-lookup"><span data-stu-id="ef1d4-301">@CreditCardApprovalCode [varchar](15\)</span></span>  
  
        -   <span data-ttu-id="ef1d4-302">@CurrencyRateID [int]</span><span class="sxs-lookup"><span data-stu-id="ef1d4-302">@CurrencyRateID [int]</span></span>  
  
        -   <span data-ttu-id="ef1d4-303">@Comment nvarchar(128)</span><span class="sxs-lookup"><span data-stu-id="ef1d4-303">@Comment nvarchar(128)</span></span>  
  
-   <span data-ttu-id="ef1d4-304">Sales.usp_UpdateSalesOrderShipInfo_inmem</span><span class="sxs-lookup"><span data-stu-id="ef1d4-304">Sales.usp_UpdateSalesOrderShipInfo_inmem</span></span>  
  
    -   <span data-ttu-id="ef1d4-305">Aggiornare le informazioni sulla spedizione per un ordine vendita specificato.</span><span class="sxs-lookup"><span data-stu-id="ef1d4-305">Update the shipping information for a given sales order.</span></span> <span data-ttu-id="ef1d4-306">Verranno aggiornate anche le informazioni sulla spedizione di tutte le voci dell'ordine vendita.</span><span class="sxs-lookup"><span data-stu-id="ef1d4-306">This will also update the shipping information for all line items of the sales order.</span></span>  
  
    -   <span data-ttu-id="ef1d4-307">Si tratta di una stored procedure wrapper per le stored procedure compilate a livello nativo Sales.usp_UpdateSalesOrderShipInfo_native con logica di riesecuzione per gestire i potenziali (imprevisti) conflitti con transazioni simultanee con cui viene aggiornato lo stesso ordine.</span><span class="sxs-lookup"><span data-stu-id="ef1d4-307">This is a wrapper procedure for the natively compiled stored procedures Sales.usp_UpdateSalesOrderShipInfo_native with retry logic to deal with (unexpected) potential conflicts with concurrent transactions updating the same order.</span></span> <span data-ttu-id="ef1d4-308">Per altre informazioni sulla logica di riesecuzione, vedere l'argomento nella documentazione online [qui](https://technet.microsoft.com/library/dn169141\(v=sql.120\).aspx).</span><span class="sxs-lookup"><span data-stu-id="ef1d4-308">For more information about retry logic see the Books Online topic [here](https://technet.microsoft.com/library/dn169141\(v=sql.120\).aspx).</span></span>  
  
-   <span data-ttu-id="ef1d4-309">Sales.usp_UpdateSalesOrderShipInfo_native</span><span class="sxs-lookup"><span data-stu-id="ef1d4-309">Sales.usp_UpdateSalesOrderShipInfo_native</span></span>  
  
    -   <span data-ttu-id="ef1d4-310">Si tratta della stored procedure compilata a livello nativo tramite cui viene elaborato effettivamente l'aggiornamento delle informazioni sulla spedizione.</span><span class="sxs-lookup"><span data-stu-id="ef1d4-310">This is the natively compiled stored procedure that actually processes the update to the shipping information.</span></span> <span data-ttu-id="ef1d4-311">Ciò significa che viene chiamata dalla stored procedure wrapper Sales.usp_UpdateSalesOrderShipInfo_inmem.</span><span class="sxs-lookup"><span data-stu-id="ef1d4-311">It is means to be called from the wrapper stored procedure Sales.usp_UpdateSalesOrderShipInfo_inmem.</span></span> <span data-ttu-id="ef1d4-312">Se tramite il client è possibile gestire gli errori e implementare la logica di riesecuzione, è possibile chiamare direttamente questa procedura, anziché usare quella wrapper.</span><span class="sxs-lookup"><span data-stu-id="ef1d4-312">If the client can deal with failures and implements retry logic, you can call this procedure directly, rather than using the wrapper stored procedure.</span></span>  
  
 <span data-ttu-id="ef1d4-313">La stored procedure seguente viene utilizzata per il carico di lavoro dimostrativo.</span><span class="sxs-lookup"><span data-stu-id="ef1d4-313">The following stored procedure is used for the demo workload.</span></span>  
  
-   <span data-ttu-id="ef1d4-314">Demo.usp_DemoReset</span><span class="sxs-lookup"><span data-stu-id="ef1d4-314">Demo.usp_DemoReset</span></span>  
  
    -   <span data-ttu-id="ef1d4-315">Reimposta la dimostrazione svuotando e reinizializzando le tabelle SalesOrderHeader e SalesOrderDetail.</span><span class="sxs-lookup"><span data-stu-id="ef1d4-315">Resets the demo by emptying and reseeding the SalesOrderHeader and SalesOrderDetail tables.</span></span>  
  
 <span data-ttu-id="ef1d4-316">Le stored procedure seguenti vengono utilizzate per l'inserimento nelle tabelle ottimizzate per la memoria ed eliminazione da queste ultime garantendo, nel contempo, le integrità di dominio e referenziale.</span><span class="sxs-lookup"><span data-stu-id="ef1d4-316">The following stored procedures are used for inserting in and deleting from memory-optimized tables while guaranteeing domain and referential integrity.</span></span>  
  
-   <span data-ttu-id="ef1d4-317">Production.usp_InsertProduct_inmem</span><span class="sxs-lookup"><span data-stu-id="ef1d4-317">Production.usp_InsertProduct_inmem</span></span>  
  
-   <span data-ttu-id="ef1d4-318">Production.usp_DeleteProduct_inmem</span><span class="sxs-lookup"><span data-stu-id="ef1d4-318">Production.usp_DeleteProduct_inmem</span></span>  
  
-   <span data-ttu-id="ef1d4-319">Sales.usp_InsertSpecialOffer_inmem</span><span class="sxs-lookup"><span data-stu-id="ef1d4-319">Sales.usp_InsertSpecialOffer_inmem</span></span>  
  
-   <span data-ttu-id="ef1d4-320">Sales.usp_DeleteSpecialOffer_inmem</span><span class="sxs-lookup"><span data-stu-id="ef1d4-320">Sales.usp_DeleteSpecialOffer_inmem</span></span>  
  
-   <span data-ttu-id="ef1d4-321">Sales.usp_InsertSpecialOfferProduct_inmem</span><span class="sxs-lookup"><span data-stu-id="ef1d4-321">Sales.usp_InsertSpecialOfferProduct_inmem</span></span>  
  
 <span data-ttu-id="ef1d4-322">Infine, la stored procedure seguente viene utilizzata per verificare le integrità di dominio e referenziale.</span><span class="sxs-lookup"><span data-stu-id="ef1d4-322">Finally the following stored procedure is used to verify domain and referential integrity.</span></span>  
  
1.  <span data-ttu-id="ef1d4-323">dbo.usp_ValidateIntegrity</span><span class="sxs-lookup"><span data-stu-id="ef1d4-323">dbo.usp_ValidateIntegrity</span></span>  
  
    -   <span data-ttu-id="ef1d4-324">Parametro facoltativo: @object_id: ID dell'oggetto per cui convalidare l'integrità</span><span class="sxs-lookup"><span data-stu-id="ef1d4-324">Optional parameter: @object_id - ID of the object to validate integrity for</span></span>  
  
    -   <span data-ttu-id="ef1d4-325">Questa procedura si basa sulle tabelle dbo.DomainIntegrity, dbo.ReferentialIntegrity e dbo.UniqueIntegrity per le regole di integrità che devono essere verificate. Nell'esempio queste tabelle vengono popolate in base ai vincoli CHECK, di chiave esterna e univoci presenti per le tabelle originali nel database AdventureWorks.</span><span class="sxs-lookup"><span data-stu-id="ef1d4-325">This procedure relies on the tables dbo.DomainIntegrity, dbo.ReferentialIntegrity, and dbo.UniqueIntegrity for the integrity rules that need to be verified - the sample populates these tables based on the check, foreign key, and unique constraints that exist for the original tables in the AdventureWorks database.</span></span>  
  
    -   <span data-ttu-id="ef1d4-326">Si basa sulle procedure helper dbo.usp_GenerateCKCheck, dbo.usp_GenerateFKCheck e dbo.GenerateUQCheck per generare il codice T-SQL necessario per eseguire i controlli di integrità.</span><span class="sxs-lookup"><span data-stu-id="ef1d4-326">It relies on the helper procedures dbo.usp_GenerateCKCheck, dbo.usp_GenerateFKCheck, and dbo.GenerateUQCheck to generate the T-SQL needed for performing the integrity checks.</span></span>  
  
##  <a name="performance-measurements-using-the-demo-workload"></a><a name="PerformanceMeasurementsusingtheDemoWorkload"></a> <span data-ttu-id="ef1d4-327">Misurazioni delle prestazioni con il carico di lavoro dimostrativo</span><span class="sxs-lookup"><span data-stu-id="ef1d4-327">Performance Measurements using the Demo Workload</span></span>  
 <span data-ttu-id="ef1d4-328">Ostress è uno strumento da riga di comando sviluppato dal team di supporto [!INCLUDE[msCoName](../includes/msconame-md.md)] CSS [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="ef1d4-328">Ostress is a command-line tool that was developed by the [!INCLUDE[msCoName](../includes/msconame-md.md)] CSS [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] support team.</span></span> <span data-ttu-id="ef1d4-329">Questo strumento può essere utilizzato per eseguire query o stored procedure in parallelo.</span><span class="sxs-lookup"><span data-stu-id="ef1d4-329">This tool can be used to execute queries or run stored procedures in parallel.</span></span> <span data-ttu-id="ef1d4-330">È possibile configurare il numero di thread per eseguire un'istruzione T-SQL fornita in parallelo e specificare il numero di esecuzioni dell'istruzione in questo thread. Tramite ostress viene eseguita l'accelerazione dei thread e l'istruzione viene eseguita in tutti i thread in parallelo.</span><span class="sxs-lookup"><span data-stu-id="ef1d4-330">You can configure the number of threads to run a given T-SQL statement in parallel, and you can specify how many times the statement should be executed on this thread; ostress will spin up the threads and execute the statement on all threads in parallel.</span></span> <span data-ttu-id="ef1d4-331">Al termine dell'esecuzione di tutti i thread, tramite ostress verrà segnalato il tempo impiegato per il completamento dell'esecuzione di tutti i thread.</span><span class="sxs-lookup"><span data-stu-id="ef1d4-331">After execution finishes for all threads, ostress will report the time taken for all threads to finish execution.</span></span>  
  
### <a name="installing-ostress"></a><span data-ttu-id="ef1d4-332">Installazione di ostress</span><span class="sxs-lookup"><span data-stu-id="ef1d4-332">Installing ostress</span></span>  
 <span data-ttu-id="ef1d4-333">Ostress viene installato come parte delle utilità RML. La relativa installazione non viene eseguita in modalità autonoma.</span><span class="sxs-lookup"><span data-stu-id="ef1d4-333">Ostress is installed as part of the RML Utilities; there is no standalone installation for ostress.</span></span>  
  
 <span data-ttu-id="ef1d4-334">Passaggi dell'installazione:</span><span class="sxs-lookup"><span data-stu-id="ef1d4-334">Installation steps:</span></span>  
  
1.  <span data-ttu-id="ef1d4-335">Scaricare ed eseguire il pacchetto di installazione x64 per le utilità RML dalla pagina seguente:[https://blogs.msdn.com/b/psssql/archive/2013/10/29/cumulative-update-2-to-the-rml-utilities-for-microsoft-sql-server-released.aspx](https://blogs.msdn.com/b/psssql/archive/2013/10/29/cumulative-update-2-to-the-rml-utilities-for-microsoft-sql-server-released.aspx)</span><span class="sxs-lookup"><span data-stu-id="ef1d4-335">Download and run the x64 installation package for the RML utilities from the following page: [https://blogs.msdn.com/b/psssql/archive/2013/10/29/cumulative-update-2-to-the-rml-utilities-for-microsoft-sql-server-released.aspx](https://blogs.msdn.com/b/psssql/archive/2013/10/29/cumulative-update-2-to-the-rml-utilities-for-microsoft-sql-server-released.aspx)</span></span>  
  
2.  <span data-ttu-id="ef1d4-336">Se viene visualizzata una finestra di dialogo indicante l'utilizzo di determinati file, scegliere 'Continua'.</span><span class="sxs-lookup"><span data-stu-id="ef1d4-336">If there is a dialog box saying certain files are in use, click 'Continue'</span></span>  
  
### <a name="running-ostress"></a><span data-ttu-id="ef1d4-337">Esecuzione di ostress</span><span class="sxs-lookup"><span data-stu-id="ef1d4-337">Running ostress</span></span>  
 <span data-ttu-id="ef1d4-338">Ostress viene eseguito dal prompt della riga di comando.</span><span class="sxs-lookup"><span data-stu-id="ef1d4-338">Ostress is run from the command-line prompt.</span></span> <span data-ttu-id="ef1d4-339">È più semplice eseguire lo strumento dal prompt dei comandi RML, installato come parte delle utilità RML.</span><span class="sxs-lookup"><span data-stu-id="ef1d4-339">It is most convenient to run the tool from the "RML Cmd Prompt", which is installed as part of the RML Utilities.</span></span>  
  
 <span data-ttu-id="ef1d4-340">Per aprire il prompt dei comandi RML, seguire queste istruzioni:</span><span class="sxs-lookup"><span data-stu-id="ef1d4-340">To open the RML Cmd Prompt follow these instructions:</span></span>  
  
 <span data-ttu-id="ef1d4-341">In Windows Server 2012 [R2] e in Windows 8 e 8.1 aprire il menu Start facendo clic sul pulsante Windows, quindi digitare 'rml'.</span><span class="sxs-lookup"><span data-stu-id="ef1d4-341">In Windows Server 2012 [R2] and in Windows 8 and 8.1, open the start menu by clicking the Windows key, and type 'rml'.</span></span> <span data-ttu-id="ef1d4-342">Fare clic sul prompt dei comandi RML, che sarà disponibile nell'elenco dei risultati della ricerca.</span><span class="sxs-lookup"><span data-stu-id="ef1d4-342">Click on "RML Cmd Prompt", which will be in the list of search results.</span></span>  
  
 <span data-ttu-id="ef1d4-343">Verificare che il prompt dei comandi si trovi nella cartella di installazione delle utilità RML.</span><span class="sxs-lookup"><span data-stu-id="ef1d4-343">Ensure that the command prompt is located in the RML Utilities installation folder.</span></span> <span data-ttu-id="ef1d4-344">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="ef1d4-344">For example:</span></span>  
  
 ![](../../2014/database-engine/media/SQLServer2014RTMIn-MemoryOLTP01.jpg)  
  
 <span data-ttu-id="ef1d4-345">Le opzioni della riga di comando per ostress possono essere visualizzate eseguendo semplicemente ostress.exe senza opzioni della riga di comando.</span><span class="sxs-lookup"><span data-stu-id="ef1d4-345">The command-line options for ostress can be seen when simply running ostress.exe without any command-line options.</span></span> <span data-ttu-id="ef1d4-346">Le opzioni principali da considerare per eseguire ostress con questo esempio sono:</span><span class="sxs-lookup"><span data-stu-id="ef1d4-346">The main options to consider for running ostress with this sample are:</span></span>  
  
-   <span data-ttu-id="ef1d4-347">-S. Nome dell'istanza di [!INCLUDE[msCoName](../includes/msconame-md.md)][!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] alla quale connettersi</span><span class="sxs-lookup"><span data-stu-id="ef1d4-347">-S name of [!INCLUDE[msCoName](../includes/msconame-md.md)][!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] instance to connect to</span></span>  
  
-   <span data-ttu-id="ef1d4-348">-E usa l'autenticazione di Windows per la connessione (impostazione predefinita); Se si utilizza l' [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] autenticazione di, utilizzare le opzioni-u e-P per specificare rispettivamente il nome utente e la password</span><span class="sxs-lookup"><span data-stu-id="ef1d4-348">-E use Windows authentication to connect (default); if you use [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] authentication, use the options -U and -P to specify the username and password, respectively</span></span>  
  
-   <span data-ttu-id="ef1d4-349">-d. Nome del database, per questo esempio AdventureWorks2014</span><span class="sxs-lookup"><span data-stu-id="ef1d4-349">-d name of the database, for this example AdventureWorks2014</span></span>  
  
-   <span data-ttu-id="ef1d4-350">-Q. L'istruzione T-SQL da eseguire</span><span class="sxs-lookup"><span data-stu-id="ef1d4-350">-Q the T-SQL statement to be executed</span></span>  
  
-   <span data-ttu-id="ef1d4-351">-n. Numero di connessioni tramite cui viene eseguita l'elaborazione di ogni query o file di input</span><span class="sxs-lookup"><span data-stu-id="ef1d4-351">-n number of connections processing each input file/query</span></span>  
  
-   <span data-ttu-id="ef1d4-352">-r. Numero di iterazioni per ogni connessione per eseguire ogni query o file di input</span><span class="sxs-lookup"><span data-stu-id="ef1d4-352">-r the number of iterations for each connection to execute each input file/query</span></span>  
  
### <a name="demo-workload"></a><span data-ttu-id="ef1d4-353">Carico di lavoro dimostrativo</span><span class="sxs-lookup"><span data-stu-id="ef1d4-353">Demo Workload</span></span>  
 <span data-ttu-id="ef1d4-354">La stored procedure principale utilizzata nel carico di lavoro dimostrativo è Sales.usp_InsertSalesOrder_inmem/ondisk.</span><span class="sxs-lookup"><span data-stu-id="ef1d4-354">The main stored procedure used in the demo workload is Sales.usp_InsertSalesOrder_inmem/ondisk.</span></span> <span data-ttu-id="ef1d4-355">Tramite lo script riportato di seguito viene costruito un parametro con valori di tabella (TVP) con dati di esempio e viene chiamata la procedura per inserire un ordine vendita con 5 voci.</span><span class="sxs-lookup"><span data-stu-id="ef1d4-355">The script in the below constructs a table-valued parameter (TVP) with sample data, and calls the procedure to insert a sales order with 5 line items.</span></span>  
  
 <span data-ttu-id="ef1d4-356">Lo strumento ostress viene utilizzato per eseguire le chiamate di stored procedure in parallelo, per simulare i client tramite cui vengono inseriti contemporaneamente gli ordini vendita.</span><span class="sxs-lookup"><span data-stu-id="ef1d4-356">The ostress tool is used to execute the stored procedure calls in parallel, to simulate clients inserting sales orders concurrently.</span></span>  
  
 <span data-ttu-id="ef1d4-357">Reimpostare la dimostrazione dopo ogni esecuzione di test di stress eseguendo Demo.usp_DemoReset.</span><span class="sxs-lookup"><span data-stu-id="ef1d4-357">Reset the demo after each stress run executing Demo.usp_DemoReset.</span></span> <span data-ttu-id="ef1d4-358">Tramite questa procedura vengono eliminate le righe nelle tabelle ottimizzate per la memoria, vengono troncate le tabelle basate su disco e viene eseguito un checkpoint del database.</span><span class="sxs-lookup"><span data-stu-id="ef1d4-358">This procedure deletes the rows in the memory-optimized tables, truncates the disk-based tables, and executes a database checkpoint.</span></span>  
  
 <span data-ttu-id="ef1d4-359">Lo script seguente viene eseguito simultaneamente per simulare un carico di lavoro di elaborazione degli ordini vendita:</span><span class="sxs-lookup"><span data-stu-id="ef1d4-359">The following script is executed concurrently to simulate a sales order processing workload:</span></span>  
  
```  
DECLARE   
      @i int = 0,   
      @od Sales.SalesOrderDetailType_inmem,   
      @SalesOrderID int,   
      @DueDate datetime2 = sysdatetime(),   
      @CustomerID int = rand() * 8000,   
      @BillToAddressID int = rand() * 10000,   
      @ShipToAddressID int = rand() * 10000,   
      @ShipMethodID int = (rand() * 5) + 1;   
  
INSERT INTO @od   
SELECT OrderQty, ProductID, SpecialOfferID   
FROM Demo.DemoSalesOrderDetailSeed   
WHERE OrderID= cast((rand()*106) + 1 as int);   
  
WHILE (@i < 20)   
BEGIN;   
      EXEC Sales.usp_InsertSalesOrder_inmem @SalesOrderID OUTPUT, @DueDate, @CustomerID, @BillToAddressID, @ShipToAddressID, @ShipMethodID, @od;   
      SET @i += 1   
END  
  
```  
  
 <span data-ttu-id="ef1d4-360">Con questo script, ogni ordine di esempio creato viene inserito 20 volte, tramite 20 stored procedure eseguite in un ciclo WHILE.</span><span class="sxs-lookup"><span data-stu-id="ef1d4-360">With this script, each sample order that is constructed is inserted 20 times, through 20 stored procedures executed in a WHILE loop.</span></span> <span data-ttu-id="ef1d4-361">Il ciclo viene utilizzato per rappresentare il fatto che il database viene utilizzato per creare l'ordine di esempio.</span><span class="sxs-lookup"><span data-stu-id="ef1d4-361">The loop is used to account for the fact that the database is used to construct the sample order.</span></span> <span data-ttu-id="ef1d4-362">Negli ambienti di produzione tipici, tramite l'applicazione di livello intermedio verrà costruito l'ordine vendita da inserire.</span><span class="sxs-lookup"><span data-stu-id="ef1d4-362">In typical production environments, the mid-tier application will construct the sales order to be inserted.</span></span>  
  
 <span data-ttu-id="ef1d4-363">Tramite lo script precedente gli ordini vendita vengono inseriti nelle tabelle ottimizzate per la memoria.</span><span class="sxs-lookup"><span data-stu-id="ef1d4-363">The above script inserts sales orders into memory-optimized tables.</span></span> <span data-ttu-id="ef1d4-364">Lo script per inserire gli ordini vendita nelle tabelle basate su disco deriva dalla sostituzione di due occorrenze di '_inmem' con '_ondisk'.</span><span class="sxs-lookup"><span data-stu-id="ef1d4-364">The script to insert sales orders into disk-based tables is derived by replacing the two occurrences of '_inmem' with '_ondisk'.</span></span>  
  
 <span data-ttu-id="ef1d4-365">Si utilizzerà lo strumento ostress per eseguire gli script utilizzando diverse connessioni simultanee.</span><span class="sxs-lookup"><span data-stu-id="ef1d4-365">We will use the ostress tool to execute the scripts using several concurrent connections.</span></span> <span data-ttu-id="ef1d4-366">Si utilizzerà il parametro '-n' per controllare il numero di connessioni e il parametro 'r' per controllare il numero di volte in cui lo script viene eseguito in ogni connessione.</span><span class="sxs-lookup"><span data-stu-id="ef1d4-366">We will use the parameter '-n' to control the number of connections, and the parameter 'r' to control how many times the script is executed on each connection.</span></span>  
  
#### <a name="functional-validation-of-the-workload"></a><span data-ttu-id="ef1d4-367">Convalida funzionale del carico di lavoro</span><span class="sxs-lookup"><span data-stu-id="ef1d4-367">Functional Validation of the Workload</span></span>  
 <span data-ttu-id="ef1d4-368">Per verificare che tutto funzioni, si inizierà con un test di esempio, usando 10 connessioni simultanee e 5 iterazioni, inserendo un totale di 10 \* 5 \* 20 = 1000 di ordini di vendita.</span><span class="sxs-lookup"><span data-stu-id="ef1d4-368">To verify everything works, we will start with a sample test, using 10 concurrent connects and 5 iterations, inserting a total of 10 \* 5 \* 20 = 1000 sales order.</span></span>  
  
 <span data-ttu-id="ef1d4-369">Con il comando seguente si supponga di usare l'istanza predefinita nel computer locale.</span><span class="sxs-lookup"><span data-stu-id="ef1d4-369">With the below command we assume using the default instance on the local machine.</span></span> <span data-ttu-id="ef1d4-370">Se si utilizza un'istanza denominata o un server remoto, modificare il nome del server di conseguenza, utilizzando il parametro -S.</span><span class="sxs-lookup"><span data-stu-id="ef1d4-370">If you are using a named instance or using a remote server, change the server name accordingly, using the parameter -S.</span></span>  
  
 <span data-ttu-id="ef1d4-371">Inserire 1000 ordini vendita nelle tabelle ottimizzate per la memoria utilizzando il comando seguente nel prompt dei comandi RML:</span><span class="sxs-lookup"><span data-stu-id="ef1d4-371">Insert 1000 sales orders in memory-optimized tables use the following command in the RML Cmd Prompt:</span></span>  
  
 <span data-ttu-id="ef1d4-372">Fare clic sul pulsante Copia per copiare il comando e incollarlo nel prompt dei comandi delle utilità RML.</span><span class="sxs-lookup"><span data-stu-id="ef1d4-372">Click the Copy button to copy the command, and paste it into the RML Utilities command prompt.</span></span>  
  
```  
ostress.exe -n10 -r5 -S. -E -dAdventureWorks2014 -q -Q"DECLARE @i int = 0, @od Sales.SalesOrderDetailType_inmem, @SalesOrderID int, @DueDate datetime2 = sysdatetime(), @CustomerID int = rand() * 8000, @BillToAddressID int = rand() * 10000, @ShipToAddressID int = rand() * 10000, @ShipMethodID int = (rand() * 5) + 1; INSERT INTO @od SELECT OrderQty, ProductID, SpecialOfferID FROM Demo.DemoSalesOrderDetailSeed WHERE OrderID= cast((rand()*106) + 1 as int); while (@i < 20) begin; EXEC Sales.usp_InsertSalesOrder_inmem @SalesOrderID OUTPUT, @DueDate, @CustomerID, @BillToAddressID, @ShipToAddressID, @ShipMethodID, @od; set @i += 1 end"  
```  
  
 <span data-ttu-id="ef1d4-373">Se tutto funziona come previsto, la finestra di comando sarà simile a quanto riportato di seguito.</span><span class="sxs-lookup"><span data-stu-id="ef1d4-373">If everything works as expected, your command window will look similar to the following.</span></span> <span data-ttu-id="ef1d4-374">I messaggi di errore non sono previsti.</span><span class="sxs-lookup"><span data-stu-id="ef1d4-374">Error messages are not expected.</span></span>  
  
 ![](../../2014/database-engine/media/SQLServer2014RTMIn-MemoryOLTP02.jpg)  
  
 <span data-ttu-id="ef1d4-375">Verificare che anche il carico di lavoro funzioni come previsto per le tabelle basate su disco eseguendo il comando riportato di seguito nel prompt dei comandi RML:</span><span class="sxs-lookup"><span data-stu-id="ef1d4-375">Validate that also the workload functions as expected for disk-based tables by running the following command in the RML Cmd Prompt:</span></span>  
  
 <span data-ttu-id="ef1d4-376">Fare clic sul pulsante Copia per copiare il comando e incollarlo nel prompt dei comandi delle utilità RML.</span><span class="sxs-lookup"><span data-stu-id="ef1d4-376">Click the Copy button to copy the command, and paste it into the RML Utilities command prompt.</span></span>  
  
```  
ostress.exe -n10 -r5 -S. -E -dAdventureWorks2014 -q -Q"DECLARE @i int = 0, @od Sales.SalesOrderDetailType_ondisk, @SalesOrderID int, @DueDate datetime2 = sysdatetime(), @CustomerID int = rand() * 8000, @BillToAddressID int = rand() * 10000, @ShipToAddressID int = rand() * 10000, @ShipMethodID int = (rand() * 5) + 1; INSERT INTO @od SELECT OrderQty, ProductID, SpecialOfferID FROM Demo.DemoSalesOrderDetailSeed WHERE OrderID= cast((rand()*106) + 1 as int); while (@i < 20) begin; EXEC Sales.usp_InsertSalesOrder_ondisk @SalesOrderID OUTPUT, @DueDate, @CustomerID, @BillToAddressID, @ShipToAddressID, @ShipMethodID, @od; set @i += 1 end"  
```  
  
#### <a name="running-the-workload"></a><span data-ttu-id="ef1d4-377">Esecuzione del carico di lavoro</span><span class="sxs-lookup"><span data-stu-id="ef1d4-377">Running the Workload</span></span>  
 <span data-ttu-id="ef1d4-378">Per testare una scala vengono inseriti 10 milioni di ordini vendita, utilizzando 100 connessioni.</span><span class="sxs-lookup"><span data-stu-id="ef1d4-378">To test at scale we insert 10 million sales orders, using 100 connections.</span></span> <span data-ttu-id="ef1d4-379">Questo test viene eseguito ragionevolmente in un server modesto, ad esempio con 8 core fisici e 16 logici, e un'archiviazione sull'unità SSD di base per il log.</span><span class="sxs-lookup"><span data-stu-id="ef1d4-379">This test performs reasonably on a modest server (e.g., 8 physical, 16 logical cores), and basic SSD storage for the log.</span></span> <span data-ttu-id="ef1d4-380">Se il test non viene eseguito correttamente nell'hardware, consultare la sezione [Risoluzione dei problemi relativi ai test con esecuzione prolungata](#Troubleshootingslow-runningtests). Se si vuole ridurre il livello di stress per questo test, ridurre il numero di connessioni modificando il parametro '-n'.</span><span class="sxs-lookup"><span data-stu-id="ef1d4-380">If the test does not perform well on your hardware, take look at the Section [Troubleshooting slow-running tests](#Troubleshootingslow-runningtests).If you want to reduce the level of stress for this test, lower the number of connections by changing the parameter '-n'.</span></span> <span data-ttu-id="ef1d4-381">Ad esempio, per abbassare il numero di connessioni a 40, impostare il parametro '-n100' su '-n40'.</span><span class="sxs-lookup"><span data-stu-id="ef1d4-381">For example to lower the connection count to 40, change the parameter '-n100' to '-n40'.</span></span>  
  
 <span data-ttu-id="ef1d4-382">Come misura delle prestazioni del carico di lavoro è possibile usare il tempo trascorso come riportato da ostress.exe dopo l'esecuzione del carico di lavoro.</span><span class="sxs-lookup"><span data-stu-id="ef1d4-382">As a performance measure for the workload we use the elapsed time as reported by ostress.exe after running the workload.</span></span>  
  
##### <a name="memory-optimized-tables"></a><span data-ttu-id="ef1d4-383">Tabelle ottimizzate per la memoria</span><span class="sxs-lookup"><span data-stu-id="ef1d4-383">Memory-optimized tables</span></span>  
 <span data-ttu-id="ef1d4-384">Si inizierà eseguendo il carico di lavoro nelle tabelle ottimizzate per la memoria.</span><span class="sxs-lookup"><span data-stu-id="ef1d4-384">We will start by running the workload on memory-optimized tables.</span></span> <span data-ttu-id="ef1d4-385">Tramite il comando seguente vengono aperti 100 thread, ognuno in esecuzione per 5.000 iterazioni.</span><span class="sxs-lookup"><span data-stu-id="ef1d4-385">The following command opens 100 threads, each running for 5,000 iterations.</span></span>  <span data-ttu-id="ef1d4-386">Tramite ogni iterazione vengono inseriti 20 ordini vendita in transazioni separate.</span><span class="sxs-lookup"><span data-stu-id="ef1d4-386">Each iteration inserts 20 sales orders in separate transactions.</span></span> <span data-ttu-id="ef1d4-387">Vi sono 20 inserimenti per ogni iterazione per compensare il fatto che il database viene utilizzato per generare i dati da inserire.</span><span class="sxs-lookup"><span data-stu-id="ef1d4-387">There are 20 inserts per iteration to compensate for the fact that the database is used to generate the data to be inserted.</span></span> <span data-ttu-id="ef1d4-388">Ciò produce un totale pari a 20 \* 5.000 \* 100 = 10.000.000 di inserimenti di ordini vendita.</span><span class="sxs-lookup"><span data-stu-id="ef1d4-388">This yield a total of 20 \* 5,000 \* 100 = 10,000,000 sales order inserts.</span></span>  
  
 <span data-ttu-id="ef1d4-389">Aprire il prompt dei comandi RML ed eseguire il comando riportato di seguito:</span><span class="sxs-lookup"><span data-stu-id="ef1d4-389">Open the RML Cmd Prompt, and execute the following command:</span></span>  
  
 <span data-ttu-id="ef1d4-390">Fare clic sul pulsante Copia per copiare il comando e incollarlo nel prompt dei comandi delle utilità RML.</span><span class="sxs-lookup"><span data-stu-id="ef1d4-390">Click the Copy button to copy the command, and paste it into the RML Utilities command prompt.</span></span>  
  
```  
ostress.exe -n100 -r5000 -S. -E -dAdventureWorks2014 -q -Q"DECLARE @i int = 0, @od Sales.SalesOrderDetailType_inmem, @SalesOrderID int, @DueDate datetime2 = sysdatetime(), @CustomerID int = rand() * 8000, @BillToAddressID int = rand() * 10000, @ShipToAddressID int = rand() * 10000, @ShipMethodID int = (rand() * 5) + 1; INSERT INTO @od SELECT OrderQty, ProductID, SpecialOfferID FROM Demo.DemoSalesOrderDetailSeed WHERE OrderID= cast((rand()*106) + 1 as int); while (@i < 20) begin; EXEC Sales.usp_InsertSalesOrder_inmem @SalesOrderID OUTPUT, @DueDate, @CustomerID, @BillToAddressID, @ShipToAddressID, @ShipMethodID, @od; set @i += 1 end"  
```  
  
 <span data-ttu-id="ef1d4-391">In un server di test con un numero totale di 8 core fisici (16 logici), l'operazione ha richiesto 2 minuti e 5 secondi.</span><span class="sxs-lookup"><span data-stu-id="ef1d4-391">On one test server with a total number of 8 physical (16 logical) cores, this took 2 minutes and 5 seconds.</span></span> <span data-ttu-id="ef1d4-392">In un secondo server di prova con 24 core fisici (48 logici), l'operazione ha richiesto 1 minuto e 0 secondi.</span><span class="sxs-lookup"><span data-stu-id="ef1d4-392">On a second test server with 24 physical (48 logical) cores, this took 1 minute and 0 seconds.</span></span>  
  
 <span data-ttu-id="ef1d4-393">Osservare l'utilizzo della CPU mentre il carico di lavoro è in esecuzione, ad esempio tramite Gestione attività.</span><span class="sxs-lookup"><span data-stu-id="ef1d4-393">Observe the CPU utilization while the workload is running, for example using task manager.</span></span> <span data-ttu-id="ef1d4-394">Si noterà che l'utilizzo della CPU è vicino al 100%.</span><span class="sxs-lookup"><span data-stu-id="ef1d4-394">You will see that CPU utilization is close to 100%.</span></span> <span data-ttu-id="ef1d4-395">In caso contrario, si avrà un collo di bottiglia a livello di operazioni di I/O del log. Vedere anche [Risoluzione dei problemi relativi ai test con esecuzione prolungata](#Troubleshootingslow-runningtests).</span><span class="sxs-lookup"><span data-stu-id="ef1d4-395">If this is not the case, you have a log IO bottleneck see also [Troubleshooting slow-running tests](#Troubleshootingslow-runningtests).</span></span>  
  
##### <a name="disk-based-tables"></a><span data-ttu-id="ef1d4-396">Tabelle basate su disco</span><span class="sxs-lookup"><span data-stu-id="ef1d4-396">Disk-based tables</span></span>  
 <span data-ttu-id="ef1d4-397">Tramite il comando riportato di seguito verrà eseguito il carico di lavoro nelle tabelle basate su disco.</span><span class="sxs-lookup"><span data-stu-id="ef1d4-397">The following command will run the workload on disk-based tables.</span></span> <span data-ttu-id="ef1d4-398">Si noti che l'esecuzione di questo carico di lavoro può richiedere del tempo, in gran parte a causa di una contesa di latch nel sistema.</span><span class="sxs-lookup"><span data-stu-id="ef1d4-398">Note that this workload may take a while to execute, which is largely due to latch contention in the system.</span></span> <span data-ttu-id="ef1d4-399">Le tabelle con ottimizzazione per la memoria sono prive di latch e pertanto prive di questo problema.</span><span class="sxs-lookup"><span data-stu-id="ef1d4-399">Memory-optimized table are latch-free and thus do not suffer from this problem.</span></span>  
  
 <span data-ttu-id="ef1d4-400">Aprire il prompt dei comandi RML ed eseguire il comando riportato di seguito:</span><span class="sxs-lookup"><span data-stu-id="ef1d4-400">Open the RML Cmd Prompt, and execute the following command:</span></span>  
  
 <span data-ttu-id="ef1d4-401">Fare clic sul pulsante Copia per copiare il comando e incollarlo nel prompt dei comandi delle utilità RML.</span><span class="sxs-lookup"><span data-stu-id="ef1d4-401">Click the Copy button to copy the command, and paste it into the RML Utilities command prompt.</span></span>  
  
```  
ostress.exe -n100 -r5000 -S. -E -dAdventureWorks2014 -q -Q"DECLARE @i int = 0, @od Sales.SalesOrderDetailType_ondisk, @SalesOrderID int, @DueDate datetime2 = sysdatetime(), @CustomerID int = rand() * 8000, @BillToAddressID int = rand() * 10000, @ShipToAddressID int = rand() * 10000, @ShipMethodID int = (rand() * 5) + 1; INSERT INTO @od SELECT OrderQty, ProductID, SpecialOfferID FROM Demo.DemoSalesOrderDetailSeed WHERE OrderID= cast((rand()*106) + 1 as int); while (@i < 20) begin; EXEC Sales.usp_InsertSalesOrder_ondisk @SalesOrderID OUTPUT, @DueDate, @CustomerID, @BillToAddressID, @ShipToAddressID, @ShipMethodID, @od; set @i += 1 end"  
```  
  
 <span data-ttu-id="ef1d4-402">In un server di prova con un numero totale di 8 core fisici (16 logici), l'operazione ha richiesto 41 minuti e 25 secondi.</span><span class="sxs-lookup"><span data-stu-id="ef1d4-402">On one test server with a total number of 8 physical (16 logical) cores, this took 41 minutes and 25 seconds.</span></span> <span data-ttu-id="ef1d4-403">In un secondo server di prova con 24 core fisici (48 logici), l'operazione ha richiesto 52 minuti e 16 secondi.</span><span class="sxs-lookup"><span data-stu-id="ef1d4-403">On a second test server with 24 physical (48 logical) cores, this took 52 minutes and 16 seconds.</span></span>  
  
 <span data-ttu-id="ef1d4-404">Il fattore principale della differenza a livello di prestazioni tra le tabelle ottimizzate per la memoria e quelle basate su disco in questo test è che quando si utilizzano le tabelle basate su disco, tramite [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] non è possibile usare completamente la CPU.</span><span class="sxs-lookup"><span data-stu-id="ef1d4-404">The main factor in the performance difference between memory-optimized tables and disk-based tables in this test is the fact that when using disk-based tables, [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] cannot not fully utilize the CPU.</span></span> <span data-ttu-id="ef1d4-405">Il motivo è la contesa di latch: tramite le transazioni simultanee si tenta di scrivere nella stessa pagina di dati; i latch vengono utilizzati per garantire che in una pagina venga scritta una sola transazione per volta.</span><span class="sxs-lookup"><span data-stu-id="ef1d4-405">The reason is latch contention: concurrent transactions are attempting to write to the same data page; latches are used to ensure only one transaction at a time can write to a page.</span></span> <span data-ttu-id="ef1d4-406">Il motore [!INCLUDE[hek_2](../includes/hek-2-md.md)] è privo di latch e le righe di dati non sono organizzate in pagine.</span><span class="sxs-lookup"><span data-stu-id="ef1d4-406">The [!INCLUDE[hek_2](../includes/hek-2-md.md)] engine is latch-free, and data rows are not organized in pages.</span></span> <span data-ttu-id="ef1d4-407">Pertanto, le transazioni simultanee non bloccano gli inserimenti degli altri, consentendo in tal modo [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] di utilizzare completamente la CPU.</span><span class="sxs-lookup"><span data-stu-id="ef1d4-407">Thus, concurrent transactions do not block each other's inserts, thus enabling [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] to fully utilize the CPU.</span></span>  
  
 <span data-ttu-id="ef1d4-408">È possibile osservare l'utilizzo della CPU mentre il carico di lavoro è in esecuzione, ad esempio tramite Gestione attività.</span><span class="sxs-lookup"><span data-stu-id="ef1d4-408">You can observe the CPU utilization while the workload is running, for example using task manager.</span></span> <span data-ttu-id="ef1d4-409">Si noterà che con le tabelle basate su disco l'utilizzo della CPU è lontano dal 100%.</span><span class="sxs-lookup"><span data-stu-id="ef1d4-409">You will see with disk-based tables the CPU utilization is far from 100%.</span></span> <span data-ttu-id="ef1d4-410">In una configurazione di prova con 16 processori logici, l'utilizzo si aggira intorno al 24%.</span><span class="sxs-lookup"><span data-stu-id="ef1d4-410">On a test configuration with 16 logical processors, the utilization would hover around 24%.</span></span>  
  
 <span data-ttu-id="ef1d4-411">Facoltativamente, è possibile visualizzare il numero di attese latch al secondo tramite Performance Monitor, con il contatore delle prestazioni '\SQL Server:Latches\Latch Waits/sec'.</span><span class="sxs-lookup"><span data-stu-id="ef1d4-411">Optionally, you can view the number of latch waits per second using Performance Monitor, with the performance counter '\SQL Server:Latches\Latch Waits/sec'.</span></span>  
  
#### <a name="resetting-the-demo"></a><span data-ttu-id="ef1d4-412">Reimpostazione della dimostrazione</span><span class="sxs-lookup"><span data-stu-id="ef1d4-412">Resetting the demo</span></span>  
 <span data-ttu-id="ef1d4-413">Per reimpostare la dimostrazione, aprire il prompt dei comandi RML ed eseguire il comando riportato di seguito:</span><span class="sxs-lookup"><span data-stu-id="ef1d4-413">To reset the demo, open the RML Cmd Prompt, and execute the following command:</span></span>  
  
```  
ostress.exe -S. -E -dAdventureWorks2014 -Q"EXEC Demo.usp_DemoReset"  
```  
  
 <span data-ttu-id="ef1d4-414">A seconda dell'hardware, l'esecuzione può richiedere alcuni minuti.</span><span class="sxs-lookup"><span data-stu-id="ef1d4-414">Depending on the hardware this may take a few minutes to run.</span></span>  
  
 <span data-ttu-id="ef1d4-415">Si consiglia una reimpostazione dopo ogni esecuzione della dimostrazione.</span><span class="sxs-lookup"><span data-stu-id="ef1d4-415">We recommend a reset after every demo run.</span></span> <span data-ttu-id="ef1d4-416">Poiché questo carico di lavoro è caratterizzato solo da operazioni di inserimento, per ogni esecuzione verrà utilizzata più memoria e, pertanto, per impedire l'esaurimento di quest'ultima sarà necessario eseguire una reimpostazione.</span><span class="sxs-lookup"><span data-stu-id="ef1d4-416">Because this workload is insert-only, each run will consume more memory, and thus a reset is required to prevent running out of memory.</span></span> <span data-ttu-id="ef1d4-417">La quantità di memoria utilizzata dopo un'esecuzione è descritta nella sezione [Utilizzo della memoria dopo l'esecuzione del carico di lavoro](#Memoryutilizationafterrunningtheworkload).</span><span class="sxs-lookup"><span data-stu-id="ef1d4-417">The amount of memory consumed after a run is discussed in Section [Memory utilization after running the workload](#Memoryutilizationafterrunningtheworkload).</span></span>  
  
###  <a name="troubleshooting-slow-running-tests"></a><a name="Troubleshootingslow-runningtests"></a> <span data-ttu-id="ef1d4-418">Risoluzione dei problemi relativi ai test con esecuzione prolungata</span><span class="sxs-lookup"><span data-stu-id="ef1d4-418">Troubleshooting slow-running tests</span></span>  
 <span data-ttu-id="ef1d4-419">I risultati dei test variano in genere a seconda dell'hardware e del livello di concorrenza utilizzato durante l'esecuzione del test.</span><span class="sxs-lookup"><span data-stu-id="ef1d4-419">Test results will typically vary with hardware, and also the level of concurrency used in the test run.</span></span> <span data-ttu-id="ef1d4-420">Se i risultati non sono quelli previsti, è opportuno verificare alcune informazioni:</span><span class="sxs-lookup"><span data-stu-id="ef1d4-420">A couple of things to look for if the results are not as expected:</span></span>  
  
-   <span data-ttu-id="ef1d4-421">Numero di transazioni simultanee. Quando si esegue il carico di lavoro in un solo thread, il miglioramento delle prestazioni con [!INCLUDE[hek_2](../includes/hek-2-md.md)] sarà probabilmente inferiore di 2 volte.</span><span class="sxs-lookup"><span data-stu-id="ef1d4-421">Number of concurrent transactions: When running the workload on a single thread, performance gain with [!INCLUDE[hek_2](../includes/hek-2-md.md)] will likely be less than 2X.</span></span> <span data-ttu-id="ef1d4-422">La contesa di latch è un grande problema solo se vi è un livello elevato di concorrenza.</span><span class="sxs-lookup"><span data-stu-id="ef1d4-422">Latch contention is only a big problem if there is a high level of concurrency.</span></span>  
  
-   <span data-ttu-id="ef1d4-423">Numero contenuto di core disponibili in [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)]. Ciò significa che vi sarà un livello basso di concorrenza nel sistema, dal momento che vi possono essere tante esecuzioni simultanee di transazioni quanti sono i core disponibili in SQL.</span><span class="sxs-lookup"><span data-stu-id="ef1d4-423">Low number of cores available to [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)]: This means there will be a low level of concurrency in the system, as there can only be as many concurrently executing transactions as there are cores available to SQL.</span></span>  
  
    -   <span data-ttu-id="ef1d4-424">Sintomo: se l'utilizzo della CPU è elevato durante l'esecuzione del carico di lavoro nelle tabelle basate su disco, ciò significa che non vi sono molte contese, puntando a una mancanza di concorrenza.</span><span class="sxs-lookup"><span data-stu-id="ef1d4-424">Symptom: if the CPU utilization is high when running the workload on disk-based tables, this means there is not a lot of contention, pointing to a lack of concurrency.</span></span>  
  
-   <span data-ttu-id="ef1d4-425">Velocità dell'unità dei log: se l'unità dei log non resta sincronizzata con il livello di velocità effettiva delle transazioni nel sistema, il carico di lavoro diventa un collo di bottiglia nelle operazioni di I/O del log.</span><span class="sxs-lookup"><span data-stu-id="ef1d4-425">Speed of the log drive: If the log drive cannot keep up with the level of transaction throughput in the system, the workload becomes bottlenecked on log IO.</span></span> <span data-ttu-id="ef1d4-426">Sebbene la registrazione sia più efficiente con [!INCLUDE[hek_2](../includes/hek-2-md.md)], se le operazioni di I/O del log rappresentano un collo di bottiglia, il potenziale miglioramento delle prestazioni sarà limitato.</span><span class="sxs-lookup"><span data-stu-id="ef1d4-426">Although logging is more efficient with [!INCLUDE[hek_2](../includes/hek-2-md.md)], if log IO is a bottleneck, the potential performance gain is limited.</span></span>  
  
    -   <span data-ttu-id="ef1d4-427">Sintomo: se l'utilizzo della CPU non è vicino al 100% o presenta molti problemi durante l'esecuzione del carico di lavoro nelle tabelle ottimizzate per la memoria, è possibile la presenza di un collo di bottiglia a livello di I/O del log.</span><span class="sxs-lookup"><span data-stu-id="ef1d4-427">Symptom: if the CPU utilization is not close to 100% or is very spiky when running the workload on memory-optimized tables, it is possible there is a log IO bottleneck.</span></span> <span data-ttu-id="ef1d4-428">Questa situazione può essere verificata aprendo il monitoraggio risorse ed esaminando la lunghezza della coda per l'unità dei log.</span><span class="sxs-lookup"><span data-stu-id="ef1d4-428">This can be confirmed by opening Resource Monitor and looking at the queue length for the log drive.</span></span>  
  
##  <a name="memory-and-disk-space-utilization-in-the-sample"></a><a name="MemoryandDiskSpaceUtilizationintheSample"></a> <span data-ttu-id="ef1d4-429">Utilizzo della memoria e dello spazio su disco nell'esempio</span><span class="sxs-lookup"><span data-stu-id="ef1d4-429">Memory and Disk Space Utilization in the Sample</span></span>  
 <span data-ttu-id="ef1d4-430">Di seguito viene descritto cosa ci si aspetta in termini di utilizzo della memoria e dello spazio su disco per il database di esempio.</span><span class="sxs-lookup"><span data-stu-id="ef1d4-430">In the below we describe what to expect in terms of memory and disk space utilization for the sample database.</span></span> <span data-ttu-id="ef1d4-431">Vengono inoltre illustrati i risultati ottenuti in un server di prova con 16 core logici.</span><span class="sxs-lookup"><span data-stu-id="ef1d4-431">We also show the results we have seen in on a test server with 16 logical cores.</span></span>  
  
###  <a name="memory-utilization-for-the-memory-optimized-tables"></a><a name="Memoryutilizationforthememory-optimizedtables"></a> <span data-ttu-id="ef1d4-432">Utilizzo della memoria per le tabelle ottimizzate per la memoria</span><span class="sxs-lookup"><span data-stu-id="ef1d4-432">Memory utilization for the memory-optimized tables</span></span>  
  
#### <a name="overall-utilization-of-the-database"></a><span data-ttu-id="ef1d4-433">Utilizzo complessivo del database</span><span class="sxs-lookup"><span data-stu-id="ef1d4-433">Overall utilization of the database</span></span>  
 <span data-ttu-id="ef1d4-434">La query seguente può essere utilizzata per ottenere l'utilizzo totale della memoria per [!INCLUDE[hek_2](../includes/hek-2-md.md)] nel sistema.</span><span class="sxs-lookup"><span data-stu-id="ef1d4-434">The following query can be used to obtain the total memory utilization for [!INCLUDE[hek_2](../includes/hek-2-md.md)] in the system.</span></span>  
  
```  
SELECT type  
   , name  
, pages_kb/1024 AS pages_MB   
FROM sys.dm_os_memory_clerks WHERE type LIKE '%xtp%'  
```  
  
 <span data-ttu-id="ef1d4-435">Snapshot dopo aver appena creato il database:</span><span class="sxs-lookup"><span data-stu-id="ef1d4-435">Snapshot after the database has just been created:</span></span>  
  
||||  
|-|-|-|  
|<span data-ttu-id="ef1d4-436">**type**</span><span class="sxs-lookup"><span data-stu-id="ef1d4-436">**type**</span></span>|<span data-ttu-id="ef1d4-437">**nome**</span><span class="sxs-lookup"><span data-stu-id="ef1d4-437">**name**</span></span>|<span data-ttu-id="ef1d4-438">**pages_MB**</span><span class="sxs-lookup"><span data-stu-id="ef1d4-438">**pages_MB**</span></span>|  
|<span data-ttu-id="ef1d4-439">MEMORYCLERK_XTP</span><span class="sxs-lookup"><span data-stu-id="ef1d4-439">MEMORYCLERK_XTP</span></span>|<span data-ttu-id="ef1d4-440">Predefinito</span><span class="sxs-lookup"><span data-stu-id="ef1d4-440">Default</span></span>|<span data-ttu-id="ef1d4-441">94</span><span class="sxs-lookup"><span data-stu-id="ef1d4-441">94</span></span>|  
|<span data-ttu-id="ef1d4-442">MEMORYCLERK_XTP</span><span class="sxs-lookup"><span data-stu-id="ef1d4-442">MEMORYCLERK_XTP</span></span>|<span data-ttu-id="ef1d4-443">DB_ID_5</span><span class="sxs-lookup"><span data-stu-id="ef1d4-443">DB_ID_5</span></span>|<span data-ttu-id="ef1d4-444">877</span><span class="sxs-lookup"><span data-stu-id="ef1d4-444">877</span></span>|  
|<span data-ttu-id="ef1d4-445">MEMORYCLERK_XTP</span><span class="sxs-lookup"><span data-stu-id="ef1d4-445">MEMORYCLERK_XTP</span></span>|<span data-ttu-id="ef1d4-446">Predefinito</span><span class="sxs-lookup"><span data-stu-id="ef1d4-446">Default</span></span>|<span data-ttu-id="ef1d4-447">0</span><span class="sxs-lookup"><span data-stu-id="ef1d4-447">0</span></span>|  
|<span data-ttu-id="ef1d4-448">MEMORYCLERK_XTP</span><span class="sxs-lookup"><span data-stu-id="ef1d4-448">MEMORYCLERK_XTP</span></span>|<span data-ttu-id="ef1d4-449">Predefinito</span><span class="sxs-lookup"><span data-stu-id="ef1d4-449">Default</span></span>|<span data-ttu-id="ef1d4-450">0</span><span class="sxs-lookup"><span data-stu-id="ef1d4-450">0</span></span>|  
  
 <span data-ttu-id="ef1d4-451">I clerk di memoria predefiniti contengono strutture di memoria di sistema e sono relativamente ridotti.</span><span class="sxs-lookup"><span data-stu-id="ef1d4-451">The default memory clerks contain system-wide memory structures and are relatively small.</span></span> <span data-ttu-id="ef1d4-452">Il clerk di memoria per il database utente, in questo caso il database con ID 5, è pari a circa 900 MB.</span><span class="sxs-lookup"><span data-stu-id="ef1d4-452">The memory clerk for the user database, in this case database with ID 5, is about 900MB.</span></span>  
  
#### <a name="memory-utilization-per-table"></a><span data-ttu-id="ef1d4-453">Utilizzo della memoria per ogni tabella</span><span class="sxs-lookup"><span data-stu-id="ef1d4-453">Memory utilization per table</span></span>  
 <span data-ttu-id="ef1d4-454">La query seguente può essere utilizzata per eseguire il drill-down nell'utilizzo della memoria delle singole tabelle e dei relativi indici:</span><span class="sxs-lookup"><span data-stu-id="ef1d4-454">The following query can be used to drill down into the memory utilization of the individual tables and their indexes:</span></span>  
  
```  
SELECT object_name(t.object_id) AS [Table Name]  
     , memory_allocated_for_table_kb  
 , memory_allocated_for_indexes_kb  
FROM sys.dm_db_xtp_table_memory_stats dms JOIN sys.tables t   
ON dms.object_id=t.object_id  
WHERE t.type='U'  
```  
  
 <span data-ttu-id="ef1d4-455">Di seguito vengono mostrati i risultati di questa query per un'installazione aggiornata dell'esempio:</span><span class="sxs-lookup"><span data-stu-id="ef1d4-455">The following shows the results of this query for a fresh installation of the sample:</span></span>  
  
||||  
|-|-|-|  
|<span data-ttu-id="ef1d4-456">**Nome tabella**</span><span class="sxs-lookup"><span data-stu-id="ef1d4-456">**Table Name**</span></span>|<span data-ttu-id="ef1d4-457">**memory_allocated_for_table_kb**</span><span class="sxs-lookup"><span data-stu-id="ef1d4-457">**memory_allocated_for_table_kb**</span></span>|<span data-ttu-id="ef1d4-458">**memory_allocated_for_indexes_kb**</span><span class="sxs-lookup"><span data-stu-id="ef1d4-458">**memory_allocated_for_indexes_kb**</span></span>|  
|<span data-ttu-id="ef1d4-459">SpecialOfferProduct_inmem</span><span class="sxs-lookup"><span data-stu-id="ef1d4-459">SpecialOfferProduct_inmem</span></span>|<span data-ttu-id="ef1d4-460">64</span><span class="sxs-lookup"><span data-stu-id="ef1d4-460">64</span></span>|<span data-ttu-id="ef1d4-461">3840</span><span class="sxs-lookup"><span data-stu-id="ef1d4-461">3840</span></span>|  
|<span data-ttu-id="ef1d4-462">DemoSalesOrderHeaderSeed</span><span class="sxs-lookup"><span data-stu-id="ef1d4-462">DemoSalesOrderHeaderSeed</span></span>|<span data-ttu-id="ef1d4-463">1984</span><span class="sxs-lookup"><span data-stu-id="ef1d4-463">1984</span></span>|<span data-ttu-id="ef1d4-464">5504</span><span class="sxs-lookup"><span data-stu-id="ef1d4-464">5504</span></span>|  
|<span data-ttu-id="ef1d4-465">SalesOrderDetail_inmem</span><span class="sxs-lookup"><span data-stu-id="ef1d4-465">SalesOrderDetail_inmem</span></span>|<span data-ttu-id="ef1d4-466">15316</span><span class="sxs-lookup"><span data-stu-id="ef1d4-466">15316</span></span>|<span data-ttu-id="ef1d4-467">663552</span><span class="sxs-lookup"><span data-stu-id="ef1d4-467">663552</span></span>|  
|<span data-ttu-id="ef1d4-468">DemoSalesOrderDetailSeed</span><span class="sxs-lookup"><span data-stu-id="ef1d4-468">DemoSalesOrderDetailSeed</span></span>|<span data-ttu-id="ef1d4-469">64</span><span class="sxs-lookup"><span data-stu-id="ef1d4-469">64</span></span>|<span data-ttu-id="ef1d4-470">10432</span><span class="sxs-lookup"><span data-stu-id="ef1d4-470">10432</span></span>|  
|<span data-ttu-id="ef1d4-471">SpecialOffer_inmem</span><span class="sxs-lookup"><span data-stu-id="ef1d4-471">SpecialOffer_inmem</span></span>|<span data-ttu-id="ef1d4-472">3</span><span class="sxs-lookup"><span data-stu-id="ef1d4-472">3</span></span>|<span data-ttu-id="ef1d4-473">8192</span><span class="sxs-lookup"><span data-stu-id="ef1d4-473">8192</span></span>|  
|<span data-ttu-id="ef1d4-474">SalesOrderHeader_inmem</span><span class="sxs-lookup"><span data-stu-id="ef1d4-474">SalesOrderHeader_inmem</span></span>|<span data-ttu-id="ef1d4-475">7168</span><span class="sxs-lookup"><span data-stu-id="ef1d4-475">7168</span></span>|<span data-ttu-id="ef1d4-476">147456</span><span class="sxs-lookup"><span data-stu-id="ef1d4-476">147456</span></span>|  
|<span data-ttu-id="ef1d4-477">Product_inmem</span><span class="sxs-lookup"><span data-stu-id="ef1d4-477">Product_inmem</span></span>|<span data-ttu-id="ef1d4-478">124</span><span class="sxs-lookup"><span data-stu-id="ef1d4-478">124</span></span>|<span data-ttu-id="ef1d4-479">12352</span><span class="sxs-lookup"><span data-stu-id="ef1d4-479">12352</span></span>|  
  
 <span data-ttu-id="ef1d4-480">Come si può notare, le dimensioni delle tabelle sono piuttosto piccole: SalesOrderHeader_inmem è di circa 7 MB e SalesOrderDetail_inmem di circa 15 MB.</span><span class="sxs-lookup"><span data-stu-id="ef1d4-480">As you can see the tables are fairly small: SalesOrderHeader_inmem is about 7MB, and SalesOrderDetail_inmem is about 15MB in size.</span></span>  
  
 <span data-ttu-id="ef1d4-481">Ciò che colpisce qui sono le dimensioni della memoria allocata per gli indici, rispetto alle dimensioni dei dati della tabella.</span><span class="sxs-lookup"><span data-stu-id="ef1d4-481">What is striking here is the size of the memory allocated for indexes, compared to the size of the table data.</span></span> <span data-ttu-id="ef1d4-482">Questa condizione è dovuta al fatto che gli indici hash nell'esempio vengono ridimensionati preventivamente per una dimensione più ampia dei dati.</span><span class="sxs-lookup"><span data-stu-id="ef1d4-482">That is because the hash indexes in the sample are pre-sized for a larger data size.</span></span> <span data-ttu-id="ef1d4-483">Si noti che gli indici hash hanno dimensioni fisse e pertanto non aumenteranno con le dimensioni dei dati nella tabella.</span><span class="sxs-lookup"><span data-stu-id="ef1d4-483">Note that hash indexes have a fixed size, and thus their size will not grow with the size of data in the table.</span></span>  
  
####  <a name="memory-utilization-after-running-the-workload"></a><a name="Memoryutilizationafterrunningtheworkload"></a> <span data-ttu-id="ef1d4-484">Utilizzo della memoria dopo l'esecuzione del carico di lavoro</span><span class="sxs-lookup"><span data-stu-id="ef1d4-484">Memory utilization after running the workload</span></span>  
 <span data-ttu-id="ef1d4-485">Dopo l'inserimento di 10 milioni di ordini vendita, l'aspetto dell'utilizzo di tutta la memoria è simile a quanto riportato di seguito:</span><span class="sxs-lookup"><span data-stu-id="ef1d4-485">After insert 10 million sales orders, the all-up memory utilization looks similar to the following:</span></span>  
  
```  
SELECT type  
, name  
, pages_kb/1024 AS pages_MB   
FROM sys.dm_os_memory_clerks WHERE type LIKE '%xtp%'  
```  
  
||||  
|-|-|-|  
|<span data-ttu-id="ef1d4-486">**type**</span><span class="sxs-lookup"><span data-stu-id="ef1d4-486">**type**</span></span>|<span data-ttu-id="ef1d4-487">**nome**</span><span class="sxs-lookup"><span data-stu-id="ef1d4-487">**name**</span></span>|<span data-ttu-id="ef1d4-488">**pages_MB**</span><span class="sxs-lookup"><span data-stu-id="ef1d4-488">**pages_MB**</span></span>|  
|<span data-ttu-id="ef1d4-489">MEMORYCLERK_XTP</span><span class="sxs-lookup"><span data-stu-id="ef1d4-489">MEMORYCLERK_XTP</span></span>|<span data-ttu-id="ef1d4-490">Predefinito</span><span class="sxs-lookup"><span data-stu-id="ef1d4-490">Default</span></span>|<span data-ttu-id="ef1d4-491">146</span><span class="sxs-lookup"><span data-stu-id="ef1d4-491">146</span></span>|  
|<span data-ttu-id="ef1d4-492">MEMORYCLERK_XTP</span><span class="sxs-lookup"><span data-stu-id="ef1d4-492">MEMORYCLERK_XTP</span></span>|<span data-ttu-id="ef1d4-493">DB_ID_5</span><span class="sxs-lookup"><span data-stu-id="ef1d4-493">DB_ID_5</span></span>|<span data-ttu-id="ef1d4-494">7374</span><span class="sxs-lookup"><span data-stu-id="ef1d4-494">7374</span></span>|  
|<span data-ttu-id="ef1d4-495">MEMORYCLERK_XTP</span><span class="sxs-lookup"><span data-stu-id="ef1d4-495">MEMORYCLERK_XTP</span></span>|<span data-ttu-id="ef1d4-496">Predefinito</span><span class="sxs-lookup"><span data-stu-id="ef1d4-496">Default</span></span>|<span data-ttu-id="ef1d4-497">0</span><span class="sxs-lookup"><span data-stu-id="ef1d4-497">0</span></span>|  
|<span data-ttu-id="ef1d4-498">MEMORYCLERK_XTP</span><span class="sxs-lookup"><span data-stu-id="ef1d4-498">MEMORYCLERK_XTP</span></span>|<span data-ttu-id="ef1d4-499">Predefinito</span><span class="sxs-lookup"><span data-stu-id="ef1d4-499">Default</span></span>|<span data-ttu-id="ef1d4-500">0</span><span class="sxs-lookup"><span data-stu-id="ef1d4-500">0</span></span>|  
  
 <span data-ttu-id="ef1d4-501">Come si può notare, tramite [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] viene utilizzato un bit in 8 GB per gli indici e le tabelle ottimizzate per la memoria nel database di esempio.</span><span class="sxs-lookup"><span data-stu-id="ef1d4-501">As you can see, [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] is using a bit under 8GB for the memory-optimized tables and indexes in the sample database.</span></span>  
  
 <span data-ttu-id="ef1d4-502">Esaminare l'utilizzo dettagliato della memoria per tabella dopo un'esecuzione di esempio:</span><span class="sxs-lookup"><span data-stu-id="ef1d4-502">Looking at the detailed memory usage per table after one example run:</span></span>  
  
```  
SELECT object_name(t.object_id) AS [Table Name]  
     , memory_allocated_for_table_kb  
 , memory_allocated_for_indexes_kb  
FROM sys.dm_db_xtp_table_memory_stats dms JOIN sys.tables t   
ON dms.object_id=t.object_id  
WHERE t.type='U'  
```  
  
||||  
|-|-|-|  
|<span data-ttu-id="ef1d4-503">**Nome tabella**</span><span class="sxs-lookup"><span data-stu-id="ef1d4-503">**Table Name**</span></span>|<span data-ttu-id="ef1d4-504">**memory_allocated_for_table_kb**</span><span class="sxs-lookup"><span data-stu-id="ef1d4-504">**memory_allocated_for_table_kb**</span></span>|<span data-ttu-id="ef1d4-505">**memory_allocated_for_indexes_kb**</span><span class="sxs-lookup"><span data-stu-id="ef1d4-505">**memory_allocated_for_indexes_kb**</span></span>|  
|<span data-ttu-id="ef1d4-506">SalesOrderDetail_inmem</span><span class="sxs-lookup"><span data-stu-id="ef1d4-506">SalesOrderDetail_inmem</span></span>|<span data-ttu-id="ef1d4-507">5113761</span><span class="sxs-lookup"><span data-stu-id="ef1d4-507">5113761</span></span>|<span data-ttu-id="ef1d4-508">663552</span><span class="sxs-lookup"><span data-stu-id="ef1d4-508">663552</span></span>|  
|<span data-ttu-id="ef1d4-509">DemoSalesOrderDetailSeed</span><span class="sxs-lookup"><span data-stu-id="ef1d4-509">DemoSalesOrderDetailSeed</span></span>|<span data-ttu-id="ef1d4-510">64</span><span class="sxs-lookup"><span data-stu-id="ef1d4-510">64</span></span>|<span data-ttu-id="ef1d4-511">10368</span><span class="sxs-lookup"><span data-stu-id="ef1d4-511">10368</span></span>|  
|<span data-ttu-id="ef1d4-512">SpecialOffer_inmem</span><span class="sxs-lookup"><span data-stu-id="ef1d4-512">SpecialOffer_inmem</span></span>|<span data-ttu-id="ef1d4-513">2</span><span class="sxs-lookup"><span data-stu-id="ef1d4-513">2</span></span>|<span data-ttu-id="ef1d4-514">8192</span><span class="sxs-lookup"><span data-stu-id="ef1d4-514">8192</span></span>|  
|<span data-ttu-id="ef1d4-515">SalesOrderHeader_inmem</span><span class="sxs-lookup"><span data-stu-id="ef1d4-515">SalesOrderHeader_inmem</span></span>|<span data-ttu-id="ef1d4-516">1575679</span><span class="sxs-lookup"><span data-stu-id="ef1d4-516">1575679</span></span>|<span data-ttu-id="ef1d4-517">147456</span><span class="sxs-lookup"><span data-stu-id="ef1d4-517">147456</span></span>|  
|<span data-ttu-id="ef1d4-518">Product_inmem</span><span class="sxs-lookup"><span data-stu-id="ef1d4-518">Product_inmem</span></span>|<span data-ttu-id="ef1d4-519">111</span><span class="sxs-lookup"><span data-stu-id="ef1d4-519">111</span></span>|<span data-ttu-id="ef1d4-520">12032</span><span class="sxs-lookup"><span data-stu-id="ef1d4-520">12032</span></span>|  
|<span data-ttu-id="ef1d4-521">SpecialOfferProduct_inmem</span><span class="sxs-lookup"><span data-stu-id="ef1d4-521">SpecialOfferProduct_inmem</span></span>|<span data-ttu-id="ef1d4-522">64</span><span class="sxs-lookup"><span data-stu-id="ef1d4-522">64</span></span>|<span data-ttu-id="ef1d4-523">3712</span><span class="sxs-lookup"><span data-stu-id="ef1d4-523">3712</span></span>|  
|<span data-ttu-id="ef1d4-524">DemoSalesOrderHeaderSeed</span><span class="sxs-lookup"><span data-stu-id="ef1d4-524">DemoSalesOrderHeaderSeed</span></span>|<span data-ttu-id="ef1d4-525">1984</span><span class="sxs-lookup"><span data-stu-id="ef1d4-525">1984</span></span>|<span data-ttu-id="ef1d4-526">5504</span><span class="sxs-lookup"><span data-stu-id="ef1d4-526">5504</span></span>|  
  
 <span data-ttu-id="ef1d4-527">Si può notare un totale pari a circa 6,5 GB di dati.</span><span class="sxs-lookup"><span data-stu-id="ef1d4-527">We can see a total of about 6.5GB of data.</span></span> <span data-ttu-id="ef1d4-528">Si noti che le dimensioni degli indici delle tabelle SalesOrderHeader_inmem e SalesOrderDetail_inmem equivalgono alle dimensioni degli indici prima dell'inserimento degli ordini vendita.</span><span class="sxs-lookup"><span data-stu-id="ef1d4-528">Notice that the size of the indexes on the table SalesOrderHeader_inmem and SalesOrderDetail_inmem is the same as the size of the indexes before inserting the sales orders.</span></span> <span data-ttu-id="ef1d4-529">Le dimensioni dell'indice non sono state modificate perché in entrambe le tabelle vengono utilizzati indici hash e questo tipo di indice è statico.</span><span class="sxs-lookup"><span data-stu-id="ef1d4-529">The index size did not change because both tables are using hash indexes, and hash indexes are static.</span></span>  
  
#### <a name="after-demo-reset"></a><span data-ttu-id="ef1d4-530">Dopo la reimpostazione della dimostrazione</span><span class="sxs-lookup"><span data-stu-id="ef1d4-530">After demo reset</span></span>  
 <span data-ttu-id="ef1d4-531">La stored procedure Demo.usp_DemoReset può essere utilizzata per reimpostare la dimostrazione.</span><span class="sxs-lookup"><span data-stu-id="ef1d4-531">The stored procedure Demo.usp_DemoReset can be used to reset the demo.</span></span> <span data-ttu-id="ef1d4-532">Tramite essa vengono eliminati i dati nelle tabelle SalesOrderHeader_inmem e SalesOrderDetail_inmem e vengono reinizializzati i dati dalle tabelle originali SalesOrderHeader e SalesOrderDetail.</span><span class="sxs-lookup"><span data-stu-id="ef1d4-532">It deletes the data in the tables SalesOrderHeader_inmem and SalesOrderDetail_inmem, and re-seeds the data from the original tables SalesOrderHeader and SalesOrderDetail.</span></span>  
  
 <span data-ttu-id="ef1d4-533">A questo punto, anche se le righe nelle tabelle sono state eliminate, questo non significa che la memoria venga recuperata immediatamente.</span><span class="sxs-lookup"><span data-stu-id="ef1d4-533">Now, even though the rows in the tables have been deleted, this does not mean that memory is reclaimed immediately.</span></span> <span data-ttu-id="ef1d4-534">La memoria viene recuperata in background da [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] dalle righe eliminate nelle tabelle ottimizzate per la memoria, in base alle esigenze.</span><span class="sxs-lookup"><span data-stu-id="ef1d4-534">[!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] reclaims memory from deleted rows in memory-optimized tables in the background, as needed.</span></span> <span data-ttu-id="ef1d4-535">Si noterà che subito dopo la reimpostazione della dimostrazione, senza il carico di lavoro transazionale nel sistema, la memoria non è ancora stata recuperata dalle righe eliminate:</span><span class="sxs-lookup"><span data-stu-id="ef1d4-535">You will see that immediately after demo reset, with no transactional workload on the system, memory from deleted rows is not yet reclaimed:</span></span>  
  
```  
SELECT type  
, name  
, pages_kb/1024 AS pages_MB   
FROM sys.dm_os_memory_clerks WHERE type LIKE '%xtp%'  
```  
  
||||  
|-|-|-|  
|<span data-ttu-id="ef1d4-536">**type**</span><span class="sxs-lookup"><span data-stu-id="ef1d4-536">**type**</span></span>|<span data-ttu-id="ef1d4-537">**nome**</span><span class="sxs-lookup"><span data-stu-id="ef1d4-537">**name**</span></span>|<span data-ttu-id="ef1d4-538">**pages_MB**</span><span class="sxs-lookup"><span data-stu-id="ef1d4-538">**pages_MB**</span></span>|  
|<span data-ttu-id="ef1d4-539">MEMORYCLERK_XTP</span><span class="sxs-lookup"><span data-stu-id="ef1d4-539">MEMORYCLERK_XTP</span></span>|<span data-ttu-id="ef1d4-540">Predefinito</span><span class="sxs-lookup"><span data-stu-id="ef1d4-540">Default</span></span>|<span data-ttu-id="ef1d4-541">2261</span><span class="sxs-lookup"><span data-stu-id="ef1d4-541">2261</span></span>|  
|<span data-ttu-id="ef1d4-542">MEMORYCLERK_XTP</span><span class="sxs-lookup"><span data-stu-id="ef1d4-542">MEMORYCLERK_XTP</span></span>|<span data-ttu-id="ef1d4-543">DB_ID_5</span><span class="sxs-lookup"><span data-stu-id="ef1d4-543">DB_ID_5</span></span>|<span data-ttu-id="ef1d4-544">7396</span><span class="sxs-lookup"><span data-stu-id="ef1d4-544">7396</span></span>|  
|<span data-ttu-id="ef1d4-545">MEMORYCLERK_XTP</span><span class="sxs-lookup"><span data-stu-id="ef1d4-545">MEMORYCLERK_XTP</span></span>|<span data-ttu-id="ef1d4-546">Predefinito</span><span class="sxs-lookup"><span data-stu-id="ef1d4-546">Default</span></span>|<span data-ttu-id="ef1d4-547">0</span><span class="sxs-lookup"><span data-stu-id="ef1d4-547">0</span></span>|  
|<span data-ttu-id="ef1d4-548">MEMORYCLERK_XTP</span><span class="sxs-lookup"><span data-stu-id="ef1d4-548">MEMORYCLERK_XTP</span></span>|<span data-ttu-id="ef1d4-549">Predefinito</span><span class="sxs-lookup"><span data-stu-id="ef1d4-549">Default</span></span>|<span data-ttu-id="ef1d4-550">0</span><span class="sxs-lookup"><span data-stu-id="ef1d4-550">0</span></span>|  
  
 <span data-ttu-id="ef1d4-551">Si prevede che la memoria verrà recuperata quando il carico di lavoro transazionale è in esecuzione.</span><span class="sxs-lookup"><span data-stu-id="ef1d4-551">This is expected: memory will be reclaimed when the transactional workload is running.</span></span>  
  
 <span data-ttu-id="ef1d4-552">Se si avvia una seconda esecuzione del carico di lavoro dimostrativo, si noterà inizialmente una diminuzione dell'utilizzo della memoria, dal momento che le righe eliminate in precedenza vengono rimosse.</span><span class="sxs-lookup"><span data-stu-id="ef1d4-552">If you start a second run of the demo workload you will see the memory utilization decrease initially, as the previously deleted rows are cleaned up.</span></span> <span data-ttu-id="ef1d4-553">A un certo punto le dimensioni della memoria aumenteranno di nuovo, finché il carico di lavoro non viene completato.</span><span class="sxs-lookup"><span data-stu-id="ef1d4-553">At some point the memory size will increase again, until the workload finishes.</span></span> <span data-ttu-id="ef1d4-554">Dopo l'inserimento di 10 milioni di righe al termine della reimpostazione della dimostrazione, l'utilizzo della memoria sarà molto simile all'utilizzo dopo la prima esecuzione.</span><span class="sxs-lookup"><span data-stu-id="ef1d4-554">After inserting 10 million rows after demo reset, the memory utilization will be very similar to the utilization after the first run.</span></span> <span data-ttu-id="ef1d4-555">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="ef1d4-555">For example:</span></span>  
  
```  
SELECT type  
, name  
, pages_kb/1024 AS pages_MB   
FROM sys.dm_os_memory_clerks WHERE type LIKE '%xtp%'  
```  
  
||||  
|-|-|-|  
|<span data-ttu-id="ef1d4-556">**type**</span><span class="sxs-lookup"><span data-stu-id="ef1d4-556">**type**</span></span>|<span data-ttu-id="ef1d4-557">**nome**</span><span class="sxs-lookup"><span data-stu-id="ef1d4-557">**name**</span></span>|<span data-ttu-id="ef1d4-558">**pages_MB**</span><span class="sxs-lookup"><span data-stu-id="ef1d4-558">**pages_MB**</span></span>|  
|<span data-ttu-id="ef1d4-559">MEMORYCLERK_XTP</span><span class="sxs-lookup"><span data-stu-id="ef1d4-559">MEMORYCLERK_XTP</span></span>|<span data-ttu-id="ef1d4-560">Predefinito</span><span class="sxs-lookup"><span data-stu-id="ef1d4-560">Default</span></span>|<span data-ttu-id="ef1d4-561">1863</span><span class="sxs-lookup"><span data-stu-id="ef1d4-561">1863</span></span>|  
|<span data-ttu-id="ef1d4-562">MEMORYCLERK_XTP</span><span class="sxs-lookup"><span data-stu-id="ef1d4-562">MEMORYCLERK_XTP</span></span>|<span data-ttu-id="ef1d4-563">DB_ID_5</span><span class="sxs-lookup"><span data-stu-id="ef1d4-563">DB_ID_5</span></span>|<span data-ttu-id="ef1d4-564">7390</span><span class="sxs-lookup"><span data-stu-id="ef1d4-564">7390</span></span>|  
|<span data-ttu-id="ef1d4-565">MEMORYCLERK_XTP</span><span class="sxs-lookup"><span data-stu-id="ef1d4-565">MEMORYCLERK_XTP</span></span>|<span data-ttu-id="ef1d4-566">Predefinito</span><span class="sxs-lookup"><span data-stu-id="ef1d4-566">Default</span></span>|<span data-ttu-id="ef1d4-567">0</span><span class="sxs-lookup"><span data-stu-id="ef1d4-567">0</span></span>|  
|<span data-ttu-id="ef1d4-568">MEMORYCLERK_XTP</span><span class="sxs-lookup"><span data-stu-id="ef1d4-568">MEMORYCLERK_XTP</span></span>|<span data-ttu-id="ef1d4-569">Predefinito</span><span class="sxs-lookup"><span data-stu-id="ef1d4-569">Default</span></span>|<span data-ttu-id="ef1d4-570">0</span><span class="sxs-lookup"><span data-stu-id="ef1d4-570">0</span></span>|  
  
### <a name="disk-utilization-for-memory-optimized-tables"></a><span data-ttu-id="ef1d4-571">Utilizzo del disco per tabelle ottimizzate per la memoria</span><span class="sxs-lookup"><span data-stu-id="ef1d4-571">Disk utilization for memory-optimized tables</span></span>  
 <span data-ttu-id="ef1d4-572">Le dimensioni complessive su disco per i file del checkpoint di un database in un determinato momento possono essere recuperate tramite la query seguente:</span><span class="sxs-lookup"><span data-stu-id="ef1d4-572">The overall on-disk size for the checkpoint files of a database at a given time can be found using the query:</span></span>  
  
```  
SELECT SUM(df.size) * 8 / 1024 AS [On-disk size in MB]  
FROM sys.filegroups f JOIN sys.database_files df   
   ON f.data_space_id=df.data_space_id  
WHERE f.type=N'FX'  
  
```  
  
#### <a name="initial-state"></a><span data-ttu-id="ef1d4-573">Stato iniziale</span><span class="sxs-lookup"><span data-stu-id="ef1d4-573">Initial state</span></span>  
 <span data-ttu-id="ef1d4-574">Quando vengono creati inizialmente il filegroup di esempio e le tabelle ottimizzate per la memoria di esempio, vengono creati preventivamente un numero di file del checkpoint e, tramite il sistema viene iniziata la compilazione di questi file. Il numero di file del checkpoint creati in precedenza dipende dal numero di processori logici nel sistema.</span><span class="sxs-lookup"><span data-stu-id="ef1d4-574">When the sample filegroup and sample memory-optimized tables are created initially, a number of checkpoint files are pre-created and the system starts filling the files - the number of checkpoint files pre-created depends on the number of logical processors in the system.</span></span> <span data-ttu-id="ef1d4-575">Poiché l'esempio è inizialmente contenuto, i file creati in precedenza saranno per la maggior parte vuoti al termine della creazione iniziale.</span><span class="sxs-lookup"><span data-stu-id="ef1d4-575">As the sample is initially very small, the pre-created files will be mostly empty after initial create.</span></span>  
  
 <span data-ttu-id="ef1d4-576">Di seguito vengono mostrate le dimensioni iniziali su disco per l'esempio in un computer con 16 processori logici:</span><span class="sxs-lookup"><span data-stu-id="ef1d4-576">The following shows the initial on-disk size for the sample on a machine with 16 logical processors:</span></span>  
  
```  
SELECT SUM(df.size) * 8 / 1024 AS [On-disk size in MB]  
FROM sys.filegroups f JOIN sys.database_files df   
   ON f.data_space_id=df.data_space_id  
WHERE f.type=N'FX'  
```  
  
||  
|-|  
|<span data-ttu-id="ef1d4-577">**On-disk size in MB**</span><span class="sxs-lookup"><span data-stu-id="ef1d4-577">**On-disk size in MB**</span></span>|  
|<span data-ttu-id="ef1d4-578">2312</span><span class="sxs-lookup"><span data-stu-id="ef1d4-578">2312</span></span>|  
  
 <span data-ttu-id="ef1d4-579">Come si può notare, esiste una grande discrepanza tra le dimensioni su disco dei file del checkpoint, vale a dire 2,3 GB, e le dimensioni effettive dei dati, prossime a 30 MB.</span><span class="sxs-lookup"><span data-stu-id="ef1d4-579">As you can see, there is a big discrepancy between the on-disk size of the checkpoint files, which is 2.3GB, and the actual data size, which is closer to 30MB.</span></span>  
  
 <span data-ttu-id="ef1d4-580">Esaminando più da vicino la provenienza dell'utilizzo dello spazio su disco, è possibile usare la query indicata di seguito.</span><span class="sxs-lookup"><span data-stu-id="ef1d4-580">Looking closer at where the disk-space utilization comes from, you can use the following query.</span></span> <span data-ttu-id="ef1d4-581">La dimensione su disco restituita dalla query è approssimativa per i file con lo stato in 5 (REQUIRED FOR BACKUP/HA), 6 (IN TRANSITION TO TOMBSTONE) o 7 (TOMBSTONE).</span><span class="sxs-lookup"><span data-stu-id="ef1d4-581">The size on disk returned by this query is approximate for files with state in 5 (REQUIRED FOR BACKUP/HA), 6 (IN TRANSITION TO TOMBSTONE), or 7 (TOMBSTONE).</span></span>  
  
```  
SELECT state_desc  
 , file_type_desc  
 , COUNT(*) AS [count]  
 , SUM(CASE  
   WHEN state = 5 AND file_type=0 THEN 128*1024*1024  
   WHEN state = 5 AND file_type=1 THEN 8*1024*1024  
   WHEN state IN (6,7) THEN 68*1024*1024  
   ELSE file_size_in_bytes  
    END) / 1024 / 1024 AS [on-disk size MB]   
FROM sys.dm_db_xtp_checkpoint_files  
GROUP BY state, state_desc, file_type, file_type_desc  
ORDER BY state, file_type  
```  
  
 <span data-ttu-id="ef1d4-582">Per lo stato iniziale dell'esempio, il risultato sarà simile per un server con 16 processori logici:</span><span class="sxs-lookup"><span data-stu-id="ef1d4-582">For the initial state of the sample, the result will look something like for a server with 16 logical processors:</span></span>  
  
|||||  
|-|-|-|-|  
|<span data-ttu-id="ef1d4-583">**state_desc**</span><span class="sxs-lookup"><span data-stu-id="ef1d4-583">**state_desc**</span></span>|<span data-ttu-id="ef1d4-584">**file_type_desc**</span><span class="sxs-lookup"><span data-stu-id="ef1d4-584">**file_type_desc**</span></span>|<span data-ttu-id="ef1d4-585">**count**</span><span class="sxs-lookup"><span data-stu-id="ef1d4-585">**count**</span></span>|<span data-ttu-id="ef1d4-586">**on-disk size MB**</span><span class="sxs-lookup"><span data-stu-id="ef1d4-586">**on-disk size MB**</span></span>|  
|<span data-ttu-id="ef1d4-587">PRECREATED</span><span class="sxs-lookup"><span data-stu-id="ef1d4-587">PRECREATED</span></span>|<span data-ttu-id="ef1d4-588">DATA</span><span class="sxs-lookup"><span data-stu-id="ef1d4-588">DATA</span></span>|<span data-ttu-id="ef1d4-589">16</span><span class="sxs-lookup"><span data-stu-id="ef1d4-589">16</span></span>|<span data-ttu-id="ef1d4-590">2048</span><span class="sxs-lookup"><span data-stu-id="ef1d4-590">2048</span></span>|  
|<span data-ttu-id="ef1d4-591">PRECREATED</span><span class="sxs-lookup"><span data-stu-id="ef1d4-591">PRECREATED</span></span>|<span data-ttu-id="ef1d4-592">DELTA</span><span class="sxs-lookup"><span data-stu-id="ef1d4-592">DELTA</span></span>|<span data-ttu-id="ef1d4-593">16</span><span class="sxs-lookup"><span data-stu-id="ef1d4-593">16</span></span>|<span data-ttu-id="ef1d4-594">128</span><span class="sxs-lookup"><span data-stu-id="ef1d4-594">128</span></span>|  
|<span data-ttu-id="ef1d4-595">UNDER CONSTRUCTION</span><span class="sxs-lookup"><span data-stu-id="ef1d4-595">UNDER CONSTRUCTION</span></span>|<span data-ttu-id="ef1d4-596">DATA</span><span class="sxs-lookup"><span data-stu-id="ef1d4-596">DATA</span></span>|<span data-ttu-id="ef1d4-597">1</span><span class="sxs-lookup"><span data-stu-id="ef1d4-597">1</span></span>|<span data-ttu-id="ef1d4-598">128</span><span class="sxs-lookup"><span data-stu-id="ef1d4-598">128</span></span>|  
|<span data-ttu-id="ef1d4-599">UNDER CONSTRUCTION</span><span class="sxs-lookup"><span data-stu-id="ef1d4-599">UNDER CONSTRUCTION</span></span>|<span data-ttu-id="ef1d4-600">DELTA</span><span class="sxs-lookup"><span data-stu-id="ef1d4-600">DELTA</span></span>|<span data-ttu-id="ef1d4-601">1</span><span class="sxs-lookup"><span data-stu-id="ef1d4-601">1</span></span>|<span data-ttu-id="ef1d4-602">8</span><span class="sxs-lookup"><span data-stu-id="ef1d4-602">8</span></span>|  
  
 <span data-ttu-id="ef1d4-603">Come si può notare, la maggior parte dello spazio è utilizzato dai file differenziali e di dati creati in precedenza.</span><span class="sxs-lookup"><span data-stu-id="ef1d4-603">As you can see, most of the space is used by precreated data and delta files.</span></span> <span data-ttu-id="ef1d4-604">Tramite [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] è stata creata preventivamente una coppia di file (differenziali e di dati) per processore logico.</span><span class="sxs-lookup"><span data-stu-id="ef1d4-604">[!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] pre-created one pair of (data, delta) files per logical processor.</span></span> <span data-ttu-id="ef1d4-605">Inoltre, i file di dati vengono ridimensionati preventivamente a 128 MB mentre quelli differenziali a 8 MB, per poter consentire un inserimento di dati in questi file più efficiente.</span><span class="sxs-lookup"><span data-stu-id="ef1d4-605">In addition, data files are pre-sized at 128MB, and delta files at 8MB, in order to make inserting data into these files more efficient.</span></span>  
  
 <span data-ttu-id="ef1d4-606">I dati effettivi nelle tabelle ottimizzate per la memoria si trovano nel singolo file di dati.</span><span class="sxs-lookup"><span data-stu-id="ef1d4-606">The actual data in the memory-optimized tables is in the single data file.</span></span>  
  
#### <a name="after-running-the-workload"></a><span data-ttu-id="ef1d4-607">Dopo l'esecuzione del carico di lavoro</span><span class="sxs-lookup"><span data-stu-id="ef1d4-607">After running the workload</span></span>  
 <span data-ttu-id="ef1d4-608">Dopo una singola esecuzione di test tramite cui vengono inseriti 10 milioni di ordini vendita, le dimensioni complessive su disco saranno simili alle seguenti (per un server di prova con 16 core):</span><span class="sxs-lookup"><span data-stu-id="ef1d4-608">After a single test run that inserts 10 million sales orders, the overall on-disk size looks something like this (for a 16-core test server):</span></span>  
  
```  
SELECT SUM(df.size) * 8 / 1024 AS [On-disk size in MB]  
FROM sys.filegroups f JOIN sys.database_files df   
   ON f.data_space_id=df.data_space_id  
WHERE f.type=N'FX'  
```  
  
||  
|-|  
|<span data-ttu-id="ef1d4-609">**On-disk size in MB**</span><span class="sxs-lookup"><span data-stu-id="ef1d4-609">**On-disk size in MB**</span></span>|  
|<span data-ttu-id="ef1d4-610">8828</span><span class="sxs-lookup"><span data-stu-id="ef1d4-610">8828</span></span>|  
  
 <span data-ttu-id="ef1d4-611">Le dimensioni su disco sono prossime ai 9 GB, che sono simili a quelle delle dimensioni in memoria dei dati.</span><span class="sxs-lookup"><span data-stu-id="ef1d4-611">The on-disk size is close to 9GB, which comes close to the in-memory size of the data.</span></span>  
  
 <span data-ttu-id="ef1d4-612">Esaminando più da vicino le dimensioni dei file del checkpoint nei vari stati:</span><span class="sxs-lookup"><span data-stu-id="ef1d4-612">Looking more closely at the sizes of the checkpoint files across the various states:</span></span>  
  
```  
SELECT state_desc  
 , file_type_desc  
 , COUNT(*) AS [count]  
 , SUM(CASE  
   WHEN state = 5 AND file_type=0 THEN 128*1024*1024  
   WHEN state = 5 AND file_type=1 THEN 8*1024*1024  
   WHEN state IN (6,7) THEN 68*1024*1024  
   ELSE file_size_in_bytes  
    END) / 1024 / 1024 AS [on-disk size MB]   
FROM sys.dm_db_xtp_checkpoint_files  
GROUP BY state, state_desc, file_type, file_type_desc  
ORDER BY state, file_type  
```  
  
|||||  
|-|-|-|-|  
|<span data-ttu-id="ef1d4-613">**state_desc**</span><span class="sxs-lookup"><span data-stu-id="ef1d4-613">**state_desc**</span></span>|<span data-ttu-id="ef1d4-614">**file_type_desc**</span><span class="sxs-lookup"><span data-stu-id="ef1d4-614">**file_type_desc**</span></span>|<span data-ttu-id="ef1d4-615">**count**</span><span class="sxs-lookup"><span data-stu-id="ef1d4-615">**count**</span></span>|<span data-ttu-id="ef1d4-616">**on-disk size MB**</span><span class="sxs-lookup"><span data-stu-id="ef1d4-616">**on-disk size MB**</span></span>|  
|<span data-ttu-id="ef1d4-617">PRECREATED</span><span class="sxs-lookup"><span data-stu-id="ef1d4-617">PRECREATED</span></span>|<span data-ttu-id="ef1d4-618">DATA</span><span class="sxs-lookup"><span data-stu-id="ef1d4-618">DATA</span></span>|<span data-ttu-id="ef1d4-619">16</span><span class="sxs-lookup"><span data-stu-id="ef1d4-619">16</span></span>|<span data-ttu-id="ef1d4-620">2048</span><span class="sxs-lookup"><span data-stu-id="ef1d4-620">2048</span></span>|  
|<span data-ttu-id="ef1d4-621">PRECREATED</span><span class="sxs-lookup"><span data-stu-id="ef1d4-621">PRECREATED</span></span>|<span data-ttu-id="ef1d4-622">DELTA</span><span class="sxs-lookup"><span data-stu-id="ef1d4-622">DELTA</span></span>|<span data-ttu-id="ef1d4-623">16</span><span class="sxs-lookup"><span data-stu-id="ef1d4-623">16</span></span>|<span data-ttu-id="ef1d4-624">128</span><span class="sxs-lookup"><span data-stu-id="ef1d4-624">128</span></span>|  
|<span data-ttu-id="ef1d4-625">UNDER CONSTRUCTION</span><span class="sxs-lookup"><span data-stu-id="ef1d4-625">UNDER CONSTRUCTION</span></span>|<span data-ttu-id="ef1d4-626">DATA</span><span class="sxs-lookup"><span data-stu-id="ef1d4-626">DATA</span></span>|<span data-ttu-id="ef1d4-627">1</span><span class="sxs-lookup"><span data-stu-id="ef1d4-627">1</span></span>|<span data-ttu-id="ef1d4-628">128</span><span class="sxs-lookup"><span data-stu-id="ef1d4-628">128</span></span>|  
|<span data-ttu-id="ef1d4-629">UNDER CONSTRUCTION</span><span class="sxs-lookup"><span data-stu-id="ef1d4-629">UNDER CONSTRUCTION</span></span>|<span data-ttu-id="ef1d4-630">DELTA</span><span class="sxs-lookup"><span data-stu-id="ef1d4-630">DELTA</span></span>|<span data-ttu-id="ef1d4-631">1</span><span class="sxs-lookup"><span data-stu-id="ef1d4-631">1</span></span>|<span data-ttu-id="ef1d4-632">8</span><span class="sxs-lookup"><span data-stu-id="ef1d4-632">8</span></span>|  
  
 <span data-ttu-id="ef1d4-633">Si dispone ancora di 16 coppie di file creati in precedenza, pronti all'utilizzo alla chiusura dei checkpoint.</span><span class="sxs-lookup"><span data-stu-id="ef1d4-633">We still have 16 pairs of pre-created files, ready to go as checkpoints are closed.</span></span>  
  
 <span data-ttu-id="ef1d4-634">È disponibile una coppia in fase di costruzione, che viene utilizzata fino a quando il checkpoint corrente non viene chiuso.</span><span class="sxs-lookup"><span data-stu-id="ef1d4-634">There is one pair under construction, which is used until the current checkpoint is closed.</span></span> <span data-ttu-id="ef1d4-635">Insieme ai file del checkpoint attivi, questa coppia offre circa 6,5 GB di utilizzo su disco per 6,5 GB di dati in memoria.</span><span class="sxs-lookup"><span data-stu-id="ef1d4-635">Along with the active checkpoint files this gives about 6.5GB of disk utilization for 6.5GB of data in memory.</span></span> <span data-ttu-id="ef1d4-636">Si tenta presente che gli indici non vengono salvati in modo persistente su disco e pertanto, in questo caso, le dimensioni complessive su disco sono inferiori rispetto a quelle in memoria.</span><span class="sxs-lookup"><span data-stu-id="ef1d4-636">Recall that indexes are not persisted on disk, and thus the overall size on disk is smaller than the size in memory in this case.</span></span>  
  
#### <a name="after-demo-reset"></a><span data-ttu-id="ef1d4-637">Dopo la reimpostazione della dimostrazione</span><span class="sxs-lookup"><span data-stu-id="ef1d4-637">After demo reset</span></span>  
 <span data-ttu-id="ef1d4-638">Dopo la reimpostazione della dimostrazione, lo spazio su disco non viene recuperato immediatamente se non vi è un carico di lavoro transazionale nel sistema e non vi sono checkpoint del database.</span><span class="sxs-lookup"><span data-stu-id="ef1d4-638">After demo reset, disk space is not reclaimed immediately if there is no transactional workload on the system, and there are not database checkpoints.</span></span> <span data-ttu-id="ef1d4-639">Per i file del checkpoint da spostare nelle varie fasi e infine da rimuovere, devono verificarsi diversi checkpoint ed eventi di troncamento del log, per avviare l'unione dei file del checkpoint, nonché il processo di Garbage Collection.</span><span class="sxs-lookup"><span data-stu-id="ef1d4-639">For checkpoint files to be moved through their various stages and eventually be discarded, a number of checkpoints and log truncation events need to happen, to initiate merge of checkpoint files, as well as to initiate garbage collection.</span></span> <span data-ttu-id="ef1d4-640">Ciò si verifica automaticamente se si dispone di un carico di lavoro transazionale nel sistema, e vengono eseguiti backup regolari del log, qualora venga utilizzato il modello di recupero con registrazione completa, ma non quando il sistema è inattivo, come in uno scenario dimostrativo.</span><span class="sxs-lookup"><span data-stu-id="ef1d4-640">These will happen automatically if you have a transactional workload in the system [and take regular log backups, in case you are using the FULL recovery model], but not when the system is idle, as in a demo scenario.</span></span>  
  
 <span data-ttu-id="ef1d4-641">Nell'esempio, dopo la reimpostazione della dimostrazione, è possibile che si ottenga un risultato simile al seguente</span><span class="sxs-lookup"><span data-stu-id="ef1d4-641">In the example, after demo reset, you may see something like</span></span>  
  
```  
SELECT SUM(df.size) * 8 / 1024 AS [On-disk size in MB]  
FROM sys.filegroups f JOIN sys.database_files df   
   ON f.data_space_id=df.data_space_id  
WHERE f.type=N'FX'  
```  
  
||  
|-|  
|<span data-ttu-id="ef1d4-642">**On-disk size in MB**</span><span class="sxs-lookup"><span data-stu-id="ef1d4-642">**On-disk size in MB**</span></span>|  
|<span data-ttu-id="ef1d4-643">11839</span><span class="sxs-lookup"><span data-stu-id="ef1d4-643">11839</span></span>|  
  
 <span data-ttu-id="ef1d4-644">Quasi 12 GB, che sono significativamente maggiori dei 9 GB disponibili prima della reimpostazione della dimostrazione.</span><span class="sxs-lookup"><span data-stu-id="ef1d4-644">At nearly 12GB, this is significantly more than the 9GB we had before the demo reset.</span></span> <span data-ttu-id="ef1d4-645">Ciò è dovuto al fatto che sono state avviate alcune operazioni di unione di file del checkpoint, ma alcune destinazioni delle unioni non sono ancora state installate e alcuni dei file di origine di unione non sono ancora stati rimossi, come si può notare da quanto riportato di seguito:</span><span class="sxs-lookup"><span data-stu-id="ef1d4-645">This is because some checkpoint file merges have been started, but some of the merge targets have not yet been installed, and some of the merge source files have not yet been cleaned up, as can be seen from the following:</span></span>  
  
```  
SELECT state_desc  
 , file_type_desc  
 , COUNT(*) AS [count]  
 , SUM(CASE  
   WHEN state = 5 AND file_type=0 THEN 128*1024*1024  
   WHEN state = 5 AND file_type=1 THEN 8*1024*1024  
   WHEN state IN (6,7) THEN 68*1024*1024  
   ELSE file_size_in_bytes  
    END) / 1024 / 1024 AS [on-disk size MB]   
FROM sys.dm_db_xtp_checkpoint_files  
GROUP BY state, state_desc, file_type, file_type_desc  
ORDER BY state, file_type  
```  
  
|||||  
|-|-|-|-|  
|<span data-ttu-id="ef1d4-646">**state_desc**</span><span class="sxs-lookup"><span data-stu-id="ef1d4-646">**state_desc**</span></span>|<span data-ttu-id="ef1d4-647">**file_type_desc**</span><span class="sxs-lookup"><span data-stu-id="ef1d4-647">**file_type_desc**</span></span>|<span data-ttu-id="ef1d4-648">**count**</span><span class="sxs-lookup"><span data-stu-id="ef1d4-648">**count**</span></span>|<span data-ttu-id="ef1d4-649">**on-disk size MB**</span><span class="sxs-lookup"><span data-stu-id="ef1d4-649">**on-disk size MB**</span></span>|  
|<span data-ttu-id="ef1d4-650">PRECREATED</span><span class="sxs-lookup"><span data-stu-id="ef1d4-650">PRECREATED</span></span>|<span data-ttu-id="ef1d4-651">DATA</span><span class="sxs-lookup"><span data-stu-id="ef1d4-651">DATA</span></span>|<span data-ttu-id="ef1d4-652">16</span><span class="sxs-lookup"><span data-stu-id="ef1d4-652">16</span></span>|<span data-ttu-id="ef1d4-653">2048</span><span class="sxs-lookup"><span data-stu-id="ef1d4-653">2048</span></span>|  
|<span data-ttu-id="ef1d4-654">PRECREATED</span><span class="sxs-lookup"><span data-stu-id="ef1d4-654">PRECREATED</span></span>|<span data-ttu-id="ef1d4-655">DELTA</span><span class="sxs-lookup"><span data-stu-id="ef1d4-655">DELTA</span></span>|<span data-ttu-id="ef1d4-656">16</span><span class="sxs-lookup"><span data-stu-id="ef1d4-656">16</span></span>|<span data-ttu-id="ef1d4-657">128</span><span class="sxs-lookup"><span data-stu-id="ef1d4-657">128</span></span>|  
|<span data-ttu-id="ef1d4-658">ACTIVE</span><span class="sxs-lookup"><span data-stu-id="ef1d4-658">ACTIVE</span></span>|<span data-ttu-id="ef1d4-659">DATA</span><span class="sxs-lookup"><span data-stu-id="ef1d4-659">DATA</span></span>|<span data-ttu-id="ef1d4-660">38</span><span class="sxs-lookup"><span data-stu-id="ef1d4-660">38</span></span>|<span data-ttu-id="ef1d4-661">5152</span><span class="sxs-lookup"><span data-stu-id="ef1d4-661">5152</span></span>|  
|<span data-ttu-id="ef1d4-662">ACTIVE</span><span class="sxs-lookup"><span data-stu-id="ef1d4-662">ACTIVE</span></span>|<span data-ttu-id="ef1d4-663">DELTA</span><span class="sxs-lookup"><span data-stu-id="ef1d4-663">DELTA</span></span>|<span data-ttu-id="ef1d4-664">38</span><span class="sxs-lookup"><span data-stu-id="ef1d4-664">38</span></span>|<span data-ttu-id="ef1d4-665">1331</span><span class="sxs-lookup"><span data-stu-id="ef1d4-665">1331</span></span>|  
|<span data-ttu-id="ef1d4-666">MERGE TARGET</span><span class="sxs-lookup"><span data-stu-id="ef1d4-666">MERGE TARGET</span></span>|<span data-ttu-id="ef1d4-667">DATA</span><span class="sxs-lookup"><span data-stu-id="ef1d4-667">DATA</span></span>|<span data-ttu-id="ef1d4-668">7</span><span class="sxs-lookup"><span data-stu-id="ef1d4-668">7</span></span>|<span data-ttu-id="ef1d4-669">896</span><span class="sxs-lookup"><span data-stu-id="ef1d4-669">896</span></span>|  
|<span data-ttu-id="ef1d4-670">MERGE TARGET</span><span class="sxs-lookup"><span data-stu-id="ef1d4-670">MERGE TARGET</span></span>|<span data-ttu-id="ef1d4-671">DELTA</span><span class="sxs-lookup"><span data-stu-id="ef1d4-671">DELTA</span></span>|<span data-ttu-id="ef1d4-672">7</span><span class="sxs-lookup"><span data-stu-id="ef1d4-672">7</span></span>|<span data-ttu-id="ef1d4-673">56</span><span class="sxs-lookup"><span data-stu-id="ef1d4-673">56</span></span>|  
|<span data-ttu-id="ef1d4-674">MERGED SOURCE</span><span class="sxs-lookup"><span data-stu-id="ef1d4-674">MERGED SOURCE</span></span>|<span data-ttu-id="ef1d4-675">DATA</span><span class="sxs-lookup"><span data-stu-id="ef1d4-675">DATA</span></span>|<span data-ttu-id="ef1d4-676">13</span><span class="sxs-lookup"><span data-stu-id="ef1d4-676">13</span></span>|<span data-ttu-id="ef1d4-677">1772</span><span class="sxs-lookup"><span data-stu-id="ef1d4-677">1772</span></span>|  
|<span data-ttu-id="ef1d4-678">MERGED SOURCE</span><span class="sxs-lookup"><span data-stu-id="ef1d4-678">MERGED SOURCE</span></span>|<span data-ttu-id="ef1d4-679">DELTA</span><span class="sxs-lookup"><span data-stu-id="ef1d4-679">DELTA</span></span>|<span data-ttu-id="ef1d4-680">13</span><span class="sxs-lookup"><span data-stu-id="ef1d4-680">13</span></span>|<span data-ttu-id="ef1d4-681">455</span><span class="sxs-lookup"><span data-stu-id="ef1d4-681">455</span></span>|  
  
 <span data-ttu-id="ef1d4-682">Le destinazioni delle unioni vengono installate e le origini unite vengono rimosse quando viene eseguita l'attività transazionale nel sistema.</span><span class="sxs-lookup"><span data-stu-id="ef1d4-682">Merge targets are installed and merged source are cleaned up as transactional activity happens in the system.</span></span>  
  
 <span data-ttu-id="ef1d4-683">Al termine di una seconda esecuzione del carico di lavoro dimostrativo, inserendo 10 milioni di ordini vendita dopo la reimpostazione della dimostrazione, si noterà che i file creati durante la prima esecuzione del carico di lavoro sono stati rimossi.</span><span class="sxs-lookup"><span data-stu-id="ef1d4-683">After a second run of the demo workload, inserting 10 million sales orders after the demo reset, you will see that the files constructed during the first run of the workload have been cleaned up.</span></span> <span data-ttu-id="ef1d4-684">Se si esegue la query sopra indicata più volte durante l'esecuzione del carico di lavoro, si potranno visualizzare i file del checkpoint durante le varie fasi.</span><span class="sxs-lookup"><span data-stu-id="ef1d4-684">If you run the above query several times while the workload is running, you can see the checkpoint files make their way through the various stages.</span></span>  
  
 <span data-ttu-id="ef1d4-685">Dopo la seconda esecuzione del carico di lavoro con l'inserimento di 10 milioni di ordini vendita, si visualizzerà un utilizzo del disco molto simile a (ma non necessariamente lo stesso di quello dopo la prima esecuzione) quello del sistema dinamico in natura.</span><span class="sxs-lookup"><span data-stu-id="ef1d4-685">After the second run of the workload insert 10 million sales orders you will see disk utilization very similar to, though not necessarily the same as after the first run, as the system is dynamic in nature.</span></span> <span data-ttu-id="ef1d4-686">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="ef1d4-686">For example:</span></span>  
  
```  
SELECT state_desc  
 , file_type_desc  
 , COUNT(*) AS [count]  
 , SUM(CASE  
   WHEN state = 5 AND file_type=0 THEN 128*1024*1024  
   WHEN state = 5 AND file_type=1 THEN 8*1024*1024  
   WHEN state IN (6,7) THEN 68*1024*1024  
   ELSE file_size_in_bytes  
    END) / 1024 / 1024 AS [on-disk size MB]   
FROM sys.dm_db_xtp_checkpoint_files  
GROUP BY state, state_desc, file_type, file_type_desc  
ORDER BY state, file_type  
```  
  
|||||  
|-|-|-|-|  
|<span data-ttu-id="ef1d4-687">**state_desc**</span><span class="sxs-lookup"><span data-stu-id="ef1d4-687">**state_desc**</span></span>|<span data-ttu-id="ef1d4-688">**file_type_desc**</span><span class="sxs-lookup"><span data-stu-id="ef1d4-688">**file_type_desc**</span></span>|<span data-ttu-id="ef1d4-689">**count**</span><span class="sxs-lookup"><span data-stu-id="ef1d4-689">**count**</span></span>|<span data-ttu-id="ef1d4-690">**on-disk size MB**</span><span class="sxs-lookup"><span data-stu-id="ef1d4-690">**on-disk size MB**</span></span>|  
|<span data-ttu-id="ef1d4-691">PRECREATED</span><span class="sxs-lookup"><span data-stu-id="ef1d4-691">PRECREATED</span></span>|<span data-ttu-id="ef1d4-692">DATA</span><span class="sxs-lookup"><span data-stu-id="ef1d4-692">DATA</span></span>|<span data-ttu-id="ef1d4-693">16</span><span class="sxs-lookup"><span data-stu-id="ef1d4-693">16</span></span>|<span data-ttu-id="ef1d4-694">2048</span><span class="sxs-lookup"><span data-stu-id="ef1d4-694">2048</span></span>|  
|<span data-ttu-id="ef1d4-695">PRECREATED</span><span class="sxs-lookup"><span data-stu-id="ef1d4-695">PRECREATED</span></span>|<span data-ttu-id="ef1d4-696">DELTA</span><span class="sxs-lookup"><span data-stu-id="ef1d4-696">DELTA</span></span>|<span data-ttu-id="ef1d4-697">16</span><span class="sxs-lookup"><span data-stu-id="ef1d4-697">16</span></span>|<span data-ttu-id="ef1d4-698">128</span><span class="sxs-lookup"><span data-stu-id="ef1d4-698">128</span></span>|  
|<span data-ttu-id="ef1d4-699">UNDER CONSTRUCTION</span><span class="sxs-lookup"><span data-stu-id="ef1d4-699">UNDER CONSTRUCTION</span></span>|<span data-ttu-id="ef1d4-700">DATA</span><span class="sxs-lookup"><span data-stu-id="ef1d4-700">DATA</span></span>|<span data-ttu-id="ef1d4-701">2</span><span class="sxs-lookup"><span data-stu-id="ef1d4-701">2</span></span>|<span data-ttu-id="ef1d4-702">268</span><span class="sxs-lookup"><span data-stu-id="ef1d4-702">268</span></span>|  
|<span data-ttu-id="ef1d4-703">UNDER CONSTRUCTION</span><span class="sxs-lookup"><span data-stu-id="ef1d4-703">UNDER CONSTRUCTION</span></span>|<span data-ttu-id="ef1d4-704">DELTA</span><span class="sxs-lookup"><span data-stu-id="ef1d4-704">DELTA</span></span>|<span data-ttu-id="ef1d4-705">2</span><span class="sxs-lookup"><span data-stu-id="ef1d4-705">2</span></span>|<span data-ttu-id="ef1d4-706">16</span><span class="sxs-lookup"><span data-stu-id="ef1d4-706">16</span></span>|  
|<span data-ttu-id="ef1d4-707">ACTIVE</span><span class="sxs-lookup"><span data-stu-id="ef1d4-707">ACTIVE</span></span>|<span data-ttu-id="ef1d4-708">DATA</span><span class="sxs-lookup"><span data-stu-id="ef1d4-708">DATA</span></span>|<span data-ttu-id="ef1d4-709">41</span><span class="sxs-lookup"><span data-stu-id="ef1d4-709">41</span></span>|<span data-ttu-id="ef1d4-710">5608</span><span class="sxs-lookup"><span data-stu-id="ef1d4-710">5608</span></span>|  
|<span data-ttu-id="ef1d4-711">ACTIVE</span><span class="sxs-lookup"><span data-stu-id="ef1d4-711">ACTIVE</span></span>|<span data-ttu-id="ef1d4-712">DELTA</span><span class="sxs-lookup"><span data-stu-id="ef1d4-712">DELTA</span></span>|<span data-ttu-id="ef1d4-713">41</span><span class="sxs-lookup"><span data-stu-id="ef1d4-713">41</span></span>|<span data-ttu-id="ef1d4-714">328</span><span class="sxs-lookup"><span data-stu-id="ef1d4-714">328</span></span>|  
  
 <span data-ttu-id="ef1d4-715">In questo caso, sono disponibili due coppie di file di checkpoint nello stato 'in costruzione', il che significa che più coppie di file sono passate allo stato 'in costruzione' probabilmente a causa dell'elevato livello di concorrenza del carico di lavoro.</span><span class="sxs-lookup"><span data-stu-id="ef1d4-715">In this case, there are two checkpoint file pairs in the 'under construction' state, which means multiple file pairs were moved to the 'under construction' state, likely due to the high level of concurrency in the workload.</span></span> <span data-ttu-id="ef1d4-716">Più thread simultanei hanno richiesto una nuova coppia di file contemporaneamente e di conseguenza una coppia è passata dallo stato di 'precreato' a quello di 'in costruzione'.</span><span class="sxs-lookup"><span data-stu-id="ef1d4-716">Multiple concurrent threads required a new file pair at the same time, and thus moved a pair from 'precreated' to 'under construction'.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ef1d4-717">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ef1d4-717">See Also</span></span>  
 [<span data-ttu-id="ef1d4-718">OLTP in memoria &#40;ottimizzazione per la memoria&#41;</span><span class="sxs-lookup"><span data-stu-id="ef1d4-718">In-Memory OLTP &#40;In-Memory Optimization&#41;</span></span>](../relational-databases/in-memory-oltp/in-memory-oltp-in-memory-optimization.md)  
  
