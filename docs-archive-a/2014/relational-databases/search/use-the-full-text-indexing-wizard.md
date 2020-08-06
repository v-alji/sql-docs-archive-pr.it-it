---
title: Usare l'Indicizzazione guidata full-text | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: search
ms.topic: conceptual
f1_keywords:
- sql12.swb.fulltextindexingwizard.selecttablecolumns.f1
- sql12.swb.fulltextindexingwizard.welcome.f1
- sql12.swb.fulltextindexingwizard.selectacatalog.f1
- sql12.swb.fulltextindexingwizard.progress.f1
- sql12.swb.fulltextindexingwizard.selectorcreatepopschedules.f1
- sql12.swb.fulltextindexingwizard.selectatableorview.f1
- sql12.swb.fulltextindexingwizard.selectchangetracking.f1
- sql12.swb.fulltextindexingwizard.selectanindex.f1
- sql12.swb.fulltextindexingwizard.summary.f1
helpviewer_keywords:
- Full-Text Indexing Wizard
- full-text search [SQL Server], Full-Text Indexing Wizard
ms.assetid: 3e9d9605-6525-4781-9168-fdaa06db3459
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 5ef8a23c4d85cbe47bf6bdb47eb3f45723f1559d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87714100"
---
# <a name="use-the-full-text-indexing-wizard"></a><span data-ttu-id="46df2-102">Utilizzare l'Indicizzazione guidata full-text</span><span class="sxs-lookup"><span data-stu-id="46df2-102">Use the Full-Text Indexing Wizard</span></span>
  <span data-ttu-id="46df2-103">L'Indicizzazione guidata full-text ha lo scopo di semplificare la procedura di creazione di un indice full-text.</span><span class="sxs-lookup"><span data-stu-id="46df2-103">The Full-Text Indexing Wizard walks you through a series of steps designed to help you create a full-text index.</span></span>  
  
#### <a name="to-use-the-full-text-indexing-wizard"></a><span data-ttu-id="46df2-104">Per utilizzare l'Indicizzazione guidata full-text</span><span class="sxs-lookup"><span data-stu-id="46df2-104">To use the Full-Text Indexing wizard</span></span>  
  
