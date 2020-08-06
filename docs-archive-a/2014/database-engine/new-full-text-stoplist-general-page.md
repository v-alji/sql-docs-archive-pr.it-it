---
title: Nuovo punto di interruzione full-text (pagina generale) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: search
ms.topic: conceptual
f1_keywords:
- sql12.swb.fulltextsearch.ftstoplist.general.f1
ms.assetid: 97f8e82d-82ab-4525-91c9-1ee3ae217309
author: rothja
ms.author: jroth
ms.openlocfilehash: a6272fb570b85989f38c8187e29712966862710d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87636878"
---
# <a name="new-full-text-stoplist-general-page"></a><span data-ttu-id="905a0-102">Nuovo elenco di parole non significative full-text (pagina Generale)</span><span class="sxs-lookup"><span data-stu-id="905a0-102">New Full-Text Stoplist (General Page)</span></span>
  <span data-ttu-id="905a0-103">Utilizzare questa finestra di dialogo per creare un elenco di parole non significative full-text.</span><span class="sxs-lookup"><span data-stu-id="905a0-103">Use this dialog box to create a full-text stoplist.</span></span> <span data-ttu-id="905a0-104">Un *elenco di parole non significative* è un set di parole di uso comune, denominate *parole non significative*, omesse dall'indicizzazione full-text per tabelle che utilizzano l'elenco di parole non significative.</span><span class="sxs-lookup"><span data-stu-id="905a0-104">A *stoplist* is a set of commonly used words, called *stopwords*, that are omitted from full-text indexing for tables that use the stoplist.</span></span> <span data-ttu-id="905a0-105">Per altre informazioni, vedere [Configurare e gestire parole non significative ed elenchi di parole non significative per la ricerca full-text](../relational-databases/search/full-text-search.md).</span><span class="sxs-lookup"><span data-stu-id="905a0-105">For more information, see [Configure and Manage Stopwords and Stoplists for Full-Text Search](../relational-databases/search/full-text-search.md).</span></span>  
  
 <span data-ttu-id="905a0-106">**Per utilizzare SQL Server Management Studio per la creazione di un elenco di parole non significative**</span><span class="sxs-lookup"><span data-stu-id="905a0-106">**To use SQL Server Management Studio to create a stoplist**</span></span>  
  
-   [<span data-ttu-id="905a0-107">Configurare e gestire parole non significative ed elenchi di parole non significative per la ricerca full-text</span><span class="sxs-lookup"><span data-stu-id="905a0-107">Configure and Manage Stopwords and Stoplists for Full-Text Search</span></span>](../relational-databases/search/full-text-search.md)  
  
## <a name="options"></a><span data-ttu-id="905a0-108">Opzioni</span><span class="sxs-lookup"><span data-stu-id="905a0-108">Options</span></span>  
 <span data-ttu-id="905a0-109">**Nome elenco di parole non significative full-text**</span><span class="sxs-lookup"><span data-stu-id="905a0-109">**Full-text stoplist name**</span></span>  
 <span data-ttu-id="905a0-110">Consente di immettere il nome dell'elenco di parole non significative full-text.</span><span class="sxs-lookup"><span data-stu-id="905a0-110">Enter the name of the full-text stoplist.</span></span>  
  
 <span data-ttu-id="905a0-111">**Proprietario**</span><span class="sxs-lookup"><span data-stu-id="905a0-111">**Owner**</span></span>  
 <span data-ttu-id="905a0-112">Consente di specificare il proprietario dell'elenco di parole non significative full-text.</span><span class="sxs-lookup"><span data-stu-id="905a0-112">Specify the owner of the full-text stoplist.</span></span> <span data-ttu-id="905a0-113">Se si desidera impostare se stessi, ovvero l'utente corrente, come proprietario, lasciare vuoto questo campo.</span><span class="sxs-lookup"><span data-stu-id="905a0-113">If you want ownership to be assigned to yourself, that is, to the current user, leave this field empty.</span></span>  
  
 <span data-ttu-id="905a0-114">Per specificare un utente diverso, fare clic sul pulsante Sfoglia.</span><span class="sxs-lookup"><span data-stu-id="905a0-114">To specify a different user, click the browse button.</span></span>  
  
