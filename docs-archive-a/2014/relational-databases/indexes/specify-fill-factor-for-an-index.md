---
title: Specificare un fattore di riempimento per un indice | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: table-view-index
ms.topic: conceptual
helpviewer_keywords:
- fill factor [SQL Server]
- page splits [SQL Server]
ms.assetid: 237a577e-b42b-4adb-90cf-aa7fb174f3ab
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: ac54f2b22de55ed74c4635ec0f86d008c7624a42
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87723840"
---
# <a name="specify-fill-factor-for-an-index"></a><span data-ttu-id="291f4-102">Specificare un fattore di riempimento per un indice</span><span class="sxs-lookup"><span data-stu-id="291f4-102">Specify Fill Factor for an Index</span></span>
  <span data-ttu-id="291f4-103">In questo argomento si descrive il fattore di riempimento e come specificare un valore del fattore di riempimento in un indice in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] tramite [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] o [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="291f4-103">This topic describes what fill factor is and how to specify a fill factor value on an index in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span>  
  
 <span data-ttu-id="291f4-104">L'opzione del fattore di riempimento viene fornita per ottimizzare l'archiviazione dati e le prestazioni degli indici.</span><span class="sxs-lookup"><span data-stu-id="291f4-104">The fill-factor option is provided for fine-tuning index data storage and performance.</span></span> <span data-ttu-id="291f4-105">Quando si crea o si ricompila un indice, il valore del fattore di riempimento determina la percentuale di spazio in ogni pagina al livello foglia da riempire di dati, riservando lo spazio rimanente in ogni pagina come spazio libero per la crescita futura.</span><span class="sxs-lookup"><span data-stu-id="291f4-105">When an index is created or rebuilt, the fill-factor value determines the percentage of space on each leaf-level page to be filled with data, reserving the remainder on each page as free space for future growth.</span></span> <span data-ttu-id="291f4-106">Se ad esempio si specifica un fattore di riempimento pari a 80, significa che il 20% di ogni pagina al livello foglia verrà lasciato vuoto, rendendo disponibile lo spazio per l'espansione dell'indice con l'aggiunta di dati alla tabella sottostante.</span><span class="sxs-lookup"><span data-stu-id="291f4-106">For example, specifying a fill-factor value of 80 means that 20 percent of each leaf-level page will be left empty, providing space for index expansion as data is added to the underlying table.</span></span> <span data-ttu-id="291f4-107">Lo spazio vuoto viene riservato tra le righe anziché alla fine dell'indice.</span><span class="sxs-lookup"><span data-stu-id="291f4-107">The empty space is reserved between the index rows rather than at the end of the index.</span></span>  
  
 <span data-ttu-id="291f4-108">Il valore del fattore di riempimento è una percentuale compresa tra 1 e 100 e l'impostazione predefinita a livello di server è 0. Questo significa che le pagine al livello foglia vengono riempite completamente.</span><span class="sxs-lookup"><span data-stu-id="291f4-108">The fill-factor value is a percentage from 1 to 100, and the server-wide default is 0 which means that the leaf-level pages are filled to capacity.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="291f4-109">I valori 0 e 100 del fattore di riempimento sono equivalenti.</span><span class="sxs-lookup"><span data-stu-id="291f4-109">Fill-factor values 0 and 100 are the same in all respects.</span></span>  
  
 <span data-ttu-id="291f4-110">**Contenuto dell'articolo**</span><span class="sxs-lookup"><span data-stu-id="291f4-110">**In This Topic**</span></span>  
  
-   <span data-ttu-id="291f4-111">**Prima di iniziare:**</span><span class="sxs-lookup"><span data-stu-id="291f4-111">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="291f4-112">Considerazioni sulle prestazioni</span><span class="sxs-lookup"><span data-stu-id="291f4-112">Performance Considerations</span></span>](#Performance)  
  
     [<span data-ttu-id="291f4-113">Sicurezza</span><span class="sxs-lookup"><span data-stu-id="291f4-113">Security</span></span>](#Security)  
  
-   <span data-ttu-id="291f4-114">**Per specificare un fattore di riempimento in un indice tramite:**</span><span class="sxs-lookup"><span data-stu-id="291f4-114">**To specify a fill factor in an index, using:**</span></span>  
  
     [<span data-ttu-id="291f4-115">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="291f4-115">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="291f4-116">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="291f4-116">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="291f4-117">Prima di iniziare</span><span class="sxs-lookup"><span data-stu-id="291f4-117">Before You Begin</span></span>  
  
###  <a name="performance-considerations"></a><a name="Performance"></a> <span data-ttu-id="291f4-118">Considerazioni sulle prestazioni</span><span class="sxs-lookup"><span data-stu-id="291f4-118">Performance Considerations</span></span>  
  
#### <a name="page-splits"></a><span data-ttu-id="291f4-119">Divisioni di pagina</span><span class="sxs-lookup"><span data-stu-id="291f4-119">Page Splits</span></span>  
 <span data-ttu-id="291f4-120">Un valore del fattore di riempimento scelto correttamente consente di ridurre le potenziali divisioni di pagina rendendo disponibile uno spazio sufficiente per l'espansione dell'indice durante l'aggiunta di dati alla tabella sottostante. Quando viene aggiunta una nuova riga a una pagina di indice completa, tramite il [!INCLUDE[ssDE](../../includes/ssde-md.md)] viene spostata circa la metà delle righe in una nuova pagina per lasciare spazio per la nuova riga.</span><span class="sxs-lookup"><span data-stu-id="291f4-120">A correctly chosen fill-factor value can reduce potential page splits by providing enough space for index expansion as data is added to the underlying table.When a new row is added to a full index page, the [!INCLUDE[ssDE](../../includes/ssde-md.md)] moves approximately half the rows to a new page to make room for the new row.</span></span> <span data-ttu-id="291f4-121">Questa riorganizzazione è nota come divisione di pagina.</span><span class="sxs-lookup"><span data-stu-id="291f4-121">This reorganization is known as a page split.</span></span> <span data-ttu-id="291f4-122">Una divisione di pagina consente di creare spazio per nuovi record, ma può richiedere una certa quantità di tempo e un elevato utilizzo di risorse.</span><span class="sxs-lookup"><span data-stu-id="291f4-122">A page split makes room for new records, but can take time to perform and is a resource intensive operation.</span></span> <span data-ttu-id="291f4-123">Può inoltre provocare la frammentazione, che a sua volta causa l'aumento delle operazioni di I/O.</span><span class="sxs-lookup"><span data-stu-id="291f4-123">Also, it can cause fragmentation that causes increased I/O operations.</span></span> <span data-ttu-id="291f4-124">Quando si verificano frequenti divisioni di pagina, l'indice può essere ricompilato utilizzando un valore del fattore di riempimento nuovo o esistente per ridistribuire i dati.</span><span class="sxs-lookup"><span data-stu-id="291f4-124">When frequent page splits occur, the index can be rebuilt by using a new or existing fill-factor value to redistribute the data.</span></span> <span data-ttu-id="291f4-125">Per altre informazioni, vedere [Riorganizzare e ricompilare gli indici](reorganize-and-rebuild-indexes.md).</span><span class="sxs-lookup"><span data-stu-id="291f4-125">For more information, see [Reorganize and Rebuild Indexes](reorganize-and-rebuild-indexes.md).</span></span>  
  
 <span data-ttu-id="291f4-126">Benché un valore del fattore di riempimento basso e diverso da 0 può ridurre la necessità di dividere le pagine con l'aumento delle dimensioni dell'indice, l'indice richiederà uno spazio di archiviazione maggiore, con possibili effetti negativi sulle prestazioni di lettura.</span><span class="sxs-lookup"><span data-stu-id="291f4-126">Although a low, nonzero fill-factor value may reduce the requirement to split pages as the index grows, the index will require more storage space and can decrease read performance.</span></span> <span data-ttu-id="291f4-127">Anche per un'applicazione progettata per il supporto di numerose operazioni di inserimento e aggiornamento, il numero di letture nel database è in genere maggiore del numero di scritture in base a un fattore di 5 a 11.</span><span class="sxs-lookup"><span data-stu-id="291f4-127">Even for an application oriented for many insert and update operations, the number of database reads typically outnumber database writes by a factor of 5 to 10.</span></span> <span data-ttu-id="291f4-128">Se pertanto si specifica un fattore di riempimento diverso dal valore predefinito, è possibile che le prestazioni di lettura del database risultino ridotte in misura inversamente proporzionale all'impostazione del fattore di riempimento.</span><span class="sxs-lookup"><span data-stu-id="291f4-128">Therefore, specifying a fill factor other than the default can decrease database read performance by an amount inversely proportional to the fill-factor setting.</span></span> <span data-ttu-id="291f4-129">Un valore del fattore di riempimento pari a 50 può ad esempio dimezzare le prestazioni di lettura del database.</span><span class="sxs-lookup"><span data-stu-id="291f4-129">For example, a fill-factor value of 50 can cause database read performance to decrease by two times.</span></span> <span data-ttu-id="291f4-130">Ciò avviene perché l'indice contiene più pagine, aumentando pertanto le operazioni di I/O su disco necessarie per recuperare i dati.</span><span class="sxs-lookup"><span data-stu-id="291f4-130">Read performance is decreased because the index contains more pages, therefore increasing the disk IO operations required to retrieve the data.</span></span>  
  
#### <a name="adding-data-to-the-end-of-the-table"></a><span data-ttu-id="291f4-131">Aggiunta di dati alla fine della tabella</span><span class="sxs-lookup"><span data-stu-id="291f4-131">Adding Data to the End of the Table</span></span>  
 <span data-ttu-id="291f4-132">Un valore del fattore di riempimento diverso da 0 o 100 può risultare efficace per le prestazioni se i nuovi dati vengono distribuiti uniformemente in tutta la tabella.</span><span class="sxs-lookup"><span data-stu-id="291f4-132">A nonzero fill factor other than 0 or 100 can be good for performance if the new data is evenly distributed throughout the table.</span></span> <span data-ttu-id="291f4-133">Se tuttavia tutti i dati vengono aggiunti alla fine della tabella, lo spazio vuoto nelle pagine di indice non verrà riempito.</span><span class="sxs-lookup"><span data-stu-id="291f4-133">However, if all the data is added to the end of the table, the empty space in the index pages will not be filled.</span></span> <span data-ttu-id="291f4-134">Se ad esempio la colonna chiave dell'indice è una colonna IDENTITY, la chiave per le nuove righe aumenta di continuo e le righe di indice vengono aggiunte logicamente alla fine dell'indice.</span><span class="sxs-lookup"><span data-stu-id="291f4-134">For example, if the index key column is an IDENTITY column, the key for new rows is always increasing and the index rows are logically added to the end of the index.</span></span> <span data-ttu-id="291f4-135">Se le righe esistenti verranno aggiornate con dati che ne aumentano le dimensioni, utilizzare un fattore di riempimento minore di 100.</span><span class="sxs-lookup"><span data-stu-id="291f4-135">If existing rows will be updated with data that lengthens the size of the rows, use a fill factor of less than 100.</span></span> <span data-ttu-id="291f4-136">I byte aggiuntivi in ogni pagina consentiranno di ridurre le divisioni di pagina causate dalla maggiore lunghezza delle righe.</span><span class="sxs-lookup"><span data-stu-id="291f4-136">The extra bytes on each page will help to minimize page splits caused by extra length in the rows.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="291f4-137">Sicurezza</span><span class="sxs-lookup"><span data-stu-id="291f4-137">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="291f4-138">Autorizzazioni</span><span class="sxs-lookup"><span data-stu-id="291f4-138">Permissions</span></span>  
 <span data-ttu-id="291f4-139">È richiesta l'autorizzazione ALTER per la tabella o la vista.</span><span class="sxs-lookup"><span data-stu-id="291f4-139">Requires ALTER permission on the table or view.</span></span> <span data-ttu-id="291f4-140">L'utente deve essere un membro del ruolo predefinito del server **sysadmin** o dei ruoli predefiniti del database **db_ddladmin** e **db_owner** .</span><span class="sxs-lookup"><span data-stu-id="291f4-140">User must be a member of the **sysadmin** fixed server role or the **db_ddladmin** and **db_owner** fixed database roles.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="291f4-141">Con SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="291f4-141">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-specify-a-fill-factor-by-using-table-designer"></a><span data-ttu-id="291f4-142">Per specificare un fattore di riempimento tramite Progettazione tabelle</span><span class="sxs-lookup"><span data-stu-id="291f4-142">To specify a fill factor by using Table Designer</span></span>  
  
1.  <span data-ttu-id="291f4-143">In Esplora oggetti fare clic sul segno più per espandere il database contenente la tabella in cui si vuole specificare il fattore di riempimento di un indice.</span><span class="sxs-lookup"><span data-stu-id="291f4-143">In Object Explorer, click the plus sign to expand the database that contains the table on which you want to specify an index's fill factor.</span></span>  
  
2.  <span data-ttu-id="291f4-144">Fare clic sul segno più per espandere la cartella **Tabelle** .</span><span class="sxs-lookup"><span data-stu-id="291f4-144">Click the plus sign to expand the **Tables** folder.</span></span>  
  
3.  <span data-ttu-id="291f4-145">Fare clic con il pulsante destro del mouse sulla tabella in cui si vuole specificare il fattore di riempimento di un indice e selezionare **Progettazione**.</span><span class="sxs-lookup"><span data-stu-id="291f4-145">Right-click the table on which you want to specify an index's fill factor and select **Design**.</span></span>  
  
4.  <span data-ttu-id="291f4-146">Scegliere **Indici/chiavi** nel menu **Progettazione tabelle**.</span><span class="sxs-lookup"><span data-stu-id="291f4-146">On the **Table Designer** menu, click **Indexes/Keys**.</span></span>  
  
5.  <span data-ttu-id="291f4-147">Selezionare l'indice con il fattore di riempimento che si desidera specificare.</span><span class="sxs-lookup"><span data-stu-id="291f4-147">Select the index with the fill factor that you want to specify.</span></span>  
  
6.  <span data-ttu-id="291f4-148">Espandere **Specifica riempimento**, selezionare la riga **Fattore di riempimento** e immettere il fattore di riempimento desiderato nella riga.</span><span class="sxs-lookup"><span data-stu-id="291f4-148">Expand **Fill Specification**, select the **Fill Factor** row and enter the fill factor you want in the row.</span></span>  
  
7.  <span data-ttu-id="291f4-149">Fare clic su **Close**.</span><span class="sxs-lookup"><span data-stu-id="291f4-149">Click **Close**.</span></span>  
  
8.  <span data-ttu-id="291f4-150">Selezionare **Salva** table_name **dal menu**_File_.</span><span class="sxs-lookup"><span data-stu-id="291f4-150">On the **File** menu, select **Save**_table_name_.</span></span>  
  
#### <a name="to-specify-a-fill-factor-in-an-index-by-using-object-explorer"></a><span data-ttu-id="291f4-151">Per specificare un fattore di riempimento in un indice tramite Esplora oggetti</span><span class="sxs-lookup"><span data-stu-id="291f4-151">To specify a fill factor in an index by using Object Explorer</span></span>  
  
1.  <span data-ttu-id="291f4-152">In Esplora oggetti fare clic sul segno più per espandere il database contenente la tabella in cui si vuole specificare il fattore di riempimento di un indice.</span><span class="sxs-lookup"><span data-stu-id="291f4-152">In Object Explorer, click the plus sign to expand the database that contains the table on which you want to specify an index's fill factor.</span></span>  
  
2.  <span data-ttu-id="291f4-153">Fare clic sul segno più per espandere la cartella **Tabelle** .</span><span class="sxs-lookup"><span data-stu-id="291f4-153">Click the plus sign to expand the **Tables** folder.</span></span>  
  
3.  <span data-ttu-id="291f4-154">Fare clic sul segno più per espandere la tabella in cui si vuole specificare il fattore di riempimento di un indice.</span><span class="sxs-lookup"><span data-stu-id="291f4-154">Click the plus sign to expand the table on which you want to specify an index's fill factor.</span></span>  
  
4.  <span data-ttu-id="291f4-155">Fare clic sul segno più per espandere la cartella **Indici** .</span><span class="sxs-lookup"><span data-stu-id="291f4-155">Click the plus sign to expand the **Indexes** folder.</span></span>  
  
5.  <span data-ttu-id="291f4-156">Fare clic con il pulsante destro del mouse sull'indice con il fattore di riempimento che si vuole specificare e scegliere **Proprietà**.</span><span class="sxs-lookup"><span data-stu-id="291f4-156">Right-click the index with the fill factor that you want to specify and select **Properties**.</span></span>  
  
6.  <span data-ttu-id="291f4-157">In **Selezione pagina**selezionare **Opzioni**.</span><span class="sxs-lookup"><span data-stu-id="291f4-157">Under **Select a page**, select **Options**.</span></span>  
  
7.  <span data-ttu-id="291f4-158">Nella riga **Fattore di riempimento** immettere il fattore di riempimento desiderato.</span><span class="sxs-lookup"><span data-stu-id="291f4-158">In the **Fill factor** row, enter the fill factor that you want.</span></span>  
  
8.  <span data-ttu-id="291f4-159">Fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="291f4-159">Click **OK**.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="291f4-160">Con Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="291f4-160">Using Transact-SQL</span></span>  
  
#### <a name="to-specify-a-fill-factor-in-an-existing-index"></a><span data-ttu-id="291f4-161">Per specificare un fattore di riempimento in un indice esistente</span><span class="sxs-lookup"><span data-stu-id="291f4-161">To specify a fill factor in an existing index</span></span>  
  
1.  <span data-ttu-id="291f4-162">In **Esplora oggetti**connettersi a un'istanza del [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="291f4-162">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="291f4-163">Sulla barra Standard fare clic su **Nuova query**.</span><span class="sxs-lookup"><span data-stu-id="291f4-163">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="291f4-164">Copiare e incollare l'esempio seguente nella finestra Query, quindi fare clic su **Esegui**.</span><span class="sxs-lookup"><span data-stu-id="291f4-164">Copy and paste the following example into the query window and click **Execute**.</span></span> <span data-ttu-id="291f4-165">Nell'esempio viene ricompilato un indice esistente e viene applicato il fattore di riempimento specificato durante l'operazione di ricompilazione.</span><span class="sxs-lookup"><span data-stu-id="291f4-165">The example rebuilds an existing index and applies the specified fill factor during the rebuild operation.</span></span>  
  
    ```  
    USE AdventureWorks2012;  
    GO  
    -- Rebuilds the IX_Employee_OrganizationLevel_OrganizationNode index   
    -- with a fill factor of 80 on the HumanResources.Employee table.  
  
    ALTER INDEX IX_Employee_OrganizationLevel_OrganizationNode ON HumanResources.Employee  
    REBUILD WITH (FILLFACTOR = 80);   
    GO  
    ```  
  
#### <a name="another-way-to-specify-a-fill-factor-in-an-index"></a><span data-ttu-id="291f4-166">Modalità alternativa per specificare un fattore di riempimento in un indice</span><span class="sxs-lookup"><span data-stu-id="291f4-166">Another way to specify a fill factor in an index</span></span>  
  
1.  <span data-ttu-id="291f4-167">In **Esplora oggetti**connettersi a un'istanza del [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="291f4-167">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="291f4-168">Sulla barra Standard fare clic su **Nuova query**.</span><span class="sxs-lookup"><span data-stu-id="291f4-168">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="291f4-169">Copiare e incollare l'esempio seguente nella finestra Query, quindi fare clic su **Esegui**.</span><span class="sxs-lookup"><span data-stu-id="291f4-169">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```  
    USE AdventureWorks2012;  
    GO  
    /* Drops and re-creates the IX_Employee_OrganizationLevel_OrganizationNode index on the HumanResources.Employee table with a fill factor of 80.  
    */  
  
    CREATE INDEX IX_Employee_OrganizationLevel_OrganizationNode ON HumanResources.Employee  
       (OrganizationLevel, OrganizationNode)   
    WITH (DROP_EXISTING = ON, FILLFACTOR = 80);   
    GO  
    ```  
  
 <span data-ttu-id="291f4-170">Per altre informazioni, vedere [ALTER INDEX &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-index-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="291f4-170">For more information, see [ALTER INDEX &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-index-transact-sql).</span></span>  
  
  
