---
title: Trovare frasi chiave nei documenti tramite la ricerca semantica | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: search
ms.topic: conceptual
helpviewer_keywords:
- semantic search [SQL Server], key phrase queries
ms.assetid: 6ee3676e-ed5d-43ec-aeca-1eed78967111
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 8388fb704bf13f44d025e6e32a1450d537f61832
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87714131"
---
# <a name="find-key-phrases-in-documents-with-semantic-search"></a><span data-ttu-id="48e8c-102">Trovare frasi chiave nei documenti mediante ricerca semantica</span><span class="sxs-lookup"><span data-stu-id="48e8c-102">Find Key Phrases in Documents with Semantic Search</span></span>
  <span data-ttu-id="48e8c-103">Viene descritto come individuare le frasi chiave nei documenti o nelle colonne di testo configurati per l'indicizzazione semantica statistica.</span><span class="sxs-lookup"><span data-stu-id="48e8c-103">Describes how to find the key phrases in documents or text columns that are configured for statistical semantic indexing.</span></span>  
  
##  <a name="finding-key-phrases-in-documents"></a><a name="BasicsQueryKey"></a><span data-ttu-id="48e8c-104">Ricerca di frasi chiave nei documenti</span><span class="sxs-lookup"><span data-stu-id="48e8c-104">Finding Key Phrases in Documents</span></span>  
  
