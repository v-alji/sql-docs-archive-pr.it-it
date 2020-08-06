---
title: Finestra di dialogo Indici XML (Visual Database Tools) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
f1_keywords:
- vdt.dlgbox.xmlindexes
ms.assetid: eef38310-4498-4ccc-bb77-5bbd1c7cc477
author: stevestein
ms.author: sstein
ms.openlocfilehash: f1fb23a801a9129611c032fa1d659caf624088aa
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87630193"
---
# <a name="xml-indexes-dialog-box-visual-database-tools"></a><span data-ttu-id="2dd9a-102">Finestra di dialogo Indici XML (Visual Database Tools)</span><span class="sxs-lookup"><span data-stu-id="2dd9a-102">XML Indexes Dialog Box (Visual Database Tools)</span></span>
  <span data-ttu-id="2dd9a-103">Usare la finestra di dialogo **Indici XML** per creare indici per le colonne con tipo di dati XML, le quali non possono essere indicizzate usando la finestra di dialogo **Indici/chiavi** .</span><span class="sxs-lookup"><span data-stu-id="2dd9a-103">Use the **XML Indexes** dialog box to create indexes for columns of the data type XML, which cannot be indexed using the **Index/Keys** dialog box.</span></span> <span data-ttu-id="2dd9a-104">Ogni colonna XML può avere più indici XML, ma il primo indice creato (primario) verrà utilizzato come base degli altri (secondari).</span><span class="sxs-lookup"><span data-stu-id="2dd9a-104">Each XML column can have more than one XML Index, but the first one created (primary) will be the basis of the others (secondary).</span></span> <span data-ttu-id="2dd9a-105">Eliminando l'indice XML primario, verranno eliminati anche gli indici secondari.</span><span class="sxs-lookup"><span data-stu-id="2dd9a-105">If you delete the primary XML index, the secondary indexes will also be deleted.</span></span>  
  
