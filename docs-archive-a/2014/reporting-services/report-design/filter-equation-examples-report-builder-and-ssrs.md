---
title: Filter Equation Examples (Report Builder and SSRS) (Esempi di equazioni di filtro (Generatore report e SSRS)) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
helpviewer_keywords:
- filtering data [Reporting Services], filter equation examples
ms.assetid: 66bec93d-7c3b-4d4a-8cb6-7a7bb2f34ec6
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 9b4d7c7c561c9185c141190e26f37bc29fe52eb6
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87627097"
---
# <a name="filter-equation-examples-report-builder-and-ssrs"></a><span data-ttu-id="220f5-102">Esempi di equazioni di filtro (Generatore report e SSRS)</span><span class="sxs-lookup"><span data-stu-id="220f5-102">Filter Equation Examples (Report Builder and SSRS)</span></span>
  <span data-ttu-id="220f5-103">Per creare un filtro è necessario specificare una o più equazioni di filtro.</span><span class="sxs-lookup"><span data-stu-id="220f5-103">To create a filter, you must specify one or more filter equations.</span></span> <span data-ttu-id="220f5-104">Un'equazione di filtro include un'espressione, un tipo di dati, un operatore e un valore.</span><span class="sxs-lookup"><span data-stu-id="220f5-104">A filter equation includes an expression, a data type, an operator, and a value.</span></span> <span data-ttu-id="220f5-105">In questo argomento vengono forniti esempi di filtri di uso comune.</span><span class="sxs-lookup"><span data-stu-id="220f5-105">This topic provides examples of commonly used filters.</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
## <a name="filter-examples"></a><span data-ttu-id="220f5-106">Esempi di filtri</span><span class="sxs-lookup"><span data-stu-id="220f5-106">Filter Examples</span></span>  
 <span data-ttu-id="220f5-107">Nella tabella seguente sono riportati esempi di equazioni di filtro che utilizzano tipi di dati e operatori differenti.</span><span class="sxs-lookup"><span data-stu-id="220f5-107">The following table shows examples of filter equations that use different data types and different operators.</span></span> <span data-ttu-id="220f5-108">L'ambito per il confronto è determinato dall'elemento del report per il quale è definito il filtro.</span><span class="sxs-lookup"><span data-stu-id="220f5-108">The scope for the comparison is determined by report item for which a filter is defined.</span></span> <span data-ttu-id="220f5-109">Per un filtro definito in un set di dati, ad esempio, **TOP% 10** si riferisce al primo 10 percento di valori nel set di dati. Per un filtro definito in un gruppo, **TOP% 10** rappresenta il primo 10 percento di valori nel gruppo.</span><span class="sxs-lookup"><span data-stu-id="220f5-109">For example, for a filter defined on a dataset, **TOP % 10** is the top 10 percent of values in the dataset; for a filter defined on a group, **TOP % 10** is the top 10 percent of values in the group.</span></span>  
  
