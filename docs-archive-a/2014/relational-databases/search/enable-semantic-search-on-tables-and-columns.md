---
title: Abilitare la ricerca semantica in tabelle e colonne | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: search
ms.topic: conceptual
helpviewer_keywords:
- semantic search [SQL Server], enabling
ms.assetid: 895d220c-6749-4954-9dd3-2ea4c6a321ff
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: f11ba654f7cc34f521990e8c420d41885d3c55b9
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87717754"
---
# <a name="enable-semantic-search-on-tables-and-columns"></a><span data-ttu-id="914c3-102">Abilitare la ricerca semantica in tabelle e colonne</span><span class="sxs-lookup"><span data-stu-id="914c3-102">Enable Semantic Search on Tables and Columns</span></span>
  <span data-ttu-id="914c3-103">Viene descritto come abilitare o disabilitare l'indicizzazione semantica statistica in colonne selezionate contenenti documenti o testo.</span><span class="sxs-lookup"><span data-stu-id="914c3-103">Describes how to enable or disable statistical semantic indexing on selected columns that contain documents or text.</span></span>  
  
 <span data-ttu-id="914c3-104">Nella ricerca semantica statistica vengono utilizzati gli indici creati dalla ricerca full-text e vengono creati indici aggiuntivi.</span><span class="sxs-lookup"><span data-stu-id="914c3-104">Statistical Semantic Search uses the indexes that are created by Full-Text Search, and creates additional indexes.</span></span> <span data-ttu-id="914c3-105">Come risultato di questa dipendenza dalla ricerca full-text, viene creato un nuovo indice semantico quando si definisce un nuovo indice full-text o si modifica un indice full-text esistente.</span><span class="sxs-lookup"><span data-stu-id="914c3-105">As a result of this dependency on full-text search, you create a new semantic index when you define a new full-text index, or when you alter an existing full-text index.</span></span> <span data-ttu-id="914c3-106">È possibile creare un nuovo indice semantico utilizzando le istruzioni [!INCLUDE[tsql](../../includes/tsql-md.md)] o l'Indicizzazione guidata full-text e le altre finestre di dialogo di [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], come descritto in questo argomento.</span><span class="sxs-lookup"><span data-stu-id="914c3-106">You can create a new semantic index by using [!INCLUDE[tsql](../../includes/tsql-md.md)] statements, or by using the Full-Text Indexing Wizard and other dialog boxes in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], as described in this topic.</span></span>  
  
##  <a name="creating-a-semantic-index"></a><a name="BasicEnabling"></a><span data-ttu-id="914c3-107">Creazione di un indice semantico</span><span class="sxs-lookup"><span data-stu-id="914c3-107">Creating a Semantic Index</span></span>  
  
###  <a name="requirements-and-restrictions-for-creating-a-semantic-index"></a><a name="reqenable"></a><span data-ttu-id="914c3-108">Requisiti e restrizioni per la creazione di un indice semantico</span><span class="sxs-lookup"><span data-stu-id="914c3-108">Requirements and Restrictions for Creating a Semantic Index</span></span>  
  
-   <span data-ttu-id="914c3-109">È possibile creare un indice in qualsiasi oggetto di database supportato per l'indicizzazione full-text, incluse tabelle e viste indicizzate.</span><span class="sxs-lookup"><span data-stu-id="914c3-109">You can create an index on any of the database objects that are supported for full-text indexing, including tables and indexed views.</span></span>  
  
-   <span data-ttu-id="914c3-110">Prima che sia possibile abilitare l'indicizzazione semantica per colonne specifiche, devono esistere i prerequisiti riportati di seguito.</span><span class="sxs-lookup"><span data-stu-id="914c3-110">Before you can enable semantic indexing for specific columns, the following prerequisites must exist:</span></span>  
  
    -   <span data-ttu-id="914c3-111">Deve esistere un catalogo full-text per il database.</span><span class="sxs-lookup"><span data-stu-id="914c3-111">A full-text catalog must exist for the database.</span></span>  
  
    -   <span data-ttu-id="914c3-112">La tabella deve disporre di un indice full-text.</span><span class="sxs-lookup"><span data-stu-id="914c3-112">The table must have a full-text index.</span></span>  
  
    -   <span data-ttu-id="914c3-113">Le colonne selezionate devono far parte dell'indice full-text.</span><span class="sxs-lookup"><span data-stu-id="914c3-113">The selected columns must participate in the full-text index.</span></span>  
  
     <span data-ttu-id="914c3-114">È possibile creare e abilitare contemporaneamente tutti questi prerequisiti.</span><span class="sxs-lookup"><span data-stu-id="914c3-114">You can create and enable all these requirements at the same time.</span></span>  
  
-   <span data-ttu-id="914c3-115">È possibile creare un indice semantico in colonne che includono qualsiasi tipo di dati supportato per l'indicizzazione full-text.</span><span class="sxs-lookup"><span data-stu-id="914c3-115">You can create a semantic index on columns that have any of the data types that are supported for full-text indexing.</span></span> <span data-ttu-id="914c3-116">Per altre informazioni, vedere [Creare e gestire indici full-text](create-and-manage-full-text-indexes.md).</span><span class="sxs-lookup"><span data-stu-id="914c3-116">For more information, see [Create and Manage Full-Text Indexes](create-and-manage-full-text-indexes.md).</span></span>  
  
-   <span data-ttu-id="914c3-117">È possibile specificare qualsiasi tipo di documento supportato per l'indicizzazione full-text per colonne `varbinary(max)`.</span><span class="sxs-lookup"><span data-stu-id="914c3-117">You can specify any document type that is supported for full-text indexing for `varbinary(max)` columns.</span></span> <span data-ttu-id="914c3-118">Per ulteriori informazioni, vedere [Procedura: determinare quali tipi di documenti è possibile indicizzare](#doctypes) in questo argomento.</span><span class="sxs-lookup"><span data-stu-id="914c3-118">For more information, see [How To: Determine Which Document Types Can Be Indexed](#doctypes) in this topic.</span></span>  
  