## <a name="options"></a><span data-ttu-id="2dd9a-106">Opzioni</span><span class="sxs-lookup"><span data-stu-id="2dd9a-106">Options</span></span>  
 <span data-ttu-id="2dd9a-107">**Indice XML selezionato**</span><span class="sxs-lookup"><span data-stu-id="2dd9a-107">**Selected XML Index**</span></span>  
 <span data-ttu-id="2dd9a-108">Elenca gli indici XML esistenti.</span><span class="sxs-lookup"><span data-stu-id="2dd9a-108">Lists existing XML indexes.</span></span> <span data-ttu-id="2dd9a-109">Selezionarne uno per visualizzarne le proprietà nella griglia di destra.</span><span class="sxs-lookup"><span data-stu-id="2dd9a-109">Select to show its properties in the grid to the right.</span></span> <span data-ttu-id="2dd9a-110">Se l'elenco è vuoto, per la tabella non sono stati definiti indici.</span><span class="sxs-lookup"><span data-stu-id="2dd9a-110">If the list is empty, none have been defined for the table.</span></span>  
  
 <span data-ttu-id="2dd9a-111">**Aggiungere**</span><span class="sxs-lookup"><span data-stu-id="2dd9a-111">**Add**</span></span>  
 <span data-ttu-id="2dd9a-112">Consente di creare un nuovo indice XML.</span><span class="sxs-lookup"><span data-stu-id="2dd9a-112">Create a new XML index.</span></span>  
  
 <span data-ttu-id="2dd9a-113">**Elimina**</span><span class="sxs-lookup"><span data-stu-id="2dd9a-113">**Delete**</span></span>  
 <span data-ttu-id="2dd9a-114">Elimina l'elemento selezionato nell'elenco **Indice XML selezionato** .</span><span class="sxs-lookup"><span data-stu-id="2dd9a-114">Delete XML index selected in the **Selected XML Index** list.</span></span> <span data-ttu-id="2dd9a-115">Se si elimina l'indice XML primario, un messaggio informerà che verranno eliminati anche gli indici secondari e sarà possibile scegliere di continuare o annullare l'operazione.</span><span class="sxs-lookup"><span data-stu-id="2dd9a-115">If you delete the primary XML index, you will be notified that this will delete all secondary ones as well, and you can either continue or cancel the action.</span></span>  
  
 <span data-ttu-id="2dd9a-116">**Categoria Generale**</span><span class="sxs-lookup"><span data-stu-id="2dd9a-116">**General Category**</span></span>  
 <span data-ttu-id="2dd9a-117">Se viene espansa, visualizza i campi delle proprietà relativi a **Colonne**, **Is Primary**e **Tipo**.</span><span class="sxs-lookup"><span data-stu-id="2dd9a-117">When expanded, shows the property fields for **Columns**, **Is Primary**, and **Type**.</span></span>  
  
 <span data-ttu-id="2dd9a-118">**Colonne**</span><span class="sxs-lookup"><span data-stu-id="2dd9a-118">**Columns**</span></span>  
 <span data-ttu-id="2dd9a-119">Indica che l'indice è ordinato in sequenza crescente.</span><span class="sxs-lookup"><span data-stu-id="2dd9a-119">Shows that this index is sorted in ascending order.</span></span>  
  
 <span data-ttu-id="2dd9a-120">**Is Primary**</span><span class="sxs-lookup"><span data-stu-id="2dd9a-120">**Is Primary**</span></span>  
 <span data-ttu-id="2dd9a-121">Indica se si tratta dell'indice primario.</span><span class="sxs-lookup"><span data-stu-id="2dd9a-121">Indicates whether this is the primary index.</span></span> <span data-ttu-id="2dd9a-122">Il primo indice XML creato per la colonna verrà utilizzato come base per gli altri.</span><span class="sxs-lookup"><span data-stu-id="2dd9a-122">The first XML index created on the column will be the basis of the others.</span></span>  
  
 <span data-ttu-id="2dd9a-123">**Nome riferimento primario**</span><span class="sxs-lookup"><span data-stu-id="2dd9a-123">**Primary reference name**</span></span>  
 <span data-ttu-id="2dd9a-124">Nel caso di un indice secondario, visualizza il nome dell'indice primario.</span><span class="sxs-lookup"><span data-stu-id="2dd9a-124">Shows the name of the primary index if this is a secondary index.</span></span> <span data-ttu-id="2dd9a-125">È disponibile solo per gli indici secondari.</span><span class="sxs-lookup"><span data-stu-id="2dd9a-125">Only available if this is a secondary index.</span></span>  
  
 <span data-ttu-id="2dd9a-126">**Tipo secondario**</span><span class="sxs-lookup"><span data-stu-id="2dd9a-126">**Secondary type**</span></span>  
 <span data-ttu-id="2dd9a-127">Visualizza il tipo di indice secondario.</span><span class="sxs-lookup"><span data-stu-id="2dd9a-127">Shows the type of secondary index.</span></span> <span data-ttu-id="2dd9a-128">È disponibile solo per gli indici secondari.</span><span class="sxs-lookup"><span data-stu-id="2dd9a-128">Only available if this is a secondary index.</span></span>  
  
 <span data-ttu-id="2dd9a-129">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="2dd9a-129">**Type**</span></span>  
 <span data-ttu-id="2dd9a-130">Indica che si tratta di un indice XML.</span><span class="sxs-lookup"><span data-stu-id="2dd9a-130">Shows that this is an XML index.</span></span>  
  
 <span data-ttu-id="2dd9a-131">**Categoria Identità**</span><span class="sxs-lookup"><span data-stu-id="2dd9a-131">**Identity Category**</span></span>  
 <span data-ttu-id="2dd9a-132">Se viene espansa, visualizza i campi delle proprietà **Nome** e **Descrizione** .</span><span class="sxs-lookup"><span data-stu-id="2dd9a-132">When expanded, shows the **Name** and **Description** property fields.</span></span>  
  
 <span data-ttu-id="2dd9a-133">**Nome**</span><span class="sxs-lookup"><span data-stu-id="2dd9a-133">**Name**</span></span>  
 <span data-ttu-id="2dd9a-134">Visualizza il nome dell'indice XML.</span><span class="sxs-lookup"><span data-stu-id="2dd9a-134">Shows the name of the XML index.</span></span> <span data-ttu-id="2dd9a-135">Quando si crea un nuovo indice, gli viene assegnato un nome predefinito sulla base della tabella presente nella finestra attiva di Progettazione tabelle.</span><span class="sxs-lookup"><span data-stu-id="2dd9a-135">When a new one is created, it is given a default name based on the table in the active window in Table Designer.</span></span> <span data-ttu-id="2dd9a-136">È possibile modificare il nome in qualsiasi momento.</span><span class="sxs-lookup"><span data-stu-id="2dd9a-136">You can change the name at any time.</span></span>  
  
 <span data-ttu-id="2dd9a-137">**Descrizione**</span><span class="sxs-lookup"><span data-stu-id="2dd9a-137">**Description**</span></span>  
 <span data-ttu-id="2dd9a-138">Consente di descrivere l'indice.</span><span class="sxs-lookup"><span data-stu-id="2dd9a-138">Describe the index.</span></span> <span data-ttu-id="2dd9a-139">Per inserire una descrizione più dettagliata, fare clic su **Descrizione** e sui puntini di sospensione ( **...** ) a destra del campo della proprietà.</span><span class="sxs-lookup"><span data-stu-id="2dd9a-139">To write a more detailed description, click **Description** and then click the ellipsis button (**...**) that appears to the right of the property field.</span></span> <span data-ttu-id="2dd9a-140">Viene così visualizzata un'area più grande in cui scrivere il testo.</span><span class="sxs-lookup"><span data-stu-id="2dd9a-140">This provides a larger area in which to write text.</span></span>  
  
 <span data-ttu-id="2dd9a-141">**Categoria Progettazione tabelle**</span><span class="sxs-lookup"><span data-stu-id="2dd9a-141">**Table Designer Category**</span></span>  
 <span data-ttu-id="2dd9a-142">Se viene espansa, visualizza le informazioni relative alle proprietà dell'indice XML.</span><span class="sxs-lookup"><span data-stu-id="2dd9a-142">When expanded, shows information about the properties of this XML index.</span></span>  
  
 <span data-ttu-id="2dd9a-143">**Specifica riempimento**</span><span class="sxs-lookup"><span data-stu-id="2dd9a-143">**Fill Specification**</span></span>  
 <span data-ttu-id="2dd9a-144">Se viene espansa, visualizza le informazioni relative a **Riempimento** e **Riempi indice**.</span><span class="sxs-lookup"><span data-stu-id="2dd9a-144">When expanded, shows information for **Fill Factor** and **Pad Index**.</span></span>  
  
 <span data-ttu-id="2dd9a-145">**Riempimento**</span><span class="sxs-lookup"><span data-stu-id="2dd9a-145">**Fill Factor**</span></span>  
 <span data-ttu-id="2dd9a-146">Specifica quale percentuale della pagina dell'indice può essere riempita dal sistema.</span><span class="sxs-lookup"><span data-stu-id="2dd9a-146">Specify what percentage of the index page the system can fill.</span></span> <span data-ttu-id="2dd9a-147">Quando la pagina è piena, dovrà essere divisa se verranno aggiunti nuovi dati, con un conseguente rallentamento delle prestazioni.</span><span class="sxs-lookup"><span data-stu-id="2dd9a-147">Once a page is full, the system must split the page if new data is added, which impairs performance.</span></span>  
  
