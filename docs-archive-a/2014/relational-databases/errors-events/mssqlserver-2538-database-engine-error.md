---
title: MSSQLSERVER_2538 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 2538 (Database Engine error)
ms.assetid: 0a0f7d79-f1ba-4749-8804-fb660cca3492
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 9f4ae886a6fd0abee2f7aa22c6a234c0a6c2d040
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87636122"
---
# <a name="mssqlserver_2538"></a><span data-ttu-id="dc7e3-102">MSSQLSERVER_2538</span><span class="sxs-lookup"><span data-stu-id="dc7e3-102">MSSQLSERVER_2538</span></span>
    
## <a name="details"></a><span data-ttu-id="dc7e3-103">Dettagli</span><span class="sxs-lookup"><span data-stu-id="dc7e3-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="dc7e3-104">Nome prodotto</span><span class="sxs-lookup"><span data-stu-id="dc7e3-104">Product Name</span></span>|<span data-ttu-id="dc7e3-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="dc7e3-105">SQL Server</span></span>|  
|<span data-ttu-id="dc7e3-106">ID evento</span><span class="sxs-lookup"><span data-stu-id="dc7e3-106">Event ID</span></span>|<span data-ttu-id="dc7e3-107">2538</span><span class="sxs-lookup"><span data-stu-id="dc7e3-107">2538</span></span>|  
|<span data-ttu-id="dc7e3-108">Origine evento</span><span class="sxs-lookup"><span data-stu-id="dc7e3-108">Event Source</span></span>|<span data-ttu-id="dc7e3-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="dc7e3-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="dc7e3-110">Componente</span><span class="sxs-lookup"><span data-stu-id="dc7e3-110">Component</span></span>|<span data-ttu-id="dc7e3-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="dc7e3-111">SQLEngine</span></span>|  
|<span data-ttu-id="dc7e3-112">Nome simbolico</span><span class="sxs-lookup"><span data-stu-id="dc7e3-112">Symbolic Name</span></span>|<span data-ttu-id="dc7e3-113">DBCC_ALLOCATION_SUMMARY_PER_FILE</span><span class="sxs-lookup"><span data-stu-id="dc7e3-113">DBCC_ALLOCATION_SUMMARY_PER_FILE</span></span>|  
|<span data-ttu-id="dc7e3-114">Testo del messaggio</span><span class="sxs-lookup"><span data-stu-id="dc7e3-114">Message Text</span></span>|<span data-ttu-id="dc7e3-115">File FILE.</span><span class="sxs-lookup"><span data-stu-id="dc7e3-115">File FILE.</span></span> <span data-ttu-id="dc7e3-116">Numero di extent = EXTENTS, pagine utilizzate = USED_PAGES e pagine riservate = RESERVED_PAGES.</span><span class="sxs-lookup"><span data-stu-id="dc7e3-116">Number of extents = EXTENTS, used pages = USED_PAGES, reserved pages = RESERVED_PAGES.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="dc7e3-117">Spiegazione</span><span class="sxs-lookup"><span data-stu-id="dc7e3-117">Explanation</span></span>  
 <span data-ttu-id="dc7e3-118">Queste informazioni fanno parte dell'output generato dal comando DBCC CHECKALLOC</span><span class="sxs-lookup"><span data-stu-id="dc7e3-118">This information is part of the output from the DBCC CHECKALLOC command.</span></span> <span data-ttu-id="dc7e3-119">e riepilogano per ogni file gli extent allocati, le pagine utilizzate e le pagine riservate del database specificato.</span><span class="sxs-lookup"><span data-stu-id="dc7e3-119">This information is the per-file summary of allocated extents, used pages, and reserved pages for the specified database.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="dc7e3-120">Azione dell'utente</span><span class="sxs-lookup"><span data-stu-id="dc7e3-120">User Action</span></span>  
 <span data-ttu-id="dc7e3-121">nessuno</span><span class="sxs-lookup"><span data-stu-id="dc7e3-121">None</span></span>  
  
  
