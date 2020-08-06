---
title: MSSQLSERVER_7911 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 7911 (Database Engine error)
ms.assetid: dd8390f3-0f77-4fb2-ba94-631a56e42bc6
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 6d37ce2dc11f231e8a6f8ae6cc8b95d8b2f87c12
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87628704"
---
# <a name="mssqlserver_7911"></a><span data-ttu-id="7753a-102">MSSQLSERVER_7911</span><span class="sxs-lookup"><span data-stu-id="7753a-102">MSSQLSERVER_7911</span></span>
    
## <a name="details"></a><span data-ttu-id="7753a-103">Dettagli</span><span class="sxs-lookup"><span data-stu-id="7753a-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="7753a-104">Nome prodotto</span><span class="sxs-lookup"><span data-stu-id="7753a-104">Product Name</span></span>|<span data-ttu-id="7753a-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="7753a-105">SQL Server</span></span>|  
|<span data-ttu-id="7753a-106">ID evento</span><span class="sxs-lookup"><span data-stu-id="7753a-106">Event ID</span></span>|<span data-ttu-id="7753a-107">7911</span><span class="sxs-lookup"><span data-stu-id="7753a-107">7911</span></span>|  
|<span data-ttu-id="7753a-108">Origine evento</span><span class="sxs-lookup"><span data-stu-id="7753a-108">Event Source</span></span>|<span data-ttu-id="7753a-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="7753a-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="7753a-110">Componente</span><span class="sxs-lookup"><span data-stu-id="7753a-110">Component</span></span>|<span data-ttu-id="7753a-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="7753a-111">SQLEngine</span></span>|  
|<span data-ttu-id="7753a-112">Nome simbolico</span><span class="sxs-lookup"><span data-stu-id="7753a-112">Symbolic Name</span></span>|<span data-ttu-id="7753a-113">DBCC2_REPAIR_PAGE_DEALLOCATED</span><span class="sxs-lookup"><span data-stu-id="7753a-113">DBCC2_REPAIR_PAGE_DEALLOCATED</span></span>|  
|<span data-ttu-id="7753a-114">Testo del messaggio</span><span class="sxs-lookup"><span data-stu-id="7753a-114">Message Text</span></span>|<span data-ttu-id="7753a-115">Correzione: la pagina P_ID è stata deallocata all'oggetto con ID O_ID, indice con ID I_ID, partizione con ID PN_ID, unità allocazione con ID A_ID (tipo TYPE).</span><span class="sxs-lookup"><span data-stu-id="7753a-115">Repair: The page P_ID has been deallocated from object ID O_ID, index ID I_ID, partition ID PN_ID, alloc unit ID A_ID (type TYPE).</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="7753a-116">Spiegazione</span><span class="sxs-lookup"><span data-stu-id="7753a-116">Explanation</span></span>  
 <span data-ttu-id="7753a-117">Si tratta di un messaggio informativo generato dall'istruzione REPAIR in cui viene indicato che una pagina è stata deallocata dalla matrice di slot a pagina singola di una mappa di allocazione degli indici (IAM, Index Allocation Map).</span><span class="sxs-lookup"><span data-stu-id="7753a-117">This is an informational message from REPAIR that states that a page has been deallocated from the single-page slot array of an Index Allocation Map (IAM) page.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="7753a-118">Azione dell'utente</span><span class="sxs-lookup"><span data-stu-id="7753a-118">User Action</span></span>  
 <span data-ttu-id="7753a-119">nessuno</span><span class="sxs-lookup"><span data-stu-id="7753a-119">None</span></span>  
  
  
