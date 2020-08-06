---
title: Query dei dati spaziali per Nearest Neighbor | Microsoft Docs
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
ms.assetid: 7af4ad5d-484e-45b4-aa16-83c33b358bb6
author: MladjoA
ms.author: mlandzic
ms.openlocfilehash: 644b3e5cfdaeff7457639bc2da77260b64011735
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87637166"
---
# <a name="query-spatial-data-for-nearest-neighbor"></a><span data-ttu-id="0001f-102">Query dei dati spaziali per Nearest Neighbor</span><span class="sxs-lookup"><span data-stu-id="0001f-102">Query Spatial Data for Nearest Neighbor</span></span>
  <span data-ttu-id="0001f-103">La query Nearest Neighbor è una query comune utilizzata con dati spaziali.</span><span class="sxs-lookup"><span data-stu-id="0001f-103">A common query used with spatial data is the Nearest Neighbor query.</span></span> <span data-ttu-id="0001f-104">Le query Nearest Neighbor vengono utilizzate per trovare gli oggetti spaziali più vicini a un oggetto spaziale specifico.</span><span class="sxs-lookup"><span data-stu-id="0001f-104">Nearest Neighbor queries are used to find the closest spatial objects to a specific spatial object.</span></span> <span data-ttu-id="0001f-105">Un localizzatore di archivio per un sito Web, ad esempio, deve spesso trovare i percorsi di archivio più vicini alla posizione di un cliente.</span><span class="sxs-lookup"><span data-stu-id="0001f-105">For example a store locater for a Web site often must find the closest store locations to a customer location.</span></span>  
  
 <span data-ttu-id="0001f-106">Una query Nearest Neighbor può essere scritta in una varietà di formati di query validi, ma per l'utilizzo di un indice spaziale è necessario utilizzare la sintassi seguente.</span><span class="sxs-lookup"><span data-stu-id="0001f-106">A Nearest Neighbor query can be written in a variety of valid query formats, but for the Nearest Neighbor query to use a spatial index the following syntax must be used.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0001f-107">Sintassi</span><span class="sxs-lookup"><span data-stu-id="0001f-107">Syntax</span></span>  
  
```vb  
SELECT TOP ( number )  
        [ WITH TIES ]  
        [ * | expression ]   
        [, ...]  
    FROM spatial_table_reference, ...   
        [ WITH   
            (   
                [ INDEX ( index_ref ) ]   
                [ , SPATIAL_WINDOW_MAX_CELLS = <value>]   
                [ ,... ]   
            )   
        ]  
    WHERE   
        column_ref.STDistance ( @spatial_ object )   
            {   
                [ IS NOT NULL ] | [ < const ] | [ > const ]   
                | [ <= const ] | [ >= const ] | [ <> const ] ]   
            }  
            [ AND { other_predicate } ]   
    }  
    ORDER BY column_ref.STDistance ( @spatial_ object ) [ ,...n ]  
[ ; ]  
  
```  
  
## <a name="nearest-neighbor-query-and-spatial-indexes"></a><span data-ttu-id="0001f-108">Query Nearest Neighbor e indici spaziali</span><span class="sxs-lookup"><span data-stu-id="0001f-108">Nearest Neighbor Query and Spatial Indexes</span></span>  
 <span data-ttu-id="0001f-109">In [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], per eseguire una query Nearest Neighbor nelle colonne di dati spaziali, vengono utilizzate le clausole `TOP` e `ORDER BY`.</span><span class="sxs-lookup"><span data-stu-id="0001f-109">In [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], `TOP` and `ORDER BY` clauses are used to perform a Nearest Neighbor query on spatial data columns.</span></span> <span data-ttu-id="0001f-110">La clausola `ORDER BY` contiene una chiamata al metodo `STDistance()` per il tipo di dati della colonna spaziale.</span><span class="sxs-lookup"><span data-stu-id="0001f-110">The `ORDER BY` clause contains a call to the `STDistance()` method for the spatial column data type.</span></span> <span data-ttu-id="0001f-111">La clausola `TOP` indica il numero di oggetti da restituire per la query.</span><span class="sxs-lookup"><span data-stu-id="0001f-111">The `TOP` clause indicates the number of objects to return for the query.</span></span>  
  
 <span data-ttu-id="0001f-112">Per utilizzare un indice spaziale in una query Nearest Neighbor, è necessario soddisfare i requisiti seguenti:</span><span class="sxs-lookup"><span data-stu-id="0001f-112">The following requirements must be met for a Nearest Neighbor query to use a spatial index:</span></span>  
  
