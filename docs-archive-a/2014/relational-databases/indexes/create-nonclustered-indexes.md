---
title: Creare indici non cluster | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: table-view-index
ms.topic: conceptual
helpviewer_keywords:
- index creation [SQL Server], nonclustered indexes
- nonclustered indexes [SQL Server], creating
- nonclustered indexes [SQL Server], UNIQUE constraint
- indexes [SQL Server], nonclustered
- nonclustered indexes [SQL Server], PRIMARY KEY constraint
ms.assetid: 9402029a-1227-46c4-93aa-c2122eb1b943
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: fae0c06b1f562dc3fc518a319df1787b3384c0cd
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87724616"
---
# <a name="create-nonclustered-indexes"></a><span data-ttu-id="c7625-102">Creare indici non cluster</span><span class="sxs-lookup"><span data-stu-id="c7625-102">Create Nonclustered Indexes</span></span>
  <span data-ttu-id="c7625-103">È possibile creare indici non cluster in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] utilizzando [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] o [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="c7625-103">You can create nonclustered indexes in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span> <span data-ttu-id="c7625-104">Un indice non cluster è una struttura di indice separata dai dati archiviati in una tabella che riordina una o più colonne selezionate.</span><span class="sxs-lookup"><span data-stu-id="c7625-104">A nonclustered index is an index structure separate from the data stored in a table that reorders one or more selected columns.</span></span> <span data-ttu-id="c7625-105">Spesso gli indici non cluster consentono di trovare i dati più rapidamente rispetto alla ricerca nella tabella sottostante. Le query talvolta possono ottenere risposta unicamente mediante i dati presenti nell'indice non cluster oppure l'indice non cluster può puntare il [!INCLUDE[ssDE](../../includes/ssde-md.md)] alle righe nella tabella sottostante.</span><span class="sxs-lookup"><span data-stu-id="c7625-105">Nonclustered indexes can often help you find data more quickly than searching the underlying table; queries can sometimes be answered entirely by the data in the nonclustered index, or the nonclustered index can point the [!INCLUDE[ssDE](../../includes/ssde-md.md)] to the rows in the underlying table.</span></span> <span data-ttu-id="c7625-106">Gli indici non cluster vengono creati generalmente per migliorare le prestazioni delle query di utilizzo frequente non coperte dall'indice cluster oppure per individuare le righe in una tabella senza un indice cluster (denominato heap).</span><span class="sxs-lookup"><span data-stu-id="c7625-106">Generally, nonclustered indexes are created to improve the performance of frequently used queries not covered by the clustered index or to locate rows in a table without a clustered index (called a heap).</span></span> <span data-ttu-id="c7625-107">In una vista tabella o indicizzata è possibile creare più indici non cluster.</span><span class="sxs-lookup"><span data-stu-id="c7625-107">You can create multiple nonclustered indexes on a table or indexed view.</span></span>  
  
 <span data-ttu-id="c7625-108">**Contenuto dell'articolo**</span><span class="sxs-lookup"><span data-stu-id="c7625-108">**In This Topic**</span></span>  
  
-   <span data-ttu-id="c7625-109">**Prima di iniziare:**</span><span class="sxs-lookup"><span data-stu-id="c7625-109">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="c7625-110">Implementazioni tipiche</span><span class="sxs-lookup"><span data-stu-id="c7625-110">Typical Implementations</span></span>](#Implementations)  
  
     [<span data-ttu-id="c7625-111">Sicurezza</span><span class="sxs-lookup"><span data-stu-id="c7625-111">Security</span></span>](#Security)  
  
-   <span data-ttu-id="c7625-112">**Per creare un indice non cluster tramite:**</span><span class="sxs-lookup"><span data-stu-id="c7625-112">**To create a nonclustered index, using:**</span></span>  
  
     [<span data-ttu-id="c7625-113">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="c7625-113">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="c7625-114">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="c7625-114">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="c7625-115">Prima di iniziare</span><span class="sxs-lookup"><span data-stu-id="c7625-115">Before You Begin</span></span>  
  
###  <a name="typical-implementations"></a><a name="Implementations"></a> <span data-ttu-id="c7625-116">Modalità di implementazione tipiche</span><span class="sxs-lookup"><span data-stu-id="c7625-116">Typical Implementations</span></span>  
 <span data-ttu-id="c7625-117">Gli indici non cluster vengono implementati nei modi seguenti:</span><span class="sxs-lookup"><span data-stu-id="c7625-117">Nonclustered indexes are implemented in the following ways:</span></span>  
  
-   <span data-ttu-id="c7625-118">**Vincoli UNIQUE**</span><span class="sxs-lookup"><span data-stu-id="c7625-118">**UNIQUE constraints**</span></span>  
  
     <span data-ttu-id="c7625-119">Quando si crea un vincolo UNIQUE, viene creato un indice non cluster univoco per applicare un vincolo UNIQUE per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="c7625-119">When you create a UNIQUE constraint, a unique nonclustered index is created to enforce a UNIQUE constraint by default.</span></span> <span data-ttu-id="c7625-120">È possibile specificare un indice cluster univoco se nella tabella non ne esiste già uno.</span><span class="sxs-lookup"><span data-stu-id="c7625-120">You can specify a unique clustered index if a clustered index on the table does not already exist.</span></span> <span data-ttu-id="c7625-121">Per altre informazioni, vedere [Unique Constraints and Check Constraints](../tables/unique-constraints-and-check-constraints.md).</span><span class="sxs-lookup"><span data-stu-id="c7625-121">For more information, see [Unique Constraints and Check Constraints](../tables/unique-constraints-and-check-constraints.md).</span></span>  
  
-   <span data-ttu-id="c7625-122">**Indice indipendente da un vincolo**</span><span class="sxs-lookup"><span data-stu-id="c7625-122">**Index independent of a constraint**</span></span>  
  
     <span data-ttu-id="c7625-123">Per impostazione predefinita, viene creato un indice non cluster se non è stato specificato l'indice cluster.</span><span class="sxs-lookup"><span data-stu-id="c7625-123">By default, a nonclustered index is created if clustered is not specified.</span></span> <span data-ttu-id="c7625-124">Il numero massimo di indici non cluster che è possibile creare per tabella è 999.</span><span class="sxs-lookup"><span data-stu-id="c7625-124">The maximum number of nonclustered indexes that can be created per table is 999.</span></span> <span data-ttu-id="c7625-125">Sono inclusi gli indici creati tramite i vincoli PRIMARY KEY o UNIQUE, ma non gli indici XML.</span><span class="sxs-lookup"><span data-stu-id="c7625-125">This includes any indexes created by PRIMARY KEY or UNIQUE constraints, but does not include XML indexes.</span></span>  
  
-   <span data-ttu-id="c7625-126">**Indice non cluster su una vista indicizzata**</span><span class="sxs-lookup"><span data-stu-id="c7625-126">**Nonclustered index on an indexed view**</span></span>  
  
     <span data-ttu-id="c7625-127">Dopo la creazione di un indice cluster univoco su una vista, è possibile creare indici non cluster.</span><span class="sxs-lookup"><span data-stu-id="c7625-127">After a unique clustered index has been created on a view, nonclustered indexes can be created.</span></span> <span data-ttu-id="c7625-128">Per altre informazioni, vedere [Creare viste indicizzate](../views/views.md).</span><span class="sxs-lookup"><span data-stu-id="c7625-128">For more information, see [Create Indexed Views](../views/views.md).</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="c7625-129">Sicurezza</span><span class="sxs-lookup"><span data-stu-id="c7625-129">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="c7625-130">Autorizzazioni</span><span class="sxs-lookup"><span data-stu-id="c7625-130">Permissions</span></span>  
 <span data-ttu-id="c7625-131">È richiesta l'autorizzazione ALTER per la tabella o la vista.</span><span class="sxs-lookup"><span data-stu-id="c7625-131">Requires ALTER permission on the table or view.</span></span> <span data-ttu-id="c7625-132">L'utente deve essere un membro del ruolo predefinito del server **sysadmin** o dei ruoli predefiniti del database **db_ddladmin** e **db_owner** .</span><span class="sxs-lookup"><span data-stu-id="c7625-132">User must be a member of the **sysadmin** fixed server role or the **db_ddladmin** and **db_owner** fixed database roles.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="c7625-133">Utilizzo di SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="c7625-133">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-create-a-nonclustered-index-by-using-the-table-designer"></a><span data-ttu-id="c7625-134">Per creare un indice non cluster tramite Progettazione tabelle</span><span class="sxs-lookup"><span data-stu-id="c7625-134">To create a nonclustered index by using the Table Designer</span></span>  
  
1.  <span data-ttu-id="c7625-135">In Esplora oggetti espandere il database contenente la tabella in cui si desidera creare un indice non cluster.</span><span class="sxs-lookup"><span data-stu-id="c7625-135">In Object Explorer, expand the database that contains the table on which you want to create a nonclustered index.</span></span>  
  
2.  <span data-ttu-id="c7625-136">Espandere la cartella **Tabelle** .</span><span class="sxs-lookup"><span data-stu-id="c7625-136">Expand the **Tables** folder.</span></span>  
  
3.  <span data-ttu-id="c7625-137">Fare clic con il pulsante destro del mouse sulla tabella in cui creare un indice non cluster e selezionare **Progetta**.</span><span class="sxs-lookup"><span data-stu-id="c7625-137">Right-click the table on which you want to create a nonclustered index and select **Design**.</span></span>  
  
4.  <span data-ttu-id="c7625-138">Scegliere **Indici/chiavi**dal menu **Progettazione tabelle** .</span><span class="sxs-lookup"><span data-stu-id="c7625-138">On the **Table Designer** menu, click **Indexes/Keys**.</span></span>  
  
5.  <span data-ttu-id="c7625-139">Nella finestra di dialogo **Indici/chiavi** fare clic su **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="c7625-139">In the **Indexes/Keys** dialog box, click **Add**.</span></span>  
  
6.  <span data-ttu-id="c7625-140">Selezionare il nuovo indice dalla casella di testo **Chiave o indice primario/univoco selezionato** .</span><span class="sxs-lookup"><span data-stu-id="c7625-140">Select the new index in the **Selected Primary/Unique Key or Index** text box.</span></span>  
  
7.  <span data-ttu-id="c7625-141">Nella griglia selezionare **Crea come CLUSTERED**, quindi scegliere **No** dall'elenco a discesa a destra della proprietà.</span><span class="sxs-lookup"><span data-stu-id="c7625-141">In the grid, select **Create as Clustered**, and choose **No** from the drop-down list to the right of the property.</span></span>  
  
8.  <span data-ttu-id="c7625-142">Fare clic su **Close**.</span><span class="sxs-lookup"><span data-stu-id="c7625-142">Click **Close**.</span></span>  
  
9. <span data-ttu-id="c7625-143">Nel menu **File** scegliere **Salva**_table_name_.</span><span class="sxs-lookup"><span data-stu-id="c7625-143">On the **File** menu, click **Save**_table_name_.</span></span>  
  
#### <a name="to-create-a-nonclustered-index-by-using-object-explorer"></a><span data-ttu-id="c7625-144">Per creare un indice non cluster tramite Esplora oggetti</span><span class="sxs-lookup"><span data-stu-id="c7625-144">To create a nonclustered index by using Object Explorer</span></span>  
  
1.  <span data-ttu-id="c7625-145">In Esplora oggetti espandere il database contenente la tabella in cui si desidera creare un indice non cluster.</span><span class="sxs-lookup"><span data-stu-id="c7625-145">In Object Explorer, expand the database that contains the table on which you want to create a nonclustered index.</span></span>  
  
2.  <span data-ttu-id="c7625-146">Espandere la cartella **Tabelle** .</span><span class="sxs-lookup"><span data-stu-id="c7625-146">Expand the **Tables** folder.</span></span>  
  
3.  <span data-ttu-id="c7625-147">Espandere la tabella in cui si desidera creare un indice non cluster.</span><span class="sxs-lookup"><span data-stu-id="c7625-147">Expand the table on which you want to create a nonclustered index.</span></span>  
  
4.  <span data-ttu-id="c7625-148">Fare clic con il pulsante destro del mouse sulla cartella **Indici**, scegliere **Nuovo indice**e selezionare **Indice non cluster**.</span><span class="sxs-lookup"><span data-stu-id="c7625-148">Right-click the **Indexes** folder, point to **New Index**, and select **Non-Clustered Index...**.</span></span>  
  
5.  <span data-ttu-id="c7625-149">Nella pagina **Generale** della finestra di dialogo **Nuovo indice** immettere il nome del nuovo indice nella casella **Nome indice** .</span><span class="sxs-lookup"><span data-stu-id="c7625-149">In the **New Index** dialog box, on the **General** page, enter the name of the new index in the **Index name** box.</span></span>  
  
6.  <span data-ttu-id="c7625-150">In **Colonne chiave indice**fare clic su **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="c7625-150">Under **Index key columns**, click **Add...**.</span></span>  
  
7.  <span data-ttu-id="c7625-151">Nella finestra di dialogo **Seleziona colonne da**_table_name_ selezionare le caselle di controllo delle colonne di tabella da aggiungere all'indice non cluster.</span><span class="sxs-lookup"><span data-stu-id="c7625-151">In the **Select Columns from**_table_name_ dialog box, select the check box or check boxes of the table column or columns to be added to the nonclustered index.</span></span>  
  
8.  <span data-ttu-id="c7625-152">Fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="c7625-152">Click **OK**.</span></span>  
  
9. <span data-ttu-id="c7625-153">Nella finestra di dialogo **Nuovo indice** fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="c7625-153">In the **New Index** dialog box, click **OK**.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="c7625-154">Uso di Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="c7625-154">Using Transact-SQL</span></span>  
  
#### <a name="to-create-a-nonclustered-index-on-a-table"></a><span data-ttu-id="c7625-155">Per creare un indice non cluster in una tabella</span><span class="sxs-lookup"><span data-stu-id="c7625-155">To create a nonclustered index on a table</span></span>  
  
1.  <span data-ttu-id="c7625-156">In **Esplora oggetti**connettersi a un'istanza del [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="c7625-156">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="c7625-157">Sulla barra Standard fare clic su **Nuova query**.</span><span class="sxs-lookup"><span data-stu-id="c7625-157">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="c7625-158">Copiare e incollare l'esempio seguente nella finestra Query, quindi fare clic su **Esegui**.</span><span class="sxs-lookup"><span data-stu-id="c7625-158">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```  
    USE AdventureWorks2012;  
    GO  
    -- Find an existing index named IX_ProductVendor_VendorID and delete it if found.   
    IF EXISTS (SELECT name FROM sys.indexes  
                WHERE name = N'IX_ProductVendor_VendorID')   
        DROP INDEX IX_ProductVendor_VendorID ON Purchasing.ProductVendor;   
    GO  
    -- Create a nonclustered index called IX_ProductVendor_VendorID   
    -- on the Purchasing.ProductVendor table using the BusinessEntityID column.   
    CREATE NONCLUSTERED INDEX IX_ProductVendor_VendorID   
        ON Purchasing.ProductVendor (BusinessEntityID);   
    GO  
    ```  
  
 <span data-ttu-id="c7625-159">Per altre informazioni, vedere [CREATE INDEX &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-index-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="c7625-159">For more information, see [CREATE INDEX &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-index-transact-sql).</span></span>  
  
  
