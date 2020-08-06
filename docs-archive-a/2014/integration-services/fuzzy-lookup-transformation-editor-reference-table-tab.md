---
title: Editor trasformazione Ricerca fuzzy (scheda tabella di riferimento) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.fuzzylookuptransformation.referencetable.f1
helpviewer_keywords:
- Fuzzy Lookup Transformation Editor
ms.assetid: 451f4e7d-1c8e-4784-b540-df0806509bf1
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 9ce51dd64c9c5807ab23ac645694cfec29a36d52
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87624836"
---
# <a name="fuzzy-lookup-transformation-editor-reference-table-tab"></a><span data-ttu-id="e93ae-102">Editor trasformazione Ricerca fuzzy (scheda Tabella di riferimento)</span><span class="sxs-lookup"><span data-stu-id="e93ae-102">Fuzzy Lookup Transformation Editor (Reference Table Tab)</span></span>
  <span data-ttu-id="e93ae-103">Usare la scheda **Tabella di riferimento** della finestra di dialogo **Editor trasformazione Ricerca fuzzy** per specificare la tabella di origine e l'indice da usare per la ricerca.</span><span class="sxs-lookup"><span data-stu-id="e93ae-103">Use the **Reference Table** tab of the **Fuzzy Lookup Transformation Editor** dialog box to specify the source table and the index to use for the lookup.</span></span> <span data-ttu-id="e93ae-104">Tale origine deve essere una tabella di un database di [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="e93ae-104">The reference data source must be a table in a [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] database.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="e93ae-105">La trasformazione Ricerca fuzzy crea una copia di lavoro della tabella di riferimento.</span><span class="sxs-lookup"><span data-stu-id="e93ae-105">The Fuzzy Lookup transformation creates a working copy of the reference table.</span></span> <span data-ttu-id="e93ae-106">Gli indici descritti di seguito vengono creati su tale tabella di lavoro usando una tabella speciale invece di un normale indice [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="e93ae-106">The indexes described below are created on this working table by using a special table, not an ordinary [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] index.</span></span> <span data-ttu-id="e93ae-107">La trasformazione non modifica le tabelle di origine esistenti, a meno che non sia stata selezionata l'opzione **Manutenzione indice archiviato**.</span><span class="sxs-lookup"><span data-stu-id="e93ae-107">The transformation does not modify the existing source tables unless you select **Maintain stored index**.</span></span> <span data-ttu-id="e93ae-108">In questo caso viene creato un trigger sulla tabella di riferimento che aggiorna la tabella di lavoro e la tabella dell'indice di ricerca in base alle modifiche apportate alla tabella di riferimento.</span><span class="sxs-lookup"><span data-stu-id="e93ae-108">In this case, it creates a trigger on the reference table that updates the working table and the lookup index table based on changes to the reference table.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="e93ae-109">Le `Exhaustive` proprietà e `MaxMemoryUsage` della trasformazione Ricerca fuzzy non sono disponibili nell' **Editor trasformazione Ricerca fuzzy**, ma possono essere impostate tramite il **Editor avanzato**.</span><span class="sxs-lookup"><span data-stu-id="e93ae-109">The `Exhaustive` and the `MaxMemoryUsage` properties of the Fuzzy Lookup transformation are not available in the **Fuzzy Lookup Transformation Editor**, but can be set by using the **Advanced Editor**.</span></span> <span data-ttu-id="e93ae-110">Inoltre, è possibile specificare un valore maggiore di 100 per `MaxOutputMatchesPerInput` solo nell' **Editor avanzato**.</span><span class="sxs-lookup"><span data-stu-id="e93ae-110">In addition, a value greater than 100 for `MaxOutputMatchesPerInput` can be specified only in the **Advanced Editor**.</span></span> <span data-ttu-id="e93ae-111">Per altre informazioni su queste proprietà, vedere la sezione relativa alla trasformazione Ricerca fuzzy in [Proprietà personalizzate delle trasformazioni](data-flow/transformations/transformation-custom-properties.md).</span><span class="sxs-lookup"><span data-stu-id="e93ae-111">For more information on these properties, see the Fuzzy Lookup Transformation section of [Transformation Custom Properties](data-flow/transformations/transformation-custom-properties.md).</span></span>  
  
 <span data-ttu-id="e93ae-112">Per ulteriori informazioni sulla trasformazione Ricerca fuzzy, vedere [Fuzzy Lookup Transformation](data-flow/transformations/lookup-transformation.md).</span><span class="sxs-lookup"><span data-stu-id="e93ae-112">To learn more about the Fuzzy Lookup transformation, see [Fuzzy Lookup Transformation](data-flow/transformations/lookup-transformation.md).</span></span>  
  