1.  <span data-ttu-id="0001f-113">In una delle colonne spaziali deve essere presente un indice spaziale e tale colonna deve essere utilizzata dal metodo `STDistance()` nelle clausole `WHERE` e `ORDER BY`.</span><span class="sxs-lookup"><span data-stu-id="0001f-113">A spatial index must be present on one of the spatial columns and the `STDistance()` method must use that column in the `WHERE` and `ORDER BY` clauses.</span></span>  
  
2.  <span data-ttu-id="0001f-114">La clausola `TOP` non può contenere un'istruzione `PERCENT`.</span><span class="sxs-lookup"><span data-stu-id="0001f-114">The `TOP` clause cannot contain a `PERCENT` statement.</span></span>  
  
3.  <span data-ttu-id="0001f-115">La clausola `WHERE` deve contenere un metodo `STDistance()`.</span><span class="sxs-lookup"><span data-stu-id="0001f-115">The `WHERE` clause must contain a `STDistance()` method.</span></span>  
  
4.  <span data-ttu-id="0001f-116">Se nella clausola `WHERE` sono presenti più predicati, il predicato che contiene il metodo `STDistance()` deve essere connesso mediante una congiunzione `AND` ad altri predicati.</span><span class="sxs-lookup"><span data-stu-id="0001f-116">If there are multiple predicates in the `WHERE` clause then the predicate containing `STDistance()` method must be connected by an `AND` conjunction to the other predicates.</span></span> <span data-ttu-id="0001f-117">Il metodo `STDistance()` non può trovarsi in una parte facoltativa della clausola `WHERE`.</span><span class="sxs-lookup"><span data-stu-id="0001f-117">The `STDistance()` method cannot be in an optional part of the `WHERE` clause.</span></span>  
  
5.  <span data-ttu-id="0001f-118">La prima espressione nella clausola `ORDER BY` deve utilizzare il metodo `STDistance()`.</span><span class="sxs-lookup"><span data-stu-id="0001f-118">The first expression in the `ORDER BY` clause must use the `STDistance()` method.</span></span>  
  
6.  <span data-ttu-id="0001f-119">L'ordinamento per la prima espressione `STDistance()` nella clausola `ORDER BY` deve essere `ASC`.</span><span class="sxs-lookup"><span data-stu-id="0001f-119">Sort order for the first `STDistance()` expression in the `ORDER BY` clause must be `ASC`.</span></span>  
  
7.  <span data-ttu-id="0001f-120">Devono essere filtrate tutte le righe per le quali `STDistance` restituisce `NULL`.</span><span class="sxs-lookup"><span data-stu-id="0001f-120">All the rows for which `STDistance` returns `NULL` must be filtered out.</span></span>  
  
