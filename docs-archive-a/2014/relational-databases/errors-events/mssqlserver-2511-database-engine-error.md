---
title: MSSQLSERVER_2511 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 2511 (Database Engine error)
ms.assetid: 9a00c0ed-eb4b-4fae-8016-192396006c37
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 23e91b0d64140329639cf57f3a336cd2eab8e4e8
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87715312"
---
# <a name="mssqlserver_2511"></a><span data-ttu-id="e8144-102">MSSQLSERVER_2511</span><span class="sxs-lookup"><span data-stu-id="e8144-102">MSSQLSERVER_2511</span></span>
    
## <a name="details"></a><span data-ttu-id="e8144-103">Dettagli</span><span class="sxs-lookup"><span data-stu-id="e8144-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="e8144-104">Nome prodotto</span><span class="sxs-lookup"><span data-stu-id="e8144-104">Product Name</span></span>|<span data-ttu-id="e8144-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="e8144-105">SQL Server</span></span>|  
|<span data-ttu-id="e8144-106">ID evento</span><span class="sxs-lookup"><span data-stu-id="e8144-106">Event ID</span></span>|<span data-ttu-id="e8144-107">2511</span><span class="sxs-lookup"><span data-stu-id="e8144-107">2511</span></span>|  
|<span data-ttu-id="e8144-108">Origine evento</span><span class="sxs-lookup"><span data-stu-id="e8144-108">Event Source</span></span>|<span data-ttu-id="e8144-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="e8144-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="e8144-110">Componente</span><span class="sxs-lookup"><span data-stu-id="e8144-110">Component</span></span>|<span data-ttu-id="e8144-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="e8144-111">SQLEngine</span></span>|  
|<span data-ttu-id="e8144-112">Nome simbolico</span><span class="sxs-lookup"><span data-stu-id="e8144-112">Symbolic Name</span></span>|<span data-ttu-id="e8144-113">DBCC_KEYS_OUT_OF_ORDER</span><span class="sxs-lookup"><span data-stu-id="e8144-113">DBCC_KEYS_OUT_OF_ORDER</span></span>|  
|<span data-ttu-id="e8144-114">Testo del messaggio</span><span class="sxs-lookup"><span data-stu-id="e8144-114">Message Text</span></span>|<span data-ttu-id="e8144-115">Errore di tabella: ID di oggetto %d, ID di indice %d, ID di partizione %I64d, ID di unità di allocazione %I64d (tipo %.\*ls).</span><span class="sxs-lookup"><span data-stu-id="e8144-115">Table error: Object ID %d, index ID %d, partition ID %I64d, alloc unit ID %I64d (type %.\*ls).</span></span> <span data-ttu-id="e8144-116">Chiavi non ordinate alla pagina %S_PGID, slot %d e %d.</span><span class="sxs-lookup"><span data-stu-id="e8144-116">Keys out of order on page %S_PGID, slots %d and %d.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="e8144-117">Spiegazione</span><span class="sxs-lookup"><span data-stu-id="e8144-117">Explanation</span></span>  
 <span data-ttu-id="e8144-118">Nell'indice specificato sono state rilevate chiavi non ordinate.</span><span class="sxs-lookup"><span data-stu-id="e8144-118">Out-of-order keys were detected in the specified index.</span></span> <span data-ttu-id="e8144-119">La pagina in cui sono contenute le chiavi può essere danneggiata.</span><span class="sxs-lookup"><span data-stu-id="e8144-119">The page in which the keys are contained may be corrupted.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="e8144-120">Azione dell'utente</span><span class="sxs-lookup"><span data-stu-id="e8144-120">User Action</span></span>  
 <span data-ttu-id="e8144-121">Ricompilare l'indice specificato utilizzando l'istruzione ALTER INDEX REBUILD.</span><span class="sxs-lookup"><span data-stu-id="e8144-121">Rebuild the specified index by using the ALTER INDEX REBUILD statement.</span></span>  
  
  
