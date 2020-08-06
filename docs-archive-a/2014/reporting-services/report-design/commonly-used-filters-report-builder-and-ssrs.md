---
title: Filtri di uso comune (Generatore report e SSRS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
helpviewer_keywords:
- multivalued parameters [Reporting Services]
- single-valued parameters [Reporting Services]
- parameters [Reporting Services], multivalued
- valid values [Reporting Services]
ms.assetid: cb70d0cd-707b-4de5-b39f-e4eb57d316aa
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 201cf83d431d1b61e0f20e9d039b2016ad4f13e4
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87629203"
---
# <a name="commonly-used-filters-report-builder-and-ssrs"></a><span data-ttu-id="b04fe-102">Filtri di uso comune (Generatore report e SSRS)</span><span class="sxs-lookup"><span data-stu-id="b04fe-102">Commonly Used Filters (Report Builder and SSRS)</span></span>
  <span data-ttu-id="b04fe-103">Per creare un filtro è necessario specificare una o più equazioni di filtro.</span><span class="sxs-lookup"><span data-stu-id="b04fe-103">To create a filter, you must specify one or more filter equations.</span></span> <span data-ttu-id="b04fe-104">Un'equazione di filtro include un'espressione, un tipo di dati, un operatore e un valore.</span><span class="sxs-lookup"><span data-stu-id="b04fe-104">A filter equation includes an expression, a data type, an operator, and a value.</span></span> <span data-ttu-id="b04fe-105">In questo argomento vengono forniti esempi di filtri di uso comune.</span><span class="sxs-lookup"><span data-stu-id="b04fe-105">This topic provides examples of commonly used filters.</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
## <a name="filter-examples"></a><span data-ttu-id="b04fe-106">Esempi di filtri</span><span class="sxs-lookup"><span data-stu-id="b04fe-106">Filter Examples</span></span>  
 <span data-ttu-id="b04fe-107">Nella tabella seguente sono riportati esempi di equazioni di filtro che utilizzano tipi di dati e operatori differenti.</span><span class="sxs-lookup"><span data-stu-id="b04fe-107">The following table shows examples of filter equations that use different data types and different operators.</span></span> <span data-ttu-id="b04fe-108">L'ambito per il confronto è determinato dall'elemento del report per il quale è definito il filtro.</span><span class="sxs-lookup"><span data-stu-id="b04fe-108">The scope for the comparison is determined by report item for which a filter is defined.</span></span> <span data-ttu-id="b04fe-109">Per un filtro definito in un set di dati, ad esempio, **TOP% 10** si riferisce al primo 10 percento di valori nel set di dati. Per un filtro definito in un gruppo, **TOP% 10** rappresenta il primo 10 percento di valori nel gruppo.</span><span class="sxs-lookup"><span data-stu-id="b04fe-109">For example, for a filter defined on a dataset, **TOP % 10** is the top 10 percent of values in the dataset; for a filter defined on a group, **TOP % 10** is the top 10 percent of values in the group.</span></span>  
  
|<span data-ttu-id="b04fe-110">Espressione semplice</span><span class="sxs-lookup"><span data-stu-id="b04fe-110">Simple Expression</span></span>|<span data-ttu-id="b04fe-111">Tipo di dati</span><span class="sxs-lookup"><span data-stu-id="b04fe-111">Data Type</span></span>|<span data-ttu-id="b04fe-112">Operatore</span><span class="sxs-lookup"><span data-stu-id="b04fe-112">Operator</span></span>|<span data-ttu-id="b04fe-113">valore</span><span class="sxs-lookup"><span data-stu-id="b04fe-113">Value</span></span>|<span data-ttu-id="b04fe-114">Descrizione</span><span class="sxs-lookup"><span data-stu-id="b04fe-114">Description</span></span>|  
|-----------------------|---------------|--------------|-----------|-----------------|  
|`[SUM(Quantity)]`|`Integer`|`>`|`7`|<span data-ttu-id="b04fe-115">Sono inclusi valori di dati maggiori di 7.</span><span class="sxs-lookup"><span data-stu-id="b04fe-115">Includes data values that are greater than 7.</span></span>|  
|`[SUM(Quantity)]`|`Integer`|`TOP N`|`10`|<span data-ttu-id="b04fe-116">Include i primi 10 valori di dati.</span><span class="sxs-lookup"><span data-stu-id="b04fe-116">Includes the top 10 data values.</span></span>|  
|`[SUM(Quantity)]`|`Integer`|`TOP %`|`20`|<span data-ttu-id="b04fe-117">Include il primo 20% di valori di dati.</span><span class="sxs-lookup"><span data-stu-id="b04fe-117">Includes the top 20% of data values.</span></span>|  
|`[Sales]`|`Text`|`>`|`=CDec(100)`|<span data-ttu-id="b04fe-118">Include tutti i valori di tipo System.Decimal (tipi di dati "money" in SQL) maggiori di 100 dollari.</span><span class="sxs-lookup"><span data-stu-id="b04fe-118">Includes all values of type System.Decimal (SQL "money" data types) greater than $100.</span></span>|  
|`[OrderDate]`|`DateTime`|`>`|`2088-01-01`|<span data-ttu-id="b04fe-119">Include tutte le date dal 1 gennaio 2008 alla data corrente.</span><span class="sxs-lookup"><span data-stu-id="b04fe-119">Includes all dates from January 1, 2008 to the present date.</span></span>|  
|`[OrderDate]`|`DateTime`|`BETWEEN`|`2008-01-01`<br /><br /> `2008-02-01`|<span data-ttu-id="b04fe-120">Include le date dal 1 gennaio 2008 al 1 febbraio 2008 compreso.</span><span class="sxs-lookup"><span data-stu-id="b04fe-120">Includes dates from January 1, 2008 up to and including February 1, 2008.</span></span>|  
|`[Territory]`|`Text`|`LIKE`|`*east`|<span data-ttu-id="b04fe-121">Tutti i nomi di territorio che terminano in "east".</span><span class="sxs-lookup"><span data-stu-id="b04fe-121">All territory names that end in "east".</span></span>|  
|`[Territory]`|`Text`|`LIKE`|`%o%th*`|<span data-ttu-id="b04fe-122">Tutti i nomi di territorio che iniziano con North e South.</span><span class="sxs-lookup"><span data-stu-id="b04fe-122">All territory names that include North and South at the beginning of the name.</span></span>|  
|`=LEFT(Fields!Subcat.Value,1)`|`Text`|`IN`|`B, C, T`|<span data-ttu-id="b04fe-123">Tutti i valori di sottocategoria che iniziano con la lettera B, C o T.</span><span class="sxs-lookup"><span data-stu-id="b04fe-123">All subcategory values that begin with the letters B, C, or T.</span></span>|  
  
## <a name="examples-with-report-parameters"></a><span data-ttu-id="b04fe-124">Esempi con parametri report</span><span class="sxs-lookup"><span data-stu-id="b04fe-124">Examples with Report Parameters</span></span>  
 <span data-ttu-id="b04fe-125">Nella tabella seguente sono forniti esempi di espressioni di filtro contenenti un riferimento a un parametro a valore singolo o multivalore.</span><span class="sxs-lookup"><span data-stu-id="b04fe-125">The following table provides examples of filter expression that includes a single-value or multivalue parameter reference.</span></span>  
  
|<span data-ttu-id="b04fe-126">Tipo di parametro</span><span class="sxs-lookup"><span data-stu-id="b04fe-126">Parameter type</span></span>|<span data-ttu-id="b04fe-127">Espressione (filtro)</span><span class="sxs-lookup"><span data-stu-id="b04fe-127">(Filter) Expression</span></span>|<span data-ttu-id="b04fe-128">Operatore</span><span class="sxs-lookup"><span data-stu-id="b04fe-128">Operator</span></span>|<span data-ttu-id="b04fe-129">Valore</span><span class="sxs-lookup"><span data-stu-id="b04fe-129">Value</span></span>|<span data-ttu-id="b04fe-130">Tipo di dati</span><span class="sxs-lookup"><span data-stu-id="b04fe-130">Data Type</span></span>|  
|--------------------|---------------------------|--------------|-----------|---------------|  
|<span data-ttu-id="b04fe-131">Valore singolo</span><span class="sxs-lookup"><span data-stu-id="b04fe-131">Single value</span></span>|`[EmployeeID]`|=|`[@EmployeeID]`|<span data-ttu-id="b04fe-132">Integer</span><span class="sxs-lookup"><span data-stu-id="b04fe-132">Integer</span></span>|  
|<span data-ttu-id="b04fe-133">Multivalore</span><span class="sxs-lookup"><span data-stu-id="b04fe-133">Multivalue</span></span>|`[EmployeeID]`|<span data-ttu-id="b04fe-134">IN</span><span class="sxs-lookup"><span data-stu-id="b04fe-134">IN</span></span>|`[@EmployeeID]`|<span data-ttu-id="b04fe-135">Integer</span><span class="sxs-lookup"><span data-stu-id="b04fe-135">Integer</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="b04fe-136">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b04fe-136">See Also</span></span>  
 <span data-ttu-id="b04fe-137">[Parametri del report &#40;Generatore report e Progettazione report&#41;](report-parameters-report-builder-and-report-designer.md) </span><span class="sxs-lookup"><span data-stu-id="b04fe-137">[Report Parameters &#40;Report Builder and Report Designer&#41;](report-parameters-report-builder-and-report-designer.md) </span></span>  
 <span data-ttu-id="b04fe-138">[Aggiungere filtri del set di dati, aree dati e gruppi &#40;Generatore report e SSRS&#41;](add-dataset-filters-data-region-filters-and-group-filters.md) </span><span class="sxs-lookup"><span data-stu-id="b04fe-138">[Add Dataset Filters, Data Region Filters, and Group Filters &#40;Report Builder and SSRS&#41;](add-dataset-filters-data-region-filters-and-group-filters.md) </span></span>  
 <span data-ttu-id="b04fe-139">[Utilizzo delle espressioni nei report &#40;Generatore report e SSRS&#41;](expression-uses-in-reports-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="b04fe-139">[Expression Uses in Reports &#40;Report Builder and SSRS&#41;](expression-uses-in-reports-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="b04fe-140">[Esempi di espressioni &#40;Generatore report e SSRS&#41;](expression-examples-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="b04fe-140">[Expression Examples &#40;Report Builder and SSRS&#41;](expression-examples-report-builder-and-ssrs.md) </span></span>  
 [<span data-ttu-id="b04fe-141">Tipi di dati nelle espressioni &#40;Generatore report e SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="b04fe-141">Data Types in Expressions &#40;Report Builder and SSRS&#41;</span></span>](expressions-report-builder-and-ssrs.md)  
  
  
