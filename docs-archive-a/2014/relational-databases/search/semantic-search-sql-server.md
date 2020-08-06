---
title: Ricerca semantica (SQL Server) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: search
ms.topic: conceptual
helpviewer_keywords:
- semantic search [SQL Server]
- semantic search [SQL Server], overview
- statistical semantic search [SQL Server]
- statistical semantic search [SQL Server], overview
ms.assetid: cd8faa9d-07db-420d-93f4-a2ea7c974b97
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 91062864b77ba3c62a87d66b8ff93068f9c10c8c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87719806"
---
# <a name="semantic-search-sql-server"></a><span data-ttu-id="3c49e-102">Ricerca semantica (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="3c49e-102">Semantic Search (SQL Server)</span></span>
  <span data-ttu-id="3c49e-103">La ricerca semantica statistica offre una visione approfondita dei documenti non strutturati archiviati in database di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] tramite l'estrazione e l'indicizzazione di *frasi chiave*statisticamente pertinenti.</span><span class="sxs-lookup"><span data-stu-id="3c49e-103">Statistical Semantic Search provides deep insight into unstructured documents stored in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] databases by extracting and indexing statistically relevant *key phrases*.</span></span> <span data-ttu-id="3c49e-104">Le frasi chiave vengono inoltre usate per identificare e indicizzare *documenti simili o correlati*.</span><span class="sxs-lookup"><span data-stu-id="3c49e-104">Then it also uses these key phrases to identify and index *documents that are similar or related*.</span></span>  
  
 <span data-ttu-id="3c49e-105">Per eseguire query sugli indici semantici si usano tre funzioni di set di righe Transact-SQL per recuperare i risultati come dati strutturati.</span><span class="sxs-lookup"><span data-stu-id="3c49e-105">You query these semantic indexes by using three Transact-SQL rowset functions to retrieve the results as structured data.</span></span>  
  
##  <a name="what-can-i-do-with-semantic-search"></a><a name="whatcanido"></a><span data-ttu-id="3c49e-106">Cosa è possibile fare con la ricerca semantica?</span><span class="sxs-lookup"><span data-stu-id="3c49e-106">What Can I Do with Semantic Search?</span></span>  
 <span data-ttu-id="3c49e-107">La ricerca semantica è basata sulla caratteristica di ricerca full-text esistente di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], ma consente nuovi scenari che vanno oltre le ricerche di parole chiave.</span><span class="sxs-lookup"><span data-stu-id="3c49e-107">Semantic search builds upon the existing full-text search feature in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], but enables new scenarios that extend beyond keyword searches.</span></span> <span data-ttu-id="3c49e-108">Mentre la ricerca full-text consente di eseguire query sulle *parole* in un documento, la ricerca semantica consente di eseguire query sul *significato* del documento.</span><span class="sxs-lookup"><span data-stu-id="3c49e-108">While full-text search lets you query the *words* in a document, semantic search lets you query the *meaning* of the document.</span></span> <span data-ttu-id="3c49e-109">Esempi di soluzioni ora possibili includono l'estrazione automatica dei tag, l'individuazione di contenuto correlato e la navigazione gerarchica in contenuto simile.</span><span class="sxs-lookup"><span data-stu-id="3c49e-109">Solutions that are now possible include automatic tag extraction, related content discovery, and hierarchical navigation across similar content.</span></span> <span data-ttu-id="3c49e-110">Ad esempio, è possibile eseguire una query sull'indice di frasi chiave per compilare la tassonomia per un'organizzazione o per una raccolta di documenti.</span><span class="sxs-lookup"><span data-stu-id="3c49e-110">For example, you can query the index of key phrases to build the taxonomy for an organization, or for a corpus of documents.</span></span> <span data-ttu-id="3c49e-111">In alternativa, è possibile eseguire una query sull'indice di somiglianza dei documenti per identificare i curriculum che corrispondono a un'offerta di lavoro.</span><span class="sxs-lookup"><span data-stu-id="3c49e-111">Or, you can query the document similarity index to identify resumes that match a job description.</span></span>  
  
 <span data-ttu-id="3c49e-112">Negli esempi seguenti vengono illustrate le capacità della ricerca semantica.</span><span class="sxs-lookup"><span data-stu-id="3c49e-112">The following examples demonstrate the capabilities of Semantic Search.</span></span>  
  
