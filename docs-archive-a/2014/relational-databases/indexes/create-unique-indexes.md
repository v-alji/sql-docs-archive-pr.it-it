---
title: Creare indici univoci | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: table-view-index
ms.topic: conceptual
helpviewer_keywords:
- unique indexes
- designing indexes [SQL Server], unique
- clustered indexes, unique
- indexes [SQL Server], unique
- nonclustered indexes [SQL Server], unique
- unique indexes, design guidelines
ms.assetid: 56b5982e-cb94-46c0-8fbb-772fc275354a
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 8c96c4e17a8ce0863452db171302d650f6114919
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87724623"
---
# <a name="create-unique-indexes"></a><span data-ttu-id="98b69-102">Creare indici univoci</span><span class="sxs-lookup"><span data-stu-id="98b69-102">Create Unique Indexes</span></span>
  <span data-ttu-id="98b69-103">In questo argomento si illustra come creare un indice univoco per una tabella in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] tramite [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] o [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="98b69-103">This topic describes how to create a unique index on a table in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span> <span data-ttu-id="98b69-104">Un indice univoco consente di garantire che nella chiave dell'indice non siano contenuti valori duplicati e che pertanto ogni riga della tabella sia univoca.</span><span class="sxs-lookup"><span data-stu-id="98b69-104">A unique index guarantees that the index key contains no duplicate values and therefore every row in the table is in some way unique.</span></span> <span data-ttu-id="98b69-105">Non vi sono differenze significative tra la creazione di un vincolo UNIQUE e la creazione di un indice univoco indipendente da un vincolo.</span><span class="sxs-lookup"><span data-stu-id="98b69-105">There are no significant differences between creating a UNIQUE constraint and creating a unique index that is independent of a constraint.</span></span> <span data-ttu-id="98b69-106">La convalida dei dati viene eseguita nello stesso modo e da Query Optimizer non viene applicata alcuna distinzione tra un indice univoco creato tramite un vincolo o manualmente.</span><span class="sxs-lookup"><span data-stu-id="98b69-106">Data validation occurs in the same manner, and the query optimizer does not differentiate between a unique index created by a constraint or manually created.</span></span> <span data-ttu-id="98b69-107">Tuttavia, se si crea un vincolo UNIQUE nella colonna, l'obiettivo dell'indice è chiaro.</span><span class="sxs-lookup"><span data-stu-id="98b69-107">However, creating a UNIQUE constraint on the column makes the objective of the index clear.</span></span> <span data-ttu-id="98b69-108">Per ulteriori informazioni sui vincoli UNIQUE, vedere [Unique Constraints and Check Constraints](../tables/unique-constraints-and-check-constraints.md).</span><span class="sxs-lookup"><span data-stu-id="98b69-108">For more information on UNIQUE constraints, see [Unique Constraints and Check Constraints](../tables/unique-constraints-and-check-constraints.md).</span></span>  
  
 <span data-ttu-id="98b69-109">Quando si crea un indice univoco, è possibile impostare un'opzione che consente di ignorare le chiavi duplicate.</span><span class="sxs-lookup"><span data-stu-id="98b69-109">When you create a unique index, you can set an option to ignore duplicate keys.</span></span> <span data-ttu-id="98b69-110">Se questa opzione è impostata su **Sì** e si cerca di creare chiavi duplicate aggiungendo dati che coinvolgono più righe (tramite l'istruzione INSERT), la riga che contiene la chiave duplicata non verrà aggiunta.</span><span class="sxs-lookup"><span data-stu-id="98b69-110">If this option is set to **Yes** and you attempt to create duplicate keys by adding data that affects multiple rows (with the INSERT statement), the row containing a duplicate is not added.</span></span> <span data-ttu-id="98b69-111">Se invece l'opzione è impostata su **No**, l'intera operazione non verrà completata e verrà eseguito il rollback di tutti i dati.</span><span class="sxs-lookup"><span data-stu-id="98b69-111">If it is set to **No**, the entire insert operation fails and all the data is rolled back.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="98b69-112">Non è possibile creare un indice univoco in un'unica colonna se in essa è contenuto il valore NULL in più righe.</span><span class="sxs-lookup"><span data-stu-id="98b69-112">You cannot create a unique index on a single column if that column contains NULL in more than one row.</span></span> <span data-ttu-id="98b69-113">Analogamente, non è possibile creare un indice univoco su più colonne se la combinazione di colonne contiene il valore NULL in più righe.</span><span class="sxs-lookup"><span data-stu-id="98b69-113">Similarly, you cannot create a unique index on multiple columns if the combination of columns contains NULL in more than one row.</span></span> <span data-ttu-id="98b69-114">Ai fini dell'indicizzazione, questi valori sono considerati duplicati.</span><span class="sxs-lookup"><span data-stu-id="98b69-114">These are treated as duplicate values for indexing purposes.</span></span>  
  
 <span data-ttu-id="98b69-115">**Contenuto dell'articolo**</span><span class="sxs-lookup"><span data-stu-id="98b69-115">**In This Topic**</span></span>  
  
