---
title: MSSQL_ENG014005 | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
helpviewer_keywords:
- MSSQL_ENG014005 error
ms.assetid: f168f0d6-cb11-45d4-9781-c374d7f388ee
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: d820fd26cceee72b0d08204d6f6ce73a76508e9c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87624070"
---
# <a name="mssql_eng014005"></a><span data-ttu-id="74f6c-102">MSSQL_ENG014005</span><span class="sxs-lookup"><span data-stu-id="74f6c-102">MSSQL_ENG014005</span></span>
    
## <a name="message-details"></a><span data-ttu-id="74f6c-103">Dettagli messaggio</span><span class="sxs-lookup"><span data-stu-id="74f6c-103">Message Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="74f6c-104">Nome prodotto</span><span class="sxs-lookup"><span data-stu-id="74f6c-104">Product Name</span></span>|<span data-ttu-id="74f6c-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="74f6c-105">SQL Server</span></span>|  
|<span data-ttu-id="74f6c-106">ID evento</span><span class="sxs-lookup"><span data-stu-id="74f6c-106">Event ID</span></span>|<span data-ttu-id="74f6c-107">14005</span><span class="sxs-lookup"><span data-stu-id="74f6c-107">14005</span></span>|  
|<span data-ttu-id="74f6c-108">Origine evento</span><span class="sxs-lookup"><span data-stu-id="74f6c-108">Event Source</span></span>|<span data-ttu-id="74f6c-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="74f6c-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="74f6c-110">Componente</span><span class="sxs-lookup"><span data-stu-id="74f6c-110">Component</span></span>|[!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)]|  
|<span data-ttu-id="74f6c-111">Nome simbolico</span><span class="sxs-lookup"><span data-stu-id="74f6c-111">Symbolic Name</span></span>||  
|<span data-ttu-id="74f6c-112">Testo del messaggio</span><span class="sxs-lookup"><span data-stu-id="74f6c-112">Message Text</span></span>|<span data-ttu-id="74f6c-113">Impossibile eliminare la pubblicazione.</span><span class="sxs-lookup"><span data-stu-id="74f6c-113">Could not drop publication.</span></span> <span data-ttu-id="74f6c-114">Vi è associata una sottoscrizione.</span><span class="sxs-lookup"><span data-stu-id="74f6c-114">A subscription exists to it.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="74f6c-115">Spiegazione</span><span class="sxs-lookup"><span data-stu-id="74f6c-115">Explanation</span></span>  
 <span data-ttu-id="74f6c-116">Si è tentato di eliminare una pubblicazione alla quale sono associate una o più sottoscrizioni.</span><span class="sxs-lookup"><span data-stu-id="74f6c-116">You have tried to drop a publication which has one or more associated subscriptions.</span></span> <span data-ttu-id="74f6c-117">È possibile eliminare una pubblicazione solo se non vi sono sottoscrizioni associate.</span><span class="sxs-lookup"><span data-stu-id="74f6c-117">A publication can only be dropped if there are no associated subscriptions.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="74f6c-118">Azione dell'utente</span><span class="sxs-lookup"><span data-stu-id="74f6c-118">User Action</span></span>  
 <span data-ttu-id="74f6c-119">Eliminare le sottoscrizioni prima di eliminare la pubblicazione.</span><span class="sxs-lookup"><span data-stu-id="74f6c-119">Drop the subscriptions before dropping the publication.</span></span> <span data-ttu-id="74f6c-120">Se si utilizza [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] per eliminare la pubblicazione, si potrà scegliere di eliminare automaticamente tutte le sottoscrizioni associate prima di eliminare la pubblicazione.</span><span class="sxs-lookup"><span data-stu-id="74f6c-120">If you use [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] to drop the publication, it will give you the option to automatically drop all associated subscriptions before dropping the publication.</span></span> <span data-ttu-id="74f6c-121">Se si utilizzano stored procedure, è necessario prima eliminare esplicitamente le sottoscrizioni.</span><span class="sxs-lookup"><span data-stu-id="74f6c-121">If you use stored procedures, you must explicitly drop the subscriptions first.</span></span> <span data-ttu-id="74f6c-122">Per ulteriori informazioni, vedere [Delete a Push Subscription](delete-a-push-subscription.md) e [Delete a Pull Subscription](delete-a-pull-subscription.md).</span><span class="sxs-lookup"><span data-stu-id="74f6c-122">For more information, see [Delete a Push Subscription](delete-a-push-subscription.md) and [Delete a Pull Subscription](delete-a-pull-subscription.md).</span></span>  
  
 <span data-ttu-id="74f6c-123">Se apparentemente non vi sono sottoscrizioni associate alla pubblicazione o se viene visualizzato questo errore durante la creazione di una pubblicazione, potrebbe esserci una sottoscrizione precedente che non è stata eliminata completamente dopo la rimozione.</span><span class="sxs-lookup"><span data-stu-id="74f6c-123">If no subscriptions appear to exist for the publication or if you see this error when you create a publication, you might have a previous subscription that was not completely cleaned up when it was removed.</span></span> <span data-ttu-id="74f6c-124">Eseguire [sp_removedbreplication &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-removedbreplication-transact-sql) sul database per rimuovere tutti gli oggetti e le impostazioni inerenti alla replica.</span><span class="sxs-lookup"><span data-stu-id="74f6c-124">Execute [sp_removedbreplication &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-removedbreplication-transact-sql) on the database to remove all objects and settings related to replication.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="74f6c-125">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="74f6c-125">See Also</span></span>  
 [<span data-ttu-id="74f6c-126">Guida di riferimento a errori ed eventi &#40;replica&#41;</span><span class="sxs-lookup"><span data-stu-id="74f6c-126">Errors and Events Reference &#40;Replication&#41;</span></span>](errors-and-events-reference-replication.md)  
  
  
