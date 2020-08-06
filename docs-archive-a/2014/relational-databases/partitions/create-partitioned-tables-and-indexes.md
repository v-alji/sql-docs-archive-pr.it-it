---
title: Creare tabelle e indici partizionati | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
f1_keywords:
- sql12.swb.createpartition.partitionscheme.f1
- sql12.swb.createpartition.selectoutput.f1
- sql12.swb.createpartition.finish.f1
- sql12.swb.createpartition.summary.f1
- sql12.swb.createpartition.mappartition.f1
- sql12.swb.createpartition.partitioncolumn.f1
- sql12.swb.createpartition.progress.f1
- sql12.swb.createpartition.createjob.f1
- sql12.swb.createpartition.getstart.f1
- sql12.swb.createpartition.partitionfunction.f1
helpviewer_keywords:
- partitioned indexes [SQL Server], creating
- partition schemes [SQL Server], creating
- partition functions [SQL Server], creating
- partitioned tables [SQL Server], creating
- partition functions [SQL Server]
- partition schemes [SQL Server]
ms.assetid: 7641df10-1921-42a7-ba6e-4cb03b3ba9c8
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 76ccd8b784902f8542f06f3823e5f8dcb78e9201
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87627213"
---
# <a name="create-partitioned-tables-and-indexes"></a><span data-ttu-id="1b4b0-102">Creare tabelle e indici partizionati</span><span class="sxs-lookup"><span data-stu-id="1b4b0-102">Create Partitioned Tables and Indexes</span></span>
  <span data-ttu-id="1b4b0-103">Utilizzando [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] o [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] è possibile creare una tabella o un indice partizionato in [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="1b4b0-103">You can create a partitioned table or index in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span> <span data-ttu-id="1b4b0-104">I dati delle tabelle e degli indici partizionati vengono suddivisi orizzontalmente in unità che possono essere distribuite in più filegroup di un database.</span><span class="sxs-lookup"><span data-stu-id="1b4b0-104">The data in partitioned tables and indexes is horizontally divided into units that can be spread across more than one filegroup in a database.</span></span> <span data-ttu-id="1b4b0-105">Il partizionamento semplifica la gestione delle tabelle e degli indici di grandi dimensioni e li rende più scalabili.</span><span class="sxs-lookup"><span data-stu-id="1b4b0-105">Partitioning can make large tables and indexes more manageable and scalable.</span></span>  
  
 <span data-ttu-id="1b4b0-106">La creazione di una tabella o di un indice partizionato richiede generalmente quattro operazioni:</span><span class="sxs-lookup"><span data-stu-id="1b4b0-106">Creating a partitioned table or index typically happens in four parts:</span></span>  
  
1.  <span data-ttu-id="1b4b0-107">Creazione di uno o più filegroup e dei file corrispondenti in cui saranno incluse le partizioni specificate dal relativo schema.</span><span class="sxs-lookup"><span data-stu-id="1b4b0-107">Create a filegroup or filegroups and corresponding files that will hold the partitions specified by the partition scheme.</span></span>  
  
2.  <span data-ttu-id="1b4b0-108">Creazione di una funzione di partizione tramite cui viene eseguito il mapping delle righe di una tabella o di un indice alle partizioni in base ai valori della colonna specificata.</span><span class="sxs-lookup"><span data-stu-id="1b4b0-108">Create a partition function that maps the rows of a table or index into partitions based on the values of a specified column.</span></span>  
  
3.  <span data-ttu-id="1b4b0-109">Creazione di uno schema di partizione tramite cui viene eseguito il mapping delle partizioni di una tabella o un indice partizionato ai nuovi filegroup.</span><span class="sxs-lookup"><span data-stu-id="1b4b0-109">Create a partition scheme that maps the partitions of a partitioned table or index to the new filegroups.</span></span>  
  
4.  <span data-ttu-id="1b4b0-110">Creazione o modifica di una tabella o un indice e specificazione dello schema di partizione come percorso di archiviazione.</span><span class="sxs-lookup"><span data-stu-id="1b4b0-110">Create or modify a table or index and specify the partition scheme as the storage location.</span></span>  
  
 <span data-ttu-id="1b4b0-111">**Contenuto dell'articolo**</span><span class="sxs-lookup"><span data-stu-id="1b4b0-111">**In This Topic**</span></span>  
  
-   <span data-ttu-id="1b4b0-112">**Prima di iniziare:**</span><span class="sxs-lookup"><span data-stu-id="1b4b0-112">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="1b4b0-113">Limitazioni e restrizioni</span><span class="sxs-lookup"><span data-stu-id="1b4b0-113">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="1b4b0-114">Sicurezza</span><span class="sxs-lookup"><span data-stu-id="1b4b0-114">Security</span></span>](#Security)  
  
-   <span data-ttu-id="1b4b0-115">**Per creare una tabella o un indice partizionato tramite:**</span><span class="sxs-lookup"><span data-stu-id="1b4b0-115">**To create a partitioned table or index, using:**</span></span>  
  
     [<span data-ttu-id="1b4b0-116">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="1b4b0-116">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="1b4b0-117">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="1b4b0-117">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="1b4b0-118">Prima di iniziare</span><span class="sxs-lookup"><span data-stu-id="1b4b0-118">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="1b4b0-119">Limitazioni e restrizioni</span><span class="sxs-lookup"><span data-stu-id="1b4b0-119">Limitations and Restrictions</span></span>  
  
-   <span data-ttu-id="1b4b0-120">L'ambito di una funzione e di uno schema di partizione è limitato al database in cui sono stati creati.</span><span class="sxs-lookup"><span data-stu-id="1b4b0-120">The scope of a partition function and scheme is limited to the database in which they have been created.</span></span> <span data-ttu-id="1b4b0-121">All'interno del database le funzioni di partizione si trovano in uno spazio dei nomi separato rispetto ad altre funzioni.</span><span class="sxs-lookup"><span data-stu-id="1b4b0-121">Within the database, partition functions reside in a separate namespace from other functions.</span></span>  
  
-   <span data-ttu-id="1b4b0-122">Se in qualsiasi riga all'interno di una funzione di partizione sono disponibili colonne di partizionamento con valori Null, queste righe vengono allocate alla partizione più a sinistra.</span><span class="sxs-lookup"><span data-stu-id="1b4b0-122">If any rows within a partition function have partitioning columns with null values, these rows are allocated to the left-most partition.</span></span> <span data-ttu-id="1b4b0-123">Tuttavia, se è specificato NULL come valore limite ed è indicato RIGHT, la partizione più a sinistra rimane vuota e i valori NULL vengono collocati nella seconda partizione.</span><span class="sxs-lookup"><span data-stu-id="1b4b0-123">However, if NULL is specified as a boundary value and RIGHT is indicated, the left-most partition remains empty and NULL values are placed in the second partition.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="1b4b0-124">Sicurezza</span><span class="sxs-lookup"><span data-stu-id="1b4b0-124">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="1b4b0-125">Autorizzazioni</span><span class="sxs-lookup"><span data-stu-id="1b4b0-125">Permissions</span></span>  
 <span data-ttu-id="1b4b0-126">La creazione di una tabella partizionata richiede l'autorizzazione CREATE TABLE per il database e l'autorizzazione ALTER per lo schema in cui viene creata la tabella.</span><span class="sxs-lookup"><span data-stu-id="1b4b0-126">Creating a partitioned table requires CREATE TABLE permission in the database and ALTER permission on the schema in which the table is being created.</span></span> <span data-ttu-id="1b4b0-127">La creazione di un indice partizionato richiede l'autorizzazione ALTER per la tabella o la vista in cui viene creato l'indice.</span><span class="sxs-lookup"><span data-stu-id="1b4b0-127">Creating a partitioned index requires ALTER permission on the table or view where the index is being created.</span></span> <span data-ttu-id="1b4b0-128">Per la creazione di una tabella o un indice partizionato è richiesta una delle seguenti autorizzazioni aggiuntive:</span><span class="sxs-lookup"><span data-stu-id="1b4b0-128">Creating either a partitioned table or index requires any one of the following additional permissions:</span></span>  
  
-   <span data-ttu-id="1b4b0-129">Autorizzazione ALTER ANY DATASPACE.</span><span class="sxs-lookup"><span data-stu-id="1b4b0-129">ALTER ANY DATASPACE permission.</span></span> <span data-ttu-id="1b4b0-130">Questa autorizzazione viene concessa per impostazione predefinita al ruolo predefinito del server **sysadmin** e ai ruoli predefiniti del database **db_owner** e **db_ddladmin** .</span><span class="sxs-lookup"><span data-stu-id="1b4b0-130">This permission defaults to members of the **sysadmin** fixed server role and the **db_owner** and **db_ddladmin** fixed database roles.</span></span>  
  
-   <span data-ttu-id="1b4b0-131">Autorizzazione CONTROL o ALTER per il database in cui vengono creati la funzione e lo schema di partizione.</span><span class="sxs-lookup"><span data-stu-id="1b4b0-131">CONTROL or ALTER permission on the database in which the partition function and partition scheme are being created.</span></span>  
  
-   <span data-ttu-id="1b4b0-132">Autorizzazione CONTROL SERVER o ALTER ANY DATABASE per il server del database in cui vengono creati la funzione e lo schema di partizione.</span><span class="sxs-lookup"><span data-stu-id="1b4b0-132">CONTROL SERVER or ALTER ANY DATABASE permission on the server of the database in which the partition function and partition scheme are being created.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="1b4b0-133">Con SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="1b4b0-133">Using SQL Server Management Studio</span></span>  
 <span data-ttu-id="1b4b0-134">Per creare uno o più filegroup, i file corrispondenti e una tabella attenersi ai passaggi della procedura riportata di seguito.</span><span class="sxs-lookup"><span data-stu-id="1b4b0-134">Follow the steps in this procedure to create one or more filegroups, corresponding files, and a table.</span></span> <span data-ttu-id="1b4b0-135">Gli oggetti della procedura descritta di seguito verranno utilizzati come riferimento quando si crea la tabella partizionata.</span><span class="sxs-lookup"><span data-stu-id="1b4b0-135">You will reference these objects in the next procedure when you create the partitioned table.</span></span>  
  
#### <a name="to-create-new-filegroups-for-a-partitioned-table"></a><span data-ttu-id="1b4b0-136">Per creare nuovi filegroup per una tabella partizionata</span><span class="sxs-lookup"><span data-stu-id="1b4b0-136">To create new filegroups for a partitioned table</span></span>  
  
1.  <span data-ttu-id="1b4b0-137">In Esplora oggetti fare clic con il pulsante destro del mouse sul database in cui si vuole creare una tabella partizionata e scegliere **Proprietà**.</span><span class="sxs-lookup"><span data-stu-id="1b4b0-137">In Object Explorer, right-click the database in which you want to create a partitioned table and select **Properties**.</span></span>  
  
2.  <span data-ttu-id="1b4b0-138">Nella finestra di dialogo **Proprietà database -** *nome_database* selezionare **Filegroup** in **Selezione pagina**.</span><span class="sxs-lookup"><span data-stu-id="1b4b0-138">In the **Database Properties -** *database_name* dialog box, under **Select a page**, select **Filegroups**.</span></span>  
  
3.  <span data-ttu-id="1b4b0-139">In **Righe**fare clic su **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="1b4b0-139">Under **Rows**, click **Add**.</span></span> <span data-ttu-id="1b4b0-140">Nella nuova riga immettere il nome del filegroup.</span><span class="sxs-lookup"><span data-stu-id="1b4b0-140">In the new row, enter the filegroup name.</span></span>  
  
    > [!WARNING]  
    >  <span data-ttu-id="1b4b0-141">Durante la creazione di partizioni, è necessario disporre sempre di un filegroup aggiuntivo oltre al numero di filegroup specificati per i valori limite.</span><span class="sxs-lookup"><span data-stu-id="1b4b0-141">You must always have one extra filegroup in addition to the number of filegroups specified for the boundary values when you are creating partitions.</span></span>  
  
4.  <span data-ttu-id="1b4b0-142">Continuare ad aggiungere righe finché non vengono creati tutti i filegroup per la tabella partizionata.</span><span class="sxs-lookup"><span data-stu-id="1b4b0-142">Continue adding rows until you have created all of the filegroups for the partitioned table.</span></span>  
  
5.  <span data-ttu-id="1b4b0-143">Fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="1b4b0-143">Click **OK**.</span></span>  
  
6.  <span data-ttu-id="1b4b0-144">In **Selezione pagina**selezionare **File**.</span><span class="sxs-lookup"><span data-stu-id="1b4b0-144">Under **Select a page**, select **Files**.</span></span>  
  
7.  <span data-ttu-id="1b4b0-145">In **Righe**fare clic su **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="1b4b0-145">Under **Rows**, click **Add**.</span></span> <span data-ttu-id="1b4b0-146">Nella nuova riga immettere un nome di file e selezionare un filegroup.</span><span class="sxs-lookup"><span data-stu-id="1b4b0-146">In the new row, enter a filename and select a filegroup.</span></span>  
  
8.  <span data-ttu-id="1b4b0-147">Continuare ad aggiungere righe finché non viene creato almeno un file per ogni filegroup.</span><span class="sxs-lookup"><span data-stu-id="1b4b0-147">Continue adding rows until you have created at least one file for each filegroup.</span></span>  
  
9. <span data-ttu-id="1b4b0-148">Espandere la cartella **Tabelle** e creare una tabella normalmente.</span><span class="sxs-lookup"><span data-stu-id="1b4b0-148">Expand the **Tables** folder and create a table as you normally would.</span></span> <span data-ttu-id="1b4b0-149">Per altre informazioni, vedere [Creare tabelle &#40;Motore di database&#41;](../tables/create-tables-database-engine.md).</span><span class="sxs-lookup"><span data-stu-id="1b4b0-149">For more information, see [Create Tables &#40;Database Engine&#41;](../tables/create-tables-database-engine.md).</span></span> <span data-ttu-id="1b4b0-150">In alternativa, è possibile specificare una tabella esistente nella procedura descritta di seguito.</span><span class="sxs-lookup"><span data-stu-id="1b4b0-150">Alternatively, you can specify an existing table in the next procedure.</span></span>  
  
#### <a name="to-create-a-partitioned-table"></a><span data-ttu-id="1b4b0-151">Per creare una tabella partizionata</span><span class="sxs-lookup"><span data-stu-id="1b4b0-151">To create a partitioned table</span></span>  
  
1.  <span data-ttu-id="1b4b0-152">Fare clic con il pulsante destro del mouse sulla tabella che si vuole partizionare e scegliere **Archiviazione**e quindi selezionare **Create Partition (Crea partizione)** .</span><span class="sxs-lookup"><span data-stu-id="1b4b0-152">Right-click the table that you wish to partition, point to **Storage**, and then click **Create Partition...**.</span></span>  
  
2.  <span data-ttu-id="1b4b0-153">Nella pagina **Creazione guidata partizione**della **relativa procedura guidata** fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="1b4b0-153">In the **Create Partition Wizard**, on the **Welcome to the Create Partition Wizard** page, click **Next**.</span></span>  
  
3.  <span data-ttu-id="1b4b0-154">Nella griglia **Colonne di partizionamento disponibili** della pagina **Seleziona una colonna di partizionamento** selezionare la colonna in cui partizionare la tabella.</span><span class="sxs-lookup"><span data-stu-id="1b4b0-154">On the **Select a Partitioning Column** page, in the **Available partitioning columns** grid, select the column on which you want to partition your table.</span></span> <span data-ttu-id="1b4b0-155">Nella griglia **Colonne di partizionamento disponibili** verranno visualizzate solo le colonne con i tipi di dati che possono essere utilizzati per partizionare dati.</span><span class="sxs-lookup"><span data-stu-id="1b4b0-155">Only columns with data types that can be used to partition data will be displayed in the **Available partitioning columns** grid.</span></span> <span data-ttu-id="1b4b0-156">Se come colonna di partizionamento se ne sceglie una calcolata, la colonna deve essere definita come persistente.</span><span class="sxs-lookup"><span data-stu-id="1b4b0-156">If you select a computed column as the partitioning column, the column must be designated as a persisted column.</span></span>  
  
     <span data-ttu-id="1b4b0-157">Le scelte disponibili per la colonna di partizionamento e per l'intervallo di valori sono determinate innanzitutto dalla possibilità di raggruppare i dati in modo logico.</span><span class="sxs-lookup"><span data-stu-id="1b4b0-157">The choices you have for the partitioning column and the values range are determined primarily by the extent to which your data can be grouped in a logical way.</span></span> <span data-ttu-id="1b4b0-158">È possibile, ad esempio, scegliere di dividere i dati in raggruppamenti logici in base ai mesi o ai trimestri di un anno.</span><span class="sxs-lookup"><span data-stu-id="1b4b0-158">For example, you may choose to divide your data into logical groupings by months or quarters of a year.</span></span> <span data-ttu-id="1b4b0-159">Le query che verranno eseguite sui dati consentiranno di determinare se questo raggruppamento logico sia appropriato per la gestione delle partizioni delle tabelle.</span><span class="sxs-lookup"><span data-stu-id="1b4b0-159">The queries you plan to make against your data will determine whether this logical grouping is adequate for managing your table partitions.</span></span> <span data-ttu-id="1b4b0-160">Come colonne di partizionamento possono essere usati tutti i tipi di dati, tranne `text`, `ntext`, `image`, `xml`, `timestamp`, `varchar(max)`, `nvarchar(max)`, `varbinary(max)`, i tipi di dati alias o i tipi CLR definiti dall'utente.</span><span class="sxs-lookup"><span data-stu-id="1b4b0-160">All data types are valid for use as partitioning columns, except `text`, `ntext`, `image`, `xml`, `timestamp`, `varchar(max)`, `nvarchar(max)`, `varbinary(max)`, alias data types, or CLR user-defined data types.</span></span>  
  
     <span data-ttu-id="1b4b0-161">In questa pagina sono disponibili le seguenti opzioni aggiuntive:</span><span class="sxs-lookup"><span data-stu-id="1b4b0-161">The following additional options are available on this page:</span></span>  
  
     <span data-ttu-id="1b4b0-162">**Colloca tabella nella tabella partizionata selezionata**</span><span class="sxs-lookup"><span data-stu-id="1b4b0-162">**Collocate this table to the selected partitioned table**</span></span>  
     <span data-ttu-id="1b4b0-163">Consente di selezionare una tabella partizionata contenente dati correlati e di creare un join con la tabella nella colonna di partizionamento.</span><span class="sxs-lookup"><span data-stu-id="1b4b0-163">Allows you to select a partitioned table that contains related data to join with this table on the partitioning column.</span></span> <span data-ttu-id="1b4b0-164">Le query sulle tabelle con partizioni unite nelle colonne di partizionamento vengono in genere eseguite in modo più efficiente.</span><span class="sxs-lookup"><span data-stu-id="1b4b0-164">Tables with partitions joined on the partitioning columns are typically queried more efficiently.</span></span>  
  
     <span data-ttu-id="1b4b0-165">**Allinea nello spazio di archiviazione indici univoci e non univoci con una colonna di partizione indicizzata**</span><span class="sxs-lookup"><span data-stu-id="1b4b0-165">**Storage-align non-unique indexes and unique indexes with an indexed partition column**</span></span>  
     <span data-ttu-id="1b4b0-166">Consente di allineare tutti gli indici della tabella partizionati con lo stesso schema di partizione.</span><span class="sxs-lookup"><span data-stu-id="1b4b0-166">Aligns all indexes of the table that are partitioned with the same partition scheme.</span></span> <span data-ttu-id="1b4b0-167">Quando una tabella e i relativi indici sono allineati, è possibile spostare in modo più efficace le partizioni all'interno e all'esterno delle tabelle partizionate, in quanto i dati vengono partizionati con lo stesso algoritmo.</span><span class="sxs-lookup"><span data-stu-id="1b4b0-167">When a table and its indexes are aligned, you can move partitions in and out of partitioned tables more effectively, because your data is partitioned with the same algorithm.</span></span>  
  
     <span data-ttu-id="1b4b0-168">Dopo aver selezionato la colonna di partizionamento e qualsiasi altra opzione, fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="1b4b0-168">After selecting the partitioning column and any other options, click **Next**.</span></span>  
  
4.  <span data-ttu-id="1b4b0-169">In **Seleziona funzione di partizione** della pagina **Seleziona una funzione di partizione**fare clic su **Nuova funzione di partizione** o **Funzione di partizione esistente**.</span><span class="sxs-lookup"><span data-stu-id="1b4b0-169">On the **Select a Partition Function** page, under **Select partition function**, click either **New partition function** or **Existing partition function**.</span></span> <span data-ttu-id="1b4b0-170">Se si sceglie **Nuova funzione di partizione**, immettere il nome della funzione.</span><span class="sxs-lookup"><span data-stu-id="1b4b0-170">If you choose **New partition function**, enter the name of the function.</span></span> <span data-ttu-id="1b4b0-171">Se si sceglie **Funzione di partizione esistente**, selezionare nell'elenco il nome della funzione che si desidera utilizzare.</span><span class="sxs-lookup"><span data-stu-id="1b4b0-171">If you choose **Existing partition function**, select the name of the function you'd like to use from the list.</span></span> <span data-ttu-id="1b4b0-172">L'opzione **Funzione di partizione esistente** non sarà disponibile se non sono presenti altre funzioni di partizione nel database.</span><span class="sxs-lookup"><span data-stu-id="1b4b0-172">The **Existing partition function** option will not be available if there are no other partition functions on the database.</span></span>  
  
     <span data-ttu-id="1b4b0-173">Dopo aver completato questa pagina, fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="1b4b0-173">After completing this page, click **Next**.</span></span>  
  
5.  <span data-ttu-id="1b4b0-174">In **Seleziona schema di partizione** della pagina **Seleziona uno schema di partizione**fare clic su **Nuovo schema di partizione** o **Schema di partizione esistente**.</span><span class="sxs-lookup"><span data-stu-id="1b4b0-174">On the **Select a Partition Scheme** page, under **Select partition scheme**, click either **New partition scheme** or **Existing partition scheme**.</span></span> <span data-ttu-id="1b4b0-175">Se si sceglie **Nuovo schema di partizione**, immettere il nome dello schema.</span><span class="sxs-lookup"><span data-stu-id="1b4b0-175">If you choose **New partition scheme**, enter the name of the scheme.</span></span> <span data-ttu-id="1b4b0-176">Se si sceglie **Schema di partizione esistente**, selezionare nell'elenco il nome dello schema che si desidera utilizzare.</span><span class="sxs-lookup"><span data-stu-id="1b4b0-176">If you choose **Existing partition scheme**, select the name of the scheme you'd like to use from the list.</span></span> <span data-ttu-id="1b4b0-177">L'opzione **Schema di partizione esistente** non sarà disponibile se non sono presenti altri schemi di partizione nel database.</span><span class="sxs-lookup"><span data-stu-id="1b4b0-177">The **Existing partition scheme** option will not be available if there are no other partition schemes on the database.</span></span>  
  
     <span data-ttu-id="1b4b0-178">Dopo aver completato questa pagina, fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="1b4b0-178">After completing this page, click **Next**.</span></span>  
  
6.  <span data-ttu-id="1b4b0-179">In **Intervallo** della pagina **Esegui mapping partizioni**selezionare **Limite sinistro** o **Limite destro** per specificare se includere il valore di delimitazione superiore o inferiore all'interno di ogni filegroup creato.</span><span class="sxs-lookup"><span data-stu-id="1b4b0-179">On the **Map Partitions** page, under **Range**, select either **Left boundary** or **Right boundary** to specify whether to include the highest or lowest bounding value within each filegroup you create.</span></span> <span data-ttu-id="1b4b0-180">Durante la creazione di partizioni, è necessario immettere sempre un filegroup aggiuntivo oltre al numero di filegroup specificati per i valori limite.</span><span class="sxs-lookup"><span data-stu-id="1b4b0-180">You must always enter one extra filegroup in addition to the number of filegroups specified for the boundary values when you are creating partitions.</span></span>  
  
     <span data-ttu-id="1b4b0-181">In **Filegroup** nella griglia **Selezionare i filegroup e specificare i valori limite**selezionare il filegroup in cui si desidera partizionare i dati.</span><span class="sxs-lookup"><span data-stu-id="1b4b0-181">In the **Select filegroups and specify boundary values** grid, under **Filegroup**, select the filegroup into which you want to partition your data.</span></span> <span data-ttu-id="1b4b0-182">In **Limite**immettere il valore limite per ogni filegroup.</span><span class="sxs-lookup"><span data-stu-id="1b4b0-182">Under **Boundary**, enter the boundary value for each filegroup.</span></span> <span data-ttu-id="1b4b0-183">Se il valore limite viene lasciato vuoto, la funzione di partizione consente di eseguire il mapping dell'intera tabella o dell'intero indice a un'unica partizione tramite il nome della funzione di partizione.</span><span class="sxs-lookup"><span data-stu-id="1b4b0-183">If boundary value is left empty, the partition function maps the whole table or index into a single partition using the partition function name.</span></span>  
  
     <span data-ttu-id="1b4b0-184">In questa pagina sono disponibili le seguenti opzioni aggiuntive:</span><span class="sxs-lookup"><span data-stu-id="1b4b0-184">The following additional options are available on this page:</span></span>  
  
     <span data-ttu-id="1b4b0-185">**Imposta limiti...**</span><span class="sxs-lookup"><span data-stu-id="1b4b0-185">**Set Boundaries...**</span></span>  
     <span data-ttu-id="1b4b0-186">Consente di aprire la finestra di dialogo **Imposta valori limite** per selezionare i valori limite e gli intervalli di date desiderati per le partizioni.</span><span class="sxs-lookup"><span data-stu-id="1b4b0-186">Opens the **Set Boundary Values** dialog box to select the boundary values and date ranges you want for your partitions.</span></span> <span data-ttu-id="1b4b0-187">Questa opzione è disponibile solo se è stata selezionata una colonna di partizionamento contenente uno dei tipi di dati seguenti: `date`, `datetime`, `smalldatetime`, `datetime2` o `datetimeoffset`.</span><span class="sxs-lookup"><span data-stu-id="1b4b0-187">This option is only available when you have selected a partitioning column that contains one of the following data types: `date`, `datetime`, `smalldatetime`, `datetime2`, or `datetimeoffset`.</span></span>  
  
     <span data-ttu-id="1b4b0-188">**Valuta spazio di archiviazione**</span><span class="sxs-lookup"><span data-stu-id="1b4b0-188">**Estimate storage**</span></span>  
     <span data-ttu-id="1b4b0-189">Consente di valutare il numero di righe, lo spazio necessario e quello disponibile per l'archiviazione di ciascun filegroup specificato per le partizioni.</span><span class="sxs-lookup"><span data-stu-id="1b4b0-189">Estimates rowcount, required space, and available space for storage for each filegroup specified for the partitions.</span></span> <span data-ttu-id="1b4b0-190">Questi valori vengono visualizzati nella griglia come valori di sola lettura.</span><span class="sxs-lookup"><span data-stu-id="1b4b0-190">These values are displayed in the grid as read-only values.</span></span>  
  
     <span data-ttu-id="1b4b0-191">Nella finestra di dialogo **Imposta valori limite** sono inoltre disponibili le seguenti opzioni aggiuntive:</span><span class="sxs-lookup"><span data-stu-id="1b4b0-191">The **Set Boundary Values** dialog box allows for the following additional options:</span></span>  
  
     <span data-ttu-id="1b4b0-192">**Data inizio**</span><span class="sxs-lookup"><span data-stu-id="1b4b0-192">**Start date**</span></span>  
     <span data-ttu-id="1b4b0-193">Consente di selezionare la data di inizio per i valori di intervallo delle partizioni.</span><span class="sxs-lookup"><span data-stu-id="1b4b0-193">Selects the starting date for the range values of your partitions.</span></span>  
  
     <span data-ttu-id="1b4b0-194">**Data fine**</span><span class="sxs-lookup"><span data-stu-id="1b4b0-194">**End date**</span></span>  
     <span data-ttu-id="1b4b0-195">Consente di selezionare la data di fine per i valori di intervallo delle partizioni.</span><span class="sxs-lookup"><span data-stu-id="1b4b0-195">Selects the ending date for the range values of your partitions.</span></span> <span data-ttu-id="1b4b0-196">Se è stata selezionata l'opzione **Limite sinistro** nella pagina **Esegui mapping partizioni** , questa data costituirà l'ultimo valore per ogni filegroup/partizione.</span><span class="sxs-lookup"><span data-stu-id="1b4b0-196">If you selected **Left boundary** on the **Map Partitions** page, this date will be the last value for each filegroup/partition.</span></span> <span data-ttu-id="1b4b0-197">Se è stata selezionata l'opzione **Limite destro** nella pagina **Esegui mapping partizioni** , questa data costituirà il primo valore nel penultimo filegroup.</span><span class="sxs-lookup"><span data-stu-id="1b4b0-197">If you selected **Right boundary** on the **Map Partitions** page, this date will be the first value in the next-to-last filegroup.</span></span>  
  
     <span data-ttu-id="1b4b0-198">**Intervallo di date**</span><span class="sxs-lookup"><span data-stu-id="1b4b0-198">**Date range**</span></span>  
     <span data-ttu-id="1b4b0-199">Consente di selezionare la granularità della data o l'incremento dei valori di intervallo desiderato per ogni partizione.</span><span class="sxs-lookup"><span data-stu-id="1b4b0-199">Selects the date granularity or range value increment you want for each partition.</span></span>  
  
     <span data-ttu-id="1b4b0-200">Dopo aver completato questa pagina, fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="1b4b0-200">After completing this page, click **Next**.</span></span>  
  
7.  <span data-ttu-id="1b4b0-201">Nella pagina **Seleziona un'opzione di output** specificare il modo in cui si desidera completare la tabella partizionata.</span><span class="sxs-lookup"><span data-stu-id="1b4b0-201">In the **Select an Output Option** page, specify how you want to complete your partitioned table.</span></span> <span data-ttu-id="1b4b0-202">Selezionare **Crea script** per creare uno script SQL in base alle pagine precedenti della procedura guidata.</span><span class="sxs-lookup"><span data-stu-id="1b4b0-202">Select **Create Script** to create a SQL script based the previous pages in the wizard.</span></span> <span data-ttu-id="1b4b0-203">Selezionare **Esegui immediatamente** per creare la nuova tabella partizionata dopo aver completato tutte le pagine rimanenti della procedura guidata.</span><span class="sxs-lookup"><span data-stu-id="1b4b0-203">Select **Run immediately** to create the new partitioned table after completing all remaining pages in the wizard.</span></span> <span data-ttu-id="1b4b0-204">Selezionare **Pianifica** per creare la nuova tabella partizionata in un momento predeterminato nel futuro.</span><span class="sxs-lookup"><span data-stu-id="1b4b0-204">Select **Schedule** to create the new partitioned table at a predetermined time in the future.</span></span>  
  
     <span data-ttu-id="1b4b0-205">Se si seleziona **Crea script**, in **Opzioni di scripting**sono disponibili le opzioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="1b4b0-205">If you select **Create script**, the following options are available under **Script options**:</span></span>  
  
     <span data-ttu-id="1b4b0-206">**Genera script nel file**</span><span class="sxs-lookup"><span data-stu-id="1b4b0-206">**Script to file**</span></span>  
     <span data-ttu-id="1b4b0-207">Genera lo script come file con estensione sql.</span><span class="sxs-lookup"><span data-stu-id="1b4b0-207">Generates the script as a .sql file.</span></span> <span data-ttu-id="1b4b0-208">Immettere un nome di file e il percorso nella casella **Nome file** o fare clic su **Sfoglia** per aprire la finestra di dialogo **Percorso file script** .</span><span class="sxs-lookup"><span data-stu-id="1b4b0-208">Enter a file name and location in the **File name** box or click **Browse** to open the **Script File Location** dialog box.</span></span> <span data-ttu-id="1b4b0-209">In **Salva con nome**selezionare **Testo Unicode** o **Testo ANSI**.</span><span class="sxs-lookup"><span data-stu-id="1b4b0-209">From **Save As**, select **Unicode text** or **ANSI text**.</span></span>  
  
     <span data-ttu-id="1b4b0-210">**Genera script negli Appunti**</span><span class="sxs-lookup"><span data-stu-id="1b4b0-210">**Script to Clipboard**</span></span>  
     <span data-ttu-id="1b4b0-211">Salva lo script negli Appunti.</span><span class="sxs-lookup"><span data-stu-id="1b4b0-211">Saves the script to the Clipboard.</span></span>  
  
     <span data-ttu-id="1b4b0-212">**Genera script in nuova finestra Query**</span><span class="sxs-lookup"><span data-stu-id="1b4b0-212">**Script to New Query Window**</span></span>  
     <span data-ttu-id="1b4b0-213">Genera lo script in una nuova finestra dell'editor di query.</span><span class="sxs-lookup"><span data-stu-id="1b4b0-213">Generates the script to a new Query Editor window.</span></span> <span data-ttu-id="1b4b0-214">Si tratta della selezione predefinita.</span><span class="sxs-lookup"><span data-stu-id="1b4b0-214">This is the default selection.</span></span>  
  
     <span data-ttu-id="1b4b0-215">Se si seleziona **Pianifica**, fare clic su **Cambia pianificazione**.</span><span class="sxs-lookup"><span data-stu-id="1b4b0-215">If you select **Schedule**, click **Change schedule**.</span></span>  
  
    1.  <span data-ttu-id="1b4b0-216">Nella casella **Nome** della finestra di dialogo **Nuova pianificazione processo** immettere il nome della pianificazione del processo.</span><span class="sxs-lookup"><span data-stu-id="1b4b0-216">In the **New Job Schedule** dialog box, in the **Name** box, enter the job schedule's name.</span></span>  
  
    2.  <span data-ttu-id="1b4b0-217">Nell'elenco **Tipo pianificazione** selezionare il tipo di pianificazione:</span><span class="sxs-lookup"><span data-stu-id="1b4b0-217">On the **Schedule type** list, select the type of schedule:</span></span>  
  
        -   <span data-ttu-id="1b4b0-218">**Avvia automaticamente all'avvio di SQL Server Agent**</span><span class="sxs-lookup"><span data-stu-id="1b4b0-218">**Start automatically when SQL Server Agent starts**</span></span>  
  
        -   <span data-ttu-id="1b4b0-219">**Avvia quando la CPU risulta inattiva**</span><span class="sxs-lookup"><span data-stu-id="1b4b0-219">**Start whenever the CPUs become idle**</span></span>  
  
        -   <span data-ttu-id="1b4b0-220">**Periodica**.</span><span class="sxs-lookup"><span data-stu-id="1b4b0-220">**Recurring**.</span></span> <span data-ttu-id="1b4b0-221">Selezionare questa opzione se la nuova tabella partizionata viene aggiornata regolarmente con nuove informazioni.</span><span class="sxs-lookup"><span data-stu-id="1b4b0-221">Select this option if your new partitioned table updates with new information on a regular basis.</span></span>  
  
        -   <span data-ttu-id="1b4b0-222">**Singola occorrenza**.</span><span class="sxs-lookup"><span data-stu-id="1b4b0-222">**One time**.</span></span> <span data-ttu-id="1b4b0-223">Si tratta della selezione predefinita.</span><span class="sxs-lookup"><span data-stu-id="1b4b0-223">This is the default selection.</span></span>  
  
    3.  <span data-ttu-id="1b4b0-224">Selezionare o deselezionare la casella di controllo **Abilitata** per abilitare o disabilitare la pianificazione.</span><span class="sxs-lookup"><span data-stu-id="1b4b0-224">Select or clear the **Enabled** check box to enable or disable the schedule.</span></span>  
  
    4.  <span data-ttu-id="1b4b0-225">Se si seleziona **Periodica**:</span><span class="sxs-lookup"><span data-stu-id="1b4b0-225">If you select **Recurring**:</span></span>  
  
        1.  <span data-ttu-id="1b4b0-226">In **Frequenza**nell'elenco **Ricorrenza** specificare la frequenza di occorrenza:</span><span class="sxs-lookup"><span data-stu-id="1b4b0-226">Under **Frequency**, on the **Occurs** list, specify the frequency of occurrence:</span></span>  
  
            -   <span data-ttu-id="1b4b0-227">Se si seleziona **Giornaliera**, nella casella **Ogni** immettere la frequenza in base alla quale si ripete la pianificazione del processo nei giorni.</span><span class="sxs-lookup"><span data-stu-id="1b4b0-227">If you select **Daily**, in the **Recurs every** box, enter how often the job schedule repeats in days.</span></span>  
  
            -   <span data-ttu-id="1b4b0-228">Se si seleziona **Settimanale**, nella casella **Ogni** immettere la frequenza in base alla quale si ripete la pianificazione del processo nelle settimane.</span><span class="sxs-lookup"><span data-stu-id="1b4b0-228">If you select **Weekly**, in the **Recurs every** box, enter how often the job schedule repeats in weeks.</span></span> <span data-ttu-id="1b4b0-229">Selezionare i giorni della settimana durante i quali viene eseguita la pianificazione del processo.</span><span class="sxs-lookup"><span data-stu-id="1b4b0-229">Select the day or days of the week on which the job schedule is run.</span></span>  
  
            -   <span data-ttu-id="1b4b0-230">Se si seleziona **Mensile**, selezionare **Giorno** oppure **Ogni**.</span><span class="sxs-lookup"><span data-stu-id="1b4b0-230">If you select **Monthly**, select either **Day** or **The**.</span></span>  
  
                -   <span data-ttu-id="1b4b0-231">Se si seleziona **Giorno**, immettere sia la data del mese in cui si desidera sia eseguita la pianificazione del processo sia la frequenza in base alla quale si ripete questa pianificazione nei mesi.</span><span class="sxs-lookup"><span data-stu-id="1b4b0-231">If you select **Day**, enter both the date of the month you want the job schedule to run and how often the job schedule repeats in months.</span></span> <span data-ttu-id="1b4b0-232">Ad esempio, se si vuole che la pianificazione del processo sia eseguita il giorno 15 del mese a mesi alterni, selezionare **Giorno** e immettere "15" nella prima casella e "2" nella seconda casella.</span><span class="sxs-lookup"><span data-stu-id="1b4b0-232">For example, if you want the job schedule to run on the 15th day of the month every other month, select **Day** and enter "15" in the first box and "2" in the second box.</span></span> <span data-ttu-id="1b4b0-233">Si noti che il numero più grande consentito nella seconda casella è "99".</span><span class="sxs-lookup"><span data-stu-id="1b4b0-233">Please note that the largest number allowed in the second box is "99".</span></span>  
  
                -   <span data-ttu-id="1b4b0-234">Se si sceglie **Ogni**, selezionare il giorno specifico della settimana del mese in cui si desidera sia eseguita la pianificazione del processo e la frequenza in base alla quale si ripete questa pianificazione nei mesi.</span><span class="sxs-lookup"><span data-stu-id="1b4b0-234">If you select **The**, select the specific day of the week within the month that you want the job schedule to run and how often the job schedule repeats in months.</span></span> <span data-ttu-id="1b4b0-235">Ad esempio, se si vuole che la pianificazione del processo sia eseguita l'ultimo giorno feriale del mese a mesi alterni, selezionare **Giorno**, selezionare **ultimo** nel primo elenco e **giorno feriale** nel secondo elenco, quindi immettere "2" nell'ultima casella.</span><span class="sxs-lookup"><span data-stu-id="1b4b0-235">For example, if you want the job schedule to run on the last weekday of the month every other month, select **Day**, select **last** from the first list and **weekday** from the second list, and then enter "2" in the last box.</span></span> <span data-ttu-id="1b4b0-236">Nei primi due elenchi è anche possibile selezionare **primo**, **secondo**, **terzo**o **quarto**, nonché i giorni della settimana specifici, ad esempio domenica o mercoledì.</span><span class="sxs-lookup"><span data-stu-id="1b4b0-236">You can also select **first**, **second**, **third**, or **fourth**, as well as specific weekdays (for example: Sunday or Wednesday) from the first two lists.</span></span> <span data-ttu-id="1b4b0-237">Si noti che il numero più grande consentito nell'ultima casella è "99".</span><span class="sxs-lookup"><span data-stu-id="1b4b0-237">Please note that the largest number allowed in the last box is "99".</span></span>  
  
        2.  <span data-ttu-id="1b4b0-238">In **Frequenza giornaliera**specificare la frequenza in base alla quale si ripete la pianificazione del processo in quel determinato giorno:</span><span class="sxs-lookup"><span data-stu-id="1b4b0-238">Under **Daily frequency**, specify how often the job schedule repeats on the day the job schedule runs:</span></span>  
  
            -   <span data-ttu-id="1b4b0-239">Se si seleziona **Una sola volta alle**, immettere l'ora specifica del giorno in cui deve essere eseguita la pianificazione del processo nella casella **Una sola volta alle** .</span><span class="sxs-lookup"><span data-stu-id="1b4b0-239">If you select **Occurs once at**, enter the specific time of day when the job schedule should run in the **Occurs once at** box.</span></span> <span data-ttu-id="1b4b0-240">Immettere l'ora, il minuto e il secondo del giorno, nonché AM o PM.</span><span class="sxs-lookup"><span data-stu-id="1b4b0-240">Enter the hour, minute, and second of the day, as well as AM or PM.</span></span>  
  
            -   <span data-ttu-id="1b4b0-241">Se si seleziona **Ogni**specificare la frequenza in base alla quale la pianificazione del processo viene eseguita durante il giorno scelto in **Frequenza**.</span><span class="sxs-lookup"><span data-stu-id="1b4b0-241">If you select **Occurs every**, specify how often the job schedule runs during the day chosen under **Frequency**.</span></span> <span data-ttu-id="1b4b0-242">Ad esempio, se si vuole che la pianificazione del processo sia ripetuta ogni 2 ore durante il giorno scelto per questa pianificazione, selezionare **Ogni**, immettere "2" nella prima casella e quindi selezionare **ora/e** nell'elenco.</span><span class="sxs-lookup"><span data-stu-id="1b4b0-242">For example, if you want the job schedule to repeat every 2 hours during the day that the job schedule is run, select **Occurs every**, enter "2" in the first box, and then select **hour(s)** from the list.</span></span> <span data-ttu-id="1b4b0-243">In questo elenco è anche possibile selezionare **minuto/i** e **secondo/i**.</span><span class="sxs-lookup"><span data-stu-id="1b4b0-243">From this list you can also select **minute(s)** and **second(s)**.</span></span> <span data-ttu-id="1b4b0-244">Si noti che il numero più grande consentito nella prima casella è "100".</span><span class="sxs-lookup"><span data-stu-id="1b4b0-244">Please note that the largest number allowed in the first box is "100".</span></span>  
  
                 <span data-ttu-id="1b4b0-245">Nella casella **A partire dalle** immettere l'ora in cui dovrebbe iniziare l'esecuzione della pianificazione del processo.</span><span class="sxs-lookup"><span data-stu-id="1b4b0-245">In the **Starting at** box, enter the time that the job schedule should start running.</span></span> <span data-ttu-id="1b4b0-246">Nella casella **Fino alle** immettere l'ora in cui dovrebbe terminare la ripetizione della pianificazione del processo.</span><span class="sxs-lookup"><span data-stu-id="1b4b0-246">In the **Ending at** box, enter the time that the job schedule should stop repeating.</span></span> <span data-ttu-id="1b4b0-247">Immettere l'ora, il minuto e il secondo del giorno, nonché AM o PM.</span><span class="sxs-lookup"><span data-stu-id="1b4b0-247">Enter the hour, minute, and second of the day, as well as AM or PM.</span></span>  
  
        3.  <span data-ttu-id="1b4b0-248">In **Durata**di **Data inizio**immettere la data in cui si desidera sia avviata l'esecuzione della pianificazione del processo.</span><span class="sxs-lookup"><span data-stu-id="1b4b0-248">Under **Duration**, in **Start date**, enter the date that you want the job schedule to start running.</span></span> <span data-ttu-id="1b4b0-249">Selezionare **Data fine** o **Nessuna data di fine** per indicare quando dovrebbe terminare l'esecuzione della pianificazione del processo.</span><span class="sxs-lookup"><span data-stu-id="1b4b0-249">Select **End date** or **No end date** to indicate when the job schedule should stop running.</span></span> <span data-ttu-id="1b4b0-250">Se si seleziona **Data fine**immettere la data in cui si desidera venga terminata l'esecuzione della pianificazione del processo.</span><span class="sxs-lookup"><span data-stu-id="1b4b0-250">If you select **End date**, enter the date that you want to job schedule to stop running.</span></span>  
  
    5.  <span data-ttu-id="1b4b0-251">Se si seleziona **Singola occorrenza**, in **Singola occorrenza**, nella casella **Data** immettere la data in cui verrà eseguita la pianificazione del processo.</span><span class="sxs-lookup"><span data-stu-id="1b4b0-251">If you select **One Time**, under **One-time occurrence**, in the **Date** box, enter the date that the job schedule will be run.</span></span> <span data-ttu-id="1b4b0-252">Nella casella **Ora** immettere l'ora in cui verrà eseguita la pianificazione del processo.</span><span class="sxs-lookup"><span data-stu-id="1b4b0-252">In the **Time** box, enter the time that the job schedule will be run.</span></span> <span data-ttu-id="1b4b0-253">Immettere l'ora, il minuto e il secondo del giorno, nonché AM o PM.</span><span class="sxs-lookup"><span data-stu-id="1b4b0-253">Enter the hour, minute, and second of the day, as well as AM or PM.</span></span>  
  
    6.  <span data-ttu-id="1b4b0-254">In **Descrizione**in **Riepilogo**verificare che tutte le impostazioni della pianificazione del processo siano corrette.</span><span class="sxs-lookup"><span data-stu-id="1b4b0-254">Under **Summary**, in **Description**, verify that all job schedule settings are correct.</span></span>  
  
    7.  <span data-ttu-id="1b4b0-255">Fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="1b4b0-255">Click **OK**.</span></span>  
  
     <span data-ttu-id="1b4b0-256">Dopo aver completato questa pagina, fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="1b4b0-256">After completing this page, click **Next**.</span></span>  
  
8.  <span data-ttu-id="1b4b0-257">In **Controlla selezioni** della pagina **Controlla riepilogo**espandere tutte le opzioni disponibili per verificare che tutte le impostazioni della partizione siano corrette.</span><span class="sxs-lookup"><span data-stu-id="1b4b0-257">On the **Review Summary** page, under **Review your selections**, expand all available options to verify that all partition settings are correct.</span></span> <span data-ttu-id="1b4b0-258">Se tutte le impostazioni sono corrette, fare clic su **Fine**.</span><span class="sxs-lookup"><span data-stu-id="1b4b0-258">If everything is as expected, click **Finish**.</span></span>  
  
9. <span data-ttu-id="1b4b0-259">Nella pagina **Stato Creazione guidata partizione** monitorare le informazioni sullo stato delle azioni della Creazione guidata partizione.</span><span class="sxs-lookup"><span data-stu-id="1b4b0-259">On the **Create Partition Wizard Progress** page, monitor status information about the actions of the Create Partition Wizard.</span></span> <span data-ttu-id="1b4b0-260">A seconda delle opzioni selezionate nella procedura guidata, la pagina di stato può contenere una o più azioni.</span><span class="sxs-lookup"><span data-stu-id="1b4b0-260">Depending on the options that you selected in the wizard, the progress page might contain one or more actions.</span></span> <span data-ttu-id="1b4b0-261">Nella casella superiore viene visualizzato lo stato complessivo della procedura guidata e viene indicato il numero di messaggi di stato, di errore e di avviso restituiti durante l'esecuzione della procedura guidata.</span><span class="sxs-lookup"><span data-stu-id="1b4b0-261">The top box displays the overall status of the wizard and the number of status, error, and warning messages that the wizard has received.</span></span>  
  
     <span data-ttu-id="1b4b0-262">Le opzioni seguenti sono disponibili nella pagina **Stato Creazione guidata partizione** :</span><span class="sxs-lookup"><span data-stu-id="1b4b0-262">The following options are available on the **Create Partition Wizard Progress** page:</span></span>  
  
     <span data-ttu-id="1b4b0-263">**Dettagli**</span><span class="sxs-lookup"><span data-stu-id="1b4b0-263">**Details**</span></span>  
     <span data-ttu-id="1b4b0-264">Consente di visualizzare i messaggi di azione, di stato e di altro tipo restituiti dall'azione eseguita nella procedura guidata.</span><span class="sxs-lookup"><span data-stu-id="1b4b0-264">Provides the action, status, and any messages that are returned from action taken by the wizard.</span></span>  
  
     <span data-ttu-id="1b4b0-265">**Azione**</span><span class="sxs-lookup"><span data-stu-id="1b4b0-265">**Action**</span></span>  
     <span data-ttu-id="1b4b0-266">Specifica il tipo e il nome di ciascuna azione.</span><span class="sxs-lookup"><span data-stu-id="1b4b0-266">Specifies the type and name of each action.</span></span>  
  
     <span data-ttu-id="1b4b0-267">**Status**</span><span class="sxs-lookup"><span data-stu-id="1b4b0-267">**Status**</span></span>  
     <span data-ttu-id="1b4b0-268">Indica se l'intera azione della procedura guidata ha restituito il valore **Esito positivo** o **Esito negativo**.</span><span class="sxs-lookup"><span data-stu-id="1b4b0-268">Indicates whether the wizard action as a whole returned the value of **Success** or **Failure**.</span></span>  
  
     <span data-ttu-id="1b4b0-269">**Messaggio**</span><span class="sxs-lookup"><span data-stu-id="1b4b0-269">**Message**</span></span>  
     <span data-ttu-id="1b4b0-270">Fornisce tutti i messaggi di errore o di avviso restituiti dal processo.</span><span class="sxs-lookup"><span data-stu-id="1b4b0-270">Provides any error or warning messages that are returned from the process.</span></span>  
  
     <span data-ttu-id="1b4b0-271">**Report**</span><span class="sxs-lookup"><span data-stu-id="1b4b0-271">**Report**</span></span>  
     <span data-ttu-id="1b4b0-272">Crea un report contenente i risultati della Creazione guidata partizione.</span><span class="sxs-lookup"><span data-stu-id="1b4b0-272">Creates a report that contains the results of the Create Partition Wizard.</span></span> <span data-ttu-id="1b4b0-273">Le opzioni sono **Visualizza report**, **Salva report su file**, **Copia report negli Appunti**e **Invia report per posta elettronica**.</span><span class="sxs-lookup"><span data-stu-id="1b4b0-273">The options are **View Report**, **Save Report to File**, **Copy Report to Clipboard**, and **Send Report as Email**.</span></span>  
  
     <span data-ttu-id="1b4b0-274">**Visualizza report**</span><span class="sxs-lookup"><span data-stu-id="1b4b0-274">**View Report**</span></span>  
     <span data-ttu-id="1b4b0-275">Apre la finestra di dialogo **Visualizza report** in cui è contenuto un report di testo dello stato della Creazione guidata partizione.</span><span class="sxs-lookup"><span data-stu-id="1b4b0-275">Opens the **View Report** dialog box, which contains a text report of the progress of the Create Partition Wizard.</span></span>  
  
     <span data-ttu-id="1b4b0-276">**Salva report su file**</span><span class="sxs-lookup"><span data-stu-id="1b4b0-276">**Save Report to File**</span></span>  
     <span data-ttu-id="1b4b0-277">Apre la finestra di dialogo **Salva report con nome** .</span><span class="sxs-lookup"><span data-stu-id="1b4b0-277">Opens the **Save Report As** dialog box.</span></span>  
  
     <span data-ttu-id="1b4b0-278">**Copia report negli Appunti**</span><span class="sxs-lookup"><span data-stu-id="1b4b0-278">**Copy Report to Clipboard**</span></span>  
     <span data-ttu-id="1b4b0-279">Copia i risultati del report dello stato della procedura guidata negli Appunti.</span><span class="sxs-lookup"><span data-stu-id="1b4b0-279">Copies the results of the wizard's progress report to the Clipboard.</span></span>  
  
     <span data-ttu-id="1b4b0-280">**Invia report per posta elettronica**</span><span class="sxs-lookup"><span data-stu-id="1b4b0-280">**Send Report as Email**</span></span>  
     <span data-ttu-id="1b4b0-281">Copia i risultati del report dello stato della procedura guidata in un messaggio di posta elettronica.</span><span class="sxs-lookup"><span data-stu-id="1b4b0-281">Copies the results of the wizard's progress report into an email message.</span></span>  
  
     <span data-ttu-id="1b4b0-282">Al termine, fare clic su **Chiudi**.</span><span class="sxs-lookup"><span data-stu-id="1b4b0-282">When complete, click **Close**.</span></span>  
  
 <span data-ttu-id="1b4b0-283">Creazione guidata partizione crea la funzione e lo schema di partizione, quindi applica il partizionamento alla tabella specificata.</span><span class="sxs-lookup"><span data-stu-id="1b4b0-283">The Create Partition Wizard creates the partition function and scheme and then applies the partitioning to the specified table.</span></span> <span data-ttu-id="1b4b0-284">Per verificare il partizionamento della tabella, in Esplora oggetti fare clic con il pulsante destro del mouse sulla tabella e scegliere **Proprietà**.</span><span class="sxs-lookup"><span data-stu-id="1b4b0-284">To verify the table partitioning, in Object Explorer, right-click the table and select **Properties**.</span></span> <span data-ttu-id="1b4b0-285">Fare clic sulla pagina **Archiviazione** .</span><span class="sxs-lookup"><span data-stu-id="1b4b0-285">Click the **Storage** page.</span></span> <span data-ttu-id="1b4b0-286">Nella pagina vengono visualizzate informazioni come il nome della funzione e dello schema di partizione e il numero di partizioni.</span><span class="sxs-lookup"><span data-stu-id="1b4b0-286">The page displays information such as the name of the partition function and scheme and the number of partitions.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="1b4b0-287">Con Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="1b4b0-287">Using Transact-SQL</span></span>  
  
#### <a name="to-create-a-partitioned-table"></a><span data-ttu-id="1b4b0-288">Per creare una tabella partizionata</span><span class="sxs-lookup"><span data-stu-id="1b4b0-288">To create a partitioned table</span></span>  
  
1.  <span data-ttu-id="1b4b0-289">In **Esplora oggetti**connettersi a un'istanza del [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="1b4b0-289">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="1b4b0-290">Sulla barra Standard fare clic su **Nuova query**.</span><span class="sxs-lookup"><span data-stu-id="1b4b0-290">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="1b4b0-291">Copiare e incollare l'esempio seguente nella finestra Query, quindi fare clic su **Esegui**.</span><span class="sxs-lookup"><span data-stu-id="1b4b0-291">Copy and paste the following example into the query window and click **Execute**.</span></span> <span data-ttu-id="1b4b0-292">Nell'esempio vengono creati i nuovi filegroup, una funzione di partizione e un schema di partizione.</span><span class="sxs-lookup"><span data-stu-id="1b4b0-292">The example creates new filegroups, a partition function, and a partition scheme.</span></span> <span data-ttu-id="1b4b0-293">Una nuova tabella viene creata con lo schema di partizione specificato come percorso di archiviazione.</span><span class="sxs-lookup"><span data-stu-id="1b4b0-293">A new table is created with the partition scheme specified as the storage location.</span></span>  
  
    ```  
    USE AdventureWorks2012;  
    GO  
    -- Adds four new filegroups to the AdventureWorks2012 database  
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
  
    -- Adds one file for each filegroup.  
    ALTER DATABASE AdventureWorks2012   
    ADD FILE   
    (  
        NAME = test1dat1,  
        FILENAME = 'C:\Program Files\Microsoft SQL Server\MSSQL12.MSSQLSERVER\MSSQL\DATA\t1dat1.ndf',  
        SIZE = 5MB,  
        MAXSIZE = 100MB,  
        FILEGROWTH = 5MB  
    )  
    TO FILEGROUP test1fg;  
    ALTER DATABASE AdventureWorks2012   
    ADD FILE   
    (  
        NAME = test2dat2,  
        FILENAME = 'C:\Program Files\Microsoft SQL Server\MSSQL12.MSSQLSERVER\MSSQL\DATA\t2dat2.ndf',  
        SIZE = 5MB,  
        MAXSIZE = 100MB,  
        FILEGROWTH = 5MB  
    )  
    TO FILEGROUP test2fg;  
    GO  
    ALTER DATABASE AdventureWorks2012   
    ADD FILE   
    (  
        NAME = test3dat3,  
        FILENAME = 'C:\Program Files\Microsoft SQL Server\MSSQL12.MSSQLSERVER\MSSQL\DATA\t3dat3.ndf',  
        SIZE = 5MB,  
        MAXSIZE = 100MB,  
        FILEGROWTH = 5MB  
    )  
    TO FILEGROUP test3fg;  
    GO  
    ALTER DATABASE AdventureWorks2012   
    ADD FILE   
    (  
        NAME = test4dat4,  
        FILENAME = 'C:\Program Files\Microsoft SQL Server\MSSQL12.MSSQLSERVER\MSSQL\DATA\t4dat4.ndf',  
        SIZE = 5MB,  
        MAXSIZE = 100MB,  
        FILEGROWTH = 5MB  
    )  
    TO FILEGROUP test4fg;  
    GO  
    -- Creates a partition function called myRangePF1 that will partition a table into four partitions  
    CREATE PARTITION FUNCTION myRangePF1 (int)  
        AS RANGE LEFT FOR VALUES (1, 100, 1000) ;  
    GO  
    -- Creates a partition scheme called myRangePS1 that applies myRangePF1 to the four filegroups created above  
    CREATE PARTITION SCHEME myRangePS1  
        AS PARTITION myRangePF1  
        TO (test1fg, test2fg, test3fg, test4fg) ;  
    GO  
    -- Creates a partitioned table called PartitionTable that uses myRangePS1 to partition col1  
    CREATE TABLE PartitionTable (col1 int PRIMARY KEY, col2 char(10))  
        ON myRangePS1 (col1) ;  
    GO  
    ```  
  
#### <a name="to-determine-if-a-table-is-partitioned"></a><span data-ttu-id="1b4b0-294">Per determinare se una tabella è partizionata</span><span class="sxs-lookup"><span data-stu-id="1b4b0-294">To determine if a table is partitioned</span></span>  
  
1.  <span data-ttu-id="1b4b0-295">Tramite la query seguente vengono restituite una o più righe se la tabella `PartitionTable` è partizionata.</span><span class="sxs-lookup"><span data-stu-id="1b4b0-295">The following query returns one or more rows if the table `PartitionTable` is partitioned.</span></span> <span data-ttu-id="1b4b0-296">Se la tabella non è partizionata, non viene restituita alcuna query.</span><span class="sxs-lookup"><span data-stu-id="1b4b0-296">If the table is not partitioned, no rows are returned.</span></span>  
  
    ```  
    SELECT *   
    FROM sys.tables AS t   
    JOIN sys.indexes AS i   
        ON t.[object_id] = i.[object_id]   
        AND i.[type] IN (0,1)   
    JOIN sys.partition_schemes ps   
        ON i.data_space_id = ps.data_space_id   
    WHERE t.name = 'PartitionTable';   
    GO  
    ```  
  
#### <a name="to-determine-the-boundary-values-for-a-partitioned-table"></a><span data-ttu-id="1b4b0-297">Per determinare i valori limite per una tabella partizionata</span><span class="sxs-lookup"><span data-stu-id="1b4b0-297">To determine the boundary values for a partitioned table</span></span>  
  
1.  <span data-ttu-id="1b4b0-298">Tramite la query seguente vengono restituiti i valori limite per ogni partizione nella tabella `PartitionTable` .</span><span class="sxs-lookup"><span data-stu-id="1b4b0-298">The following query returns the boundary values for each partition in the `PartitionTable` table.</span></span>  
  
    ```  
    SELECT t.name AS TableName, i.name AS IndexName, p.partition_number, p.partition_id, i.data_space_id, f.function_id, f.type_desc, r.boundary_id, r.value AS BoundaryValue   
    FROM sys.tables AS t  
    JOIN sys.indexes AS i  
        ON t.object_id = i.object_id  
    JOIN sys.partitions AS p  
        ON i.object_id = p.object_id AND i.index_id = p.index_id   
    JOIN  sys.partition_schemes AS s   
        ON i.data_space_id = s.data_space_id  
    JOIN sys.partition_functions AS f   
        ON s.function_id = f.function_id  
    LEFT JOIN sys.partition_range_values AS r   
        ON f.function_id = r.function_id and r.boundary_id = p.partition_number  
    WHERE t.name = 'PartitionTable' AND i.type <= 1  
    ORDER BY p.partition_number;  
    ```  
  
#### <a name="to-determine-the-partition-column-for-a-partitioned-table"></a><span data-ttu-id="1b4b0-299">Per determinare la colonna di partizione per una tabella partizionata</span><span class="sxs-lookup"><span data-stu-id="1b4b0-299">To determine the partition column for a partitioned table</span></span>  
  
1.  <span data-ttu-id="1b4b0-300">Tramite la query seguente viene restituito il nome della colonna di partizionamento per la tabella.</span><span class="sxs-lookup"><span data-stu-id="1b4b0-300">The following query returns the name of the partitioning column for table.</span></span> <span data-ttu-id="1b4b0-301">`PartitionTable`.</span><span class="sxs-lookup"><span data-stu-id="1b4b0-301">`PartitionTable`.</span></span>  
  
    ```  
    SELECT   
        t.[object_id] AS ObjectID   
        , t.name AS TableName   
        , ic.column_id AS PartitioningColumnID   
        , c.name AS PartitioningColumnName   
    FROM sys.tables AS t   
    JOIN sys.indexes AS i   
        ON t.[object_id] = i.[object_id]   
        AND i.[type] <= 1 -- clustered index or a heap   
    JOIN sys.partition_schemes AS ps   
        ON ps.data_space_id = i.data_space_id   
    JOIN sys.index_columns AS ic   
        ON ic.[object_id] = i.[object_id]   
        AND ic.index_id = i.index_id   
        AND ic.partition_ordinal >= 1 -- because 0 = non-partitioning column   
    JOIN sys.columns AS c   
        ON t.[object_id] = c.[object_id]   
        AND ic.column_id = c.column_id   
    WHERE t.name = 'PartitionTable' ;   
    GO  
    ```  
  
 <span data-ttu-id="1b4b0-302">Per altre informazioni, vedere:</span><span class="sxs-lookup"><span data-stu-id="1b4b0-302">For more information, see:</span></span>  
  
-   [<span data-ttu-id="1b4b0-303">Opzioni per file e filegroup ALTER DATABASE &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="1b4b0-303">ALTER DATABASE File and Filegroup Options &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/alter-database-transact-sql-file-and-filegroup-options)  
  
-   [<span data-ttu-id="1b4b0-304">CREATE PARTITION FUNCTION &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="1b4b0-304">CREATE PARTITION FUNCTION &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/create-partition-function-transact-sql)  
  
-   [<span data-ttu-id="1b4b0-305">CREATE PARTITION SCHEME &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="1b4b0-305">CREATE PARTITION SCHEME &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/create-partition-scheme-transact-sql)  
  
-   [<span data-ttu-id="1b4b0-306">CREATE TABLE &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="1b4b0-306">CREATE TABLE &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/create-table-transact-sql)  
  
  
