---
title: Accesso al contesto di query nelle stored procedure | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: reference
helpviewer_keywords:
- execution context [Analysis Services]
- stored procedures [Analysis Services], query context
- Context object
- query context [Analysis Services]
ms.assetid: bdc7dad8-2f22-4265-aba4-a3a451527840
author: minewiskan
ms.author: owend
ms.openlocfilehash: 9da8ddb223ed03c0208fe524ea5cd7195a039c97
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87711116"
---
# <a name="accessing-query-context-in-stored-procedures"></a><span data-ttu-id="a3be8-102">Accesso al contesto di query nelle stored procedure</span><span class="sxs-lookup"><span data-stu-id="a3be8-102">Accessing Query Context in Stored Procedures</span></span>
  <span data-ttu-id="a3be8-103">Il contesto di esecuzione di una stored procedure è disponibile all'interno del codice della stored procedure stessa sotto forma di oggetto `Context` del modello a oggetti server ADOMD.NET.</span><span class="sxs-lookup"><span data-stu-id="a3be8-103">The execution context of a stored procedure is available within the code of the stored procedure as the `Context` object of the ADOMD.NET server object model.</span></span> <span data-ttu-id="a3be8-104">Si tratta di un contesto di sola lettura che non può essere modificato dalla stored procedure.</span><span class="sxs-lookup"><span data-stu-id="a3be8-104">This is a read-only context and cannot be modified by the stored procedure.</span></span> <span data-ttu-id="a3be8-105">Per questo oggetto sono disponibili le proprietà seguenti.</span><span class="sxs-lookup"><span data-stu-id="a3be8-105">The following properties are available on this object.</span></span>  
  
|<span data-ttu-id="a3be8-106">Proprietà</span><span class="sxs-lookup"><span data-stu-id="a3be8-106">Property</span></span>|<span data-ttu-id="a3be8-107">Type</span><span class="sxs-lookup"><span data-stu-id="a3be8-107">Type</span></span>|<span data-ttu-id="a3be8-108">Descrizione</span><span class="sxs-lookup"><span data-stu-id="a3be8-108">Description</span></span>|  
|--------------|----------|-----------------|  
|<span data-ttu-id="a3be8-109">**CurrentCube**</span><span class="sxs-lookup"><span data-stu-id="a3be8-109">**CurrentCube**</span></span>|<span data-ttu-id="a3be8-110">Cubo</span><span class="sxs-lookup"><span data-stu-id="a3be8-110">Cube</span></span>|<span data-ttu-id="a3be8-111">Cubo per il contesto di query corrente.</span><span class="sxs-lookup"><span data-stu-id="a3be8-111">The cube for the current query context.</span></span>|  
|<span data-ttu-id="a3be8-112">**CurrentDatabaseName**</span><span class="sxs-lookup"><span data-stu-id="a3be8-112">**CurrentDatabaseName**</span></span>|<span data-ttu-id="a3be8-113">string</span><span class="sxs-lookup"><span data-stu-id="a3be8-113">String</span></span>|<span data-ttu-id="a3be8-114">Identificatore del database corrente.</span><span class="sxs-lookup"><span data-stu-id="a3be8-114">The identifier of the current database.</span></span>|  
|<span data-ttu-id="a3be8-115">**CurrentConnection**</span><span class="sxs-lookup"><span data-stu-id="a3be8-115">**CurrentConnection**</span></span>|<span data-ttu-id="a3be8-116">Connessione</span><span class="sxs-lookup"><span data-stu-id="a3be8-116">Connection</span></span>|<span data-ttu-id="a3be8-117">Riferimento all'oggetto connessione nel contesto corrente.</span><span class="sxs-lookup"><span data-stu-id="a3be8-117">A reference to the connection object in the current context.</span></span>|  
|<span data-ttu-id="a3be8-118">**Corretto**</span><span class="sxs-lookup"><span data-stu-id="a3be8-118">**Pass**</span></span>|<span data-ttu-id="a3be8-119">Integer</span><span class="sxs-lookup"><span data-stu-id="a3be8-119">Integer</span></span>|<span data-ttu-id="a3be8-120">Numero della sessione di calcolo per il contesto corrente.</span><span class="sxs-lookup"><span data-stu-id="a3be8-120">The pass number for the current context.</span></span>|  
  
 <span data-ttu-id="a3be8-121">L'oggetto `Context` è presente se in una stored procedure viene utilizzato un modello a oggetti MDX (Multidimensional Expressions),</span><span class="sxs-lookup"><span data-stu-id="a3be8-121">The `Context` object exists when the Multidimensional Expressions (MDX) object model is used in a stored procedure.</span></span> <span data-ttu-id="a3be8-122">mentre non è disponibile se il modello a oggetti MDX viene utilizzato in un client.</span><span class="sxs-lookup"><span data-stu-id="a3be8-122">It is not available when the MDX object model is used on a client.</span></span> <span data-ttu-id="a3be8-123">L'oggetto `Context` non viene esplicitamente passato a o restituito dalla stored procedure,</span><span class="sxs-lookup"><span data-stu-id="a3be8-123">The `Context` object is not explicitly passed to or returned by the stored procedure.</span></span> <span data-ttu-id="a3be8-124">ma è disponibile durante l'esecuzione della stored procedure stessa.</span><span class="sxs-lookup"><span data-stu-id="a3be8-124">It is available during the execution of the stored procedure.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a3be8-125">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a3be8-125">See Also</span></span>  
 <span data-ttu-id="a3be8-126">[Gestione di assembly di modelli multidimensionali](../multidimensional-models/multidimensional-model-assemblies-management.md) </span><span class="sxs-lookup"><span data-stu-id="a3be8-126">[Multidimensional Model Assemblies Management](../multidimensional-models/multidimensional-model-assemblies-management.md) </span></span>  
 [<span data-ttu-id="a3be8-127">Definizione di stored procedure</span><span class="sxs-lookup"><span data-stu-id="a3be8-127">Defining Stored Procedures</span></span>](../multidimensional-models-extending-olap-stored-procedures/defining-stored-procedures.md)  
  
  
