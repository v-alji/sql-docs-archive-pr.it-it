---
title: MSSQLSERVER_2530 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
ms.assetid: 5d4be07a-38a5-4b25-819c-4dcb4636cc15
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 30b57aae907d6f0acc4d1c0e6021bf936621c69e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87624234"
---
# <a name="mssqlserver_2530"></a><span data-ttu-id="42ac8-102">MSSQLSERVER_2530</span><span class="sxs-lookup"><span data-stu-id="42ac8-102">MSSQLSERVER_2530</span></span>
    
## <a name="details"></a><span data-ttu-id="42ac8-103">Dettagli</span><span class="sxs-lookup"><span data-stu-id="42ac8-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="42ac8-104">Nome prodotto</span><span class="sxs-lookup"><span data-stu-id="42ac8-104">Product Name</span></span>|<span data-ttu-id="42ac8-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="42ac8-105">SQL Server</span></span>|  
|<span data-ttu-id="42ac8-106">ID evento</span><span class="sxs-lookup"><span data-stu-id="42ac8-106">Event ID</span></span>|<span data-ttu-id="42ac8-107">2530</span><span class="sxs-lookup"><span data-stu-id="42ac8-107">2530</span></span>|  
|<span data-ttu-id="42ac8-108">Origine evento</span><span class="sxs-lookup"><span data-stu-id="42ac8-108">Event Source</span></span>|<span data-ttu-id="42ac8-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="42ac8-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="42ac8-110">Componente</span><span class="sxs-lookup"><span data-stu-id="42ac8-110">Component</span></span>|<span data-ttu-id="42ac8-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="42ac8-111">SQLEngine</span></span>|  
|<span data-ttu-id="42ac8-112">Nome simbolico</span><span class="sxs-lookup"><span data-stu-id="42ac8-112">Symbolic Name</span></span>|<span data-ttu-id="42ac8-113">DBCC_INDEX_IS_OFFLINE</span><span class="sxs-lookup"><span data-stu-id="42ac8-113">DBCC_INDEX_IS_OFFLINE</span></span>|  
|<span data-ttu-id="42ac8-114">Testo del messaggio</span><span class="sxs-lookup"><span data-stu-id="42ac8-114">Message Text</span></span>|<span data-ttu-id="42ac8-115">L'indice "%.\*ls" sulla tabella "%.\*ls" è disabilitato.</span><span class="sxs-lookup"><span data-stu-id="42ac8-115">The index "%.\*ls" on table "%.\*ls" is disabled.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="42ac8-116">Spiegazione</span><span class="sxs-lookup"><span data-stu-id="42ac8-116">Explanation</span></span>  
 <span data-ttu-id="42ac8-117">L'istruzione DBCC non può proseguire perché l'indice specificato è disabilitato.</span><span class="sxs-lookup"><span data-stu-id="42ac8-117">The DBCC statement cannot proceed because the specified index is disabled.</span></span> <span data-ttu-id="42ac8-118">Dopo che un indice viene disabilitato, resta in questo stato fino a quando non viene ricompilato o eliminato e quindi ricreato.</span><span class="sxs-lookup"><span data-stu-id="42ac8-118">After an index is disabled, it remains in a disabled state until it is rebuilt or dropped and re-created.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="42ac8-119">Azione dell'utente</span><span class="sxs-lookup"><span data-stu-id="42ac8-119">User Action</span></span>  
  
1.  <span data-ttu-id="42ac8-120">Abilitare l'indice disabilitato utilizzando uno dei metodi seguenti:</span><span class="sxs-lookup"><span data-stu-id="42ac8-120">Enable the disabled index by using one of the following methods:</span></span>  
  
    -   <span data-ttu-id="42ac8-121">Istruzione ALTER INDEX con la clausola REBUILD</span><span class="sxs-lookup"><span data-stu-id="42ac8-121">ALTER INDEX statement with the REBUILD clause</span></span>  
  
    -   <span data-ttu-id="42ac8-122">Istruzione CREATE INDEX con la clausola DROP_EXISTING</span><span class="sxs-lookup"><span data-stu-id="42ac8-122">CREATE INDEX with the DROP_EXISTING clause</span></span>  
  
    -   <span data-ttu-id="42ac8-123">DBCC DBREINDEX</span><span class="sxs-lookup"><span data-stu-id="42ac8-123">DBCC DBREINDEX</span></span>  
  
2.  <span data-ttu-id="42ac8-124">Rieseguire l'istruzione DBCC.</span><span class="sxs-lookup"><span data-stu-id="42ac8-124">Rerun the DBCC statement.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="42ac8-125">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="42ac8-125">See Also</span></span>  
 <span data-ttu-id="42ac8-126">[Abilita indici e vincoli](../indexes/enable-indexes-and-constraints.md) </span><span class="sxs-lookup"><span data-stu-id="42ac8-126">[Enable Indexes and Constraints](../indexes/enable-indexes-and-constraints.md) </span></span>  
 <span data-ttu-id="42ac8-127">[ALTER INDEX &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-index-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="42ac8-127">[ALTER INDEX &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-index-transact-sql) </span></span>  
 <span data-ttu-id="42ac8-128">[CREATE INDEX &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-index-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="42ac8-128">[CREATE INDEX &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-index-transact-sql) </span></span>  
 [<span data-ttu-id="42ac8-129">DBCC DBREINDEX &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="42ac8-129">DBCC DBREINDEX &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/database-console-commands/dbcc-dbreindex-transact-sql)  
  
  