-   <span data-ttu-id="914c3-119">L'indicizzazione semantica consente di creare due tipi di indici per le colonne selezionate, ovvero un indice di frasi chiave e un indice di somiglianza del documento.</span><span class="sxs-lookup"><span data-stu-id="914c3-119">Semantic indexing creates two types of indexes for the columns that you select - an index of key phrases, and an index of document similarity.</span></span> <span data-ttu-id="914c3-120">Non è possibile selezionare solo uno dei due tipi di indice quando si abilita l'indicizzazione semantica.</span><span class="sxs-lookup"><span data-stu-id="914c3-120">You cannot select only one type of index or the other when you enable semantic indexing.</span></span> <span data-ttu-id="914c3-121">È tuttavia possibile eseguire query indipendenti su questi due indici.</span><span class="sxs-lookup"><span data-stu-id="914c3-121">However you can query these two indexes independently.</span></span> <span data-ttu-id="914c3-122">Per altre informazioni, vedere [Trovare frasi chiave nei documenti mediante ricerca semantica](find-key-phrases-in-documents-with-semantic-search.md) e [Trovare documenti simili e correlati tramite la ricerca semantica](find-similar-and-related-documents-with-semantic-search.md).</span><span class="sxs-lookup"><span data-stu-id="914c3-122">For more information, see [Find Key Phrases in Documents with Semantic Search](find-key-phrases-in-documents-with-semantic-search.md) and [Find Similar and Related Documents with Semantic Search](find-similar-and-related-documents-with-semantic-search.md).</span></span>  
  
-   <span data-ttu-id="914c3-123">Se non si specifica in modo esplicito un LCID per un indice semantico, per l'indicizzazione semantica vengono utilizzate solo la lingua principale e le statistiche sulla lingua associate.</span><span class="sxs-lookup"><span data-stu-id="914c3-123">If you do not explicitly specify an LCID for a semantic index, then only the primary language and its associated language statistics are used for semantic indexing.</span></span>  
  
-   <span data-ttu-id="914c3-124">Se si specifica una lingua per una colonna per cui non è disponibile il modello di lingua, la creazione dell'indice ha esito negativo e viene restituito un messaggio di errore.</span><span class="sxs-lookup"><span data-stu-id="914c3-124">If you specify a language for a column for which the language model is not available, the creation of the index fails and returns an error message.</span></span>  
  
###  <a name="how-to-create-a-semantic-index-when-there-is-no-full-text-index"></a><a name="HowToEnableCreate"></a><span data-ttu-id="914c3-125">Procedura: creare un indice semantico quando non esiste alcun indice full-text</span><span class="sxs-lookup"><span data-stu-id="914c3-125">How To: Create a Semantic Index When There Is No Full-Text Index</span></span>  
 <span data-ttu-id="914c3-126">Quando si crea un nuovo indice full-text con l'istruzione **CREATE FULLTEXT INDEX** , è possibile abilitare l'indicizzazione semantica a livello di colonna specificando la parola chiave **STATISTICAL_SEMANTICS** come parte della definizione della colonna.</span><span class="sxs-lookup"><span data-stu-id="914c3-126">When you create a new full-text index with the **CREATE FULLTEXT INDEX** statement, you can enable semantic indexing at the column level by specifying the keyword **STATISTICAL_SEMANTICS** as part of the column definition.</span></span> <span data-ttu-id="914c3-127">È inoltre possibile abilitare l'indicizzazione semantica quando si utilizza l'Indicizzazione guidata full-text per creare un nuovo indice full-text.</span><span class="sxs-lookup"><span data-stu-id="914c3-127">You can also enable semantic indexing when you use the Full-Text Indexing Wizard to create a new full-text index.</span></span>  
  
 <span data-ttu-id="914c3-128">**Creare un nuovo indice semantico tramite Transact-SQL**</span><span class="sxs-lookup"><span data-stu-id="914c3-128">**Create a new semantic index by using Transact-SQL**</span></span>  
 <span data-ttu-id="914c3-129">Chiamare l'istruzione **CREATE FULLTEXT INDEX** e specificare **STATISTICAL_SEMANTICS** per ogni colonna in cui creare un indice semantico.</span><span class="sxs-lookup"><span data-stu-id="914c3-129">Call the **CREATE FULLTEXT INDEX** statement and specify **STATISTICAL_SEMANTICS** for each column on which you want to create a semantic index.</span></span> <span data-ttu-id="914c3-130">Per altre informazioni su tutte le opzioni per questa istruzione, vedere [CREATE FULLTEXT INDEX &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-fulltext-index-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="914c3-130">For more information about all the options for this statement, see [CREATE FULLTEXT INDEX &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-fulltext-index-transact-sql).</span></span>  
  
 <span data-ttu-id="914c3-131">**Esempio 1: creazione di un indice univoco, di un indice full-text e di un indice semantico**</span><span class="sxs-lookup"><span data-stu-id="914c3-131">**Example 1: Create a unique index, full-text index, and semantic index**</span></span>  
  
 <span data-ttu-id="914c3-132">L'esempio riportato di seguito crea il catalogo full-text predefinito **ft**. L'esempio crea quindi un indice univoco nella colonna **JobCandidateID** della tabella **HumanResources.JobCandidate** del database di esempio AdventureWorks2012.</span><span class="sxs-lookup"><span data-stu-id="914c3-132">The following example creates a default full-text catalog, **ft**. The example then creates a unique index on the **JobCandidateID** column of the **HumanResources.JobCandidate** table of the AdventureWorks2012 sample database.</span></span> <span data-ttu-id="914c3-133">Questo indice univoco è necessario come colonna chiave di un indice full-text.</span><span class="sxs-lookup"><span data-stu-id="914c3-133">This unique index is required as the key column for a full-text index.</span></span> <span data-ttu-id="914c3-134">L'esempio crea infine un indice full-text e un indice semantico nella colonna **Resume** .</span><span class="sxs-lookup"><span data-stu-id="914c3-134">The example then creates a full-text index and a semantic index on the **Resume** column.</span></span>  
  
