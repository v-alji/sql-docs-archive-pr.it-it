---
title: MSSQLSERVER_8710 | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 8710 (Database Engine error)
ms.assetid: 78b9f9da-5489-4be0-94df-f065d86ed18c
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 65fb6b3efb42c282347f560353a2b21edc337859
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87638418"
---
# <a name="mssqlserver_8710"></a><span data-ttu-id="5aed0-102">MSSQLSERVER_8710</span><span class="sxs-lookup"><span data-stu-id="5aed0-102">MSSQLSERVER_8710</span></span>
    
## <a name="details"></a><span data-ttu-id="5aed0-103">Dettagli</span><span class="sxs-lookup"><span data-stu-id="5aed0-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="5aed0-104">Nome prodotto</span><span class="sxs-lookup"><span data-stu-id="5aed0-104">Product Name</span></span>|<span data-ttu-id="5aed0-105">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="5aed0-105">MSSQLSERVER</span></span>|  
|<span data-ttu-id="5aed0-106">ID evento</span><span class="sxs-lookup"><span data-stu-id="5aed0-106">Event ID</span></span>|<span data-ttu-id="5aed0-107">8710</span><span class="sxs-lookup"><span data-stu-id="5aed0-107">8710</span></span>|  
|<span data-ttu-id="5aed0-108">Origine evento</span><span class="sxs-lookup"><span data-stu-id="5aed0-108">Event Source</span></span>|<span data-ttu-id="5aed0-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="5aed0-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="5aed0-110">Componente</span><span class="sxs-lookup"><span data-stu-id="5aed0-110">Component</span></span>|<span data-ttu-id="5aed0-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="5aed0-111">SQLEngine</span></span>|  
|<span data-ttu-id="5aed0-112">Nome simbolico</span><span class="sxs-lookup"><span data-stu-id="5aed0-112">Symbolic Name</span></span>|<span data-ttu-id="5aed0-113">QUERY2_CUBE_ILLEGAL_AGG_FUNC</span><span class="sxs-lookup"><span data-stu-id="5aed0-113">QUERY2_CUBE_ILLEGAL_AGG_FUNC</span></span>|  
|<span data-ttu-id="5aed0-114">Testo del messaggio</span><span class="sxs-lookup"><span data-stu-id="5aed0-114">Message Text</span></span>|<span data-ttu-id="5aed0-115">Le funzioni di aggregazione utilizzate con query CUBE, ROLLUP o GROUPING SET devono supportare l'unione di aggregazioni secondarie.</span><span class="sxs-lookup"><span data-stu-id="5aed0-115">Aggregate functions that are used with CUBE, ROLLUP, or GROUPING SET queries must provide for the merging of subaggregates.</span></span> <span data-ttu-id="5aed0-116">Per risolvere il problema, rimuovere la funzione di aggregazione o scrivere la query utilizzando UNION ALL nelle clausole GROUP BY.</span><span class="sxs-lookup"><span data-stu-id="5aed0-116">To fix this problem, remove the aggregate function or write the query using UNION ALL over GROUP BY clauses.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="5aed0-117">Spiegazione</span><span class="sxs-lookup"><span data-stu-id="5aed0-117">Explanation</span></span>  
 <span data-ttu-id="5aed0-118">Una funzione di aggregazione è stata utilizzata con CUBE, ROLLUP o GROUPING SETS che non forniscono un metodo per unire aggregazioni secondarie.</span><span class="sxs-lookup"><span data-stu-id="5aed0-118">An aggregate function has been used with CUBE, ROLLUP, or GROUPING SETS that does not provide a method for merging subaggregates.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="5aed0-119">Azione dell'utente</span><span class="sxs-lookup"><span data-stu-id="5aed0-119">User Action</span></span>  
 <span data-ttu-id="5aed0-120">Per risolvere il problema, rimuovere la funzione di aggregazione o scrivere la query utilizzando UNION ALL nelle clausole GROUP BY.</span><span class="sxs-lookup"><span data-stu-id="5aed0-120">To fix this problem, remove the aggregate function or write the query using UNION ALL over GROUP BY clauses.</span></span>  
  
  
