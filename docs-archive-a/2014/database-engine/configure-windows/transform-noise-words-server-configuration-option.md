---
title: Opzione di configurazione del server transform noise words | Microsoft Docs
ms.custom: ''
ms.date: 03/07/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
helpviewer_keywords:
- full-text queries [SQL Server], performance
- transform noise words option
- noise words [full-text search]
- full-text search [SQL Server], stopwords
- stopwords [full-text search]
ms.assetid: 69bd388e-a86c-4de4-b5d5-d093424d9c57
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 49de4a381de3e998073a73c284e3e3e5960f4921
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87723024"
---
# <a name="transform-noise-words-server-configuration-option"></a><span data-ttu-id="1d8f3-102">Opzione di configurazione del server transform noise words Server</span><span class="sxs-lookup"><span data-stu-id="1d8f3-102">transform noise words Server Configuration Option</span></span>
  <span data-ttu-id="1d8f3-103">Utilizzare l' `transform noise words` opzione di configurazione del server per non visualizzare un messaggio di errore se le parole non significative, ovvero [parole non significative](../../relational-databases/search/full-text-search.md), determinano la restituzione di zero righe da parte di un'operazione booleana su una query full-text.</span><span class="sxs-lookup"><span data-stu-id="1d8f3-103">Use the `transform noise words` server configuration option to suppress an error message if noise words, that is [stopwords](../../relational-databases/search/full-text-search.md), cause a Boolean operation on a full-text query to return zero rows.</span></span> <span data-ttu-id="1d8f3-104">Questa opzione è utile per le query full-text in cui viene utilizzato il predicato CONTAINS e con operazioni booleane o operazioni NEAR che includono parole non significative.</span><span class="sxs-lookup"><span data-stu-id="1d8f3-104">This option is useful for full-text queries that use the CONTAINS predicate in which Boolean operations or NEAR operations include noise words.</span></span> <span data-ttu-id="1d8f3-105">I valori possibili sono illustrati nella tabella seguente.</span><span class="sxs-lookup"><span data-stu-id="1d8f3-105">The possible values are described in the following table.</span></span>  
  
|<span data-ttu-id="1d8f3-106">valore</span><span class="sxs-lookup"><span data-stu-id="1d8f3-106">Value</span></span>|<span data-ttu-id="1d8f3-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="1d8f3-107">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="1d8f3-108">0</span><span class="sxs-lookup"><span data-stu-id="1d8f3-108">0</span></span>|<span data-ttu-id="1d8f3-109">Le parole non significative non vengono trasformate.</span><span class="sxs-lookup"><span data-stu-id="1d8f3-109">Noise words (or stopwords) are not transformed.</span></span> <span data-ttu-id="1d8f3-110">Quando una query full-text contiene parole non significative, la query restituisce zero righe e in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] viene generato un avviso.</span><span class="sxs-lookup"><span data-stu-id="1d8f3-110">When a full-text query contains noise words, the query returns zero rows, and [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] raises a warning.</span></span> <span data-ttu-id="1d8f3-111">Questo è il comportamento predefinito.</span><span class="sxs-lookup"><span data-stu-id="1d8f3-111">This is the default behavior.</span></span><br /><br /> <span data-ttu-id="1d8f3-112">Si noti che l'avviso è un avviso di run-time.</span><span class="sxs-lookup"><span data-stu-id="1d8f3-112">Note that the warning is a run-time warning.</span></span> <span data-ttu-id="1d8f3-113">Pertanto, se la clausola full-text nella query non viene eseguita, l'avviso non viene generato.</span><span class="sxs-lookup"><span data-stu-id="1d8f3-113">Therefore, if the full-text clause in the query is not executed, the warning is not raised.</span></span> <span data-ttu-id="1d8f3-114">Per una query locale, viene generato un solo avviso, anche se sono presenti più clausole di query full-text.</span><span class="sxs-lookup"><span data-stu-id="1d8f3-114">For a local query, only one warning is raised, even when there are multiple full-text query clauses.</span></span> <span data-ttu-id="1d8f3-115">Per una query remota, il server collegato potrebbe non inoltrare l'errore ed è pertanto possibile che l'avviso non venga generato.</span><span class="sxs-lookup"><span data-stu-id="1d8f3-115">For a remote query, the linked server might not relay the error; therefore, the warning might not be raised.</span></span>|  
|<span data-ttu-id="1d8f3-116">1</span><span class="sxs-lookup"><span data-stu-id="1d8f3-116">1</span></span>|<span data-ttu-id="1d8f3-117">Le parole non significative vengono trasformate.</span><span class="sxs-lookup"><span data-stu-id="1d8f3-117">Noise words (or stopwords) are transformed.</span></span> <span data-ttu-id="1d8f3-118">Tali parole vengono ignorate e viene valutato e il resto della query.</span><span class="sxs-lookup"><span data-stu-id="1d8f3-118">They are ignored, and the rest of the query is evaluated.</span></span><br /><br /> <span data-ttu-id="1d8f3-119">Se vengono specificate parole non significative in un termine di prossimità, queste vengono rimosse da [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="1d8f3-119">If noise words are specified in a proximity term, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] removes them.</span></span> <span data-ttu-id="1d8f3-120">La parola non significativa `is` viene ad esempio rimossa da `CONTAINS(<column_name>, 'NEAR (hello,is,goodbye)')`, trasformando la query di ricerca in `CONTAINS(<column_name>, 'NEAR(hello,goodbye)')`.</span><span class="sxs-lookup"><span data-stu-id="1d8f3-120">For example, the noise word `is` is removed from `CONTAINS(<column_name>, 'NEAR (hello,is,goodbye)')`, transforming the search query into `CONTAINS(<column_name>, 'NEAR(hello,goodbye)')`.</span></span> <span data-ttu-id="1d8f3-121">Si noti che la query `CONTAINS(<column_name>, 'NEAR(hello,is)')` verrebbe trasformata semplicemente in `CONTAINS(<column_name>, hello)` in quanto vi è un solo termine di ricerca valido.</span><span class="sxs-lookup"><span data-stu-id="1d8f3-121">Notice that `CONTAINS(<column_name>, 'NEAR(hello,is)')` would be transformed into simply `CONTAINS(<column_name>, hello)` because there is only one valid search term.</span></span>|  
  
