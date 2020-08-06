---
title: Funzionalità del server ADOMD.NET | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: reference
helpviewer_keywords:
- functionality [ADOMD.NET]
- ADOMD.NET, functionality
ms.assetid: b74c6957-3f64-4e09-aa09-d06ee93f82fa
author: minewiskan
ms.author: owend
ms.openlocfilehash: f00215c6bcc0104c920be29e0837288a469b252e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87712599"
---
# <a name="adomdnet-server-functionality"></a><span data-ttu-id="cd646-102">Funzionalità server di ADOMD.NET</span><span class="sxs-lookup"><span data-stu-id="cd646-102">ADOMD.NET Server Functionality</span></span>
  <span data-ttu-id="cd646-103">Tutti gli oggetti server ADOMD.NET forniscono l'accesso in sola lettura ai dati e i metadati presenti nel server.</span><span class="sxs-lookup"><span data-stu-id="cd646-103">All ADOMD.NET server objects provide read-only access to the data and metadata on the server.</span></span> <span data-ttu-id="cd646-104">Per recuperare i dati e i metadati, viene utilizzato il modello a oggetti server di ADOMD.NET poiché il modello a oggetti server non supporta i set di righe dello schema.</span><span class="sxs-lookup"><span data-stu-id="cd646-104">To retrieve data and metadata, you use the ADOMD.NET server object model as the server object model does not support schema rowsets.</span></span>  
  
 <span data-ttu-id="cd646-105">Con gli oggetti del server ADOMD.NET è possibile creare una funzione definita dall'utente (UDF) o una stored procedure per [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="cd646-105">With ADOMD.NET server objects, you can create a user defined function (UDF) or a stored procedure for [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)].</span></span> <span data-ttu-id="cd646-106">Tali metodi in-process vengono chiamati tramite istruzioni di query create in linguaggi diversi, ad esempio MDX (Multidimensional Expressions), DMX (Data Mining Extensions) o SQL.</span><span class="sxs-lookup"><span data-stu-id="cd646-106">These in-process methods are called through query statements created in languages such as Multidimensional Expressions (MDX), Data Mining Extensions (DMX), or SQL.</span></span> <span data-ttu-id="cd646-107">Tali metodi forniscono inoltre funzionalità aggiunte senza le latenze associate alle comunicazioni della rete.</span><span class="sxs-lookup"><span data-stu-id="cd646-107">These in-process methods also provide added functionality without the latencies associated with network communications.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="cd646-108">L'oggetto [Microsoft. AnalysisServices. AdomdServer. AdomdCommand](/previous-versions/sql/sql-server-2014/ms143286(v=sql.120)) supporta solo DMX.</span><span class="sxs-lookup"><span data-stu-id="cd646-108">The [Microsoft.AnalysisServices.AdomdServer.AdomdCommand](/previous-versions/sql/sql-server-2014/ms143286(v=sql.120)) object only supports DMX.</span></span>  
  
## <a name="what-is-a-udf"></a><span data-ttu-id="cd646-109">Funzioni definite dall'utente</span><span class="sxs-lookup"><span data-stu-id="cd646-109">What is a UDF?</span></span>  
 <span data-ttu-id="cd646-110">Una funzione *definita dall'utente* è un metodo con le caratteristiche seguenti:</span><span class="sxs-lookup"><span data-stu-id="cd646-110">A *UDF* is a method that has the following characteristics:</span></span>  
  
-   <span data-ttu-id="cd646-111">Possibilità di essere chiamata nel contesto di una query.</span><span class="sxs-lookup"><span data-stu-id="cd646-111">You can call the UDF in the context of a query.</span></span>  
  
-   <span data-ttu-id="cd646-112">Possibilità di accettare un numero qualsiasi di parametri.</span><span class="sxs-lookup"><span data-stu-id="cd646-112">The UDF can take any number of parameters.</span></span>  
  
-   <span data-ttu-id="cd646-113">Possibilità di restituire diversi tipi di dati.</span><span class="sxs-lookup"><span data-stu-id="cd646-113">The UDF can return various types of data.</span></span>  
  
 <span data-ttu-id="cd646-114">Nell'esempio seguente viene utilizzata la funzione definita dall'utente fittizia `FinalSalesNumber`:</span><span class="sxs-lookup"><span data-stu-id="cd646-114">The following example uses the fictional UDF, `FinalSalesNumber`:</span></span>  
  
```  
SELECT SalesPerson.Name ON ROWS,  
       FinalSalesNumber() ON COLUMNS  
FROM SalesModel  
```  
  
## <a name="what-is-a-stored-procedure"></a><span data-ttu-id="cd646-115">Stored procedure</span><span class="sxs-lookup"><span data-stu-id="cd646-115">What is a Stored Procedure?</span></span>  
 <span data-ttu-id="cd646-116">Un *stored procedure* è un metodo con le caratteristiche seguenti:</span><span class="sxs-lookup"><span data-stu-id="cd646-116">A *stored procedure* is a method that has the following characteristics:</span></span>  
  
-   <span data-ttu-id="cd646-117">È possibile chiamare un stored procedure autonomamente con l'istruzione [Call](/sql/mdx/mdx-data-manipulation-call) MDX.</span><span class="sxs-lookup"><span data-stu-id="cd646-117">You call a stored procedure on its own with the MDX [CALL](/sql/mdx/mdx-data-manipulation-call) statement.</span></span>  
  
-   <span data-ttu-id="cd646-118">Possibilità di accettare un numero qualsiasi di parametri.</span><span class="sxs-lookup"><span data-stu-id="cd646-118">A stored procedure can take any number of parameters.</span></span>  
  
-   <span data-ttu-id="cd646-119">Possibilità di restituire un set di dati, un oggetto `IDataReader` oppure un risultato vuoto.</span><span class="sxs-lookup"><span data-stu-id="cd646-119">A stored procedure can return a dataset, an `IDataReader`, or an empty result.</span></span>  
  
 <span data-ttu-id="cd646-120">Nell'esempio seguente viene utilizzata la stored procedure fittizia `FinalSalesNumbers`:</span><span class="sxs-lookup"><span data-stu-id="cd646-120">The following example uses the fictional stored procedure, `FinalSalesNumbers`:</span></span>  
  
```  
CALL FinalSalesNumbers()  
```  
  
## <a name="see-also"></a><span data-ttu-id="cd646-121">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="cd646-121">See Also</span></span>  
 [<span data-ttu-id="cd646-122">Programmazione di server ADOMD.NET</span><span class="sxs-lookup"><span data-stu-id="cd646-122">ADOMD.NET Server Programming</span></span>](https://docs.microsoft.com/bi-reference/adomd/multidimensional-models-adomd-net-server/adomd-net-server-programming)  
  
  
