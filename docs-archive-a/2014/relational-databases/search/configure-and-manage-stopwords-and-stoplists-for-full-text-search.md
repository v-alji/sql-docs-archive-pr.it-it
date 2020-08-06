---
title: Configurare e gestire parole non significative ed elenchi di parole non significative per la ricerca full-text | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: search
ms.topic: conceptual
helpviewer_keywords:
- stoplists [full-text search]
- full-text search [SQL Server], stoplists
- full-text search [SQL Server], noise words
- noise words [full-text search]
- full-text search [SQL Server], stopwords
- stopwords [full-text search]
ms.assetid: 43b5ce7b-9f09-4443-8a5b-c3da6eb28bcc
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 103b5024368c5ca239856580e9b45473aabf6a92
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87725428"
---
# <a name="configure-and-manage-stopwords-and-stoplists-for-full-text-search"></a><span data-ttu-id="ce9cd-102">Configurare e gestire parole non significative ed elenchi di parole non significative per la ricerca full-text</span><span class="sxs-lookup"><span data-stu-id="ce9cd-102">Configure and Manage Stopwords and Stoplists for Full-Text Search</span></span>
  <span data-ttu-id="ce9cd-103">Per garantire l'efficienza di un indice full-text, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] è dotato di un meccanismo che rimuove le stringhe più frequenti, inutili ai fini della ricerca.</span><span class="sxs-lookup"><span data-stu-id="ce9cd-103">To prevent a full-text index from becoming bloated, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] has a mechanism that discards commonly occurring strings that do not help the search.</span></span> <span data-ttu-id="ce9cd-104">Queste stringhe scartate vengono denominate *parole non significative*.</span><span class="sxs-lookup"><span data-stu-id="ce9cd-104">These discarded strings are called *stopwords*.</span></span> <span data-ttu-id="ce9cd-105">Durante la creazione dell'indice, il motore di ricerca full-text omette le parole non significative dall'indice full-text,</span><span class="sxs-lookup"><span data-stu-id="ce9cd-105">During index creation, the Full-Text Engine omits stopwords from the full-text index.</span></span> <span data-ttu-id="ce9cd-106">in modo che le query full-text non eseguano ricerche in tali parole.</span><span class="sxs-lookup"><span data-stu-id="ce9cd-106">This means that full-text queries will not search on stopwords.</span></span>  
  
##  <a name="understanding-stopwords-and-stoplists"></a><a name="understand"></a><span data-ttu-id="ce9cd-107">Informazioni su parole non significative e elenchi</span><span class="sxs-lookup"><span data-stu-id="ce9cd-107">Understanding Stopwords and Stoplists</span></span>  
 <span data-ttu-id="ce9cd-108">Una parola non significativa può essere una parola con un significato in un linguaggio specifico o può essere un *token* che non dispone di significato linguistico.</span><span class="sxs-lookup"><span data-stu-id="ce9cd-108">A stopword can be a word with meaning in a specific language, or it can be a *token* that does not have linguistic meaning.</span></span> <span data-ttu-id="ce9cd-109">Nella lingua italiana, ad esempio, parole quali "circa", "con", "devo" e "cui" vengono escluse dall'indice full-text poiché in pratica risultano inutili ai fini della ricerca.</span><span class="sxs-lookup"><span data-stu-id="ce9cd-109">For example, in the English language, words such as "a," "and," "is," and "the" are left out of the full-text index since they are known to be useless to a search.</span></span>  
  
 <span data-ttu-id="ce9cd-110">Anche se ignora l'inclusione di parole non significative, l'indice full-text ne prende in considerazione la posizione.</span><span class="sxs-lookup"><span data-stu-id="ce9cd-110">Although it ignores the inclusion of stopwords, the full-text index does take into account their position.</span></span> <span data-ttu-id="ce9cd-111">Si consideri ad esempio la frase "Istruzioni non valide per questi modelli Adventure Works Cycles".</span><span class="sxs-lookup"><span data-stu-id="ce9cd-111">For example, consider the phrase, "Instructions are applicable to these Adventure Works Cycles models".</span></span> <span data-ttu-id="ce9cd-112">Nella tabella seguente viene illustrata la posizione delle parole nella frase:</span><span class="sxs-lookup"><span data-stu-id="ce9cd-112">The following table depicts the position of the words in the phrase:</span></span>  
  
