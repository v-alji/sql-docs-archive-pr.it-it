---
title: Uso forzato del servizio in una sessione di mirroring del database (Transact-SQL) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: high-availability
ms.topic: conceptual
helpviewer_keywords:
- forced service [SQL Server]
- database mirroring [SQL Server], forcing service
ms.assetid: 8b6ffe77-35f3-4e2a-a658-8a38a8e1c794
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: b909f3602a78f3244ab3cf4479b8745956a7bd62
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87726248"
---
# <a name="force-service-in-a-database-mirroring-session-transact-sql"></a><span data-ttu-id="cd9f3-102">Utilizzo forzato del servizio in una sessione di mirroring del database (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="cd9f3-102">Force Service in a Database Mirroring Session (Transact-SQL)</span></span>
  <span data-ttu-id="cd9f3-103">Nella modalità a prestazioni elevate e in quella a sicurezza elevata senza failover automatico, se si verifica un errore nel server principale mentre è disponibile il server mirror, il proprietario del database può rendere disponibile il database forzando il failover del servizio nel database mirror, sebbene tale operazione implichi la possibile perdita di dati.</span><span class="sxs-lookup"><span data-stu-id="cd9f3-103">In high-performance mode and high-safety mode without automatic failover, if the principal server fails while the mirror server is available, the database owner can make the database available by forcing service to fail over (with possible data loss) to the mirror database.</span></span> <span data-ttu-id="cd9f3-104">Questa opzione è disponibile esclusivamente nelle condizioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="cd9f3-104">This option is available only under all the following conditions:</span></span>  
  
-   <span data-ttu-id="cd9f3-105">Il server principale non è disponibile.</span><span class="sxs-lookup"><span data-stu-id="cd9f3-105">The principal server is down.</span></span>  
  
-   <span data-ttu-id="cd9f3-106">WITNESS è impostato su OFF o connesso al server mirror.</span><span class="sxs-lookup"><span data-stu-id="cd9f3-106">WITNESS is set to OFF or is connected to the mirror server.</span></span>  
  
> [!CAUTION]  
>  <span data-ttu-id="cd9f3-107">Il servizio forzato rappresenta esclusivamente un metodo di ripristino di emergenza.</span><span class="sxs-lookup"><span data-stu-id="cd9f3-107">Forced service is strictly a disaster recovery method.</span></span> <span data-ttu-id="cd9f3-108">L'utilizzo forzato del servizio può implicare perdite di dati.</span><span class="sxs-lookup"><span data-stu-id="cd9f3-108">Forcing service may involve some data loss.</span></span> <span data-ttu-id="cd9f3-109">È quindi consigliabile forzare il servizio solo se si è consapevoli che il ripristino immediato del servizio nel database può causare perdite di dati.</span><span class="sxs-lookup"><span data-stu-id="cd9f3-109">Therefore, force service only if you are willing to risk losing some data in order to restore service to the database immediately.</span></span> <span data-ttu-id="cd9f3-110">Se l'utilizzo forzato del servizio implica il rischio della perdita di dati importanti, è consigliabile arrestare il mirroring e risincronizzare manualmente i database.</span><span class="sxs-lookup"><span data-stu-id="cd9f3-110">If forcing service risks losing significant data, we recommend that you stop mirroring and manually resynchronize the databases.</span></span> <span data-ttu-id="cd9f3-111">Per altre informazioni sui rischi dell'uso forzato del servizio, vedere [Modalità di funzionamento del mirroring del database](database-mirroring-operating-modes.md).</span><span class="sxs-lookup"><span data-stu-id="cd9f3-111">For more information about the risks of forcing service, see [Database Mirroring Operating Modes](database-mirroring-operating-modes.md).</span></span>  
  
 <span data-ttu-id="cd9f3-112">L'utilizzo forzato del servizio comporta l'interruzione della sessione e l'avvio di un nuovo fork di recupero.</span><span class="sxs-lookup"><span data-stu-id="cd9f3-112">Forcing service suspends the session and starts a new recovery fork.</span></span> <span data-ttu-id="cd9f3-113">L'effetto dell'utilizzo forzato del servizio è simile alla rimozione del mirroring e al recupero del database principale precedente.</span><span class="sxs-lookup"><span data-stu-id="cd9f3-113">The effect of forcing service is similar to removing mirroring and recovering the former principal database.</span></span> <span data-ttu-id="cd9f3-114">Tuttavia, l'utilizzo forzato del servizio facilita la risincronizzazione dei database, con possibile perdita di dati, quando viene ripreso il mirroring.</span><span class="sxs-lookup"><span data-stu-id="cd9f3-114">However, forcing service facilitates resynchronizing the databases (with possible data loss) when mirroring resumes.</span></span>  
  
### <a name="to-force-service-in-a-database-mirroring-session"></a><span data-ttu-id="cd9f3-115">Per forzare il servizio in una sessione di mirroring del database</span><span class="sxs-lookup"><span data-stu-id="cd9f3-115">To force service in a database mirroring session</span></span>  
  
1.  <span data-ttu-id="cd9f3-116">Connettersi al server mirror.</span><span class="sxs-lookup"><span data-stu-id="cd9f3-116">Connect to the mirror server.</span></span>  
  
2.  <span data-ttu-id="cd9f3-117">Eseguire l'istruzione seguente:</span><span class="sxs-lookup"><span data-stu-id="cd9f3-117">Issue the following statement:</span></span>  
  
     <span data-ttu-id="cd9f3-118">ALTER DATABASE *<nome_database>* SET PARTNER FORCE_SERVICE_ALLOW_DATA_LOSS</span><span class="sxs-lookup"><span data-stu-id="cd9f3-118">ALTER DATABASE *<database_name>* SET PARTNER FORCE_SERVICE_ALLOW_DATA_LOSS</span></span>  
  
     <span data-ttu-id="cd9f3-119">dove *<nome_database>* corrisponde al database con mirroring.</span><span class="sxs-lookup"><span data-stu-id="cd9f3-119">where *<database_name>* is the mirrored database.</span></span>  
  
     <span data-ttu-id="cd9f3-120">Il server mirror esegue immediatamente la transizione al server principale e il mirroring viene sospeso.</span><span class="sxs-lookup"><span data-stu-id="cd9f3-120">The mirror server immediately transitions to principal server, and mirroring is suspended.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cd9f3-121">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="cd9f3-121">See Also</span></span>  
 <span data-ttu-id="cd9f3-122">[ALTER DATABASE &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-database-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="cd9f3-122">[ALTER DATABASE &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-database-transact-sql) </span></span>  
 [<span data-ttu-id="cd9f3-123">Database Mirroring Operating Modes</span><span class="sxs-lookup"><span data-stu-id="cd9f3-123">Database Mirroring Operating Modes</span></span>](database-mirroring-operating-modes.md)  
  
  
