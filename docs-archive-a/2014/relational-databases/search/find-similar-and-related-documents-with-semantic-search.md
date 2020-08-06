---
title: Trovare documenti simili e correlati tramite la ricerca semantica | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: search
ms.topic: conceptual
helpviewer_keywords:
- semantic search [SQL Server], document similarity queries
ms.assetid: 9f527883-031b-442f-8e95-24bc0151ecbf
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: b11493b5b04fa9308e3afbe56176251225248338
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87637726"
---
# <a name="find-similar-and-related-documents-with-semantic-search"></a><span data-ttu-id="2be65-102">Trovare documenti simili e correlati tramite la ricerca semantica</span><span class="sxs-lookup"><span data-stu-id="2be65-102">Find Similar and Related Documents with Semantic Search</span></span>
  <span data-ttu-id="2be65-103">Viene descritto come reperire documenti o valori di testo simili o correlati, nonché informazioni relative alla somiglianza o correlazione, in colonne configurate per l'indicizzazione semantica statistica.</span><span class="sxs-lookup"><span data-stu-id="2be65-103">Describes how to find similar or related documents or text values, and information about how they are similar or related, in columns that are configured for statistical semantic indexing.</span></span>  
  
##  <a name="finding-similar-or-related-documents"></a><a name="BasicsQuerySimilar"></a><span data-ttu-id="2be65-104">Ricerca di documenti simili o correlati</span><span class="sxs-lookup"><span data-stu-id="2be65-104">Finding Similar or Related Documents</span></span>  
  