|<span data-ttu-id="220f5-110">Espressione semplice</span><span class="sxs-lookup"><span data-stu-id="220f5-110">Simple Expression</span></span>|<span data-ttu-id="220f5-111">Tipo di dati</span><span class="sxs-lookup"><span data-stu-id="220f5-111">Data Type</span></span>|<span data-ttu-id="220f5-112">Operatore</span><span class="sxs-lookup"><span data-stu-id="220f5-112">Operator</span></span>|<span data-ttu-id="220f5-113">valore</span><span class="sxs-lookup"><span data-stu-id="220f5-113">Value</span></span>|<span data-ttu-id="220f5-114">Descrizione</span><span class="sxs-lookup"><span data-stu-id="220f5-114">Description</span></span>|  
|-----------------------|---------------|--------------|-----------|-----------------|  
|`[SUM(Quantity)]`|`Integer`|`>`|`7`|<span data-ttu-id="220f5-115">Sono inclusi valori di dati maggiori di 7.</span><span class="sxs-lookup"><span data-stu-id="220f5-115">Includes data values that are greater than 7.</span></span>|  
|`[SUM(Quantity)]`|`Integer`|`TOP N`|`10`|<span data-ttu-id="220f5-116">Include i primi 10 valori di dati.</span><span class="sxs-lookup"><span data-stu-id="220f5-116">Includes the top 10 data values.</span></span>|  
|`[SUM(Quantity)]`|`Integer`|`TOP %`|`20`|<span data-ttu-id="220f5-117">Include il primo 20% di valori di dati.</span><span class="sxs-lookup"><span data-stu-id="220f5-117">Includes the top 20% of data values.</span></span>|  
|`[Sales]`|`Text`|`>`|`=CDec(100)`|<span data-ttu-id="220f5-118">Include tutti i valori di tipo System.Decimal (tipi di dati "money" in SQL) maggiori di 100 dollari.</span><span class="sxs-lookup"><span data-stu-id="220f5-118">Includes all values of type System.Decimal (SQL "money" data types) greater than $100.</span></span>|  
|`[OrderDate]`|`DateTime`|`>`|`2008-01-01`|<span data-ttu-id="220f5-119">Include tutte le date dal 1 gennaio 2008 alla data corrente.</span><span class="sxs-lookup"><span data-stu-id="220f5-119">Includes all dates from January 1, 2008 to the present date.</span></span>|  
|`[OrderDate]`|`DateTime`|`BETWEEN`|`2008-01-01`<br /><br /> `2008-02-01`|<span data-ttu-id="220f5-120">Include le date dal 1 gennaio 2008 al 1 febbraio 2008 compreso.</span><span class="sxs-lookup"><span data-stu-id="220f5-120">Includes dates from January 1, 2008 up to and including February 1, 2008.</span></span>|  
|`[Territory]`|`Text`|`LIKE`|`*east`|<span data-ttu-id="220f5-121">Tutti i nomi di territorio che terminano in "east".</span><span class="sxs-lookup"><span data-stu-id="220f5-121">All territory names that end in "east".</span></span>|  
|`[Territory]`|`Text`|`LIKE`|`%o%th*`|<span data-ttu-id="220f5-122">Tutti i nomi di territorio che iniziano con North e South.</span><span class="sxs-lookup"><span data-stu-id="220f5-122">All territory names that include North and South at the beginning of the name.</span></span>|  
|`=LEFT(Fields!Subcat.Value,1)`|`Text`|`IN`|`B, C, T`|<span data-ttu-id="220f5-123">Tutti i valori di sottocategoria che iniziano con la lettera B, C o T.</span><span class="sxs-lookup"><span data-stu-id="220f5-123">All subcategory values that begin with the letters B, C, or T.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="220f5-124">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="220f5-124">See Also</span></span>  
 <span data-ttu-id="220f5-125">[Parametri del report &#40;Generatore report e Progettazione report&#41;](report-parameters-report-builder-and-report-designer.md) </span><span class="sxs-lookup"><span data-stu-id="220f5-125">[Report Parameters &#40;Report Builder and Report Designer&#41;](report-parameters-report-builder-and-report-designer.md) </span></span>  
 <span data-ttu-id="220f5-126">[Aggiungere filtri del set di dati, aree dati e gruppi &#40;Generatore report e SSRS&#41;](add-dataset-filters-data-region-filters-and-group-filters.md) </span><span class="sxs-lookup"><span data-stu-id="220f5-126">[Add Dataset Filters, Data Region Filters, and Group Filters &#40;Report Builder and SSRS&#41;](add-dataset-filters-data-region-filters-and-group-filters.md) </span></span>  
 <span data-ttu-id="220f5-127">[Tipi di dati nelle espressioni &#40;Generatore report e SSRS&#41;](expressions-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="220f5-127">[Data Types in Expressions &#40;Report Builder and SSRS&#41;](expressions-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="220f5-128">[Utilizzo delle espressioni nei report &#40;Generatore report e SSRS&#41;](expression-uses-in-reports-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="220f5-128">[Expression Uses in Reports &#40;Report Builder and SSRS&#41;](expression-uses-in-reports-report-builder-and-ssrs.md) </span></span>  
 [<span data-ttu-id="220f5-129">Esempi di espressioni &#40;Generatore report e SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="220f5-129">Expression Examples &#40;Report Builder and SSRS&#41;</span></span>](expression-examples-report-builder-and-ssrs.md)  
  
  
