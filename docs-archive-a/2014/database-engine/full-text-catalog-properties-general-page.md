---
title: Proprietà catalogo full-text (pagina generale) | Microsoft Docs
ms.custom: ''
ms.date: 03/08/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: search
ms.topic: conceptual
f1_keywords:
- sql12.swb.fulltextsearch.ftcatalogproperties.general.f1
ms.assetid: d1f66762-2d40-4f24-b635-a417d22ee79a
author: rothja
ms.author: jroth
ms.openlocfilehash: 483601c53db6c8a806ea8c53f771fd4f2608293b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87724096"
---
# <a name="full-text-catalog-properties-general-page"></a><span data-ttu-id="b1041-102">Proprietà catalogo full-text (pagina Generale)</span><span class="sxs-lookup"><span data-stu-id="b1041-102">Full-Text Catalog Properties (General Page)</span></span>
  <span data-ttu-id="b1041-103">In questa sezione vengono illustrate le opzioni e le funzioni disponibili nella pagina **generale** della finestra di dialogo **Proprietà catalogo full-text** .</span><span class="sxs-lookup"><span data-stu-id="b1041-103">This section shows the options and functions available on the **General** page of the **Full-Text Catalog Properties** dialog box.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="b1041-104">Per i database di [!INCLUDE[ssCurrent](../includes/sscurrent-md.md)], un catalogo full-text è un concetto logico che fa riferimento a un gruppo di indici full-text.</span><span class="sxs-lookup"><span data-stu-id="b1041-104">For [!INCLUDE[ssCurrent](../includes/sscurrent-md.md)] databases, a full-text catalog is a logical concept that refers to a group of full-text indexes.</span></span> <span data-ttu-id="b1041-105">Il catalogo full-text è un oggetto virtuale che non appartiene ad alcun filegroup.</span><span class="sxs-lookup"><span data-stu-id="b1041-105">The full-text catalog is a virtual object that does not belong to any filegroup.</span></span>  
  
## <a name="options"></a><span data-ttu-id="b1041-106">Opzioni</span><span class="sxs-lookup"><span data-stu-id="b1041-106">Options</span></span>  
  
### <a name="properties"></a><span data-ttu-id="b1041-107">Proprietà</span><span class="sxs-lookup"><span data-stu-id="b1041-107">Properties</span></span>  
 <span data-ttu-id="b1041-108">**Catalogo predefinito**</span><span class="sxs-lookup"><span data-stu-id="b1041-108">**Default Catalog**</span></span>  
 <span data-ttu-id="b1041-109">Indica se il catalogo è quello predefinito per il database.</span><span class="sxs-lookup"><span data-stu-id="b1041-109">Displays whether the catalog is the default catalog for the database.</span></span>  
  
 <span data-ttu-id="b1041-110">**Stato popolamento**</span><span class="sxs-lookup"><span data-stu-id="b1041-110">**Population Status**</span></span>  
 <span data-ttu-id="b1041-111">Indica lo stato del catalogo.</span><span class="sxs-lookup"><span data-stu-id="b1041-111">Indicates the status of the catalog.</span></span> <span data-ttu-id="b1041-112">I valori possibili sono:</span><span class="sxs-lookup"><span data-stu-id="b1041-112">Possible values are:</span></span>  
  
-   <span data-ttu-id="b1041-113">**Idle**</span><span class="sxs-lookup"><span data-stu-id="b1041-113">**Idle**</span></span>  
  
-   <span data-ttu-id="b1041-114">**Ricerca per indicizzazione in corso**</span><span class="sxs-lookup"><span data-stu-id="b1041-114">**Crawl in Progress**</span></span>  
  
-   <span data-ttu-id="b1041-115">**Sospeso**</span><span class="sxs-lookup"><span data-stu-id="b1041-115">**Paused**</span></span>  
  
-   <span data-ttu-id="b1041-116">**Sospensione causata dal servizio Microsoft FullText**</span><span class="sxs-lookup"><span data-stu-id="b1041-116">**Throttled**</span></span>  
  
-   <span data-ttu-id="b1041-117">**Ripristino**</span><span class="sxs-lookup"><span data-stu-id="b1041-117">**Recovering**</span></span>  
  
-   <span data-ttu-id="b1041-118">**Arresto**</span><span class="sxs-lookup"><span data-stu-id="b1041-118">**Shutdown**</span></span>  
  
-   <span data-ttu-id="b1041-119">**Popolamento incrementale del catalogo in corso**</span><span class="sxs-lookup"><span data-stu-id="b1041-119">**Incremental population in progress**</span></span>  
  