|<span data-ttu-id="ce9cd-113">Word</span><span class="sxs-lookup"><span data-stu-id="ce9cd-113">Word</span></span>|<span data-ttu-id="ce9cd-114">Posizione</span><span class="sxs-lookup"><span data-stu-id="ce9cd-114">Position</span></span>|  
|----------|--------------|  
|<span data-ttu-id="ce9cd-115">Istruzioni</span><span class="sxs-lookup"><span data-stu-id="ce9cd-115">Instructions</span></span>|<span data-ttu-id="ce9cd-116">1</span><span class="sxs-lookup"><span data-stu-id="ce9cd-116">1</span></span>|  
|<span data-ttu-id="ce9cd-117">non</span><span class="sxs-lookup"><span data-stu-id="ce9cd-117">are</span></span>|<span data-ttu-id="ce9cd-118">2</span><span class="sxs-lookup"><span data-stu-id="ce9cd-118">2</span></span>|  
|<span data-ttu-id="ce9cd-119">valide</span><span class="sxs-lookup"><span data-stu-id="ce9cd-119">applicable</span></span>|<span data-ttu-id="ce9cd-120">3</span><span class="sxs-lookup"><span data-stu-id="ce9cd-120">3</span></span>|  
|<span data-ttu-id="ce9cd-121">in</span><span class="sxs-lookup"><span data-stu-id="ce9cd-121">to</span></span>|<span data-ttu-id="ce9cd-122">4</span><span class="sxs-lookup"><span data-stu-id="ce9cd-122">4</span></span>|  
|<span data-ttu-id="ce9cd-123">questi</span><span class="sxs-lookup"><span data-stu-id="ce9cd-123">these</span></span>|<span data-ttu-id="ce9cd-124">5</span><span class="sxs-lookup"><span data-stu-id="ce9cd-124">5</span></span>|  
|<span data-ttu-id="ce9cd-125">modelli</span><span class="sxs-lookup"><span data-stu-id="ce9cd-125">Adventure</span></span>|<span data-ttu-id="ce9cd-126">6</span><span class="sxs-lookup"><span data-stu-id="ce9cd-126">6</span></span>|  
|<span data-ttu-id="ce9cd-127">Adventure</span><span class="sxs-lookup"><span data-stu-id="ce9cd-127">Works</span></span>|<span data-ttu-id="ce9cd-128">7</span><span class="sxs-lookup"><span data-stu-id="ce9cd-128">7</span></span>|  
|<span data-ttu-id="ce9cd-129">Cicli</span><span class="sxs-lookup"><span data-stu-id="ce9cd-129">Cycles</span></span>|<span data-ttu-id="ce9cd-130">8</span><span class="sxs-lookup"><span data-stu-id="ce9cd-130">8</span></span>|  
|<span data-ttu-id="ce9cd-131">modelli</span><span class="sxs-lookup"><span data-stu-id="ce9cd-131">models</span></span>|<span data-ttu-id="ce9cd-132">9</span><span class="sxs-lookup"><span data-stu-id="ce9cd-132">9</span></span>|  
  
 <span data-ttu-id="ce9cd-133">Le parole non significative "sono", "in" e "questi" nelle posizioni 2, 4 e 5 vengono escluse dall'indice full-text.</span><span class="sxs-lookup"><span data-stu-id="ce9cd-133">The stopwords "are", "to", and "these" that are in positions 2, 4, and 5 are left out of the full-text index.</span></span> <span data-ttu-id="ce9cd-134">Le relative informazioni di posizione vengono comunque mantenute, lasciando invariata la posizione delle altre parole nella frase.</span><span class="sxs-lookup"><span data-stu-id="ce9cd-134">However, their positional information is maintained, thereby leaving the position of the other words in the phrase unaffected.</span></span>  
  
 <span data-ttu-id="ce9cd-135">Le parole non significative vengono gestite nei database utilizzando oggetti denominati elenchi di parole non significative.</span><span class="sxs-lookup"><span data-stu-id="ce9cd-135">Stopwords are managed in databases using objects called stoplists.</span></span> <span data-ttu-id="ce9cd-136">Un *elenco di parole non significative* è un elenco che, quando associato a un indice full-text, viene applicato alle query full-text su tale indice.</span><span class="sxs-lookup"><span data-stu-id="ce9cd-136">A *stoplist* is a list of stopwords that, when associated with a full-text index, is applied to full-text queries on that index.</span></span>  
  
  