-   <span data-ttu-id="98b69-116">**Prima di iniziare:**</span><span class="sxs-lookup"><span data-stu-id="98b69-116">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="98b69-117">Vantaggi di un indice univoco</span><span class="sxs-lookup"><span data-stu-id="98b69-117">Benefits of a Unique Index</span></span>](#Benefits)  
  
     [<span data-ttu-id="98b69-118">Modalità di implementazione tipiche</span><span class="sxs-lookup"><span data-stu-id="98b69-118">Typical Implementations</span></span>](#Implementations)  
  
     [<span data-ttu-id="98b69-119">Limitazioni e restrizioni</span><span class="sxs-lookup"><span data-stu-id="98b69-119">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="98b69-120">Sicurezza</span><span class="sxs-lookup"><span data-stu-id="98b69-120">Security</span></span>](#Security)  
  
-   <span data-ttu-id="98b69-121">**Per creare un indice univoco per una tabella utilizzando:**</span><span class="sxs-lookup"><span data-stu-id="98b69-121">**To create a unique index on a table, using:**</span></span>  
  
     [<span data-ttu-id="98b69-122">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="98b69-122">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="98b69-123">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="98b69-123">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="98b69-124">Prima di iniziare</span><span class="sxs-lookup"><span data-stu-id="98b69-124">Before You Begin</span></span>  
  
###  <a name="benefits-of-a-unique-index"></a><a name="Benefits"></a> <span data-ttu-id="98b69-125">Vantaggi di un indice univoco</span><span class="sxs-lookup"><span data-stu-id="98b69-125">Benefits of a Unique Index</span></span>  
  
-   <span data-ttu-id="98b69-126">Gli indici univoci a più colonne consentono di garantire che ogni combinazione di valori nella chiave dell'indice sia univoca.</span><span class="sxs-lookup"><span data-stu-id="98b69-126">Multicolumn unique indexes guarantee that each combination of values in the index key is unique.</span></span> <span data-ttu-id="98b69-127">Ad esempio, se si crea un indice univoco basato su una combinazione delle colonne **LastName**, **FirstName**e **MiddleName** , non è possibile che nella tabella siano incluse due righe in cui è presente la stessa combinazione di valori per queste colonne.</span><span class="sxs-lookup"><span data-stu-id="98b69-127">For example, if a unique index is created on a combination of **LastName**, **FirstName**, and **MiddleName** columns, no two rows in the table could have the same combination of values for these columns.</span></span>  
  
-   <span data-ttu-id="98b69-128">Se i dati in ogni colonna sono univoci, nella stessa tabella è possibile creare sia un indice cluster univoco sia più indici non cluster univoci.</span><span class="sxs-lookup"><span data-stu-id="98b69-128">Provided that the data in each column is unique, you can create both a unique clustered index and multiple unique nonclustered indexes on the same table.</span></span>  
  
-   <span data-ttu-id="98b69-129">Gli indici univoci consentono di garantire l'integrità dei dati delle colonne definite.</span><span class="sxs-lookup"><span data-stu-id="98b69-129">Unique indexes ensure the data integrity of the defined columns.</span></span>  
  
-   <span data-ttu-id="98b69-130">Gli indici univoci forniscono informazioni aggiuntive utili a Query Optimizer tramite cui è possibile produrre piani di esecuzione più efficienti.</span><span class="sxs-lookup"><span data-stu-id="98b69-130">Unique indexes provide additional information helpful to the query optimizer that can produce more efficient execution plans.</span></span>  
  
###  <a name="typical-implementations"></a><a name="Implementations"></a> <span data-ttu-id="98b69-131">Modalità di implementazione tipiche</span><span class="sxs-lookup"><span data-stu-id="98b69-131">Typical Implementations</span></span>  
 <span data-ttu-id="98b69-132">Gli indici univoci vengono implementati nei modi seguenti:</span><span class="sxs-lookup"><span data-stu-id="98b69-132">Unique indexes are implemented in the following ways:</span></span>  
  
-   <span data-ttu-id="98b69-133">**Vincolo PRIMARY KEY o UNIQUE**</span><span class="sxs-lookup"><span data-stu-id="98b69-133">**PRIMARY KEY or UNIQUE constraint**</span></span>  
  
     <span data-ttu-id="98b69-134">Quando si crea un vincolo PRIMARY KEY, viene automaticamente creato un indice cluster univoco nella colonna o nelle colonne se nella tabella non esiste già un indice cluster e non si specifica un indice non cluster univoco.</span><span class="sxs-lookup"><span data-stu-id="98b69-134">When you create a PRIMARY KEY constraint, a unique clustered index on the column or columns is automatically created if a clustered index on the table does not already exist and you do not specify a unique nonclustered index.</span></span> <span data-ttu-id="98b69-135">La colonna chiave primaria non può supportare i valori NULL.</span><span class="sxs-lookup"><span data-stu-id="98b69-135">The primary key column cannot allow NULL values.</span></span>  
  
     <span data-ttu-id="98b69-136">Quando si crea un vincolo UNIQUE, viene creato un indice non cluster univoco per applicare un vincolo UNIQUE per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="98b69-136">When you create a UNIQUE constraint, a unique nonclustered index is created to enforce a UNIQUE constraint by default.</span></span> <span data-ttu-id="98b69-137">È possibile specificare un indice cluster univoco se nella tabella non ne esiste già uno.</span><span class="sxs-lookup"><span data-stu-id="98b69-137">You can specify a unique clustered index if a clustered index on the table does not already exist.</span></span>  
  
     <span data-ttu-id="98b69-138">Per ulteriori informazioni, vedere [Unique Constraints and Check Constraints](../tables/unique-constraints-and-check-constraints.md) e [Primary and Foreign Key Constraints](../tables/primary-and-foreign-key-constraints.md).</span><span class="sxs-lookup"><span data-stu-id="98b69-138">For more information, see [Unique Constraints and Check Constraints](../tables/unique-constraints-and-check-constraints.md) and [Primary and Foreign Key Constraints](../tables/primary-and-foreign-key-constraints.md).</span></span>  
  
-   <span data-ttu-id="98b69-139">**Indice indipendente da un vincolo**</span><span class="sxs-lookup"><span data-stu-id="98b69-139">**Index independent of a constraint**</span></span>  
  
     <span data-ttu-id="98b69-140">In una tabella è possibile definire più indici non cluster.</span><span class="sxs-lookup"><span data-stu-id="98b69-140">Multiple unique nonclustered indexes can be defined on a table.</span></span>  
  
     <span data-ttu-id="98b69-141">Per altre informazioni, vedere [CREATE INDEX &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-index-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="98b69-141">For more information, see [CREATE INDEX &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-index-transact-sql).</span></span>  
  
-   <span data-ttu-id="98b69-142">**Vista indicizzata**</span><span class="sxs-lookup"><span data-stu-id="98b69-142">**Indexed view**</span></span>  
  
     <span data-ttu-id="98b69-143">Per creare una vista indicizzata, viene definito un indice cluster univoco in una o più colonne della vista.</span><span class="sxs-lookup"><span data-stu-id="98b69-143">To create an indexed view, a unique clustered index is defined on one or more view columns.</span></span> <span data-ttu-id="98b69-144">La vista viene eseguita e il set di risultati viene archiviato nel livello foglia allo stesso modo in cui vengono archiviati i dati della tabella in un indice cluster.</span><span class="sxs-lookup"><span data-stu-id="98b69-144">The view is executed and the result set is stored in the leaf level of the index in the same way table data is stored in a clustered index.</span></span> <span data-ttu-id="98b69-145">Per altre informazioni, vedere [Creare viste indicizzate](../views/views.md).</span><span class="sxs-lookup"><span data-stu-id="98b69-145">For more information, see [Create Indexed Views](../views/views.md).</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="98b69-146">Limitazioni e restrizioni</span><span class="sxs-lookup"><span data-stu-id="98b69-146">Limitations and Restrictions</span></span>  
  
-   <span data-ttu-id="98b69-147">Se nei dati sono presenti valori di chiave duplicati, non è possibile creare un indice univoco, un vincolo UNIQUE o un vincolo PRIMARY KEY.</span><span class="sxs-lookup"><span data-stu-id="98b69-147">A unique index, UNIQUE constraint, or PRIMARY KEY constraint cannot be created if duplicate key values exist in the data.</span></span>  
  
-   <span data-ttu-id="98b69-148">In un indice non cluster univoco possono essere contenute colonne non chiave.</span><span class="sxs-lookup"><span data-stu-id="98b69-148">A unique nonclustered index can contain included nonkey columns.</span></span> <span data-ttu-id="98b69-149">Per altre informazioni, vedere [Creare indici con colonne incluse](create-indexes-with-included-columns.md).</span><span class="sxs-lookup"><span data-stu-id="98b69-149">For more information, see [Create Indexes with Included Columns](create-indexes-with-included-columns.md).</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="98b69-150">Sicurezza</span><span class="sxs-lookup"><span data-stu-id="98b69-150">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="98b69-151">Autorizzazioni</span><span class="sxs-lookup"><span data-stu-id="98b69-151">Permissions</span></span>  
 <span data-ttu-id="98b69-152">È richiesta l'autorizzazione ALTER per la tabella o la vista.</span><span class="sxs-lookup"><span data-stu-id="98b69-152">Requires ALTER permission on the table or view.</span></span> <span data-ttu-id="98b69-153">L'utente deve essere un membro del ruolo predefinito del server **sysadmin** o dei ruoli predefiniti del database **db_ddladmin** e **db_owner** .</span><span class="sxs-lookup"><span data-stu-id="98b69-153">User must be a member of the **sysadmin** fixed server role or the **db_ddladmin** and **db_owner** fixed database roles.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="98b69-154">Con SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="98b69-154">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-create-a-unique-index-by-using-the-table-designer"></a><span data-ttu-id="98b69-155">Per creare un indice univoco tramite Progettazione tabelle</span><span class="sxs-lookup"><span data-stu-id="98b69-155">To create a unique index by using the Table Designer</span></span>  
  
1.  <span data-ttu-id="98b69-156">In Esplora oggetti espandere il database contenente la tabella in cui si desidera creare un indice univoco.</span><span class="sxs-lookup"><span data-stu-id="98b69-156">In Object Explorer, expand the database that contains the table on which you want to create a unique index.</span></span>  
  
2.  <span data-ttu-id="98b69-157">Espandere la cartella **Tabelle** .</span><span class="sxs-lookup"><span data-stu-id="98b69-157">Expand the **Tables** folder.</span></span>  
  
3.  <span data-ttu-id="98b69-158">Fare clic con il pulsante destro del mouse sulla tabella nella quale creare un indice univoco e selezionare **Progetta**.</span><span class="sxs-lookup"><span data-stu-id="98b69-158">Right-click the table on which you want to create a unique index and select **Design**.</span></span>  
  
4.  <span data-ttu-id="98b69-159">Selezionare **Indici/chiavi** nel menu **Progettazione tabelle**.</span><span class="sxs-lookup"><span data-stu-id="98b69-159">On the **Table Designer** menu, select **Indexes/Keys**.</span></span>  
  
5.  <span data-ttu-id="98b69-160">Nella finestra di dialogo **Indici/chiavi** fare clic su **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="98b69-160">In the **Indexes/Keys** dialog box, click **Add**.</span></span>  
  
6.  <span data-ttu-id="98b69-161">Selezionare il nuovo indice dalla casella di testo **Chiave o indice primario/univoco selezionato** .</span><span class="sxs-lookup"><span data-stu-id="98b69-161">Select the new index in the **Selected Primary/Unique Key or Index** text box.</span></span>  
  
7.  <span data-ttu-id="98b69-162">In **(Generale)** nella griglia principale selezionare **Tipo** , quindi scegliere **Indice** dall'elenco.</span><span class="sxs-lookup"><span data-stu-id="98b69-162">In the main grid, under **(General)**, select **Type** and then choose **Index** from the list.</span></span>  
  
8.  <span data-ttu-id="98b69-163">Selezionare **Colonne** e quindi fare clic sul pulsante con i puntini di sospensione **(...)** .</span><span class="sxs-lookup"><span data-stu-id="98b69-163">Select **Columns**, and then click the ellipsis **(...)**.</span></span>  
  
9. <span data-ttu-id="98b69-164">In **Nome colonna** della finestra di dialogo **Colonne indice**selezionare le colonne da indicizzare.</span><span class="sxs-lookup"><span data-stu-id="98b69-164">In the **Index Columns** dialog box, under **Column Name**, select the columns you want to index.</span></span> <span data-ttu-id="98b69-165">È possibile selezionare fino a 16 colonne.</span><span class="sxs-lookup"><span data-stu-id="98b69-165">You can select up to 16 columns.</span></span> <span data-ttu-id="98b69-166">Per ottenere prestazioni ottimali, selezionare una o due colonne per indice.</span><span class="sxs-lookup"><span data-stu-id="98b69-166">For optimal performance, select only one or two columns per index.</span></span> <span data-ttu-id="98b69-167">Per ogni colonna selezionata, è possibile specificare se nell'indice i valori della colonna dovranno essere organizzati in ordine crescente o decrescente.</span><span class="sxs-lookup"><span data-stu-id="98b69-167">For each column you select, indicate whether the index arranges values of this column in ascending or descending order.</span></span>  
  
10. <span data-ttu-id="98b69-168">Una volta selezionate tutte le colonne per l'indice, fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="98b69-168">When all columns for the index are selected, click **OK**.</span></span>  
  
11. <span data-ttu-id="98b69-169">In **(Generale)** nella griglia principale selezionare **Univoco** , quindi scegliere **Sì** dall'elenco.</span><span class="sxs-lookup"><span data-stu-id="98b69-169">In the grid, under **(General)**, select **Is Unique** and then choose **Yes** from the list.</span></span>  
  
12. <span data-ttu-id="98b69-170">Facoltativo: In **Progettazione tabelle**nella griglia principale selezionare **Ignora chiavi duplicate** , quindi scegliere **Sì** dall'elenco.</span><span class="sxs-lookup"><span data-stu-id="98b69-170">Optional: In the main grid, under **Table Designer**, select **Ignore Duplicate Keys** and then choose **Yes** from the list.</span></span> <span data-ttu-id="98b69-171">Eseguire questa operazione se si desidera ignorare i tentativi per aggiungere dati che comporterebbero la creazione di una chiave duplicata nell'indice univoco.</span><span class="sxs-lookup"><span data-stu-id="98b69-171">Do this if you want to ignore attempts to add data that would create a duplicate key in the unique index.</span></span>  
  
13. <span data-ttu-id="98b69-172">Fare clic su **Close**.</span><span class="sxs-lookup"><span data-stu-id="98b69-172">Click **Close**.</span></span>  
  
14. <span data-ttu-id="98b69-173">Nel menu **File** scegliere **Salva**_table_name_.</span><span class="sxs-lookup"><span data-stu-id="98b69-173">On the **File** menu, click **Save**_table_name_.</span></span>  
  
#### <a name="create-a-unique-index-by-using-object-explorer"></a><span data-ttu-id="98b69-174">Creare un indice univoco tramite Esplora oggetti</span><span class="sxs-lookup"><span data-stu-id="98b69-174">Create a unique index by using Object Explorer</span></span>  
  
1.  <span data-ttu-id="98b69-175">In Esplora oggetti espandere il database contenente la tabella in cui si desidera creare un indice univoco.</span><span class="sxs-lookup"><span data-stu-id="98b69-175">In Object Explorer, expand the database that contains the table on which you want to create a unique index.</span></span>  
  
2.  <span data-ttu-id="98b69-176">Espandere la cartella **Tabelle** .</span><span class="sxs-lookup"><span data-stu-id="98b69-176">Expand the **Tables** folder.</span></span>  
  
3.  <span data-ttu-id="98b69-177">Espandere la tabella in cui si desidera creare un indice univoco.</span><span class="sxs-lookup"><span data-stu-id="98b69-177">Expand the table on which you want to create a unique index.</span></span>  
  
4.  <span data-ttu-id="98b69-178">Fare clic con il pulsante destro del mouse sulla cartella **Indici**, scegliere **Nuovo indice**e selezionare **Indice non cluster**.</span><span class="sxs-lookup"><span data-stu-id="98b69-178">Right-click the **Indexes** folder, point to **New Index**, and select **Non-Clustered Index...**.</span></span>  
  
5.  <span data-ttu-id="98b69-179">Nella pagina **Generale** della finestra di dialogo **Nuovo indice** immettere il nome del nuovo indice nella casella **Nome indice** .</span><span class="sxs-lookup"><span data-stu-id="98b69-179">In the **New Index** dialog box, on the **General** page, enter the name of the new index in the **Index name** box.</span></span>  
  
6.  <span data-ttu-id="98b69-180">Selezionare la casella di controllo **Univoco** .</span><span class="sxs-lookup"><span data-stu-id="98b69-180">Select the **Unique** check box.</span></span>  
  
7.  <span data-ttu-id="98b69-181">In **Colonne chiave indice**fare clic su **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="98b69-181">Under **Index key columns**, click **Add...**.</span></span>  
  
8.  <span data-ttu-id="98b69-182">Nella finestra di dialogo **Seleziona colonne da**_table_name_ Selezionare le caselle di controllo delle colonne della tabella da aggiungere all'indice univoco.</span><span class="sxs-lookup"><span data-stu-id="98b69-182">In the **Select Columns from**_table_name_ dialog box, select the check box or check boxes of the table column or columns to be added to the unique index.</span></span>  
  
9. <span data-ttu-id="98b69-183">Fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="98b69-183">Click **OK**.</span></span>  
  
10. <span data-ttu-id="98b69-184">Nella finestra di dialogo **Nuovo indice** fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="98b69-184">In the **New Index** dialog box, click **OK**.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="98b69-185">Con Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="98b69-185">Using Transact-SQL</span></span>  
  
#### <a name="to-create-a-unique-index-on-a-table"></a><span data-ttu-id="98b69-186">Per creare un indice univoco per una tabella</span><span class="sxs-lookup"><span data-stu-id="98b69-186">To create a unique index on a table</span></span>  
  
1.  <span data-ttu-id="98b69-187">In **Esplora oggetti**connettersi a un'istanza del [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="98b69-187">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="98b69-188">Sulla barra Standard fare clic su **Nuova query**.</span><span class="sxs-lookup"><span data-stu-id="98b69-188">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="98b69-189">Copiare e incollare l'esempio seguente nella finestra Query, quindi fare clic su **Esegui**.</span><span class="sxs-lookup"><span data-stu-id="98b69-189">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```  
    USE AdventureWorks2012;  
    GO  
    -- Find an existing index named AK_UnitMeasure_Name and delete it if found  
    IF EXISTS (SELECT name from sys.indexes  
               WHERE name = N'AK_UnitMeasure_Name')   
       DROP INDEX AK_UnitMeasure_Name ON Production.UnitMeasure;   
    GO  
    -- Create a unique index called AK_UnitMeasure_Name  
    -- on the Production.UnitMeasure table using the Name column.  
    CREATE UNIQUE INDEX AK_UnitMeasure_Name   
       ON Production.UnitMeasure (Name);   
    GO  
    ```  
  
 <span data-ttu-id="98b69-190">Per altre informazioni, vedere [CREATE INDEX &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-index-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="98b69-190">For more information, see [CREATE INDEX &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-index-transact-sql).</span></span>  
  
  
