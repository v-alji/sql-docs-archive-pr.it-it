---
title: Spostare un indice esistente in un filegroup diverso | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: table-view-index
ms.topic: conceptual
helpviewer_keywords:
- moving tables
- switching filegroups for index
- moving indexes
- indexes [SQL Server], moving
- filegroups [SQL Server], switching
ms.assetid: 167ebe77-487d-4ca8-9452-4b2c7d5cb96e
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: c99847dcb8d4d65272dd3660c7fd60d3efb8d951
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87637303"
---
# <a name="move-an-existing-index-to-a-different-filegroup"></a><span data-ttu-id="3b700-102">Spostare un indice esistente in un filegroup diverso</span><span class="sxs-lookup"><span data-stu-id="3b700-102">Move an Existing Index to a Different Filegroup</span></span>
  <span data-ttu-id="3b700-103">In questo argomento viene descritta la procedura per spostare un indice esistente dal relativo filegroup corrente in un filegroup diverso in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] tramite [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] o [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="3b700-103">This topic describes how to move an existing index from its current filegroup to a different filegroup in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span>  
  
 <span data-ttu-id="3b700-104">**Contenuto dell'articolo**</span><span class="sxs-lookup"><span data-stu-id="3b700-104">**In This Topic**</span></span>  
  
-   <span data-ttu-id="3b700-105">**Prima di iniziare:**</span><span class="sxs-lookup"><span data-stu-id="3b700-105">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="3b700-106">Limitazioni e restrizioni</span><span class="sxs-lookup"><span data-stu-id="3b700-106">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="3b700-107">Sicurezza</span><span class="sxs-lookup"><span data-stu-id="3b700-107">Security</span></span>](#Security)  
  
-   <span data-ttu-id="3b700-108">**Per spostare un indice esistente in un filegroup diverso tramite:**</span><span class="sxs-lookup"><span data-stu-id="3b700-108">**To move an existing index to a different filegroup, using:**</span></span>  
  
     [<span data-ttu-id="3b700-109">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="3b700-109">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="3b700-110">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="3b700-110">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="3b700-111">Prima di iniziare</span><span class="sxs-lookup"><span data-stu-id="3b700-111">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="3b700-112">Limitazioni e restrizioni</span><span class="sxs-lookup"><span data-stu-id="3b700-112">Limitations and Restrictions</span></span>  
  
-   <span data-ttu-id="3b700-113">Se una tabella presenta un indice cluster, lo spostamento di tale indice in un nuovo filegroup causa lo spostamento della tabella in tale filegroup.</span><span class="sxs-lookup"><span data-stu-id="3b700-113">If a table has a clustered index, moving the clustered index to a new filegroup moves the table to that filegroup.</span></span>  
  
-   <span data-ttu-id="3b700-114">Non è possibile spostare gli indici creati utilizzando un vincolo UNIQUE o PRIMARY KEY tramite [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)].</span><span class="sxs-lookup"><span data-stu-id="3b700-114">You cannot move indexes created using a UNIQUE or PRIMARY KEY constraint using [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)].</span></span> <span data-ttu-id="3b700-115">Per spostare questi indici, usare l'istruzione [CREATE INDEX](/sql/t-sql/statements/create-index-transact-sql) con l'opzione DROP_EXISTING=ON in [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="3b700-115">To move these indexes use the [CREATE INDEX](/sql/t-sql/statements/create-index-transact-sql) statement with the (DROP_EXISTING=ON) option in [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="3b700-116">Sicurezza</span><span class="sxs-lookup"><span data-stu-id="3b700-116">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="3b700-117">Autorizzazioni</span><span class="sxs-lookup"><span data-stu-id="3b700-117">Permissions</span></span>  
 <span data-ttu-id="3b700-118">È richiesta l'autorizzazione ALTER per la tabella o la vista.</span><span class="sxs-lookup"><span data-stu-id="3b700-118">Requires ALTER permission on the table or view.</span></span> <span data-ttu-id="3b700-119">L'utente deve essere un membro del ruolo predefinito del server **sysadmin** o dei ruoli predefiniti del database **db_ddladmin** e **db_owner** .</span><span class="sxs-lookup"><span data-stu-id="3b700-119">User must be a member of the **sysadmin** fixed server role or the **db_ddladmin** and **db_owner** fixed database roles.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="3b700-120">Con SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="3b700-120">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-move-an-existing-index-to-a-different-filegroup-using-table-designer"></a><span data-ttu-id="3b700-121">Per spostare un indice esistente in un filegroup diverso tramite Progettazione tabelle</span><span class="sxs-lookup"><span data-stu-id="3b700-121">To move an existing index to a different filegroup using Table Designer</span></span>  
  
1.  <span data-ttu-id="3b700-122">In Esplora oggetti fare clic sul segno più per espandere il database contenente la tabella che contiene l'indice da spostare.</span><span class="sxs-lookup"><span data-stu-id="3b700-122">In Object Explorer, click the plus sign to expand the database that contains the table containing the index that you want to move.</span></span>  
  
2.  <span data-ttu-id="3b700-123">Fare clic sul segno più per espandere la cartella **Tabelle** .</span><span class="sxs-lookup"><span data-stu-id="3b700-123">Click the plus sign to expand the **Tables** folder.</span></span>  
  
3.  <span data-ttu-id="3b700-124">Fare clic con il pulsante destro del mouse sulla tabella contenente l'indice da spostare e selezionare **Progetta**.</span><span class="sxs-lookup"><span data-stu-id="3b700-124">Right-click the table containing the index that you want to move and select **Design**.</span></span>  
  
4.  <span data-ttu-id="3b700-125">Scegliere **Indici/chiavi** nel menu **Progettazione tabelle**.</span><span class="sxs-lookup"><span data-stu-id="3b700-125">On the **Table Designer** menu, click **Indexes/Keys**.</span></span>  
  
5.  <span data-ttu-id="3b700-126">Selezionare l'indice che si desidera spostare.</span><span class="sxs-lookup"><span data-stu-id="3b700-126">Select the index that you want to move.</span></span>  
  
6.  <span data-ttu-id="3b700-127">Nella griglia principale espandere **Specifica spazio dei dati**.</span><span class="sxs-lookup"><span data-stu-id="3b700-127">In the main grid, expand **Data Space Specification**.</span></span>  
  
7.  <span data-ttu-id="3b700-128">Selezionare **Nome filegroup o schema di partizione** e selezionare dall'elenco il filegroup o lo schema di partizione in cui si desidera spostare l'indice.</span><span class="sxs-lookup"><span data-stu-id="3b700-128">Select **Filegroup or Partition Scheme Name** and select from the list the filegroup or partition scheme to where you want to move the index.</span></span>  
  
8.  <span data-ttu-id="3b700-129">Fare clic su **Close**.</span><span class="sxs-lookup"><span data-stu-id="3b700-129">Click **Close**.</span></span>  
  
9. <span data-ttu-id="3b700-130">Selezionare **Salva** table_name **dal menu**_File_.</span><span class="sxs-lookup"><span data-stu-id="3b700-130">On the **File** menu, select **Save**_table_name_.</span></span>  
  
#### <a name="to-move-an-existing-index-to-a-different-filegroup-in-object-explorer"></a><span data-ttu-id="3b700-131">Per spostare un indice esistente in un filegroup diverso in Esplora oggetti</span><span class="sxs-lookup"><span data-stu-id="3b700-131">To move an existing index to a different filegroup in Object Explorer</span></span>  
  
1.  <span data-ttu-id="3b700-132">In Esplora oggetti fare clic sul segno più per espandere il database contenente la tabella che contiene l'indice da spostare.</span><span class="sxs-lookup"><span data-stu-id="3b700-132">In Object Explorer, click the plus sign to expand the database that contains the table containing the index that you want to move.</span></span>  
  
2.  <span data-ttu-id="3b700-133">Fare clic sul segno più per espandere la cartella **Tabelle** .</span><span class="sxs-lookup"><span data-stu-id="3b700-133">Click the plus sign to expand the **Tables** folder.</span></span>  
  
3.  <span data-ttu-id="3b700-134">Fare clic sul segno più per espandere la tabella contenente l'indice da spostare.</span><span class="sxs-lookup"><span data-stu-id="3b700-134">Click the plus sign to expand the table containing the index that you want to move.</span></span>  
  
4.  <span data-ttu-id="3b700-135">Fare clic sul segno più per espandere la cartella **Indici** .</span><span class="sxs-lookup"><span data-stu-id="3b700-135">Click the plus sign to expand the **Indexes** folder.</span></span>  
  
5.  <span data-ttu-id="3b700-136">Fare clic con il pulsante destro del mouse sull'indice da spostare e selezionare **Proprietà**.</span><span class="sxs-lookup"><span data-stu-id="3b700-136">Right-click the index that you want to move and select **Properties**.</span></span>  
  
6.  <span data-ttu-id="3b700-137">In **Selezione pagina**selezionare **Archiviazione**.</span><span class="sxs-lookup"><span data-stu-id="3b700-137">Under **Select a page**, select **Storage**.</span></span>  
  
7.  <span data-ttu-id="3b700-138">Selezionare il filegroup in cui si desidera spostare l'indice.</span><span class="sxs-lookup"><span data-stu-id="3b700-138">Select the filegroup in which to move the index.</span></span>  
  
     <span data-ttu-id="3b700-139">Se la tabella o l'indice è partizionato, selezionare lo schema di partizione in cui si desidera spostare l'indice.</span><span class="sxs-lookup"><span data-stu-id="3b700-139">If the table or index is partitioned, select the partition scheme in which to move the index.</span></span> <span data-ttu-id="3b700-140">Per ulteriori informazioni sugli indici partizionati, vedere [Partitioned Tables and Indexes](../partitions/partitioned-tables-and-indexes.md).</span><span class="sxs-lookup"><span data-stu-id="3b700-140">For more information about partitioned indexes, see [Partitioned Tables and Indexes](../partitions/partitioned-tables-and-indexes.md).</span></span>  
  
     <span data-ttu-id="3b700-141">Per spostare un indice cluster, è possibile utilizzare l'elaborazione online.</span><span class="sxs-lookup"><span data-stu-id="3b700-141">If you are moving a clustered index, you can use online processing.</span></span> <span data-ttu-id="3b700-142">L'elaborazione online consente l'accesso simultaneo degli utenti ai dati sottostanti e agli indici non cluster durante l'operazione sull'indice.</span><span class="sxs-lookup"><span data-stu-id="3b700-142">Online processing allows concurrent user access to the underlying data and to nonclustered indexes during the index operation.</span></span> <span data-ttu-id="3b700-143">Per altre informazioni, vedere [Perform Index Operations Online](perform-index-operations-online.md).</span><span class="sxs-lookup"><span data-stu-id="3b700-143">For more information, see [Perform Index Operations Online](perform-index-operations-online.md).</span></span>  
  
     <span data-ttu-id="3b700-144">Nei computer multiprocessore che utilizzano [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)]è possibile configurare il numero di processori utilizzati per l'esecuzione dell'istruzione dell'indice specificando il valore massimo per il grado di parallelismo.</span><span class="sxs-lookup"><span data-stu-id="3b700-144">On multiprocessor computers using [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)], you can configure the number of processors used to execute the index statement by specifying a maximum degree of parallelism value.</span></span> <span data-ttu-id="3b700-145">La funzionalità Operazioni indicizzate parallele non è disponibile in tutte le edizioni di [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="3b700-145">The Parallel indexed operations feature is not available in every edition of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="3b700-146">Per un elenco delle funzionalità supportate dalle edizioni di [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)], vedere [Features Supported by the Editions of SQL Server 2014](../../getting-started/features-supported-by-the-editions-of-sql-server-2014.md).</span><span class="sxs-lookup"><span data-stu-id="3b700-146">For a list of features that are supported by the editions of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)], see [Features Supported by the Editions of SQL Server 2014](../../getting-started/features-supported-by-the-editions-of-sql-server-2014.md).</span></span> <span data-ttu-id="3b700-147">Per altre informazioni sulle operazioni indicizzate parallele, vedere [Configurazione di operazioni parallele sugli indici](configure-parallel-index-operations.md).</span><span class="sxs-lookup"><span data-stu-id="3b700-147">For more information about Parallel indexed operations, see [Configure Parallel Index Operations](configure-parallel-index-operations.md).</span></span>  
  
8.  <span data-ttu-id="3b700-148">Fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="3b700-148">Click **OK**.</span></span>  
  
 <span data-ttu-id="3b700-149">Le informazioni seguenti sono disponibili nella pagina **Archiviazione** della finestra di dialogo **Proprietà indice -** _nome_indice_:</span><span class="sxs-lookup"><span data-stu-id="3b700-149">The following information is available on the **Storage** page of the **Index Properties -** _index_name_ dialog box:</span></span>  
  
 <span data-ttu-id="3b700-150">**Filegroup**</span><span class="sxs-lookup"><span data-stu-id="3b700-150">**Filegroup**</span></span>  
 <span data-ttu-id="3b700-151">Archivia l'indice nel filegroup specificato.</span><span class="sxs-lookup"><span data-stu-id="3b700-151">Stores the index in the specified filegroup.</span></span> <span data-ttu-id="3b700-152">Nell'elenco sono visualizzati solo filegroup standard (ROW).</span><span class="sxs-lookup"><span data-stu-id="3b700-152">The list only displays standard (row) filegroups.</span></span> <span data-ttu-id="3b700-153">La selezione predefinita nell'elenco è il filegroup PRIMARY del database.</span><span class="sxs-lookup"><span data-stu-id="3b700-153">The default list selection is the PRIMARY filegroup of the database.</span></span>  
  
 <span data-ttu-id="3b700-154">**Filegroup FILESTREAM**</span><span class="sxs-lookup"><span data-stu-id="3b700-154">**Filestream filegroup**</span></span>  
 <span data-ttu-id="3b700-155">Specifica il filegroup per i dati FILESTREAM.</span><span class="sxs-lookup"><span data-stu-id="3b700-155">Specifies the filegroup for FILESTREAM data.</span></span> <span data-ttu-id="3b700-156">Questo elenco visualizza solo i filegroup FILESTREAM.</span><span class="sxs-lookup"><span data-stu-id="3b700-156">This list displays only FILESTREAM filegroups.</span></span> <span data-ttu-id="3b700-157">La selezione predefinita nell'elenco è il filegroup PRIMARY FILESTREAM del database.</span><span class="sxs-lookup"><span data-stu-id="3b700-157">The default list selection is the PRIMARY FILESTREAM filegroup.</span></span>  
  
 <span data-ttu-id="3b700-158">**Schema di partizione**</span><span class="sxs-lookup"><span data-stu-id="3b700-158">**Partition scheme**</span></span>  
 <span data-ttu-id="3b700-159">Archivia l'indice in uno schema di partizione.</span><span class="sxs-lookup"><span data-stu-id="3b700-159">Stores the index in a partition scheme.</span></span> <span data-ttu-id="3b700-160">Facendo clic su **Schema partizione** si abilita la griglia sottostante.</span><span class="sxs-lookup"><span data-stu-id="3b700-160">Clicking **Partition Scheme** enables the grid below.</span></span> <span data-ttu-id="3b700-161">La selezione predefinita nell'elenco è lo schema di partizione usato per archiviare i dati di tabella.</span><span class="sxs-lookup"><span data-stu-id="3b700-161">The default list selection is the partition scheme that is used for storing the table data.</span></span> <span data-ttu-id="3b700-162">Selezionando uno schema di partizione diverso nell'elenco si aggiornano le informazioni visualizzate nella griglia.</span><span class="sxs-lookup"><span data-stu-id="3b700-162">When you select a different partition scheme in the list, the information in the grid is updated.</span></span>  
  
 <span data-ttu-id="3b700-163">L'opzione relativa allo schema di partizione non è disponibile se il database non contiene schemi di partizione.</span><span class="sxs-lookup"><span data-stu-id="3b700-163">The partition scheme option is unavailable if there are no partition schemes in the database.</span></span>  
  
 <span data-ttu-id="3b700-164">**Schema di partizione FILESTREAM**</span><span class="sxs-lookup"><span data-stu-id="3b700-164">**Filestream partition scheme**</span></span>  
 <span data-ttu-id="3b700-165">Specifica lo schema di partizione per i dati FILESTREAM.</span><span class="sxs-lookup"><span data-stu-id="3b700-165">Specifies the partition scheme for FILESTREAM data.</span></span> <span data-ttu-id="3b700-166">Lo schema di partizione deve essere simmetrico con la combinazione specificata nell'opzione **Schema partizione** .</span><span class="sxs-lookup"><span data-stu-id="3b700-166">The partition scheme must be symmetric with the scheme that is specified in the **Partition scheme** option.</span></span>  
  
 <span data-ttu-id="3b700-167">Se la tabella non è partizionata, il campo è vuoto.</span><span class="sxs-lookup"><span data-stu-id="3b700-167">If the table is not partitioned, the field is blank.</span></span>  
  
 <span data-ttu-id="3b700-168">**Parametro schema partizione**</span><span class="sxs-lookup"><span data-stu-id="3b700-168">**Partition Scheme Parameter**</span></span>  
 <span data-ttu-id="3b700-169">Consente di visualizzare il nome della colonna che partecipa allo schema di partizione.</span><span class="sxs-lookup"><span data-stu-id="3b700-169">Displays the name of the column that participates in the partition scheme.</span></span>  
  
 <span data-ttu-id="3b700-170">**Colonne della tabella**</span><span class="sxs-lookup"><span data-stu-id="3b700-170">**Table Column**</span></span>  
 <span data-ttu-id="3b700-171">Consente di selezionare la tabella o la vista su cui eseguire il mapping allo schema di partizione.</span><span class="sxs-lookup"><span data-stu-id="3b700-171">Select the table or view to map to the partition scheme.</span></span>  
  
 <span data-ttu-id="3b700-172">**Tipo di dati colonna**</span><span class="sxs-lookup"><span data-stu-id="3b700-172">**Column Data Type**</span></span>  
 <span data-ttu-id="3b700-173">Consente di visualizzare le informazioni sul tipo di dati relative alla colonna.</span><span class="sxs-lookup"><span data-stu-id="3b700-173">Displays data type information about the column.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="3b700-174">Se la colonna della tabella è una colonna calcolata, l'opzione **Tipo di dati colonna** visualizza "colonna calcolata".</span><span class="sxs-lookup"><span data-stu-id="3b700-174">If the table column is a computed column, **Column Data Type** displays "computed column."</span></span>  
  
 <span data-ttu-id="3b700-175">**Consenti elaborazione online di istruzioni DML durante lo spostamento dell'indice**</span><span class="sxs-lookup"><span data-stu-id="3b700-175">**Allow online processing of DML statements while moving the index**</span></span>  
 <span data-ttu-id="3b700-176">Consente agli utenti di accedere ai dati della tabella o dell'indice cluster sottostanti e a eventuali indici non cluster associati durante l'operazione sull'indice.</span><span class="sxs-lookup"><span data-stu-id="3b700-176">Allows users to access the underlying table or clustered index data and any associated nonclustered indexes during the index operation.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="3b700-177">Questa opzione non è disponibile per gli indici XML o se l'indice è un indice cluster disabilitato.</span><span class="sxs-lookup"><span data-stu-id="3b700-177">This option is not available for XML indexes, or if the index is a disabled clustered index.</span></span>  
  
 <span data-ttu-id="3b700-178">**Imposta massimo grado di parallelismo**</span><span class="sxs-lookup"><span data-stu-id="3b700-178">**Set maximum degree of parallelism**</span></span>  
 <span data-ttu-id="3b700-179">Consente di limitare il numero di processori da usare durante l'esecuzione di piani paralleli.</span><span class="sxs-lookup"><span data-stu-id="3b700-179">Limits the number of processors to use during parallel plan execution.</span></span> <span data-ttu-id="3b700-180">Il valore predefinito è 0 e corrisponde al numero effettivo di CPU disponibili.</span><span class="sxs-lookup"><span data-stu-id="3b700-180">The default value, 0, uses the actual number of available CPUs.</span></span> <span data-ttu-id="3b700-181">L'impostazione del valore su 1 impedisce la generazione di piani paralleli. L'impostazione del valore su un numero maggiore di 1 limita il numero massimo di processori usati da una singola esecuzione della query.</span><span class="sxs-lookup"><span data-stu-id="3b700-181">Setting the value to 1 suppresses parallel plan generation; setting the value to a number greater than 1 restricts the maximum number of processors used by a single query execution.</span></span> <span data-ttu-id="3b700-182">Questa opzione diventa disponibile solo se la finestra di dialogo è nello stato **Ricompila** o **Ricrea** .</span><span class="sxs-lookup"><span data-stu-id="3b700-182">This option only becomes available if the dialog box is in the **Rebuild** or **Recreate** state.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="3b700-183">Se viene specificato un valore maggiore del numero di CPU disponibili, verrà usato l'effettivo numero di CPU disponibili.</span><span class="sxs-lookup"><span data-stu-id="3b700-183">If a value greater than the number of available CPUs is specified, the actual number of available CPUs is used.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="3b700-184">Con Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="3b700-184">Using Transact-SQL</span></span>  
  
#### <a name="to-move-an-existing-index-to-a-different-filegroup"></a><span data-ttu-id="3b700-185">Per spostare un indice esistente in un filegroup diverso</span><span class="sxs-lookup"><span data-stu-id="3b700-185">To move an existing index to a different filegroup</span></span>  
  
1.  <span data-ttu-id="3b700-186">In **Esplora oggetti**connettersi a un'istanza del [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="3b700-186">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="3b700-187">Sulla barra Standard fare clic su **Nuova query**.</span><span class="sxs-lookup"><span data-stu-id="3b700-187">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="3b700-188">Copiare e incollare l'esempio seguente nella finestra Query, quindi fare clic su **Esegui**.</span><span class="sxs-lookup"><span data-stu-id="3b700-188">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```  
    USE AdventureWorks2012;  
    GO  
    -- Creates the TransactionsFG1 filegroup on the AdventureWorks2012 database  
    ALTER DATABASE AdventureWorks2012  
    ADD FILEGROUP TransactionsFG1;  
    GO  
    /* Adds the TransactionsFG1dat3 file to the TransactionsFG1 filegroup. Please note that you will have to change the filename parameter in this statement to execute it without errors.  
    */  
    ALTER DATABASE AdventureWorks2012   
    ADD FILE   
    (  
        NAME = TransactionsFG1dat3,  
        FILENAME = 'C:\Program Files\Microsoft SQL Server\MSSQL12\MSSQL\DATA\TransactionsFG1dat3.ndf',  
        SIZE = 5MB,  
        MAXSIZE = 100MB,  
        FILEGROWTH = 5MB  
    )  
    TO FILEGROUP TransactionsFG1;  
    GO  
    /*Creates the IX_Employee_OrganizationLevel_OrganizationNode index  
      on the TransactionsPS1 filegroup and drops the original IX_Employee_OrganizationLevel_OrganizationNode index.  
    */  
    CREATE NONCLUSTERED INDEX IX_Employee_OrganizationLevel_OrganizationNode  
        ON HumanResources.Employee (OrganizationLevel, OrganizationNode)  
        WITH (DROP_EXISTING = ON)  
        ON TransactionsFG1;  
    GO  
    ```  
  
 <span data-ttu-id="3b700-189">Per altre informazioni, vedere [CREATE INDEX &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-index-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="3b700-189">For more information, see [CREATE INDEX &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-index-transact-sql).</span></span>  
  
  
