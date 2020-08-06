---
title: Specifica di un asse (SQLXML 4,0) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: reference
helpviewer_keywords:
- XPath queries [SQLXML], axes
- XPath queries [SQLXML], location paths
- self axis
- attribute axis [SQLXML]
- axis [SQLXML]
- child axis
- parent axis
- location path for XPath query
- axes [SQLXML]
ms.assetid: 65631795-3389-40cf-90ea-85e9438956c5
author: rothja
ms.author: jroth
ms.openlocfilehash: 5e43281fe31d323a7eea19e749b80b59458752b7
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87629290"
---
# <a name="specifying-an-axis-sqlxml-40"></a><span data-ttu-id="17482-102">Specifica di un asse (SQLXML 4.0)</span><span class="sxs-lookup"><span data-stu-id="17482-102">Specifying an Axis (SQLXML 4.0)</span></span>
    
-   <span data-ttu-id="17482-103">L'asse specifica la relazione all'interno dell'albero tra i nodi selezionati dal passo e dal nodo di contesto.</span><span class="sxs-lookup"><span data-stu-id="17482-103">The axis specifies the tree relationship between the nodes selected by the location step and the context node.</span></span> <span data-ttu-id="17482-104">Sono supportati gli assi seguenti:  `child`</span><span class="sxs-lookup"><span data-stu-id="17482-104">The following axes are supported:  `child`</span></span>  
  
     <span data-ttu-id="17482-105">Contiene l'elemento figlio del nodo di contesto.</span><span class="sxs-lookup"><span data-stu-id="17482-105">Contains the child of the context node.</span></span>  
  
     <span data-ttu-id="17482-106">L'espressione XPath seguente (percorso) Seleziona dal nodo di contesto corrente tutti gli **\<Customer>** elementi figlio:</span><span class="sxs-lookup"><span data-stu-id="17482-106">The following XPath expression (location path) selects from the current context node all the **\<Customer>** children:</span></span>  
  
    ```  
    child::Customer  
    ```  
  
     <span data-ttu-id="17482-107">Nella query XPath seguente, `child` è l'asse.</span><span class="sxs-lookup"><span data-stu-id="17482-107">In the following XPath query, `child` is the axis.</span></span> <span data-ttu-id="17482-108">`Customer` è il test del nodo.</span><span class="sxs-lookup"><span data-stu-id="17482-108">`Customer` is the node test.</span></span>  
  
-   `parent`  
  
     <span data-ttu-id="17482-109">Contiene l'elemento padre del nodo di contesto.</span><span class="sxs-lookup"><span data-stu-id="17482-109">Contains the parent of the context node.</span></span>  
  
     <span data-ttu-id="17482-110">L'espressione XPath seguente seleziona tutti gli **\<Customer>** elementi padre degli **\<Order>** elementi figlio:</span><span class="sxs-lookup"><span data-stu-id="17482-110">The following XPath expression selects all the **\<Customer>** parents of the **\<Order>** children:</span></span>  
  
    ```  
    child::Customer/child::Order[parent::Customer/@customerID="ALFKI"]  
    ```  
  
     <span data-ttu-id="17482-111">L'espressione equivale a specificare `child::Customer`.</span><span class="sxs-lookup"><span data-stu-id="17482-111">This is the same as specifying `child::Customer`.</span></span> <span data-ttu-id="17482-112">In questa query XPath, `child` e `parent` sono le assi.</span><span class="sxs-lookup"><span data-stu-id="17482-112">In this XPath query, `child` and `parent` are the axes.</span></span> <span data-ttu-id="17482-113">`Customer` e `Order` sono i test di nodo.</span><span class="sxs-lookup"><span data-stu-id="17482-113">`Customer` and `Order` are the node tests.</span></span>  
  
-   `attribute`  
  
     <span data-ttu-id="17482-114">Contiene l'attributo del nodo di contesto.</span><span class="sxs-lookup"><span data-stu-id="17482-114">Contains the attribute of the context node.</span></span>  
  
     <span data-ttu-id="17482-115">L'espressione XPath seguente seleziona l'attributo **CustomerID** del nodo di contesto:</span><span class="sxs-lookup"><span data-stu-id="17482-115">The following XPath expression selects the **CustomerID** attribute of the context node:</span></span>  
  
    ```  
    attribute::CustomerID  
    ```  
  
-   `self`  
  
     <span data-ttu-id="17482-116">Contiene il nodo di contesto stesso.</span><span class="sxs-lookup"><span data-stu-id="17482-116">Contains the context node itself.</span></span>  
  
     <span data-ttu-id="17482-117">L'espressione XPath seguente seleziona il nodo corrente se si tratta del **\<Order>** nodo:</span><span class="sxs-lookup"><span data-stu-id="17482-117">The following XPath expression selects the current node if it is the **\<Order>** node:</span></span>  
  
    ```  
    self::Order  
    ```  
  
     <span data-ttu-id="17482-118">Nella query XPath seguente `self` è l'asse e `Order` è il test di nodo.</span><span class="sxs-lookup"><span data-stu-id="17482-118">In this XPath query, `self` is the axis and `Order` is the node test.</span></span>  
  
  