> [!WARNING]  
>  <span data-ttu-id="0001f-121">I metodi che accettano tipi di dati `geography` o `geometry` come argomenti restituiranno `NULL` se gli identificatori SRID non sono gli stessi per i tipi.</span><span class="sxs-lookup"><span data-stu-id="0001f-121">Methods that take `geography` or `geometry` data types as arguments will return `NULL` if the SRIDs are not the same for the types.</span></span>  
  
 <span data-ttu-id="0001f-122">Per gli indici utilizzati nelle query Nearest Neighbor è consigliabile utilizzare i nuovi schemi a mosaico di indice spaziale.</span><span class="sxs-lookup"><span data-stu-id="0001f-122">It is recommended that the new spatial index tessellations be used for indexes used in Nearest Neighbor queries.</span></span> <span data-ttu-id="0001f-123">Per altre informazioni sugli schemi a mosaico di indice spaziale, vedere [Dati spaziali &#40;SQL Server&#41;](spatial-data-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="0001f-123">For more information on spatial index tessellations, see [Spatial Data &#40;SQL Server&#41;](spatial-data-sql-server.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="0001f-124">Esempio</span><span class="sxs-lookup"><span data-stu-id="0001f-124">Example</span></span>  
 <span data-ttu-id="0001f-125">Nell'esempio di codice seguente viene illustrata una query Nearest Neighbor nella quale può essere utilizzato un indice spaziale.</span><span class="sxs-lookup"><span data-stu-id="0001f-125">The following code example shows a Nearest Neighbor query that can use a spatial index.</span></span> <span data-ttu-id="0001f-126">Nell'esempio viene utilizzata la tabella `Person.Address` del database `AdventureWorks2012` .</span><span class="sxs-lookup"><span data-stu-id="0001f-126">The example uses the `Person.Address` table in `AdventureWorks2012` database.</span></span>  
  
```  
USE AdventureWorks2012  
GO  
DECLARE @g geography = 'POINT(-121.626 47.8315)';  
SELECT TOP(7) SpatialLocation.ToString(), City FROM Person.Address  
WHERE SpatialLocation.STDistance(@g) IS NOT NULL  
ORDER BY SpatialLocation.STDistance(@g);  
  
```  
  
 <span data-ttu-id="0001f-127">Creare un indice spaziale nella colonna SpatialLocation per vedere in che modo viene utilizzato un indice spaziale in una query Nearest Neighbor.</span><span class="sxs-lookup"><span data-stu-id="0001f-127">Create a spatial index on the column SpatialLocation to see how a Nearest Neighbor query uses a spatial index.</span></span> <span data-ttu-id="0001f-128">Per ulteriori informazioni sulla creazione di indici spaziali, vedere [Create, Modify, and Drop Spatial Indexes](create-modify-and-drop-spatial-indexes.md).</span><span class="sxs-lookup"><span data-stu-id="0001f-128">For more information on creating spatial indexes, see [Create, Modify, and Drop Spatial Indexes](create-modify-and-drop-spatial-indexes.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="0001f-129">Esempio</span><span class="sxs-lookup"><span data-stu-id="0001f-129">Example</span></span>  
 <span data-ttu-id="0001f-130">Nell'esempio di codice seguente viene illustrata una query Nearest Neighbor nella quale non può essere utilizzato un indice spaziale.</span><span class="sxs-lookup"><span data-stu-id="0001f-130">The following code example shows a Nearest Neighbor query that cannot use a spatial index.</span></span>  
  
```  
USE AdventureWorks2012  
GO  
DECLARE @g geography = 'POINT(-121.626 47.8315)';  
SELECT TOP(7) SpatialLocation.ToString(), City FROM Person.Address  
ORDER BY SpatialLocation.STDistance(@g);  
  
```  
  
 <span data-ttu-id="0001f-131">Nella query manca una clausola `WHERE` che utilizza `STDistance()` in un formato specificato nella sezione relativa alla sintassi, pertanto nella query non può essere utilizzato un indice spaziale.</span><span class="sxs-lookup"><span data-stu-id="0001f-131">The query lacks a `WHERE` clause that uses `STDistance()` in a form specified in the syntax section so the query cannot use a spatial index.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0001f-132">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="0001f-132">See Also</span></span>  
 [<span data-ttu-id="0001f-133">Dati spaziali &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="0001f-133">Spatial Data &#40;SQL Server&#41;</span></span>](spatial-data-sql-server.md)  
  
  
