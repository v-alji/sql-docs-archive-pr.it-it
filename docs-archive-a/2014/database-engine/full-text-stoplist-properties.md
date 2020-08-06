---
title: Proprietà di parole non significative full-text | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: search
ms.topic: conceptual
f1_keywords:
- sql12.swb.fulltextsearch.ftstoplistproperties.general.f1
- sql12.swb.fulltextsearch.ftstoplistproperties.schedule.f1
ms.assetid: 2e907f5b-0cf9-484a-afcf-a4e7f1e2f87f
author: rothja
ms.author: jroth
ms.openlocfilehash: 4ff27a1258d5164e3e93d34b6ff757993d6f6363
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87638043"
---
# <a name="full-text-stoplist-properties"></a><span data-ttu-id="0603f-102">Proprietà elenco di parole non significative full-text</span><span class="sxs-lookup"><span data-stu-id="0603f-102">Full-Text Stoplist Properties</span></span>
  <span data-ttu-id="0603f-103">Utilizzare questa finestra di dialogo per aggiungere o eliminare singole parole non significative, eliminare tutte le parole non significative per una lingua specifica oppure cancellare l'elenco di parole non significative corrente.</span><span class="sxs-lookup"><span data-stu-id="0603f-103">Use this dialog box to add or delete individual stopwords, delete all stopwords for a specific language, or clear the current stoplist.</span></span> <span data-ttu-id="0603f-104">Una parola non significativa è una parola di uso comune inclusa in un elenco di parole non significative.</span><span class="sxs-lookup"><span data-stu-id="0603f-104">A stopword is a commonly used word that is included in a stoplist.</span></span> <span data-ttu-id="0603f-105">Le parole contenute in un elenco di questo tipo vengono omesse dall'indicizzazione full-text nelle tabelle che utilizzano l'elenco stesso.</span><span class="sxs-lookup"><span data-stu-id="0603f-105">The stopwords in a stoplist are omitted from full-text indexing for tables that use the stoplist.</span></span> <span data-ttu-id="0603f-106">Per altre informazioni, vedere [Configurare e gestire parole non significative ed elenchi di parole non significative per la ricerca full-text](../relational-databases/search/full-text-search.md).</span><span class="sxs-lookup"><span data-stu-id="0603f-106">For more information, see [Configure and Manage Stopwords and Stoplists for Full-Text Search](../relational-databases/search/full-text-search.md).</span></span>  
  
 <span data-ttu-id="0603f-107">**Per utilizzare SQL Server Management Studio per modificare le proprietà dell'elenco di parole non significative**</span><span class="sxs-lookup"><span data-stu-id="0603f-107">**To use SQL Server Management Studio to change stoplist properties**</span></span>  
  
-   [<span data-ttu-id="0603f-108">Configurare e gestire parole non significative ed elenchi di parole non significative per la ricerca full-text</span><span class="sxs-lookup"><span data-stu-id="0603f-108">Configure and Manage Stopwords and Stoplists for Full-Text Search</span></span>](../relational-databases/search/full-text-search.md)  
  
