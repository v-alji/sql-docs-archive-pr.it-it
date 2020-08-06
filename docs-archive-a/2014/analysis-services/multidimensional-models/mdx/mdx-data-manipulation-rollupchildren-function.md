---
title: Utilizzo della funzione RollupChildren (MDX) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- queries [MDX], RollupChildren function
- RollupChildren function
- custom member properties [MDX]
- IIf function
ms.assetid: 03c624d4-f277-451d-9995-623a07ea2f86
author: minewiskan
ms.author: owend
ms.openlocfilehash: 341468d521cebe1fda33d73ea999f3b6571cb01e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87721920"
---
# <a name="working-with-the-rollupchildren-function-mdx"></a><span data-ttu-id="c9469-102">Utilizzo della funzione RollupChildren (MDX)</span><span class="sxs-lookup"><span data-stu-id="c9469-102">Working with the RollupChildren Function (MDX)</span></span>
  <span data-ttu-id="c9469-103">La funzione MDX (Multidimensional Expressions) [RollupChildren](/sql/mdx/rollupchildren-mdx) [script for Search and Replace] esegue il rollup degli elementi figlio di un membro, applicando un operatore unario diverso a ogni elemento figlio e restituisce il valore di questo rollup sotto forma di numero.</span><span class="sxs-lookup"><span data-stu-id="c9469-103">The Multidimensional Expressions (MDX) [RollupChildren](/sql/mdx/rollupchildren-mdx) [Script for Search and Replace] function rolls up the children of a member, applying a different unary operator to each child, and returns the value of this rollup as a number.</span></span> <span data-ttu-id="c9469-104">L'operatore unario utilizzato può essere specificato da una proprietà del membro associata al membro figlio oppure può essere costituito da un'espressione stringa fornita direttamente alla funzione.</span><span class="sxs-lookup"><span data-stu-id="c9469-104">The unary operator can be supplied by a member property associated with the child member, or the operator can be a string expression provided directly to the function.</span></span>  
  
## <a name="rollupchildren-function-examples"></a><span data-ttu-id="c9469-105">Esempi sulla funzione RollupChildren</span><span class="sxs-lookup"><span data-stu-id="c9469-105">RollupChildren Function Examples</span></span>  
 <span data-ttu-id="c9469-106">L'utilizzo della funzione `RollupChildren` nelle istruzioni MDX (Multidimensional Expressions) è semplice da spiegare, ma questa funzione può avere un'ampia gamma di effetti sulle query MDX.</span><span class="sxs-lookup"><span data-stu-id="c9469-106">The use of the `RollupChildren` function in Multidimensional Expressions (MDX) statements is simple to explain, but the effect of this function on MDX queries can be wide-ranging.</span></span>  
  
 <span data-ttu-id="c9469-107">L'effetto della funzione `RollupChildren` viene rilevato nelle query MDX progettate per l'esecuzione dell'analisi selettiva sui dati esistenti di un cubo.</span><span class="sxs-lookup"><span data-stu-id="c9469-107">The effect of the `RollupChildren` function occurs in MDX queries designed to perform selective analysis on existing cube data.</span></span> <span data-ttu-id="c9469-108">Nella tabella seguente è ad esempio riportato un elenco di membri figlio per il membro padre Net Sales, con i relativi operatori unari (rappresentati dalla proprietà `UNARY_OPERATOR` del membro) indicati tra parentesi.</span><span class="sxs-lookup"><span data-stu-id="c9469-108">For example, the following table contains a list of child members for the Net Sales parent member, with their unary operators (represented by the `UNARY_OPERATOR` member property) shown in parentheses.</span></span>  
  
|<span data-ttu-id="c9469-109">Membro padre</span><span class="sxs-lookup"><span data-stu-id="c9469-109">Parent member</span></span>|<span data-ttu-id="c9469-110">Membro figlio</span><span class="sxs-lookup"><span data-stu-id="c9469-110">Child member</span></span>|  
|-------------------|------------------|  
|<span data-ttu-id="c9469-111">Net Sales</span><span class="sxs-lookup"><span data-stu-id="c9469-111">Net Sales</span></span>|<span data-ttu-id="c9469-112">Domestic Sales (+)</span><span class="sxs-lookup"><span data-stu-id="c9469-112">Domestic Sales (+)</span></span><br /><br /> <span data-ttu-id="c9469-113">Domestic Returns (-)</span><span class="sxs-lookup"><span data-stu-id="c9469-113">Domestic Returns (-)</span></span><br /><br /> <span data-ttu-id="c9469-114">Foreign Sales (+)</span><span class="sxs-lookup"><span data-stu-id="c9469-114">Foreign Sales (+)</span></span><br /><br /> <span data-ttu-id="c9469-115">Foreign Returns (-)</span><span class="sxs-lookup"><span data-stu-id="c9469-115">Foreign Returns (-)</span></span>|  
  
 <span data-ttu-id="c9469-116">Il membro padre Net Sales specifica le vendite nette totali meno i valori delle vendite nazionali ed estere lorde, sottraendo i resi nazionali ed esteri durante il rollup.</span><span class="sxs-lookup"><span data-stu-id="c9469-116">The Net Sales parent member currently provides a total of net sales minus the gross domestic and foreign sales values, with the domestic and foreign returns subtracted as part of the rollup.</span></span>  
  
 <span data-ttu-id="c9469-117">Si desidera tuttavia fornire una previsione semplice e rapida delle vendite lorde nazionali ed estere maggiorata del 10%, ignorando i resi nazionali ed esteri.</span><span class="sxs-lookup"><span data-stu-id="c9469-117">However, you want to provide a quick and easy forecast of domestic and foreign gross sales plus 10%, ignoring the domestic and foreign returns.</span></span> <span data-ttu-id="c9469-118">Per calcolare tale valore, è possibile utilizzare la funzione `RollupChildren` in uno dei due modi seguenti: con una proprietà personalizzata del membro o con la funzione `IIf`.</span><span class="sxs-lookup"><span data-stu-id="c9469-118">To calculate this value, you can use the `RollupChildren` function in one of two ways: with a custom member property or with the `IIf` function.</span></span>  
  
