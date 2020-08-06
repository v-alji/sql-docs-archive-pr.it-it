---
title: Creare, modificare ed eliminare indici spaziali | Microsoft Docs
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
helpviewer_keywords:
- indexes [SQL Server], creating
- spatial indexes [SQL Server], dropping
- spatial indexes [SQL Server], creating
- indexes [SQL Server], dropping
- indexes [SQL Server], modifying
- spatial indexes [SQL Server], modifying
ms.assetid: 00c1b927-8ec5-44cf-87c2-c8de59745735
author: MladjoA
ms.author: mlandzic
ms.openlocfilehash: 88de17e8c487d9a965f2e236edac064dc2fe4c7c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87624564"
---
# <a name="create-modify-and-drop-spatial-indexes"></a><span data-ttu-id="45303-102">Creazione, modifica ed eliminazione di indici spaziali</span><span class="sxs-lookup"><span data-stu-id="45303-102">Create, Modify, and Drop Spatial Indexes</span></span>
  <span data-ttu-id="45303-103">Un indice spaziale può eseguire in modo più efficiente determinate operazioni su una colonna `geometry` del `geography` tipo di dati o (una *colonna spaziale*).</span><span class="sxs-lookup"><span data-stu-id="45303-103">A spatial index can more efficiently perform certain operations on a column of the `geometry` or `geography` data type (a *spatial column*).</span></span> <span data-ttu-id="45303-104">In una colonna spaziale è possibile specificare più di un indice spaziale.</span><span class="sxs-lookup"><span data-stu-id="45303-104">More than one spatial index can be specified on a spatial column.</span></span> <span data-ttu-id="45303-105">Ciò è utile, ad esempio, per indicizzare diversi parametri della suddivisione a mosaico in una sola colonna.</span><span class="sxs-lookup"><span data-stu-id="45303-105">This is useful, for example, for indexing different tessellation parameters in a single column.</span></span>  
  
 <span data-ttu-id="45303-106">La creazione di indici spaziali è soggetta a un certo numero di limitazioni.</span><span class="sxs-lookup"><span data-stu-id="45303-106">There are a number of restrictions on creating spatial indexes.</span></span> <span data-ttu-id="45303-107">Per altre informazioni, vedere [Restrizioni relative agli indici spaziali](#restrictions) .</span><span class="sxs-lookup"><span data-stu-id="45303-107">For more information, see [Restrictions on Spatial Indexes](#restrictions) in this topic.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="45303-108">Per informazioni sulla relazione degli indici spaziali con la partizione e i filegroup, vedere la sezione "Osservazioni" in [CREATE SPATIAL INDEX &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-spatial-index-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="45303-108">For information about the relationship of spatial indexes to partition and to filegroups, see the "Remarks" section in [CREATE SPATIAL INDEX &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-spatial-index-transact-sql).</span></span>  
  
##  <a name="creating-modifying-and-dropping-spatial-indexes"></a><a name="creating"></a> <span data-ttu-id="45303-109">Creazione, modifica e rimozione di indici spaziali</span><span class="sxs-lookup"><span data-stu-id="45303-109">Creating, Modifying, and Dropping Spatial Indexes</span></span>  
  
###  <a name="to-create-a-spatial-index"></a><a name="create"></a> <span data-ttu-id="45303-110">Per creare un indice spaziale</span><span class="sxs-lookup"><span data-stu-id="45303-110">To create a spatial index</span></span>  
 <span data-ttu-id="45303-111">**Per creare un indice spaziale tramite Transact-SQL**</span><span class="sxs-lookup"><span data-stu-id="45303-111">**To create a spatial index by using Transact-SQL**</span></span>  
 [<span data-ttu-id="45303-112">CREATE SPATIAL INDEX &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="45303-112">CREATE SPATIAL INDEX &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/create-spatial-index-transact-sql)  
  
 <span data-ttu-id="45303-113">**Per creare un indice spaziale tramite la finestra di dialogo Nuovo indice in Management Studio**</span><span class="sxs-lookup"><span data-stu-id="45303-113">**To create a spatial index by using the New Index dialog box in Management Studio**</span></span>  
 ##### <a name="to-create-a-spatial-index-in-management-studio"></a><span data-ttu-id="45303-114">Per creare un indice spaziale in Management Studio</span><span class="sxs-lookup"><span data-stu-id="45303-114">To create a spatial index in Management Studio</span></span>  
  
1.  <span data-ttu-id="45303-115">In Esplora oggetti connettersi a un'istanza del [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] , quindi espandere questa istanza.</span><span class="sxs-lookup"><span data-stu-id="45303-115">In Object Explorer, connect to an instance of the [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] and then expand that instance.</span></span>  
  
2.  <span data-ttu-id="45303-116">Espandere **Database**, espandere il database che contiene la tabella con l'indice specificato e quindi espandere **Tabelle**.</span><span class="sxs-lookup"><span data-stu-id="45303-116">Expand **Databases**, expand the database that contains the table with the specified index, and then expand **Tables**.</span></span>  
  
3.  <span data-ttu-id="45303-117">Espandere la tabella per la quale si desidera creare l'indice.</span><span class="sxs-lookup"><span data-stu-id="45303-117">Expand the table for which you want to create the index.</span></span>  
  
4.  <span data-ttu-id="45303-118">Fare clic con il pulsante destro del mouse su **Indici** e scegliere **Nuovo indice**.</span><span class="sxs-lookup"><span data-stu-id="45303-118">Right-click **Indexes** and select **New Index**.</span></span>  
  
5.  <span data-ttu-id="45303-119">Nel campo **Nome indice** immettere un nome per l'indice.</span><span class="sxs-lookup"><span data-stu-id="45303-119">In the **Index name** field, enter a name for the index.</span></span>  
  
6.  <span data-ttu-id="45303-120">Nell'elenco a discesa **Tipo di indice** selezionare **Spaziale**.</span><span class="sxs-lookup"><span data-stu-id="45303-120">In the **Index type** drop-down list, select **Spatial**.</span></span>  
  
7.  <span data-ttu-id="45303-121">Per specificare la colonna spaziale che si vuole indicizzare, fare clic su **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="45303-121">To specify the spatial column that you want to index, click **Add**.</span></span>  
  
8.  <span data-ttu-id="45303-122">Nella finestra di dialogo **Seleziona colonne da** *\<table name>* selezionare una colonna di tipo `geometry` o `geography` selezionando la casella di controllo corrispondente.</span><span class="sxs-lookup"><span data-stu-id="45303-122">In the **Select Columns from** *\<table name>* dialog box, select a column of type `geometry` or `geography` by selecting the corresponding check box.</span></span> <span data-ttu-id="45303-123">Le altre colonne spaziali eventualmente presenti diventano non modificabili.</span><span class="sxs-lookup"><span data-stu-id="45303-123">Any other spatial columns then become uneditable.</span></span> <span data-ttu-id="45303-124">Se si desidera selezionare una colonna spaziale diversa, è innanzitutto necessario deselezionare la colonna attualmente selezionata.</span><span class="sxs-lookup"><span data-stu-id="45303-124">If you want to select a different spatial column, you must first clear the currently selected column.</span></span> <span data-ttu-id="45303-125">Al termine, fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="45303-125">When finished, click **OK**.</span></span>  
  
9. <span data-ttu-id="45303-126">Verificare la selezione della colonna nella griglia **Colonne chiave indice** .</span><span class="sxs-lookup"><span data-stu-id="45303-126">Verify your column selection in the **Index key columns** grid.</span></span>  
  
10. <span data-ttu-id="45303-127">Nel riquadro **Selezione pagina** della finestra di dialogo **Proprietà indice** fare clic su **Spaziale**.</span><span class="sxs-lookup"><span data-stu-id="45303-127">In the **Select a page** pane of the **Index Properties** dialog box, click **Spatial**.</span></span>  
  
11. <span data-ttu-id="45303-128">Nella pagina **Spaziale** specificare i valori che si vogliono usare per le proprietà spaziali dell'indice.</span><span class="sxs-lookup"><span data-stu-id="45303-128">On the **Spatial** page, specify the values that you want to use for the spatial properties of the index.</span></span>  
  
     <span data-ttu-id="45303-129">Quando si crea un indice in una `geometry` colonna di tipo, è necessario specificare le coordinate **( *`X-min`* , *`Y-min`* )** e **( *`X-max`* , *`Y-max`* )** del rettangolo di delimitazione.</span><span class="sxs-lookup"><span data-stu-id="45303-129">When creating an index on a `geometry` type column, you must specify the **(*`X-min`*,*`Y-min`*)** and **(*`X-max`*,*`Y-max`*)** coordinates of the bounding box.</span></span> <span data-ttu-id="45303-130">Per un indice in una `geography` colonna di tipo, i campi del riquadro diventano di sola lettura dopo avere specificato lo schema a mosaico della **griglia geografica** , perché lo schema a mosaico della griglia geografica non utilizza un rettangolo di delimitazione.</span><span class="sxs-lookup"><span data-stu-id="45303-130">For an index on a `geography` type column, the bounding-box fields become read-only after you specify the **Geography grid** tessellation scheme, because geography grid tessellation does not use a bounding box.</span></span>  
  
     <span data-ttu-id="45303-131">È eventualmente possibile specificare valori non predefiniti per il campo **Celle per oggetto** e per la densità griglia a qualsiasi livello dello schema a mosaico.</span><span class="sxs-lookup"><span data-stu-id="45303-131">Optionally, you can specify nondefault values for the **Cells Per Object** field and for the grid density at any level of the tessellation scheme.</span></span> <span data-ttu-id="45303-132">Il numero predefinito di celle per oggetto è 16 per [!INCLUDE[ssKatmai](../../../includes/sskatmai-md.md)] o 8 per [!INCLUDE[ssSQL11](../../../includes/sssql11-md.md)] o versione successiva, mentre la densità della griglia predefinita è **Media** per [!INCLUDE[ssKatmai](../../../includes/sskatmai-md.md)].</span><span class="sxs-lookup"><span data-stu-id="45303-132">The default number of cells per object is 16 for [!INCLUDE[ssKatmai](../../../includes/sskatmai-md.md)] or 8 for [!INCLUDE[ssSQL11](../../../includes/sssql11-md.md)] or higher, and the default grid density is **Medium** for [!INCLUDE[ssKatmai](../../../includes/sskatmai-md.md)].</span></span>  
  
     <span data-ttu-id="45303-133">È possibile selezionare GEOMETRY_AUTO_GRID o GEOGRAPHY_AUTO_GRID per lo schema a mosaico in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="45303-133">You can select GEOMETRY_AUTO_GRID or GEOGRAPHY_AUTO_GRID for tessellation scheme in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="45303-134">Quando si seleziona GEOMETRY_AUTO_GRID o GEOGRAPHY_AUTO_GRID, le opzioni Livello 1, Livello 2, Livello 3 e Livello 4 per la densità della griglia sono disabilitate.</span><span class="sxs-lookup"><span data-stu-id="45303-134">When GEOMETRY_AUTO_GRID or GEOGRAPHY_AUTO_GRID is selected, then Level 1, Level 2, Level 3, and Level 4 grid density options are disabled.</span></span>  
  
     <span data-ttu-id="45303-135">Per altre informazioni su queste proprietà, vedere [Guida sensibile al contesto di Proprietà indice](../indexes/index-properties-f1-help.md).</span><span class="sxs-lookup"><span data-stu-id="45303-135">For more information about these properties, see [Index Properties F1 Help](../indexes/index-properties-f1-help.md).</span></span>  
  
12. <span data-ttu-id="45303-136">Fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="45303-136">Click **OK**.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="45303-137">Per creare un altro indice spaziale nella stessa colonna spaziale o in una colonna diversa, ripetere i passaggi precedenti.</span><span class="sxs-lookup"><span data-stu-id="45303-137">To create another spatial index on the same or a different spatial column, repeat the preceding steps.</span></span>  
  
  
 <span data-ttu-id="45303-138">**Per creare un indice spaziale tramite Progettazione tabelle in Management Studio**</span><span class="sxs-lookup"><span data-stu-id="45303-138">**To create a spatial index by using Table Designer in Management Studio**</span></span>  
 ##### <a name="to-create-a-spatial-index-in-table-designer"></a><span data-ttu-id="45303-139">Per creare un indice spaziale in Progettazione tabelle</span><span class="sxs-lookup"><span data-stu-id="45303-139">To create a spatial index in Table Designer</span></span>  
  
1.  <span data-ttu-id="45303-140">In Esplora oggetti fare clic con il pulsante destro del mouse sulla tabella per la quale si vuole creare un indice spaziale e scegliere **Progetta**.</span><span class="sxs-lookup"><span data-stu-id="45303-140">In Object Explorer, right-click the table for which you want to create a spatial index, and then click **Design**.</span></span>  
  
     <span data-ttu-id="45303-141">La tabella verrà visualizzata in Progettazione tabelle.</span><span class="sxs-lookup"><span data-stu-id="45303-141">The table opens in Table Designer.</span></span>  
  
2.  <span data-ttu-id="45303-142">Selezionare una colonna `geometry` o una colonna `geography` per l'indice.</span><span class="sxs-lookup"><span data-stu-id="45303-142">Select a `geometry` or `geography` column for the index.</span></span>  
  
3.  <span data-ttu-id="45303-143">Scegliere **Indice spaziale** dal menu **Progettazione tabelle**.</span><span class="sxs-lookup"><span data-stu-id="45303-143">On the **Table Designer** menu, click **Spatial Index**.</span></span>  
  
4.  <span data-ttu-id="45303-144">Nella finestra di dialogo **Indici spaziali** fare clic su **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="45303-144">In the **Spatial Indexes** dialog box, click **Add**.</span></span>  
  
5.  <span data-ttu-id="45303-145">Selezionare il nuovo indice dall'elenco **Indice spaziale selezionato** e impostarne le proprietà nella griglia a destra.</span><span class="sxs-lookup"><span data-stu-id="45303-145">Select the new index in the **Selected Spatial Index** list, and in the grid to the right, set the properties for the spatial index.</span></span> <span data-ttu-id="45303-146">Per informazioni sulle proprietà, vedere [Finestra di dialogo Indici spaziali &#40;Visual Database Tools&#41;](../../ssms/visual-db-tools/visual-database-tools.md).</span><span class="sxs-lookup"><span data-stu-id="45303-146">For information about the properties, see [Spatial Indexes Dialog Box &#40;Visual Database Tools&#41;](../../ssms/visual-db-tools/visual-database-tools.md).</span></span>  
  
  
###  <a name="to-alter-a-spatial-index"></a><a name="alter"></a> <span data-ttu-id="45303-147">Per modificare un indice spaziale</span><span class="sxs-lookup"><span data-stu-id="45303-147">To alter a spatial index</span></span>  
  
-   [<span data-ttu-id="45303-148">ALTER INDEX &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="45303-148">ALTER INDEX &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/alter-index-transact-sql)  
  
    > [!IMPORTANT]  
    >  <span data-ttu-id="45303-149">Per modificare opzioni specifiche di un indice spaziale, ad esempio BOUNDING_BOX o GRID, è possibile utilizzare un'istruzione CREATE SPATIAL INDEX che specifica DROP_EXISTING = ON oppure eliminare l'indice spaziale e crearne un nuovo.</span><span class="sxs-lookup"><span data-stu-id="45303-149">To change options that are specific to a spatial index, such as BOUNDING_BOX or GRID, you can either use a CREATE SPATIAL INDEX statement that specifies DROP_EXISTING = ON, or drop the spatial index and create a new one.</span></span> <span data-ttu-id="45303-150">Per un esempio vedere [CREATE SPATIAL INDEX &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-spatial-index-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="45303-150">For an example, see [CREATE SPATIAL INDEX &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-spatial-index-transact-sql).</span></span>  
  
-   [<span data-ttu-id="45303-151">Modificare un indice</span><span class="sxs-lookup"><span data-stu-id="45303-151">Modify an Index</span></span>](../indexes/modify-an-index.md)  
  
-   [<span data-ttu-id="45303-152">Spostare un indice esistente in un filegroup diverso</span><span class="sxs-lookup"><span data-stu-id="45303-152">Move an Existing Index to a Different Filegroup</span></span>](../indexes/move-an-existing-index-to-a-different-filegroup.md)  
  
  
###  <a name="to-drop-a-spatial-index"></a><a name="drop"></a> <span data-ttu-id="45303-153">Per eliminare un indice spaziale</span><span class="sxs-lookup"><span data-stu-id="45303-153">To drop a spatial index</span></span>  
 <span data-ttu-id="45303-154">**Per eliminare un indice spaziale tramite Transact-SQL**</span><span class="sxs-lookup"><span data-stu-id="45303-154">**To drop a spatial index by using Transact-SQL**</span></span>  
 [<span data-ttu-id="45303-155">DROP INDEX &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="45303-155">DROP INDEX &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/drop-index-transact-sql)  
  
 <span data-ttu-id="45303-156">**Per eliminare un indice utilizzando Management Studio**</span><span class="sxs-lookup"><span data-stu-id="45303-156">**To drop an index by using Management Studio**</span></span>  
 [<span data-ttu-id="45303-157">Eliminare un indice</span><span class="sxs-lookup"><span data-stu-id="45303-157">Delete an Index</span></span>](../indexes/delete-an-index.md)  
  
 <span data-ttu-id="45303-158">**Per eliminare un indice spaziale tramite Progettazione tabelle in Management Studio**</span><span class="sxs-lookup"><span data-stu-id="45303-158">**To drop a spatial index by using Table Designer in Management Studio**</span></span>  
 ##### <a name="to-drop-a-spatial-index-in-table-designer"></a><span data-ttu-id="45303-159">Per eliminare un indice spaziale in Progettazione tabelle</span><span class="sxs-lookup"><span data-stu-id="45303-159">To drop a spatial index in Table Designer</span></span>  
  
1.  <span data-ttu-id="45303-160">In Esplora oggetti, selezionare con il pulsante destro del mouse la tabella contenente l'indice spaziale da eliminare, quindi selezionare **Progetta**.</span><span class="sxs-lookup"><span data-stu-id="45303-160">In Object Explorer, right-click the table with the spatial index you want to delete and click **Design**.</span></span>  
  
     <span data-ttu-id="45303-161">La tabella verrà visualizzata in Progettazione tabelle.</span><span class="sxs-lookup"><span data-stu-id="45303-161">The table opens in Table Designer.</span></span>  
  
2.  <span data-ttu-id="45303-162">Scegliere **Indice spaziale** dal menu **Progettazione tabelle**.</span><span class="sxs-lookup"><span data-stu-id="45303-162">On the **Table Designer** menu, click **Spatial Index**.</span></span>  
  
     <span data-ttu-id="45303-163">Verrà visualizzata la finestra di dialogo **Indice spaziale** .</span><span class="sxs-lookup"><span data-stu-id="45303-163">The **Spatial Index** dialog box opens.</span></span>  
  
3.  <span data-ttu-id="45303-164">Fare clic sull'indice da eliminare nella colonna **Indice spaziale selezionato** .</span><span class="sxs-lookup"><span data-stu-id="45303-164">Click the index you want to delete in the **Selected Spatial Index** column.</span></span>  
  
4.  <span data-ttu-id="45303-165">Fare clic su **Elimina**.</span><span class="sxs-lookup"><span data-stu-id="45303-165">Click **Delete**.</span></span>  
  
  
##  <a name="restrictions-on-spatial-indexes"></a><a name="restrictions"></a> <span data-ttu-id="45303-166">Restrizioni relative agli indici spaziali</span><span class="sxs-lookup"><span data-stu-id="45303-166">Restrictions on Spatial Indexes</span></span>  
 <span data-ttu-id="45303-167">È possibile creare un indice spaziale solo in una colonna di tipo `geometry` o `geography`.</span><span class="sxs-lookup"><span data-stu-id="45303-167">A spatial index can be created only on a column of type `geometry` or `geography`.</span></span>  
  
### <a name="table-and-view-restrictions"></a><span data-ttu-id="45303-168">Restrizioni per viste e tabelle</span><span class="sxs-lookup"><span data-stu-id="45303-168">Table and View Restrictions</span></span>  
 <span data-ttu-id="45303-169">È possibile definire indici spaziali solo per una tabella con chiave primaria.</span><span class="sxs-lookup"><span data-stu-id="45303-169">Spatial indexes can be defined only on a table that has a primary key.</span></span> <span data-ttu-id="45303-170">Il numero massimo di colonne chiave primaria in una tabella è pari a 15.</span><span class="sxs-lookup"><span data-stu-id="45303-170">The maximum number of primary key columns on the table is 15.</span></span>  
  
 <span data-ttu-id="45303-171">La dimensione massima dei record di una chiave di indice è 895 byte.</span><span class="sxs-lookup"><span data-stu-id="45303-171">The maximum size of index key records is 895 bytes.</span></span> <span data-ttu-id="45303-172">Dimensioni maggiori generano un errore.</span><span class="sxs-lookup"><span data-stu-id="45303-172">Larger sizes raise an error.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="45303-173">I metadati della chiave primaria non possono essere modificati se un indice spaziale è definito in una tabella.</span><span class="sxs-lookup"><span data-stu-id="45303-173">Primary key metadata cannot be changed while a spatial index is defined on a table.</span></span>  
  
 <span data-ttu-id="45303-174">Non è possibile specificare indici spaziali in viste indicizzate.</span><span class="sxs-lookup"><span data-stu-id="45303-174">Spatial indexes cannot be specified on indexed views.</span></span>  
  
### <a name="multiple-spatial-index-restrictions"></a><span data-ttu-id="45303-175">Restrizioni relative a più indici spaziali</span><span class="sxs-lookup"><span data-stu-id="45303-175">Multiple Spatial Index Restrictions</span></span>  
 <span data-ttu-id="45303-176">È possibile creare fino a 249 indici spaziali in ognuna delle colonne spaziali in una tabella supportata.</span><span class="sxs-lookup"><span data-stu-id="45303-176">You can create up to 249 spatial indexes on any of the spatial columns in a supported table.</span></span> <span data-ttu-id="45303-177">La creazione di più di un indice spaziale nella stessa colonna spaziale può essere utile, ad esempio, per indicizzare parametri della suddivisione a mosaico diversi in una sola colonna.</span><span class="sxs-lookup"><span data-stu-id="45303-177">Creating more than one spatial index on the same spatial column can be useful, for example, to index different tessellation parameters in a single column.</span></span>  
  
 <span data-ttu-id="45303-178">È possibile creare solo un indice spaziale alla volta.</span><span class="sxs-lookup"><span data-stu-id="45303-178">You can create only one spatial index at a time.</span></span>  
  
### <a name="spatial-indexes-and-process-parallelism"></a><span data-ttu-id="45303-179">Indici spaziali e parallelismo di processi</span><span class="sxs-lookup"><span data-stu-id="45303-179">Spatial Indexes and Process Parallelism</span></span>  
 <span data-ttu-id="45303-180">Per la compilazione di un indice è possibile utilizzare il parallelismo di processi disponibile.</span><span class="sxs-lookup"><span data-stu-id="45303-180">An index build can use available process parallelism.</span></span>  
  
### <a name="version-restrictions"></a><span data-ttu-id="45303-181">Restrizioni della versione</span><span class="sxs-lookup"><span data-stu-id="45303-181">Version Restrictions</span></span>  
 <span data-ttu-id="45303-182">Non è possibile eseguire la replica di schemi a mosaico spaziali introdotti in [!INCLUDE[ssSQL11](../../../includes/sssql11-md.md)] in [!INCLUDE[ssKilimanjaro](../../../includes/sskilimanjaro-md.md)] o [!INCLUDE[ssKatmai](../../../includes/sskatmai-md.md)].</span><span class="sxs-lookup"><span data-stu-id="45303-182">Spatial tessellations introduced in [!INCLUDE[ssSQL11](../../../includes/sssql11-md.md)] cannot be replicated to [!INCLUDE[ssKilimanjaro](../../../includes/sskilimanjaro-md.md)] or [!INCLUDE[ssKatmai](../../../includes/sskatmai-md.md)].</span></span> <span data-ttu-id="45303-183">È necessario usare schemi a mosaico spaziali [!INCLUDE[ssKilimanjaro](../../../includes/sskilimanjaro-md.md)] o [!INCLUDE[ssKatmai](../../../includes/sskatmai-md.md)] per gli indici spaziali quando è necessario garantire la compatibilità con i database di [!INCLUDE[ssKilimanjaro](../../../includes/sskilimanjaro-md.md)] o [!INCLUDE[ssKatmai](../../../includes/sskatmai-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="45303-183">You must use [!INCLUDE[ssKilimanjaro](../../../includes/sskilimanjaro-md.md)] or [!INCLUDE[ssKatmai](../../../includes/sskatmai-md.md)] spatial tessellations for spatial indexes when backward compatibility with [!INCLUDE[ssKilimanjaro](../../../includes/sskilimanjaro-md.md)] or [!INCLUDE[ssKatmai](../../../includes/sskatmai-md.md)] databases is a requirement.</span></span>  
  
  
## <a name="see-also"></a><span data-ttu-id="45303-184">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="45303-184">See Also</span></span>  
 [<span data-ttu-id="45303-185">Panoramica degli indici spaziali</span><span class="sxs-lookup"><span data-stu-id="45303-185">Spatial Indexes Overview</span></span>](spatial-indexes-overview.md)  
  
  