###  <a name="how-to-find-the-key-phrases-in-documents-with-semantickeyphrasetable"></a><a name="howtofind"></a><span data-ttu-id="48e8c-105">Procedura: trovare le frasi chiave nei documenti con SEMANTICKEYPHRASETABLE</span><span class="sxs-lookup"><span data-stu-id="48e8c-105">How to: Find the Key Phrases in Documents with SEMANTICKEYPHRASETABLE</span></span>  
 <span data-ttu-id="48e8c-106">Per identificare le frasi chiave in documenti specifici o identificare documenti che contengono frasi chiave specifiche, eseguire una query sulla funzione [semantickeyphrasetable &#40;Transact-SQL&#41;](/sql/relational-databases/system-functions/semantickeyphrasetable-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="48e8c-106">To identify the key phrases in specific documents, or to identify documents that contain specific key phrases, query the function [semantickeyphrasetable &#40;Transact-SQL&#41;](/sql/relational-databases/system-functions/semantickeyphrasetable-transact-sql).</span></span>  
  
 <span data-ttu-id="48e8c-107">SEMANTICKEYPHRASETABLE restituisce una tabella con zero, una o più righe per le frasi chiave associate alle colonne nella tabella specificata.</span><span class="sxs-lookup"><span data-stu-id="48e8c-107">SEMANTICKEYPHRASETABLE returns a table with zero, one, or more rows for those key phrases associated with columns in the specified table.</span></span> <span data-ttu-id="48e8c-108">A questa funzione per i set di righe è possibile fare riferimento nella clausola FROM di un'istruzione SELECT come se fosse un normale nome di tabella.</span><span class="sxs-lookup"><span data-stu-id="48e8c-108">This rowset function can be referenced in the FROM clause of a SELECT statement as if it were a regular table name.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="48e8c-109">In [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)]solo singole parole vengono indicizzate per la ricerca semantica; le frasi composte da più parole (ngrams) non vengono indicizzate.</span><span class="sxs-lookup"><span data-stu-id="48e8c-109">In [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)], only single words are indexed for semantic search; multi-word phrases (ngrams) are not indexed.</span></span> <span data-ttu-id="48e8c-110">Inoltre, varie forme della stessa parola vengono indicizzate separatamente; ad esempio "calcolo" e "calcoli" vengono indicizzati separatamente.</span><span class="sxs-lookup"><span data-stu-id="48e8c-110">Also, various forms of the same word are indexed separately; for example, "computer" and "computers" are indexed separately.</span></span>  
  
 <span data-ttu-id="48e8c-111">Per informazioni dettagliate sui parametri necessari per la funzione SEMANTICKEYPHRASETABLE e sulla tabella dei risultati restituita, vedere [semantickeyphrasetable &#40;Transact-SQL&#41;](/sql/relational-databases/system-functions/semantickeyphrasetable-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="48e8c-111">For detailed information about the parameters required by the SEMANTICKEYPHRASETABLE function, and about the table of results that it returns, see [semantickeyphrasetable &#40;Transact-SQL&#41;](/sql/relational-databases/system-functions/semantickeyphrasetable-transact-sql).</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="48e8c-112">Per le colonne di destinazione deve essere abilitata l'indicizzazione full-text e semantica.</span><span class="sxs-lookup"><span data-stu-id="48e8c-112">The columns that you target must have full-text and semantic indexing enabled.</span></span>  
  
###  <a name="example-1-find-the-top-key-phrases-in-a-specific-document"></a><a name="HowToTopPhrases"></a><span data-ttu-id="48e8c-113">Esempio 1: trovare le principali frasi chiave in un documento specifico</span><span class="sxs-lookup"><span data-stu-id="48e8c-113">Example 1: Find the Top Key Phrases in a Specific Document</span></span>  
 <span data-ttu-id="48e8c-114">L'esempio seguente recupera le prime 10 frasi chiave dal documento specificato tramite la variabile @DocumentId nella colonna Document della tabella Production.Document del database di esempio AdventureWorks.</span><span class="sxs-lookup"><span data-stu-id="48e8c-114">The following example retrieves the top 10 key phrases from the document specified by the @DocumentId variable in the Document column of the Production.Document table of the AdventureWorks sample database.</span></span> <span data-ttu-id="48e8c-115">La variabile @DocumentId rappresenta un valore della colonna chiave dell'indice full-text.</span><span class="sxs-lookup"><span data-stu-id="48e8c-115">The @DocumentId variable represents a value from the key column of the full-text index.</span></span>  
  
```sql  
SELECT TOP(10) KEYP_TBL.keyphrase  
FROM SEMANTICKEYPHRASETABLE  
    (  
    Production.Document,  
    Document,  
    @DocumentId  
    ) AS KEYP_TBL  
ORDER BY KEYP_TBL.score DESC;  
GO  
```  
  
 <span data-ttu-id="48e8c-116">La funzione **SEMANTICKEYPHRASETABLE** recupera in modo efficiente questi risultati tramite una ricerca nell'indice anziché un'analisi della tabella.</span><span class="sxs-lookup"><span data-stu-id="48e8c-116">The **SEMANTICKEYPHRASETABLE** function retrieves these results efficiently by using an index seek instead of a table scan.</span></span>  
  
###  <a name="example-2-find-the-top-documents-that-contain-a-specific-key-phrase"></a><a name="HowToTopDocuments"></a><span data-ttu-id="48e8c-117">Esempio 2: trovare i documenti principali che contengono una frase chiave specifica</span><span class="sxs-lookup"><span data-stu-id="48e8c-117">Example 2: Find the Top Documents that Contain a Specific Key Phrase</span></span>  
 <span data-ttu-id="48e8c-118">Nell'esempio seguente vengono recuperati i primi 25 documenti che contengono la frase chiave "Bracket" dalla colonna Documento della tabella Production.Document del database di esempio AdventureWorks.</span><span class="sxs-lookup"><span data-stu-id="48e8c-118">The following example retrieves the top 25 documents that contain the key phrase "Bracket" from the Document column of the Production.Document table of the AdventureWorks sample database.</span></span>  
  
```sql  
SELECT TOP (25) DOC_TBL.DocumentID, DOC_TBL.DocumentSummary  
FROM Production.Document AS DOC_TBL  
    INNER JOIN SEMANTICKEYPHRASETABLE  
    (  
    Production.Document,  
    Document  
    ) AS KEYP_TBL  
ON DOC_TBL.DocumentID = KEYP_TBL.document_key  
WHERE KEYP_TBL.keyphrase = 'Bracket'  
ORDER BY KEYP_TBL.Score DESC;  
GO  
```  
  
  