-   <span data-ttu-id="b1041-120">**Compilazione dell'indice in corso**</span><span class="sxs-lookup"><span data-stu-id="b1041-120">**Building index**</span></span>  
  
-   <span data-ttu-id="b1041-121">**Il disco è completamente sospeso**</span><span class="sxs-lookup"><span data-stu-id="b1041-121">**Disk is full-Paused**</span></span>  
  
-   <span data-ttu-id="b1041-122">**Change tracking**</span><span class="sxs-lookup"><span data-stu-id="b1041-122">**Change tracking**</span></span>  
  
 <span data-ttu-id="b1041-123">**Item Count**</span><span class="sxs-lookup"><span data-stu-id="b1041-123">**Item Count**</span></span>  
 <span data-ttu-id="b1041-124">Consente di visualizzare il numero di elementi full-text presenti nel catalogo.</span><span class="sxs-lookup"><span data-stu-id="b1041-124">Displays the number of full-text items in the catalog.</span></span>  
  
 <span data-ttu-id="b1041-125">**Dimensioni catalogo**</span><span class="sxs-lookup"><span data-stu-id="b1041-125">**Catalog Size**</span></span>  
 <span data-ttu-id="b1041-126">Consente di visualizzare le dimensioni in megabyte del catalogo full-text.</span><span class="sxs-lookup"><span data-stu-id="b1041-126">Displays the size, in megabytes, of the full-text catalog.</span></span>  
  
 <span data-ttu-id="b1041-127">**Nome**</span><span class="sxs-lookup"><span data-stu-id="b1041-127">**Name**</span></span>  
 <span data-ttu-id="b1041-128">Nome del catalogo full-text.</span><span class="sxs-lookup"><span data-stu-id="b1041-128">The name of the full-text catalog.</span></span>  
  
 <span data-ttu-id="b1041-129">**Distinzione tra caratteri accentati**</span><span class="sxs-lookup"><span data-stu-id="b1041-129">**Accent Sensitive**</span></span>  
 <span data-ttu-id="b1041-130">Consente di visualizzare o modificare se il catalogo è sensibile ai segni diacritici, ad esempio una tilde ( **~** ), un contrassegno acuto acuto (**́**) o una diereszione (**̈**).</span><span class="sxs-lookup"><span data-stu-id="b1041-130">View or modify whether the catalog is sensitive to diacritical marks, such as a tilde (**~**), acute accent mark (**´**), or umlaut (**¨**).</span></span> <span data-ttu-id="b1041-131">I valori validi sono:</span><span class="sxs-lookup"><span data-stu-id="b1041-131">Valid values are:</span></span>  
  
-   <span data-ttu-id="b1041-132">**No**</span><span class="sxs-lookup"><span data-stu-id="b1041-132">**No**</span></span>  
  
-   <span data-ttu-id="b1041-133">**Sì**</span><span class="sxs-lookup"><span data-stu-id="b1041-133">**Yes**</span></span>  
  
