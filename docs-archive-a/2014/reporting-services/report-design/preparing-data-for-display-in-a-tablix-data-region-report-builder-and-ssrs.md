---
title: Preparare i dati per la visualizzazione in un'area dati Tablix (Generatore report e SSRS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: fbb00dc6-7887-480c-b771-cab6fecb8dcc
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 72ac150f2dcd227b1e3afb624a5ca5866fb4c360
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87636564"
---
# <a name="preparing-data-for-display-in-a-tablix-data-region-report-builder-and-ssrs"></a><span data-ttu-id="d46d9-102">Preparare i dati per la visualizzazione in un'area dati Tablix (Generatore report e SSRS)</span><span class="sxs-lookup"><span data-stu-id="d46d9-102">Preparing Data for Display in a Tablix Data Region (Report Builder and SSRS)</span></span>
  <span data-ttu-id="d46d9-103">In un'area dati Tablix vengono visualizzati i dati di un set di dati.</span><span class="sxs-lookup"><span data-stu-id="d46d9-103">A tablix data region displays data from a dataset.</span></span> <span data-ttu-id="d46d9-104">È possibile visualizzare tutti i dati recuperati per il set di dati o creare filtri in modo da visualizzare solo un subset dei dati.</span><span class="sxs-lookup"><span data-stu-id="d46d9-104">You can view all the data retrieved for the dataset or you can create filters so that you see only a subset of the data.</span></span> <span data-ttu-id="d46d9-105">È inoltre possibile aggiungere espressioni condizionali per inserire valori Null o modificare la query affinché un set di dati includa colonne che definiscono il tipo di ordinamento per una colonna esistente.</span><span class="sxs-lookup"><span data-stu-id="d46d9-105">You can also add conditional expressions to fill in null values or modify the query for a dataset to include columns that define the sort order for an existing column.</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
## <a name="working-with-nulls-and-blanks-in-field-values"></a><span data-ttu-id="d46d9-106">Utilizzo di valori Null e spazi vuoti nei valori dei campi</span><span class="sxs-lookup"><span data-stu-id="d46d9-106">Working with Nulls and Blanks in Field Values</span></span>  
 <span data-ttu-id="d46d9-107">Nei dati relativi alla raccolta di campi di un set di dati sono compresi tutti i valori recuperati in fase di esecuzione dall'origine dati, inclusi i valori Null e gli spazi vuoti.</span><span class="sxs-lookup"><span data-stu-id="d46d9-107">Data for the field collection in a dataset includes all values retrieved from the data source at run time, including null values and blanks.</span></span> <span data-ttu-id="d46d9-108">In genere, i valori Null e gli spazi vuoti non sono distinguibili.</span><span class="sxs-lookup"><span data-stu-id="d46d9-108">Normally null values and blanks are indistinguishable.</span></span> <span data-ttu-id="d46d9-109">Nella maggior parte dei casi questo è il comportamento desiderato.</span><span class="sxs-lookup"><span data-stu-id="d46d9-109">In most cases, this is the desired behavior.</span></span> <span data-ttu-id="d46d9-110">Funzioni di aggregazione numeriche come [Sum](report-builder-functions-sum-function.md) e [Avg](report-builder-functions-avg-function.md) ignorano ad esempio i valori Null.</span><span class="sxs-lookup"><span data-stu-id="d46d9-110">For example, Numeric aggregate functions like [Sum](report-builder-functions-sum-function.md) and [Avg](report-builder-functions-avg-function.md) ignore null values.</span></span> <span data-ttu-id="d46d9-111">Per altre informazioni, vedere [Riferimento a funzioni di aggregazione &#40;Generatore report e SSRS&#41;](report-builder-functions-aggregate-functions-reference.md).</span><span class="sxs-lookup"><span data-stu-id="d46d9-111">For more information, see [Aggregate Functions Reference &#40;Report Builder and SSRS&#41;](report-builder-functions-aggregate-functions-reference.md).</span></span>  
  
 <span data-ttu-id="d46d9-112">Se si desidera gestire in modo diverso i valori Null, è possibile utilizzare espressioni condizionali o codice personalizzato per sostituire un valore personalizzato al valore Null.</span><span class="sxs-lookup"><span data-stu-id="d46d9-112">If you do want to handle null values differently, you can use conditional expressions or custom code to substitute a custom value for the null value.</span></span> <span data-ttu-id="d46d9-113">Nell'espressione seguente ad esempio il testo `Null` viene sostituito ogni volta che si rileva un valore Null nel campo `[Size]`.</span><span class="sxs-lookup"><span data-stu-id="d46d9-113">For example, the following expression substitutes the text `Null` wherever a null value occurs in the field `[Size]`.</span></span>  
  
