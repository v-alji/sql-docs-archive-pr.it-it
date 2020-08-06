---
title: Creare e gestire cataloghi full-text | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: search
ms.topic: conceptual
helpviewer_keywords:
- full-text catalogs [SQL Server], creating
- full-text search [SQL Server], using SQL Server Management Studio
ms.assetid: 824b7131-44a6-4815-89e6-62b7bab060e3
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 18efd79bc34beee94d4edc61e9165a986edba90b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87637727"
---
# <a name="create-and-manage-full-text-catalogs"></a><span data-ttu-id="89eac-102">Creazione e gestione dei cataloghi full-text</span><span class="sxs-lookup"><span data-stu-id="89eac-102">Create and Manage Full-Text Catalogs</span></span>
  <span data-ttu-id="89eac-103">Un catalogo full-text è un oggetto virtuale che non appartiene ad alcun filegroup. Si tratta di un concetto logico che fa riferimento a un gruppo di indici full-text.</span><span class="sxs-lookup"><span data-stu-id="89eac-103">A full-text catalog is a virtual object that does not belong to any filegroup; it is a logical concept that refers to a group of full-text indexes.</span></span>  
  
##  <a name="creating-a-full-text-catalog"></a><a name="creating"></a><span data-ttu-id="89eac-104">Creazione di un catalogo full-text</span><span class="sxs-lookup"><span data-stu-id="89eac-104">Creating a Full-Text Catalog</span></span>  
  
#### <a name="to-create-a-full-text-catalog"></a><span data-ttu-id="89eac-105">Per creare un catalogo full-text</span><span class="sxs-lookup"><span data-stu-id="89eac-105">To create a full-text catalog</span></span>  
  
1.  <span data-ttu-id="89eac-106">In Esplora oggetti espandere il server, quindi **Database**e infine il database in cui si vuole creare il catalogo full-text.</span><span class="sxs-lookup"><span data-stu-id="89eac-106">In Object Explorer, expand the server, expand **Databases**, and expand the database in which you want to create the full-text catalog.</span></span>  
  
2.  <span data-ttu-id="89eac-107">Espandere **Archivio**, quindi fare clic con il pulsante destro del mouse su **Cataloghi full-text**.</span><span class="sxs-lookup"><span data-stu-id="89eac-107">Expand **Storage**, and then right-click **Full Text Catalogs**.</span></span>  
  
3.  <span data-ttu-id="89eac-108">Selezionare **Nuovo catalogo full-text**.</span><span class="sxs-lookup"><span data-stu-id="89eac-108">Select **New Full-Text Catalog**.</span></span>  
  
