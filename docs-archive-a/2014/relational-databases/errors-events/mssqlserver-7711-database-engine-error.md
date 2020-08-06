---
title: MSSQLSERVER_7711 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 7711 (Database Engine error)
ms.assetid: a5c7cd6e-18d6-47ef-902b-db9dd64bba34
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: e29b2ea993e8e5332ef03b05f628dc791e20aba9
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87628723"
---
# <a name="mssqlserver_7711"></a><span data-ttu-id="0b477-102">MSSQLSERVER_7711</span><span class="sxs-lookup"><span data-stu-id="0b477-102">MSSQLSERVER_7711</span></span>
    
## <a name="details"></a><span data-ttu-id="0b477-103">Dettagli</span><span class="sxs-lookup"><span data-stu-id="0b477-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="0b477-104">Nome prodotto</span><span class="sxs-lookup"><span data-stu-id="0b477-104">Product Name</span></span>|<span data-ttu-id="0b477-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="0b477-105">SQL Server</span></span>|  
|<span data-ttu-id="0b477-106">ID evento</span><span class="sxs-lookup"><span data-stu-id="0b477-106">Event ID</span></span>|<span data-ttu-id="0b477-107">7711</span><span class="sxs-lookup"><span data-stu-id="0b477-107">7711</span></span>|  
|<span data-ttu-id="0b477-108">Origine evento</span><span class="sxs-lookup"><span data-stu-id="0b477-108">Event Source</span></span>|<span data-ttu-id="0b477-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="0b477-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="0b477-110">Componente</span><span class="sxs-lookup"><span data-stu-id="0b477-110">Component</span></span>|<span data-ttu-id="0b477-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="0b477-111">SQLEngine</span></span>|  
|<span data-ttu-id="0b477-112">Nome simbolico</span><span class="sxs-lookup"><span data-stu-id="0b477-112">Symbolic Name</span></span>|<span data-ttu-id="0b477-113">PRT_RANGE_OVERLAP</span><span class="sxs-lookup"><span data-stu-id="0b477-113">PRT_RANGE_OVERLAP</span></span>|  
|<span data-ttu-id="0b477-114">Testo del messaggio</span><span class="sxs-lookup"><span data-stu-id="0b477-114">Message Text</span></span>|<span data-ttu-id="0b477-115">L'opzione DATA_COMPRESSION è stata specificata più di una volta per la tabella o per l'indice o per una delle relative partizioni.</span><span class="sxs-lookup"><span data-stu-id="0b477-115">The DATA_COMPRESSION option was specified more than once for the table or index or one of its partitions.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="0b477-116">Spiegazione</span><span class="sxs-lookup"><span data-stu-id="0b477-116">Explanation</span></span>  
 <span data-ttu-id="0b477-117">Si è verificato un errore nell'opzione DATA_COMPRESSION di una delle istruzioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="0b477-117">An error occurred in the DATA_COMPRESSION option in one of the following statements:</span></span>  
  
-   <span data-ttu-id="0b477-118">CREA TABELLA</span><span class="sxs-lookup"><span data-stu-id="0b477-118">CREATE TABLE</span></span>  
  
-   <span data-ttu-id="0b477-119">MODIFICA TABELLA</span><span class="sxs-lookup"><span data-stu-id="0b477-119">ALTER TABLE</span></span>  
  
-   <span data-ttu-id="0b477-120">CREATE INDEX</span><span class="sxs-lookup"><span data-stu-id="0b477-120">CREATE INDEX</span></span>  
  
-   <span data-ttu-id="0b477-121">ALTER INDEX</span><span class="sxs-lookup"><span data-stu-id="0b477-121">ALTER INDEX</span></span>  
  
 <span data-ttu-id="0b477-122">Se la tabella o l'indice indicato è partizionato, l'opzione DATA_COMPRESSION è stata elencata più volte per almeno una delle partizioni.</span><span class="sxs-lookup"><span data-stu-id="0b477-122">If the table or index cited is partitioned, the DATA_COMPRESSION option was listed more than one time for at least one of the partitions.</span></span> <span data-ttu-id="0b477-123">Se la tabella o l'indice non è partizionato, l'opzione DATA_COMPRESSION è stata indicata più volte.</span><span class="sxs-lookup"><span data-stu-id="0b477-123">If the table or index is not partitioned, the DATA_COMPRESSION option was cited more than one time.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="0b477-124">Azione dell'utente</span><span class="sxs-lookup"><span data-stu-id="0b477-124">User Action</span></span>  
 <span data-ttu-id="0b477-125">Per una tabella o un indice partizionato, verificare che l'opzione DATA_COMPRESSION sia specificata solo una volta per ciascuna partizione.</span><span class="sxs-lookup"><span data-stu-id="0b477-125">For a partitioned table or index, make sure that the DATA_COMPRESSION option is specified only one time for each partition.</span></span> <span data-ttu-id="0b477-126">Per una tabella o un indice non partizionato, utilizzare l'opzione DATA_COMPRESSION solo una volta nell'istruzione.</span><span class="sxs-lookup"><span data-stu-id="0b477-126">For a table or index that is not partitioned, use the DATA_COMPRESSION option only one time in the statement.</span></span>  
  
  