1.  <span data-ttu-id="46df2-105">In Esplora oggetti fare clic con il pulsante destro del mouse sulla tabella nella quale si desidera creare un indice full-text, scegliere **Indice full-text**, quindi fare clic su **Definisci indice full-text**.</span><span class="sxs-lookup"><span data-stu-id="46df2-105">In Object Explorer, right-click the table on which you want to create a full-text index, point to **Full-Text index**, and then click **Define Full-Text Index**.</span></span>  
  
     <span data-ttu-id="46df2-106">**Indice univoco**</span><span class="sxs-lookup"><span data-stu-id="46df2-106">**Unique Index**</span></span>  
     <span data-ttu-id="46df2-107">Selezionare un indice dall'elenco a discesa.</span><span class="sxs-lookup"><span data-stu-id="46df2-107">Select an index from the drop down list.</span></span> <span data-ttu-id="46df2-108">L'indice deve essere univoco, a colonna singola, che non ammette valori Null.</span><span class="sxs-lookup"><span data-stu-id="46df2-108">The index must be a single-key-column, unique, non-nullable index.</span></span> <span data-ttu-id="46df2-109">Selezionare l'indice di chiave univoca più piccolo possibile per la chiave univoca full-text.</span><span class="sxs-lookup"><span data-stu-id="46df2-109">Select the smallest unique key index for the full-text unique key.</span></span> <span data-ttu-id="46df2-110">Per prestazioni ottimali, utilizzare un indice cluster.</span><span class="sxs-lookup"><span data-stu-id="46df2-110">For best performance, a clustered index is recommended.</span></span>  
  
     <span data-ttu-id="46df2-111">**Colonne disponibili**</span><span class="sxs-lookup"><span data-stu-id="46df2-111">**Available Columns**</span></span>  
     <span data-ttu-id="46df2-112">Per includere una colonna nell'indice, selezionare la casella di controllo accanto al nome della colonna.</span><span class="sxs-lookup"><span data-stu-id="46df2-112">To include a column in the index, select the check box next to the column name.</span></span> <span data-ttu-id="46df2-113">Le colonne non idonee per l'indicizzazione full-text vengono visualizzate in grigio con le relative caselle di controllo disabilitate.</span><span class="sxs-lookup"><span data-stu-id="46df2-113">Columns that are not eligible for full-text indexing appear in grey with their check boxes disabled.</span></span>  
  
     <span data-ttu-id="46df2-114">**Lingua per il Word breaker**</span><span class="sxs-lookup"><span data-stu-id="46df2-114">**Language for Word Breaker**</span></span>  
     <span data-ttu-id="46df2-115">Consente di selezionare una lingua nell'elenco a discesa.</span><span class="sxs-lookup"><span data-stu-id="46df2-115">Select a language from the drop-down list.</span></span> <span data-ttu-id="46df2-116">La selezione effettuata verrà utilizzata da [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] per identificare i word breaker corretti per l'indice.</span><span class="sxs-lookup"><span data-stu-id="46df2-116">This choice will be used by [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] to identify the correct word breakers for the index.</span></span> [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="46df2-117">usa i word breaker per individuare i delimitatori delle parole nei dati con indicizzazione full-text.</span><span class="sxs-lookup"><span data-stu-id="46df2-117">uses word breakers to identify word boundaries in the full-text indexed data.</span></span>  
  
     <span data-ttu-id="46df2-118">**Digitare una colonna**</span><span class="sxs-lookup"><span data-stu-id="46df2-118">**Type Column**</span></span>  
     <span data-ttu-id="46df2-119">Consente di selezionare il nome della colonna che contiene il tipo di documento della colonna sottoposta all'indicizzazione full-text.</span><span class="sxs-lookup"><span data-stu-id="46df2-119">Select the name of the column that holds the document type of column being full-text indexed.</span></span>  
  
     <span data-ttu-id="46df2-120">La **colonna tipo** è abilitata solo se la colonna specificata nella colonna **colonne disponibili** è di tipo `varbinary(max)` o `image` .</span><span class="sxs-lookup"><span data-stu-id="46df2-120">The  **Type Column** is only enabled when the column named in the **Available Columns** column is of type `varbinary(max)` or `image`.</span></span>  
  
     <span data-ttu-id="46df2-121">**Semantica statistica**</span><span class="sxs-lookup"><span data-stu-id="46df2-121">**Statistical Semantics**</span></span>  
     <span data-ttu-id="46df2-122">Consente di selezionare se abilitare l'indicizzazione semantica per la colonna selezionata.</span><span class="sxs-lookup"><span data-stu-id="46df2-122">Select whether to enable semantic indexing for the selected column.</span></span> <span data-ttu-id="46df2-123">Per altre informazioni, vedere [Ricerca semantica &#40;SQL Server&#41;](semantic-search-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="46df2-123">For more information, see [Semantic Search &#40;SQL Server&#41;](semantic-search-sql-server.md).</span></span>  
  
     <span data-ttu-id="46df2-124">Se si seleziona una lingua in **Lingua** prima di selezionare **Semantica statistica**e alla lingua selezionata non è associato alcun modello di lingua semantico, la casella di controllo **Semantica statistica** è disabilitata.</span><span class="sxs-lookup"><span data-stu-id="46df2-124">If you select a **Language** prior to selecting **Statistical Semantics**, and the selected language does not have an associated Semantic Language Model, then the **Statistical Semantics** checkbox is disabled.</span></span> <span data-ttu-id="46df2-125">Se si seleziona **Semantica statistica** prima di selezionare una lingua in **Lingua**, le lingue disponibili nella casella combinata a discesa saranno limitate a quelle per cui è disponibile un modello di lingua semantico.</span><span class="sxs-lookup"><span data-stu-id="46df2-125">If you select **Statistical Semantics** prior to selecting a **Language**, the languages available in the drop-down combo box will be restricted to those for which there is Semantic Language Model support.</span></span>  
  
2.  <span data-ttu-id="46df2-126">Selezionare le opzioni di rilevamento delle modifiche.</span><span class="sxs-lookup"><span data-stu-id="46df2-126">Select the change tracking options.</span></span>  
  
     <span data-ttu-id="46df2-127">**Automatico**</span><span class="sxs-lookup"><span data-stu-id="46df2-127">**Automatically**</span></span>  
     <span data-ttu-id="46df2-128">Selezionare questo pulsante di opzione per aggiornare automaticamente l'indice full-text a mano a mano che le modifiche vengono apportate ai dati sottostanti.</span><span class="sxs-lookup"><span data-stu-id="46df2-128">Select this radio button to have the full-text index updated automatically as changes occur to the underlying data.</span></span>  
  
     <span data-ttu-id="46df2-129">**Operazione manuale**</span><span class="sxs-lookup"><span data-stu-id="46df2-129">**Manually**</span></span>  
     <span data-ttu-id="46df2-130">Selezionare questo pulsante di opzione se non si desidera che l'indice full-text venga aggiornato automaticamente a mano a mano che le modifiche vengono apportate ai dati sottostanti.</span><span class="sxs-lookup"><span data-stu-id="46df2-130">Select this radio button if you do not want the full-text index to be updated automatically as changes occur to the underlying data.</span></span> <span data-ttu-id="46df2-131">Le modifiche apportate ai dati sottostanti vengono mantenute.</span><span class="sxs-lookup"><span data-stu-id="46df2-131">Changes to the underlying data are maintained.</span></span> <span data-ttu-id="46df2-132">Tuttavia, per applicare le modifiche all'indice full-text è necessario avviare o pianificare il processo in modo manuale.</span><span class="sxs-lookup"><span data-stu-id="46df2-132">However, to apply the changes to the full-text index you must start or schedule this process manually.</span></span>  
  
     <span data-ttu-id="46df2-133">**Non rilevare modifiche**</span><span class="sxs-lookup"><span data-stu-id="46df2-133">**Do not track changes**</span></span>  
     <span data-ttu-id="46df2-134">Selezionare questo pulsante di opzione se non si desidera che l'indice full-text venga aggiornato con le modifiche apportate ai dati sottostanti.</span><span class="sxs-lookup"><span data-stu-id="46df2-134">Select this radio button if you do not want the full-text index to be updated with changes to the underlying data.</span></span>  
  
     <span data-ttu-id="46df2-135">**Avvia popolamento completo quando viene creato l'indice**</span><span class="sxs-lookup"><span data-stu-id="46df2-135">**Start full population when index is created**</span></span>  
     <span data-ttu-id="46df2-136">Selezionare questo pulsante di opzione per avviare il popolamento completo dopo il completamento della procedura guidata.</span><span class="sxs-lookup"><span data-stu-id="46df2-136">Select this radio button to kick off a full population at the successful completion of this wizard.</span></span> <span data-ttu-id="46df2-137">Ciò comporterà la creazione della struttura dell'indice full-text nel catalogo e il suo popolamento con dati con indicizzazione full-text.</span><span class="sxs-lookup"><span data-stu-id="46df2-137">This will consist of creating the full-text index structure in the catalog and populating it with full-text indexed data.</span></span>  
  
3.  <span data-ttu-id="46df2-138">Selezionare il catalogo, il filegroup indice e l'elenco di parole non significative.</span><span class="sxs-lookup"><span data-stu-id="46df2-138">Select the catalog, index filegroup and stoplist.</span></span>  
  
     <span data-ttu-id="46df2-139">**Seleziona catalogo full-text**</span><span class="sxs-lookup"><span data-stu-id="46df2-139">**Select full-text catalog**</span></span>  
     <span data-ttu-id="46df2-140">Consente di selezionare un catalogo full-text dall'elenco.</span><span class="sxs-lookup"><span data-stu-id="46df2-140">Select a full-text catalog from the list.</span></span> <span data-ttu-id="46df2-141">Il catalogo predefinito del database corrisponderà all'elemento selezionato per impostazione predefinita nell'elenco.</span><span class="sxs-lookup"><span data-stu-id="46df2-141">The default catalog for the database will be the selected item by default in the list.</span></span> <span data-ttu-id="46df2-142">Se non è disponibile alcun catalogo, l'elenco sarà disabilitato e la casella di controllo **Crea un nuovo catalogo** sarà selezionata e disabilitata.</span><span class="sxs-lookup"><span data-stu-id="46df2-142">If no catalogs are available, the list will be disabled, and the **Create a new catalog** checkbox will be checked and disabled.</span></span>  
  
    |||  
    |-|-|  
    |<span data-ttu-id="46df2-143">**Crea un nuovo catalogo**</span><span class="sxs-lookup"><span data-stu-id="46df2-143">**Create a new catalog**</span></span>|<span data-ttu-id="46df2-144">Selezionare questa casella di controllo per creare un nuovo catalogo full-text.</span><span class="sxs-lookup"><span data-stu-id="46df2-144">Select to create a new full-text catalog.</span></span>|  
  
     <span data-ttu-id="46df2-145">**Nome**</span><span class="sxs-lookup"><span data-stu-id="46df2-145">**Name**</span></span>  
     <span data-ttu-id="46df2-146">Immettere un nome per il nuovo catalogo full-text.</span><span class="sxs-lookup"><span data-stu-id="46df2-146">Enter a name for the new full-text catalog.</span></span>  
  
     <span data-ttu-id="46df2-147">**Imposta come catalogo predefinito**</span><span class="sxs-lookup"><span data-stu-id="46df2-147">**Set as default catalog**</span></span>  
     <span data-ttu-id="46df2-148">Selezionare questa opzione per impostare il catalogo come predefinito per il database.</span><span class="sxs-lookup"><span data-stu-id="46df2-148">Select to make the catalog the default for this database.</span></span>  
  
     <span data-ttu-id="46df2-149">**Distinzione caratteri accentati/non accentati**</span><span class="sxs-lookup"><span data-stu-id="46df2-149">**Accent sensitivity**</span></span>  
     <span data-ttu-id="46df2-150">Consente di specificare se nel catalogo viene fatta distinzione tra caratteri accentati e non accentati.</span><span class="sxs-lookup"><span data-stu-id="46df2-150">Specify whether the new catalog will be accent-sensitive or accent-insensitive.</span></span> <span data-ttu-id="46df2-151">Se il database supporta la distinzione tra caratteri accentati e non accentati, l'opzione **Attiva** sarà selezionata per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="46df2-151">If the database is accent-sensitive, **Sensitive** will be selected by default.</span></span>  
  
     <span data-ttu-id="46df2-152">**Selezione filegroup indice**</span><span class="sxs-lookup"><span data-stu-id="46df2-152">**Select index filegroup**</span></span>  
     <span data-ttu-id="46df2-153">Consente di specificare il filegroup in cui creare l'indice full-text.</span><span class="sxs-lookup"><span data-stu-id="46df2-153">Specify the filegroup on which to create the full-text index.</span></span>  
  
     <span data-ttu-id="46df2-154">Selezionare uno dei valori seguenti:</span><span class="sxs-lookup"><span data-stu-id="46df2-154">Select one of the following values:</span></span>  
  
    |<span data-ttu-id="46df2-155">Valore</span><span class="sxs-lookup"><span data-stu-id="46df2-155">Value</span></span>|<span data-ttu-id="46df2-156">Descrizione</span><span class="sxs-lookup"><span data-stu-id="46df2-156">Description</span></span>|  
    |-----------|-----------------|  
    |**\<default>**|<span data-ttu-id="46df2-157">Se la tabella o la vista non è partizionata, selezionare questa opzione per utilizzare lo stesso filegroup della tabella o della vista sottostante.</span><span class="sxs-lookup"><span data-stu-id="46df2-157">If the table or view is not partitioned, select to use the same filegroup as the underlying table or view.</span></span> <span data-ttu-id="46df2-158">Se la tabella o vista è partizionata, viene utilizzato il filegroup primario.</span><span class="sxs-lookup"><span data-stu-id="46df2-158">If the table or view is partitioned, the primary filegroup is used.</span></span>|  
    |<span data-ttu-id="46df2-159">**PRIMARY**</span><span class="sxs-lookup"><span data-stu-id="46df2-159">**PRIMARY**</span></span>|<span data-ttu-id="46df2-160">Selezionare questa opzione per utilizzare il filegroup primario per il nuovo indice full-text.</span><span class="sxs-lookup"><span data-stu-id="46df2-160">Select to use the primary filegroup for the new full-text index.</span></span>|  
    |<span data-ttu-id="46df2-161">*user-specified default filegroup*</span><span class="sxs-lookup"><span data-stu-id="46df2-161">*user-specified default filegroup*</span></span>|<span data-ttu-id="46df2-162">Se è presente un elenco di parole non significative predefinito definito dall'utente, selezionarne il nome nell'elenco per utilizzare tale filegroup per il nuovo indice full-text.</span><span class="sxs-lookup"><span data-stu-id="46df2-162">If a user-defined default stoplist exists, select its name from the list to use that filegroup for the new full-text index.</span></span>|  
  
     <span data-ttu-id="46df2-163">**Selezione elenco di parole non significative full-text**</span><span class="sxs-lookup"><span data-stu-id="46df2-163">**Select full-text stoplist**</span></span>  
     <span data-ttu-id="46df2-164">Consente di specificare un elenco di parole non significative da utilizzare per l'indice full-text o di disabilitare l'utilizzo dell'elenco di parole non significative.</span><span class="sxs-lookup"><span data-stu-id="46df2-164">Specify a stoplist to use for the full-text index, or disable stoplist use.</span></span>  
  
     <span data-ttu-id="46df2-165">In [!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)] e versioni successive le parole non significative vengono gestite nei database tramite oggetti denominati elenchi di parole non significative.</span><span class="sxs-lookup"><span data-stu-id="46df2-165">In [!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)] and later versions, stopwords are managed in databases using objects called stoplists.</span></span> <span data-ttu-id="46df2-166">Un *elenco di parole non significative* è un elenco che, quando associato a un indice full-text, viene applicato alle query full-text su tale indice.</span><span class="sxs-lookup"><span data-stu-id="46df2-166">A *stoplist* is a list of stopwords that, when associated with a full-text index, is applied to full-text queries on that index.</span></span> <span data-ttu-id="46df2-167">Per altre informazioni, vedere [Configurare e gestire parole non significative ed elenchi di parole non significative per la ricerca full-text](configure-and-manage-stopwords-and-stoplists-for-full-text-search.md).</span><span class="sxs-lookup"><span data-stu-id="46df2-167">For more information, see [Configure and Manage Stopwords and Stoplists for Full-Text Search](configure-and-manage-stopwords-and-stoplists-for-full-text-search.md).</span></span>  
  
     <span data-ttu-id="46df2-168">Selezionare uno dei valori seguenti:</span><span class="sxs-lookup"><span data-stu-id="46df2-168">Select one of the following values:</span></span>  
  
    |<span data-ttu-id="46df2-169">Valore</span><span class="sxs-lookup"><span data-stu-id="46df2-169">Value</span></span>|<span data-ttu-id="46df2-170">Descrizione</span><span class="sxs-lookup"><span data-stu-id="46df2-170">Description</span></span>|  
    |-----------|-----------------|  
    |**\<system>**|<span data-ttu-id="46df2-171">Selezionare questa opzione per utilizzare l'elenco di parole non significative di sistema nel nuovo indice full-text.</span><span class="sxs-lookup"><span data-stu-id="46df2-171">Select to use the system stoplist on the new full-text index.</span></span> <span data-ttu-id="46df2-172">Si tratta dell'impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="46df2-172">This is the default</span></span>|  
    |**\<off>**|<span data-ttu-id="46df2-173">Selezionare questa opzione per disabilitare gli elenchi di parole non significative per il nuovo indice full-text.</span><span class="sxs-lookup"><span data-stu-id="46df2-173">Select to disable stoplists for the new full-text index.</span></span>|  
    |<span data-ttu-id="46df2-174">*user-defined-stoplist-name*</span><span class="sxs-lookup"><span data-stu-id="46df2-174">*user-defined-stoplist-name*</span></span>|<span data-ttu-id="46df2-175">Nell'elenco viene visualizzato il nome di ogni elenco di parole non significative definito dall'utente, se presente, creato nel database.</span><span class="sxs-lookup"><span data-stu-id="46df2-175">The list displays the name of each user-defined stoplist, if any, that has been created on the database.</span></span> <span data-ttu-id="46df2-176">Selezionare qualsiasi elenco di parole non significative definito dall'utente da utilizzare per il nuovo indice full-text.</span><span class="sxs-lookup"><span data-stu-id="46df2-176">Select any user-defined stoplist to use for the new full-text index.</span></span>|  
  