```sql  
CREATE FULLTEXT CATALOG ft AS DEFAULT  
GO  
  
CREATE UNIQUE INDEX ui_ukJobCand  
    ON HumanResources.JobCandidate(JobCandidateID)  
GO  
  
CREATE FULLTEXT INDEX ON HumanResources.JobCandidate  
    (Resume  
        Language 1033  
        Statistical_Semantics  
    )   
    KEY INDEX JobCandidateID   
    WITH STOPLIST = SYSTEM  
GO  
```  
  
 <span data-ttu-id="914c3-135">**Esempio: creazione di un indice full-text e semantico in diverse colonne con popolamento dell'indice posticipato**</span><span class="sxs-lookup"><span data-stu-id="914c3-135">**Example 2: Create a full-text and semantic index on several columns with delayed index population**</span></span>  
  
 <span data-ttu-id="914c3-136">L'esempio seguente crea un catalogo full-text **documents_catalog**nel database di esempio AdventureWorks2012.</span><span class="sxs-lookup"><span data-stu-id="914c3-136">The following example creates a full-text catalog, **documents_catalog**, in the AdventureWorks2012 sample database.</span></span> <span data-ttu-id="914c3-137">Nell'esempio viene quindi creato un indice full-text che utilizza questo nuovo catalogo.</span><span class="sxs-lookup"><span data-stu-id="914c3-137">The example then creates a full-text index that uses this new catalog.</span></span> <span data-ttu-id="914c3-138">L'indice full-text viene creato per le colonne **Title**, **DocumentSummary**e **Document** della tabella **Production.Document** , mentre l'indice semantico viene creato solo per la colonna **Document** .</span><span class="sxs-lookup"><span data-stu-id="914c3-138">The full-text index is created on the **Title**, **DocumentSummary**, and **Document** columns of the **Production.Document** table, while the semantic index is only created on the **Document** column.</span></span> <span data-ttu-id="914c3-139">Questo indice full-text usa il catalogo full-text appena creato e un indice di chiave univoca esistente, **PK_Document_DocumentID**.</span><span class="sxs-lookup"><span data-stu-id="914c3-139">This full-text index uses the newly-created full-text catalog and an existing unique key index, **PK_Document_DocumentID**.</span></span> <span data-ttu-id="914c3-140">Come consigliato, questa chiave di indice viene creata in una colonna Integer, **DocumentID**.</span><span class="sxs-lookup"><span data-stu-id="914c3-140">As recommended, this index key is created on an integer column, **DocumentID**.</span></span> <span data-ttu-id="914c3-141">Nell'esempio viene specificato l'LCID 1033 per l'inglese, che identifica la lingua dei dati presenti nelle colonne.</span><span class="sxs-lookup"><span data-stu-id="914c3-141">The example specifies the LCID for English, 1033, which is the language of the data in the columns.</span></span>  
  
 <span data-ttu-id="914c3-142">Nell'esempio viene anche specificato che il rilevamento delle modifiche è disabilitato e che non viene eseguito il popolamento.</span><span class="sxs-lookup"><span data-stu-id="914c3-142">This example also specifies that change tracking is off with no population.</span></span> <span data-ttu-id="914c3-143">In seguito, durante le ore di minore attività, l'esempio usa un'istruzione **ALTER FULLTEXT INDEX** per avviare un popolamento completo nel nuovo indice e abilitare il rilevamento automatico delle modifiche.</span><span class="sxs-lookup"><span data-stu-id="914c3-143">Later, during off-peak hours, the example uses an **ALTER FULLTEXT INDEX** statement to start a full population on the new index and enable automatic change tracking.</span></span>  
  
```sql  
CREATE FULLTEXT CATALOG documents_catalog  
GO  
  
CREATE FULLTEXT INDEX ON Production.Document  
    (   
    Title  
        Language 1033,   
    DocumentSummary  
        Language 1033,   
    Document   
        TYPE COLUMN FileExtension  
        Language 1033  
        Statistical_Semantics  
    )  
    KEY INDEX PK_Document_DocumentID  
        ON documents_catalog  
        WITH CHANGE_TRACKING OFF, NO POPULATION  
GO  
```  
  
 <span data-ttu-id="914c3-144">In un secondo momento, in un orario di minore attività, l'indice viene popolato:</span><span class="sxs-lookup"><span data-stu-id="914c3-144">Later, at an off-peak time, the index is populated:</span></span>  
  
