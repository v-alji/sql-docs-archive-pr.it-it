---
title: Definire formule personalizzate membro | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- members [Analysis Services], custom
- custom rollup formulas [Analysis Services]
- MDX [Analysis Services], custom rollup formulas
- custom member formulas [Analysis Services]
ms.assetid: 258304e2-d900-4013-97e3-871f51dfdce2
author: minewiskan
ms.author: owend
ms.openlocfilehash: 51649bea0c4134971b342b779c778b857343e62b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87725123"
---
# <a name="define-custom-member-formulas"></a><span data-ttu-id="a4606-102">Definire formule personalizzate membro</span><span class="sxs-lookup"><span data-stu-id="a4606-102">Define Custom Member Formulas</span></span>
  <span data-ttu-id="a4606-103">È possibile definire un'espressione MDX (MultiDimensional Expression), denominata formula personalizzata membro, per indicare i valori dei membri di un attributo specificato.</span><span class="sxs-lookup"><span data-stu-id="a4606-103">You can define a Multidimensional Expressions (MDX) expression, called a custom member formula, to supply the values for the members of a specified attribute.</span></span> <span data-ttu-id="a4606-104">L'espressione utilizzata per specificare il valore di ogni membro di un attributo è indicata in una colonna di una tabella di una vista origine dati.</span><span class="sxs-lookup"><span data-stu-id="a4606-104">A column in a table from a data source view provides, for each member in an attribute, the expression used to supply the value for that member.</span></span>  
  
 <span data-ttu-id="a4606-105">Le formule personalizzate membro determinano i valori delle celle associati ai membri e hanno priorità rispetto alle funzioni di aggregazione delle misure.</span><span class="sxs-lookup"><span data-stu-id="a4606-105">Custom member formulas determine the cell values that are associated with members and override the aggregate functions of measures.</span></span> <span data-ttu-id="a4606-106">Le formule personalizzate membro sono scritte in MDX.</span><span class="sxs-lookup"><span data-stu-id="a4606-106">Custom member formulas are written in MDX.</span></span> <span data-ttu-id="a4606-107">Ogni formula personalizzata membro viene applicata a un singolo membro.</span><span class="sxs-lookup"><span data-stu-id="a4606-107">Each custom member formula applies to a single member.</span></span> <span data-ttu-id="a4606-108">Le formule personalizzate membro vengono archiviate nella tabella della dimensione o in un'altra tabella collegata tramite una relazione di chiave esterna alla tabella della dimensione.</span><span class="sxs-lookup"><span data-stu-id="a4606-108">Custom member formulas are stored in the dimension table or in another table that has a foreign key relationship with the dimension table.</span></span>  
  
 <span data-ttu-id="a4606-109">La proprietà `CustomRollupColumn` di un attributo specifica la colonna che include le formule personalizzate membro per i membri dell'attributo.</span><span class="sxs-lookup"><span data-stu-id="a4606-109">The `CustomRollupColumn` property on an attribute specifies the column that contains custom member formulas for members of the attribute.</span></span> <span data-ttu-id="a4606-110">Se una riga della colonna è vuota, il valore della cella per il membro viene restituito normalmente.</span><span class="sxs-lookup"><span data-stu-id="a4606-110">If a row in the column is empty, the cell value for the member is returned normally.</span></span> <span data-ttu-id="a4606-111">Se la formula nella colonna non è valida, si verifica un errore di run-time ogni volta che viene recuperato il valore di una cella che utilizza il membro.</span><span class="sxs-lookup"><span data-stu-id="a4606-111">If the formula in the column is not valid, a run-time error occurs whenever a cell value that uses the member is retrieved.</span></span>  
  
 <span data-ttu-id="a4606-112">Prima di poter specificare formule personalizzate membro per un attributo, verificare che nella tabella della dimensione contenente l'attributo o in una tabella direttamente correlata sia disponibile una colonna stringa per l'archiviazione delle formule personalizzate membro.</span><span class="sxs-lookup"><span data-stu-id="a4606-112">Before you can specify custom member formulas for an attribute, make sure that the dimension table that contains the attribute, or a directly related table, has a string column to store the custom member formulas.</span></span> <span data-ttu-id="a4606-113">In tal caso, è possibile impostare `CustomRollupColumn` manualmente la proprietà su un attributo o utilizzare l'impostazione avanzata formule personalizzate membro della configurazione guidata funzionalità di Business Intelligence per abilitare una formula personalizzata membro su un attributo.</span><span class="sxs-lookup"><span data-stu-id="a4606-113">If this is the case, you can either set the `CustomRollupColumn` property on an attribute manually or use the Set Custom Member Formula enhancement of the Business Intelligence Wizard to enable a custom member formula on an attribute.</span></span> <span data-ttu-id="a4606-114">Per altre informazioni su come usare questa funzionalità avanzata, vedere [Impostare formule personalizzate membro per gli attributi in una dimensione](bi-wizard-custom-member-formulas-for-attributes-in-a-dimension.md).</span><span class="sxs-lookup"><span data-stu-id="a4606-114">For more information about how to use this enhancement, see [Set Custom Member Formulas for Attributes in a Dimension](bi-wizard-custom-member-formulas-for-attributes-in-a-dimension.md).</span></span>  
  