### <a name="using-a-custom-member-property"></a><span data-ttu-id="c9469-119">Utilizzo di una proprietà personalizzata del membro</span><span class="sxs-lookup"><span data-stu-id="c9469-119">Using a Custom Member Property</span></span>  
 <span data-ttu-id="c9469-120">Se il calcolo del rollup deve essere eseguito di frequente, è consigliabile creare una proprietà di membro in cui memorizzare l'operatore da utilizzare per ogni membro figlio per una funzione specifica.</span><span class="sxs-lookup"><span data-stu-id="c9469-120">If the rollup calculation is to be a frequently performed operation, one method is to create a member property that stores the operator that will be used for each child for a specific function.</span></span> <span data-ttu-id="c9469-121">Nella tabella seguente sono indicati gli operatori unari validi e vengono descritti i risultati previsti.</span><span class="sxs-lookup"><span data-stu-id="c9469-121">The following table displays valid unary operators and describes the expected result.</span></span>  
  
|<span data-ttu-id="c9469-122">Operatore</span><span class="sxs-lookup"><span data-stu-id="c9469-122">Operator</span></span>|<span data-ttu-id="c9469-123">Risultato</span><span class="sxs-lookup"><span data-stu-id="c9469-123">Result</span></span>|  
|--------------|------------|  
|+|<span data-ttu-id="c9469-124">totale = totale + membro figlio corrente</span><span class="sxs-lookup"><span data-stu-id="c9469-124">total = total + current child</span></span>|  
|-|<span data-ttu-id="c9469-125">totale = totale - membro figlio corrente</span><span class="sxs-lookup"><span data-stu-id="c9469-125">total = total - current child</span></span>|  
|*|<span data-ttu-id="c9469-126">totale = totale \* membro figlio corrente</span><span class="sxs-lookup"><span data-stu-id="c9469-126">total = total \* current child</span></span>|  
|/|<span data-ttu-id="c9469-127">totale = totale / membro figlio corrente</span><span class="sxs-lookup"><span data-stu-id="c9469-127">total = total / current child</span></span>|  
|~|<span data-ttu-id="c9469-128">Il membro figlio non viene utilizzato nel rollup</span><span class="sxs-lookup"><span data-stu-id="c9469-128">Child is not used in the rollup.</span></span> <span data-ttu-id="c9469-129">e il suo valore viene ignorato.</span><span class="sxs-lookup"><span data-stu-id="c9469-129">The child's value is ignored.</span></span>|  
  
 <span data-ttu-id="c9469-130">È ad esempio possibile creare una proprietà di membro denominata `SALES_OPERATOR` alla quale possono essere assegnati gli operatori unari indicati nella tabella seguente.</span><span class="sxs-lookup"><span data-stu-id="c9469-130">For example, a member property called `SALES_OPERATOR` could be created, and the following unary operators would be assigned to that member property, as shown in the following table.</span></span>  
  