4.  <span data-ttu-id="89eac-109">Nella finestra di dialogo **Nuovo catalogo full-text** specificare le informazioni per il catalogo da creare.</span><span class="sxs-lookup"><span data-stu-id="89eac-109">In the **New Full-Text Catalog** dialog box, specify the information for the catalog that you are re-creating.</span></span> <span data-ttu-id="89eac-110">Per altre informazioni, vedere [Nuovo catalogo full-text &#40;pagina Generale&#41;](../../integration-services/general-page-of-integration-services-designers-options.md).</span><span class="sxs-lookup"><span data-stu-id="89eac-110">For more information, see [New Full-Text Catalog &#40;General Page&#41;](../../integration-services/general-page-of-integration-services-designers-options.md).</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="89eac-111">Gli ID dei cataloghi full-text iniziano da 00005 e vengono incrementati di un'unità per ogni catalogo creato.</span><span class="sxs-lookup"><span data-stu-id="89eac-111">Full-text catalog IDs begin at 00005 and are incremented by one for each new catalog created.</span></span>  
  
5.  [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
  
  
##  <a name="viewing-the-properties-of-a-full-text-catalog"></a><a name="props"></a><span data-ttu-id="89eac-112">Visualizzazione delle proprietà di un catalogo full-text</span><span class="sxs-lookup"><span data-stu-id="89eac-112">Viewing the Properties of a Full-Text Catalog</span></span>  
 <span data-ttu-id="89eac-113">Per ottenere il valore di varie proprietà di indicizzazione full-text, è possibile utilizzare funzioni quali [!INCLUDE[tsql](../../includes/tsql-md.md)] FULLTEXTCATALOGPROPERTY.</span><span class="sxs-lookup"><span data-stu-id="89eac-113">[!INCLUDE[tsql](../../includes/tsql-md.md)] functions such as FULLTEXTCATALOGPROPERTY can be used to obtain the value of various properties related to full-text indexing.</span></span> <span data-ttu-id="89eac-114">Queste informazioni sono utili per l'amministrazione e la risoluzione dei problemi relativi alla ricerca full-text.</span><span class="sxs-lookup"><span data-stu-id="89eac-114">This information is useful for administering and troubleshooting full-text search.</span></span>  
  
 <span data-ttu-id="89eac-115">Nella tabella seguente sono elencate le proprietà correlate ai cataloghi full-text.</span><span class="sxs-lookup"><span data-stu-id="89eac-115">The following table lists the properties that are related to full-text catalogs.</span></span>  
  
|<span data-ttu-id="89eac-116">Proprietà</span><span class="sxs-lookup"><span data-stu-id="89eac-116">Property</span></span>|<span data-ttu-id="89eac-117">Descrizione</span><span class="sxs-lookup"><span data-stu-id="89eac-117">Description</span></span>|<span data-ttu-id="89eac-118">Funzione</span><span class="sxs-lookup"><span data-stu-id="89eac-118">Function</span></span>|  
|--------------|-----------------|--------------|  
|`AccentSensitivity`|<span data-ttu-id="89eac-119">Impostazione relativa alla distinzione tra caratteri accentati e non accentati.</span><span class="sxs-lookup"><span data-stu-id="89eac-119">Accent-sensitivity setting.</span></span>|[<span data-ttu-id="89eac-120">FULLTEXTCATALOGPROPERTY</span><span class="sxs-lookup"><span data-stu-id="89eac-120">FULLTEXTCATALOGPROPERTY</span></span>](/sql/t-sql/functions/fulltextcatalogproperty-transact-sql)|  
|`ImportStatus`|<span data-ttu-id="89eac-121">Indica se il catalogo full-text viene importato o meno.</span><span class="sxs-lookup"><span data-stu-id="89eac-121">Whether the full-text catalog is being imported.</span></span>|<span data-ttu-id="89eac-122">FULLTEXTCATALOGPROPERTY</span><span class="sxs-lookup"><span data-stu-id="89eac-122">FULLTEXTCATALOGPROPERTY</span></span>|  
|`IndexSize`|<span data-ttu-id="89eac-123">Dimensione del catalogo full-text in megabyte (MB).</span><span class="sxs-lookup"><span data-stu-id="89eac-123">Size of the full-text catalog in megabytes (MB).</span></span>|<span data-ttu-id="89eac-124">FULLTEXTCATALOGPROPERTY</span><span class="sxs-lookup"><span data-stu-id="89eac-124">FULLTEXTCATALOGPROPERTY</span></span>|  
|`ItemCount`|<span data-ttu-id="89eac-125">Numero delle voci indicizzate incluse attualmente nel catalogo full-text.</span><span class="sxs-lookup"><span data-stu-id="89eac-125">Number of full-text indexed items currently in the full-text catalog.</span></span>|<span data-ttu-id="89eac-126">FULLTEXTCATALOGPROPERTY</span><span class="sxs-lookup"><span data-stu-id="89eac-126">FULLTEXTCATALOGPROPERTY</span></span>|  
|`MergeStatus`|<span data-ttu-id="89eac-127">Indica se è in corso un'unione nell'indice master.</span><span class="sxs-lookup"><span data-stu-id="89eac-127">Whether a master merge is in progress.</span></span>|<span data-ttu-id="89eac-128">FULLTEXTCATALOGPROPERTY</span><span class="sxs-lookup"><span data-stu-id="89eac-128">FULLTEXTCATALOGPROPERTY</span></span>|  
|`PopulateCompletionAge`|<span data-ttu-id="89eac-129">Differenza espressa in secondi tra il completamento dell'ultimo popolamento di indici full-text e la data 01/01/1990 00:00:00.</span><span class="sxs-lookup"><span data-stu-id="89eac-129">Difference in seconds between the completion of the last full-text index population and 01/01/1990 00:00:00.</span></span>|<span data-ttu-id="89eac-130">FULLTEXTCATALOGPROPERTY</span><span class="sxs-lookup"><span data-stu-id="89eac-130">FULLTEXTCATALOGPROPERTY</span></span>|  
|`PopulateStatus`|<span data-ttu-id="89eac-131">Stato popolamento.</span><span class="sxs-lookup"><span data-stu-id="89eac-131">Populate status.</span></span><br /><br /> [!INCLUDE[ssNoteDepFutureAvoid](../../includes/ssnotedepfutureavoid-md.md)]|<span data-ttu-id="89eac-132">FULLTEXTCATALOGPROPERTY</span><span class="sxs-lookup"><span data-stu-id="89eac-132">FULLTEXTCATALOGPROPERTY</span></span>|  
|`UniqueKeyCount`|<span data-ttu-id="89eac-133">Numero di chiavi univoche nel catalogo full-text.</span><span class="sxs-lookup"><span data-stu-id="89eac-133">Number of unique keys in the full-text catalog.</span></span>|<span data-ttu-id="89eac-134">FULLTEXTCATALOGPROPERTY</span><span class="sxs-lookup"><span data-stu-id="89eac-134">FULLTEXTCATALOGPROPERTY</span></span>|  
  
  
  
##  <a name="rebuilding-a-full-text-catalog"></a><a name="rebuildone"></a><span data-ttu-id="89eac-135">Ricompilazione di un catalogo full-text</span><span class="sxs-lookup"><span data-stu-id="89eac-135">Rebuilding a Full-Text Catalog</span></span>  
  
#### <a name="to-rebuild-a-full-text-catalog"></a><span data-ttu-id="89eac-136">Per ricompilare un catalogo full-text</span><span class="sxs-lookup"><span data-stu-id="89eac-136">To rebuild a full-text catalog</span></span>  
  
1.  <span data-ttu-id="89eac-137">In Esplora oggetti espandere il server, quindi **Database**e infine il database contenente il catalogo full-text che si vuole ricompilare.</span><span class="sxs-lookup"><span data-stu-id="89eac-137">In Object Explorer, expand the server, expand **Databases**, and then expand the database that contains the full-text catalog that you want to rebuild.</span></span>  
  
2.  <span data-ttu-id="89eac-138">Espandere **Archivio**e quindi **Cataloghi full-text**.</span><span class="sxs-lookup"><span data-stu-id="89eac-138">Expand **Storage**, and then expand **Full Text Catalogs**.</span></span>  
  
3.  <span data-ttu-id="89eac-139">Fare clic con il pulsante destro sul nome del catalogo full-text da ricompilare e scegliere **Ricompila**.</span><span class="sxs-lookup"><span data-stu-id="89eac-139">Right-click the name of the full-text catalog that you want to rebuild, and select **Rebuild**.</span></span>  
  
4.  <span data-ttu-id="89eac-140">Quando viene visualizzato il messaggio **Eliminare il catalogo full-text e ricompilarlo?**, fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="89eac-140">To the question **Do you want to delete the full-text catalog and rebuild it?**, click **OK**.</span></span>  
  
5.  <span data-ttu-id="89eac-141">Nella finestra di dialogo **Ricompila catalogo full-text** fare clic su **Chiudi**.</span><span class="sxs-lookup"><span data-stu-id="89eac-141">In the **Rebuild Full-Text Catalog** dialog box, click **Close**.</span></span>  
  
  
  
##  <a name="rebuilding-all-full-text-catalogs-for-a-database"></a><a name="rebuildall"></a><span data-ttu-id="89eac-142">Ricompilazione di tutti i cataloghi full-text per un database</span><span class="sxs-lookup"><span data-stu-id="89eac-142">Rebuilding All Full-Text Catalogs for a Database</span></span>  
  
#### <a name="to-rebuild-the-full-text-catalogs-for-a-database"></a><span data-ttu-id="89eac-143">Per ricompilare i cataloghi full-text di un database</span><span class="sxs-lookup"><span data-stu-id="89eac-143">To rebuild the full-text catalogs for a database</span></span>  
  
1.  <span data-ttu-id="89eac-144">In Esplora oggetti espandere il server, quindi **Database**e infine il database contenente i cataloghi full-text da ricompilare.</span><span class="sxs-lookup"><span data-stu-id="89eac-144">In Object Explorer, expand the server, expand **Databases**, and then expand the database that contains the full-text catalogs that you want to rebuild.</span></span>  
  
2.  <span data-ttu-id="89eac-145">Espandere **Archivio**, quindi fare clic con il pulsante destro del mouse su **Cataloghi full-text**.</span><span class="sxs-lookup"><span data-stu-id="89eac-145">Expand **Storage**, and then right-click **Full Text Catalogs**.</span></span>  
  
3.  <span data-ttu-id="89eac-146">Scegliere **Ricompila tutto**.</span><span class="sxs-lookup"><span data-stu-id="89eac-146">Select **Rebuild All**.</span></span>  
  
4.  <span data-ttu-id="89eac-147">Quando viene visualizzato il messaggio **Eliminare tutti i cataloghi full-text e ricompilarli?**, fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="89eac-147">To the question, **Do you want to delete all full-text catalogs and rebuild them?**, click **OK**.</span></span>  
  
5.  <span data-ttu-id="89eac-148">Nella finestra di dialogo **Ricompila tutti i cataloghi full-text** scegliere **Chiudi**.</span><span class="sxs-lookup"><span data-stu-id="89eac-148">In the **Rebuild All Full-Text Catalogs** dialog box, click **Close**.</span></span>  
  
  
  
##  <a name="removing-a-full-text-catalog-from-a-database"></a><a name="removing"></a><span data-ttu-id="89eac-149">Rimozione di un catalogo full-text da un database</span><span class="sxs-lookup"><span data-stu-id="89eac-149">Removing a Full-Text Catalog from a Database</span></span>  
  
#### <a name="to-remove-a-full-text-catalog-from-a-database"></a><span data-ttu-id="89eac-150">Per rimuovere un catalogo full-text da un database</span><span class="sxs-lookup"><span data-stu-id="89eac-150">To remove a full-text catalog from a database</span></span>  
  
1.  <span data-ttu-id="89eac-151">In Esplora oggetti espandere il server, quindi **Database**e infine il database contenente il catalogo full-text che si vuole rimuovere.</span><span class="sxs-lookup"><span data-stu-id="89eac-151">In Object Explorer, expand the server, expand **Databases**, and expand the database that contains the full-text catalog you want to remove.</span></span>  
  
2.  <span data-ttu-id="89eac-152">Espandere **Archivio**e quindi **Cataloghi full-text**.</span><span class="sxs-lookup"><span data-stu-id="89eac-152">Expand **Storage**, and expand **Full Text Catalogs**.</span></span>  
  
3.  <span data-ttu-id="89eac-153">Fare clic con il pulsante destro del mouse sul catalogo full-text da rimuovere e quindi scegliere **Elimina**.</span><span class="sxs-lookup"><span data-stu-id="89eac-153">Right-click the full-text catalog that you want to remove, and then select **Delete**.</span></span>  
  
4.  <span data-ttu-id="89eac-154">Nella finestra di dialogo **Elimina oggetti** fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="89eac-154">In the **Delete Objects** dialog box, click **OK**.</span></span>  
  
  
  
## <a name="see-also"></a><span data-ttu-id="89eac-155">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="89eac-155">See Also</span></span>  
 [<span data-ttu-id="89eac-156">CREATE FULLTEXT CATALOG &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="89eac-156">CREATE FULLTEXT CATALOG &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/create-fulltext-catalog-transact-sql)  
  
  
