---
title: Creare relazioni | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.createrelationships.f1
ms.assetid: 6ebd305f-ffd2-4a1d-b24c-e28c151b94f5
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 5a1095e193587ae7d416311031e5297a035ca37e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87626166"
---
# <a name="create-relationships"></a><span data-ttu-id="029e8-102">Crea relazioni</span><span class="sxs-lookup"><span data-stu-id="029e8-102">Create Relationships</span></span>
  <span data-ttu-id="029e8-103">Utilizzare la finestra di dialogo **Crea relazioni** per modificare i mapping tra le colonne di origine e le colonne della tabella di ricerca configurati nell'Editor trasformazione Ricerca fuzzy, nell'Editor trasformazione Ricerca e nell'Editor trasformazione Ricerca termini.</span><span class="sxs-lookup"><span data-stu-id="029e8-103">Use the **Create Relationships** dialog box to edit mappings between the source columns and the lookup table columns that you configured in the Fuzzy Lookup Transformation Editor, the Lookup Transformation Editor, and the Term Lookup Transformation Editor.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="029e8-104">Quando viene richiamata dall'Editor trasformazione Ricerca termini, la finestra di dialogo **Crea relazioni** visualizza solo gli elenchi **Colonna di input** e **Colonna di ricerca** .</span><span class="sxs-lookup"><span data-stu-id="029e8-104">The **Create Relationships** dialog box displays only the **Input Column** and **Lookup Column** lists when invoked from the Term Lookup Transformation Editor.</span></span>  
  
 <span data-ttu-id="029e8-105">Per ulteriori informazioni sulle trasformazioni che utilizzano la finestra di dialogo **Crea relazioni** , vedere [Fuzzy Lookup Transformation](lookup-transformation.md), [Lookup Transformation](lookup-transformation.md)e [Term Lookup Transformation](term-lookup-transformation.md).</span><span class="sxs-lookup"><span data-stu-id="029e8-105">To learn more about the transformations that use the **Create Relationships** dialog box, see [Fuzzy Lookup Transformation](lookup-transformation.md), [Lookup Transformation](lookup-transformation.md), and [Term Lookup Transformation](term-lookup-transformation.md).</span></span>  
  