-   <span data-ttu-id="2dd9a-148">Un valore pari a 100 indica che le pagine saranno piene. Tale impostazione richiede la quantità più ridotta di spazio di archiviazione ma è la meno efficiente.</span><span class="sxs-lookup"><span data-stu-id="2dd9a-148">A value of 100 means the pages will be full; this requires the least amount of storage space but is the least efficient.</span></span> <span data-ttu-id="2dd9a-149">È consigliabile utilizzare questa impostazione solo se non verranno apportate modifiche ai dati, ad esempio per una tabella di sola lettura.</span><span class="sxs-lookup"><span data-stu-id="2dd9a-149">This setting should be used only when there will be no changes to the data, for example, on a read-only table.</span></span>  
  
-   <span data-ttu-id="2dd9a-150">Un valore inferiore lascia più spazio nelle pagine di dati e quindi riduce la necessità di suddividerle all'aumentare delle dimensioni degli indici,</span><span class="sxs-lookup"><span data-stu-id="2dd9a-150">A lower value leaves more empty space on the data pages, which reduces the need to split data pages as indexes grow.</span></span> <span data-ttu-id="2dd9a-151">ma richiede uno spazio di archiviazione maggiore.</span><span class="sxs-lookup"><span data-stu-id="2dd9a-151">However, it requires more storage space.</span></span> <span data-ttu-id="2dd9a-152">Questa impostazione è consigliabile se si prevede che i dati della tabella saranno soggetti a modifiche.</span><span class="sxs-lookup"><span data-stu-id="2dd9a-152">This setting is more appropriate when there will be changes to the data in the table.</span></span>  
  
 <span data-ttu-id="2dd9a-153">**Riempi indice**</span><span class="sxs-lookup"><span data-stu-id="2dd9a-153">**Pad Index**</span></span>  
 <span data-ttu-id="2dd9a-154">Offre alle pagine di questo indice la stessa percentuale di spazio vuoto (riempimento) specificata in **Riempimento**.</span><span class="sxs-lookup"><span data-stu-id="2dd9a-154">Provide pages in this index the same percentage of empty space (padding) that is specified in **Fill Factor**.</span></span>  
  
 <span data-ttu-id="2dd9a-155">**Disabilitato**</span><span class="sxs-lookup"><span data-stu-id="2dd9a-155">**Is Disabled**</span></span>  
 <span data-ttu-id="2dd9a-156">Specifica se l'indice è disabilitato.</span><span class="sxs-lookup"><span data-stu-id="2dd9a-156">Specify whether this index is disabled.</span></span> <span data-ttu-id="2dd9a-157">Gli indici disabilitati non consentono l'esecuzione di ricerche, né vengono aggiornati quando si aggiungono nuovi elementi alla tabella.</span><span class="sxs-lookup"><span data-stu-id="2dd9a-157">Disabled indexes do not support searches, nor do they get updated when new items are added to the table.</span></span> <span data-ttu-id="2dd9a-158">Disabilitando un indice è possibile migliorare le prestazioni in caso di operazioni di inserimento e aggiornamento bulk.</span><span class="sxs-lookup"><span data-stu-id="2dd9a-158">You can improve performance for bulk inserts and updates by disabling an index.</span></span>  
  
 <span data-ttu-id="2dd9a-159">**Blocchi pagine consentiti**</span><span class="sxs-lookup"><span data-stu-id="2dd9a-159">**Page Locks Allowed**</span></span>  
 <span data-ttu-id="2dd9a-160">Specifica se per l'indice è consentito il blocco a livello delle pagine.</span><span class="sxs-lookup"><span data-stu-id="2dd9a-160">Specify whether page-level locking is allowed on this index.</span></span> <span data-ttu-id="2dd9a-161">L'attivazione o la disattivazione di tale blocco incide sulle prestazioni del database.</span><span class="sxs-lookup"><span data-stu-id="2dd9a-161">Allowing or disallowing page-level locking affects database performance.</span></span>  
  
 <span data-ttu-id="2dd9a-162">**Ricalcola statistiche**</span><span class="sxs-lookup"><span data-stu-id="2dd9a-162">**Re-compute Statistics**</span></span>  
 <span data-ttu-id="2dd9a-163">Consente di calcolare nuove statistiche quando viene creato l'indice.</span><span class="sxs-lookup"><span data-stu-id="2dd9a-163">Compute new statistics when the index is created.</span></span> <span data-ttu-id="2dd9a-164">Il ricalcolo delle statistiche rallenta la compilazione degli indici, ma in genere consente di migliorare le prestazioni delle query.</span><span class="sxs-lookup"><span data-stu-id="2dd9a-164">Re-computing statistics slows the building of indexes but usually improves query performance.</span></span>  
  
 <span data-ttu-id="2dd9a-165">**Blocchi righe consentiti**</span><span class="sxs-lookup"><span data-stu-id="2dd9a-165">**Row Locks Allowed**</span></span>  
 <span data-ttu-id="2dd9a-166">Specifica se per l'indice è consentito il blocco a livello delle righe.</span><span class="sxs-lookup"><span data-stu-id="2dd9a-166">Specify whether row-level locking is allowed on this index.</span></span> <span data-ttu-id="2dd9a-167">L'attivazione o la disattivazione di tale blocco incide sulle prestazioni del database.</span><span class="sxs-lookup"><span data-stu-id="2dd9a-167">Allowing or disallowing row-level locking affects database performance.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2dd9a-168">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="2dd9a-168">See Also</span></span>  
 [<span data-ttu-id="2dd9a-169">Creazione di indici XML</span><span class="sxs-lookup"><span data-stu-id="2dd9a-169">Create XML Indexes</span></span>](../../relational-databases/xml/create-xml-indexes.md)  
  
  
