---
title: Guida sensibile al contesto di Proprietà indice | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: table-view-index
ms.topic: conceptual
f1_keywords:
- sql12.swb.indexproperties.storage.f1
- sql12.swb.indexproperties.columns.f1
- sql12.swb.indexproperties.partitions.f1
- sql12.swb.indexproperties.general.f1
- sql12.swb.indexproperties.filter.f1
- sql12.swb.indexproperties.options.f1
- sql12.swb.indexproperties.spatial.f1
ms.assetid: 45efd81a-3796-4b04-b0cc-f3deec94c733
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 390a63d21dc72e052017f2d30b061d71de863bc1
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87725723"
---
# <a name="index-properties-f1-help"></a><span data-ttu-id="30000-102">Guida sensibile al contesto di Proprietà indice</span><span class="sxs-lookup"><span data-stu-id="30000-102">Index Properties F1 Help</span></span>
  <span data-ttu-id="30000-103">Le sezioni in questo argomento fanno riferimento a varie proprietà di indice disponibili tramite le finestre di dialogo di [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="30000-103">The sections in this topic refer to various index properties that are available by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] dialogs.</span></span>  
  
 <span data-ttu-id="30000-104">**Contenuto dell'argomento:**</span><span class="sxs-lookup"><span data-stu-id="30000-104">**In This Topic:**</span></span>  
  
 [<span data-ttu-id="30000-105">Pagina Generale di Proprietà indice</span><span class="sxs-lookup"><span data-stu-id="30000-105">Index Properties General Page</span></span>](#General)  
  
 [<span data-ttu-id="30000-106">Finestra di dialogo Seleziona colonne (Indice)</span><span class="sxs-lookup"><span data-stu-id="30000-106">Select (Index) Columns Dialog Box</span></span>](#Columns)  
  
 [<span data-ttu-id="30000-107">Pagina Archiviazione di Proprietà indice</span><span class="sxs-lookup"><span data-stu-id="30000-107">Index Properties Storage Page</span></span>](#Storage)  
  
 [<span data-ttu-id="30000-108">Pagina Spaziale di Proprietà indice</span><span class="sxs-lookup"><span data-stu-id="30000-108">Index Properties Spatial Page</span></span>](#Spatial)  
  
 [<span data-ttu-id="30000-109">Pagina Filtro di Proprietà indice</span><span class="sxs-lookup"><span data-stu-id="30000-109">Index Properties Filter Page</span></span>](#Filter)  
  
##  <a name="index-properties-general-page"></a><a name="General"></a> <span data-ttu-id="30000-110">Pagina Generale di Proprietà indice</span><span class="sxs-lookup"><span data-stu-id="30000-110">Index Properties General Page</span></span>  
 <span data-ttu-id="30000-111">Usare la pagina Generale per visualizzare o modificare le proprietà di indice per la tabella o la vista selezionata.</span><span class="sxs-lookup"><span data-stu-id="30000-111">Use the General page to view or modify index properties for the selected table or view.</span></span> <span data-ttu-id="30000-112">Le opzioni per ogni pagina possono cambiare a seconda del tipo di indice selezionato.</span><span class="sxs-lookup"><span data-stu-id="30000-112">The options for each page may change based on the type of index selected.</span></span>  
  
 <span data-ttu-id="30000-113">**Nome tabella**</span><span class="sxs-lookup"><span data-stu-id="30000-113">**Table name**</span></span>  
 <span data-ttu-id="30000-114">Visualizza il nome della tabella o della vista in cui l'indice è stato creato.</span><span class="sxs-lookup"><span data-stu-id="30000-114">Displays the name of the table or view that the index was created on.</span></span> <span data-ttu-id="30000-115">Questo campo è di sola lettura.</span><span class="sxs-lookup"><span data-stu-id="30000-115">This field is read-only.</span></span> <span data-ttu-id="30000-116">Per selezionare una tabella diversa chiudere la pagina Proprietà indice, selezionare la tabella corretta e quindi riaprire la pagina Proprietà indice.</span><span class="sxs-lookup"><span data-stu-id="30000-116">To select a different table, close the Index Properties page, select the correct table, and then open the Index Properties page again.</span></span>  
  
 <span data-ttu-id="30000-117">Non è possibile specificare indici spaziali in viste indicizzate.</span><span class="sxs-lookup"><span data-stu-id="30000-117">Spatial indexes cannot be specified on indexed views.</span></span> <span data-ttu-id="30000-118">È possibile definire indici spaziali solo per una tabella con chiave primaria.</span><span class="sxs-lookup"><span data-stu-id="30000-118">Spatial indexes can be defined only for a table that has a primary key.</span></span> <span data-ttu-id="30000-119">Il numero massimo di colonne chiave primaria in una tabella è pari a 15.</span><span class="sxs-lookup"><span data-stu-id="30000-119">The maximum number of primary key columns on the table is 15.</span></span> <span data-ttu-id="30000-120">La dimensione combinata per riga delle colonne chiave primaria non può essere superiore a 895 byte.</span><span class="sxs-lookup"><span data-stu-id="30000-120">The combined per-row size of the primary-key columns is limited to a maximum of 895 bytes.</span></span>  
  
 <span data-ttu-id="30000-121">**Nome indice**</span><span class="sxs-lookup"><span data-stu-id="30000-121">**Index name**</span></span>  
 <span data-ttu-id="30000-122">Consente di visualizzare il nome dell'indice.</span><span class="sxs-lookup"><span data-stu-id="30000-122">Displays the name of the index.</span></span> <span data-ttu-id="30000-123">Per un indice esistente questo campo è di sola lettura.</span><span class="sxs-lookup"><span data-stu-id="30000-123">This field is read-only for an existing index.</span></span> <span data-ttu-id="30000-124">Quando si crea un nuovo indice, digitare il nome dell'indice.</span><span class="sxs-lookup"><span data-stu-id="30000-124">When creating a new index, type the name of the index.</span></span>  
  
 <span data-ttu-id="30000-125">**Tipo di indice**</span><span class="sxs-lookup"><span data-stu-id="30000-125">**Index type**</span></span>  
 <span data-ttu-id="30000-126">Indica il tipo di indice.</span><span class="sxs-lookup"><span data-stu-id="30000-126">Indicates the type of index.</span></span> <span data-ttu-id="30000-127">Per i nuovi indici, indica il tipo di indice selezionato all'apertura della finestra di dialogo.</span><span class="sxs-lookup"><span data-stu-id="30000-127">For new indexes, indicates the type of index selected when opening the dialog box.</span></span> <span data-ttu-id="30000-128">Gli indici possono essere: **Cluster**, **Non cluster**, **XML primario**, **XML secondario**, **Spaziale**, **Columnstore cluster** o **Columnstore non cluster**.</span><span class="sxs-lookup"><span data-stu-id="30000-128">Indexes can be: **Clustered**, **Nonclustered**, **Primary XML**, **Secondary XML**, **Spatial**, **Clustered columnstore**, or **Nonclustered Columnstore**.</span></span>  
  
 <span data-ttu-id="30000-129">**Nota** È consentito un solo indice cluster per ogni tabella.</span><span class="sxs-lookup"><span data-stu-id="30000-129">**Note** Only one clustered index is allowed for each table.</span></span> <span data-ttu-id="30000-130">È consentito un solo indice columnstore con ottimizzazione per la memoria xVelocity per ogni tabella.</span><span class="sxs-lookup"><span data-stu-id="30000-130">Only one xVelocity memory optimized columnstore index is allowed for each table.</span></span>  
  
 <span data-ttu-id="30000-131">**Univoco**</span><span class="sxs-lookup"><span data-stu-id="30000-131">**Unique**</span></span>  
 <span data-ttu-id="30000-132">Selezionando questa casella di controllo, si rende l'indice univoco.</span><span class="sxs-lookup"><span data-stu-id="30000-132">Selecting this check box makes the index unique.</span></span> <span data-ttu-id="30000-133">Due righe non potranno avere lo stesso valore di indice.</span><span class="sxs-lookup"><span data-stu-id="30000-133">No two rows are permitted to have the same index value.</span></span> <span data-ttu-id="30000-134">Per impostazione predefinita, tale casella di controllo è deselezionata.</span><span class="sxs-lookup"><span data-stu-id="30000-134">By default, this check box is cleared.</span></span> <span data-ttu-id="30000-135">Se due righe hanno lo stesso valore durante la modifica di un indice esistente, la creazione dell'indice avrà esito negativo.</span><span class="sxs-lookup"><span data-stu-id="30000-135">When modifying an existing index, index creation will fail if two rows have the same value.</span></span> <span data-ttu-id="30000-136">Per le colonne in cui sono consentiti valori Null, un indice univoco consente un solo valore Null.</span><span class="sxs-lookup"><span data-stu-id="30000-136">For columns where NULL is permitted, a unique index permits one NULL value.</span></span>  
  
 <span data-ttu-id="30000-137">Se nel campo **Tipo di indice** si seleziona **Spaziale** , la casella di controllo **Univoco** è visualizzata in grigio.</span><span class="sxs-lookup"><span data-stu-id="30000-137">If you select **Spatial** in the **Index type** field, the **Unique** check box is dimmed.</span></span>  
  
 <span data-ttu-id="30000-138">**Colonne chiave indice**</span><span class="sxs-lookup"><span data-stu-id="30000-138">**Index key columns**</span></span>  
 <span data-ttu-id="30000-139">Consente di aggiungere le colonne desiderate alla griglia **Colonne chiave indice** .</span><span class="sxs-lookup"><span data-stu-id="30000-139">Add the desired columns to the **Index key columns** grid.</span></span> <span data-ttu-id="30000-140">Quando viene aggiunta più di una colonna, le colonne devono essere elencate nell'ordine desiderato.</span><span class="sxs-lookup"><span data-stu-id="30000-140">When more than one column is added, the columns must be listed in the order desired.</span></span> <span data-ttu-id="30000-141">L'ordine delle colonne in un indice può influenzare notevolmente le prestazioni dell'indice.</span><span class="sxs-lookup"><span data-stu-id="30000-141">The column order in an index can have a great impact on the index performance.</span></span>  
  
 <span data-ttu-id="30000-142">Non è possibile includere più di 16 colonne in un solo indice composto.</span><span class="sxs-lookup"><span data-stu-id="30000-142">No more than 16 columns can participate in a single composite index.</span></span> <span data-ttu-id="30000-143">Per un numero di colonne maggiore di 16, vedere la sezione dedicata a included_columns alla fine di questo argomento.</span><span class="sxs-lookup"><span data-stu-id="30000-143">For greater than 16 columns, see included columns at the end of this topic.</span></span>  
  
 <span data-ttu-id="30000-144">È possibile definire un indice spaziale solo in una colonna che contiene un tipo di dati spaziali ( *colonna spaziale*).</span><span class="sxs-lookup"><span data-stu-id="30000-144">A spatial index can be defined only on a single column that contains a spatial data type (a *spatial column*).</span></span>  
  
 <span data-ttu-id="30000-145">**Nome**</span><span class="sxs-lookup"><span data-stu-id="30000-145">**Name**</span></span>  
 <span data-ttu-id="30000-146">Consente di visualizzare il nome della colonna che partecipa alla chiave dell'indice.</span><span class="sxs-lookup"><span data-stu-id="30000-146">Displays the name of the column that participates in the index key.</span></span>  
  
 <span data-ttu-id="30000-147">**Ordinamento**</span><span class="sxs-lookup"><span data-stu-id="30000-147">**Sort Order**</span></span>  
 <span data-ttu-id="30000-148">Consente di specificare la direzione di ordinamento, **Crescente** o **Decrescente**, della colonna dell'indice selezionata.</span><span class="sxs-lookup"><span data-stu-id="30000-148">Specifies the sort direction of the selected index column, either **Ascending** or **Descending**.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="30000-149">Se il tipo di indice è **XML primario** o **Spaziale**, questa colonna non viene visualizzata nella tabella.</span><span class="sxs-lookup"><span data-stu-id="30000-149">If the index type is **Primary XML** or **Spatial**, this column does not appear in the table.</span></span>  
  
 <span data-ttu-id="30000-150">**Tipo di dati**</span><span class="sxs-lookup"><span data-stu-id="30000-150">**Data Type**</span></span>  
 <span data-ttu-id="30000-151">Consente di visualizzare informazioni sul tipo di dati.</span><span class="sxs-lookup"><span data-stu-id="30000-151">Displays the data type information.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="30000-152">Se la colonna della tabella è una colonna calcolata, l'opzione **Tipo di dati** visualizza "colonna calcolata".</span><span class="sxs-lookup"><span data-stu-id="30000-152">If the table column is a computed column, **Data type** displays "computed column."</span></span>  
  
 <span data-ttu-id="30000-153">**Dimensione**</span><span class="sxs-lookup"><span data-stu-id="30000-153">**Size**</span></span>  
 <span data-ttu-id="30000-154">Consente di visualizzare il numero massimo di byte necessari per archiviare il tipo di dati della colonna.</span><span class="sxs-lookup"><span data-stu-id="30000-154">Displays the maximum number of bytes required to store the column data type.</span></span> <span data-ttu-id="30000-155">In caso di colonna spaziale o XML, il valore visualizzato è zero (0).</span><span class="sxs-lookup"><span data-stu-id="30000-155">Displays zero (0) for a spatial or XML column.</span></span>  
  
 <span data-ttu-id="30000-156">**Identità**</span><span class="sxs-lookup"><span data-stu-id="30000-156">**Identity**</span></span>  
 <span data-ttu-id="30000-157">Indica se la colonna che partecipa alla chiave dell'indice è una colonna Identity.</span><span class="sxs-lookup"><span data-stu-id="30000-157">Displays whether the column participating in the index key is an identity column.</span></span>  
  
 <span data-ttu-id="30000-158">**Consenti valori Null**</span><span class="sxs-lookup"><span data-stu-id="30000-158">**Allow NULLs**</span></span>  
 <span data-ttu-id="30000-159">Indica se la colonna che partecipa alla chiave dell'indice consente l'archiviazione di valori Null nella colonna della tabella o della vista.</span><span class="sxs-lookup"><span data-stu-id="30000-159">Displays whether the column participating in the index key allows NULL values to be stored in the table or view column.</span></span>  
  
 <span data-ttu-id="30000-160">**Aggiungere**</span><span class="sxs-lookup"><span data-stu-id="30000-160">**Add**</span></span>  
 <span data-ttu-id="30000-161">Consente di aggiungere una colonna alla chiave dell'indice.</span><span class="sxs-lookup"><span data-stu-id="30000-161">Adds a column to the index key.</span></span> <span data-ttu-id="30000-162">Selezionare le colonne della tabella nella finestra di dialogo **Seleziona colonne da** *\<table name>* che viene visualizzata quando si fa clic su **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="30000-162">Select table columns from the **Select Columns from** *\<table name>* dialog box that appears when you click **Add**.</span></span> <span data-ttu-id="30000-163">In caso di indice spaziale, questo pulsante viene visualizzato in grigio dopo la selezione di una colonna.</span><span class="sxs-lookup"><span data-stu-id="30000-163">For a spatial index, after you select one column, this button is dimmed.</span></span>  
  
 <span data-ttu-id="30000-164">**Rimuovi**</span><span class="sxs-lookup"><span data-stu-id="30000-164">**Remove**</span></span>  
 <span data-ttu-id="30000-165">Consente di rimuovere la colonna selezionata dalla partecipazione alla chiave dell'indice.</span><span class="sxs-lookup"><span data-stu-id="30000-165">Removes the selected column from participation in the index key.</span></span>  
  
 <span data-ttu-id="30000-166">**Sposta su**</span><span class="sxs-lookup"><span data-stu-id="30000-166">**Move Up**</span></span>  
 <span data-ttu-id="30000-167">Consente di spostare verso l'alto la colonna selezionata nella griglia della chiave dell'indice.</span><span class="sxs-lookup"><span data-stu-id="30000-167">Moves the selected column up in the index key grid.</span></span>  
  
 <span data-ttu-id="30000-168">**Sposta giù**</span><span class="sxs-lookup"><span data-stu-id="30000-168">**Move Down**</span></span>  
 <span data-ttu-id="30000-169">Consente di spostare verso il basso la colonna selezionata nella griglia della chiave dell'indice.</span><span class="sxs-lookup"><span data-stu-id="30000-169">Moves the selected column down in the index key grid.</span></span>  
  
 <span data-ttu-id="30000-170">**Colonne columnstore**</span><span class="sxs-lookup"><span data-stu-id="30000-170">**Columnstore columns**</span></span>  
 <span data-ttu-id="30000-171">Fare clic su **Aggiungi** per selezionare le colonne per l'indice columnstore.</span><span class="sxs-lookup"><span data-stu-id="30000-171">Click **Add** to select columns for the columnstore index.</span></span> <span data-ttu-id="30000-172">Per le limitazioni in un indice columnstore, vedere [CREATE COLUMNSTORE INDEX &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-columnstore-index-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="30000-172">For limitations on a columnstore index, see [CREATE COLUMNSTORE INDEX &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-columnstore-index-transact-sql).</span></span>  
  
 <span data-ttu-id="30000-173">**included_columns**</span><span class="sxs-lookup"><span data-stu-id="30000-173">**Included columns**</span></span>  
 <span data-ttu-id="30000-174">Consente di includere colonne non chiave nell'indice non cluster.</span><span class="sxs-lookup"><span data-stu-id="30000-174">Include nonkey columns in the nonclustered index.</span></span> <span data-ttu-id="30000-175">Questa opzione consente di ignorare i limiti dell'indice corrente relativi alle dimensioni totali di una chiave di indice e il numero massimo di colonne che fanno parte di una chiave di indice aggiungendo colonne come colonne non chiave nel livello foglia dell'indice non cluster.</span><span class="sxs-lookup"><span data-stu-id="30000-175">This option allows you to bypass the current index limits on the total size of an index key and the maximum number of columns participating in an index key by adding columns as nonkey columns in the leaf level of the nonclustered index.</span></span> <span data-ttu-id="30000-176">Per altre informazioni, vedere [Creare indici con colonne incluse](create-indexes-with-included-columns.md).</span><span class="sxs-lookup"><span data-stu-id="30000-176">For more information, see [Create Indexes with Included Columns](create-indexes-with-included-columns.md)</span></span>  
  
##  <a name="select-index-columns-dialog-box"></a><a name="Columns"></a> <span data-ttu-id="30000-177">Finestra di dialogo Seleziona colonne (Indice)</span><span class="sxs-lookup"><span data-stu-id="30000-177">Select (Index) Columns Dialog Box</span></span>  
 <span data-ttu-id="30000-178">Usare questa pagina per aggiungere colonne alla pagina Generale di **Proprietà indice** durante la creazione o la modifica di un indice.</span><span class="sxs-lookup"><span data-stu-id="30000-178">Use this page to add columns to the **Index Properties General** page when creating or modifying an index.</span></span>  
  
 <span data-ttu-id="30000-179">**Casella di controllo**</span><span class="sxs-lookup"><span data-stu-id="30000-179">**Check box**</span></span>  
 <span data-ttu-id="30000-180">È possibile selezionare le caselle di controllo per aggiungere le colonne desiderate.</span><span class="sxs-lookup"><span data-stu-id="30000-180">Select to add columns.</span></span>  
  
 <span data-ttu-id="30000-181">**Nome**</span><span class="sxs-lookup"><span data-stu-id="30000-181">**Name**</span></span>  
 <span data-ttu-id="30000-182">Nome della colonna.</span><span class="sxs-lookup"><span data-stu-id="30000-182">Name of the column.</span></span>  
  
 <span data-ttu-id="30000-183">**Tipo di dati**</span><span class="sxs-lookup"><span data-stu-id="30000-183">**Data Type**</span></span>  
 <span data-ttu-id="30000-184">Tipo di dati della colonna.</span><span class="sxs-lookup"><span data-stu-id="30000-184">The data type of the column.</span></span>  
  
 <span data-ttu-id="30000-185">**Byte**</span><span class="sxs-lookup"><span data-stu-id="30000-185">**Bytes**</span></span>  
 <span data-ttu-id="30000-186">Dimensioni in byte della colonna.</span><span class="sxs-lookup"><span data-stu-id="30000-186">The size of the column in bytes.</span></span>  
  
 <span data-ttu-id="30000-187">**Identità**</span><span class="sxs-lookup"><span data-stu-id="30000-187">**Identity**</span></span>  
 <span data-ttu-id="30000-188">Il valore indicato è **Sì** per le colonne Identity oppure **No** se la colonna non è di tipo Identity.</span><span class="sxs-lookup"><span data-stu-id="30000-188">Displays **Yes** for identity columns, and **No** when the column is not an identity column.</span></span>  
  
 <span data-ttu-id="30000-189">**Consenti valori NULL**</span><span class="sxs-lookup"><span data-stu-id="30000-189">**Allow Nulls**</span></span>  
 <span data-ttu-id="30000-190">Il valore indicato è **Sì** se la definizione della tabella consente valori Null per la colonna.</span><span class="sxs-lookup"><span data-stu-id="30000-190">Displays **Yes** when the table definition allows null values for the column.</span></span> <span data-ttu-id="30000-191">oppure **No** se la definizione della tabella non consente valori Null per la colonna.</span><span class="sxs-lookup"><span data-stu-id="30000-191">Displays **No** when the table definition does not allow nulls for the column.</span></span>  
  
##  <a name="storage-page-options"></a><a name="Storage"></a> <span data-ttu-id="30000-192">Opzioni della pagina Archiviazione</span><span class="sxs-lookup"><span data-stu-id="30000-192">Storage Page Options</span></span>  
 <span data-ttu-id="30000-193">Usare questa pagina per visualizzare o modificare proprietà di filegroup o di schemi di partizione per l'indice selezionato.</span><span class="sxs-lookup"><span data-stu-id="30000-193">Use this page to view or modify filegroup or partition scheme properties for the selected index.</span></span> <span data-ttu-id="30000-194">Vengono mostrate solo le opzioni correlate al tipo di indice.</span><span class="sxs-lookup"><span data-stu-id="30000-194">Only shows options related to the type of index.</span></span>  
  
 <span data-ttu-id="30000-195">**Filegroup**</span><span class="sxs-lookup"><span data-stu-id="30000-195">**Filegroup**</span></span>  
 <span data-ttu-id="30000-196">Archivia l'indice nel filegroup specificato.</span><span class="sxs-lookup"><span data-stu-id="30000-196">Stores the index in the specified filegroup.</span></span> <span data-ttu-id="30000-197">Nell'elenco sono visualizzati solo filegroup standard (ROW).</span><span class="sxs-lookup"><span data-stu-id="30000-197">The list only displays standard (row) filegroups.</span></span> <span data-ttu-id="30000-198">La selezione predefinita nell'elenco è il filegroup PRIMARY del database.</span><span class="sxs-lookup"><span data-stu-id="30000-198">The default list selection is the PRIMARY filegroup of the database.</span></span> <span data-ttu-id="30000-199">Per altre informazioni, vedere [Database Files and Filegroups](../databases/database-files-and-filegroups.md).</span><span class="sxs-lookup"><span data-stu-id="30000-199">For more information, see [Database Files and Filegroups](../databases/database-files-and-filegroups.md).</span></span>  
  
 <span data-ttu-id="30000-200">**Filegroup FILESTREAM**</span><span class="sxs-lookup"><span data-stu-id="30000-200">**Filestream filegroup**</span></span>  
 <span data-ttu-id="30000-201">Specifica il filegroup per i dati FILESTREAM.</span><span class="sxs-lookup"><span data-stu-id="30000-201">Specifies the filegroup for FILESTREAM data.</span></span> <span data-ttu-id="30000-202">Questo elenco visualizza solo i filegroup FILESTREAM.</span><span class="sxs-lookup"><span data-stu-id="30000-202">This list displays only FILESTREAM filegroups.</span></span> <span data-ttu-id="30000-203">La selezione predefinita nell'elenco è il filegroup PRIMARY FILESTREAM del database.</span><span class="sxs-lookup"><span data-stu-id="30000-203">The default list selection is the PRIMARY FILESTREAM filegroup.</span></span> <span data-ttu-id="30000-204">Per altre informazioni, vedere [FILESTREAM &#40;SQL Server&#41;](../blob/filestream-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="30000-204">For more information, see [FILESTREAM &#40;SQL Server&#41;](../blob/filestream-sql-server.md).</span></span>  
  
 <span data-ttu-id="30000-205">**Schema di partizione**</span><span class="sxs-lookup"><span data-stu-id="30000-205">**Partition scheme**</span></span>  
 <span data-ttu-id="30000-206">Archivia l'indice in uno schema di partizione.</span><span class="sxs-lookup"><span data-stu-id="30000-206">Stores the index in a partition scheme.</span></span> <span data-ttu-id="30000-207">Facendo clic su **Schema partizione** si abilita la griglia sottostante.</span><span class="sxs-lookup"><span data-stu-id="30000-207">Clicking **Partition Scheme** enables the grid below.</span></span> <span data-ttu-id="30000-208">La selezione predefinita nell'elenco è lo schema di partizione usato per archiviare i dati di tabella.</span><span class="sxs-lookup"><span data-stu-id="30000-208">The default list selection is the partition scheme that is used for storing the table data.</span></span> <span data-ttu-id="30000-209">Selezionando uno schema di partizione diverso nell'elenco si aggiornano le informazioni visualizzate nella griglia.</span><span class="sxs-lookup"><span data-stu-id="30000-209">When you select a different partition scheme in the list, the information in the grid is updated.</span></span> <span data-ttu-id="30000-210">Per ulteriori informazioni, vedere [Partitioned Tables and Indexes](../partitions/partitioned-tables-and-indexes.md).</span><span class="sxs-lookup"><span data-stu-id="30000-210">For more information, see [Partitioned Tables and Indexes](../partitions/partitioned-tables-and-indexes.md).</span></span>  
  
 <span data-ttu-id="30000-211">L'opzione relativa allo schema di partizione non è disponibile se il database non contiene schemi di partizione.</span><span class="sxs-lookup"><span data-stu-id="30000-211">The partition scheme option is unavailable if there are no partition schemes in the database.</span></span>  
  
 <span data-ttu-id="30000-212">**Schema di partizione FILESTREAM**</span><span class="sxs-lookup"><span data-stu-id="30000-212">**Filestream partition scheme**</span></span>  
 <span data-ttu-id="30000-213">Specifica lo schema di partizione per i dati FILESTREAM.</span><span class="sxs-lookup"><span data-stu-id="30000-213">Specifies the partition scheme for FILESTREAM data.</span></span> <span data-ttu-id="30000-214">Lo schema di partizione deve essere simmetrico con la combinazione specificata nell'opzione **Schema partizione** .</span><span class="sxs-lookup"><span data-stu-id="30000-214">The partition scheme must be symmetric with the scheme that is specified in the **Partition scheme** option.</span></span>  
  
 <span data-ttu-id="30000-215">Se la tabella non è partizionata, il campo è vuoto.</span><span class="sxs-lookup"><span data-stu-id="30000-215">If the table is not partitioned, the field is blank.</span></span>  
  
 <span data-ttu-id="30000-216">**Parametro schema partizione**</span><span class="sxs-lookup"><span data-stu-id="30000-216">**Partition Scheme Parameter**</span></span>  
 <span data-ttu-id="30000-217">Consente di visualizzare il nome della colonna che partecipa allo schema di partizione.</span><span class="sxs-lookup"><span data-stu-id="30000-217">Displays the name of the column that participates in the partition scheme.</span></span>  
  
 <span data-ttu-id="30000-218">**Colonne della tabella**</span><span class="sxs-lookup"><span data-stu-id="30000-218">**Table Column**</span></span>  
 <span data-ttu-id="30000-219">Consente di selezionare la tabella o la vista su cui eseguire il mapping allo schema di partizione.</span><span class="sxs-lookup"><span data-stu-id="30000-219">Select the table or view to map to the partition scheme.</span></span>  
  
 <span data-ttu-id="30000-220">**Tipo di dati colonna**</span><span class="sxs-lookup"><span data-stu-id="30000-220">**Column Data Type**</span></span>  
 <span data-ttu-id="30000-221">Consente di visualizzare le informazioni sul tipo di dati relative alla colonna.</span><span class="sxs-lookup"><span data-stu-id="30000-221">Displays data type information about the column.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="30000-222">Se la colonna della tabella è una colonna calcolata, l'opzione **Tipo di dati colonna** visualizza "colonna calcolata".</span><span class="sxs-lookup"><span data-stu-id="30000-222">If the table column is a computed column, **Column Data Type** displays "computed column."</span></span>  
  
 <span data-ttu-id="30000-223">**Consenti elaborazione online di istruzioni DML durante lo spostamento dell'indice**</span><span class="sxs-lookup"><span data-stu-id="30000-223">**Allow online processing of DML statements while moving the index**</span></span>  
 <span data-ttu-id="30000-224">Consente agli utenti di accedere ai dati della tabella o dell'indice cluster sottostanti e a eventuali indici non cluster associati durante l'operazione sull'indice.</span><span class="sxs-lookup"><span data-stu-id="30000-224">Allows users to access the underlying table or clustered index data and any associated nonclustered indexes during the index operation.</span></span> <span data-ttu-id="30000-225">Per altre informazioni, vedere [Perform Index Operations Online](perform-index-operations-online.md).</span><span class="sxs-lookup"><span data-stu-id="30000-225">For more information, see [Perform Index Operations Online](perform-index-operations-online.md).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="30000-226">Questa opzione non è disponibile per gli indici XML o se l'indice è un indice cluster disabilitato.</span><span class="sxs-lookup"><span data-stu-id="30000-226">This option is not available for XML indexes, or if the index is a disabled clustered index.</span></span>  
  
 <span data-ttu-id="30000-227">**Imposta massimo grado di parallelismo**</span><span class="sxs-lookup"><span data-stu-id="30000-227">**Set maximum degree of parallelism**</span></span>  
 <span data-ttu-id="30000-228">Consente di limitare il numero di processori da usare durante l'esecuzione di piani paralleli.</span><span class="sxs-lookup"><span data-stu-id="30000-228">Limits the number of processors to use during parallel plan execution.</span></span> <span data-ttu-id="30000-229">Il valore predefinito è 0 e corrisponde al numero effettivo di CPU disponibili.</span><span class="sxs-lookup"><span data-stu-id="30000-229">The default value, 0, uses the actual number of available CPUs.</span></span> <span data-ttu-id="30000-230">L'impostazione del valore su 1 impedisce la generazione di piani paralleli. L'impostazione del valore su un numero maggiore di 1 limita il numero massimo di processori usati da una singola esecuzione della query.</span><span class="sxs-lookup"><span data-stu-id="30000-230">Setting the value to 1 suppresses parallel plan generation; setting the value to a number greater than 1 restricts the maximum number of processors used by a single query execution.</span></span> <span data-ttu-id="30000-231">Questa opzione diventa disponibile solo se la finestra di dialogo è nello stato **Ricompila** o **Ricrea** .</span><span class="sxs-lookup"><span data-stu-id="30000-231">This option only becomes available if the dialog box is in the **Rebuild** or **Recreate** state.</span></span> <span data-ttu-id="30000-232">Per altre informazioni, vedere [Impostazione dell'opzione relativa al massimo grado di parallelismo per ottenere prestazioni ottimali](../policy-based-management/set-the-max-degree-of-parallelism-option-for-optimal-performance.md).</span><span class="sxs-lookup"><span data-stu-id="30000-232">For more information, see [Set the Max Degree of Parallelism Option for Optimal Performance](../policy-based-management/set-the-max-degree-of-parallelism-option-for-optimal-performance.md).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="30000-233">Se viene specificato un valore maggiore del numero di CPU disponibili, verrà usato l'effettivo numero di CPU disponibili.</span><span class="sxs-lookup"><span data-stu-id="30000-233">If a value greater than the number of available CPUs is specified, the actual number of available CPUs is used.</span></span>  
  
##  <a name="spatial-page-index-options"></a><a name="Spatial"></a> <span data-ttu-id="30000-234">Opzioni di indice della pagina Spaziale</span><span class="sxs-lookup"><span data-stu-id="30000-234">Spatial Page Index Options</span></span>  
 <span data-ttu-id="30000-235">Usare la pagina **Spaziale** per visualizzare o specificare i valori delle proprietà spaziali.</span><span class="sxs-lookup"><span data-stu-id="30000-235">Use the **Spatial** page to view or specify the values of the spatial properties.</span></span> <span data-ttu-id="30000-236">Per altre informazioni, vedere [Dati spaziali &#40;SQL Server&#41;](../spatial/spatial-data-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="30000-236">For more information, see [Spatial Data &#40;SQL Server&#41;](../spatial/spatial-data-sql-server.md).</span></span>  
  
### <a name="bounding-box"></a><span data-ttu-id="30000-237">Riquadro</span><span class="sxs-lookup"><span data-stu-id="30000-237">Bounding Box</span></span>  
 <span data-ttu-id="30000-238">Si definisce *riquadro* il perimetro della griglia di livello principale di un piano geometrico.</span><span class="sxs-lookup"><span data-stu-id="30000-238">The *bounding box* is the perimeter of the top-level grid of a geometric plane.</span></span> <span data-ttu-id="30000-239">I parametri del riquadro sono presenti solo nello schema a mosaico griglia geometrica.</span><span class="sxs-lookup"><span data-stu-id="30000-239">The bounding-box parameters exist only in the geometry grid tessellation.</span></span> <span data-ttu-id="30000-240">Questi parametri non sono disponibili se **Schema a mosaico** è impostato su **Griglia geografica**.</span><span class="sxs-lookup"><span data-stu-id="30000-240">These parameters are unavailable if the **Tessellation Scheme** is **Geography grid**.</span></span>  
  
 <span data-ttu-id="30000-241">Nel pannello vengono visualizzate le coordinate **( *`X-min`* , *`Y-min`* )** e **( *`X-max`* , *`Y-max`* )** del rettangolo di delimitazione.</span><span class="sxs-lookup"><span data-stu-id="30000-241">The panel displays the **(*`X-min`*,*`Y-min`*)** and **(*`X-max`*,*`Y-max`*)** coordinates of the bounding box.</span></span> <span data-ttu-id="30000-242">Non esistono valori predefiniti,</span><span class="sxs-lookup"><span data-stu-id="30000-242">There are no default coordinate values.</span></span> <span data-ttu-id="30000-243">pertanto, quando si crea un indice spaziale nuovo su una colonna di tipo `geometry`, è necessario specificare i valori delle coordinate.</span><span class="sxs-lookup"><span data-stu-id="30000-243">Therefore, when you are creating a new spatial index on a `geometry` type column, you must specify the coordinate values.</span></span>  
  
 `X-min`  
 <span data-ttu-id="30000-244">La coordinata X dell'angolo inferiore sinistro del riquadro.</span><span class="sxs-lookup"><span data-stu-id="30000-244">The X-coordinate of the lower-left corner of the bounding box.</span></span>  
  
 `Y-min`  
 <span data-ttu-id="30000-245">La coordinata Y dell'angolo inferiore sinistro del riquadro.</span><span class="sxs-lookup"><span data-stu-id="30000-245">The Y-coordinate of the lower-left corner of the bounding box.</span></span>  
  
 `X-max`  
 <span data-ttu-id="30000-246">La coordinata X dell'angolo superiore destro del riquadro.</span><span class="sxs-lookup"><span data-stu-id="30000-246">The X-coordinate of the upper-right corner of the bounding box.</span></span>  
  
 `Y-max`  
 <span data-ttu-id="30000-247">La coordinata Y dell'angolo superiore destro del riquadro.</span><span class="sxs-lookup"><span data-stu-id="30000-247">The Y-coordinate of upper-right corner of the bounding box.</span></span>  
  
### <a name="general"></a><span data-ttu-id="30000-248">Generale</span><span class="sxs-lookup"><span data-stu-id="30000-248">General</span></span>  
 <span data-ttu-id="30000-249">**Schema a mosaico**</span><span class="sxs-lookup"><span data-stu-id="30000-249">**Tessellation Scheme**</span></span>  
 <span data-ttu-id="30000-250">Indica lo schema a mosaico dell'indice.</span><span class="sxs-lookup"><span data-stu-id="30000-250">Indicates the tessellation scheme of the index.</span></span> <span data-ttu-id="30000-251">Sono supportati gli schemi a mosaico seguenti.</span><span class="sxs-lookup"><span data-stu-id="30000-251">The supported tessellation schemes are as follows.</span></span>  
  
 <span data-ttu-id="30000-252">**Griglia geometrica**</span><span class="sxs-lookup"><span data-stu-id="30000-252">**Geometry grid**</span></span>  
 <span data-ttu-id="30000-253">Specifica lo schema a mosaico per griglia geometrica che viene applicato a una colonna del tipo di dati `geometry`.</span><span class="sxs-lookup"><span data-stu-id="30000-253">Specifies the geometry grid tessellation scheme, which applies to a column of the `geometry` data type.</span></span>  
  
 <span data-ttu-id="30000-254">**Griglia geometrica automatica**</span><span class="sxs-lookup"><span data-stu-id="30000-254">**Geometry Auto grid**</span></span>  
 <span data-ttu-id="30000-255">Questa opzione è abilitata per [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] quando il livello di compatibilità del database è impostato su 110 o su un valore maggiore.</span><span class="sxs-lookup"><span data-stu-id="30000-255">This option is enabled for [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] when database compatibility level is set to 110 or higher.</span></span>  
  
 <span data-ttu-id="30000-256">**Griglia geografica**</span><span class="sxs-lookup"><span data-stu-id="30000-256">**Geography grid**</span></span>  
 <span data-ttu-id="30000-257">Specifica lo schema a mosaico per griglia geografica che viene applicato a una colonna con il tipo di dati **geography** .</span><span class="sxs-lookup"><span data-stu-id="30000-257">Specifies the geography grid tessellation scheme, which applies to a column of the **geography** data type.</span></span>  
  
 <span data-ttu-id="30000-258">**Griglia geografica automatica**</span><span class="sxs-lookup"><span data-stu-id="30000-258">**Geography Auto grid**</span></span>  
 <span data-ttu-id="30000-259">Questa opzione è abilitata per [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] quando il livello di compatibilità del database è impostato su 110 o su un valore maggiore.</span><span class="sxs-lookup"><span data-stu-id="30000-259">This option is enabled for [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] when database compatibility level is set to 110 or higher.</span></span>  
  
 <span data-ttu-id="30000-260">Per informazioni sull'implementazione dello schema a mosaico in [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)], vedere [Dati spaziali &#40;SQL Server&#41;](../spatial/spatial-data-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="30000-260">For information about how [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] implements tessellation, see [Spatial Data &#40;SQL Server&#41;](../spatial/spatial-data-sql-server.md).</span></span>  
  
 <span data-ttu-id="30000-261">**Celle per oggetto**</span><span class="sxs-lookup"><span data-stu-id="30000-261">**Cells Per Object**</span></span>  
 <span data-ttu-id="30000-262">Indica il numero di celle per oggetto di mosaico utilizzabile per un singolo oggetto spaziale nell'indice.</span><span class="sxs-lookup"><span data-stu-id="30000-262">Indicates the number of tessellation cells-per-object that can be used for a single spatial object in the index.</span></span> <span data-ttu-id="30000-263">È possibile usare qualsiasi numero intero compreso tra 1 e 8192.</span><span class="sxs-lookup"><span data-stu-id="30000-263">This number can be any integer between 1 and 8192, inclusive.</span></span> <span data-ttu-id="30000-264">Quando il livello di compatibilità del database è impostato su 110 o su un valore maggiore, il valore predefinito è 16, mentre è 8 per le versioni precedenti di [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="30000-264">The default is 16, and 8 for earlier versions of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] when database compatibility level is set to 110 or higher.</span></span>  
  
 <span data-ttu-id="30000-265">Se al livello principale un oggetto include più celle rispetto a quanto specificato da *n*, l'indicizzazione usa il numero di celle necessario per offrire uno schema a mosaico di livello principale completo.</span><span class="sxs-lookup"><span data-stu-id="30000-265">At the top level, if an object covers more cells than specified by *n*, the indexing uses as many cells as necessary to provide a complete top-level tessellation.</span></span> <span data-ttu-id="30000-266">In tali casi un oggetto può ricevere un numero di celle maggiore di quello specificato:</span><span class="sxs-lookup"><span data-stu-id="30000-266">In such cases, an object might receive more than the specified number of cells.</span></span> <span data-ttu-id="30000-267">il numero massimo è il numero di celle generate dalla griglia di livello principale che dipende dalla densità di **Livello 1** .</span><span class="sxs-lookup"><span data-stu-id="30000-267">In this case, the maximum number is the number of cells generated by the top-level grid, which depends on the **Level 1** density.</span></span>  
  
### <a name="grids"></a><span data-ttu-id="30000-268">Griglie</span><span class="sxs-lookup"><span data-stu-id="30000-268">Grids</span></span>  
 <span data-ttu-id="30000-269">In questo pannello è visualizzata la densità della griglia a ogni livello dello schema a mosaico.</span><span class="sxs-lookup"><span data-stu-id="30000-269">This panel shows the density of the grid at each level of the tessellation scheme.</span></span> <span data-ttu-id="30000-270">Le opzioni disponibili sono **Bassa**, **Media**o **Alta**.</span><span class="sxs-lookup"><span data-stu-id="30000-270">Density is specified as **Low**, **Medium**, or **High**.</span></span> <span data-ttu-id="30000-271">Il valore predefinito è **Media**.</span><span class="sxs-lookup"><span data-stu-id="30000-271">The default is **Medium**.</span></span> <span data-ttu-id="30000-272">**Bassa** rappresenta una griglia 4x4 (16 celle), **Media** una griglia 8x8 (64 celle) e **Alta** una griglia 16x16 (256 celle).</span><span class="sxs-lookup"><span data-stu-id="30000-272">**Low** represents a 4x4 grid (16 cells), **Medium** represents an 8x8 grid (64 cells), and **High** represents a 16x16 grid (256 cells).</span></span> <span data-ttu-id="30000-273">Queste opzioni non sono disponibili se si scelgono le opzioni di schema a mosaico **Griglia geometrica automatica** o **Griglia geografica automatica** .</span><span class="sxs-lookup"><span data-stu-id="30000-273">These options are not available when the **Geometry Auto grid** or **Geography Auto grid** tessellation options are chosen.</span></span>  
  
 <span data-ttu-id="30000-274">**Livello 1**</span><span class="sxs-lookup"><span data-stu-id="30000-274">**Level 1**</span></span>  
 <span data-ttu-id="30000-275">Densità della griglia di primo livello (principale).</span><span class="sxs-lookup"><span data-stu-id="30000-275">The density of the first-level (top) grid.</span></span>  
  
 <span data-ttu-id="30000-276">**Livello 2**</span><span class="sxs-lookup"><span data-stu-id="30000-276">**Level 2**</span></span>  
 <span data-ttu-id="30000-277">Densità della griglia di secondo livello.</span><span class="sxs-lookup"><span data-stu-id="30000-277">The density of the second-level grid.</span></span>  
  
 <span data-ttu-id="30000-278">**Livello 3**</span><span class="sxs-lookup"><span data-stu-id="30000-278">**Level 3**</span></span>  
 <span data-ttu-id="30000-279">Densità della griglia di terzo livello.</span><span class="sxs-lookup"><span data-stu-id="30000-279">The density of the third-level grid.</span></span>  
  
 <span data-ttu-id="30000-280">**Livello 4**</span><span class="sxs-lookup"><span data-stu-id="30000-280">**Level 4**</span></span>  
 <span data-ttu-id="30000-281">Densità della griglia di quarto livello.</span><span class="sxs-lookup"><span data-stu-id="30000-281">The density of the fourth-level grid.</span></span>  
  
##  <a name="filter-page"></a><a name="Filter"></a> <span data-ttu-id="30000-282">Pagina Filtro</span><span class="sxs-lookup"><span data-stu-id="30000-282">Filter Page</span></span>  
 <span data-ttu-id="30000-283">Usare questa pagina per immettere il predicato del filtro per un indice filtrato.</span><span class="sxs-lookup"><span data-stu-id="30000-283">Use this page to enter the filter predicate for a filtered index.</span></span> <span data-ttu-id="30000-284">Per altre informazioni, vedere [Create Filtered Indexes](create-filtered-indexes.md).</span><span class="sxs-lookup"><span data-stu-id="30000-284">For more information, see [Create Filtered Indexes](create-filtered-indexes.md).</span></span>  
  
 <span data-ttu-id="30000-285">**Espressione filtro**</span><span class="sxs-lookup"><span data-stu-id="30000-285">**Filter Expression**</span></span>  
 <span data-ttu-id="30000-286">Definisce le righe di dati da includere nell'indice filtrato.</span><span class="sxs-lookup"><span data-stu-id="30000-286">Defines which data rows to include in the filtered index.</span></span> <span data-ttu-id="30000-287">Ad esempio, usare `StartDate > '20000101' AND EndDate IS NOT NULL'.`</span><span class="sxs-lookup"><span data-stu-id="30000-287">For example, `StartDate > '20000101' AND EndDate IS NOT NULL'.`</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="30000-288">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="30000-288">See Also</span></span>  
 <span data-ttu-id="30000-289">[Impostare le opzioni di indice](set-index-options.md) </span><span class="sxs-lookup"><span data-stu-id="30000-289">[Set Index Options](set-index-options.md) </span></span>  
 <span data-ttu-id="30000-290">[INDEXPROPERTY &#40;Transact-SQL&#41;](/sql/t-sql/functions/indexproperty-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="30000-290">[INDEXPROPERTY &#40;Transact-SQL&#41;](/sql/t-sql/functions/indexproperty-transact-sql) </span></span>  
 [<span data-ttu-id="30000-291">sys.indexes &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="30000-291">sys.indexes &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-catalog-views/sys-indexes-transact-sql)  
  
  