##  <a name="creating-a-stoplist"></a><a name="creating"></a><span data-ttu-id="ce9cd-137">Creazione di un oggetto di parole non significative</span><span class="sxs-lookup"><span data-stu-id="ce9cd-137">Creating a Stoplist</span></span>  
 <span data-ttu-id="ce9cd-138">È possibile creare un elenco di parole non significative in uno dei modi seguenti:</span><span class="sxs-lookup"><span data-stu-id="ce9cd-138">You can create a stoplist in any of the following ways:</span></span>  
  
-   <span data-ttu-id="ce9cd-139">Utilizzando l'elenco di parole non significative fornito dal sistema nel database.</span><span class="sxs-lookup"><span data-stu-id="ce9cd-139">Using the system-supplied stoplist in the database.</span></span> <span data-ttu-id="ce9cd-140">L'elenco di parole non significative di sistema incluso in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] contiene le parole non significative più comuni per ogni lingua supportata, ovvero per ogni lingua associata a word breaker specifici per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="ce9cd-140">[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] ships with a system stoplist that contains the most commonly used stopwords for each supported language, that is for every language that is associated with given word breakers by default.</span></span> <span data-ttu-id="ce9cd-141">L'elenco di parole non significative contiene le parole non significative comuni per tutte le lingue supportate.</span><span class="sxs-lookup"><span data-stu-id="ce9cd-141">The system stoplist contains common stopwords for all supported languages.</span></span>  <span data-ttu-id="ce9cd-142">È possibile copiare l'elenco di parole non significative di sistema e personalizzarne una copia aggiungendone e rimuovendone alcune.</span><span class="sxs-lookup"><span data-stu-id="ce9cd-142">You can copy the system stoplist, and customize your copy by adding and removing stopwords.</span></span>  
  
     <span data-ttu-id="ce9cd-143">L'elenco di parole non significative di sistema è installato nel database [Resource](../databases/resource-database.md) .</span><span class="sxs-lookup"><span data-stu-id="ce9cd-143">The system stoplist is installed in the [Resource](../databases/resource-database.md) database.</span></span>  
  
-   <span data-ttu-id="ce9cd-144">Creando un elenco di parole non significative personalizzato, quindi aggiungendovi altre parole non significative per ogni lingua specificata.</span><span class="sxs-lookup"><span data-stu-id="ce9cd-144">Creating your own stoplist, and then adding stopwords to it for any language that you specify.</span></span> <span data-ttu-id="ce9cd-145">Se necessario, è inoltre possibile eliminare parole non significative dall'elenco.</span><span class="sxs-lookup"><span data-stu-id="ce9cd-145">You can also drop stopwords from your stoplist when necessary.</span></span>  
  
-   <span data-ttu-id="ce9cd-146">Utilizzando un elenco di parole non significative personalizzato esistente da qualsiasi altro database nell'instanza del server corrente e successivamente aggiungendo ed eliminando le parole non significative in base alle specifiche esigenze.</span><span class="sxs-lookup"><span data-stu-id="ce9cd-146">Using an existing custom stoplist from any other database in the current server instance and then adding and dropping stopwords as necessary.</span></span>  
  
 <span data-ttu-id="ce9cd-147">**Per creare un elenco di parole non significative**</span><span class="sxs-lookup"><span data-stu-id="ce9cd-147">**To create a stoplist**</span></span>  
  