## <a name="options"></a><span data-ttu-id="0603f-109">Opzioni</span><span class="sxs-lookup"><span data-stu-id="0603f-109">Options</span></span>  
 <span data-ttu-id="0603f-110">**Azione**</span><span class="sxs-lookup"><span data-stu-id="0603f-110">**Action**</span></span>  
 <span data-ttu-id="0603f-111">Consente di specificare l'azione che si desidera eseguire.</span><span class="sxs-lookup"><span data-stu-id="0603f-111">Specifies the action that you want to perform.</span></span>  
  
 <span data-ttu-id="0603f-112">**Aggiungi parola non significativa**</span><span class="sxs-lookup"><span data-stu-id="0603f-112">**Add stopword**</span></span>  
 <span data-ttu-id="0603f-113">Consente di aggiungere una parola di uso comune all'elenco di parole non significative.</span><span class="sxs-lookup"><span data-stu-id="0603f-113">Add a commonly used word to the stoplist.</span></span>  
  
 <span data-ttu-id="0603f-114">**Elimina parola non significativa**</span><span class="sxs-lookup"><span data-stu-id="0603f-114">**Delete stopword**</span></span>  
 <span data-ttu-id="0603f-115">Consente di eliminare una parola non significativa dall'elenco.</span><span class="sxs-lookup"><span data-stu-id="0603f-115">Delete a stopword from the stoplist.</span></span>  
  
 <span data-ttu-id="0603f-116">**Elimina tutte le parole non significative**</span><span class="sxs-lookup"><span data-stu-id="0603f-116">**Delete all stopwords**</span></span>  
 <span data-ttu-id="0603f-117">Consente di eliminare tutte le parole non significative per una lingua specifica.</span><span class="sxs-lookup"><span data-stu-id="0603f-117">Delete all the stopwords for a specific language.</span></span>  
  
 <span data-ttu-id="0603f-118">**Cancella elenco di parole non significative**</span><span class="sxs-lookup"><span data-stu-id="0603f-118">**Clear stoplist**</span></span>  
 <span data-ttu-id="0603f-119">Consente di cancellare l'elenco di parole non significative eliminando tutte le parole non significative per tutte le lingue.</span><span class="sxs-lookup"><span data-stu-id="0603f-119">Clear the stoplist by deleting all the stopwords for all languages.</span></span>  
  
 <span data-ttu-id="0603f-120">**Parola non significativa**</span><span class="sxs-lookup"><span data-stu-id="0603f-120">**Stopword**</span></span>  
 <span data-ttu-id="0603f-121">Se è stata selezionata l'opzione **Aggiungi parola non significativa** o **Elimina parola non significativa**, immettere parola non significativa nel campo **parola non significativa** .</span><span class="sxs-lookup"><span data-stu-id="0603f-121">If you selected **Add stopword** or **Delete stopword**, enter the stopword in the **Stopword** field.</span></span> <span data-ttu-id="0603f-122">Una nuova parola non significativa deve essere univoca, ovvero non ancora inclusa nell'elenco di parole non significative per la lingua selezionata.</span><span class="sxs-lookup"><span data-stu-id="0603f-122">A new stopword must be unique; that is, not yet in this stoplist for the language that you select.</span></span>  
  
 <span data-ttu-id="0603f-123">**Lingua full-text**</span><span class="sxs-lookup"><span data-stu-id="0603f-123">**Full-text language**</span></span>  
 <span data-ttu-id="0603f-124">Se è stata selezionata l'opzione **Aggiungi parola non significativa**, **Elimina parola non significativa**o **Elimina tutti i parole non significative**, selezionare la lingua di parola non significativa o parole non significative nella casella di riepilogo.</span><span class="sxs-lookup"><span data-stu-id="0603f-124">If you selected **Add stopword**, **Delete stopword**, or **Delete all stopwords**, select the language of the stopword or stopwords from the list box.</span></span> <span data-ttu-id="0603f-125">Nella casella sono elencate tutte le lingue full-text supportate dall'istanza del server.</span><span class="sxs-lookup"><span data-stu-id="0603f-125">This lists all the full-text languages that are supported by the server instance.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0603f-126">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="0603f-126">See Also</span></span>  
 <span data-ttu-id="0603f-127">[sys. fulltext_stopwords &#40;&#41;Transact-SQL](/sql/relational-databases/system-catalog-views/sys-fulltext-stopwords-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="0603f-127">[sys.fulltext_stopwords &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-fulltext-stopwords-transact-sql) </span></span>  
 <span data-ttu-id="0603f-128">[sys. fulltext_stoplists &#40;&#41;Transact-SQL](/sql/relational-databases/system-catalog-views/sys-fulltext-stoplists-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="0603f-128">[sys.fulltext_stoplists &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-fulltext-stoplists-transact-sql) </span></span>  
 <span data-ttu-id="0603f-129">[Configurare e gestire parole non significative e elenchi per la ricerca full-text](../relational-databases/search/full-text-search.md) </span><span class="sxs-lookup"><span data-stu-id="0603f-129">[Configure and Manage Stopwords and Stoplists for Full-Text Search](../relational-databases/search/full-text-search.md) </span></span>  
 <span data-ttu-id="0603f-130">[ALTER FULLTEXT &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-fulltext-stoplist-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="0603f-130">[ALTER FULLTEXT STOPLIST &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-fulltext-stoplist-transact-sql) </span></span>  
 <span data-ttu-id="0603f-131">[CREAZIONE di un &#40;di parole non significative full-text&#41;Transact-SQL](/sql/t-sql/statements/create-fulltext-stoplist-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="0603f-131">[CREATE FULLTEXT STOPLIST &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-fulltext-stoplist-transact-sql) </span></span>  
 [<span data-ttu-id="0603f-132">DROP FULLTEXT STOPLIST &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="0603f-132">DROP FULLTEXT STOPLIST &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/drop-fulltext-stoplist-transact-sql)  
  
  