### <a name="create-stoplist-options"></a><span data-ttu-id="905a0-115">Opzioni di creazione di elenchi di parole non significative</span><span class="sxs-lookup"><span data-stu-id="905a0-115">Create stoplist options</span></span>  
 <span data-ttu-id="905a0-116">Fare clic su una delle opzioni di creazione seguenti:</span><span class="sxs-lookup"><span data-stu-id="905a0-116">Click one of the following create options:</span></span>  
  
 <span data-ttu-id="905a0-117">**Creare un elenco di parole non significative vuoto**</span><span class="sxs-lookup"><span data-stu-id="905a0-117">**Create an empty stoplist**</span></span>  
 <span data-ttu-id="905a0-118">Il nuovo elenco di parole non significative non conterrà alcuna parola non significativa.</span><span class="sxs-lookup"><span data-stu-id="905a0-118">The new stoplist will not contain any stopwords.</span></span>  
  
 <span data-ttu-id="905a0-119">**Creare un elenco di parole non significative da un elenco di parole non significative di sistema**</span><span class="sxs-lookup"><span data-stu-id="905a0-119">**Create from the system stoplist**</span></span>  
 <span data-ttu-id="905a0-120">Il nuovo elenco di parole non significative viene creato dall'elenco di parole non significative esistente per impostazione predefinita nel [Database Resource](../relational-databases/databases/resource-database.md).</span><span class="sxs-lookup"><span data-stu-id="905a0-120">The new stoplist is created from the stoplist that exists by default in the [Resource database](../relational-databases/databases/resource-database.md).</span></span>  
  
 <span data-ttu-id="905a0-121">**Creare un elenco di parole non significative da un elenco di parole non significative full-text esistente**</span><span class="sxs-lookup"><span data-stu-id="905a0-121">**Create from an existing full-text stoplist**</span></span>  
 <span data-ttu-id="905a0-122">Il nuovo elenco di parole non significative viene creato copiando un elenco di parole non significative esistente.</span><span class="sxs-lookup"><span data-stu-id="905a0-122">The new stoplist is created by copying an existing stoplist.</span></span>  
  
 <span data-ttu-id="905a0-123">**Database di origine**</span><span class="sxs-lookup"><span data-stu-id="905a0-123">**Source database**</span></span>  
 <span data-ttu-id="905a0-124">Specifica il nome del database a cui appartiene l'elenco di parole non significative esistente.</span><span class="sxs-lookup"><span data-stu-id="905a0-124">Specifies the name of the database to which the existing stoplist belongs.</span></span> <span data-ttu-id="905a0-125">Per impostazione predefinita, è selezionato il database corrente.</span><span class="sxs-lookup"><span data-stu-id="905a0-125">The current database is selected by default.</span></span> <span data-ttu-id="905a0-126">Se si desidera, selezionare un database diverso nella casella di riepilogo.</span><span class="sxs-lookup"><span data-stu-id="905a0-126">Optionally, select a different database from the list box.</span></span>  
  
 <span data-ttu-id="905a0-127">**Elenco di parole non significative di origine**</span><span class="sxs-lookup"><span data-stu-id="905a0-127">**Source stoplist**</span></span>  
 <span data-ttu-id="905a0-128">Specifica il nome di un elenco di parole non significative esistente.</span><span class="sxs-lookup"><span data-stu-id="905a0-128">Specifies the name of an existing stoplist.</span></span> <span data-ttu-id="905a0-129">Nell'elenco di elenchi di parole non significative disponibili selezionare quello da utilizzare come origine.</span><span class="sxs-lookup"><span data-stu-id="905a0-129">From the list of available stoplists, select the one to use as the source.</span></span> <span data-ttu-id="905a0-130">Gli elenchi di parole non significative disponibili sono elencati nell'ordine in cui vengono visualizzati in Esplora oggetti.</span><span class="sxs-lookup"><span data-stu-id="905a0-130">The available stoplists are listed in the order in which they appear in Object Explorer.</span></span>  
  
 <span data-ttu-id="905a0-131">Se qualsiasi lingua specificata nelle parole non significative dell'elenco di parole non significative di origine non è registrata nel database corrente, CREATE FULLTEXT STOPLIST ha esito positivo, ma vengono restituiti avvisi e le parole non significative corrispondenti non vengono aggiunte.</span><span class="sxs-lookup"><span data-stu-id="905a0-131">If any languages specified in the stop words of the source stoplist are not registered in the current database, CREATE FULLTEXT STOPLIST succeeds, but warning(s) are returned and the corresponding stop words are not added.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="905a0-132">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="905a0-132">See Also</span></span>  
 <span data-ttu-id="905a0-133">[ALTER FULLTEXT &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-fulltext-stoplist-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="905a0-133">[ALTER FULLTEXT STOPLIST &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-fulltext-stoplist-transact-sql) </span></span>  
 <span data-ttu-id="905a0-134">[CREAZIONE di un &#40;di parole non significative full-text&#41;Transact-SQL](/sql/t-sql/statements/create-fulltext-stoplist-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="905a0-134">[CREATE FULLTEXT STOPLIST &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-fulltext-stoplist-transact-sql) </span></span>  
 <span data-ttu-id="905a0-135">[DROP FULLTEXT elenco di parole non significative &#40;Transact-SQL&#41;](/sql/t-sql/statements/drop-fulltext-stoplist-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="905a0-135">[DROP FULLTEXT STOPLIST &#40;Transact-SQL&#41;](/sql/t-sql/statements/drop-fulltext-stoplist-transact-sql) </span></span>  
 <span data-ttu-id="905a0-136">[Configurare e gestire parole non significative e elenchi per la ricerca full-text](../relational-databases/search/full-text-search.md) </span><span class="sxs-lookup"><span data-stu-id="905a0-136">[Configure and Manage Stopwords and Stoplists for Full-Text Search](../relational-databases/search/full-text-search.md) </span></span>  
 [<span data-ttu-id="905a0-137">sys.fulltext_stoplists &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="905a0-137">sys.fulltext_stoplists &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-catalog-views/sys-fulltext-stoplists-transact-sql)  
  
  
