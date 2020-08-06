---
title: MSSQLSERVER_617 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 617 (Database Engine error)
ms.assetid: 213545d9-08a7-4427-bfd1-8b7e16644281
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 88e9feb7c3ac5d8cf646d2243319b2b160b7757e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87718155"
---
# <a name="mssqlserver_617"></a><span data-ttu-id="b791a-102">MSSQLSERVER_617</span><span class="sxs-lookup"><span data-stu-id="b791a-102">MSSQLSERVER_617</span></span>
    
## <a name="details"></a><span data-ttu-id="b791a-103">Dettagli</span><span class="sxs-lookup"><span data-stu-id="b791a-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="b791a-104">Nome prodotto</span><span class="sxs-lookup"><span data-stu-id="b791a-104">Product Name</span></span>|<span data-ttu-id="b791a-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="b791a-105">SQL Server</span></span>|  
|<span data-ttu-id="b791a-106">ID evento</span><span class="sxs-lookup"><span data-stu-id="b791a-106">Event ID</span></span>|<span data-ttu-id="b791a-107">617</span><span class="sxs-lookup"><span data-stu-id="b791a-107">617</span></span>|  
|<span data-ttu-id="b791a-108">Origine evento</span><span class="sxs-lookup"><span data-stu-id="b791a-108">Event Source</span></span>|<span data-ttu-id="b791a-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="b791a-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="b791a-110">Componente</span><span class="sxs-lookup"><span data-stu-id="b791a-110">Component</span></span>|<span data-ttu-id="b791a-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="b791a-111">SQLEngine</span></span>|  
|<span data-ttu-id="b791a-112">Nome simbolico</span><span class="sxs-lookup"><span data-stu-id="b791a-112">Symbolic Name</span></span>|<span data-ttu-id="b791a-113">NODESHASH</span><span class="sxs-lookup"><span data-stu-id="b791a-113">NODESHASH</span></span>|  
|<span data-ttu-id="b791a-114">Testo del messaggio</span><span class="sxs-lookup"><span data-stu-id="b791a-114">Message Text</span></span>|<span data-ttu-id="b791a-115">Impossibile trovare nella tabella hash il descrittore per l'ID di oggetto %ld nel database con ID %d durante il tentativo di annullare l'hashing.</span><span class="sxs-lookup"><span data-stu-id="b791a-115">Descriptor for object ID %ld in database ID %d not found in the hash table during attempt to unhash it.</span></span> <span data-ttu-id="b791a-116">Voce mancante in una tabella di lavoro.</span><span class="sxs-lookup"><span data-stu-id="b791a-116">A work table is missing an entry.</span></span> <span data-ttu-id="b791a-117">Eseguire nuovamente la query.</span><span class="sxs-lookup"><span data-stu-id="b791a-117">Rerun the query.</span></span> <span data-ttu-id="b791a-118">Se viene utilizzato un cursore, chiuderlo e riaprirlo.</span><span class="sxs-lookup"><span data-stu-id="b791a-118">If a cursor is involved, close and reopen the cursor.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="b791a-119">Spiegazione</span><span class="sxs-lookup"><span data-stu-id="b791a-119">Explanation</span></span>  
 <span data-ttu-id="b791a-120">SQL Server non è in grado di trovare la tabella di lavoro per una voce specifica.</span><span class="sxs-lookup"><span data-stu-id="b791a-120">SQL Server cannot locate the work table for a specific entry.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="b791a-121">Azione dell'utente</span><span class="sxs-lookup"><span data-stu-id="b791a-121">User Action</span></span>  
  
1.  <span data-ttu-id="b791a-122">Se viene utilizzato un cursore, chiuderlo e riaprirlo.</span><span class="sxs-lookup"><span data-stu-id="b791a-122">If a cursor is involved, close the cursor and re-open the cursor.</span></span>  
  
2.  <span data-ttu-id="b791a-123">Eseguire nuovamente la query.</span><span class="sxs-lookup"><span data-stu-id="b791a-123">Run the query again.</span></span>  
  
  
