---
title: Definire e modificare un filtro di riga con parametri per un articolo di merge | Microsoft Docs
ms.custom: ''
ms.date: 06/02/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
helpviewer_keywords:
- parameterized filters [SQL Server replication], defining
- parameterized filters [SQL Server replication], modifying
- merge replication [SQL Server replication], dynamic filters
- merge replication parameterized filters [SQL Server replication]
- filters [SQL Server replication], parameterized
- modifying filters, parameterized row
- dynamic filters [SQL Server replication]
ms.assetid: de0482a2-3cc8-4030-8a4a-14364549ac9f
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: d80ad53661aced22795220507398e2fcc510edd3
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87721287"
---
# <a name="define-and-modify-a-parameterized-row-filter-for-a-merge-article"></a><span data-ttu-id="03b89-102">Definizione e modifica di un filtro di riga con parametri per un articolo di merge</span><span class="sxs-lookup"><span data-stu-id="03b89-102">Define and Modify a Parameterized Row Filter for a Merge Article</span></span>
  <span data-ttu-id="03b89-103">In questo argomento viene descritto come definire e modificare un filtro di riga con parametri in [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)] tramite [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)] o [!INCLUDE[tsql](../../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="03b89-103">This topic describes how to define and modify a parameterized row filter in [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../../includes/tsql-md.md)].</span></span>  
  
 <span data-ttu-id="03b89-104">Quando si creano articoli di tabella, è possibile usare filtri di riga con parametri.</span><span class="sxs-lookup"><span data-stu-id="03b89-104">When creating table articles, you can use parameterized row filters.</span></span> <span data-ttu-id="03b89-105">Questi filtri usano una clausola [WHERE](/sql/t-sql/queries/where-transact-sql) per selezionare i dati adatti da pubblicare.</span><span class="sxs-lookup"><span data-stu-id="03b89-105">These filters use a [WHERE](/sql/t-sql/queries/where-transact-sql) clause to select the appropriate data to be published.</span></span> <span data-ttu-id="03b89-106">Anziché specificare un valore letterale nella clausola, come avviene con il filtro di riga statico, specificare una o entrambe le funzioni di sistema seguenti: [SUSER_SNAME](/sql/t-sql/functions/suser-sname-transact-sql) e [HOST_NAME](/sql/t-sql/functions/host-name-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="03b89-106">Rather than specifying a literal value in the clause (as you do with a static row filter), you specify one or both of the following system functions: [SUSER_SNAME](/sql/t-sql/functions/suser-sname-transact-sql) and [HOST_NAME](/sql/t-sql/functions/host-name-transact-sql).</span></span> <span data-ttu-id="03b89-107">Per altre informazioni sui filtri di riga con parametri, vedere [Filtri di riga con parametri](../merge/parameterized-filters-parameterized-row-filters.md).</span><span class="sxs-lookup"><span data-stu-id="03b89-107">For more information, see [Parameterized Row Filters](../merge/parameterized-filters-parameterized-row-filters.md).</span></span>  
  
 
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="03b89-108">Prima di iniziare</span><span class="sxs-lookup"><span data-stu-id="03b89-108">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="03b89-109">Limitazioni e restrizioni</span><span class="sxs-lookup"><span data-stu-id="03b89-109">Limitations and Restrictions</span></span>  
  
-   <span data-ttu-id="03b89-110">Se si aggiunge, modifica o elimina un filtro di riga con parametri dopo che sono state inizializzate sottoscrizioni per la pubblicazione, è necessario generare un nuovo snapshot e reinizializzare tutte le sottoscrizioni in seguito alla modifica.</span><span class="sxs-lookup"><span data-stu-id="03b89-110">If you add, modify, or delete a parameterized row filter after subscriptions to the publication have been initialized, you must generate a new snapshot and reinitialize all subscriptions after making the change.</span></span> <span data-ttu-id="03b89-111">Per altre informazioni sui requisiti per la modifica delle proprietà, vedere [Modificare le proprietà di pubblicazioni e articoli](change-publication-and-article-properties.md).</span><span class="sxs-lookup"><span data-stu-id="03b89-111">For more information about requirements for property changes, see [Change Publication and Article Properties](change-publication-and-article-properties.md).</span></span>  
  
###  <a name="recommendations"></a><a name="Recommendations"></a> <span data-ttu-id="03b89-112">Indicazioni</span><span class="sxs-lookup"><span data-stu-id="03b89-112">Recommendations</span></span>  
  
-   <span data-ttu-id="03b89-113">Per motivi relativi alle prestazioni è consigliabile evitare di applicare funzioni ai nomi di colonna nelle clausole per filtri di riga con parametri, come `LEFT([MyColumn]) = SUSER_SNAME()`.</span><span class="sxs-lookup"><span data-stu-id="03b89-113">For performance reasons, we recommend that you not apply functions to column names in parameterized row filter clauses, such as `LEFT([MyColumn]) = SUSER_SNAME()`.</span></span> <span data-ttu-id="03b89-114">Se si usano HOST_NAME in una clausola di filtro e si sostituisce il valore HOST_NAME, può essere necessario convertire i tipi di dati tramite l'istruzione CONVERT.</span><span class="sxs-lookup"><span data-stu-id="03b89-114">If you use HOST_NAME in a filter clause and override the HOST_NAME value, it might be necessary to convert data types using CONVERT.</span></span> <span data-ttu-id="03b89-115">Per altre informazioni sulle procedure consigliate in questo caso, vedere la sezione relativa alla sostituzione del valore HOST_NAME() nell'argomento [Parameterized Row Filters](../merge/parameterized-filters-parameterized-row-filters.md).</span><span class="sxs-lookup"><span data-stu-id="03b89-115">For more information about best practices for this case, see the section "Overriding the HOST_NAME() Value" in the topic [Parameterized Row Filters](../merge/parameterized-filters-parameterized-row-filters.md).</span></span>  
  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="03b89-116">Utilizzo di SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="03b89-116">Using SQL Server Management Studio</span></span>  
 <span data-ttu-id="03b89-117">Definire, modificare ed eliminare filtri di riga con parametri nella pagina **Filtro righe tabella** della Creazione guidata nuova pubblicazione oppure nella pagina **Filtra righe** della finestra di dialogo **Proprietà pubblicazione - \<Publication>** .</span><span class="sxs-lookup"><span data-stu-id="03b89-117">Define, modify, and delete parameterized row filters on the **Filter Table Rows** page of the New Publication Wizard or the **Filter Rows** page of the **Publication Properties - \<Publication>** dialog box.</span></span> <span data-ttu-id="03b89-118">Per altre informazioni sull'uso della creazione guidata e l'accesso alla finestra di dialogo, vedere [Creare una pubblicazione](create-a-publication.md) e [Visualizzare e modificare le proprietà della pubblicazione](view-and-modify-publication-properties.md).</span><span class="sxs-lookup"><span data-stu-id="03b89-118">For more information about using the wizard and accessing the dialog box, see [Create a Publication](create-a-publication.md) and [View and Modify Publication Properties](view-and-modify-publication-properties.md).</span></span>  
  
#### <a name="to-define-a-parameterized-row-filter"></a><span data-ttu-id="03b89-119">Per definire un filtro di riga con parametri</span><span class="sxs-lookup"><span data-stu-id="03b89-119">To define a parameterized row filter</span></span>  
  
1.  <span data-ttu-id="03b89-120">Nella pagina **Filtro righe tabella** della Creazione guidata nuova pubblicazione oppure nella pagina **Filtra righe** della finestra di dialogo **Proprietà pubblicazione - \<Publication>** fare clic su **Aggiungi** e quindi su **Aggiungi filtro**.</span><span class="sxs-lookup"><span data-stu-id="03b89-120">On the **Filter Table Rows** page of the New Publication Wizard or the **Filter Rows** page of the **Publication Properties - \<Publication>**, click **Add**, and then click **Add Filter**.</span></span>  
  
2.  <span data-ttu-id="03b89-121">Nella finestra di dialogo **Aggiungi filtro** selezionare una tabella da filtrare nell'elenco a discesa.</span><span class="sxs-lookup"><span data-stu-id="03b89-121">In the **Add Filter** dialog box, select a table to filter from the drop-down list box.</span></span>  
  
3.  <span data-ttu-id="03b89-122">Creare un'istruzione di filtro nella casella di testo **Istruzione per il filtro** .</span><span class="sxs-lookup"><span data-stu-id="03b89-122">Create a filter statement in the **Filter statement** text box.</span></span> <span data-ttu-id="03b89-123">È possibile digitare direttamente nell'area di testo nonché trascinare colonne dalla casella di riepilogo **Colonne** .</span><span class="sxs-lookup"><span data-stu-id="03b89-123">You can type directly in the text area, and you can also drag and drop columns from the **Columns** list box.</span></span>  
  
    -   <span data-ttu-id="03b89-124">L'area di testo **Istruzione per il filtro** contiene il testo predefinito, nel formato seguente:</span><span class="sxs-lookup"><span data-stu-id="03b89-124">The **Filter statement** text area includes the default text, which is in the form of:</span></span>  
  
        ```  
        SELECT <published_columns> FROM [tableowner].[tablename] WHERE  
        ```  
  
    -   <span data-ttu-id="03b89-125">Il testo predefinito non può essere modificato. Digitare la clausola di filtro dopo la parola chiave WHERE usando la sintassi SQL standard.</span><span class="sxs-lookup"><span data-stu-id="03b89-125">The default text cannot be changed; type the filter clause after the WHERE keyword using standard SQL syntax.</span></span> <span data-ttu-id="03b89-126">Un filtro con parametri include una chiamata alla funzione di sistema `HOST_NAME()` e/o `SUSER_SNAME()` oppure a una funzione definita dall'utente che fa riferimento a una di queste funzioni o a entrambe.</span><span class="sxs-lookup"><span data-stu-id="03b89-126">A parameterized filter includes a call to the system function `HOST_NAME()` and/or `SUSER_SNAME()`, or a user-defined function that references one or both of these functions.</span></span> <span data-ttu-id="03b89-127">Di seguito è riportato un esempio di una clausola di filtro completa per un filtro di riga con parametri:</span><span class="sxs-lookup"><span data-stu-id="03b89-127">The following is an example of a complete filter clause for a parameterized row filter:</span></span>  
  
        ```  
        SELECT <published_columns> FROM [HumanResources].[Employee] WHERE LoginID = SUSER_SNAME()  
        ```  
  
         <span data-ttu-id="03b89-128">Per la clausola WHERE è consigliabile usare nomi in due parti. I nomi in tre e quattro parti non sono supportati.</span><span class="sxs-lookup"><span data-stu-id="03b89-128">The WHERE clause should use two-part naming; three-part naming and four-part naming are not supported.</span></span>  
  
4.  <span data-ttu-id="03b89-129">Selezionare l'opzione corrispondente alla modalità desiderata di condivisione dei dati tra i Sottoscrittori:</span><span class="sxs-lookup"><span data-stu-id="03b89-129">Select the option that matches how data will be shared among Subscribers:</span></span>  
  
    -   <span data-ttu-id="03b89-130">**Una riga di questa tabella verrà inviata a più sottoscrizioni**</span><span class="sxs-lookup"><span data-stu-id="03b89-130">**A row from this table will go to multiple subscriptions**</span></span>  
  
    -   <span data-ttu-id="03b89-131">**Una riga di questa tabella verrà inviata a una sola sottoscrizione**</span><span class="sxs-lookup"><span data-stu-id="03b89-131">**A row from this table will go to only one subscription**</span></span>  
  
     <span data-ttu-id="03b89-132">Selezionando **Una riga di questa tabella verrà inviata a una sola sottoscrizione**è possibile ottimizzare le prestazioni della replica di tipo merge archiviando ed elaborando una minore quantità di metadati.</span><span class="sxs-lookup"><span data-stu-id="03b89-132">If you select **A row from this table will go to only one subscription**, merge replication can optimize performance by storing and processing less metadata.</span></span> <span data-ttu-id="03b89-133">È tuttavia necessario garantire che i dati vengano partizionati in modo da non consentire la replica di una riga in più Sottoscrittori.</span><span class="sxs-lookup"><span data-stu-id="03b89-133">However, you must ensure that the data is partitioned in such a way that a row cannot be replicated to more than one Subscriber.</span></span> <span data-ttu-id="03b89-134">Per altre informazioni, vedere la sezione relativa all'impostazione delle opzioni delle partizioni nell'argomento [Filtri di riga con parametri](../merge/parameterized-filters-parameterized-row-filters.md).</span><span class="sxs-lookup"><span data-stu-id="03b89-134">For more information, see the section "Setting 'partition options'" in the topic [Parameterized Row Filters](../merge/parameterized-filters-parameterized-row-filters.md).</span></span>  
  
5.  [!INCLUDE[clickOK](../../../includes/clickok-md.md)]  
  
6.  <span data-ttu-id="03b89-135">Se è visualizzata la finestra di dialogo **Proprietà pubblicazione - \<Publication>** fare clic su **OK** per salvare e chiudere la finestra di dialogo.</span><span class="sxs-lookup"><span data-stu-id="03b89-135">If you are in the **Publication Properties - \<Publication>** dialog box, click **OK** to save and close the dialog box.</span></span>  
  
#### <a name="to-modify-a-parameterized-row-filter"></a><span data-ttu-id="03b89-136">Per modificare un filtro di riga con parametri</span><span class="sxs-lookup"><span data-stu-id="03b89-136">To modify a parameterized row filter</span></span>  
  
1.  <span data-ttu-id="03b89-137">Nella pagina **Filtro righe tabella** della Creazione guidata nuova pubblicazione o nella pagina **Filtro righe** di **Proprietà pubblicazione - \<Publication>** selezionare un filtro nel riquadro **Tabelle filtrate** e quindi fare clic su **Modifica**.</span><span class="sxs-lookup"><span data-stu-id="03b89-137">On the **Filter Table Rows** page of the New Publication Wizard or the **Filter Rows** page of the **Publication Properties - \<Publication>**, select a filter in the **Filtered Tables** pane, and then click **Edit**.</span></span>  
  
2.  <span data-ttu-id="03b89-138">Nella finestra di dialogo **Modifica filtro** modificare il filtro.</span><span class="sxs-lookup"><span data-stu-id="03b89-138">In the **Edit Filter** dialog box, modify the filter.</span></span>  
  
3.  [!INCLUDE[clickOK](../../../includes/clickok-md.md)]  
  
#### <a name="to-delete-a-parameterized-row-filter"></a><span data-ttu-id="03b89-139">Per eliminare un filtro di riga con parametri</span><span class="sxs-lookup"><span data-stu-id="03b89-139">To delete a parameterized row filter</span></span>  
  
1.  <span data-ttu-id="03b89-140">Nella pagina **Filtro righe tabella** della Creazione guidata nuova pubblicazione o nella pagina **Filtro righe** di **Proprietà pubblicazione - \<Publication>** selezionare un filtro nel riquadro **Tabelle filtrate** e quindi fare clic su **Elimina**.</span><span class="sxs-lookup"><span data-stu-id="03b89-140">On the **Filter Table Rows** page of the New Publication Wizard or the **Filter Rows** page of the **Publication Properties - \<Publication>**, select a filter in the **Filtered Tables** pane, and then click **Delete**.</span></span>  
  

  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="03b89-141">Uso di Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="03b89-141">Using Transact-SQL</span></span>  
 <span data-ttu-id="03b89-142">È possibile creare e modificare a livello di programmazione i filtri di riga con parametri tramite le stored procedure di replica.</span><span class="sxs-lookup"><span data-stu-id="03b89-142">Parameterized row filters can be created and modified programmatically using replication stored procedures.</span></span>  
  
#### <a name="to-define-a-parameterized-row-filter-for-an-article-in-a-merge-publication"></a><span data-ttu-id="03b89-143">Per definire un filtro di riga con parametri per un articolo in una pubblicazione di tipo merge</span><span class="sxs-lookup"><span data-stu-id="03b89-143">To define a parameterized row filter for an article in a merge publication</span></span>  
  
1.  <span data-ttu-id="03b89-144">Nel database di pubblicazione del server di pubblicazione eseguire [sp_addmergearticle &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-addmergearticle-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="03b89-144">At the Publisher on the publication database, execute [sp_addmergearticle &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-addmergearticle-transact-sql).</span></span> <span data-ttu-id="03b89-145">Specificare **@publication** , un nome per l'articolo per **@article** , la tabella da pubblicare per **@source_object** , la clausola WHERE che definisce il filtro con parametri per **@subset_filterclause** (escluso `WHERE` ) e uno dei valori seguenti per **@partition_options** , che descrive il tipo di partizionamento risultante dal filtro di riga con parametri:</span><span class="sxs-lookup"><span data-stu-id="03b89-145">Specify **@publication**, a name for the article for **@article**, the table being published for **@source_object**, the WHERE clause that defines the parameterized filter for **@subset_filterclause** (not including `WHERE`), and one of the following values for **@partition_options**, which describes the type of partitioning that will result from the parameterized row filter:</span></span>  
  
    -   <span data-ttu-id="03b89-146">**0** : il filtro dell'articolo è statico oppure non restituisce un subset univoco di dati per ogni partizione, ovvero si tratta di una partizione "sovrapposta".</span><span class="sxs-lookup"><span data-stu-id="03b89-146">**0** - Filtering for the article either is static or does not yield a unique subset of data for each partition (an "overlapping" partition).</span></span>  
  
    -   <span data-ttu-id="03b89-147">**1** : le partizioni risultanti sono sovrapposte e gli aggiornamenti apportati nel Sottoscrittore non possono modificare la partizione a cui appartiene una riga.</span><span class="sxs-lookup"><span data-stu-id="03b89-147">**1** - Resulting partitions are overlapping, and updates made at the Subscriber cannot change the partition to which a row belongs.</span></span>  
  
    -   <span data-ttu-id="03b89-148">**2** : il filtro dell'articolo restituisce partizioni non sovrapposte, ma più Sottoscrittori ricevono la stessa partizione.</span><span class="sxs-lookup"><span data-stu-id="03b89-148">**2** - Filtering for the article yields nonoverlapping partitions, but multiple Subscribers can receive the same partition.</span></span>  
  
    -   <span data-ttu-id="03b89-149">**3** : il filtro dell'articolo restituisce partizioni non sovrapposte univoche per ogni sottoscrizione.</span><span class="sxs-lookup"><span data-stu-id="03b89-149">**3** - Filtering for the article yields nonoverlapping partitions that are unique for each subscription.</span></span>  
  
#### <a name="to-change-a-parameterized-row-filter-for-an-article-in-a-merge-publication"></a><span data-ttu-id="03b89-150">Per modificare un filtro di riga con parametri per un articolo in una pubblicazione di tipo merge</span><span class="sxs-lookup"><span data-stu-id="03b89-150">To change a parameterized row filter for an article in a merge publication</span></span>  
  
1.  <span data-ttu-id="03b89-151">Nel database di pubblicazione del server di pubblicazione eseguire [sp_changemergearticle](/sql/relational-databases/system-stored-procedures/sp-changemergearticle-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="03b89-151">At the Publisher on the publication database, execute [sp_changemergearticle](/sql/relational-databases/system-stored-procedures/sp-changemergearticle-transact-sql).</span></span> <span data-ttu-id="03b89-152">Specificare **@publication** , **@article** , `subset_filterclause` il valore per **@property** , l'espressione che definisce il filtro con parametri per **@value** (escluso `WHERE` ) e il valore **1** sia per che per **@force_invalidate_snapshot** **@force_reinit_subscription** .</span><span class="sxs-lookup"><span data-stu-id="03b89-152">Specify **@publication**, **@article**, a value of `subset_filterclause` for **@property**, the expression that defines the parameterized filter for **@value** (not including `WHERE`), and a value of **1** for both **@force_invalidate_snapshot** and **@force_reinit_subscription**.</span></span>  
  
2.  <span data-ttu-id="03b89-153">Se questa modifica implica un diverso comportamento del partizionamento, eseguire nuovamente [sp_changemergearticle](/sql/relational-databases/system-stored-procedures/sp-changemergearticle-transact-sql) .</span><span class="sxs-lookup"><span data-stu-id="03b89-153">If this change results in different partitioning behavior, then execute [sp_changemergearticle](/sql/relational-databases/system-stored-procedures/sp-changemergearticle-transact-sql) again.</span></span> <span data-ttu-id="03b89-154">Specificare **@publication** , **@article** , `partition_options` il valore per **@property** e l'opzione di partizionamento più appropriata per **@value** , che può essere uno dei seguenti:</span><span class="sxs-lookup"><span data-stu-id="03b89-154">Specify **@publication**, **@article**, a value of `partition_options` for **@property**, and the most appropriate partitioning option for **@value**, which can be one of the following:</span></span>  
  
    -   <span data-ttu-id="03b89-155">**0** : il filtro dell'articolo è statico oppure non restituisce un subset univoco di dati per ogni partizione, ovvero si tratta di una partizione "sovrapposta".</span><span class="sxs-lookup"><span data-stu-id="03b89-155">**0** - Filtering for the article either is static or does not yield a unique subset of data for each partition (an "overlapping" partition).</span></span>  
  
    -   <span data-ttu-id="03b89-156">**1** : le partizioni risultanti sono sovrapposte e gli aggiornamenti apportati nel Sottoscrittore non possono modificare la partizione a cui appartiene una riga.</span><span class="sxs-lookup"><span data-stu-id="03b89-156">**1** - Resulting partitions are overlapping, and updates made at the Subscriber cannot change the partition to which a row belongs.</span></span>  
  
    -   <span data-ttu-id="03b89-157">**2** : il filtro dell'articolo restituisce partizioni non sovrapposte, ma più Sottoscrittori ricevono la stessa partizione.</span><span class="sxs-lookup"><span data-stu-id="03b89-157">**2** - Filtering for the article yields nonoverlapping partitions, but multiple Subscribers can receive the same partition.</span></span>  
  
    -   <span data-ttu-id="03b89-158">**3** : il filtro dell'articolo restituisce partizioni non sovrapposte univoche per ogni sottoscrizione.</span><span class="sxs-lookup"><span data-stu-id="03b89-158">**3** - Filtering for the article yields nonoverlapping partitions that are unique for each subscription.</span></span>  
  
###  <a name="example-transact-sql"></a><a name="TsqlExample"></a> <span data-ttu-id="03b89-159">Esempio (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="03b89-159">Example (Transact-SQL)</span></span>  
 <span data-ttu-id="03b89-160">In questo esempio viene definito un gruppo di articoli di una pubblicazione di tipo merge in cui agli articoli è applicata una serie di filtri di join sulla tabella `Employee` che presenta essa stessa un filtro di riga con parametri sulla colonna **LoginID** .</span><span class="sxs-lookup"><span data-stu-id="03b89-160">This example defines a group of articles in a merge publication where the articles are filtered with a series of join filters against the `Employee` table that is itself filtered using a parameterized row filter on the **LoginID** column.</span></span> <span data-ttu-id="03b89-161">Durante la sincronizzazione viene sostituito il valore restituito dalla funzione [HOST_NAME](/sql/t-sql/functions/host-name-transact-sql) .</span><span class="sxs-lookup"><span data-stu-id="03b89-161">During synchronization, the value returned by the [HOST_NAME](/sql/t-sql/functions/host-name-transact-sql) function is overridden.</span></span> <span data-ttu-id="03b89-162">Per altre informazioni, vedere la sezione relativa alla sostituzione del valore HOST_NAME() nell'argomento [Parameterized Row Filters](../merge/parameterized-filters-parameterized-row-filters.md).</span><span class="sxs-lookup"><span data-stu-id="03b89-162">For more information, see Overriding the HOST_NAME() Value in the topic [Parameterized Row Filters](../merge/parameterized-filters-parameterized-row-filters.md).</span></span>  
  
 [!code-sql[HowTo#sp_MergeDynamicPub1](../../../snippets/tsql/SQL15/replication/howto/tsql/createmergepubdynamic1.sql#sp_mergedynamicpub1)]  
  
  
## <a name="see-also"></a><span data-ttu-id="03b89-163">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="03b89-163">See Also</span></span>  
 <span data-ttu-id="03b89-164">[Definizione e modifica di un filtro di join tra articoli di merge](define-and-modify-a-join-filter-between-merge-articles.md) </span><span class="sxs-lookup"><span data-stu-id="03b89-164">[Define and Modify a Join Filter Between Merge Articles](define-and-modify-a-join-filter-between-merge-articles.md) </span></span>  
 <span data-ttu-id="03b89-165">[Modificare le proprietà di pubblicazioni e articoli](change-publication-and-article-properties.md) </span><span class="sxs-lookup"><span data-stu-id="03b89-165">[Change Publication and Article Properties](change-publication-and-article-properties.md) </span></span>  
 <span data-ttu-id="03b89-166">[Join Filters](../merge/join-filters.md) </span><span class="sxs-lookup"><span data-stu-id="03b89-166">[Join Filters](../merge/join-filters.md) </span></span>  
 [<span data-ttu-id="03b89-167">Filtri di riga con parametri</span><span class="sxs-lookup"><span data-stu-id="03b89-167">Parameterized Row Filters</span></span>](../merge/parameterized-filters-parameterized-row-filters.md)  
  
  
