---
title: Risolvere i problemi nell'indicizzazione full-text | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: search
ms.topic: conceptual
helpviewer_keywords:
- indexes [full-text search]
- troubleshooting [SQL Server], full-text search
- troubleshooting [full-text search]
ms.assetid: 964c43a8-5019-4179-82aa-63cd0ef592ef
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: eaca5fcf2dfbac57fc6d3ba6178251927d15aba9
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87637725"
---
# <a name="troubleshoot-full-text-indexing"></a><span data-ttu-id="c404e-102">Risoluzione dei problemi nell'indicizzazione full-text</span><span class="sxs-lookup"><span data-stu-id="c404e-102">Troubleshoot Full-Text Indexing</span></span>
     
##  <a name="troubleshoot-full-text-indexing-failures"></a><a name="failure"></a> <span data-ttu-id="c404e-103">Risoluzione degli errori nell'indicizzazione full-text</span><span class="sxs-lookup"><span data-stu-id="c404e-103">Troubleshoot Full-Text Indexing Failures</span></span>  
 <span data-ttu-id="c404e-104">Durante il popolamento o la gestione di un indice full-text, l'indicizzatore full-text potrebbe non eseguire correttamente l'indicizzazione di una o più righe per i motivi descritti di seguito.</span><span class="sxs-lookup"><span data-stu-id="c404e-104">While populating or maintaining a full-text index, the full-text indexer, for reasons described below, might fail to index one or more rows.</span></span> <span data-ttu-id="c404e-105">Questi errori a livello di riga non impediscono il completamento del popolamento.</span><span class="sxs-lookup"><span data-stu-id="c404e-105">These row-level errors do not prevent the population from completing.</span></span> <span data-ttu-id="c404e-106">L'indicizzatore ignora queste righe, pertanto non sarà possibile recuperare il contenuto di tali righe tramite query.</span><span class="sxs-lookup"><span data-stu-id="c404e-106">The indexer skips these rows, which means that you are not able to query for content contained in these rows.</span></span>  
  
 <span data-ttu-id="c404e-107">È possibile che si verifichino errori di indicizzazione nelle situazioni seguenti.</span><span class="sxs-lookup"><span data-stu-id="c404e-107">Indexing failures can occur when:</span></span>  
  
-   <span data-ttu-id="c404e-108">Quando l'indicizzatore non è in grado di trovare o caricare un componente filtro o word breaker.</span><span class="sxs-lookup"><span data-stu-id="c404e-108">The indexer cannot find or load a filter or word breaker component.</span></span> <span data-ttu-id="c404e-109">Questo errore può verificarsi se la riga della tabella include contenuto o un formato di documento in una lingua non registrata con l'istanza di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c404e-109">This failure can occur if the table row contains a document format or content in a language that has not been registered with the instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="c404e-110">oppure se il componente filtro o word breaker registrato non è stato firmato o non ha superato il controllo della firma durante il caricamento.</span><span class="sxs-lookup"><span data-stu-id="c404e-110">This failure can also happen if the registered word breaker or filter component was not signed or failed signature verification when it was being loaded.</span></span>  
  
-   <span data-ttu-id="c404e-111">Quando un componente, ad esempio un word breaker o un filtro, restituisce un errore all'indicizzatore.</span><span class="sxs-lookup"><span data-stu-id="c404e-111">A component, such as a word breaker or filter, fails and returns an error to the indexer.</span></span> <span data-ttu-id="c404e-112">Questa situazione può verificarsi se il documento indicizzato è danneggiato e il filtro non è in grado di estrarre il testo del documento</span><span class="sxs-lookup"><span data-stu-id="c404e-112">This can happen if the document being indexed is corrupt and the filter is unable to extract text from the document.</span></span> <span data-ttu-id="c404e-113">oppure quando un componente non è in grado di gestire il contenuto di una singola riga oltre una determinata dimensione, a causa di limiti di memoria nell'host del daemon di filtri (fdhost.exe).</span><span class="sxs-lookup"><span data-stu-id="c404e-113">This can also occur when a component is unable to handle the content of a single row above a certain size, due to memory limits on the full-text filter daemon host (fdhost.exe).</span></span>  
  
 <span data-ttu-id="c404e-114">Per ogni errore a livello di riga, nel log di tipo ricerca per indicizzazione vengono inserite informazioni sul motivo dell'errore.</span><span class="sxs-lookup"><span data-stu-id="c404e-114">For each row-level failure, the crawl log contains details on the reason for the failure.</span></span> <span data-ttu-id="c404e-115">Il numero di errori è riepilogato al termine di un popolamento completo o incrementale.</span><span class="sxs-lookup"><span data-stu-id="c404e-115">The error counts are summarized at the end of a full or incremental population.</span></span>  
  
 <span data-ttu-id="c404e-116">Esistono altri errori che possono influire sul processo di indicizzazione e impedire il completamento del popolamento.</span><span class="sxs-lookup"><span data-stu-id="c404e-116">There are other failures that can impact the indexing process itself and prevent the population from completing:</span></span>  
  
-   <span data-ttu-id="c404e-117">L'indice full-text supera il limite del numero di righe che è possibile inserire in un catalogo full-text.</span><span class="sxs-lookup"><span data-stu-id="c404e-117">The full-text index exceeds the limit for the number of rows that can be contained in a full-text catalog.</span></span>  
  