4.  <span data-ttu-id="46df2-177">Facoltativamente, definire la pianificazione di popolamento.</span><span class="sxs-lookup"><span data-stu-id="46df2-177">Optionally, define the population schedule.</span></span> <span data-ttu-id="46df2-178">Le operazioni di indicizzazione avranno inizio immediatamente, a meno che non siano state pianificate per un'esecuzione futura.</span><span class="sxs-lookup"><span data-stu-id="46df2-178">Indexing operations will begin immediately unless they have been scheduled for future execution.</span></span> <span data-ttu-id="46df2-179">Le pianificazioni verranno create immediatamente, anche se l'esecuzione avverrà solo all'ora pianificata.</span><span class="sxs-lookup"><span data-stu-id="46df2-179">Schedules will be created immediately, although they will not run until their scheduled time.</span></span>  
  
     <span data-ttu-id="46df2-180">**Nuova pianificazione tabella**</span><span class="sxs-lookup"><span data-stu-id="46df2-180">**New Table Schedule**</span></span>  
     <span data-ttu-id="46df2-181">Consente di definire una pianificazione di popolamento per una tabella.</span><span class="sxs-lookup"><span data-stu-id="46df2-181">Define a population schedule for a table.</span></span>  
  
     <span data-ttu-id="46df2-182">**Nuova pianificazione catalogo**</span><span class="sxs-lookup"><span data-stu-id="46df2-182">**New Catalog Schedule**</span></span>  
     <span data-ttu-id="46df2-183">Consente di definire una pianificazione di popolamento per un catalogo full-text.</span><span class="sxs-lookup"><span data-stu-id="46df2-183">Define a population schedule for a full-text catalog.</span></span>  
  
     <span data-ttu-id="46df2-184">**Modifica**</span><span class="sxs-lookup"><span data-stu-id="46df2-184">**Edit**</span></span>  
     <span data-ttu-id="46df2-185">Consente di modificare una pianificazione.</span><span class="sxs-lookup"><span data-stu-id="46df2-185">Edit a schedule.</span></span>  
  
     <span data-ttu-id="46df2-186">**Elimina**</span><span class="sxs-lookup"><span data-stu-id="46df2-186">**Delete**</span></span>  
     <span data-ttu-id="46df2-187">Consente di eliminare una pianificazione.</span><span class="sxs-lookup"><span data-stu-id="46df2-187">Delete a schedule.</span></span>  
  
