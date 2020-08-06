---
title: Failover manuale in una sessione di mirroring del database (Transact-SQL) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: high-availability
ms.topic: conceptual
helpviewer_keywords:
- failover [SQL Server], database mirroring
- manual failover [SQL Server]
- database mirroring [SQL Server], failover
ms.assetid: 36218d61-b5f5-4194-905a-608e0e903db4
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 2c04ea4908ccbc4cfe4f6bb3606347dd444ef416
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87624900"
---
# <a name="manually-fail-over-a-database-mirroring-session-transact-sql"></a><span data-ttu-id="4a5e6-102">Failover manuale in una sessione di mirroring del database (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="4a5e6-102">Manually Fail Over a Database Mirroring Session (Transact-SQL)</span></span>
  <span data-ttu-id="4a5e6-103">Quando il database con mirroring è sincronizzato, ovvero è in stato SYNCHRONIZED, il proprietario del database può iniziare il failover manuale al server mirror.</span><span class="sxs-lookup"><span data-stu-id="4a5e6-103">When the mirrored database is synchronized (that is, when the database is in the SYNCHRONIZED state), the database owner can initiate manual failover to the mirror server.</span></span> <span data-ttu-id="4a5e6-104">Il failover manuale può essere avviato solo dal server principale.</span><span class="sxs-lookup"><span data-stu-id="4a5e6-104">Manual failover can be initiated only from the principal server.</span></span>  
  
### <a name="to-manually-fail-over-a-database-mirroring-session"></a><span data-ttu-id="4a5e6-105">Per eseguire il failover manuale in una sessione di mirroring del database</span><span class="sxs-lookup"><span data-stu-id="4a5e6-105">To manually fail over a database mirroring session</span></span>  
  
1.  <span data-ttu-id="4a5e6-106">Connettersi al server principale.</span><span class="sxs-lookup"><span data-stu-id="4a5e6-106">Connect to the principal server.</span></span>  
  
2.  <span data-ttu-id="4a5e6-107">Impostare il contesto del database sul database **master** :</span><span class="sxs-lookup"><span data-stu-id="4a5e6-107">Set the database context to the **master** database:</span></span>  
  
     `USE master;`  
  
3.  <span data-ttu-id="4a5e6-108">Eseguire l'istruzione seguente sul server principale:</span><span class="sxs-lookup"><span data-stu-id="4a5e6-108">Issue the following statement on the principal server:</span></span>  
  
     <span data-ttu-id="4a5e6-109">[ALTER DATABASE](/sql/t-sql/statements/alter-database-transact-sql-database-mirroring) *nome_database* SET PARTNER FAILOVER, dove *nome_database* rappresenta il database con mirroring.</span><span class="sxs-lookup"><span data-stu-id="4a5e6-109">[ALTER DATABASE](/sql/t-sql/statements/alter-database-transact-sql-database-mirroring) *database_name* SET PARTNER FAILOVER, where *database_name* is the mirrored database.</span></span>  
  
     <span data-ttu-id="4a5e6-110">Verrà avviata una transizione immediata del server mirror al ruolo principale.</span><span class="sxs-lookup"><span data-stu-id="4a5e6-110">This initiates an immediate transition of the mirror server to the principal role.</span></span>  
  
 <span data-ttu-id="4a5e6-111">Nel server principale precedente i client verranno disconnessi dal database e verrà eseguito il rollback delle transazioni di cui è in corso la migrazione.</span><span class="sxs-lookup"><span data-stu-id="4a5e6-111">On the former principal, clients are disconnected from the database and in-flight transactions are rolled back.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="4a5e6-112">Le transazioni preparate utilizzando [!INCLUDE[msCoName](../../includes/msconame-md.md)] Distributed Transaction Coordinator ma delle quali non sia stato ancora eseguito il commit quando si verifica un failover sono considerate interrotte dopo il failover del database.</span><span class="sxs-lookup"><span data-stu-id="4a5e6-112">Transactions that have been prepared by using the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Distributed Transaction Coordinator but are still not committed when a failover occurs are considered aborted after the database has failed over.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4a5e6-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="4a5e6-113">See Also</span></span>  
 <span data-ttu-id="4a5e6-114">[Mirroring del database di ALTER DATABASE &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-database-transact-sql-database-mirroring) </span><span class="sxs-lookup"><span data-stu-id="4a5e6-114">[ALTER DATABASE Database Mirroring &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-database-transact-sql-database-mirroring) </span></span>  
 <span data-ttu-id="4a5e6-115">[Eseguire il failover manuale di una sessione di mirroring del database &#40;SQL Server Management Studio&#41;](manually-fail-over-a-database-mirroring-session-sql-server-management-studio.md) </span><span class="sxs-lookup"><span data-stu-id="4a5e6-115">[Manually Fail Over a Database Mirroring Session &#40;SQL Server Management Studio&#41;](manually-fail-over-a-database-mirroring-session-sql-server-management-studio.md) </span></span>  
 [<span data-ttu-id="4a5e6-116">Cambio di ruolo durante una sessione di mirroring del database &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="4a5e6-116">Role Switching During a Database Mirroring Session &#40;SQL Server&#41;</span></span>](role-switching-during-a-database-mirroring-session-sql-server.md)  
  
  