## <a name="evaluating-custom-member-formulas"></a><span data-ttu-id="a4606-115">Valutazione delle formule personalizzate membro</span><span class="sxs-lookup"><span data-stu-id="a4606-115">Evaluating Custom Member Formulas</span></span>  
 <span data-ttu-id="a4606-116">Le formule personalizzate membro si differenziano dai membri calcolati per vari aspetti.</span><span class="sxs-lookup"><span data-stu-id="a4606-116">Custom member formulas differ from calculated members.</span></span> <span data-ttu-id="a4606-117">Vengono applicate ai membri esistenti nelle tabelle delle dimensioni e determinano solo il valore del membro.</span><span class="sxs-lookup"><span data-stu-id="a4606-117">Custom member formulas apply to members that exist in dimension tables, and only provide the value of the member.</span></span> <span data-ttu-id="a4606-118">I membri calcolati, viceversa, non vengono archiviati nelle tabelle delle dimensioni e le relative espressioni definiscono sia i dati che i metadati dei membri aggiuntivi inclusi in una dimensione o una gerarchia.</span><span class="sxs-lookup"><span data-stu-id="a4606-118">In contrast, calculated members are not stored in dimension tables, and calculated member expressions define both data and metadata for additional members included in a dimension or hierarchy.</span></span>  
  
 <span data-ttu-id="a4606-119">Le formule personalizzate membro hanno priorità rispetto alle funzioni di aggregazione associate alle misure.</span><span class="sxs-lookup"><span data-stu-id="a4606-119">Custom member formulas override the aggregate functions associated with measures.</span></span> <span data-ttu-id="a4606-120">Si supponga, ad esempio, che prima dell'impostazione di una formula personalizzata membro, una misura che utilizza la funzione di aggregazione `Sum` presenti i valori seguenti per questi membri della dimensione Time:</span><span class="sxs-lookup"><span data-stu-id="a4606-120">For example, before a custom member formula is specified, a measure using the `Sum` aggregate function has the following values for the following members of the Time dimension:</span></span>  
  
-   <span data-ttu-id="a4606-121">2003: 2100</span><span class="sxs-lookup"><span data-stu-id="a4606-121">2003: 2100</span></span>  
  
    -   <span data-ttu-id="a4606-122">Quarter 1: 700</span><span class="sxs-lookup"><span data-stu-id="a4606-122">Quarter 1: 700</span></span>  
  
    -   <span data-ttu-id="a4606-123">Quarter 2: 500</span><span class="sxs-lookup"><span data-stu-id="a4606-123">Quarter 2: 500</span></span>  
  
    -   <span data-ttu-id="a4606-124">Quarter 3: 100</span><span class="sxs-lookup"><span data-stu-id="a4606-124">Quarter 3: 100</span></span>  
  
    -   <span data-ttu-id="a4606-125">Quarter 4: 800</span><span class="sxs-lookup"><span data-stu-id="a4606-125">Quarter 4: 800</span></span>  
  
-   <span data-ttu-id="a4606-126">2004: 1500</span><span class="sxs-lookup"><span data-stu-id="a4606-126">2004: 1500</span></span>  
  
    -   <span data-ttu-id="a4606-127">Quarter 1: 600</span><span class="sxs-lookup"><span data-stu-id="a4606-127">Quarter 1: 600</span></span>  
  
    -   <span data-ttu-id="a4606-128">Quarter 2: 200</span><span class="sxs-lookup"><span data-stu-id="a4606-128">Quarter 2: 200</span></span>  
  
    -   <span data-ttu-id="a4606-129">Quarter 3: 300</span><span class="sxs-lookup"><span data-stu-id="a4606-129">Quarter 3: 300</span></span>  
  
    -   <span data-ttu-id="a4606-130">Quarter 4: 400</span><span class="sxs-lookup"><span data-stu-id="a4606-130">Quarter 4: 400</span></span>  
  
 <span data-ttu-id="a4606-131">Se si utilizza una formula personalizzata membro, il valore del membro è invece specificato dalla formula personalizzata di rollup.</span><span class="sxs-lookup"><span data-stu-id="a4606-131">With a custom member formula, the value of the member is instead supplied by the custom rollup formula.</span></span> <span data-ttu-id="a4606-132">Ad esempio, la formula personalizzata membro seguente può essere utilizzata per determinare il valore 450 per il membro figlio Quarter 4 del membro 2004 nella dimensione Time.</span><span class="sxs-lookup"><span data-stu-id="a4606-132">For example, the following custom member formula can be used to supply the value for the Quarter 4 child member of the 2004 member in the Time dimension as 450.</span></span>  
  