-   <span data-ttu-id="c404e-118">Un indice cluster o un indice di chiave full-text della tabella indicizzata viene danneggiato, eliminato o ricompilato.</span><span class="sxs-lookup"><span data-stu-id="c404e-118">A clustered index or full-text key index on the table being indexed gets altered, dropped, or rebuilt.</span></span>  
  
-   <span data-ttu-id="c404e-119">Un errore hardware o del disco provoca il danneggiamento del catalogo full-text.</span><span class="sxs-lookup"><span data-stu-id="c404e-119">A hardware failure or disk corruption results in the corruption of the full-text catalog.</span></span>  
  
-   <span data-ttu-id="c404e-120">Un gruppo di file contenente la tabella indicizzata full-text passa alla modalità offline o viene impostato in sola lettura.</span><span class="sxs-lookup"><span data-stu-id="c404e-120">A file group that contains the table being full-text indexed goes offline, or is made read-only.</span></span>  
  
 <span data-ttu-id="c404e-121">È consigliabile visualizzare il log di tipo ricerca per indicizzazione al termine di tutte le operazioni di popolamento dell'indice full-text significative o quando il popolamento non risulta completato.</span><span class="sxs-lookup"><span data-stu-id="c404e-121">You should view the crawl log at the end of any significant full-text index population operation, or when you find that a population did not complete.</span></span>  
  
### <a name="unsigned-components"></a><span data-ttu-id="c404e-122">Componenti non firmati</span><span class="sxs-lookup"><span data-stu-id="c404e-122">Unsigned Components</span></span>  
 <span data-ttu-id="c404e-123">Per impostazione predefinita, l'indicizzatore full-text richiede la firma dei filtri e dei word breaker caricati.</span><span class="sxs-lookup"><span data-stu-id="c404e-123">By default, the full-text indexer requires the filters and word breakers that it loads to be signed.</span></span> <span data-ttu-id="c404e-124">Se tali componenti non sono firmati, ad esempio in alcuni casi di installazione di componenti personalizzati, è necessario configurare l'indicizzatore full-text in modo che ignori il controllo della firma.</span><span class="sxs-lookup"><span data-stu-id="c404e-124">If they are not signed, which is the case sometimes when custom components are installed, you must configure the full-text indexer to ignore signature verification.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="c404e-125">Questa impostazione rende tuttavia l'istanza di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] meno sicura.</span><span class="sxs-lookup"><span data-stu-id="c404e-125">Ignoring signature verification makes the instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] less secure.</span></span> <span data-ttu-id="c404e-126">È consigliabile firmare tutti i componenti implementati o assicurarsi che tutti i componenti acquistati siano firmati.</span><span class="sxs-lookup"><span data-stu-id="c404e-126">We recommend that you sign any components that you implement or ensure that any components that you acquire are signed.</span></span> <span data-ttu-id="c404e-127">Per informazioni sulle firme dei componenti, vedere [sp_fulltext_service &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-fulltext-service-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="c404e-127">For information about signing components, see [sp_fulltext_service &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-fulltext-service-transact-sql).</span></span>  
  

  
##  <a name="full-text-index-in-inconsistent-state-after-transaction-log-restored"></a><a name="state"></a> <span data-ttu-id="c404e-128">Stato incoerente di un indice full-text dopo il ripristino del log delle transazioni</span><span class="sxs-lookup"><span data-stu-id="c404e-128">Full-Text Index in Inconsistent State after Transaction Log Restored</span></span>  
 <span data-ttu-id="c404e-129">Durante il ripristino del log delle transazioni di un database, è possibile che venga visualizzato un avviso che indica che lo stato dell'indice full-text non è coerente.</span><span class="sxs-lookup"><span data-stu-id="c404e-129">When restoring the transaction log of a database, you might see a warning indicating that the full-text index is not in a consistent state.</span></span> <span data-ttu-id="c404e-130">Questo accade perché l'indice full-text di una tabella è stato modificato dopo il backup del database.</span><span class="sxs-lookup"><span data-stu-id="c404e-130">The reason for this is that the full-text index on a table was modified after the database was backed up.</span></span> <span data-ttu-id="c404e-131">Per riportare l'indice full-text a uno stato coerente, è necessario eseguire un popolamento completo (ricerca per indicizzazione) della tabella.</span><span class="sxs-lookup"><span data-stu-id="c404e-131">To bring the full-text index to a consistent state, you must run a full population (crawl) on the table.</span></span> <span data-ttu-id="c404e-132">Per altre informazioni sugli indici full-text, vedere [Popolamento degli indici full-text](../indexes/indexes.md).</span><span class="sxs-lookup"><span data-stu-id="c404e-132">For more information, see [Populate Full-Text Indexes](../indexes/indexes.md).</span></span>  
  

  
## <a name="see-also"></a><span data-ttu-id="c404e-133">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c404e-133">See Also</span></span>  
 <span data-ttu-id="c404e-134">[ALTER FULLTEXT CATALOG &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-fulltext-catalog-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="c404e-134">[ALTER FULLTEXT CATALOG &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-fulltext-catalog-transact-sql) </span></span>  
 [<span data-ttu-id="c404e-135">Popolamento degli indici full-text</span><span class="sxs-lookup"><span data-stu-id="c404e-135">Populate Full-Text Indexes</span></span>](../indexes/indexes.md)  
  
  