|<span data-ttu-id="c9469-131">Membro padre</span><span class="sxs-lookup"><span data-stu-id="c9469-131">Parent member</span></span>|<span data-ttu-id="c9469-132">Membro figlio</span><span class="sxs-lookup"><span data-stu-id="c9469-132">Child member</span></span>|  
|-------------------|------------------|  
|<span data-ttu-id="c9469-133">Net Sales</span><span class="sxs-lookup"><span data-stu-id="c9469-133">Net Sales</span></span>|<span data-ttu-id="c9469-134">Domestic Sales (+)</span><span class="sxs-lookup"><span data-stu-id="c9469-134">Domestic Sales (+)</span></span><br /><br /> <span data-ttu-id="c9469-135">Domestic Returns (~)</span><span class="sxs-lookup"><span data-stu-id="c9469-135">Domestic Returns (~)</span></span><br /><br /> <span data-ttu-id="c9469-136">Foreign Sales (+)</span><span class="sxs-lookup"><span data-stu-id="c9469-136">Foreign Sales (+)</span></span><br /><br /> <span data-ttu-id="c9469-137">Foreign Returns (~)</span><span class="sxs-lookup"><span data-stu-id="c9469-137">Foreign Returns (~)</span></span>|  
  
 <span data-ttu-id="c9469-138">Con questa nuova proprietà di membro, l'istruzione MDX seguente esegue l'operazione di stima delle vendite lorde in modo rapido ed efficace, ignorando i resi nazionali ed esteri:</span><span class="sxs-lookup"><span data-stu-id="c9469-138">With this new member property, the following MDX statement would perform the gross sales estimate operation quickly and efficiently (ignoring Foreign and Domestic returns):</span></span>  
  
```  
RollupChildren([Net Sales], [Net Sales].CurrentMember.Properties("SALES_OPERATOR")) * 1.1  
```  
  
 <span data-ttu-id="c9469-139">Quando la funzione viene chiamata, il valore di ogni membro figlio viene applicato a un totale utilizzando l'operatore archiviato nella proprietà del membro.</span><span class="sxs-lookup"><span data-stu-id="c9469-139">When the function is called, the value of each child is applied to a total using the operator stored in the member property.</span></span> <span data-ttu-id="c9469-140">I membri relativi ai resi nazionali ed esteri vengono ignorati e il totale di rollup restituito dalla funzione `RollupChildren` viene moltiplicato per 1,1.</span><span class="sxs-lookup"><span data-stu-id="c9469-140">The members for domestic and foreign returns are ignored, and the rollup total returned by the `RollupChildren` function is multiplied by 1.1.</span></span>  
  
### <a name="using-the-iif-function"></a><span data-ttu-id="c9469-141">Utilizzo della funzione IIf</span><span class="sxs-lookup"><span data-stu-id="c9469-141">Using the IIf Function</span></span>  
 <span data-ttu-id="c9469-142">Se l'operazione di esempio non è comune o si applica solo a una query MDX, è possibile utilizzare la funzione [IIf](/sql/mdx/iif-mdx) con la `RollupChildren` funzione per ottenere lo stesso risultato.</span><span class="sxs-lookup"><span data-stu-id="c9469-142">If the example operation is not commonplace or if the operation applies only to one MDX query, the [IIf](/sql/mdx/iif-mdx) function can be used with the `RollupChildren` function to provide the same result.</span></span> <span data-ttu-id="c9469-143">La query MDX seguente genera lo stesso risultato dell'esempio precedente, ma senza ricorrere a una proprietà di membro personalizzata:</span><span class="sxs-lookup"><span data-stu-id="c9469-143">The following MDX query provides the same result as the earlier MDX example, but does so without resorting to the use of a custom member property:</span></span>  
  
```  
RollupChildren([Net Sales], IIf([Net Sales].CurrentMember.Properties("UNARY_OPERATOR") = "-", "~", [Net Sales].CurrentMember.Properties("UNARY_OPERATOR))) * 1.1  
```  
  
 <span data-ttu-id="c9469-144">L'istruzione MDX esamina l'operatore unario del membro figlio.</span><span class="sxs-lookup"><span data-stu-id="c9469-144">The MDX statement examines the unary operator of the child member.</span></span> <span data-ttu-id="c9469-145">Se l'operatore unario viene utilizzato per eseguire una sottrazione, ad esempio quando sono presenti resi nazionali ed esteri, la funzione `IIf` sostituisce l'operatore unario ~,</span><span class="sxs-lookup"><span data-stu-id="c9469-145">If the unary operator is used for subtraction (as in the case with the domestic and foreign returns members), the `IIf` function substitutes the tilde (~) unary operator.</span></span> <span data-ttu-id="c9469-146">in caso contrario la funzione `IIf` utilizza l'operatore unario del membro figlio.</span><span class="sxs-lookup"><span data-stu-id="c9469-146">Otherwise, the `IIf` function uses the unary operator of the child member.</span></span> <span data-ttu-id="c9469-147">Il totale di rollup restituito viene infine moltiplicato per 1,1 per determinare il valore della stima per le vendite nazionali ed estere lorde.</span><span class="sxs-lookup"><span data-stu-id="c9469-147">Finally, the returned rollup total is then multiplied by 1.1 to provide the domestic and foreign gross sales forecast value.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c9469-148">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c9469-148">See Also</span></span>  
 [<span data-ttu-id="c9469-149">Manipolazione dei dati &#40;MDX&#41;</span><span class="sxs-lookup"><span data-stu-id="c9469-149">Manipulating Data &#40;MDX&#41;</span></span>](mdx-data-manipulation-manipulating-data.md)  
  
  