-   [<span data-ttu-id="ce9cd-148">CREATE FULLTEXT STOPLIST &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="ce9cd-148">CREATE FULLTEXT STOPLIST &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/create-fulltext-stoplist-transact-sql)  
  
#### <a name="to-create-a-full-text-stoplist-in-management-studio"></a><span data-ttu-id="ce9cd-149">Per creare un elenco di parole non significative full-text in Management Studio</span><span class="sxs-lookup"><span data-stu-id="ce9cd-149">To create a full-text stoplist in Management Studio</span></span>  
  
1.  <span data-ttu-id="ce9cd-150">In Esplora oggetti espandere il server.</span><span class="sxs-lookup"><span data-stu-id="ce9cd-150">In Object Explorer, expand the server.</span></span>  
  
2.  <span data-ttu-id="ce9cd-151">Espandere **Database**, quindi espandere il database in cui si vuole creare l'elenco di parole non significative full-text.</span><span class="sxs-lookup"><span data-stu-id="ce9cd-151">Expand **Databases**, and then expand the database in which you want to create the full-text stoplist.</span></span>  
  
3.  <span data-ttu-id="ce9cd-152">Espandere **Archivio**, quindi fare clic con il pulsante destro del mouse su **Elenchi di parole non significative full-text**.</span><span class="sxs-lookup"><span data-stu-id="ce9cd-152">Expand **Storage**, and then right-click **Full-Text Stoplists**.</span></span>  
  
4.  <span data-ttu-id="ce9cd-153">Selezionare **Nuovo elenco di parole non significative full-text**.</span><span class="sxs-lookup"><span data-stu-id="ce9cd-153">Select **New Full-Text Stoplist**.</span></span>  
  
5.  <span data-ttu-id="ce9cd-154">Specificare il nome dell'elenco di parole non significative.</span><span class="sxs-lookup"><span data-stu-id="ce9cd-154">Specify the stoplist name.</span></span>  
  
6.  <span data-ttu-id="ce9cd-155">Facoltativamente, specificare un altro utente come proprietario dell'elenco di parole non significative.</span><span class="sxs-lookup"><span data-stu-id="ce9cd-155">Optionally, specify someone else as the stoplist owner.</span></span>  
  
