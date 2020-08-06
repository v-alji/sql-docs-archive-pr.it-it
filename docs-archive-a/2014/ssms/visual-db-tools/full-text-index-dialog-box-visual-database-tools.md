---
title: Finestra di dialogo Indice full-text (Visual Database Tools) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
f1_keywords:
- vdt.dlgbox.fulltextindex
ms.assetid: ef45b585-2567-4abe-b421-9fd0994e0146
author: stevestein
ms.author: sstein
ms.openlocfilehash: f98d3bf43707caedd8c9d0a01349f36d5a5bfbcf
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87725184"
---
# <a name="full-text-index-dialog-box-visual-database-tools"></a><span data-ttu-id="7bc26-102">Finestra di dialogo Indice full-text (Visual Database Tools)</span><span class="sxs-lookup"><span data-stu-id="7bc26-102">Full-Text Index Dialog Box (Visual Database Tools)</span></span>
  <span data-ttu-id="7bc26-103">Questa finestra di dialogo consente di creare un indice full-text per eseguire ricerche full-text nelle colonne basate su testo delle tabelle di database.</span><span class="sxs-lookup"><span data-stu-id="7bc26-103">This dialog box allows you to create a full-text index, for full-text searches on text-based columns in your database tables.</span></span> <span data-ttu-id="7bc26-104">Poiché un indice di questo tipo si basa su un indice normale, è necessario innanzitutto creare tale indice.</span><span class="sxs-lookup"><span data-stu-id="7bc26-104">A full-text index relies on a regular index, so you must create that first.</span></span> <span data-ttu-id="7bc26-105">L'indice normale deve essere creato utilizzando una sola colonna non Null, preferibilmente con valori non particolarmente elevati.</span><span class="sxs-lookup"><span data-stu-id="7bc26-105">The regular index must be created on a single, non-null column; it is best to choose a column with small values rather than a column with large ones.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="7bc26-106">Per creare un indice full-text, è innanzitutto necessario creare un catalogo full-text per il database utilizzando uno strumento esterno quale [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] o Enterprise Manager.</span><span class="sxs-lookup"><span data-stu-id="7bc26-106">To create a full-text index, you must first create a full-text catalog for the database using an outside tool, such as [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or Enterprise Manager.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="7bc26-107">La funzionalità degli indici full-text non è disponibile in tutte le edizioni di [!INCLUDE[msCoName](../../includes/msconame-md.md)][!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="7bc26-107">Full-text index functionality is not available in every edition of [!INCLUDE[msCoName](../../includes/msconame-md.md)][!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="7bc26-108">Per un elenco delle funzionalità supportate dalle edizioni di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], vedere [Features Supported by the Editions of SQL Server 2014](../../getting-started/features-supported-by-the-editions-of-sql-server-2014.md).</span><span class="sxs-lookup"><span data-stu-id="7bc26-108">For a list of features that are supported by the editions of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], see [Features Supported by the Editions of SQL Server 2014](../../getting-started/features-supported-by-the-editions-of-sql-server-2014.md).</span></span>  
  
