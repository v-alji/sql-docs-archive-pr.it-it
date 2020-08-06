---
title: MSSQLSERVER_8621 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 8621 (Database Engine error)
ms.assetid: 67f59865-becd-4999-8bb0-90aedd7effbf
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 48c36cf936475e3deea37a172c7dc59f88d0a31a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87635068"
---
# <a name="mssqlserver_8621"></a><span data-ttu-id="93c3f-102">MSSQLSERVER_8621</span><span class="sxs-lookup"><span data-stu-id="93c3f-102">MSSQLSERVER_8621</span></span>
    
## <a name="details"></a><span data-ttu-id="93c3f-103">Dettagli</span><span class="sxs-lookup"><span data-stu-id="93c3f-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="93c3f-104">Nome prodotto</span><span class="sxs-lookup"><span data-stu-id="93c3f-104">Product Name</span></span>|<span data-ttu-id="93c3f-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="93c3f-105">SQL Server</span></span>|  
|<span data-ttu-id="93c3f-106">ID evento</span><span class="sxs-lookup"><span data-stu-id="93c3f-106">Event ID</span></span>|<span data-ttu-id="93c3f-107">8621</span><span class="sxs-lookup"><span data-stu-id="93c3f-107">8621</span></span>|  
|<span data-ttu-id="93c3f-108">Origine evento</span><span class="sxs-lookup"><span data-stu-id="93c3f-108">Event Source</span></span>|<span data-ttu-id="93c3f-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="93c3f-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="93c3f-110">Componente</span><span class="sxs-lookup"><span data-stu-id="93c3f-110">Component</span></span>|<span data-ttu-id="93c3f-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="93c3f-111">SQLEngine</span></span>|  
|<span data-ttu-id="93c3f-112">Nome simbolico</span><span class="sxs-lookup"><span data-stu-id="93c3f-112">Symbolic Name</span></span>|<span data-ttu-id="93c3f-113">OPTIMIZER_STACK_OVERFLOW_ERR</span><span class="sxs-lookup"><span data-stu-id="93c3f-113">OPTIMIZER_STACK_OVERFLOW_ERR</span></span>|  
|<span data-ttu-id="93c3f-114">Testo del messaggio</span><span class="sxs-lookup"><span data-stu-id="93c3f-114">Message Text</span></span>|<span data-ttu-id="93c3f-115">Spazio di stack esaurito durante l'ottimizzazione della query da parte di Query Processor.</span><span class="sxs-lookup"><span data-stu-id="93c3f-115">The query processor ran out of stack space during query optimization.</span></span> <span data-ttu-id="93c3f-116">Semplificare la query.</span><span class="sxs-lookup"><span data-stu-id="93c3f-116">Please simplify the query.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="93c3f-117">Spiegazione</span><span class="sxs-lookup"><span data-stu-id="93c3f-117">Explanation</span></span>  
 <span data-ttu-id="93c3f-118">La causa più probabile dell'errore risiede nelle dimensioni della query espansa,</span><span class="sxs-lookup"><span data-stu-id="93c3f-118">The size of the expanded query is the most likely cause of the error.</span></span> <span data-ttu-id="93c3f-119">che sostituisce nella query originale le definizioni di ogni vista, colonna calcolata, funzione [!INCLUDE[tsql](../../includes/tsql-md.md)] ed espressione di tabella comune a cui fa riferimento, nonché di ogni operazione di propagazione, ad esempio l'aggiornamento di indici secondari, viste e trigger.</span><span class="sxs-lookup"><span data-stu-id="93c3f-119">The expanded query substitutes into the original query the definitions of each of the views, computed columns, [!INCLUDE[tsql](../../includes/tsql-md.md)] functions, and common table expressions it references, as well as cascading actions like updating secondary indexes, views, and triggers.</span></span>  
  
 <span data-ttu-id="93c3f-120">Probabilmente la query presenta alcune dimensioni grandi, ad esempio il numero di tabelle a cui fanno riferimento le definizioni delle viste o un'espressione scalare di dimensioni molto estese.</span><span class="sxs-lookup"><span data-stu-id="93c3f-120">Most likely the query is large in some dimension; for example, the number of tables referenced by view definitions, or a very large scalar expression.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="93c3f-121">Azione dell'utente</span><span class="sxs-lookup"><span data-stu-id="93c3f-121">User Action</span></span>  
 <span data-ttu-id="93c3f-122">Semplificare la query suddividendola in più query secondo la dimensione più grande.</span><span class="sxs-lookup"><span data-stu-id="93c3f-122">Simplify the query by breaking the query into multiple queries along the largest dimension.</span></span> <span data-ttu-id="93c3f-123">Rimuovere innanzitutto qualsiasi elemento della query non strettamente necessario, quindi provare ad aggiungere una tabella temporanea e separare la query in due parti.</span><span class="sxs-lookup"><span data-stu-id="93c3f-123">First remove any query elements that are not really necessary, then try adding a temp table and splitting the query in two.</span></span>  <span data-ttu-id="93c3f-124">Non è sufficiente spostare semplicemente una parte della query in una subquery, funzione o espressione di tabella comune, poiché verrebbero ricombinate dal compilatore [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="93c3f-124">Merely moving a part of the query to a subquery, function, or common table expression is insufficient because they get recombined by the [!INCLUDE[tsql](../../includes/tsql-md.md)] compiler.</span></span>  
  
  
