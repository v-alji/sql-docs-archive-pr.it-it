---
title: MSSQL_ENG014144 | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
helpviewer_keywords:
- MSSQL_ENG014144 error
ms.assetid: fdc744d5-530e-48c4-9420-cca032fd482b
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 0d93f06a585bcc01c52438ff7b99bbd635532402
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87623174"
---
# <a name="mssql_eng014144"></a><span data-ttu-id="ff95d-102">MSSQL_ENG014144</span><span class="sxs-lookup"><span data-stu-id="ff95d-102">MSSQL_ENG014144</span></span>
    
## <a name="message-details"></a><span data-ttu-id="ff95d-103">Dettagli messaggio</span><span class="sxs-lookup"><span data-stu-id="ff95d-103">Message Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="ff95d-104">Nome prodotto</span><span class="sxs-lookup"><span data-stu-id="ff95d-104">Product Name</span></span>|<span data-ttu-id="ff95d-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="ff95d-105">SQL Server</span></span>|  
|<span data-ttu-id="ff95d-106">ID evento</span><span class="sxs-lookup"><span data-stu-id="ff95d-106">Event ID</span></span>|<span data-ttu-id="ff95d-107">14144</span><span class="sxs-lookup"><span data-stu-id="ff95d-107">14144</span></span>|  
|<span data-ttu-id="ff95d-108">Origine evento</span><span class="sxs-lookup"><span data-stu-id="ff95d-108">Event Source</span></span>|<span data-ttu-id="ff95d-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="ff95d-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="ff95d-110">Componente</span><span class="sxs-lookup"><span data-stu-id="ff95d-110">Component</span></span>|[!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)]|  
|<span data-ttu-id="ff95d-111">Nome simbolico</span><span class="sxs-lookup"><span data-stu-id="ff95d-111">Symbolic Name</span></span>||  
|<span data-ttu-id="ff95d-112">Testo del messaggio</span><span class="sxs-lookup"><span data-stu-id="ff95d-112">Message Text</span></span>|<span data-ttu-id="ff95d-113">Al Sottoscrittore '%s' sono associate sottoscrizioni nel database di pubblicazione '%s'.</span><span class="sxs-lookup"><span data-stu-id="ff95d-113">Cannot drop Subscriber '%s'.</span></span> <span data-ttu-id="ff95d-114">Impossibile eliminarlo.</span><span class="sxs-lookup"><span data-stu-id="ff95d-114">There are subscriptions for it in the publication database '%s'.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="ff95d-115">Spiegazione</span><span class="sxs-lookup"><span data-stu-id="ff95d-115">Explanation</span></span>  
 <span data-ttu-id="ff95d-116">Non è possibile rimuovere dal ruolo del Sottoscrittore un'istanza di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] che è configurata come Sottoscrittore fino a che vi sono sottoscrizioni attive configurate per quell'istanza.</span><span class="sxs-lookup"><span data-stu-id="ff95d-116">A [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instance that is configured as a Subscriber cannot be removed from the role of Subscriber while there are active subscriptions configured for the instance.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="ff95d-117">Azione dell'utente</span><span class="sxs-lookup"><span data-stu-id="ff95d-117">User Action</span></span>  
 <span data-ttu-id="ff95d-118">Eliminare tutte le sottoscrizioni associate prima di tentare di modificare lo stato del Sottoscrittore dell'istanza di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] :</span><span class="sxs-lookup"><span data-stu-id="ff95d-118">Drop all associated subscriptions before attempting to change the Subscriber status of the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instance:</span></span>  
  
1.  <span data-ttu-id="ff95d-119">Per trovare le sottoscrizioni, eseguire [sp_helpsubscription &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-helpsubscription-transact-sql) nel database di pubblicazione sul server di pubblicazione.</span><span class="sxs-lookup"><span data-stu-id="ff95d-119">Execute [sp_helpsubscription &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-helpsubscription-transact-sql) in the publication database at the Publisher to find subscriptions.</span></span>  
  
2.  <span data-ttu-id="ff95d-120">Per eliminare le sottoscrizioni, eseguire [sp_dropsubscription &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-dropsubscription-transact-sql) nel database di pubblicazione.</span><span class="sxs-lookup"><span data-stu-id="ff95d-120">Execute [sp_dropsubscription &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-dropsubscription-transact-sql) in the publication database to drop subscriptions.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ff95d-121">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ff95d-121">See Also</span></span>  
 <span data-ttu-id="ff95d-122">[Guida di riferimento a errori ed eventi &#40;replica&#41;](errors-and-events-reference-replication.md) </span><span class="sxs-lookup"><span data-stu-id="ff95d-122">[Errors and Events Reference &#40;Replication&#41;](errors-and-events-reference-replication.md) </span></span>  
 [<span data-ttu-id="ff95d-123">Sottoscrizione delle pubblicazioni</span><span class="sxs-lookup"><span data-stu-id="ff95d-123">Subscribe to Publications</span></span>](subscribe-to-publications.md)  
  
  
