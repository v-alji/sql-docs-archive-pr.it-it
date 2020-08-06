---
title: Specifica di un test di nodo nel percorso (SQLXML 4,0) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: reference
helpviewer_keywords:
- XPath queries [SQLXML], location paths
- principal node types [SQLXML]
- node tests [SQLXML]
- location path for XPath query
ms.assetid: f46c30bf-1e24-4435-9ac2-f8ba43a8ff94
author: rothja
ms.author: jroth
ms.openlocfilehash: 9d8535154f4b481c8a47bfdb8b801e3136a1ef0f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87629292"
---
# <a name="specifying-a-node-test-in-the-location-path-sqlxml-40"></a><span data-ttu-id="10291-102">Specifica di un test di nodo nel percorso (SQLXML 4.0)</span><span class="sxs-lookup"><span data-stu-id="10291-102">Specifying a Node Test in the Location Path (SQLXML 4.0)</span></span>
  <span data-ttu-id="10291-103">Un test di nodo specifica il tipo di nodo selezionato dal passo.</span><span class="sxs-lookup"><span data-stu-id="10291-103">A node test specifies the node type selected by the location step.</span></span> <span data-ttu-id="10291-104">Ogni asse (`child`, `parent`, `attribute` o `self`) dispone di un tipo di nodo principale.</span><span class="sxs-lookup"><span data-stu-id="10291-104">Every axis (`child`, `parent`, `attribute`, or `self`) has a principal node type.</span></span> <span data-ttu-id="10291-105">Per l' `attribute` asse, il tipo di nodo principale è **\<attribute>** .</span><span class="sxs-lookup"><span data-stu-id="10291-105">For the `attribute` axis, the principal node type is **\<attribute>**.</span></span> <span data-ttu-id="10291-106">Per gli `parent` `child` assi, e `self` , il tipo di nodo principale è **\<element>** .</span><span class="sxs-lookup"><span data-stu-id="10291-106">For the `parent`, `child`, and `self` axes, the principal node type is **\<element>**.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="10291-107">Il test di nodo con carattere jolly \*, ad esempio `child::*`, non è supportato.</span><span class="sxs-lookup"><span data-stu-id="10291-107">The wildcard node test \* (for example, `child::*`) is not supported.</span></span>  
  
## <a name="node-test-example-1"></a><span data-ttu-id="10291-108">Test del nodo: esempio 1</span><span class="sxs-lookup"><span data-stu-id="10291-108">Node Test: Example 1</span></span>  
 <span data-ttu-id="10291-109">Il percorso `child::Customer` Seleziona gli **\<Customer>** elementi figlio del nodo di contesto.</span><span class="sxs-lookup"><span data-stu-id="10291-109">The location path `child::Customer` selects **\<Customer>** element children of the context node.</span></span>  
  
 <span data-ttu-id="10291-110">In questo esempio `child` è l'asse e `Customer` è il test di nodo.</span><span class="sxs-lookup"><span data-stu-id="10291-110">In this example, `child` is the axis and `Customer` is the node test.</span></span> <span data-ttu-id="10291-111">Il tipo di nodo principale per l' `child` asse è **\<element>** .</span><span class="sxs-lookup"><span data-stu-id="10291-111">The principal node type for the `child` axis is **\<element>**.</span></span> <span data-ttu-id="10291-112">Pertanto, il test di nodo è TRUE se il **\<Customer>** nodo è un **\<element>** nodo.</span><span class="sxs-lookup"><span data-stu-id="10291-112">Therefore, the node test is TRUE if the **\<Customer>** node is an **\<element>** node.</span></span> <span data-ttu-id="10291-113">Se il nodo di contesto non dispone **\<Customer>** di elementi figlio, viene restituito un set di nodi vuoto.</span><span class="sxs-lookup"><span data-stu-id="10291-113">If the context node has no **\<Customer>** children, an empty set of nodes is returned.</span></span>  
  