```  
=IIF(Fields!Size.Value IS NOTHING,"Null",Fields!Size.Value)  
```  
  
 <span data-ttu-id="d46d9-114">Per altre informazioni sull'eliminazione di valori Null nei dati prima del recupero dei dati da un'origine dati [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] tramite query [!INCLUDE[tsql](../../includes/tsql-md.md)] , vedere le sezioni relative a valori Null e valori Null e join nella documentazione di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] inclusa nella [documentazione online di SQL Server](https://go.microsoft.com/fwlink/?linkid=120955).</span><span class="sxs-lookup"><span data-stu-id="d46d9-114">For more information about eliminating nulls in your data before retrieving the data from a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] data source using [!INCLUDE[tsql](../../includes/tsql-md.md)] queries, see "Null Values" and "Null Values and Joins" in the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] documentation in [SQL Server Books Online](https://go.microsoft.com/fwlink/?linkid=120955).</span></span>  
  
## <a name="handling-null-field-names"></a><span data-ttu-id="d46d9-115">Gestione dei nomi dei campi con valori Null</span><span class="sxs-lookup"><span data-stu-id="d46d9-115">Handling Null Field Names</span></span>  
 <span data-ttu-id="d46d9-116">Il testing dei valori Null in un'espressione risulta appropriato fino a quando il campo stesso è presente nel set di risultati della query.</span><span class="sxs-lookup"><span data-stu-id="d46d9-116">Testing for null values in an expression is fine as long as the field itself exists in the query result set.</span></span> <span data-ttu-id="d46d9-117">Partendo dal codice personalizzato è possibile eseguire il testing per verificare la presenza del campo tra i campi della raccolta restituiti in fase di esecuzione dall'origine dati.</span><span class="sxs-lookup"><span data-stu-id="d46d9-117">From custom code, you can test whether the field itself is present in the collection fields returned from the data source at run time.</span></span> <span data-ttu-id="d46d9-118">Per altre informazioni, vedere [Riferimenti alla raccolta di campi del set di dati &#40;Generatore report e SSRS&#41;](built-in-collections-dataset-fields-collection-references-report-builder.md).</span><span class="sxs-lookup"><span data-stu-id="d46d9-118">For more information, see [Dataset Fields Collection References &#40;Report Builder and SSRS&#41;](built-in-collections-dataset-fields-collection-references-report-builder.md).</span></span>  
  
## <a name="adding-a-sort-order-column"></a><span data-ttu-id="d46d9-119">Aggiunta di una colonna per il tipo di ordinamento</span><span class="sxs-lookup"><span data-stu-id="d46d9-119">Adding a Sort Order Column</span></span>  
 <span data-ttu-id="d46d9-120">Per impostazione predefinita, è possibile disporre in ordine alfabetico i valori di un campo del set di dati.</span><span class="sxs-lookup"><span data-stu-id="d46d9-120">By default, you can alphabetically sort values in a dataset field.</span></span> <span data-ttu-id="d46d9-121">Per impostare un ordine diverso, è possibile aggiungere una nuova colonna al set di dati che definisce il tipo di ordinamento desiderato in un'area dati.</span><span class="sxs-lookup"><span data-stu-id="d46d9-121">To sort in a different order, you can add a new column to your dataset that defines the sort order you want in a data region.</span></span> <span data-ttu-id="d46d9-122">Per eseguire l'ordinamento in base al campo `[Color]` , disponendo per primi gli elementi bianchi e neri, è possibile aggiungere una colonna `[ColorSortOrder]`, come mostrato nella query seguente:</span><span class="sxs-lookup"><span data-stu-id="d46d9-122">For example, to sort on the field `[Color]` and sort white and black items first, you can add a column `[ColorSortOrder]`, shown in the following query:</span></span>  
  
```  
SELECT ProductID, p.Name, Color,  
   CASE  
      WHEN p.Color = 'White' THEN 1  
      WHEN p.Color = 'Black' THEN 2  
      WHEN p.Color = 'Blue' THEN 3  
      WHEN p.Color = 'Yellow' THEN 4  
      ELSE 5  
   END As ColorSortOrder  
FROM Production.Product p  
```  
  
 <span data-ttu-id="d46d9-123">Per configurare un'area dati della tabella in base a questo tipo di ordinamento, impostare l'espressione di ordinamento nel gruppo dettagli su `=Fields!ColorSortOrder.Value`.</span><span class="sxs-lookup"><span data-stu-id="d46d9-123">To sort a table data region according to this sort order, set the sort expression on the detail group to `=Fields!ColorSortOrder.Value`.</span></span> <span data-ttu-id="d46d9-124">Per altre informazioni, vedere [Ordinare i dati in un'area dati &#40;Generatore report e SSRS& #41;](sort-data-in-a-data-region-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="d46d9-124">For more information, see [Sort Data in a Data Region &#40;Report Builder and SSRS&#41;](sort-data-in-a-data-region-report-builder-and-ssrs.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d46d9-125">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d46d9-125">See Also</span></span>  
 <span data-ttu-id="d46d9-126">[Raccolta di campi del set di dati &#40;Generatore report e SSRS&#41;](../report-data/dataset-fields-collection-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="d46d9-126">[Dataset Fields Collection &#40;Report Builder and SSRS&#41;](../report-data/dataset-fields-collection-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="d46d9-127">[Espressioni &#40;Generatore report e SSRS&#41;](expressions-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="d46d9-127">[Expressions &#40;Report Builder and SSRS&#41;](expressions-report-builder-and-ssrs.md) </span></span>  
 [<span data-ttu-id="d46d9-128">Filtro, raggruppamento e ordinamento di dati &#40;Generatore report e SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="d46d9-128">Filter, Group, and Sort Data &#40;Report Builder and SSRS&#41;</span></span>](filter-group-and-sort-data-report-builder-and-ssrs.md)  
  
  