## <a name="effects-of-the-transform-noise-words-setting"></a><span data-ttu-id="1d8f3-122">Effetti dell'impostazione transform noise words</span><span class="sxs-lookup"><span data-stu-id="1d8f3-122">Effects of the transform noise words Setting</span></span>  
 <span data-ttu-id="1d8f3-123">In questa sezione viene illustrato il comportamento di query che contengono una parola non significativa, "`the`", quando vengono utilizzate le impostazioni alternative di `transform noise words`.</span><span class="sxs-lookup"><span data-stu-id="1d8f3-123">This section illustrates the behavior of queries containing a noise word, "`the`", under the alternate settings of `transform noise words`.</span></span>  <span data-ttu-id="1d8f3-124">Si presuppone che le stringhe di query full-text di esempio vengano eseguite su una riga di tabella che contiene i dati seguenti: `[1, "The black cat"]`.</span><span class="sxs-lookup"><span data-stu-id="1d8f3-124">The sample full-text query strings are assumed to be run against a table row containing the following data: `[1, "The black cat"]`.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="1d8f3-125">In tutti gli scenari di questo tipo può venire generato un avviso di parola non significativa.</span><span class="sxs-lookup"><span data-stu-id="1d8f3-125">All such scenarios can generate a noise word warning.</span></span>  
  
-   <span data-ttu-id="1d8f3-126">Con transform noise words impostato su 0:</span><span class="sxs-lookup"><span data-stu-id="1d8f3-126">With transform noise words set to 0:</span></span>  
  
    |<span data-ttu-id="1d8f3-127">Stringa di query</span><span class="sxs-lookup"><span data-stu-id="1d8f3-127">Query string</span></span>|<span data-ttu-id="1d8f3-128">Risultato</span><span class="sxs-lookup"><span data-stu-id="1d8f3-128">Result</span></span>|  
    |------------------|------------|  
    |<span data-ttu-id="1d8f3-129">"`cat`" AND "`the`"</span><span class="sxs-lookup"><span data-stu-id="1d8f3-129">"`cat`" AND "`the`"</span></span>|<span data-ttu-id="1d8f3-130">Nessun risultato (il comportamento è lo stesso per "`the`" AND "`cat`").</span><span class="sxs-lookup"><span data-stu-id="1d8f3-130">No results (The behavior is the same for "`the`" AND "`cat`".)</span></span>|  
    |<span data-ttu-id="1d8f3-131">"`cat`" NEAR "`the`"</span><span class="sxs-lookup"><span data-stu-id="1d8f3-131">"`cat`" NEAR "`the`"</span></span>|<span data-ttu-id="1d8f3-132">Nessun risultato (il comportamento è lo stesso per "`the`" NEAR "`cat`").</span><span class="sxs-lookup"><span data-stu-id="1d8f3-132">No results (The behavior is the same for "`the`" NEAR "`cat`".)</span></span>|  
    |<span data-ttu-id="1d8f3-133">"`the`" AND NOT "`black`"</span><span class="sxs-lookup"><span data-stu-id="1d8f3-133">"`the`" AND NOT "`black`"</span></span>|<span data-ttu-id="1d8f3-134">Nessun risultato</span><span class="sxs-lookup"><span data-stu-id="1d8f3-134">No results</span></span>|  
    |<span data-ttu-id="1d8f3-135">"`black`" AND NOT "`the`"</span><span class="sxs-lookup"><span data-stu-id="1d8f3-135">"`black`" AND NOT "`the`"</span></span>|<span data-ttu-id="1d8f3-136">Nessun risultato</span><span class="sxs-lookup"><span data-stu-id="1d8f3-136">No results</span></span>|  
  
