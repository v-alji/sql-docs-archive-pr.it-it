---
title: MSSQLSERVER_15517 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 15517 (Database Engine error)
ms.assetid: f94287f5-129f-4c52-9d34-62b996088001
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: b8e66e211faf03e1457953d0292e711cde1798ea
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87636157"
---
# <a name="mssqlserver_15517"></a><span data-ttu-id="f0e78-102">MSSQLSERVER_15517</span><span class="sxs-lookup"><span data-stu-id="f0e78-102">MSSQLSERVER_15517</span></span>
    
## <a name="details"></a><span data-ttu-id="f0e78-103">Dettagli</span><span class="sxs-lookup"><span data-stu-id="f0e78-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="f0e78-104">Nome prodotto</span><span class="sxs-lookup"><span data-stu-id="f0e78-104">Product Name</span></span>|[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]|  
|<span data-ttu-id="f0e78-105">ID evento</span><span class="sxs-lookup"><span data-stu-id="f0e78-105">Event ID</span></span>|<span data-ttu-id="f0e78-106">15517</span><span class="sxs-lookup"><span data-stu-id="f0e78-106">15517</span></span>|  
|<span data-ttu-id="f0e78-107">Origine evento</span><span class="sxs-lookup"><span data-stu-id="f0e78-107">Event Source</span></span>|<span data-ttu-id="f0e78-108">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="f0e78-108">MSSQLSERVER</span></span>|  
|<span data-ttu-id="f0e78-109">Componente</span><span class="sxs-lookup"><span data-stu-id="f0e78-109">Component</span></span>|<span data-ttu-id="f0e78-110">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="f0e78-110">SQLEngine</span></span>|  
|<span data-ttu-id="f0e78-111">Nome simbolico</span><span class="sxs-lookup"><span data-stu-id="f0e78-111">Symbolic Name</span></span>|<span data-ttu-id="f0e78-112">SEC_CANNOTEXECUTEASUSER</span><span class="sxs-lookup"><span data-stu-id="f0e78-112">SEC_CANNOTEXECUTEASUSER</span></span>|  
|<span data-ttu-id="f0e78-113">Testo del messaggio</span><span class="sxs-lookup"><span data-stu-id="f0e78-113">Message Text</span></span>|<span data-ttu-id="f0e78-114">Non può essere eseguita come entità di database perché l'entità "*principal*" non esiste; questo tipo di entità non può essere rappresentato oppure non si ha l'autorizzazione.</span><span class="sxs-lookup"><span data-stu-id="f0e78-114">Cannot execute as the database principal because the principal "*principal*" does not exist, this type of principal cannot be impersonated, or you do not have permission.</span></span>|  
  
## <a name="user-action"></a><span data-ttu-id="f0e78-115">Azione dell'utente</span><span class="sxs-lookup"><span data-stu-id="f0e78-115">User Action</span></span>  
 <span data-ttu-id="f0e78-116">Utilizzare il nome di un'entità esistente oppure ottenere l'autorizzazione IMPERSONATE per tale entità.</span><span class="sxs-lookup"><span data-stu-id="f0e78-116">Use the name of an existing principal or get the IMPERSONATE permission on that principal.</span></span>  
  
 <span data-ttu-id="f0e78-117">L'errore 15517 si può verificare anche dopo l'esecuzione di un'operazione di collegamento e ripristino di un database da un utente diverso dal proprietario del database originale.</span><span class="sxs-lookup"><span data-stu-id="f0e78-117">15517 can also occur after performing an attach and restore of a database by someone other than the original database owner.</span></span> <span data-ttu-id="f0e78-118">Per risolvere il problema, impostare db_owner su un account di accesso nel server, eseguendo il comando indicato di seguito:</span><span class="sxs-lookup"><span data-stu-id="f0e78-118">To resolve this error, change the db_owner to a login on your server, by running the following command:</span></span>  
  
```  
ALTER AUTHORIZATION ON DATABASE:: DBName TO [NewLogin]  
```  
  
## <a name="see-also"></a><span data-ttu-id="f0e78-119">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f0e78-119">See Also</span></span>  
 [<span data-ttu-id="f0e78-120">OLTP in memoria &#40;ottimizzazione per la memoria&#41;</span><span class="sxs-lookup"><span data-stu-id="f0e78-120">In-Memory OLTP &#40;In-Memory Optimization&#41;</span></span>](../in-memory-oltp/in-memory-oltp-in-memory-optimization.md)  
  
  