###  <a name="find-the-key-phrases-in-a-document"></a><a name="find1"></a><span data-ttu-id="3c49e-113">Trovare le frasi chiave in un documento</span><span class="sxs-lookup"><span data-stu-id="3c49e-113">Find the Key Phrases in a Document</span></span>  
 <span data-ttu-id="3c49e-114">Nella query seguente vengono ottenute le frasi chiave identificate nel documento di esempio.</span><span class="sxs-lookup"><span data-stu-id="3c49e-114">The following query gets the key phrases that were identified in the sample document.</span></span> <span data-ttu-id="3c49e-115">Presenta i risultati in ordine decrescente in base al punteggio di classificazione della rilevanza statistica di ogni frase chiave.</span><span class="sxs-lookup"><span data-stu-id="3c49e-115">It presents the results in descending order by the score that ranks the statistical significance of each key phrase.</span></span> <span data-ttu-id="3c49e-116">Questa query chiama la funzione [semantickeyphrasetable &#40;Transact-SQL&#41;](/sql/relational-databases/system-functions/semantickeyphrasetable-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="3c49e-116">This query calls the [semantickeyphrasetable &#40;Transact-SQL&#41;](/sql/relational-databases/system-functions/semantickeyphrasetable-transact-sql) function.</span></span>  
  
```sql  
SET @Title = 'Sample Document.docx'  
  
SELECT @DocID = DocumentID  
    FROM Documents  
    WHERE DocumentTitle = @Title  
  
SELECT @Title AS Title, keyphrase, score  
    FROM SEMANTICKEYPHRASETABLE(Documents, *, @DocID)  
    ORDER BY score DESC  
  
```  
  
  
  
###  <a name="find-similar-or-related-documents"></a><a name="find2"></a><span data-ttu-id="3c49e-117">Trovare documenti simili o correlati</span><span class="sxs-lookup"><span data-stu-id="3c49e-117">Find Similar or Related Documents</span></span>  
 <span data-ttu-id="3c49e-118">Nella query seguente vengono ottenuti i documenti identificati come simili o correlati al documento di esempio.</span><span class="sxs-lookup"><span data-stu-id="3c49e-118">The following query gets the documents that were identified as similar or related to the sample document.</span></span> <span data-ttu-id="3c49e-119">Presenta i risultati in ordine decrescente in base al punteggio di classificazione della somiglianza dei 2 documenti.</span><span class="sxs-lookup"><span data-stu-id="3c49e-119">It presents the results in descending order by the score that ranks the similarity of the 2 documents.</span></span> <span data-ttu-id="3c49e-120">Questa query chiama la funzione [semanticsimilaritytable &#40;Transact-SQL&#41;](/sql/relational-databases/system-functions/semanticsimilaritytable-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="3c49e-120">This query calls the [semanticsimilaritytable &#40;Transact-SQL&#41;](/sql/relational-databases/system-functions/semanticsimilaritytable-transact-sql) function.</span></span>  
  
```vb  
SET @Title = 'Sample Document.docx'  
  
SELECT @DocID = DocumentID  
    FROM Documents  
    WHERE DocumentTitle = @Title  
  
SELECT @Title AS SourceTitle, DocumentTitle AS MatchedTitle,  
        DocumentID, score  
    FROM SEMANTICSIMILARITYTABLE(Documents, *, @DocID)  
    INNER JOIN Documents ON DocumentID = matched_document_key  
    ORDER BY score DESC  
  
```  
  
  
  
###  <a name="find-the-key-phrases-that-make-documents-similar-or-related"></a><a name="find3"></a><span data-ttu-id="3c49e-121">Trovare le frasi chiave che rendono simili o correlati i documenti</span><span class="sxs-lookup"><span data-stu-id="3c49e-121">Find the Key Phrases That Make Documents Similar or Related</span></span>  
 <span data-ttu-id="3c49e-122">Nella query seguente vengono ottenute le frasi chiavi indicanti la somiglianza o la correlazione tra due documenti di esempio.</span><span class="sxs-lookup"><span data-stu-id="3c49e-122">The following query gets the key phrases that make the 2 sample documents similar or related to one another.</span></span> <span data-ttu-id="3c49e-123">Presenta i risultati in ordine decrescente in base al punteggio di classificazione del peso di ogni frase chiave.</span><span class="sxs-lookup"><span data-stu-id="3c49e-123">It presents the results in descending order by the score that ranks the weight of each key phrase.</span></span> <span data-ttu-id="3c49e-124">Questa query chiama la funzione [semanticsimilaritydetailstable &#40;Transact-SQL&#41;](/sql/relational-databases/system-functions/semanticsimilaritydetailstable-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="3c49e-124">This query calls the [semanticsimilaritydetailstable &#40;Transact-SQL&#41;](/sql/relational-databases/system-functions/semanticsimilaritydetailstable-transact-sql) function.</span></span>  
  
```sql  
SET @SourceTitle = 'first.docx'  
SET @MatchedTitle = 'second.docx'  
  
SELECT @SourceDocID = DocumentID FROM Documents WHERE DocumentTitle = @SourceTitle  
SELECT @MatchedDocID = DocumentID FROM Documents WHERE DocumentTitle = @MatchedTitle  
  
SELECT @SourceTitle AS SourceTitle, @MatchedTitle AS MatchedTitle, keyphrase, score  
    FROM semanticsimilaritydetailstable(Documents, DocumentContent,  
        @SourceDocID, DocumentContent, @MatchedDocID)  
    ORDER BY score DESC  
  
```  
  
  
  
##  <a name="storing-documents-in-sql-server"></a><a name="store"></a><span data-ttu-id="3c49e-125">Archiviazione di documenti in SQL Server</span><span class="sxs-lookup"><span data-stu-id="3c49e-125">Storing Documents in SQL Server</span></span>  
 <span data-ttu-id="3c49e-126">Per poter indicizzare documenti con la ricerca semantica, è necessario archiviarli in un database di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="3c49e-126">Before you can index documents with Semantic Search, you have to store the documents in a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] database.</span></span>  
  
 <span data-ttu-id="3c49e-127">La funzionalità FileTable in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] consente di inserire perfettamente file e documenti non strutturati nel database relazionale.</span><span class="sxs-lookup"><span data-stu-id="3c49e-127">The FileTable feature in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] makes unstructured files and documents first-class citizens of the relational database.</span></span> <span data-ttu-id="3c49e-128">Di conseguenza, gli sviluppatori di database possono modificare documenti insieme a dati strutturati in operazioni basate su set Transact-SQL.</span><span class="sxs-lookup"><span data-stu-id="3c49e-128">As a result, database developers can manipulate documents together with structured data in Transact-SQL set-based operations.</span></span>  
  
 <span data-ttu-id="3c49e-129">Per altre informazioni sulla caratteristica FileTable, vedere [FileTables &#40;SQL Server&#41;](../blob/filetables-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="3c49e-129">For more information about the FileTable feature, see [FileTables &#40;SQL Server&#41;](../blob/filetables-sql-server.md).</span></span> <span data-ttu-id="3c49e-130">Per informazioni sulla caratteristica FILESTREAM, ovvero un'altra opzione per l'archiviazione di documenti nel database vedere [FILESTREAM &#40;SQL Server&#41;](../blob/filestream-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="3c49e-130">For information about the FILESTREAM feature, which is another option for storing documents in the database, see [FILESTREAM &#40;SQL Server&#41;](../blob/filestream-sql-server.md).</span></span>  
  
  
  
##  <a name="related-tasks"></a><a name="reltasks"></a> <span data-ttu-id="3c49e-131">Attività correlate</span><span class="sxs-lookup"><span data-stu-id="3c49e-131">Related Tasks</span></span>  
 [<span data-ttu-id="3c49e-132">Installare e configurare la ricerca semantica</span><span class="sxs-lookup"><span data-stu-id="3c49e-132">Install and Configure Semantic Search</span></span>](install-and-configure-semantic-search.md)  
 <span data-ttu-id="3c49e-133">Vengono descritti i prerequisiti per la ricerca semantica statistica e viene indicato come installarli o verificarli.</span><span class="sxs-lookup"><span data-stu-id="3c49e-133">Describes the prerequisites for statistical semantic search and how to install or check them.</span></span>  
  
 [<span data-ttu-id="3c49e-134">Abilitare la ricerca semantica in tabelle e colonne</span><span class="sxs-lookup"><span data-stu-id="3c49e-134">Enable Semantic Search on Tables and Columns</span></span>](enable-semantic-search-on-tables-and-columns.md)  
 <span data-ttu-id="3c49e-135">Viene descritto come abilitare o disabilitare l'indicizzazione semantica statistica in colonne selezionate contenenti documenti o testo.</span><span class="sxs-lookup"><span data-stu-id="3c49e-135">Describes how to enable or disable statistical semantic indexing on selected columns that contain documents or text.</span></span>  
  
 [<span data-ttu-id="3c49e-136">Trovare frasi chiave nei documenti tramite la ricerca semantica</span><span class="sxs-lookup"><span data-stu-id="3c49e-136">Find Key Phrases in Documents with Semantic Search</span></span>](find-key-phrases-in-documents-with-semantic-search.md)  
 <span data-ttu-id="3c49e-137">Viene descritto come individuare le frasi chiave nei documenti o nelle colonne di testo configurati per l'indicizzazione semantica statistica.</span><span class="sxs-lookup"><span data-stu-id="3c49e-137">Describes how to find the key phrases in documents or text columns that are configured for statistical semantic indexing.</span></span>  
  
 [<span data-ttu-id="3c49e-138">Trovare documenti simili e correlati tramite la ricerca semantica</span><span class="sxs-lookup"><span data-stu-id="3c49e-138">Find Similar and Related Documents with Semantic Search</span></span>](find-similar-and-related-documents-with-semantic-search.md)  
 <span data-ttu-id="3c49e-139">Viene descritto come reperire documenti o valori di testo simili o correlati, nonché informazioni relative alla somiglianza o correlazione, in colonne configurate per l'indicizzazione semantica statistica.</span><span class="sxs-lookup"><span data-stu-id="3c49e-139">Describes how to find similar or related documents or text values, and information about how they are similar or related, in columns that are configured for statistical semantic indexing.</span></span>  
  
 [<span data-ttu-id="3c49e-140">Gestire e monitorare la ricerca semantica</span><span class="sxs-lookup"><span data-stu-id="3c49e-140">Manage and Monitor Semantic Search</span></span>](manage-and-monitor-semantic-search.md)  
 <span data-ttu-id="3c49e-141">Vengono descritti il processo di indicizzazione semantica e le attività correlate al monitoraggio e alla gestione degli indici.</span><span class="sxs-lookup"><span data-stu-id="3c49e-141">Describes the process of semantic indexing and the tasks related to monitoring and managing the indexes.</span></span>  
  
##  <a name="related-content"></a><a name="relcontent"></a> <span data-ttu-id="3c49e-142">Contenuto correlato</span><span class="sxs-lookup"><span data-stu-id="3c49e-142">Related Content</span></span>  
 [<span data-ttu-id="3c49e-143">DDL, funzioni, stored procedure e viste di ricerca semantica</span><span class="sxs-lookup"><span data-stu-id="3c49e-143">Semantic Search DDL, Functions, Stored Procedures, and Views</span></span>](../views/views.md)  
 <span data-ttu-id="3c49e-144">Sono elencati le istruzioni Transact-SQL e gli oggetti di database di SQL Server aggiunti o modificati per supportare la ricerca semantica statistica.</span><span class="sxs-lookup"><span data-stu-id="3c49e-144">Lists the Transact-SQL statements and the SQL Server database objects added or changed to support statistical semantic search.</span></span>  
  
  