```  
Time.[Quarter 3] * 1.5  
```  
  
 <span data-ttu-id="a4606-133">Le formule personalizzate membro vengono archiviate in una colonna della tabella della dimensione.</span><span class="sxs-lookup"><span data-stu-id="a4606-133">Custom member formulas are stored in a column of the dimension table.</span></span> <span data-ttu-id="a4606-134">Per abilitare le formule personalizzate di rollup, impostare la proprietà `CustomRollupColumn` di un attributo.</span><span class="sxs-lookup"><span data-stu-id="a4606-134">You enable custom rollup formulas by setting the `CustomRollupColumn` property on an attribute.</span></span>  
  
 <span data-ttu-id="a4606-135">Per applicare una singola espressione MDX a tutti i membri di un attributo, creare un calcolo denominato nella tabella della dimensione che restituisce un'espressione sotto forma di una stringa letterale.</span><span class="sxs-lookup"><span data-stu-id="a4606-135">To apply a single MDX expression to all members of an attribute, create a named calculation on the dimension table that returns an MDX expression as a literal string.</span></span> <span data-ttu-id="a4606-136">Specificare quindi il calcolo denominato nella proprietà `CustomRollupColumn` dell'attributo che si desidera configurare.</span><span class="sxs-lookup"><span data-stu-id="a4606-136">Then, specify the named calculation with the `CustomRollupColumn` property setting on the attribute that you want to configure.</span></span> <span data-ttu-id="a4606-137">Un calcolo denominato è una colonna di una tabella di una vista origine dati che restituisce valori di riga definiti da un'espressione SQL.</span><span class="sxs-lookup"><span data-stu-id="a4606-137">A named calculation is a column in a data source view table that returns row values defined by a SQL expression.</span></span> <span data-ttu-id="a4606-138">Per altre informazioni sulla creazione di calcoli denominati, vedere [Definire calcoli denominati in una vista origine dati &#40;Analysis Services&#41;](define-named-calculations-in-a-data-source-view-analysis-services.md)</span><span class="sxs-lookup"><span data-stu-id="a4606-138">For more information about constructing named calculations, see [Define Named Calculations in a Data Source View &#40;Analysis Services&#41;](define-named-calculations-in-a-data-source-view-analysis-services.md)</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="a4606-139">Per applicare un'espressione MDX ai membri di un livello particolare invece che ai membri di tutti i livelli in base a un particolare attributo, è possibile definire l'espressione come script MDX nel livello.</span><span class="sxs-lookup"><span data-stu-id="a4606-139">To apply an MDX expression to members of a particular level instead of to members of all levels based on a particular attribute, you can define the expression as an MDX script on the level.</span></span> <span data-ttu-id="a4606-140">Per altre informazioni, vedere [Nozioni fondamentali sullo scripting MDX &#40;Analysis Services&#41;](mdx/mdx-scripting-fundamentals-analysis-services.md).</span><span class="sxs-lookup"><span data-stu-id="a4606-140">For more information, see [MDX Scripting Fundamentals &#40;Analysis Services&#41;](mdx/mdx-scripting-fundamentals-analysis-services.md).</span></span>  
  
 <span data-ttu-id="a4606-141">Se si utilizzano sia membri calcolati che formule personalizzate di rollup per i membri di un attributo, è importante tenere presente l'ordine di valutazione.</span><span class="sxs-lookup"><span data-stu-id="a4606-141">If you use both calculated members and custom rollup formulas for members of an attribute, you should be aware of the order of evaluation.</span></span> <span data-ttu-id="a4606-142">I membri calcolati vengono risolti prima delle formule personalizzate di rollup.</span><span class="sxs-lookup"><span data-stu-id="a4606-142">Calculated members are resolved before custom rollup formulas are resolved.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a4606-143">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a4606-143">See Also</span></span>  
 <span data-ttu-id="a4606-144">[Attributi e gerarchie di attributi](../multidimensional-models-olap-logical-dimension-objects/attributes-and-attribute-hierarchies.md) </span><span class="sxs-lookup"><span data-stu-id="a4606-144">[Attributes and Attribute Hierarchies](../multidimensional-models-olap-logical-dimension-objects/attributes-and-attribute-hierarchies.md) </span></span>  
 [<span data-ttu-id="a4606-145">Impostare formule personalizzate membro per gli attributi in una dimensione</span><span class="sxs-lookup"><span data-stu-id="a4606-145">Set Custom Member Formulas for Attributes in a Dimension</span></span>](bi-wizard-custom-member-formulas-for-attributes-in-a-dimension.md)  
  
  