7.  <span data-ttu-id="ce9cd-156">Selezionare una delle opzioni di creazione di un elenco di parole non significative seguenti:</span><span class="sxs-lookup"><span data-stu-id="ce9cd-156">Select one of the following create stoplist options:</span></span>  
  
    -   <span data-ttu-id="ce9cd-157">**Creare un elenco di parole non significative vuoto**</span><span class="sxs-lookup"><span data-stu-id="ce9cd-157">**Create an empty stoplist**</span></span>  
  
    -   <span data-ttu-id="ce9cd-158">**Creare un elenco di parole non significative da un elenco di parole non significative di sistema**</span><span class="sxs-lookup"><span data-stu-id="ce9cd-158">**Create from the system stoplist**</span></span>  
  
    -   <span data-ttu-id="ce9cd-159">**Creare un elenco di parole non significative da un elenco di parole non significative full-text esistente**</span><span class="sxs-lookup"><span data-stu-id="ce9cd-159">**Create from an existing full-text stoplist**</span></span>  
  
     <span data-ttu-id="ce9cd-160">Per altre informazioni, vedere [Nuovo elenco di parole non significative full-text &#40;pagina Generale&#41;](../../integration-services/general-page-of-integration-services-designers-options.md).</span><span class="sxs-lookup"><span data-stu-id="ce9cd-160">For more information, see [New Full-Text Stoplist &#40;General Page&#41;](../../integration-services/general-page-of-integration-services-designers-options.md).</span></span>  
  
8.  [!INCLUDE[clickOK](../../../includes/clickok-md.md)]  
  
 <span data-ttu-id="ce9cd-161">**Per eliminare un elenco di parole non significative**</span><span class="sxs-lookup"><span data-stu-id="ce9cd-161">**To drop a stoplist**</span></span>  
  
-   [<span data-ttu-id="ce9cd-162">DROP FULLTEXT STOPLIST &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="ce9cd-162">DROP FULLTEXT STOPLIST &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/drop-fulltext-stoplist-transact-sql)  
  
  
##  <a name="using-a-stoplist-in-full-text-queries"></a><a name="queries"></a><span data-ttu-id="ce9cd-163">Utilizzo di un oggetto di parole non significative nelle query full-text</span><span class="sxs-lookup"><span data-stu-id="ce9cd-163">Using a Stoplist in Full-Text Queries</span></span>  
 <span data-ttu-id="ce9cd-164">Per utilizzare un elenco di parole non significative nelle query, è necessario associarlo a un indice full-text.</span><span class="sxs-lookup"><span data-stu-id="ce9cd-164">To make use of a stoplist in queries, you must associate it with a full-text index.</span></span> <span data-ttu-id="ce9cd-165">È possibile associare un elenco di parole non significative a un indice full-text quando si crea l'indice oppure è possibile modificare l'indice in seguito per aggiungere un elenco.</span><span class="sxs-lookup"><span data-stu-id="ce9cd-165">You can attach a stoplist to a full-text index when you create the index, or you can alter the index later to add a stoplist.</span></span>  
  
 <span data-ttu-id="ce9cd-166">**Per creare un indice full-text e associare un elenco di parole non significative**</span><span class="sxs-lookup"><span data-stu-id="ce9cd-166">**To create a full-text index and associate a stoplist with it**</span></span>  
  
-   [<span data-ttu-id="ce9cd-167">CREATE FULLTEXT INDEX &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="ce9cd-167">CREATE FULLTEXT INDEX &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/create-fulltext-index-transact-sql)  
  
 <span data-ttu-id="ce9cd-168">**Per associare o annullare l'associazione di un elenco di parole non significative a un indice full-text esistente**</span><span class="sxs-lookup"><span data-stu-id="ce9cd-168">**To associate or disassociate a stoplist with an existing full-text index**</span></span>  
  
-   [<span data-ttu-id="ce9cd-169">ALTER FULLTEXT INDEX &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="ce9cd-169">ALTER FULLTEXT INDEX &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/alter-fulltext-index-transact-sql)  
  
 <span data-ttu-id="ce9cd-170">**Per eliminare un messaggio di errore visualizzato nel caso in cui le parole non significative impediscono l'esecuzione di un'operazione booleana in una query full-text**</span><span class="sxs-lookup"><span data-stu-id="ce9cd-170">**To suppress an error message if stopwords cause a Boolean operation on a full-text query to fail**</span></span>  
  
-   [<span data-ttu-id="ce9cd-171">Opzione di configurazione del server transform noise words Server</span><span class="sxs-lookup"><span data-stu-id="ce9cd-171">transform noise words Server Configuration Option</span></span>](../../database-engine/configure-windows/transform-noise-words-server-configuration-option.md)  
  
  
##  <a name="viewing-stoplists-and-stoplist-metadata"></a><a name="viewing"></a><span data-ttu-id="ce9cd-172">Visualizzazione dei metadati di elenchi e di parole non significative</span><span class="sxs-lookup"><span data-stu-id="ce9cd-172">Viewing Stoplists and Stoplist Metadata</span></span>  
 <span data-ttu-id="ce9cd-173">**Per visualizzare tutte le parole non significative di un elenco**</span><span class="sxs-lookup"><span data-stu-id="ce9cd-173">**To view all the stopwords of a stoplist**</span></span>  
  
-   [<span data-ttu-id="ce9cd-174">sys.fulltext_stopwords &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="ce9cd-174">sys.fulltext_stopwords &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-catalog-views/sys-fulltext-stopwords-transact-sql)  
  
 <span data-ttu-id="ce9cd-175">**Per ottenere informazioni su tutti gli elenchi di parole non significative nel database corrente**</span><span class="sxs-lookup"><span data-stu-id="ce9cd-175">**To get information about all the stoplists in the current database**</span></span>  
  
-   [<span data-ttu-id="ce9cd-176">sys.fulltext_stoplists &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="ce9cd-176">sys.fulltext_stoplists &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-catalog-views/sys-fulltext-stoplists-transact-sql)  
  
-   [<span data-ttu-id="ce9cd-177">sys.fulltext_stopwords &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="ce9cd-177">sys.fulltext_stopwords &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-catalog-views/sys-fulltext-stopwords-transact-sql)  
  
 <span data-ttu-id="ce9cd-178">**Per visualizzare il risultato della suddivisione in token di una combinazione di word breaker, thesaurus ed elenchi di parole non significative**</span><span class="sxs-lookup"><span data-stu-id="ce9cd-178">**To view the tokenization result of a word breaker, thesaurus, and stoplist combination**</span></span>  
  
-   [<span data-ttu-id="ce9cd-179">sys. dm_fts_parser &#40;&#41;Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="ce9cd-179">sys.dm_fts_parser &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-dynamic-management-views/sys-dm-fts-parser-transact-sql)  
  
  
##  <a name="changing-the-stopwords-in-a-stoplist"></a><a name="change"></a><span data-ttu-id="ce9cd-180">Modifica di parole non significative in un oggetto di parole non significative</span><span class="sxs-lookup"><span data-stu-id="ce9cd-180">Changing the Stopwords in a Stoplist</span></span>  
 <span data-ttu-id="ce9cd-181">**Per aggiungere o eliminare parole non significative in un elenco**</span><span class="sxs-lookup"><span data-stu-id="ce9cd-181">**To add or drop stopwords from a stoplist**</span></span>  
  
-   [<span data-ttu-id="ce9cd-182">ALTER FULLTEXT STOPLIST &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="ce9cd-182">ALTER FULLTEXT STOPLIST &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/alter-fulltext-stoplist-transact-sql)  
  
#### <a name="to-change-the-stopwords-in-a-stoplist-in-management-studio"></a><span data-ttu-id="ce9cd-183">Per modificare le parole non significative in un elenco di parole non significative in Management Studio</span><span class="sxs-lookup"><span data-stu-id="ce9cd-183">To change the stopwords in a stoplist in Management Studio</span></span>  
  
1.  <span data-ttu-id="ce9cd-184">In Esplora oggetti espandere il server.</span><span class="sxs-lookup"><span data-stu-id="ce9cd-184">In Object Explorer, expand the server.</span></span>  
  
2.  <span data-ttu-id="ce9cd-185">Espandere **Database**, quindi espandere il database.</span><span class="sxs-lookup"><span data-stu-id="ce9cd-185">Expand **Databases**, and then expand the database.</span></span>  
  
3.  <span data-ttu-id="ce9cd-186">Espandere **Archiviazione**, quindi selezionare **Elenco di parole non significative full-text**.</span><span class="sxs-lookup"><span data-stu-id="ce9cd-186">Expand **Storage**, and then select **Full Text Stoplists**.</span></span>  
  
4.  <span data-ttu-id="ce9cd-187">Fare clic con il pulsante destro del mouse sull'elenco di parole non significative che si vuole modificare, quindi scegliere **Proprietà**.</span><span class="sxs-lookup"><span data-stu-id="ce9cd-187">Right-click the stoplist whose properties you want to change, and select **Properties**.</span></span>  
  
5.  <span data-ttu-id="ce9cd-188">Nella finestra di dialogo [Proprietà elenco di parole non significative full-text](../../database-engine/full-text-stoplist-properties.md) :</span><span class="sxs-lookup"><span data-stu-id="ce9cd-188">In the [Full-Text Stoplist Properties](../../database-engine/full-text-stoplist-properties.md) dialog box:</span></span>  
  
    1.  <span data-ttu-id="ce9cd-189">Nella casella di riepilogo **Azione** selezionare una delle azioni seguenti: **Aggiungi parola non significativa**, **Elimina parola non significativa**, **Elimina tutte le parole non significative**o **Cancella elenco di parole non significative**.</span><span class="sxs-lookup"><span data-stu-id="ce9cd-189">In the **Action** list box, select one of the following actions: **Add stopword**, **Delete stopword**, **Delete all stopwords**, or **Clear stoplist**.</span></span>  
  
    2.  <span data-ttu-id="ce9cd-190">Se la casella di testo **Parola non significativa** è abilitata per l'azione selezionata, immettere una singola parola non significativa.</span><span class="sxs-lookup"><span data-stu-id="ce9cd-190">If the **Stopword** text box is enabled for the selected action, enter a single stopword.</span></span> <span data-ttu-id="ce9cd-191">Questa parola deve essere univoca, ovvero non ancora inclusa nell'elenco di parole non significative per la lingua selezionata.</span><span class="sxs-lookup"><span data-stu-id="ce9cd-191">This stopword must be unique; that is, not yet in this stoplist for the language that you select.</span></span>  
  
    3.  <span data-ttu-id="ce9cd-192">Se la casella di riepilogo **Full-text language** è abilitata per l'azione selezionata, selezionare una lingua.</span><span class="sxs-lookup"><span data-stu-id="ce9cd-192">If the **Full-text language** list box is enabled for the selected action, select a language.</span></span>  
  
6.  [!INCLUDE[clickOK](../../../includes/clickok-md.md)]  
  
  
##  <a name="upgrading-noise-words-from-sql-server-2005"></a><a name="upgrade"></a><span data-ttu-id="ce9cd-193">Aggiornamento delle parole non significative da SQL Server 2005</span><span class="sxs-lookup"><span data-stu-id="ce9cd-193">Upgrading Noise Words from SQL Server 2005</span></span>  
 [!INCLUDE[ssVersion2005](../../../includes/ssversion2005-md.md)] <span data-ttu-id="ce9cd-194">Le parole non significative di  sono state sostituite.</span><span class="sxs-lookup"><span data-stu-id="ce9cd-194">noise words have been replaced by stopwords.</span></span> <span data-ttu-id="ce9cd-195">Quando si aggiorna un database da [!INCLUDE[ssVersion2005](../../../includes/ssversion2005-md.md)], i file delle parole non significative non vengono più utilizzati.</span><span class="sxs-lookup"><span data-stu-id="ce9cd-195">When a database is upgraded from [!INCLUDE[ssVersion2005](../../../includes/ssversion2005-md.md)], the noise-word files are no longer used.</span></span> <span data-ttu-id="ce9cd-196">Tali file vengono tuttavia archiviati nella cartella FTDATA\ FTNoiseThesaurusBak e possono essere utilizzati in seguito durante l'aggiornamento o la compilazione di elenchi di parole non significative corrispondenti.</span><span class="sxs-lookup"><span data-stu-id="ce9cd-196">However, the noise-word files are stored in the FTDATA\ FTNoiseThesaurusBak folder, and you can use them later when updating or building the corresponding stoplists.</span></span> <span data-ttu-id="ce9cd-197">Per informazioni sull'aggiornamento dei file delle parole non significative agli elenchi corrispondenti, vedere [Aggiornamento della ricerca full-text](upgrade-full-text-search.md).</span><span class="sxs-lookup"><span data-stu-id="ce9cd-197">For information about upgrading noise-word files to stoplists, see [Upgrade Full-Text Search](upgrade-full-text-search.md).</span></span>  
  
  
  