## <a name="node-test-example-2"></a><span data-ttu-id="10291-114">Test di nodo: esempio 2</span><span class="sxs-lookup"><span data-stu-id="10291-114">Node Test: Example 2</span></span>  
 <span data-ttu-id="10291-115">Il percorso consente `attribute::CustomerID` di selezionare l'attributo **CustomerID** del nodo di contesto.</span><span class="sxs-lookup"><span data-stu-id="10291-115">The location path `attribute::CustomerID` selects the **CustomerID** attribute of the context node.</span></span>  
  
 <span data-ttu-id="10291-116">Nell'esempio `attribute` è l'asse e `CustomerID` è il test di nodo.</span><span class="sxs-lookup"><span data-stu-id="10291-116">In the example, `attribute` is the axis and `CustomerID` is the node test.</span></span> <span data-ttu-id="10291-117">Il tipo di nodo principale dell' `attribute` asse è **\<attribute>** .</span><span class="sxs-lookup"><span data-stu-id="10291-117">The principal node type of the `attribute` axis is **\<attribute>**.</span></span> <span data-ttu-id="10291-118">Pertanto, il test di nodo è TRUE se **CustomerID** è un **\<attribute>** nodo.</span><span class="sxs-lookup"><span data-stu-id="10291-118">Therefore, the node test is TRUE if **CustomerID** is an **\<attribute>** node.</span></span> <span data-ttu-id="10291-119">Se il nodo di contesto non dispone di **CustomerID**, viene restituito un set di nodi vuoto.</span><span class="sxs-lookup"><span data-stu-id="10291-119">If the context node has no **CustomerID**, an empty set of nodes is returned.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="10291-120">In questa implementazione di XPath, se un passaggio del percorso si riferisce a un **\<element>** **\<attribute>** tipo o non dichiarato nello schema, viene generato un errore.</span><span class="sxs-lookup"><span data-stu-id="10291-120">In this implementation of XPath, if a location step refers to an **\<element>** or an **\<attribute>** type that is not declared in the schema, an error is generated.</span></span> <span data-ttu-id="10291-121">a differenza di quanto avviene con l'implementazione di XPath in MSXML, che restituisce un set di nodi vuoto.</span><span class="sxs-lookup"><span data-stu-id="10291-121">This is different from the implementation of XPath in MSXML, which returns an empty node set.</span></span>  
  
## <a name="abbreviated-syntax-for-the-axes"></a><span data-ttu-id="10291-122">Sintassi abbreviata per gli assi</span><span class="sxs-lookup"><span data-stu-id="10291-122">Abbreviated Syntax for the Axes</span></span>  
 <span data-ttu-id="10291-123">Per il percorso è supportata la sintassi abbreviata seguente:</span><span class="sxs-lookup"><span data-stu-id="10291-123">The following abbreviated syntax for the location path is supported:</span></span>  
  
-   <span data-ttu-id="10291-124">`attribute::` può essere abbreviato utilizzando `@`.</span><span class="sxs-lookup"><span data-stu-id="10291-124">`attribute::` can be abbreviated to `@`.</span></span>  
  
     <span data-ttu-id="10291-125">Il percorso `Customer[@CustomerID="ALFKI"]` è uguale a `child::Customer[attribute::CustomerID="ALFKI"]`.</span><span class="sxs-lookup"><span data-stu-id="10291-125">The location path `Customer[@CustomerID="ALFKI"]` is the same as `child::Customer[attribute::CustomerID="ALFKI"]`.</span></span>  
  
-   <span data-ttu-id="10291-126">`child::` può essere omesso da un passo.</span><span class="sxs-lookup"><span data-stu-id="10291-126">`child::` can be omitted from a location step.</span></span>  
  
     <span data-ttu-id="10291-127">In questo caso, `child` è l'asse predefinito.</span><span class="sxs-lookup"><span data-stu-id="10291-127">Thus, `child` is the default axis.</span></span> <span data-ttu-id="10291-128">Il percorso `Customer/Order` è uguale a `child::Customer/child::Order`.</span><span class="sxs-lookup"><span data-stu-id="10291-128">The location path `Customer/Order` is the same as `child::Customer/child::Order`.</span></span>  
  
-   <span data-ttu-id="10291-129">`self::node()` può essere abbreviato utilizzando un punto (.), mentre `parent::node()` può essere abbreviato utilizzando due punti (..).</span><span class="sxs-lookup"><span data-stu-id="10291-129">`self::node()` can be abbreviated to one period (.), and `parent::node()` can be abbreviated to two periods (..).</span></span>  
  
  
