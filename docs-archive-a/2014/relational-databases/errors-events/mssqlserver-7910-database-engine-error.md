---
title: MSSQLSERVER_7910 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 7910 (Database Engine error)
ms.assetid: 017a0113-2b17-40b3-a419-30bbc43d46b8
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 60e7cca3f6973374ae7aeaa959a0b31207a1258e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87628706"
---
# <a name="mssqlserver_7910"></a><span data-ttu-id="f4d12-102">MSSQLSERVER_7910</span><span class="sxs-lookup"><span data-stu-id="f4d12-102">MSSQLSERVER_7910</span></span>
    
## <a name="details"></a><span data-ttu-id="f4d12-103">Dettagli</span><span class="sxs-lookup"><span data-stu-id="f4d12-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="f4d12-104">Nome prodotto</span><span class="sxs-lookup"><span data-stu-id="f4d12-104">Product Name</span></span>|<span data-ttu-id="f4d12-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="f4d12-105">SQL Server</span></span>|  
|<span data-ttu-id="f4d12-106">ID evento</span><span class="sxs-lookup"><span data-stu-id="f4d12-106">Event ID</span></span>|<span data-ttu-id="f4d12-107">7910</span><span class="sxs-lookup"><span data-stu-id="f4d12-107">7910</span></span>|  
|<span data-ttu-id="f4d12-108">Origine evento</span><span class="sxs-lookup"><span data-stu-id="f4d12-108">Event Source</span></span>|<span data-ttu-id="f4d12-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="f4d12-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="f4d12-110">Componente</span><span class="sxs-lookup"><span data-stu-id="f4d12-110">Component</span></span>|<span data-ttu-id="f4d12-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="f4d12-111">SQLEngine</span></span>|  
|<span data-ttu-id="f4d12-112">Nome simbolico</span><span class="sxs-lookup"><span data-stu-id="f4d12-112">Symbolic Name</span></span>|<span data-ttu-id="f4d12-113">DBCC2_REPAIR_PAGE_ALLOCATED</span><span class="sxs-lookup"><span data-stu-id="f4d12-113">DBCC2_REPAIR_PAGE_ALLOCATED</span></span>|  
|<span data-ttu-id="f4d12-114">Testo del messaggio</span><span class="sxs-lookup"><span data-stu-id="f4d12-114">Message Text</span></span>|<span data-ttu-id="f4d12-115">Correzione: la pagina P_ID è stata allocata all'oggetto con ID O_ID, indice con ID I_ID, partizione con ID PN_ID, unità allocazione con ID A_ID (tipo TYPE).</span><span class="sxs-lookup"><span data-stu-id="f4d12-115">Repair: The page P_ID has been allocated to object ID O_ID, index ID I_ID, partition ID PN_ID, alloc unit ID A_ID (type TYPE).</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="f4d12-116">Spiegazione</span><span class="sxs-lookup"><span data-stu-id="f4d12-116">Explanation</span></span>  
 <span data-ttu-id="f4d12-117">Si tratta di un messaggio informativo generato dall'istruzione REPAIR in cui viene indicato che una pagina è stata allocata alla matrice di slot a pagina singola di una mappa di allocazione degli indici (IAM, Index Allocation Map).</span><span class="sxs-lookup"><span data-stu-id="f4d12-117">This is an informational message from REPAIR that states that a page has been allocated to the single-page slot array of an Index Allocation Map (IAM) page.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="f4d12-118">Azione dell'utente</span><span class="sxs-lookup"><span data-stu-id="f4d12-118">User Action</span></span>  
 <span data-ttu-id="f4d12-119">nessuno</span><span class="sxs-lookup"><span data-stu-id="f4d12-119">None</span></span>  
  
  
