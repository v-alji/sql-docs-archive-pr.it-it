---
title: Finestra di dialogo Indici spaziali (Visual Database Tools) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
f1_keywords:
- vdt.dlgbox.spatialindexes
ms.assetid: 4d84239a-68c7-4aa2-8602-2b51dd07260f
author: stevestein
ms.author: sstein
ms.openlocfilehash: e401b7f93a8376b1c6dc0c75ca29cbdc8a39863d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87628060"
---
# <a name="spatial-indexes-dialog-box-visual-database-tools"></a><span data-ttu-id="2ef0e-102">Finestra di dialogo Indici spaziali (Visual Database Tools)</span><span class="sxs-lookup"><span data-stu-id="2ef0e-102">Spatial Indexes Dialog Box (Visual Database Tools)</span></span>
  <span data-ttu-id="2ef0e-103">La finestra di dialogo **Indici spaziali** consente di creare indici per le colonne con tipo di dati **geometria** o **geografia** (*colonne spaziali*), che non possono essere indicizzate con la finestra di dialogo **Indici/chiavi** .</span><span class="sxs-lookup"><span data-stu-id="2ef0e-103">Use the **Spatial Indexes** dialog box to create indexes for columns of the **geometry** or **geography** data type (*spatial columns*), which cannot be indexed using the **Index/Keys** dialog box.</span></span> <span data-ttu-id="2ef0e-104">Ogni colonna spaziale può avere più indici spaziali, ma gli indici devono essere creati uno alla volta.</span><span class="sxs-lookup"><span data-stu-id="2ef0e-104">Each spatial column can have more than one spatial index, but they must be created one at a time.</span></span>  
  
 <span data-ttu-id="2ef0e-105">Per informazioni sulle restrizioni alla creazione di indici spaziali, vedere [Panoramica degli indici spaziali](../../relational-databases/spatial/spatial-indexes-overview.md).</span><span class="sxs-lookup"><span data-stu-id="2ef0e-105">For information about restrictions on spatial index creation, see [Spatial Indexes Overview](../../relational-databases/spatial/spatial-indexes-overview.md).</span></span>  
  
