---
title: Chiamata di stored procedure | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: reference
helpviewer_keywords:
- calling stored procedures
- stored procedures [Analysis Services], calling
- MDX queries [Analysis Services]
- CALL statement
ms.assetid: 96a9660d-875b-4ee4-b339-90020b1d9895
author: minewiskan
ms.author: owend
ms.openlocfilehash: 5c9da6edef576a6ab25c183cbc87ff95cc056845
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87715848"
---
# <a name="calling-stored-procedures"></a><span data-ttu-id="aaa10-102">Chiamata di stored procedure</span><span class="sxs-lookup"><span data-stu-id="aaa10-102">Calling Stored Procedures</span></span>
  <span data-ttu-id="aaa10-103">È possibile chiamare stored procedure nel server o da un'applicazione client.</span><span class="sxs-lookup"><span data-stu-id="aaa10-103">Stored procedures can be called on the server or from client application.</span></span> <span data-ttu-id="aaa10-104">In entrambi i casi le stored procedure vengono sempre eseguite nel server, nel contesto del server o di un database.</span><span class="sxs-lookup"><span data-stu-id="aaa10-104">In either case, stored procedures always run on the server, either the context of the server or of a database.</span></span> <span data-ttu-id="aaa10-105">Non sono richieste autorizzazioni speciali per eseguire una stored procedure.</span><span class="sxs-lookup"><span data-stu-id="aaa10-105">There are no special permissions required to execute a stored procedure.</span></span> <span data-ttu-id="aaa10-106">Dopo che una stored procedure viene aggiunta da un assembly al contesto del server o del database, qualsiasi utente può eseguire la stored procedure purché il ruolo di quell'utente consenta le operazioni eseguite dalla stored procedure.</span><span class="sxs-lookup"><span data-stu-id="aaa10-106">Once a stored procedure is added by an assembly to the server or database context, any user can execute the stored procedure as long as the role for the user permits the actions performed by the stored procedure.</span></span>  
  
 <span data-ttu-id="aaa10-107">La chiamata di una stored procedure in MDX viene eseguita allo stesso modo della chiamata di una funzione MDX intrinseca.</span><span class="sxs-lookup"><span data-stu-id="aaa10-107">Calling a stored procedure in MDX is done in the same manner as calling an intrinsic MDX function.</span></span> <span data-ttu-id="aaa10-108">Per una stored procedure che non prevede parametri, vengono utilizzati il nome della stored procedure e una coppia vuota di parentesi:</span><span class="sxs-lookup"><span data-stu-id="aaa10-108">For a stored procedure that takes no parameters, the name of the procedure and an empty pair of parentheses are used, as shown here:</span></span>  
  
```  
MyStoredProcedure()  
```  
  
 <span data-ttu-id="aaa10-109">Se la stored procedure utilizza uno o più parametri, i parametri vengono specificati in ordine separati da virgole.</span><span class="sxs-lookup"><span data-stu-id="aaa10-109">If the stored procedure takes one or more parameters, then the parameters are supplied, in order, separated by commas.</span></span> <span data-ttu-id="aaa10-110">Nell'esempio seguente viene illustrata una stored procedure di esempio con tre parametri:</span><span class="sxs-lookup"><span data-stu-id="aaa10-110">The following example demonstrates a sample stored procedure with three parameters:</span></span>  
  
```  
MyStoredProcedure("Parameter1", 2, 800)  
```  
  
## <a name="calling-stored-procedures-in-mdx-queries"></a><span data-ttu-id="aaa10-111">Chiamata di stored procedure in query MDX</span><span class="sxs-lookup"><span data-stu-id="aaa10-111">Calling Stored Procedures in MDX Queries</span></span>  
 <span data-ttu-id="aaa10-112">In tutte le query MDX le stored procedure devono restituire il tipo sintatticamente corretto richiesto da un'espressione MDX.</span><span class="sxs-lookup"><span data-stu-id="aaa10-112">In all MDX queries, the stored procedure must return the syntactically correct type required by an MDX expression.</span></span> <span data-ttu-id="aaa10-113">In caso contrario, si verifica un errore MDX.</span><span class="sxs-lookup"><span data-stu-id="aaa10-113">If a stored procedure does not return the correct type, an MDX error occurs.</span></span> <span data-ttu-id="aaa10-114">Nell'esempio seguente vengono illustrate stored procedure che restituiscono un set, un membro e il risultato di un'operazione matematica.</span><span class="sxs-lookup"><span data-stu-id="aaa10-114">The following examples demonstrate stored procedures that return a set, a member, and the result of a mathematical operation.</span></span>  
  