###  <a name="how-to-find-similar-or-related-documents-with-semanticsimilaritytable"></a><a name="HowToQuerySimilar"></a><span data-ttu-id="2be65-105">Procedura: trovare documenti simili o correlati con SEMANTICSIMILARITYTABLE</span><span class="sxs-lookup"><span data-stu-id="2be65-105">How To: Find Similar or Related Documents with SEMANTICSIMILARITYTABLE</span></span>  
 <span data-ttu-id="2be65-106">Per identificare documenti simili o correlati in una colonna specifica, eseguire una query sulla funzione [semanticsimilaritytable &#40;Transact-SQL&#41;](/sql/relational-databases/system-functions/semanticsimilaritytable-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="2be65-106">To identify similar or related documents in a specific column, query the function [semanticsimilaritytable &#40;Transact-SQL&#41;](/sql/relational-databases/system-functions/semanticsimilaritytable-transact-sql).</span></span>  
  
 <span data-ttu-id="2be65-107">**SEMANTICSIMILARITYTABLE** restituisce una tabella di zero, una o più righe per le colonne il cui contenuto nella colonna specificata è semanticamente simile a un documento specificato.</span><span class="sxs-lookup"><span data-stu-id="2be65-107">**SEMANTICSIMILARITYTABLE** returns a table of zero, one, or more rows whose content in the specified column is semantically similar to the specified document.</span></span> <span data-ttu-id="2be65-108">A questa funzione del set di righe è possibile fare riferimento nella clausola FROM di un'istruzione SELECT come normale nome di tabella.</span><span class="sxs-lookup"><span data-stu-id="2be65-108">This rowset function can be referenced in the FROM clause of a SELECT statement like a regular table name.</span></span>  
  
 <span data-ttu-id="2be65-109">Non è possibile eseguire una query su diverse colonne per ottenere documenti simili.</span><span class="sxs-lookup"><span data-stu-id="2be65-109">You cannot query across columns for similar documents.</span></span> <span data-ttu-id="2be65-110">La funzione **SEMANTICSIMILARITYTABLE** recupera risultati solo dalla stessa colonna specificata come colonna di origine, identificata dall'argomento **source_key** .</span><span class="sxs-lookup"><span data-stu-id="2be65-110">The **SEMANTICSIMILARITYTABLE** function only retrieves results from the same column as the source column, which is identified by the **source_key** argument.</span></span>  
  
 <span data-ttu-id="2be65-111">Per informazioni dettagliate sui parametri necessari per la funzione **SEMANTICSIMILARITYTABLE** e sulla tabella dei risultati restituita, vedere [semanticsimilaritytable &#40;Transact-SQL&#41;](/sql/relational-databases/system-functions/semanticsimilaritytable-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="2be65-111">For detailed information about the parameters required by the **SEMANTICSIMILARITYTABLE** function, and about the table of results that it returns, see [semanticsimilaritytable &#40;Transact-SQL&#41;](/sql/relational-databases/system-functions/semanticsimilaritytable-transact-sql).</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="2be65-112">Per le colonne di destinazione deve essere abilitata l'indicizzazione full-text e semantica.</span><span class="sxs-lookup"><span data-stu-id="2be65-112">The columns that you target must have full-text and semantic indexing enabled.</span></span>  
  
###  <a name="example-find-the-top-documents-that-are-similar-to-another-document"></a><a name="HowToIdentifySimilar"></a><span data-ttu-id="2be65-113">Esempio: trovare i documenti più simili a un altro documento</span><span class="sxs-lookup"><span data-stu-id="2be65-113">Example: Find the Top Documents That Are Similar to Another Document</span></span>  
 <span data-ttu-id="2be65-114">Nell'esempio seguente vengono recuperati i primi 10 candidati simili al candidato specificato dalla *@CandidateID* tabella HumanResources. JobCandidate nel database di esempio AdventureWorks2012.</span><span class="sxs-lookup"><span data-stu-id="2be65-114">The following example retrieves the top 10 candidates who are similar to the candidate specified by *@CandidateID* from the HumanResources.JobCandidate table in the AdventureWorks2012 sample database.</span></span>  
  
```scr  
SELECT TOP(10) KEY_TBL.matched_document_key AS Candidate_ID  
FROM SEMANTICSIMILARITYTABLE  
    (  
    HumanResources.JobCandidate,  
    Resume,  
    @CandidateID  
    ) AS KEY_TBL  
ORDER BY KEY_TBL.score DESC;  
GO  
```  
  
##  <a name="finding-information-about-how-documents-are-similar-or-related"></a><a name="BasicsQuerySimilarity"></a><span data-ttu-id="2be65-115">Ricerca di informazioni sulla somiglianza o correlazione dei documenti</span><span class="sxs-lookup"><span data-stu-id="2be65-115">Finding Information about How Documents Are Similar or Related</span></span>  
  
###  <a name="how-to-find-information-about-how-documents-are-similar-or-related-with-semanticsimilaritydetailstable"></a><a name="HowToQuerySimilarity"></a><span data-ttu-id="2be65-116">Procedura: trovare informazioni sulla somiglianza o correlazione dei documenti con SEMANTICSIMILARITYDETAILSTABLE</span><span class="sxs-lookup"><span data-stu-id="2be65-116">How To: Find Information about How Documents Are Similar or Related with SEMANTICSIMILARITYDETAILSTABLE</span></span>  
 <span data-ttu-id="2be65-117">Per ottenere informazioni sulle frasi chiave che rendono simili o correlati alcuni documenti, è possibile eseguire una query sulla funzione [semanticsimilaritydetailstable &#40;Transact-SQL&#41;](/sql/relational-databases/system-functions/semanticsimilaritydetailstable-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="2be65-117">To get information about the key phrases that make documents similar or related, you can query the function [semanticsimilaritydetailstable &#40;Transact-SQL&#41;](/sql/relational-databases/system-functions/semanticsimilaritydetailstable-transact-sql).</span></span>  
  
 <span data-ttu-id="2be65-118">**SEMANTICSIMILARITYDETAILSTABLE** restituisce una tabella di zero, una o più righe di frasi chiave comuni in due documenti, ovvero un documento di origine e un documento corrispondente, il cui contenuto è semanticamente simile.</span><span class="sxs-lookup"><span data-stu-id="2be65-118">**SEMANTICSIMILARITYDETAILSTABLE** returns a table of zero, one, or more rows of key phrases common across two documents (a source document and a matched document) whose content is semantically similar.</span></span> <span data-ttu-id="2be65-119">A questa funzione del set di righe è possibile fare riferimento nella clausola FROM di un'istruzione SELECT come normale nome di tabella.</span><span class="sxs-lookup"><span data-stu-id="2be65-119">This rowset function can be referenced in the FROM clause of a SELECT statement like a regular table name.</span></span>  
  
 <span data-ttu-id="2be65-120">Per informazioni dettagliate sui parametri necessari per la funzione **SEMANTICSIMILARITYDETAILSTABLE** e sulla tabella dei risultati restituita, vedere [semanticsimilaritydetailstable &#40;Transact-SQL&#41;](/sql/relational-databases/system-functions/semanticsimilaritydetailstable-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="2be65-120">For detailed information about the parameters required by the **SEMANTICSIMILARITYDETAILSTABLE** function, and about the table of results that it returns, see [semanticsimilaritydetailstable &#40;Transact-SQL&#41;](/sql/relational-databases/system-functions/semanticsimilaritydetailstable-transact-sql).</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="2be65-121">Per le colonne di destinazione deve essere abilitata l'indicizzazione full-text e semantica.</span><span class="sxs-lookup"><span data-stu-id="2be65-121">The columns that you target must have full-text and semantic indexing enabled.</span></span>  
  
###  <a name="example-find-the-top-key-phrases-that-are-similar-between-documents"></a><a name="HowToSimilarPhrases"></a><span data-ttu-id="2be65-122">Esempio: trovare le principali frasi chiave simili tra i documenti</span><span class="sxs-lookup"><span data-stu-id="2be65-122">Example: Find the Top Key Phrases That Are Similar between Documents</span></span>  
 <span data-ttu-id="2be65-123">Nell'esempio seguente vengono recuperate le 5 frasi chiave associate al punteggio di somiglianza più elevato tra i candidati specificati nella tabella **HumanResources.JobCandidate** del database di esempio AdventureWorks2012.</span><span class="sxs-lookup"><span data-stu-id="2be65-123">The following example retrieves the 5 key phrases that have the highest similarity score between the specified candidates in **HumanResources.JobCandidate** table of the AdventureWorks2012 sample database.</span></span>  
  
```sql  
SELECT TOP(5) KEY_TBL.keyphrase, KEY_TBL.score  
FROM SEMANTICSIMILARITYDETAILSTABLE  
    (  
    HumanResources.JobCandidate,  
    Resume, @CandidateID,  
    Resume, @MatchedID  
    ) AS KEY_TBL  
ORDER BY KEY_TBL.score DESC;  
GO  
```  
  
  
