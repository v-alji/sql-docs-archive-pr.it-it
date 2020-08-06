---
title: MSSQLSERVER_7916 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 7916 (Database Engine error)
ms.assetid: 9bac3536-de14-4e98-84c2-bde9a59ba0d1
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 21b31eedf61369d9c4d1cfdfd5f53eebd3f5341c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87629418"
---
# <a name="mssqlserver_7916"></a><span data-ttu-id="f792f-102">MSSQLSERVER_7916</span><span class="sxs-lookup"><span data-stu-id="f792f-102">MSSQLSERVER_7916</span></span>
    
## <a name="details"></a><span data-ttu-id="f792f-103">Dettagli</span><span class="sxs-lookup"><span data-stu-id="f792f-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="f792f-104">Nome prodotto</span><span class="sxs-lookup"><span data-stu-id="f792f-104">Product Name</span></span>|<span data-ttu-id="f792f-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="f792f-105">SQL Server</span></span>|  
|<span data-ttu-id="f792f-106">ID evento</span><span class="sxs-lookup"><span data-stu-id="f792f-106">Event ID</span></span>|<span data-ttu-id="f792f-107">7916</span><span class="sxs-lookup"><span data-stu-id="f792f-107">7916</span></span>|  
|<span data-ttu-id="f792f-108">Origine evento</span><span class="sxs-lookup"><span data-stu-id="f792f-108">Event Source</span></span>|<span data-ttu-id="f792f-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="f792f-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="f792f-110">Componente</span><span class="sxs-lookup"><span data-stu-id="f792f-110">Component</span></span>|<span data-ttu-id="f792f-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="f792f-111">SQLEngine</span></span>|  
|<span data-ttu-id="f792f-112">Nome simbolico</span><span class="sxs-lookup"><span data-stu-id="f792f-112">Symbolic Name</span></span>|<span data-ttu-id="f792f-113">DBCC2_REPAIR_RECORD_DELETED</span><span class="sxs-lookup"><span data-stu-id="f792f-113">DBCC2_REPAIR_RECORD_DELETED</span></span>|  
|<span data-ttu-id="f792f-114">Testo del messaggio</span><span class="sxs-lookup"><span data-stu-id="f792f-114">Message Text</span></span>|<span data-ttu-id="f792f-115">Correzione: record eliminato per l'oggetto con ID O_ID, indice con ID I_ID, partizione con ID PN_ID, unità allocazione con ID A_ID (tipo TYPE), a pagina P_ID, slot S_ID.</span><span class="sxs-lookup"><span data-stu-id="f792f-115">Repair: Deleted record for object ID O_ID, index ID I_ID, partition ID PN_ID, alloc unit ID A_ID (type TYPE), on page P_ID, slot S_ID.</span></span> <span data-ttu-id="f792f-116">Gli indici verranno ricompilati.</span><span class="sxs-lookup"><span data-stu-id="f792f-116">Indexes will be rebuilt.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="f792f-117">Spiegazione</span><span class="sxs-lookup"><span data-stu-id="f792f-117">Explanation</span></span>  
 <span data-ttu-id="f792f-118">Messaggio informativo inviato da REPAIR che indica che il record specificato è stato eliminato dalla pagina.</span><span class="sxs-lookup"><span data-stu-id="f792f-118">This is an information messages from REPAIR that indicates the specified record was deleted from the page.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="f792f-119">Azione dell'utente</span><span class="sxs-lookup"><span data-stu-id="f792f-119">User Action</span></span>  
 <span data-ttu-id="f792f-120">nessuno</span><span class="sxs-lookup"><span data-stu-id="f792f-120">None</span></span>  
  
  