```sql  
ALTER FULLTEXT INDEX ON Production.Document SET CHANGE_TRACKING AUTO  
GO  
```  
  
 <span data-ttu-id="914c3-145">**Creare un nuovo indice semantico tramite SQL Server Management Studio**</span><span class="sxs-lookup"><span data-stu-id="914c3-145">**Create a new semantic index by using SQL Server Management Studio**</span></span>  
 <span data-ttu-id="914c3-146">Eseguire l'Indicizzazione guidata full-text e abilitare **Semantica statistica** nella pagina **Selezione colonne tabella** per ogni colonna in cui creare un indice semantico.</span><span class="sxs-lookup"><span data-stu-id="914c3-146">Run the Full-Text Indexing Wizard and enable **Statistical Semantics** on the **Select Table Columns** page for each column on which you want to create a semantic index.</span></span> <span data-ttu-id="914c3-147">Per altre informazioni, comprese le informazioni sulla modalità di avvio dell'Indicizzazione guidata full-text, vedere [Usare l'Indicizzazione guidata full-text](use-the-full-text-indexing-wizard.md).</span><span class="sxs-lookup"><span data-stu-id="914c3-147">For more information, including information about how to start the Full-Text Indexing Wizard, see [Use the Full-Text Indexing Wizard](use-the-full-text-indexing-wizard.md).</span></span>  
  
###  <a name="how-to-create-a-semantic-index-when-there-is-an-existing-full-text-index"></a><a name="HowToEnableAlter"></a><span data-ttu-id="914c3-148">Procedura: creare un indice semantico quando esiste un indice full-text esistente</span><span class="sxs-lookup"><span data-stu-id="914c3-148">How To: Create a Semantic Index When There Is an Existing Full-Text Index</span></span>  
 <span data-ttu-id="914c3-149">È possibile aggiungere un'indicizzazione semantica quando si modifica un indice full-text esistente tramite l'istruzione **ALTER FULLTEXT INDEX** .</span><span class="sxs-lookup"><span data-stu-id="914c3-149">You can add semantic indexing when you alter an existing full-text index with the **ALTER FULLTEXT INDEX** statement.</span></span> <span data-ttu-id="914c3-150">È inoltre possibile aggiungere l'indicizzazione semantica utilizzando le varie finestre di dialogo in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="914c3-150">You can also add semantic indexing by using various dialog boxes in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span></span>  
  
 <span data-ttu-id="914c3-151">**Aggiungere un indice semantico tramite Transact-SQL**</span><span class="sxs-lookup"><span data-stu-id="914c3-151">**Add a semantic index by using Transact-SQL**</span></span>  
 <span data-ttu-id="914c3-152">Chiamare l'istruzione **ALTER FULLTEXT INDEX** con le opzioni descritte di seguito per ogni colonna in cui aggiungere un indice semantico.</span><span class="sxs-lookup"><span data-stu-id="914c3-152">Call the **ALTER FULLTEXT INDEX** statement with the options described below for each column on which you want to add a semantic index.</span></span> <span data-ttu-id="914c3-153">Per altre informazioni su tutte le opzioni per questa istruzione, vedere [ALTER FULLTEXT INDEX &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-fulltext-index-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="914c3-153">For more information about all the options for this statement, see [ALTER FULLTEXT INDEX &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-fulltext-index-transact-sql).</span></span>  
  
 <span data-ttu-id="914c3-154">Se non diversamente specificato, dopo una chiamata ad **ALTER** vengono ripopolati sia gli indici full-text, sia gli indici semantici.</span><span class="sxs-lookup"><span data-stu-id="914c3-154">Both full-text and semantic indexes are repopulated after a call to **ALTER**, unless you specify otherwise.</span></span>  
  
-   <span data-ttu-id="914c3-155">Per aggiungere l'indicizzazione full-text solo a una colonna, usare la sintassi **ADD** .</span><span class="sxs-lookup"><span data-stu-id="914c3-155">To add full-text indexing only to a column, use the **ADD** syntax.</span></span>  
  
-   <span data-ttu-id="914c3-156">Per aggiungere l'indicizzazione sia full-text, sia semantica a una colonna, usare la sintassi **ADD** con l'opzione **STATISTICAL_SEMANTICS** .</span><span class="sxs-lookup"><span data-stu-id="914c3-156">To add both full-text and semantic indexing to a column, use the **ADD** syntax with the **STATISTICAL_SEMANTICS** option.</span></span>  
  
-   <span data-ttu-id="914c3-157">Per aggiungere l'indicizzazione semantica a una colonna già abilitata per l'indicizzazione full-text, usare l'opzione **ADD STATISTICAL_SEMANTICS** .</span><span class="sxs-lookup"><span data-stu-id="914c3-157">To add semantic indexing to a column that is already enabled for full-text indexing, use the **ADD STATISTICAL_SEMANTICS** option.</span></span> <span data-ttu-id="914c3-158">È possibile aggiungere l'indicizzazione semantica solo a una colonna in una singola istruzione **ALTER** .</span><span class="sxs-lookup"><span data-stu-id="914c3-158">You can only add semantic indexing to one column in a single **ALTER** statement.</span></span>  
  
 <span data-ttu-id="914c3-159">**Esempio: aggiunta di indicizzazione semantica a una colonna già abilitata per l'indicizzazione full-text**</span><span class="sxs-lookup"><span data-stu-id="914c3-159">**Example: Add semantic indexing to a column that already has full-text indexing**</span></span>  
  
 <span data-ttu-id="914c3-160">Nell'esempio seguente viene modificato un indice full-text esistente nella tabella **Production.Document** del database di esempio AdventureWorks2012.</span><span class="sxs-lookup"><span data-stu-id="914c3-160">The following example alters an existing full-text index on **Production.Document** table in AdventureWorks2012 sample database.</span></span> <span data-ttu-id="914c3-161">Nell'esempio viene aggiunto un indice semantico nella colonna **Document** della tabella **Production.Document** , in cui è già presente un indice full-text.</span><span class="sxs-lookup"><span data-stu-id="914c3-161">The example adds a semantic index on the **Document** column of the **Production.Document** table, which already has a full-text index.</span></span> <span data-ttu-id="914c3-162">Nell'esempio viene specificato che l'indice non verrà ripopolato automaticamente.</span><span class="sxs-lookup"><span data-stu-id="914c3-162">The example specifies that the index will not be repopulated automatically.</span></span>  
  
```sql  
ALTER FULLTEXT INDEX ON Production.Document  
    ALTER COLUMN Document  
        ADD Statistical_Semantics  
    WITH NO POPULATION  
GO  
```  
  
 <span data-ttu-id="914c3-163">**Aggiungere un indice semantico tramite SQL Server Management Studio**</span><span class="sxs-lookup"><span data-stu-id="914c3-163">**Add a semantic index by using SQL Server Management Studio**</span></span>  
 <span data-ttu-id="914c3-164">È possibile modificare le colonne abilitate per l'indicizzazione semantica e full-text nella pagina **Colonne indice full-text** della finestra di dialogo **Proprietà indice full-text** .</span><span class="sxs-lookup"><span data-stu-id="914c3-164">You can change the columns that are enabled for semantic and full-text indexing on the **Full-Text Index Columns** page of the **Full-Text Index Properties** dialog box.</span></span> <span data-ttu-id="914c3-165">Per altre informazioni, vedere [Gestire indici full-text](../../database-engine/manage-full-text-indexes.md).</span><span class="sxs-lookup"><span data-stu-id="914c3-165">For more information, see [Manage Full-Text Indexes](../../database-engine/manage-full-text-indexes.md).</span></span>  
  
###  <a name="requirements-and-restrictions-for-altering-an-existing-index"></a><a name="addreq"></a><span data-ttu-id="914c3-166">Requisiti e restrizioni per la modifica di un indice esistente</span><span class="sxs-lookup"><span data-stu-id="914c3-166">Requirements and Restrictions for Altering an Existing Index</span></span>  
  
-   <span data-ttu-id="914c3-167">Non è possibile modificare un indice esistente mentre è in corso il popolamento dell'indice.</span><span class="sxs-lookup"><span data-stu-id="914c3-167">You cannot alter an existing index while population of the index is in progress.</span></span> <span data-ttu-id="914c3-168">Per altre informazioni sul monitoraggio dello stato di popolamento dell'indice, vedere [Gestire e monitorare la ricerca semantica](manage-and-monitor-semantic-search.md).</span><span class="sxs-lookup"><span data-stu-id="914c3-168">For more information on monitoring the progress of index population, see [Manage and Monitor Semantic Search](manage-and-monitor-semantic-search.md).</span></span>  
  
-   <span data-ttu-id="914c3-169">Non è possibile aggiungere l'indicizzazione a una colonna e modificare o eliminare l'indicizzazione per la stessa colonna in una singola chiamata all'istruzione **ALTER FULLTEXT INDEX** .</span><span class="sxs-lookup"><span data-stu-id="914c3-169">You cannot add indexing to a column, and alter or drop indexing for the same column, in a single call to the **ALTER FULLTEXT INDEX** statement.</span></span>  
  
##  <a name="dropping-a-semantic-index"></a><a name="dropping"></a><span data-ttu-id="914c3-170">Eliminazione di un indice semantico</span><span class="sxs-lookup"><span data-stu-id="914c3-170">Dropping a Semantic Index</span></span>  
  
###  <a name="how-to-drop-a-semantic-index"></a><a name="drophow"></a><span data-ttu-id="914c3-171">Procedura: eliminare un indice semantico</span><span class="sxs-lookup"><span data-stu-id="914c3-171">How to: Drop a Semantic Index</span></span>  
 <span data-ttu-id="914c3-172">È possibile eliminare un'indicizzazione semantica quando si modifica un indice full-text esistente tramite l'istruzione **ALTER FULLTEXT INDEX** .</span><span class="sxs-lookup"><span data-stu-id="914c3-172">You can drop semantic indexing when you alter an existing full-text index with the **ALTER FULLTEXT INDEX** statement.</span></span> <span data-ttu-id="914c3-173">È possibile eliminare inoltre l'indicizzazione semantica tramite le varie finestre di dialogo in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="914c3-173">You can also drop semantic indexing by using various dialog boxes in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span></span>  
  
 <span data-ttu-id="914c3-174">**Eliminare l'indice semantico tramite Transact-SQL**</span><span class="sxs-lookup"><span data-stu-id="914c3-174">**Drop a semantic index by using Transact-SQL**</span></span>  
 -   <span data-ttu-id="914c3-175">Per eliminare l'indicizzazione semantica solo da una colonna o da colonne, chiamare l'istruzione **ALTER FULLTEXT INDEX** con l'opzione **ALTER column***column_name***drop STATISTICAL_SEMANTICS** .</span><span class="sxs-lookup"><span data-stu-id="914c3-175">To drop semantic indexing only from a column or columns, call the **ALTER FULLTEXT INDEX** statement with the **ALTER COLUMN***column_name***DROP STATISTICAL_SEMANTICS** option.</span></span> <span data-ttu-id="914c3-176">È possibile eliminare l'indicizzazione da più colonne in una singola istruzione **ALTER** .</span><span class="sxs-lookup"><span data-stu-id="914c3-176">You can drop the indexing from multiple columns in a single **ALTER** statement.</span></span>  
  
    ```sql  
    USE database_name  
    GO  
  
    ALTER FULLTEXT INDEX  
        ALTER COLUMN column_name  
        DROP STATISTICAL_SEMANTICS  
    GO  
    ```  
  
-   <span data-ttu-id="914c3-177">Per eliminare l'indicizzazione full-text e semantica da una colonna, chiamare l'istruzione **ALTER FULLTEXT INDEX** con l'opzione **ALTER COLUMN***column_name***drop** .</span><span class="sxs-lookup"><span data-stu-id="914c3-177">To drop both full-text and semantic indexing from a column, call the **ALTER FULLTEXT INDEX** statement with the **ALTER COLUMN***column_name***DROP** option.</span></span>  
  
    ```sql  
    USE database_name  
    GO  
  
    ALTER FULLTEXT INDEX  
        ALTER COLUMN column_name  
        DROP  
    GO  
    ```  
  
 <span data-ttu-id="914c3-178">**Eliminare un indice semantico tramite SQL Server Management Studio**</span><span class="sxs-lookup"><span data-stu-id="914c3-178">**Drop a semantic index by using SQL Server Management Studio**</span></span>  
 <span data-ttu-id="914c3-179">È possibile modificare le colonne abilitate per l'indicizzazione semantica e full-text nella pagina **Colonne indice full-text** della finestra di dialogo **Proprietà indice full-text** .</span><span class="sxs-lookup"><span data-stu-id="914c3-179">You can change the columns that are enabled for semantic and full-text indexing on the **Full-Text Index Columns** page of the **Full-Text Index Properties** dialog box.</span></span> <span data-ttu-id="914c3-180">Per altre informazioni, vedere [Gestire indici full-text](../../database-engine/manage-full-text-indexes.md).</span><span class="sxs-lookup"><span data-stu-id="914c3-180">For more information, see [Manage Full-Text Indexes](../../database-engine/manage-full-text-indexes.md).</span></span>  
  
###  <a name="requirements-and-restrictions-for-dropping-a-semantic-index"></a><a name="dropreq"></a><span data-ttu-id="914c3-181">Requisiti e restrizioni per l'eliminazione di un indice semantico</span><span class="sxs-lookup"><span data-stu-id="914c3-181">Requirements and Restrictions for Dropping a Semantic Index</span></span>  
  
-   <span data-ttu-id="914c3-182">Non è possibile eliminare indicizzazione full-text da una colonna mantenendo l'indicizzazione semantica.</span><span class="sxs-lookup"><span data-stu-id="914c3-182">You cannot drop full-text indexing from a column while retaining semantic indexing.</span></span> <span data-ttu-id="914c3-183">L'indicizzazione semantica dipende dall'indicizzazione full-text per i risultati di somiglianza del documento.</span><span class="sxs-lookup"><span data-stu-id="914c3-183">Semantic indexing depends on full-text indexing for document similarity results.</span></span>  
  
-   <span data-ttu-id="914c3-184">Non è possibile specificare l'opzione **NO POPULATION** quando si elimina l'indicizzazione semantica dall'ultima colonna in una tabella per cui è stata abilitata l'indicizzazione semantica.</span><span class="sxs-lookup"><span data-stu-id="914c3-184">You cannot specify the **NO POPULATION** option when you drop semantic indexing from the last column in a table for which semantic indexing was enabled.</span></span> <span data-ttu-id="914c3-185">È necessario un ciclo di popolamento per rimuovere i risultati precedentemente indicizzati.</span><span class="sxs-lookup"><span data-stu-id="914c3-185">A population cycle is required to remove the results that were indexed previously.</span></span>  
  
## <a name="checking-whether-semantic-search-is-enabled-on-database-objects"></a><span data-ttu-id="914c3-186">Verifica dell'abilitazione della ricerca semantica su oggetti di database</span><span class="sxs-lookup"><span data-stu-id="914c3-186">Checking Whether Semantic Search Is Enabled on Database Objects</span></span>  
  
###  <a name="how-to-check-whether-semantic-search-is-enabled-on-database-objects"></a><a name="HowToCheckEnabled"></a><span data-ttu-id="914c3-187">Procedura: verificare se la ricerca semantica è abilitata per gli oggetti di database</span><span class="sxs-lookup"><span data-stu-id="914c3-187">How To: Check Whether Semantic Search Is Enabled on Database Objects</span></span>  
 <span data-ttu-id="914c3-188">**Verifica dell'abilitazione della ricerca semantica per un database**</span><span class="sxs-lookup"><span data-stu-id="914c3-188">**Is semantic search enabled for a database?**</span></span>  
 <span data-ttu-id="914c3-189">Eseguire una query sulla proprietà **IsFullTextEnabled** della funzione per i metadati [DATABASEPROPERTYEX &#40;Transact-SQL&#41;](/sql/t-sql/functions/databasepropertyex-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="914c3-189">Query the **IsFullTextEnabled** property of the [DATABASEPROPERTYEX &#40;Transact-SQL&#41;](/sql/t-sql/functions/databasepropertyex-transact-sql) metadata function.</span></span>  
  
 <span data-ttu-id="914c3-190">Se viene restituito il valore 1, la ricerca full-text e la ricerca semantica sono abilitate per il database. Se viene restituito il valore 0, le ricerche non sono abilitate.</span><span class="sxs-lookup"><span data-stu-id="914c3-190">A return value of 1 indicates that full-text search and semantic search are enabled for the database; a return value of 0 indicates that they are not enabled.</span></span>  
  
```sql  
SELECT DATABASEPROPERTYEX('database_name', 'IsFullTextEnabled')  
GO  
```  
  
 <span data-ttu-id="914c3-191">**Verifica dell'abilitazione della ricerca semantica per una tabella**</span><span class="sxs-lookup"><span data-stu-id="914c3-191">**Is semantic search enabled for a table?**</span></span>  
 <span data-ttu-id="914c3-192">Eseguire una query sulla proprietà **TableFullTextSemanticExtraction** della funzione per i metadati [OBJECTPROPERTYEX &#40;Transact-SQL&#41;](/sql/t-sql/functions/objectproperty-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="914c3-192">Query the **TableFullTextSemanticExtraction** property of the [OBJECTPROPERTYEX &#40;Transact-SQL&#41;](/sql/t-sql/functions/objectproperty-transact-sql) metadata function.</span></span>  
  
 <span data-ttu-id="914c3-193">Se viene restituito il valore 1, la ricerca semantica è abilitata per la tabella. Se viene restituito il valore 0, la ricerca non è abilitata.</span><span class="sxs-lookup"><span data-stu-id="914c3-193">A return value of 1 indicates that semantic search is enabled for the table; a return value of 0 indicates that it is not enabled.</span></span>  
  
```scr  
SELECT OBJECTPROPERTYEX(OBJECT_ID('table_name'), 'TableFullTextSemanticExtraction')  
GO  
```  
  
 <span data-ttu-id="914c3-194">**Verifica dell'abilitazione della ricerca semantica per una colonna**</span><span class="sxs-lookup"><span data-stu-id="914c3-194">**Is semantic search enabled for a column?**</span></span>  
 <span data-ttu-id="914c3-195">Per determinare se la ricerca semantica è abilitata per una colonna specifica:</span><span class="sxs-lookup"><span data-stu-id="914c3-195">To determine whether semantic search is enabled for a specific column:</span></span>  
  
-   <span data-ttu-id="914c3-196">Eseguire una query sulla proprietà **StatisticalSemantics** della funzione per i metadati [COLUMNPROPERTY &#40;Transact-SQL&#41;](/sql/t-sql/functions/columnproperty-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="914c3-196">Query the **StatisticalSemantics** property of the [COLUMNPROPERTY &#40;Transact-SQL&#41;](/sql/t-sql/functions/columnproperty-transact-sql) metadata function.</span></span>  
  
     <span data-ttu-id="914c3-197">Se viene restituito il valore 1, la ricerca semantica è abilitata per la colonna. Se viene restituito il valore 0, la ricerca non è abilitata.</span><span class="sxs-lookup"><span data-stu-id="914c3-197">A return value of 1 indicates that semantic search is enabled for the column; a return value of 0 indicates that it is not enabled.</span></span>  
  
    ```sql  
    SELECT COLUMNPROPERTY(OBJECT_ID('table_name'), 'column_name', 'StatisticalSemantics')  
    GO  
    ```  
  
-   <span data-ttu-id="914c3-198">Eseguire una query sulla vista del catalogo [sys.fulltext_index_columns &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-fulltext-index-columns-transact-sql) per l'indice full-text.</span><span class="sxs-lookup"><span data-stu-id="914c3-198">Query the catalog view [sys.fulltext_index_columns &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-fulltext-index-columns-transact-sql) for the full-text index.</span></span>  
  
     <span data-ttu-id="914c3-199">Il valore 1 nella colonna **statistical_semantics** indica che la colonna specificata è abilitata per l'indicizzazione semantica oltre che per l'indicizzazione full-text.</span><span class="sxs-lookup"><span data-stu-id="914c3-199">A value of 1 in the **statistical_semantics** column indicates that the specified column is enabled for semantic indexing in addition to full-text indexing.</span></span>  
  
    ```sql  
    SELECT * FROM sys.fulltext_index_columns WHERE object_id = OBJECT_ID('table_name')  
    GO  
    ```  
  
-   <span data-ttu-id="914c3-200">In Esplora oggetti in [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)]fare clic con il pulsante destro del mouse su una colonna e scegliere **Proprietà**.</span><span class="sxs-lookup"><span data-stu-id="914c3-200">In Object Explorer in [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)], right-click on a column and select **Properties**.</span></span> <span data-ttu-id="914c3-201">Nella pagina **Generale** della finestra di dialogo **Proprietà colonna** verificare il valore della proprietà **Semantica statistica** .</span><span class="sxs-lookup"><span data-stu-id="914c3-201">On the **General** page of the **Column Properties** dialog box, check the value of the **Statistical Semantics** property.</span></span>  
  
     <span data-ttu-id="914c3-202">Il valore True indica che la colonna specificata è abilitata per l'indicizzazione semantica oltre che per l'indicizzazione full-text.</span><span class="sxs-lookup"><span data-stu-id="914c3-202">A value of True indicates that the specified column is enabled for semantic indexing in addition to full-text indexing.</span></span>  
  
## <a name="determining-what-can-be-indexed-for-semantic-search"></a><span data-ttu-id="914c3-203">Determinare ciò che può essere indicizzato per la ricerca semantica</span><span class="sxs-lookup"><span data-stu-id="914c3-203">Determining What Can Be Indexed for Semantic Search</span></span>  
  
###  <a name="how-to-check-which-languages-are-supported-for-semantic-search"></a><a name="HowToCheckLanguages"></a><span data-ttu-id="914c3-204">Procedura: verificare quali lingue sono supportate per la ricerca semantica</span><span class="sxs-lookup"><span data-stu-id="914c3-204">How To: Check Which Languages Are Supported for Semantic Search</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="914c3-205">L'indicizzazione semantica supporta un numero minore di lingue rispetto all'indicizzazione full-text.</span><span class="sxs-lookup"><span data-stu-id="914c3-205">Fewer languages are supported for semantic indexing than for full-text indexing.</span></span> <span data-ttu-id="914c3-206">Di conseguenza, alcune colonne supportano l'indicizzazione full-text, ma non l'indicizzazione semantica.</span><span class="sxs-lookup"><span data-stu-id="914c3-206">As a result, there may be columns that you can index for full-text search, but not for semantic search.</span></span>  
  
 <span data-ttu-id="914c3-207">Eseguire una query sulla vista del catalogo [sys.fulltext_semantic_languages &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-fulltext-semantic-languages-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="914c3-207">Query the catalog view [sys.fulltext_semantic_languages &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-fulltext-semantic-languages-transact-sql).</span></span>  
  
```sql  
SELECT * FROM sys.fulltext_semantic_languages  
GO  
```  
  
 <span data-ttu-id="914c3-208">Per l'indicizzazione semantica sono supportate le lingue seguenti.</span><span class="sxs-lookup"><span data-stu-id="914c3-208">The following languages are supported for semantic indexing.</span></span> <span data-ttu-id="914c3-209">Questo elenco rappresenta l'output della vista del catalogo [sys.fulltext_semantic_languages &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-fulltext-semantic-languages-transact-sql), ordinato per LCID.</span><span class="sxs-lookup"><span data-stu-id="914c3-209">This list represents the output of the catalog view [sys.fulltext_semantic_languages &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-fulltext-semantic-languages-transact-sql), ordered by LCID.</span></span>  
  
|<span data-ttu-id="914c3-210">Linguaggio</span><span class="sxs-lookup"><span data-stu-id="914c3-210">Language</span></span>|<span data-ttu-id="914c3-211">LCID</span><span class="sxs-lookup"><span data-stu-id="914c3-211">LCID</span></span>|  
|--------------|----------|  
|<span data-ttu-id="914c3-212">Tedesco</span><span class="sxs-lookup"><span data-stu-id="914c3-212">German</span></span>|<span data-ttu-id="914c3-213">1031</span><span class="sxs-lookup"><span data-stu-id="914c3-213">1031</span></span>|  
|<span data-ttu-id="914c3-214">Inglese (Stati Uniti)</span><span class="sxs-lookup"><span data-stu-id="914c3-214">English (US)</span></span>|<span data-ttu-id="914c3-215">1033</span><span class="sxs-lookup"><span data-stu-id="914c3-215">1033</span></span>|  
|<span data-ttu-id="914c3-216">Francese</span><span class="sxs-lookup"><span data-stu-id="914c3-216">French</span></span>|<span data-ttu-id="914c3-217">1036</span><span class="sxs-lookup"><span data-stu-id="914c3-217">1036</span></span>|  
|<span data-ttu-id="914c3-218">Italiano</span><span class="sxs-lookup"><span data-stu-id="914c3-218">Italian</span></span>|<span data-ttu-id="914c3-219">1040</span><span class="sxs-lookup"><span data-stu-id="914c3-219">1040</span></span>|  
|<span data-ttu-id="914c3-220">Portoghese (Brasile)</span><span class="sxs-lookup"><span data-stu-id="914c3-220">Portuguese (Brazil)</span></span>|<span data-ttu-id="914c3-221">1046</span><span class="sxs-lookup"><span data-stu-id="914c3-221">1046</span></span>|  
|<span data-ttu-id="914c3-222">Russo</span><span class="sxs-lookup"><span data-stu-id="914c3-222">Russian</span></span>|<span data-ttu-id="914c3-223">1049</span><span class="sxs-lookup"><span data-stu-id="914c3-223">1049</span></span>|  
|<span data-ttu-id="914c3-224">Svedese</span><span class="sxs-lookup"><span data-stu-id="914c3-224">Swedish</span></span>|<span data-ttu-id="914c3-225">1053</span><span class="sxs-lookup"><span data-stu-id="914c3-225">1053</span></span>|  
|<span data-ttu-id="914c3-226">Inglese (Regno Unito)</span><span class="sxs-lookup"><span data-stu-id="914c3-226">English (UK)</span></span>|<span data-ttu-id="914c3-227">2057</span><span class="sxs-lookup"><span data-stu-id="914c3-227">2057</span></span>|  
|<span data-ttu-id="914c3-228">Portoghese (Portogallo)</span><span class="sxs-lookup"><span data-stu-id="914c3-228">Portuguese (Portugal)</span></span>|<span data-ttu-id="914c3-229">2070</span><span class="sxs-lookup"><span data-stu-id="914c3-229">2070</span></span>|  
|<span data-ttu-id="914c3-230">Spagnolo</span><span class="sxs-lookup"><span data-stu-id="914c3-230">Spanish</span></span>|<span data-ttu-id="914c3-231">3082</span><span class="sxs-lookup"><span data-stu-id="914c3-231">3082</span></span>|  
  
###  <a name="how-to-determine-which-document-types-can-be-indexed"></a><a name="doctypes"></a><span data-ttu-id="914c3-232">Procedura: determinare quali tipi di documenti è possibile indicizzare</span><span class="sxs-lookup"><span data-stu-id="914c3-232">How To: Determine Which Document Types Can Be Indexed</span></span>  
 <span data-ttu-id="914c3-233">Eseguire una query sulla vista del catalogo [sys.fulltext_document_types &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-fulltext-document-types-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="914c3-233">Query the catalog view [sys.fulltext_document_types &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-fulltext-document-types-transact-sql).</span></span>  
  
 <span data-ttu-id="914c3-234">Se il tipo di documento che si desidera indicizzare non è nell'elenco di tipi supportati, può essere necessario individuare, scaricare e installare filtri aggiuntivi.</span><span class="sxs-lookup"><span data-stu-id="914c3-234">If the document type that you want to index is not in the list of supported types, then you may have to locate, download, and install additional filters.</span></span> <span data-ttu-id="914c3-235">Per altre informazioni, vedere [Visualizzazione o modifica di word breaker e filtri registrati](view-or-change-registered-filters-and-word-breakers.md).</span><span class="sxs-lookup"><span data-stu-id="914c3-235">For more information, see [View or Change Registered Filters and Word Breakers](view-or-change-registered-filters-and-word-breakers.md).</span></span>  
  
##  <a name="best-practice-consider-creating-a-separate-filegroup-for-the-full-text-and-semantic-indexes"></a><a name="BestPracticeFilegroup"></a><span data-ttu-id="914c3-236">Procedura consigliata: provare a creare un filegroup distinto per gli indici full-text e semantico</span><span class="sxs-lookup"><span data-stu-id="914c3-236">Best Practice: Consider Creating a Separate Filegroup for the Full-Text and Semantic Indexes</span></span>  
 <span data-ttu-id="914c3-237">Valutare se creare un filegroup distinto per gli indici full-text e semantici se l'allocazione di spazio su disco costituisce un problema.</span><span class="sxs-lookup"><span data-stu-id="914c3-237">Consider creating a separate filegroup for the full-text and semantic indexes if disk space allocation is a concern.</span></span> <span data-ttu-id="914c3-238">Gli indici semantici vengono creati nello stesso filegroup dell'indice full-text.</span><span class="sxs-lookup"><span data-stu-id="914c3-238">The semantic indexes are created in the same filegroup as the full-text index.</span></span> <span data-ttu-id="914c3-239">Un indice semantico completamente popolato può contenere una notevole quantità di dati.</span><span class="sxs-lookup"><span data-stu-id="914c3-239">A fully populated semantic index may contain large amount of data.</span></span>  
  
##  <a name="BestPracticeUnderstand"></a>   
##  <a name="problem-searching-on-specific-column-returns-no-results"></a><a name="IssueNoResults"></a><span data-ttu-id="914c3-240">Problema: la ricerca in una colonna specifica non restituisce alcun risultato</span><span class="sxs-lookup"><span data-stu-id="914c3-240">Problem: Searching on Specific Column Returns No Results</span></span>  
 <span data-ttu-id="914c3-241">**È possibile che sia stato specificato un LCID non Unicode per una lingua Unicode.**</span><span class="sxs-lookup"><span data-stu-id="914c3-241">**Was a non-Unicode LCID specified for a Unicode language?**</span></span>  
 <span data-ttu-id="914c3-242">È possibile abilitare l'indicizzazione semantica in un tipo di colonna non Unicode con un LCID per una lingua che include solo parole Unicode, ad esempio l'LCID 1049 per il russo.</span><span class="sxs-lookup"><span data-stu-id="914c3-242">It is possible to enable semantic indexing on a non-Unicode column type with an LCID for a language that only has Unicode words, such as LCID 1049 for Russian.</span></span> <span data-ttu-id="914c3-243">In questo caso, non verrà restituito alcun risultato dagli indici semantici in questa colonna.</span><span class="sxs-lookup"><span data-stu-id="914c3-243">In this case, no results will ever be returned from the semantic indexes on this column.</span></span>  
  
  