## <a name="options"></a><span data-ttu-id="2ef0e-106">Opzioni</span><span class="sxs-lookup"><span data-stu-id="2ef0e-106">Options</span></span>  
 <span data-ttu-id="2ef0e-107">**Indice spaziale selezionato**</span><span class="sxs-lookup"><span data-stu-id="2ef0e-107">**Selected Spatial Index**</span></span>  
 <span data-ttu-id="2ef0e-108">Consente di visualizzare un elenco degli indici spaziali esistenti.</span><span class="sxs-lookup"><span data-stu-id="2ef0e-108">Lists existing spatial indexes.</span></span> <span data-ttu-id="2ef0e-109">Selezionare un indice per visualizzare le relative proprietà.</span><span class="sxs-lookup"><span data-stu-id="2ef0e-109">Select an index to show its properties.</span></span> <span data-ttu-id="2ef0e-110">Se l'elenco è vuoto, significa che non sono stati definiti indici spaziali per la tabella.</span><span class="sxs-lookup"><span data-stu-id="2ef0e-110">If the list is empty, no spatial indexes have been defined for the table.</span></span>  
  
 <span data-ttu-id="2ef0e-111">**Aggiungere**</span><span class="sxs-lookup"><span data-stu-id="2ef0e-111">**Add**</span></span>  
 <span data-ttu-id="2ef0e-112">Consente di creare un nuovo indice spaziale.</span><span class="sxs-lookup"><span data-stu-id="2ef0e-112">Creates a new spatial index.</span></span>  
  
 <span data-ttu-id="2ef0e-113">**Elimina**</span><span class="sxs-lookup"><span data-stu-id="2ef0e-113">**Delete**</span></span>  
 <span data-ttu-id="2ef0e-114">Consente di eliminare l'indice spaziale selezionato nell'elenco **Indice spaziale selezionato** .</span><span class="sxs-lookup"><span data-stu-id="2ef0e-114">Deletes the spatial index selected in the **Selected Spatial Index** list.</span></span>  
  
 <span data-ttu-id="2ef0e-115">**Celle per oggetto**</span><span class="sxs-lookup"><span data-stu-id="2ef0e-115">**Cells Per Object**</span></span>  
 <span data-ttu-id="2ef0e-116">Indica il numero di celle per oggetto di mosaico utilizzabile per un singolo oggetto spaziale nell'indice.</span><span class="sxs-lookup"><span data-stu-id="2ef0e-116">Indicates the number of tessellation cells-per-object that can be used for a single spatial object in the index.</span></span> <span data-ttu-id="2ef0e-117">È possibile usare qualsiasi numero intero compreso tra 1 e 8192.</span><span class="sxs-lookup"><span data-stu-id="2ef0e-117">This number can be any integer between 1 and 8192, inclusive.</span></span> <span data-ttu-id="2ef0e-118">Il valore predefinito è 16.</span><span class="sxs-lookup"><span data-stu-id="2ef0e-118">The default is 16.</span></span>  
  
 <span data-ttu-id="2ef0e-119">Se un oggetto include più celle rispetto a quanto specificato da *n*, per l'indicizzazione viene usata la quantità di celle necessaria a offrire un mosaico di livello principale completo.</span><span class="sxs-lookup"><span data-stu-id="2ef0e-119">If an object covers more cells than specified by *n*, the indexing uses as many cells as necessary to provide a complete top-level tessellation.</span></span> <span data-ttu-id="2ef0e-120">In tali casi un oggetto può ricevere un numero di celle maggiore di quello specificato:</span><span class="sxs-lookup"><span data-stu-id="2ef0e-120">In such cases, an object might receive more than the specified number of cells.</span></span> <span data-ttu-id="2ef0e-121">il numero massimo è il numero di celle generate dalla griglia di livello principale che dipende dalla densità di **Livello 1** .</span><span class="sxs-lookup"><span data-stu-id="2ef0e-121">In this case, the maximum number is the number of cells generated by the top-level grid, which depends on the **Level 1** density.</span></span>  
  
 <span data-ttu-id="2ef0e-122">**Colonne**</span><span class="sxs-lookup"><span data-stu-id="2ef0e-122">**Columns**</span></span>  
 <span data-ttu-id="2ef0e-123">Indica il nome e l'ordinamento della colonna.</span><span class="sxs-lookup"><span data-stu-id="2ef0e-123">Indicates the column name and sort order.</span></span>  
  
 <span data-ttu-id="2ef0e-124">**IsSpatialIndex**</span><span class="sxs-lookup"><span data-stu-id="2ef0e-124">**IsSpatialIndex**</span></span>  
 <span data-ttu-id="2ef0e-125">Indica che è stato selezionato un indice spaziale.</span><span class="sxs-lookup"><span data-stu-id="2ef0e-125">Indicates that a spatial index is selected.</span></span>  
  
 <span data-ttu-id="2ef0e-126">**Livello 1**</span><span class="sxs-lookup"><span data-stu-id="2ef0e-126">**Level 1**</span></span>  
 <span data-ttu-id="2ef0e-127">Indica la densità della griglia di primo livello (superiore).</span><span class="sxs-lookup"><span data-stu-id="2ef0e-127">Indicates the density of the first-level (top) grid.</span></span>  
  
 <span data-ttu-id="2ef0e-128">**Livello 2**</span><span class="sxs-lookup"><span data-stu-id="2ef0e-128">**Level 2**</span></span>  
 <span data-ttu-id="2ef0e-129">Indica la densità della griglia di secondo livello.</span><span class="sxs-lookup"><span data-stu-id="2ef0e-129">Indicates the density of the second-level grid.</span></span>  
  
 <span data-ttu-id="2ef0e-130">**Livello 3**</span><span class="sxs-lookup"><span data-stu-id="2ef0e-130">**Level 3**</span></span>  
 <span data-ttu-id="2ef0e-131">Indica la densità della griglia di terzo livello.</span><span class="sxs-lookup"><span data-stu-id="2ef0e-131">Indicates the density of the third-level grid.</span></span>  
  
 <span data-ttu-id="2ef0e-132">**Livello 4**</span><span class="sxs-lookup"><span data-stu-id="2ef0e-132">**Level 4**</span></span>  
 <span data-ttu-id="2ef0e-133">Indica la densità della griglia di quarto livello.</span><span class="sxs-lookup"><span data-stu-id="2ef0e-133">Indicates the density of the fourth-level grid.</span></span>  
  
 <span data-ttu-id="2ef0e-134">**Schema a mosaico**</span><span class="sxs-lookup"><span data-stu-id="2ef0e-134">**Tessellation Scheme**</span></span>  
 <span data-ttu-id="2ef0e-135">Indica lo schema a mosaico:</span><span class="sxs-lookup"><span data-stu-id="2ef0e-135">Indicates the tessellation scheme:</span></span>  
  
 <span data-ttu-id="2ef0e-136">Opzioni per le colonne di tipo**geometria** :</span><span class="sxs-lookup"><span data-stu-id="2ef0e-136">**Geometry** column options:</span></span>  
  
