---
title: MSSQLSERVER_1406 | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 1406 (Database Engine error)
ms.assetid: 915f97de-9b74-41f8-8bd5-b2d061416718
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: adaa0084b875f720c477189e0e8e085af124f4cb
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87718209"
---
# <a name="mssqlserver_1406"></a><span data-ttu-id="747de-102">MSSQLSERVER_1406</span><span class="sxs-lookup"><span data-stu-id="747de-102">MSSQLSERVER_1406</span></span>
    
## <a name="details"></a><span data-ttu-id="747de-103">Dettagli</span><span class="sxs-lookup"><span data-stu-id="747de-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="747de-104">Nome prodotto</span><span class="sxs-lookup"><span data-stu-id="747de-104">Product Name</span></span>|<span data-ttu-id="747de-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="747de-105">SQL Server</span></span>|  
|<span data-ttu-id="747de-106">ID evento</span><span class="sxs-lookup"><span data-stu-id="747de-106">Event ID</span></span>|<span data-ttu-id="747de-107">1406</span><span class="sxs-lookup"><span data-stu-id="747de-107">1406</span></span>|  
|<span data-ttu-id="747de-108">Origine evento</span><span class="sxs-lookup"><span data-stu-id="747de-108">Event Source</span></span>|<span data-ttu-id="747de-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="747de-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="747de-110">Componente</span><span class="sxs-lookup"><span data-stu-id="747de-110">Component</span></span>|<span data-ttu-id="747de-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="747de-111">SQLEngine</span></span>|  
|<span data-ttu-id="747de-112">Nome simbolico</span><span class="sxs-lookup"><span data-stu-id="747de-112">Symbolic Name</span></span>|<span data-ttu-id="747de-113">DBM_BADSTATEFORFORCESERVICE</span><span class="sxs-lookup"><span data-stu-id="747de-113">DBM_BADSTATEFORFORCESERVICE</span></span>|  
|<span data-ttu-id="747de-114">Testo del messaggio</span><span class="sxs-lookup"><span data-stu-id="747de-114">Message Text</span></span>|<span data-ttu-id="747de-115">Impossibile forzare il servizio senza rischi.</span><span class="sxs-lookup"><span data-stu-id="747de-115">Unable to force service safely.</span></span> <span data-ttu-id="747de-116">Per ottenere l'accesso, rimuovere il mirroring del database e recuperare il database "%.\*ls".</span><span class="sxs-lookup"><span data-stu-id="747de-116">Remove database mirroring and recover database "%.\*ls" to gain access.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="747de-117">Spiegazione</span><span class="sxs-lookup"><span data-stu-id="747de-117">Explanation</span></span>  
 <span data-ttu-id="747de-118">Il [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] non può forzare il servizio perché lo stato del mirroring non è in grado di garantire che il servizio venga forzato correttamente.</span><span class="sxs-lookup"><span data-stu-id="747de-118">The [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] cannot force service because the mirroring state cannot guarantee that the force service process would work correctly.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="747de-119">Azione dell'utente</span><span class="sxs-lookup"><span data-stu-id="747de-119">User Action</span></span>  
 <span data-ttu-id="747de-120">Rimuovere il mirroring del database.</span><span class="sxs-lookup"><span data-stu-id="747de-120">Remove database mirroring.</span></span> <span data-ttu-id="747de-121">Sarà quindi possibile recuperare il database mirror per potervi accedere.</span><span class="sxs-lookup"><span data-stu-id="747de-121">You can then recover the mirror database to gain access to it.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="747de-122">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="747de-122">See Also</span></span>  
 <span data-ttu-id="747de-123">[Utilizzo forzato del servizio in una sessione di mirroring del database &#40;Transact-SQL&#41;](../../database-engine/database-mirroring/force-service-in-a-database-mirroring-session-transact-sql.md) </span><span class="sxs-lookup"><span data-stu-id="747de-123">[Force Service in a Database Mirroring Session &#40;Transact-SQL&#41;](../../database-engine/database-mirroring/force-service-in-a-database-mirroring-session-transact-sql.md) </span></span>  
 [<span data-ttu-id="747de-124">Rimozione del mirroring del database &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="747de-124">Removing Database Mirroring &#40;SQL Server&#41;</span></span>](../../database-engine/database-mirroring/database-mirroring-sql-server.md)  
  
  