-   <span data-ttu-id="b1041-134">Per informazioni sui segni diacritici, vedere [segni diacritici](https://www.merriam-webster.com/dictionary/diacritic) nel dizionario Merriam-Webster.</span><span class="sxs-lookup"><span data-stu-id="b1041-134">For information about diacritical marks, see [Diacritic](https://www.merriam-webster.com/dictionary/diacritic) in the Merriam-Webster dictionary.</span></span>  
  
 <span data-ttu-id="b1041-135">**Data ultimo popolamento**</span><span class="sxs-lookup"><span data-stu-id="b1041-135">**Last Population Date**</span></span>  
 <span data-ttu-id="b1041-136">Consente di visualizzare la data dell'ultimo popolamento del catalogo.</span><span class="sxs-lookup"><span data-stu-id="b1041-136">Displays the date the catalog was last populated.</span></span>  
  
 <span data-ttu-id="b1041-137">**Proprietario**</span><span class="sxs-lookup"><span data-stu-id="b1041-137">**Owner**</span></span>  
 <span data-ttu-id="b1041-138">Proprietario del catalogo full-text.</span><span class="sxs-lookup"><span data-stu-id="b1041-138">The owner of the full-text catalog.</span></span>  
  
 <span data-ttu-id="b1041-139">**Conteggio chiavi univoche**</span><span class="sxs-lookup"><span data-stu-id="b1041-139">**Unique Key Count**</span></span>  
 <span data-ttu-id="b1041-140">Numero di parole univoche che costituiscono l'indice full-text del catalogo.</span><span class="sxs-lookup"><span data-stu-id="b1041-140">The number of unique words that make up the full-text index for the catalog.</span></span>  
  
### <a name="catalog-action"></a><span data-ttu-id="b1041-141">Azione catalogo</span><span class="sxs-lookup"><span data-stu-id="b1041-141">Catalog Action</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="b1041-142">**Nessuno**</span><span class="sxs-lookup"><span data-stu-id="b1041-142">**None**</span></span>|<span data-ttu-id="b1041-143">Non esegue le operazioni **Ottimizza catalogo**, **Ricompila catalogo**o **Ripopola catalogo** .</span><span class="sxs-lookup"><span data-stu-id="b1041-143">Does not perform **Optimize catalog**, **Rebuild catalog**, or **Repopulate catalog** operations.</span></span>|  
|<span data-ttu-id="b1041-144">**Ottimizza catalogo**</span><span class="sxs-lookup"><span data-stu-id="b1041-144">**Optimize catalog**</span></span>|<span data-ttu-id="b1041-145">Consente di ottimizzare l'utilizzo di spazio del catalogo e di migliorare le prestazioni di query,</span><span class="sxs-lookup"><span data-stu-id="b1041-145">Optimizes the space utilization of the catalog and improves query performance.</span></span> <span data-ttu-id="b1041-146">nonché di migliorare l'accuratezza della classificazione della pertinenza dei risultati delle ricerche.</span><span class="sxs-lookup"><span data-stu-id="b1041-146">It also improves the accuracy of relevance ranking of search results.</span></span><br /><br /> <span data-ttu-id="b1041-147">Questa azione esegue ALTER FULLTEXT CATALOG *catalog_name* REORGANIZE.</span><span class="sxs-lookup"><span data-stu-id="b1041-147">This action executes ALTER FULLTEXT CATALOG *catalog_name* REORGANIZE.</span></span>|  
|<span data-ttu-id="b1041-148">**Ricompila catalogo**</span><span class="sxs-lookup"><span data-stu-id="b1041-148">**Rebuild catalog**</span></span>|<span data-ttu-id="b1041-149">Consente di eliminare e ricompilare il catalogo full-text.</span><span class="sxs-lookup"><span data-stu-id="b1041-149">Deletes and rebuilds the full-text catalog.</span></span> <span data-ttu-id="b1041-150">È necessario eseguire questa operazione quando viene modificata una proprietà fondamentale del catalogo, ad esempio l'impostazione relativa alla distinzione dei caratteri accentati e non accentati.</span><span class="sxs-lookup"><span data-stu-id="b1041-150">This operation must be performed if a fundamental catalog property is changed, such as accent sensitivity.</span></span><br /><br /> <span data-ttu-id="b1041-151">Affinché l'operazione di ricompilazione abbia esito positivo, il filegroup in cui risiede il catalogo full-text deve essere online oppure di lettura e scrittura.</span><span class="sxs-lookup"><span data-stu-id="b1041-151">For the rebuild to succeed, the filegroup the full-text catalog resides in must be online or read-writeable.</span></span> <span data-ttu-id="b1041-152">Al termine della ricompilazione, l'indice full-text verrà ripopolato.</span><span class="sxs-lookup"><span data-stu-id="b1041-152">After the rebuild, the full-text index will be repopulated.</span></span><br /><br /> <span data-ttu-id="b1041-153">Questa azione esegue ALTER FULLTEXT CATALOG *catalog_name* Rebuild.</span><span class="sxs-lookup"><span data-stu-id="b1041-153">This action executes ALTER FULLTEXT CATALOG *catalog_name* REBUILD.</span></span>|  
|<span data-ttu-id="b1041-154">**Ripopola catalogo**</span><span class="sxs-lookup"><span data-stu-id="b1041-154">**Repopulate catalog**</span></span>|<span data-ttu-id="b1041-155">Consente di aggiornare il catalogo con le modifiche più recenti apportate ai dati.</span><span class="sxs-lookup"><span data-stu-id="b1041-155">Updates the catalog with recent changes to the data.</span></span> <span data-ttu-id="b1041-156">Questa opzione implica tempi di inattività del catalogo.</span><span class="sxs-lookup"><span data-stu-id="b1041-156">This option does require catalog downtime.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="b1041-157">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b1041-157">See Also</span></span>  
 [<span data-ttu-id="b1041-158">Popolamento degli indici full-text</span><span class="sxs-lookup"><span data-stu-id="b1041-158">Populate Full-Text Indexes</span></span>](../relational-databases/indexes/indexes.md)  
  
  