-   <span data-ttu-id="2ef0e-137">**Griglia geometrica** per una colonna di tipo geometria</span><span class="sxs-lookup"><span data-stu-id="2ef0e-137">**Geometry grid** for a geometry column</span></span>  
  
-   <span data-ttu-id="2ef0e-138">**Griglia geografica** per una colonna di tipo geografia</span><span class="sxs-lookup"><span data-stu-id="2ef0e-138">**Geography grid** for a geography column</span></span>  
  
 <span data-ttu-id="2ef0e-139">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="2ef0e-139">**Type**</span></span>  
 <span data-ttu-id="2ef0e-140">Indica che è stato selezionato un indice spaziale.</span><span class="sxs-lookup"><span data-stu-id="2ef0e-140">Indicates that a spatial index is selected.</span></span>  
  
 <span data-ttu-id="2ef0e-141">**X-max**</span><span class="sxs-lookup"><span data-stu-id="2ef0e-141">**X-max**</span></span>  
 <span data-ttu-id="2ef0e-142">Specifica la coordinata x dell'angolo superiore destro del rettangolo di selezione.</span><span class="sxs-lookup"><span data-stu-id="2ef0e-142">Specifies the x-coordinate of the upper-right corner of the bounding box.</span></span> <span data-ttu-id="2ef0e-143">Questa proprietà è visualizzata in grigio se lo **Schema a mosaico** è **Griglia geografica**.</span><span class="sxs-lookup"><span data-stu-id="2ef0e-143">This property is dimmed if the **Tessellation Scheme** is **Geography grid**.</span></span>  
  
 <span data-ttu-id="2ef0e-144">**X-min**</span><span class="sxs-lookup"><span data-stu-id="2ef0e-144">**X-min**</span></span>  
 <span data-ttu-id="2ef0e-145">Specifica la coordinata x dell'angolo inferiore sinistro del rettangolo di selezione.</span><span class="sxs-lookup"><span data-stu-id="2ef0e-145">Specifies the x-coordinate of the lower-left corner of the bounding box.</span></span> <span data-ttu-id="2ef0e-146">Questa proprietà è visualizzata in grigio se lo **Schema a mosaico** è **Griglia geografica**.</span><span class="sxs-lookup"><span data-stu-id="2ef0e-146">This property is dimmed if the **Tessellation Scheme** is **Geography grid**.</span></span>  
  
 <span data-ttu-id="2ef0e-147">**Y-max**</span><span class="sxs-lookup"><span data-stu-id="2ef0e-147">**Y-max**</span></span>  
 <span data-ttu-id="2ef0e-148">Specifica la coordinata Y dell'angolo superiore destro del riquadro.</span><span class="sxs-lookup"><span data-stu-id="2ef0e-148">Specifies the y-coordinate of upper-right corner of the bounding box.</span></span> <span data-ttu-id="2ef0e-149">Questa proprietà è visualizzata in grigio se lo **Schema a mosaico** è **Griglia geografica**.</span><span class="sxs-lookup"><span data-stu-id="2ef0e-149">This property is dimmed if the **Tessellation Scheme** is **Geography grid**.</span></span>  
  
 <span data-ttu-id="2ef0e-150">**Y-min**</span><span class="sxs-lookup"><span data-stu-id="2ef0e-150">**Y-min**</span></span>  
 <span data-ttu-id="2ef0e-151">Specifica la coordinata y dell'angolo inferiore sinistro del rettangolo di selezione.</span><span class="sxs-lookup"><span data-stu-id="2ef0e-151">Specifies the y-coordinate of the lower-left corner of the bounding box.</span></span> <span data-ttu-id="2ef0e-152">Questa proprietà è visualizzata in grigio se lo **Schema a mosaico** è **Griglia geografica**.</span><span class="sxs-lookup"><span data-stu-id="2ef0e-152">This property is dimmed if the **Tessellation Scheme** is **Geography grid**.</span></span>  
  
 <span data-ttu-id="2ef0e-153">**Identità**</span><span class="sxs-lookup"><span data-stu-id="2ef0e-153">**Identity**</span></span>  
 <span data-ttu-id="2ef0e-154">Se viene espansa, visualizza i campi delle proprietà **Nome** e **Descrizione** .</span><span class="sxs-lookup"><span data-stu-id="2ef0e-154">When expanded, shows the **Name** and **Description** property fields.</span></span>  
  
 <span data-ttu-id="2ef0e-155">**(Nome)**</span><span class="sxs-lookup"><span data-stu-id="2ef0e-155">**(Name)**</span></span>  
 <span data-ttu-id="2ef0e-156">Visualizza il nome dell'indice spaziale.</span><span class="sxs-lookup"><span data-stu-id="2ef0e-156">Shows the name of the spatial index.</span></span> <span data-ttu-id="2ef0e-157">Quando viene creato un nuovo indice, gli viene assegnato un nome predefinito sulla base della tabella presente nella finestra attiva di Progettazione tabelle.</span><span class="sxs-lookup"><span data-stu-id="2ef0e-157">When a new index is created, it is given a default name based on the table in the active window in Table Designer.</span></span> <span data-ttu-id="2ef0e-158">È possibile modificare il nome in qualsiasi momento.</span><span class="sxs-lookup"><span data-stu-id="2ef0e-158">You can change the name at any time.</span></span>  
  
 <span data-ttu-id="2ef0e-159">**Descrizione**</span><span class="sxs-lookup"><span data-stu-id="2ef0e-159">**Description**</span></span>  
 <span data-ttu-id="2ef0e-160">Descrive l'indice.</span><span class="sxs-lookup"><span data-stu-id="2ef0e-160">Describes the index.</span></span> <span data-ttu-id="2ef0e-161">Per inserire una descrizione più dettagliata, fare clic su **Descrizione** e sui puntini di sospensione ( **...** ) a destra del campo della proprietà.</span><span class="sxs-lookup"><span data-stu-id="2ef0e-161">To write a more detailed description, click **Description** and then click the ellipsis button (**...**) that appears to the right of the property field.</span></span> <span data-ttu-id="2ef0e-162">Viene così visualizzata un'area più grande in cui scrivere il testo.</span><span class="sxs-lookup"><span data-stu-id="2ef0e-162">This provides a larger area in which to write text.</span></span>  
  
 <span data-ttu-id="2ef0e-163">**Categoria Progettazione tabelle**</span><span class="sxs-lookup"><span data-stu-id="2ef0e-163">**Table Designer Category**</span></span>  
 <span data-ttu-id="2ef0e-164">Se viene espansa, visualizza le informazioni relative alle proprietà dell'indice spaziale.</span><span class="sxs-lookup"><span data-stu-id="2ef0e-164">When expanded, shows information about the properties of this spatial index.</span></span>  
  
 <span data-ttu-id="2ef0e-165">**Specifica riempimento**</span><span class="sxs-lookup"><span data-stu-id="2ef0e-165">**Fill Specification**</span></span>  
 <span data-ttu-id="2ef0e-166">Se viene espansa, visualizza le informazioni relative a **Riempimento** e **Riempi indice**.</span><span class="sxs-lookup"><span data-stu-id="2ef0e-166">When expanded, shows information for **Fill Factor** and **Pad Index**.</span></span>  
  
 <span data-ttu-id="2ef0e-167">**Riempimento**</span><span class="sxs-lookup"><span data-stu-id="2ef0e-167">**Fill Factor**</span></span>  
 <span data-ttu-id="2ef0e-168">Specifica quale percentuale della pagina dell'indice può essere riempita dal sistema.</span><span class="sxs-lookup"><span data-stu-id="2ef0e-168">Specify what percentage of the index page the system can fill.</span></span> <span data-ttu-id="2ef0e-169">Quando una pagina è piena, se vengono aggiunti nuovi dati deve essere divisa, con un conseguente rallentamento delle prestazioni.</span><span class="sxs-lookup"><span data-stu-id="2ef0e-169">When a page is full, if new data is added, the system must split the page, which impairs performance.</span></span>  
  
