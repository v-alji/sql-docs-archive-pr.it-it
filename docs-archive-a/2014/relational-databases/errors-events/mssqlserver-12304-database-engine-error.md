---
title: MSSQLSERVER_12304 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 12304 (Database Engine error)
ms.assetid: a2c252c2-e815-4ac8-a101-7af5b32e3233
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: c2347fc46fe5ab83ef2ff46b81500cd737ed02d8
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87629865"
---
# <a name="mssqlserver_12304"></a><span data-ttu-id="3d6e9-102">MSSQLSERVER_12304</span><span class="sxs-lookup"><span data-stu-id="3d6e9-102">MSSQLSERVER_12304</span></span>
    
## <a name="details"></a><span data-ttu-id="3d6e9-103">Dettagli</span><span class="sxs-lookup"><span data-stu-id="3d6e9-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="3d6e9-104">Nome prodotto</span><span class="sxs-lookup"><span data-stu-id="3d6e9-104">Product Name</span></span>|<span data-ttu-id="3d6e9-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="3d6e9-105">SQL Server</span></span>|  
|<span data-ttu-id="3d6e9-106">ID evento</span><span class="sxs-lookup"><span data-stu-id="3d6e9-106">Event ID</span></span>|<span data-ttu-id="3d6e9-107">12304</span><span class="sxs-lookup"><span data-stu-id="3d6e9-107">12304</span></span>|  
|<span data-ttu-id="3d6e9-108">Origine evento</span><span class="sxs-lookup"><span data-stu-id="3d6e9-108">Event Source</span></span>|<span data-ttu-id="3d6e9-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="3d6e9-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="3d6e9-110">Componente</span><span class="sxs-lookup"><span data-stu-id="3d6e9-110">Component</span></span>|<span data-ttu-id="3d6e9-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="3d6e9-111">SQLEngine</span></span>|  
|<span data-ttu-id="3d6e9-112">Nome simbolico</span><span class="sxs-lookup"><span data-stu-id="3d6e9-112">Symbolic Name</span></span>|<span data-ttu-id="3d6e9-113">HK_UNSUPPORTED_IDENTITY_TABLE_VAR</span><span class="sxs-lookup"><span data-stu-id="3d6e9-113">HK_UNSUPPORTED_IDENTITY_TABLE_VAR</span></span>|  
|<span data-ttu-id="3d6e9-114">Testo del messaggio</span><span class="sxs-lookup"><span data-stu-id="3d6e9-114">Message Text</span></span>|<span data-ttu-id="3d6e9-115">L'utilizzo di un tipo di tabella con ottimizzazione per la memoria in cui viene utilizzata la proprietà IDENTITY con una delle relative colonne non è supportato quando si utilizza il tipo al di fuori del contesto di una stored procedure compilata in modo nativo.</span><span class="sxs-lookup"><span data-stu-id="3d6e9-115">Using a memory optimized table type that uses the IDENTITY property with any of its columns is not supported when using the type outside the context of a natively compiled stored procedure.</span></span>|  
  
## <a name="user-action"></a><span data-ttu-id="3d6e9-116">Azione dell'utente</span><span class="sxs-lookup"><span data-stu-id="3d6e9-116">User Action</span></span>  
 <span data-ttu-id="3d6e9-117">Non utilizzare un tipo di tabella ottimizzata per la memoria in cui viene utilizzata la proprietà Identity con una delle relative colonne.</span><span class="sxs-lookup"><span data-stu-id="3d6e9-117">Do not use a memory-optimized table type that uses the identity property with any of its columns.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3d6e9-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="3d6e9-118">See Also</span></span>  
 [<span data-ttu-id="3d6e9-119">OLTP in memoria &#40;ottimizzazione per la memoria&#41;</span><span class="sxs-lookup"><span data-stu-id="3d6e9-119">In-Memory OLTP &#40;In-Memory Optimization&#41;</span></span>](../in-memory-oltp/in-memory-oltp-in-memory-optimization.md)  
  
  