## <a name="options"></a><span data-ttu-id="e93ae-113">Opzioni</span><span class="sxs-lookup"><span data-stu-id="e93ae-113">Options</span></span>  
 <span data-ttu-id="e93ae-114">**Gestione connessione OLE DB**</span><span class="sxs-lookup"><span data-stu-id="e93ae-114">**OLE DB connection manager**</span></span>  
 <span data-ttu-id="e93ae-115">Selezionare una gestione connessione OLE DB esistente nell'elenco o fare clic su **Nuova**per creare una nuova connessione.</span><span class="sxs-lookup"><span data-stu-id="e93ae-115">Select an existing OLE DB connection manager from the list, or create a new connection by clicking **New**.</span></span>  
  
 <span data-ttu-id="e93ae-116">**Nuovo**</span><span class="sxs-lookup"><span data-stu-id="e93ae-116">**New**</span></span>  
 <span data-ttu-id="e93ae-117">Consente di creare una nuova connessione usando la finestra di dialogo **Configura gestione connessione OLE DB** .</span><span class="sxs-lookup"><span data-stu-id="e93ae-117">Create a new connection by using the **Configure OLE DB Connection Manager** dialog box.</span></span>  
  
 <span data-ttu-id="e93ae-118">**Genera nuovo indice**</span><span class="sxs-lookup"><span data-stu-id="e93ae-118">**Generate new index**</span></span>  
 <span data-ttu-id="e93ae-119">Consente di specificare che la trasformazione deve creare un nuovo indice da utilizzare per la ricerca.</span><span class="sxs-lookup"><span data-stu-id="e93ae-119">Specify that the transformation should create a new index to use for the lookup.</span></span>  
  
 <span data-ttu-id="e93ae-120">**Nome tabella di riferimento**</span><span class="sxs-lookup"><span data-stu-id="e93ae-120">**Reference table name**</span></span>  
 <span data-ttu-id="e93ae-121">Consente di selezionare la tabella esistente da utilizzare come tabella di riferimento, ovvero di ricerca.</span><span class="sxs-lookup"><span data-stu-id="e93ae-121">Select the existing table to use as the reference (lookup) table.</span></span>  
  
 <span data-ttu-id="e93ae-122">**Archivia nuovo indice**</span><span class="sxs-lookup"><span data-stu-id="e93ae-122">**Store new index**</span></span>  
 <span data-ttu-id="e93ae-123">Selezionare questa opzione per salvare il nuovo indice di ricerca.</span><span class="sxs-lookup"><span data-stu-id="e93ae-123">Select this option if you want to save the new lookup index.</span></span>  
  
 <span data-ttu-id="e93ae-124">**Nome nuovo indice**</span><span class="sxs-lookup"><span data-stu-id="e93ae-124">**New index name**</span></span>  
 <span data-ttu-id="e93ae-125">Consente di digitare un nome descrittivo per il nuovo indice di ricerca da salvare.</span><span class="sxs-lookup"><span data-stu-id="e93ae-125">If you have chosen to save the new lookup index, type a descriptive name for the index.</span></span>  
  
 <span data-ttu-id="e93ae-126">**Manutenzione indice archiviato**</span><span class="sxs-lookup"><span data-stu-id="e93ae-126">**Maintain stored index**</span></span>  
 <span data-ttu-id="e93ae-127">Consente di specificare se la manutenzione dell'indice deve essere eseguita anche da [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] se si è scelto di salvare il nuovo indice di ricerca.</span><span class="sxs-lookup"><span data-stu-id="e93ae-127">If you have chosen to save the new lookup index, specify whether you also want [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] to maintain the index.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="e93ae-128">Se si seleziona **Manutenzione indice archiviato** nella scheda **Tabella di riferimento** di **Editor trasformazione Ricerca fuzzy**, la trasformazione utilizza stored procedure gestite per gestire l'indice.</span><span class="sxs-lookup"><span data-stu-id="e93ae-128">When you select **Maintain stored index** on the **Reference Table** tab of the **Fuzzy Lookup Transformation Editor**, the transformation uses managed stored procedures to maintain the index.</span></span> <span data-ttu-id="e93ae-129">Queste stored procedure gestite usano la funzionalità di integrazione con Common Language Runtime (CLR) presente in [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="e93ae-129">These managed stored procedures use the common language runtime (CLR) integration feature in [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="e93ae-130">Per impostazione predefinita, l'integrazione con CLR non è abilitata in [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="e93ae-130">By default, CLR integration in [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] is not enabled.</span></span> <span data-ttu-id="e93ae-131">Per utilizzare la funzionalità **Manutenzione indice archiviato** è necessario abilitare l'integrazione con CLR.</span><span class="sxs-lookup"><span data-stu-id="e93ae-131">To use the **Maintain stored index** functionality, you must enable CLR integration.</span></span> <span data-ttu-id="e93ae-132">Per altre informazioni, vedere [Enabling CLR Integration](../relational-databases/clr-integration/clr-integration-enabling.md).</span><span class="sxs-lookup"><span data-stu-id="e93ae-132">For more information, see [Enabling CLR Integration](../relational-databases/clr-integration/clr-integration-enabling.md).</span></span>  
>   
>  <span data-ttu-id="e93ae-133">Considerato che l'opzione **Manutenzione indice archiviato** richiede l'integrazione con CLR, questa funzionalità può essere usata solo se si seleziona una tabella di riferimento in un'istanza di [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] in cui è abilitata l'integrazione con CLR.</span><span class="sxs-lookup"><span data-stu-id="e93ae-133">Because the **Maintain stored index** option requires CLR integration, this feature works only when you select a reference table on an instance of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] where CLR integration is enabled.</span></span>  
  
 <span data-ttu-id="e93ae-134">**Usa indice esistente**</span><span class="sxs-lookup"><span data-stu-id="e93ae-134">**Use existing index**</span></span>  
 <span data-ttu-id="e93ae-135">Consente di specificare che la trasformazione deve utilizzare un indice esistente per la ricerca.</span><span class="sxs-lookup"><span data-stu-id="e93ae-135">Specify that the transformation should use an existing index for the lookup.</span></span>  
  
 <span data-ttu-id="e93ae-136">**Nome di un indice esistente**</span><span class="sxs-lookup"><span data-stu-id="e93ae-136">**Name of an existing index**</span></span>  
 <span data-ttu-id="e93ae-137">Consente di selezionare nell'elenco un indice di ricerca creato precedentemente.</span><span class="sxs-lookup"><span data-stu-id="e93ae-137">Select a previously created lookup index from the list.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e93ae-138">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e93ae-138">See Also</span></span>  
 <span data-ttu-id="e93ae-139">[Guida di riferimento ai messaggi e agli errori di Integration Services](../../2014/integration-services/integration-services-error-and-message-reference.md) </span><span class="sxs-lookup"><span data-stu-id="e93ae-139">[Integration Services Error and Message Reference](../../2014/integration-services/integration-services-error-and-message-reference.md) </span></span>  
 <span data-ttu-id="e93ae-140">[Editor trasformazione Ricerca fuzzy &#40;scheda colonne&#41;](../../2014/integration-services/fuzzy-lookup-transformation-editor-columns-tab.md) </span><span class="sxs-lookup"><span data-stu-id="e93ae-140">[Fuzzy Lookup Transformation Editor &#40;Columns Tab&#41;](../../2014/integration-services/fuzzy-lookup-transformation-editor-columns-tab.md) </span></span>  
 [<span data-ttu-id="e93ae-141">Editor trasformazione Ricerca fuzzy &#40;scheda Avanzate&#41;</span><span class="sxs-lookup"><span data-stu-id="e93ae-141">Fuzzy Lookup Transformation Editor &#40;Advanced Tab&#41;</span></span>](../../2014/integration-services/fuzzy-lookup-transformation-editor-advanced-tab.md)  
  
  