5.  <span data-ttu-id="46df2-188">Visualizzare o controllare lo stato dell'Indicizzazione guidata full-text.</span><span class="sxs-lookup"><span data-stu-id="46df2-188">View or control the progress of the Full-Text Indexing Wizard.</span></span>  
  
     <span data-ttu-id="46df2-189">**Stop**</span><span class="sxs-lookup"><span data-stu-id="46df2-189">**Stop**</span></span>  
     <span data-ttu-id="46df2-190">Consente di interrompere l'operazione corrente e impedire l'esecuzione di operazioni full-text successive da parte della procedura guidata nel corso della sessione.</span><span class="sxs-lookup"><span data-stu-id="46df2-190">Interrupts the current operation and prevents subsequent full-text operations from being performed by the wizard during this session.</span></span>  
  
     <span data-ttu-id="46df2-191">**Report**</span><span class="sxs-lookup"><span data-stu-id="46df2-191">**Report**</span></span>  
     <span data-ttu-id="46df2-192">Al termine dell'esecuzione di tutte le operazioni, fare clic su questo pulsante per accedere a un report delle operazioni eseguite.</span><span class="sxs-lookup"><span data-stu-id="46df2-192">When all of the operations have finished executing, click this button to access a report on the operations performed.</span></span> <span data-ttu-id="46df2-193">È possibile visualizzare il report, stamparlo su file, copiarlo negli Appunti o inviarlo tramite posta elettronica.</span><span class="sxs-lookup"><span data-stu-id="46df2-193">You can view the report, print it to a file, copy it to the clipboard, or e-mail the report.</span></span>  
  
  
