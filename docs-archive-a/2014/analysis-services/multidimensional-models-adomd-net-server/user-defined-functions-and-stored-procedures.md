---
title: Funzioni definite dall'utente e stored procedure | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: reference
helpviewer_keywords:
- stored procedures [ADOMD.NET]
- ADOMD.NET, user defined functions
- user defined functions [ADOMD.NET]
- ADOMD.NET, UDFs
- ADOMD.NET, stored procedures
ms.assetid: 07e8aa47-37d4-4bbc-8bff-49e422d12897
author: minewiskan
ms.author: owend
ms.openlocfilehash: a49aa41d158bf2c9fd1ebb1a711d6ff35c0df98b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87711123"
---
# <a name="user-defined-functions-and-stored-procedures"></a><span data-ttu-id="e1c2b-102">Funzioni definite dall'utente e stored procedure</span><span class="sxs-lookup"><span data-stu-id="e1c2b-102">User Defined Functions and Stored Procedures</span></span>
  <span data-ttu-id="e1c2b-103">Con gli oggetti del server ADOMD.NET è possibile creare funzioni definite dall'utente o stored procedure per [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] che interagiscono con i metadati e i dati dal server.</span><span class="sxs-lookup"><span data-stu-id="e1c2b-103">With ADOMD.NET server objects, you can create user defined function (UDF) or stored procedures for [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] that interact with metadata and data from the server.</span></span> <span data-ttu-id="e1c2b-104">Questi metodi in-process vengono chiamati tramite istruzioni MDX (Multidimensional Expressions) o DMX (Data Mining Extensions) per fornire funzionalità aggiunte senza le latenze associate alle comunicazioni di rete.</span><span class="sxs-lookup"><span data-stu-id="e1c2b-104">These in-process methods are called through Multidimensional Expressions (MDX) or Data Mining Extensions (DMX) statements to provide added functionality without the latencies associated with network communications.</span></span>  
  
## <a name="udf-examples"></a><span data-ttu-id="e1c2b-105">Esempi di funzioni definite dall'utente</span><span class="sxs-lookup"><span data-stu-id="e1c2b-105">UDF Examples</span></span>  
 <span data-ttu-id="e1c2b-106">Una funzione definita dall'utente è un metodo che può essere chiamato nel contesto di un'istruzione MDX o DMX, accettare un numero qualsiasi di parametri e restituire qualsiasi tipo di dati.</span><span class="sxs-lookup"><span data-stu-id="e1c2b-106">A UDF is a method that can be called in the context of an MDX or DMX statement, can take any number of parameters, and can return any type of data.</span></span>  
  
 <span data-ttu-id="e1c2b-107">Una funzione definita dall'utente creata utilizzando MDX è analoga a una creata per DMX.</span><span class="sxs-lookup"><span data-stu-id="e1c2b-107">A UDF created using MDX is similar to one created for DMX.</span></span> <span data-ttu-id="e1c2b-108">La differenza principale è che alcune proprietà dell'oggetto [Microsoft. AnalysisServices. AdomdServer. Context](/previous-versions/sql/sql-server-2014/ms143353(v=sql.120)) , ad esempio le proprietà [Microsoft. AnalysisServices. AdomdServer. Context. CURRENTCUBE \*](/previous-versions/sql/sql-server-2014/ms137081(v=sql.120)) e [Microsoft. AnalysisServices. AdomdServer. Context. CurrentMiningModel \*](/previous-versions/sql/sql-server-2014/ms137178(v=sql.120)) , sono disponibili solo per un linguaggio di scripting o l'altro.</span><span class="sxs-lookup"><span data-stu-id="e1c2b-108">The main difference is that certain properties of the [Microsoft.AnalysisServices.AdomdServer.Context](/previous-versions/sql/sql-server-2014/ms143353(v=sql.120)) object, such as the [Microsoft.AnalysisServices.AdomdServer.Context.CurrentCube\*](/previous-versions/sql/sql-server-2014/ms137081(v=sql.120)) and [Microsoft.AnalysisServices.AdomdServer.Context.CurrentMiningModel\*](/previous-versions/sql/sql-server-2014/ms137178(v=sql.120)) properties, are available only for one scripting language or the other.</span></span>  
  
 <span data-ttu-id="e1c2b-109">Negli esempi seguenti viene illustrato come utilizzare una funzione definita dall'utente per restituire una descrizione del nodo e tuple di filtri e per applicare un filtro a una tupla.</span><span class="sxs-lookup"><span data-stu-id="e1c2b-109">The following examples show how to use a UDF to return a node description, filter tuples, and apply a filter to a tuple.</span></span>  
  
### <a name="returning-a-node-description"></a><span data-ttu-id="e1c2b-110">Restituzione di una descrizione del nodo</span><span class="sxs-lookup"><span data-stu-id="e1c2b-110">Returning a Node Description</span></span>  
 <span data-ttu-id="e1c2b-111">Nell'esempio seguente viene creata una funzione definita dall'utente che restituisce la descrizione per un nodo specificato.</span><span class="sxs-lookup"><span data-stu-id="e1c2b-111">The following example creates a UDF that returns the node description for a specified node.</span></span> <span data-ttu-id="e1c2b-112">La funzione definita dall'utente utilizza il contesto corrente in cui è in esecuzione e recupera il nodo dal modello di data mining corrente tramite una clausola FROM DMX.</span><span class="sxs-lookup"><span data-stu-id="e1c2b-112">The UDF uses the current context in which it is being run, and uses a DMX FROM clause to retrieve the node from the current mining model.</span></span>  
  