### <a name="returning-a-set"></a><span data-ttu-id="aaa10-115">Restituzione di un set</span><span class="sxs-lookup"><span data-stu-id="aaa10-115">Returning a Set</span></span>  
 <span data-ttu-id="aaa10-116">Negli esempi seguenti viene implementata una stored procedure chiamata MySproc che restituisce un set.</span><span class="sxs-lookup"><span data-stu-id="aaa10-116">The following examples implement a stored procedure, called MySproc, that returns a set.</span></span> <span data-ttu-id="aaa10-117">Nel primo esempio MySproc restituisce il set direttamente nell'espressione SELECT.</span><span class="sxs-lookup"><span data-stu-id="aaa10-117">In the first example, MySproc returns the set directly in the SELECT expression.</span></span> <span data-ttu-id="aaa10-118">Nei due esempi successivi MySproc restituisce il set come un argomento delle funzioni Crossjoin e DrilldownLevel.</span><span class="sxs-lookup"><span data-stu-id="aaa10-118">In the second two examples, MySproc returns the set as an argument for the Crossjoin and DrilldownLevel functions.</span></span>  
  
```  
SELECT MySetProcedure(a,b,c) ON 0 FROM Sales  
SELECT Crossjoin(MySetProcedure(a,b,c)) ON 0 FROM Sales  
SELECT DrilldownLevel(MySetProcedure(a,b,c)) ON 0 FROM Sales  
```  
  
### <a name="returning-a-member"></a><span data-ttu-id="aaa10-119">Restituzione di un membro</span><span class="sxs-lookup"><span data-stu-id="aaa10-119">Returning a Member</span></span>  
 <span data-ttu-id="aaa10-120">Nell'esempio seguente viene visualizzata una funzione MySproc che restituisce un membro:</span><span class="sxs-lookup"><span data-stu-id="aaa10-120">The following example shows a function MySproc function that returns a member:</span></span>  
  
```  
SELECT Descendants(MySproc(a,b,c),3) ON 0 FROM Sales  
```  
  
### <a name="returning-the-result-of-a-math-operation"></a><span data-ttu-id="aaa10-121">Restituzione del risultato di un'operazione matematica</span><span class="sxs-lookup"><span data-stu-id="aaa10-121">Returning the Result of a Math Operation</span></span>  
  
```  
SELECT Country.Members on 0, MySproc(Measures.Sales) ON 1 FROM Sales  
```  
  
## <a name="calling-stored-procedures-with-the-call-statement"></a><span data-ttu-id="aaa10-122">Chiamata di stored procedure con l'istruzione Call</span><span class="sxs-lookup"><span data-stu-id="aaa10-122">Calling Stored Procedures with the Call Statement</span></span>  
 <span data-ttu-id="aaa10-123">È possibile chiamare stored procedure al di fuori del contesto di una query MDX utilizzando l'istruzione MDX `Call`.</span><span class="sxs-lookup"><span data-stu-id="aaa10-123">Stored procedures can be called outside of the context of an MDX query using the MDX `Call` statement.</span></span>  
  
 <span data-ttu-id="aaa10-124">È possibile utilizzare questo metodo per creare un'istanza degli effetti collaterali di una query archiviata oppure per l'applicazione per ottenere i risultati di una query archiviata.</span><span class="sxs-lookup"><span data-stu-id="aaa10-124">You can use this method to either instantiate the side effects of a stored query or for the application to get the results of a stored query.</span></span> <span data-ttu-id="aaa10-125">L'istruzione `Call` viene in genere utilizzata per eseguire tramite AMO (Analysis Management Objects) funzioni amministrative che non restituiscono risultati.</span><span class="sxs-lookup"><span data-stu-id="aaa10-125">A common use of the `Call` statement would be to use Analysis Management Objects (AMO) to perform administrative functions that do not have a return result.</span></span> <span data-ttu-id="aaa10-126">Ad esempio, per chiamare una stored procedure è possibile utilizzare i comandi seguenti:</span><span class="sxs-lookup"><span data-stu-id="aaa10-126">For example, the following command calls a stored procedure:</span></span>  
  
