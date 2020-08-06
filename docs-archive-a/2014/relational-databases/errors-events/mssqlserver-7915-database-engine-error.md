---
title: MSSQLSERVER_7915 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 7915 (Database Engine error)
ms.assetid: 63338587-7dd3-40e6-b70e-d8ae18fff47b
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: e1dc7a69023e49b48a10da9f0388cbd72fbe46be
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87629417"
---
# <a name="mssqlserver_7915"></a><span data-ttu-id="2cc58-102">MSSQLSERVER_7915</span><span class="sxs-lookup"><span data-stu-id="2cc58-102">MSSQLSERVER_7915</span></span>
    
## <a name="details"></a><span data-ttu-id="2cc58-103">Dettagli</span><span class="sxs-lookup"><span data-stu-id="2cc58-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="2cc58-104">Nome prodotto</span><span class="sxs-lookup"><span data-stu-id="2cc58-104">Product Name</span></span>|<span data-ttu-id="2cc58-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="2cc58-105">SQL Server</span></span>|  
|<span data-ttu-id="2cc58-106">ID evento</span><span class="sxs-lookup"><span data-stu-id="2cc58-106">Event ID</span></span>|<span data-ttu-id="2cc58-107">7915</span><span class="sxs-lookup"><span data-stu-id="2cc58-107">7915</span></span>|  
|<span data-ttu-id="2cc58-108">Origine evento</span><span class="sxs-lookup"><span data-stu-id="2cc58-108">Event Source</span></span>|<span data-ttu-id="2cc58-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="2cc58-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="2cc58-110">Componente</span><span class="sxs-lookup"><span data-stu-id="2cc58-110">Component</span></span>|<span data-ttu-id="2cc58-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="2cc58-111">SQLEngine</span></span>|  
|<span data-ttu-id="2cc58-112">Nome simbolico</span><span class="sxs-lookup"><span data-stu-id="2cc58-112">Symbolic Name</span></span>|<span data-ttu-id="2cc58-113">DBCC2_REPAIR_IAM_CHAIN_REBUILT</span><span class="sxs-lookup"><span data-stu-id="2cc58-113">DBCC2_REPAIR_IAM_CHAIN_REBUILT</span></span>|  
|<span data-ttu-id="2cc58-114">Testo del messaggio</span><span class="sxs-lookup"><span data-stu-id="2cc58-114">Message Text</span></span>|<span data-ttu-id="2cc58-115">Correzione: la catena IAM per l'oggetto con ID O_ID, indice con ID I_ID, partizione con ID PN_ID, unità allocazione con ID A_ID (tipo TYPE), è stata troncata prima della pagina P_ID e verrà ricompilata.</span><span class="sxs-lookup"><span data-stu-id="2cc58-115">Repair: IAM chain for object ID O_ID, index ID I_ID, partition ID PN_ID, alloc unit ID A_ID (type TYPE), has been truncated before page P_ID and will be rebuilt.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="2cc58-116">Spiegazione</span><span class="sxs-lookup"><span data-stu-id="2cc58-116">Explanation</span></span>  
 <span data-ttu-id="2cc58-117">Si tratta di un messaggio informativo inviato da REPAIR che indica che la catena IAM (Index Allocation Map) specificata è stata corretta in modo da essere ricompilata.</span><span class="sxs-lookup"><span data-stu-id="2cc58-117">This is an information message sent by REPAIR that indicates that the specified Index Allocation Map (IAM) chain was patched so that it could be rebuilt.</span></span> <span data-ttu-id="2cc58-118">Per la correzione può essere necessaria l'allocazione di un nuovo inizio della catena IAM o la rimozione delle pagine danneggiate dalla catena.</span><span class="sxs-lookup"><span data-stu-id="2cc58-118">This patching may have required the allocation of a new head of the IAM chain or the removal of bad pages from the chain.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="2cc58-119">Azione dell'utente</span><span class="sxs-lookup"><span data-stu-id="2cc58-119">User Action</span></span>  
 <span data-ttu-id="2cc58-120">nessuno</span><span class="sxs-lookup"><span data-stu-id="2cc58-120">None</span></span>  
  
  