## <a name="options"></a><span data-ttu-id="7bc26-109">Opzioni</span><span class="sxs-lookup"><span data-stu-id="7bc26-109">Options</span></span>  
 <span data-ttu-id="7bc26-110">**Indice full-text selezionato**</span><span class="sxs-lookup"><span data-stu-id="7bc26-110">**Selected Full-Text Index**</span></span>  
 <span data-ttu-id="7bc26-111">Elenca gli indici full-text disponibili.</span><span class="sxs-lookup"><span data-stu-id="7bc26-111">Lists existing full-text indexes.</span></span> <span data-ttu-id="7bc26-112">Selezionarne uno per visualizzarne le proprietà nella griglia a destra.</span><span class="sxs-lookup"><span data-stu-id="7bc26-112">Select an index to show its properties in the grid to the right.</span></span> <span data-ttu-id="7bc26-113">Se l'elenco è vuoto, significa che per la tabella non sono state definite relazioni full-text.</span><span class="sxs-lookup"><span data-stu-id="7bc26-113">If the list is empty, no full-text relationships have been defined for the table.</span></span>  
  
 <span data-ttu-id="7bc26-114">**Aggiungere**</span><span class="sxs-lookup"><span data-stu-id="7bc26-114">**Add**</span></span>  
 <span data-ttu-id="7bc26-115">Crea un nuovo indice full-text.</span><span class="sxs-lookup"><span data-stu-id="7bc26-115">Create a new full-text index.</span></span>  
  
 <span data-ttu-id="7bc26-116">**Elimina**</span><span class="sxs-lookup"><span data-stu-id="7bc26-116">**Delete**</span></span>  
 <span data-ttu-id="7bc26-117">Elimina l'elemento selezionato nell'elenco **Indice full-text selezionato** .</span><span class="sxs-lookup"><span data-stu-id="7bc26-117">Delete the full-text index selected in the **Selected Full-Text Index** list.</span></span>  
  
 <span data-ttu-id="7bc26-118">**Categoria Generale**</span><span class="sxs-lookup"><span data-stu-id="7bc26-118">**General Category**</span></span>  
 <span data-ttu-id="7bc26-119">Se viene espansa, visualizza **Colonne** e **Nome catalogo full-text**.</span><span class="sxs-lookup"><span data-stu-id="7bc26-119">When expanded, shows **Columns** and **Full-text Catalog Name**.</span></span>  
  
 <span data-ttu-id="7bc26-120">**Colonne**</span><span class="sxs-lookup"><span data-stu-id="7bc26-120">**Columns**</span></span>  
 <span data-ttu-id="7bc26-121">Visualizza un elenco separato da virgole con i nomi delle colonne in cui è possibile effettuare la ricerca full-text.</span><span class="sxs-lookup"><span data-stu-id="7bc26-121">Displays a comma-separated list of the names of full-text-searchable columns.</span></span> <span data-ttu-id="7bc26-122">Per visualizzare l'elenco completo, fare clic sul pulsante con i puntini di sospensione ( **...** ) a sinistra del campo della proprietà.</span><span class="sxs-lookup"><span data-stu-id="7bc26-122">To see the complete list, click the ellipsis button (**...**) to the left of the property field.</span></span>  
  
 <span data-ttu-id="7bc26-123">**Full-Text Catalog Name**</span><span class="sxs-lookup"><span data-stu-id="7bc26-123">**Full-Text Catalog Name**</span></span>  
 <span data-ttu-id="7bc26-124">Visualizza il nome del catalogo full-text in cui è archiviato l'indice full-text.</span><span class="sxs-lookup"><span data-stu-id="7bc26-124">Displays the name of the full-text catalog on which this full-text index is stored.</span></span> <span data-ttu-id="7bc26-125">Per archiviare l'indice in un catalogo diverso, fare clic sul nome del catalogo e selezionarne un altro dall'elenco a discesa.</span><span class="sxs-lookup"><span data-stu-id="7bc26-125">To store the index on a different catalog, click the catalog name and choose another from the drop-down list.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="7bc26-126">Il catalogo deve essere già stato creato con uno strumento esterno, ad esempio [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] o Enterprise Manager.</span><span class="sxs-lookup"><span data-stu-id="7bc26-126">The catalog must be created first in an outside tool, such as [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or Enterprise Manager.</span></span>  
  
 <span data-ttu-id="7bc26-127">**Categoria Identità**</span><span class="sxs-lookup"><span data-stu-id="7bc26-127">**Identity Category**</span></span>  
 <span data-ttu-id="7bc26-128">Se viene espansa, visualizza il campo del nome dell'indice.</span><span class="sxs-lookup"><span data-stu-id="7bc26-128">When expanded, shows the name field for this index.</span></span>  
  
 <span data-ttu-id="7bc26-129">**Nome**</span><span class="sxs-lookup"><span data-stu-id="7bc26-129">**Name**</span></span>  
 <span data-ttu-id="7bc26-130">Visualizza il nome specificato dal sistema per l'indice full-text.</span><span class="sxs-lookup"><span data-stu-id="7bc26-130">Displays the system-specified name for this full-text index.</span></span>  
  
 <span data-ttu-id="7bc26-131">**Categoria Progettazione tabelle**</span><span class="sxs-lookup"><span data-stu-id="7bc26-131">**Table Designer Category**</span></span>  
 <span data-ttu-id="7bc26-132">Se viene espansa, visualizza le proprietà che determinano il funzionamento dell'indice.</span><span class="sxs-lookup"><span data-stu-id="7bc26-132">When expanded, shows properties that dictate how the index performs.</span></span>  
  
 <span data-ttu-id="7bc26-133">**Attivo**</span><span class="sxs-lookup"><span data-stu-id="7bc26-133">**Active**</span></span>  
 <span data-ttu-id="7bc26-134">Indica se è possibile eseguire una ricerca full-text utilizzando l'indice full-text.</span><span class="sxs-lookup"><span data-stu-id="7bc26-134">Indicates whether you can currently perform a full-text search using this full-text index.</span></span>  
  
 <span data-ttu-id="7bc26-135">**Impostazione ricerca delle modifiche**</span><span class="sxs-lookup"><span data-stu-id="7bc26-135">**Change Tracking Setting**</span></span>  
 <span data-ttu-id="7bc26-136">Visualizza lo stato della ricerca delle modifiche per l'indice: Manuale, Automatico o Disattivato.</span><span class="sxs-lookup"><span data-stu-id="7bc26-136">Describes the status of change tracking for this index: Manual, Auto, or Off.</span></span>  
  
 <span data-ttu-id="7bc26-137">**Ricerca completata**</span><span class="sxs-lookup"><span data-stu-id="7bc26-137">**Crawl Completed**</span></span>  
 <span data-ttu-id="7bc26-138">Indica se la ricerca più recente è stata completata.</span><span class="sxs-lookup"><span data-stu-id="7bc26-138">Shows whether the most recent crawl has been completed.</span></span> <span data-ttu-id="7bc26-139">Se la proprietà è impostata su No, è in corso una ricerca.</span><span class="sxs-lookup"><span data-stu-id="7bc26-139">If this property value is No, a crawl is currently in progress.</span></span>  
  
 <span data-ttu-id="7bc26-140">**Data e ora di fine ricerca corrente o più recente**</span><span class="sxs-lookup"><span data-stu-id="7bc26-140">**End Date And Time Of Current Or Last Crawl**</span></span>  
 <span data-ttu-id="7bc26-141">Visualizza la data e l'ora in cui è terminata la ricerca più recente.</span><span class="sxs-lookup"><span data-stu-id="7bc26-141">Displays the date and time that the most recent crawl ended.</span></span>  
  
 <span data-ttu-id="7bc26-142">**Errori nella ricerca corrente o più recente**</span><span class="sxs-lookup"><span data-stu-id="7bc26-142">**Errors In Current Or Last Crawl**</span></span>  
 <span data-ttu-id="7bc26-143">Visualizza il numero di errori verificatisi nella ricerca corrente o più recente.</span><span class="sxs-lookup"><span data-stu-id="7bc26-143">Displays the number of errors in current or most recent crawl.</span></span>  
  
 <span data-ttu-id="7bc26-144">**Versione indice**</span><span class="sxs-lookup"><span data-stu-id="7bc26-144">**Index Version**</span></span>  
 <span data-ttu-id="7bc26-145">Visualizza la versione dello schema della tabella al momento in cui è stata avviata la ricerca.</span><span class="sxs-lookup"><span data-stu-id="7bc26-145">Displays the schema version of table at time the crawl started.</span></span>  
  
 <span data-ttu-id="7bc26-146">**Righe nella ricerca corrente o più recente**</span><span class="sxs-lookup"><span data-stu-id="7bc26-146">**Rows In Current Or Last Crawl**</span></span>  
 <span data-ttu-id="7bc26-147">Visualizza il numero di righe aggiornate nella ricerca corrente o più recente.</span><span class="sxs-lookup"><span data-stu-id="7bc26-147">Displays the number of rows updated in the current or most recent crawl.</span></span>  
  
 <span data-ttu-id="7bc26-148">**Data e ora di inizio ricerca corrente o più recente**</span><span class="sxs-lookup"><span data-stu-id="7bc26-148">**Start Date And Time Of Current Or Last Crawl**</span></span>  
 <span data-ttu-id="7bc26-149">Visualizza la data e l'ora in cui è iniziata la ricerca corrente o più recente.</span><span class="sxs-lookup"><span data-stu-id="7bc26-149">Displays the date and time that the current or most recent crawl started.</span></span>  
  
 <span data-ttu-id="7bc26-150">**Timestamp per ricerca successiva**</span><span class="sxs-lookup"><span data-stu-id="7bc26-150">**Time Stamp For Next Crawl**</span></span>  
 <span data-ttu-id="7bc26-151">Visualizza la data e l'ora di inizio della prossima ricerca.</span><span class="sxs-lookup"><span data-stu-id="7bc26-151">Displays the date and time that the next crawl will start.</span></span>  
  
 <span data-ttu-id="7bc26-152">**Tipo di ricerca corrente o più recente**</span><span class="sxs-lookup"><span data-stu-id="7bc26-152">**Type Of Current Or Last Crawl**</span></span>  
 <span data-ttu-id="7bc26-153">Visualizza il tipo della ricerca corrente o più recente: Completa, Incrementale, Aggiornamento o Propagazione automatica.</span><span class="sxs-lookup"><span data-stu-id="7bc26-153">Displays the type of the current or most recent crawl: Full, Incremental, Update, or Auto Propagation.</span></span>  
  
 <span data-ttu-id="7bc26-154">**Nome indice univoco**</span><span class="sxs-lookup"><span data-stu-id="7bc26-154">**Unique Index Name**</span></span>  
 <span data-ttu-id="7bc26-155">Visualizza un elenco di tutti i nomi delle colonne del database con indici di colonne singole univoci.</span><span class="sxs-lookup"><span data-stu-id="7bc26-155">Displays a list of all of the names of columns in this database that have unique single-column indexes.</span></span> <span data-ttu-id="7bc26-156">Queste colonne possono essere utilizzate per creare un indice full-text.</span><span class="sxs-lookup"><span data-stu-id="7bc26-156">These columns can be used to create a full-text index.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7bc26-157">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="7bc26-157">See Also</span></span>  
 <span data-ttu-id="7bc26-158">[Utilizzare l'indicizzazione guidata full-text](../../relational-databases/search/use-the-full-text-indexing-wizard.md) </span><span class="sxs-lookup"><span data-stu-id="7bc26-158">[Use the Full-Text Indexing Wizard](../../relational-databases/search/use-the-full-text-indexing-wizard.md) </span></span>  
 [<span data-ttu-id="7bc26-159">CREATE FULLTEXT INDEX &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="7bc26-159">CREATE FULLTEXT INDEX &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/create-fulltext-index-transact-sql)  
  
  