-   <span data-ttu-id="2ef0e-170">Un valore pari a 100 indica che le pagine saranno piene. Tale impostazione richiede la quantità più ridotta di spazio di archiviazione ma è la meno efficiente.</span><span class="sxs-lookup"><span data-stu-id="2ef0e-170">A value of 100 means the pages will be full; this requires the least amount of storage space but is the least efficient.</span></span> <span data-ttu-id="2ef0e-171">È consigliabile utilizzare questa impostazione solo se non verranno apportate modifiche ai dati, ad esempio per una tabella di sola lettura.</span><span class="sxs-lookup"><span data-stu-id="2ef0e-171">This setting should be used only when there will be no changes to the data, for example, on a read-only table.</span></span>  
  
-   <span data-ttu-id="2ef0e-172">Un valore inferiore lascia più spazio nelle pagine di dati e quindi riduce la necessità di suddividerle all'aumentare delle dimensioni degli indici,</span><span class="sxs-lookup"><span data-stu-id="2ef0e-172">A lower value leaves more empty space on the data pages, which reduces the need to split data pages as indexes grow.</span></span> <span data-ttu-id="2ef0e-173">ma richiede uno spazio di archiviazione maggiore.</span><span class="sxs-lookup"><span data-stu-id="2ef0e-173">However, it requires more storage space.</span></span> <span data-ttu-id="2ef0e-174">Questa impostazione è consigliabile se si prevede che i dati della tabella saranno soggetti a modifiche.</span><span class="sxs-lookup"><span data-stu-id="2ef0e-174">This setting is more appropriate when there will be changes to the data in the table.</span></span>  
  
 <span data-ttu-id="2ef0e-175">**Riempi indice**</span><span class="sxs-lookup"><span data-stu-id="2ef0e-175">**Pad Index**</span></span>  
 <span data-ttu-id="2ef0e-176">Consente di usare per le pagine dell'indice la stessa percentuale di spazio vuoto (riempimento) specificata in **Fattore di riempimento**.</span><span class="sxs-lookup"><span data-stu-id="2ef0e-176">Provides pages in this index the same percentage of empty space (padding) that is specified in **Fill Factor**.</span></span>  
  
 <span data-ttu-id="2ef0e-177">**Blocchi pagine consentiti**</span><span class="sxs-lookup"><span data-stu-id="2ef0e-177">**Page Locks Allowed**</span></span>  
 <span data-ttu-id="2ef0e-178">Consente di specificare se per l'indice è consentito il blocco a livello di pagina.</span><span class="sxs-lookup"><span data-stu-id="2ef0e-178">Specifies whether page-level locking is allowed on this index.</span></span> <span data-ttu-id="2ef0e-179">L'attivazione o la disattivazione di tale blocco incide sulle prestazioni del database.</span><span class="sxs-lookup"><span data-stu-id="2ef0e-179">Allowing or disallowing page-level locking affects database performance.</span></span>  
  
 <span data-ttu-id="2ef0e-180">**Ricalcola statistiche**</span><span class="sxs-lookup"><span data-stu-id="2ef0e-180">**Re-compute  Statistics**</span></span>  
 <span data-ttu-id="2ef0e-181">Consente di specificare se calcolare nuove statistiche quando viene creato l'indice.</span><span class="sxs-lookup"><span data-stu-id="2ef0e-181">Specifies whether to compute new statistics when the index is created.</span></span> <span data-ttu-id="2ef0e-182">Il ricalcolo delle statistiche rallenta la compilazione degli indici, ma in genere consente di migliorare le prestazioni delle query.</span><span class="sxs-lookup"><span data-stu-id="2ef0e-182">Recomputing statistics slows the building of indexes but usually improves query performance.</span></span>  
  
 <span data-ttu-id="2ef0e-183">**Blocchi righe consentiti**</span><span class="sxs-lookup"><span data-stu-id="2ef0e-183">**Row Locks Allowed**</span></span>  
 <span data-ttu-id="2ef0e-184">Consente di specificare se per l'indice è consentito il blocco a livello di riga.</span><span class="sxs-lookup"><span data-stu-id="2ef0e-184">Specifies whether row-level locking is allowed on this index.</span></span> <span data-ttu-id="2ef0e-185">L'attivazione o la disattivazione di tale blocco incide sulle prestazioni del database.</span><span class="sxs-lookup"><span data-stu-id="2ef0e-185">Allowing or disallowing row-level locking affects database performance.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2ef0e-186">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="2ef0e-186">See Also</span></span>  
 [<span data-ttu-id="2ef0e-187">Panoramica degli indici spaziali</span><span class="sxs-lookup"><span data-stu-id="2ef0e-187">Spatial Indexes Overview</span></span>](../../relational-databases/spatial/spatial-indexes-overview.md)  
  
  
