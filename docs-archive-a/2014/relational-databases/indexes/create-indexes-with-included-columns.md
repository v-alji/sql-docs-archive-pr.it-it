---
title: Creare indici con colonne incluse | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: table-view-index
ms.topic: conceptual
helpviewer_keywords:
- index size [SQL Server]
- index keys [SQL Server]
- index columns [SQL Server]
- size [SQL Server], indexes
- key columns [SQL Server]
- included columns
- nonclustered indexes [SQL Server], included columns
- designing indexes [SQL Server], included columns
- nonkey columns
ms.assetid: d198648d-fea5-416d-9f30-f9d4aebbf4ec
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: e5a464f9791ea635236069555647229bf1f0d79e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87724631"
---
# <a name="create-indexes-with-included-columns"></a><span data-ttu-id="5a95a-102">Creare indici con colonne incluse</span><span class="sxs-lookup"><span data-stu-id="5a95a-102">Create Indexes with Included Columns</span></span>
  <span data-ttu-id="5a95a-103">In questo argomento si illustra come aggiungere colonne incluse (o non chiave) per estendere la funzionalità di indici non cluster in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] tramite [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] o [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="5a95a-103">This topic describes how to add included (or nonkey) columns to extend the functionality of nonclustered indexes in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span> <span data-ttu-id="5a95a-104">Con l'inclusione di colonne non chiave è possibile creare indici non cluster in grado di coprire più query.</span><span class="sxs-lookup"><span data-stu-id="5a95a-104">By including nonkey columns, you can create nonclustered indexes that cover more queries.</span></span> <span data-ttu-id="5a95a-105">Ciò è possibile perché le colonne non chiave presentano i vantaggi seguenti:</span><span class="sxs-lookup"><span data-stu-id="5a95a-105">This is because the nonkey columns have the following benefits:</span></span>  
  
-   <span data-ttu-id="5a95a-106">Possono essere tipi di dati che non sono consentiti come colonne chiave indice.</span><span class="sxs-lookup"><span data-stu-id="5a95a-106">They can be data types not allowed as index key columns.</span></span>  
  
-   <span data-ttu-id="5a95a-107">Non vengono prese in esame dal [!INCLUDE[ssDE](../../includes/ssde-md.md)] durante il calcolo del numero di colonne chiave indice o della dimensione delle chiavi di indice.</span><span class="sxs-lookup"><span data-stu-id="5a95a-107">They are not considered by the [!INCLUDE[ssDE](../../includes/ssde-md.md)] when calculating the number of index key columns or index key size.</span></span>  
  
 <span data-ttu-id="5a95a-108">Con un indice con colonne non chiave è possibile aumentare significativamente le prestazioni delle query quando tutte le relative colonne sono incluse nell'indice come colonne chiave o non chiave.</span><span class="sxs-lookup"><span data-stu-id="5a95a-108">An index with nonkey columns can significantly improve query performance when all columns in the query are included in the index either as key or nonkey columns.</span></span> <span data-ttu-id="5a95a-109">I vantaggi nelle prestazioni si ottengono poiché Query Optimizer può individuare tutti i valori delle colonne all'interno dell'indice. In questo modo, la quantità di operazioni di I/O su disco è inferiore dato che non viene eseguito alcun accesso ai dati delle tabelle o degli indici cluster.</span><span class="sxs-lookup"><span data-stu-id="5a95a-109">Performance gains are achieved because the query optimizer can locate all the column values within the index; table or clustered index data is not accessed resulting in fewer disk I/O operations.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="5a95a-110">Quando in un indice sono contenute tutte le colonne a cui fa riferimento una query, viene generalmente indicato come *copertura della query*.</span><span class="sxs-lookup"><span data-stu-id="5a95a-110">When an index contains all the columns referenced by a query it is typically referred to as *covering the query*.</span></span>  
  
 <span data-ttu-id="5a95a-111">**Contenuto dell'articolo**</span><span class="sxs-lookup"><span data-stu-id="5a95a-111">**In This Topic**</span></span>  
  
-   <span data-ttu-id="5a95a-112">**Prima di iniziare:**</span><span class="sxs-lookup"><span data-stu-id="5a95a-112">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="5a95a-113">Suggerimenti per la progettazione</span><span class="sxs-lookup"><span data-stu-id="5a95a-113">Design Recommendations</span></span>](#DesignRecs)  
  
     [<span data-ttu-id="5a95a-114">Limitazioni e restrizioni</span><span class="sxs-lookup"><span data-stu-id="5a95a-114">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="5a95a-115">Sicurezza</span><span class="sxs-lookup"><span data-stu-id="5a95a-115">Security</span></span>](#Security)  
  
-   <span data-ttu-id="5a95a-116">**Per creare un indice con colonne non chiave utilizzando:**</span><span class="sxs-lookup"><span data-stu-id="5a95a-116">**To create an index with nonkey columns, using:**</span></span>  
  
     [<span data-ttu-id="5a95a-117">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="5a95a-117">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="5a95a-118">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="5a95a-118">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="5a95a-119">Prima di iniziare</span><span class="sxs-lookup"><span data-stu-id="5a95a-119">Before You Begin</span></span>  
  
###  <a name="design-recommendations"></a><a name="DesignRecs"></a> <span data-ttu-id="5a95a-120">Indicazioni sulla progettazione</span><span class="sxs-lookup"><span data-stu-id="5a95a-120">Design Recommendations</span></span>  
  
-   <span data-ttu-id="5a95a-121">Progettare nuovamente gli indici non cluster con chiavi di indice dalle dimensioni elevate in modo da utilizzare come colonne chiave solo le colonne utilizzate per le ricerche.</span><span class="sxs-lookup"><span data-stu-id="5a95a-121">Redesign nonclustered indexes with a large index key size so that only columns used for searching and lookups are key columns.</span></span> <span data-ttu-id="5a95a-122">Modificare in colonne non chiave tutte le altre colonne che coprono la query.</span><span class="sxs-lookup"><span data-stu-id="5a95a-122">Make all other columns that cover the query into nonkey columns.</span></span> <span data-ttu-id="5a95a-123">In questo modo si avranno tutte le colonne necessarie per coprire la query, contenendo al tempo stesso le dimensioni della chiave dell'indice e mantenendone l'efficienza.</span><span class="sxs-lookup"><span data-stu-id="5a95a-123">In this way, you will have all columns needed to cover the query, but the index key itself is small and efficient.</span></span>  
  
-   <span data-ttu-id="5a95a-124">Includere colonne non chiave in un indice non cluster per evitare il superamento delle limitazioni di dimensione correnti degli indici (numero massimo di colonne chiave pari a 16 e dimensione massima delle chiavi di indice pari a 900 byte).</span><span class="sxs-lookup"><span data-stu-id="5a95a-124">Include nonkey columns in a nonclustered index to avoid exceeding the current index size limitations of a maximum of 16 key columns and a maximum index key size of 900 bytes.</span></span> <span data-ttu-id="5a95a-125">Il [!INCLUDE[ssDE](../../includes/ssde-md.md)] non prende in esame le colonne non chiave durante il calcolo del numero di colonne chiave indice o della dimensione delle chiavi di indice.</span><span class="sxs-lookup"><span data-stu-id="5a95a-125">The [!INCLUDE[ssDE](../../includes/ssde-md.md)] does not consider nonkey columns when calculating the number of index key columns or index key size.</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="5a95a-126">Limitazioni e restrizioni</span><span class="sxs-lookup"><span data-stu-id="5a95a-126">Limitations and Restrictions</span></span>  
  
-   <span data-ttu-id="5a95a-127">Le colonne non chiave possono essere definite solo negli indici non cluster.</span><span class="sxs-lookup"><span data-stu-id="5a95a-127">Nonkey columns can only be defined on nonclustered indexes.</span></span>  
  
-   <span data-ttu-id="5a95a-128">È possibile utilizzare come colonne non chiave tutti i tipi di dati eccetto `text`, `ntext` e `image`.</span><span class="sxs-lookup"><span data-stu-id="5a95a-128">All data types except `text`, `ntext`, and `image` can be used as nonkey columns.</span></span>  
  
-   <span data-ttu-id="5a95a-129">Le colonne calcolate deterministiche, precise o imprecise, possono essere colonne non chiave.</span><span class="sxs-lookup"><span data-stu-id="5a95a-129">Computed columns that are deterministic and either precise or imprecise can be nonkey columns.</span></span> <span data-ttu-id="5a95a-130">Per altre informazioni, vedere [Indici per le colonne calcolate](indexes-on-computed-columns.md).</span><span class="sxs-lookup"><span data-stu-id="5a95a-130">For more information, see [Indexes on Computed Columns](indexes-on-computed-columns.md).</span></span>  
  
-   <span data-ttu-id="5a95a-131">Le colonne calcolate derivate dai tipi di dati `image`, `ntext` e `text` possono essere colonne non chiave purché il tipo di dati della colonna calcolata sia consentito come colonna non chiave dell'indice.</span><span class="sxs-lookup"><span data-stu-id="5a95a-131">Computed columns derived from `image`, `ntext`, and `text` data types can be nonkey columns as long as the computed column data type is allowed as a nonkey index column.</span></span>  
  
-   <span data-ttu-id="5a95a-132">Non è possibile rimuovere da una tabella le colonne non chiave se non si è prima eliminato l'indice di questa tabella.</span><span class="sxs-lookup"><span data-stu-id="5a95a-132">Nonkey columns cannot be dropped from a table unless that table's index is dropped first.</span></span>  
  
-   <span data-ttu-id="5a95a-133">Non è possibile modificare le colonne non chiave se non per eseguire le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="5a95a-133">Nonkey columns cannot be changed, except to do the following:</span></span>  
  
    -   <span data-ttu-id="5a95a-134">Modifica del supporto di valori NULL della colonna da NOT NULL a NULL.</span><span class="sxs-lookup"><span data-stu-id="5a95a-134">Change the nullability of the column from NOT NULL to NULL.</span></span>  
  
    -   <span data-ttu-id="5a95a-135">Aumento della lunghezza di colonne `varchar`, `nvarchar` o `varbinary`.</span><span class="sxs-lookup"><span data-stu-id="5a95a-135">Increase the length of `varchar`, `nvarchar`, or `varbinary` columns.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="5a95a-136">Sicurezza</span><span class="sxs-lookup"><span data-stu-id="5a95a-136">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="5a95a-137">Autorizzazioni</span><span class="sxs-lookup"><span data-stu-id="5a95a-137">Permissions</span></span>  
 <span data-ttu-id="5a95a-138">È richiesta l'autorizzazione ALTER per la tabella o la vista.</span><span class="sxs-lookup"><span data-stu-id="5a95a-138">Requires ALTER permission on the table or view.</span></span> <span data-ttu-id="5a95a-139">L'utente deve essere un membro del ruolo predefinito del server **sysadmin** o dei ruoli predefiniti del database **db_ddladmin** e **db_owner** .</span><span class="sxs-lookup"><span data-stu-id="5a95a-139">User must be a member of the **sysadmin** fixed server role or the **db_ddladmin** and **db_owner** fixed database roles.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="5a95a-140">Utilizzo di SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="5a95a-140">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-create-an-index-with-nonkey-columns"></a><span data-ttu-id="5a95a-141">Per creare un indice con colonne non chiave</span><span class="sxs-lookup"><span data-stu-id="5a95a-141">To create an index with nonkey columns</span></span>  
  
1.  <span data-ttu-id="5a95a-142">In Esplora oggetti fare clic sul segno più per espandere il database contenente la tabella in cui si desidera creare un indice con colonne non chiave.</span><span class="sxs-lookup"><span data-stu-id="5a95a-142">In Object Explorer, click the plus sign to expand the database that contains the table on which you want to create an index with nonkey columns.</span></span>  
  
2.  <span data-ttu-id="5a95a-143">Fare clic sul segno più per espandere la cartella **Tabelle** .</span><span class="sxs-lookup"><span data-stu-id="5a95a-143">Click the plus sign to expand the **Tables** folder.</span></span>  
  
3.  <span data-ttu-id="5a95a-144">Fare clic sul segno più per espandere la tabella in cui si desidera creare un indice con colonne non chiave.</span><span class="sxs-lookup"><span data-stu-id="5a95a-144">Click the plus sign to expand the table on which you want to create an index with nonkey columns.</span></span>  
  
4.  <span data-ttu-id="5a95a-145">Fare clic con il pulsante destro del mouse sulla cartella **Indici**, scegliere **Nuovo indice**e selezionare **Indice non cluster**.</span><span class="sxs-lookup"><span data-stu-id="5a95a-145">Right-click the **Indexes** folder, point to **New Index**, and select **Non-Clustered Index...**.</span></span>  
  
5.  <span data-ttu-id="5a95a-146">Nella pagina **Generale** della finestra di dialogo **Nuovo indice** immettere il nome del nuovo indice nella casella **Nome indice** .</span><span class="sxs-lookup"><span data-stu-id="5a95a-146">In the **New Index** dialog box, on the **General** page, enter the name of the new index in the **Index name** box.</span></span>  
  
6.  <span data-ttu-id="5a95a-147">Nella scheda **Colonne chiave indice** scegliere **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="5a95a-147">Under the **Index key columns** tab, click **Add...**.</span></span>  
  
7.  <span data-ttu-id="5a95a-148">Nella finestra di dialogo **Seleziona colonne da**_table_name_ Selezionare le caselle di controllo delle colonne della tabella da aggiungere all'indice.</span><span class="sxs-lookup"><span data-stu-id="5a95a-148">In the **Select Columns from**_table_name_ dialog box, select the check box or check boxes of the table column or columns to be added to the index.</span></span>  
  
8.  <span data-ttu-id="5a95a-149">Fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="5a95a-149">Click **OK**.</span></span>  
  
9. <span data-ttu-id="5a95a-150">Nella scheda **Colonne incluse** scegliere **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="5a95a-150">Under the **Included columns** tab, click **Add...**.</span></span>  
  
10. <span data-ttu-id="5a95a-151">Nella finestra di dialogo **Seleziona colonne da**_table_name_ Selezionare le caselle di controllo della colonna o delle colonne della tabella da aggiungere all'indice come colonne colonne.</span><span class="sxs-lookup"><span data-stu-id="5a95a-151">In the **Select Columns from**_table_name_ dialog box, select the check box or check boxes of the table column or columns to be added to the index as nonkey columns.</span></span>  
  
11. <span data-ttu-id="5a95a-152">Fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="5a95a-152">Click **OK**.</span></span>  
  
12. <span data-ttu-id="5a95a-153">Nella finestra di dialogo **Nuovo indice** fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="5a95a-153">In the **New Index** dialog box, click **OK**.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="5a95a-154">Uso di Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="5a95a-154">Using Transact-SQL</span></span>  
  
#### <a name="to-create-an-index-with-nonkey-columns"></a><span data-ttu-id="5a95a-155">Per creare un indice con colonne non chiave</span><span class="sxs-lookup"><span data-stu-id="5a95a-155">To create an index with nonkey columns</span></span>  
  
1.  <span data-ttu-id="5a95a-156">In **Esplora oggetti**connettersi a un'istanza del [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="5a95a-156">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="5a95a-157">Sulla barra Standard fare clic su **Nuova query**.</span><span class="sxs-lookup"><span data-stu-id="5a95a-157">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="5a95a-158">Copiare e incollare l'esempio seguente nella finestra Query, quindi fare clic su **Esegui**.</span><span class="sxs-lookup"><span data-stu-id="5a95a-158">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```  
    USE AdventureWorks2012;  
    GO  
    -- Creates a nonclustered index on the Person.Address table with four included (nonkey) columns.   
    -- index key column is PostalCode and the nonkey columns are  
    -- AddressLine1, AddressLine2, City, and StateProvinceID.  
    CREATE NONCLUSTERED INDEX IX_Address_PostalCode  
    ON Person.Address (PostalCode)  
    INCLUDE (AddressLine1, AddressLine2, City, StateProvinceID);  
    GO  
    ```  
  
 <span data-ttu-id="5a95a-159">Per altre informazioni, vedere [CREATE INDEX &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-index-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="5a95a-159">For more information, see [CREATE INDEX &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-index-transact-sql).</span></span>  
  
  