-   <span data-ttu-id="1d8f3-137">Con transform noise words impostato su 1:</span><span class="sxs-lookup"><span data-stu-id="1d8f3-137">With transform noise words set to 1:</span></span>  
  
    |<span data-ttu-id="1d8f3-138">Stringa di query</span><span class="sxs-lookup"><span data-stu-id="1d8f3-138">Query string</span></span>|<span data-ttu-id="1d8f3-139">Risultato</span><span class="sxs-lookup"><span data-stu-id="1d8f3-139">Result</span></span>|  
    |------------------|------------|  
    |<span data-ttu-id="1d8f3-140">"`cat`" AND "`the`"</span><span class="sxs-lookup"><span data-stu-id="1d8f3-140">"`cat`" AND "`the`"</span></span>|<span data-ttu-id="1d8f3-141">Riscontro per la riga con ID 1</span><span class="sxs-lookup"><span data-stu-id="1d8f3-141">Hit for row with ID 1</span></span>|  
    |<span data-ttu-id="1d8f3-142">"`cat`" NEAR "`the`"</span><span class="sxs-lookup"><span data-stu-id="1d8f3-142">"`cat`" NEAR "`the`"</span></span>|<span data-ttu-id="1d8f3-143">Riscontro per la riga con ID 1</span><span class="sxs-lookup"><span data-stu-id="1d8f3-143">Hit for row with ID 1</span></span>|  
    |<span data-ttu-id="1d8f3-144">"`the`" AND NOT "`black`"</span><span class="sxs-lookup"><span data-stu-id="1d8f3-144">"`the`" AND NOT "`black`"</span></span>|<span data-ttu-id="1d8f3-145">Nessun risultato</span><span class="sxs-lookup"><span data-stu-id="1d8f3-145">No results</span></span>|  
    |<span data-ttu-id="1d8f3-146">"`black`" AND NOT "`the`"</span><span class="sxs-lookup"><span data-stu-id="1d8f3-146">"`black`" AND NOT "`the`"</span></span>|<span data-ttu-id="1d8f3-147">Riscontro per la riga con ID 1</span><span class="sxs-lookup"><span data-stu-id="1d8f3-147">Hit for row with ID 1</span></span>|  
  
## <a name="example"></a><span data-ttu-id="1d8f3-148">Esempio</span><span class="sxs-lookup"><span data-stu-id="1d8f3-148">Example</span></span>  
 <span data-ttu-id="1d8f3-149">Nell'esempio seguente il valore di `transform noise words` viene impostato su `1`.</span><span class="sxs-lookup"><span data-stu-id="1d8f3-149">The following example sets `transform noise words` to `1`.</span></span>  
  
```  
sp_configure 'show advanced options', 1;  
RECONFIGURE;  
GO  
sp_configure 'transform noise words', 1;  
RECONFIGURE;  
GO  
```  
  
## <a name="see-also"></a><span data-ttu-id="1d8f3-150">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="1d8f3-150">See Also</span></span>  
 <span data-ttu-id="1d8f3-151">[Opzioni di configurazione del server &#40;SQL Server&#41;](server-configuration-options-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="1d8f3-151">[Server Configuration Options &#40;SQL Server&#41;](server-configuration-options-sql-server.md) </span></span>  
 [<span data-ttu-id="1d8f3-152">CONTAINS &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="1d8f3-152">CONTAINS &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/queries/contains-transact-sql)  
  
  