```  
Call MyStoredProcedure(a,b,c)  
```  
  
 <span data-ttu-id="aaa10-127">Il solo tipo supportato restituito da una stored procedure in un'istruzione `Call` è un set di righe.</span><span class="sxs-lookup"><span data-stu-id="aaa10-127">The only supported type returned from stored procedure in a `Call` statement is a rowset.</span></span> <span data-ttu-id="aaa10-128">La serializzazione di un set di righe viene definita tramite XML for Analysis.</span><span class="sxs-lookup"><span data-stu-id="aaa10-128">The serialization for a rowset is defined by XML for Analysis.</span></span> <span data-ttu-id="aaa10-129">Se una stored procedure in un'istruzione `Call` restituisce qualsiasi altro tipo, viene ignorata e non viene restituita in XML all'applicazione chiamante.</span><span class="sxs-lookup"><span data-stu-id="aaa10-129">If a stored procedure in a `Call` statement returns any other type, it is ignored and not returned in XML to the calling application.</span></span> <span data-ttu-id="aaa10-130">Per ulteriori informazioni sui set di righe di schema di XML for Analysis, vedere l'argomento corrispondente.</span><span class="sxs-lookup"><span data-stu-id="aaa10-130">For more information about XML for Analysis rowsets, see, XML for Analysis Schema Rowsets.</span></span>  
  
 <span data-ttu-id="aaa10-131">Se una stored procedure restituisce un set di righe .NET, [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] converte il risultato nel server in un set di righe XML for Analysis.</span><span class="sxs-lookup"><span data-stu-id="aaa10-131">If a stored procedure returns a .NET rowset, [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] converts the result on the server to an XML for Analysis rowset.</span></span> <span data-ttu-id="aaa10-132">Il set di righe XML for Analysis viene sempre restituito da una stored procedure nella funzione `Call`.</span><span class="sxs-lookup"><span data-stu-id="aaa10-132">The XML for Analysis rowset is always returned by a stored procedure in the `Call` function.</span></span> <span data-ttu-id="aaa10-133">Se un set di dati contiene caratteristiche che non possono essere espresse nel set di righe di XML for Analysis, si verifica un errore.</span><span class="sxs-lookup"><span data-stu-id="aaa10-133">If a dataset contains features that cannot be expressed in the XML for Analysis rowset, a failure results.</span></span>  
  
 <span data-ttu-id="aaa10-134">Le stored procedure che restituiscono valori void, ad esempio subroutine di Visual Basic, possono essere utilizzate con la parola chiave CALL.</span><span class="sxs-lookup"><span data-stu-id="aaa10-134">Procedures that return void values (for example, subroutines in Visual Basic) can also be employed with the CALL keyword.</span></span> <span data-ttu-id="aaa10-135">Se ad esempio si desidera utilizzare la funzione MyVoidFunction() in un'istruzione MDX, è necessario utilizzare la sintassi seguente:</span><span class="sxs-lookup"><span data-stu-id="aaa10-135">If, for example, you wanted to use the function MyVoidFunction() in an MDX statement, the following syntax would be employed:</span></span>  
  
```  
CALL(MyVoidFunction)  
```  
  
## <a name="see-also"></a><span data-ttu-id="aaa10-136">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="aaa10-136">See Also</span></span>  
 <span data-ttu-id="aaa10-137">[Gestione di assembly di modelli multidimensionali](../multidimensional-models/multidimensional-model-assemblies-management.md) </span><span class="sxs-lookup"><span data-stu-id="aaa10-137">[Multidimensional Model Assemblies Management](../multidimensional-models/multidimensional-model-assemblies-management.md) </span></span>  
 [<span data-ttu-id="aaa10-138">Definizione di stored procedure</span><span class="sxs-lookup"><span data-stu-id="aaa10-138">Defining Stored Procedures</span></span>](../multidimensional-models-extending-olap-stored-procedures/defining-stored-procedures.md)  
  
  