```  
public string GetNodeDescription(string nodeUniqueName)  
{  
   return Context.CurrentMiningModel.GetNodeFromUniqueName(nodeUniqueName).Description;  
}  
```  
  
 <span data-ttu-id="e1c2b-113">Una volta distribuito, l'esempio di funzione definita dall'utente precedente può essere chiamato dall'espressione DMX seguente, che recupera il nodo relativo alla stima più probabile.</span><span class="sxs-lookup"><span data-stu-id="e1c2b-113">Once deployed, the previous UDF example can be called by the following DMX expression, which retrieves the most-likely prediction node.</span></span> <span data-ttu-id="e1c2b-114">La descrizione contiene informazioni che specificano le condizioni che costituiscono il nodo relativo alla stima.</span><span class="sxs-lookup"><span data-stu-id="e1c2b-114">The description contains information that describes the conditions that make up the prediction node.</span></span>  
  
```  
select Cluster(), SampleAssembly.GetNodeDescription( PredictNodeId(Cluster()) ) FROM [Customer Clusters]  
```  
  
### <a name="returning-tuples"></a><span data-ttu-id="e1c2b-115">Restituzione di tuple</span><span class="sxs-lookup"><span data-stu-id="e1c2b-115">Returning Tuples</span></span>  
 <span data-ttu-id="e1c2b-116">Nell'esempio seguente vengono accettati un set e un conteggio di risultati, vengono recuperate tuple dal set in modo causale e viene restituito un subset finale.</span><span class="sxs-lookup"><span data-stu-id="e1c2b-116">The following example takes a set and a return count, and randomly retrieves tuples from the set, returning a final subset:</span></span>  
  
```  
public Set RandomSample(Set set, int returnCount)  
{  
   //Return the original set if there are fewer tuples  
   //in the set than the number requested.  
   if (set.Tuples.Count <= returnCount)  
      return set;  
  
   System.Random r = new System.Random();  
   SetBuilder returnSet = new SetBuilder();  
  
   //Retrieve random tuples until the return set is filled.  
   int i = set.Tuples.Count;  
   foreach (Tuple t in set.Tuples)  
   {  
      if (r.Next(i) < returnCount)  
      {  
         returnCount--;  
         returnSet.Add(t);  
      }  
      i--;  
      //Stop the loop if we have enough tuples.  
      if (returnCount == 0)  
         break;  
   }  
   return returnSet.ToSet();  
}  
```  
  
 <span data-ttu-id="e1c2b-117">L'esempio precedente viene chiamato nell'esempio MDX seguente,</span><span class="sxs-lookup"><span data-stu-id="e1c2b-117">The previous example is called in the following MDX example.</span></span> <span data-ttu-id="e1c2b-118">In questo esempio MDX vengono recuperate cinque Stati o province casuali dal database **Adventure Works** .</span><span class="sxs-lookup"><span data-stu-id="e1c2b-118">In this MDX example, five random states or provinces are retrieved from the **Adventure Works** database.</span></span>  
  
```  
SELECT SampleAssembly.RandomSample([Geography].[State-Province].Members, 5) on ROWS,   
[Date].[Calendar].[Calendar Year] on COLUMNS  
FROM [Adventure Works]  
WHERE [Measures].[Reseller Freight Cost]  
```  
  
### <a name="applying-a-filter-to-a-tuple"></a><span data-ttu-id="e1c2b-119">Applicazione di un filtro a una tupla</span><span class="sxs-lookup"><span data-stu-id="e1c2b-119">Applying a Filter to a Tuple</span></span>  
 <span data-ttu-id="e1c2b-120">Nell'esempio seguente viene creata una funzione definita dall'utente che accetta un set e applica un filtro a ogni tupla del set tramite l'oggetto Expression.</span><span class="sxs-lookup"><span data-stu-id="e1c2b-120">In the following example, a UDF is defined that takes a set, and applies a filter to each tuple in the set, using the Expression object.</span></span> <span data-ttu-id="e1c2b-121">Tutte le tuple conformi al filtro verranno aggiunte a un set restituito.</span><span class="sxs-lookup"><span data-stu-id="e1c2b-121">Any tuples that conform to the filter will be added to a set that is returned.</span></span>  
  
 [!code-csharp[Adomd.NetServer#FilterSet](../../snippets/csharp/SQL14/adomd.net/adomd.netserver/cs/class1.cs#filterset)]  
  
 <span data-ttu-id="e1c2b-122">L'esempio precedente viene chiamato nell'esempio MDX seguente che filtra il set in base alle città i cui nomi iniziano con la lettera "A".</span><span class="sxs-lookup"><span data-stu-id="e1c2b-122">The previous example is called in the following MDX example, which filters the set to cities with names beginning with 'A'.</span></span>  
  
```  
Select Measures.Members on Rows,  
SampleAssembly.FilterSet([Customer].[Customer Geography].[City], "[Customer].[Customer Geography].[City].CurrentMember.Name < 'B'") on Columns  
From [Adventure Works]  
```  
  
## <a name="stored-procedure-example"></a><span data-ttu-id="e1c2b-123">Esempio di stored procedure</span><span class="sxs-lookup"><span data-stu-id="e1c2b-123">Stored Procedure Example</span></span>  
 <span data-ttu-id="e1c2b-124">Nell'esempio seguente una stored procedure basata su MDX utilizza AMO per creare partizioni per Internet Sales, qualora siano necessarie.</span><span class="sxs-lookup"><span data-stu-id="e1c2b-124">In the following example, an MDX-based stored procedure uses AMO to create partitions, if needed, for Internet Sales.</span></span>  
  
 [!code-csharp[Adomd.NetServer#CreateInternetSalesMeasureGroupPartitions](../../snippets/csharp/SQL14/adomd.net/adomd.netserver/cs/class1.cs#createinternetsalesmeasuregrouppartitions)]  
  
  