## <a name="options"></a><span data-ttu-id="029e8-106">Opzioni</span><span class="sxs-lookup"><span data-stu-id="029e8-106">Options</span></span>  
 <span data-ttu-id="029e8-107">**Colonna di input**</span><span class="sxs-lookup"><span data-stu-id="029e8-107">**Input Column**</span></span>  
 <span data-ttu-id="029e8-108">Consente di selezionare una colonna di input nell'elenco delle colonne di input disponibili.</span><span class="sxs-lookup"><span data-stu-id="029e8-108">Select from the list of available input columns.</span></span>  
  
 <span data-ttu-id="029e8-109">**Colonna di ricerca**</span><span class="sxs-lookup"><span data-stu-id="029e8-109">**Lookup Column**</span></span>  
 <span data-ttu-id="029e8-110">Consente di selezionare una colonna di ricerca nell'elenco delle colonne di ricerca disponibili.</span><span class="sxs-lookup"><span data-stu-id="029e8-110">Select from the list of available lookup columns.</span></span>  
  
 <span data-ttu-id="029e8-111">**Tipo di mapping**</span><span class="sxs-lookup"><span data-stu-id="029e8-111">**Mapping Type**</span></span>  
 <span data-ttu-id="029e8-112">Consente di selezionare la corrispondenza fuzzy o esatta.</span><span class="sxs-lookup"><span data-stu-id="029e8-112">Select fuzzy or exact matching.</span></span>  
  
 <span data-ttu-id="029e8-113">Quando si utilizza la corrispondenza fuzzy, le righe vengono considerate duplicati quando sono sufficientemente simili in tutte le colonne che hanno un tipo di corrispondenza fuzzy.</span><span class="sxs-lookup"><span data-stu-id="029e8-113">When you use fuzzy matching, rows are considered duplicates if they are sufficiently similar across all columns that have a fuzzy match type.</span></span> <span data-ttu-id="029e8-114">Per ottenere i migliori risultati dalla corrispondenza fuzzy, è possibile specificare che alcune colonne devono utilizzare la corrispondenza esatta anziché la corrispondenza fuzzy.</span><span class="sxs-lookup"><span data-stu-id="029e8-114">To obtain better results from fuzzy matching, you can specify that some columns should use exact matching instead of fuzzy matching.</span></span> <span data-ttu-id="029e8-115">Ad esempio, se è noto che una determinata colonna non contiene errori o inconsistenze, è possibile specificare la corrispondenza esatta per tale colonna, in modo che vengano considerati come possibili duplicati solo le righe della colonna che contengono valori identici.</span><span class="sxs-lookup"><span data-stu-id="029e8-115">For example, if you know that a certain column contains no errors or inconsistencies, you can specify exact matching on that column, so that only rows which contain identical values in this column are considered as possible duplicates.</span></span> <span data-ttu-id="029e8-116">Ciò migliora l'accuratezza della corrispondenza fuzzy nelle altre colonne.</span><span class="sxs-lookup"><span data-stu-id="029e8-116">This increases the accuracy of fuzzy matching on other columns.</span></span>  
  
 <span data-ttu-id="029e8-117">**Flag di confronto**</span><span class="sxs-lookup"><span data-stu-id="029e8-117">**Comparison Flags**</span></span>  
 <span data-ttu-id="029e8-118">Per altre informazioni sulle opzioni per il confronto di stringhe, vedere [Confronto di dati stringa](../comparing-string-data.md).</span><span class="sxs-lookup"><span data-stu-id="029e8-118">For information about the string comparison options, see [Comparing String Data](../comparing-string-data.md).</span></span>  
  
 <span data-ttu-id="029e8-119">**Somiglianza minima**</span><span class="sxs-lookup"><span data-stu-id="029e8-119">**Minimum Similarity**</span></span>  
 <span data-ttu-id="029e8-120">Consente di impostare la soglia di somiglianza a livello di colonna utilizzando il dispositivo di scorrimento.</span><span class="sxs-lookup"><span data-stu-id="029e8-120">Set the similarity threshold at the column level by using the slider.</span></span> <span data-ttu-id="029e8-121">Più il valore è prossimo a 1, più prossima deve essere la somiglianza del valore di ricerca con il valore di origine per essere qualificata come corrispondenza.</span><span class="sxs-lookup"><span data-stu-id="029e8-121">The closer the value is to 1, the more the lookup value must resemble the source value to qualify as a match.</span></span> <span data-ttu-id="029e8-122">L'aumento della soglia può incrementare la velocità di ricerca della corrispondenza in quanto viene considerato un minor numero di record candidati.</span><span class="sxs-lookup"><span data-stu-id="029e8-122">Increasing the threshold can improve the speed of matching because fewer candidate records have to be considered.</span></span>  
  
 <span data-ttu-id="029e8-123">**Alias di output somiglianza**</span><span class="sxs-lookup"><span data-stu-id="029e8-123">**Similarity Output Alias**</span></span>  
 <span data-ttu-id="029e8-124">Consente di specificare il nome per una nuova colonna di output che contiene i punteggi di somiglianza per la colonna selezionata.</span><span class="sxs-lookup"><span data-stu-id="029e8-124">Specify the name for a new output column that contains the similarity scores for the selected column.</span></span> <span data-ttu-id="029e8-125">Se non si specifica un valore, la colonna di output non viene creata.</span><span class="sxs-lookup"><span data-stu-id="029e8-125">If you leave this value empty, the output column is not created.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="029e8-126">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="029e8-126">See Also</span></span>  
 <span data-ttu-id="029e8-127">[Guida di riferimento ai messaggi e agli errori di Integration Services](../../integration-services-error-and-message-reference.md) </span><span class="sxs-lookup"><span data-stu-id="029e8-127">[Integration Services Error and Message Reference](../../integration-services-error-and-message-reference.md) </span></span>  
 <span data-ttu-id="029e8-128">[Editor trasformazione Ricerca fuzzy &#40;scheda Colonne&#41;](../../fuzzy-lookup-transformation-editor-columns-tab.md) </span><span class="sxs-lookup"><span data-stu-id="029e8-128">[Fuzzy Lookup Transformation Editor &#40;Columns Tab&#41;](../../fuzzy-lookup-transformation-editor-columns-tab.md) </span></span>  
 <span data-ttu-id="029e8-129">[Editor trasformazione Ricerca &#40;pagina Colonne&#41;](../../lookup-transformation-editor-columns-page.md) </span><span class="sxs-lookup"><span data-stu-id="029e8-129">[Lookup Transformation Editor &#40;Columns Page&#41;](../../lookup-transformation-editor-columns-page.md) </span></span>  
 [<span data-ttu-id="029e8-130">Editor trasformazione Ricerca termini &#40;scheda Ricerca termini&#41;</span><span class="sxs-lookup"><span data-stu-id="029e8-130">Term Lookup Transformation Editor &#40;Term Lookup Tab&#41;</span></span>](../../term-lookup-transformation-editor-term-lookup-tab.md)  
  
  
