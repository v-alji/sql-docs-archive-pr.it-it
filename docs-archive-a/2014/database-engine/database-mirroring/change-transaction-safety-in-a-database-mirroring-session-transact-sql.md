---
title: Modifica della protezione delle transazioni in una sessione di mirroring del database (Transact-SQL) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: high-availability
ms.topic: conceptual
helpviewer_keywords:
- transaction safety [SQL Server database mirroring]
ms.assetid: 8b03bb82-8589-4558-8545-9942fe008391
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: d8bc9d0fb639770d33507c29a6ec67f60bd0434a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87626288"
---
# <a name="change-transaction-safety-in-a-database-mirroring-session-transact-sql"></a><span data-ttu-id="e9da5-102">Modifica della protezione delle transazioni in una sessione di mirroring del database (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="e9da5-102">Change Transaction Safety in a Database Mirroring Session (Transact-SQL)</span></span>
  <span data-ttu-id="e9da5-103">La protezione delle transazioni è l'attributo che controlla la modalità operativa della sessione.</span><span class="sxs-lookup"><span data-stu-id="e9da5-103">Transaction safety is the attribute that controls the operating mode of the session.</span></span> <span data-ttu-id="e9da5-104">Il proprietario del database può tuttavia modificare in qualsiasi momento tale protezione.</span><span class="sxs-lookup"><span data-stu-id="e9da5-104">At any time, however, the database owner can change the transaction safety.</span></span> <span data-ttu-id="e9da5-105">Per impostazione predefinita, il livello di protezione delle transazioni è impostato su FULL (modalità operativa sincrona).</span><span class="sxs-lookup"><span data-stu-id="e9da5-105">By default, the level of transaction safety is set to FULL (synchronous operating mode).</span></span>  
  
 <span data-ttu-id="e9da5-106">Se la protezione delle transazioni viene disabilitata, la sessione passa alla modalità operativa asincrona che consente di ottimizzare le prestazioni.</span><span class="sxs-lookup"><span data-stu-id="e9da5-106">Turning off transaction safety shifts the session into asynchronous operating mode, which maximizes performance.</span></span> <span data-ttu-id="e9da5-107">In caso di indisponibilità del server principale, il server mirror viene arrestato ma risulta disponibile come server di standby a caldo (warm standby). Per il failover è necessario forzare il servizio, pertanto potrebbero verificarsi perdite di dati.</span><span class="sxs-lookup"><span data-stu-id="e9da5-107">If the principal becomes unavailable, the mirror stops but is available as a warm standby (failover requires forcing service with possible data loss).</span></span>  
  
### <a name="to-turn-on-transaction-safety"></a><span data-ttu-id="e9da5-108">Per attivare la protezione delle transazioni</span><span class="sxs-lookup"><span data-stu-id="e9da5-108">To turn on transaction safety</span></span>  
  
1.  <span data-ttu-id="e9da5-109">Connettersi al server principale.</span><span class="sxs-lookup"><span data-stu-id="e9da5-109">Connect to the principal server.</span></span>  
  
2.  <span data-ttu-id="e9da5-110">Eseguire l'istruzione Transact-SQL seguente:</span><span class="sxs-lookup"><span data-stu-id="e9da5-110">Issue the following Transact-SQL statement:</span></span>  
  
    ```  
    ALTER DATABASE <database> SET PARTNER SAFETY FULL  
    ```  
  
     <span data-ttu-id="e9da5-111">dove *\<database>* è il nome del database con mirroring.</span><span class="sxs-lookup"><span data-stu-id="e9da5-111">where *\<database>* is the name of the mirrored database.</span></span>  
  
### <a name="to-turn-off-transaction-safety"></a><span data-ttu-id="e9da5-112">Per disabilitare la protezione delle transazioni</span><span class="sxs-lookup"><span data-stu-id="e9da5-112">To turn off transaction safety</span></span>  
  
1.  <span data-ttu-id="e9da5-113">Connettersi al server principale.</span><span class="sxs-lookup"><span data-stu-id="e9da5-113">Connect to the principal server.</span></span>  
  
2.  <span data-ttu-id="e9da5-114">Eseguire l'istruzione seguente:</span><span class="sxs-lookup"><span data-stu-id="e9da5-114">Issue the following statement:</span></span>  
  
    ```  
    ALTER DATABASE <database> SET PARTNER SAFETY OFF  
    ```  
  
     <span data-ttu-id="e9da5-115">dove *\<database>* è il database con mirroring.</span><span class="sxs-lookup"><span data-stu-id="e9da5-115">where *\<database>* is the mirrored database.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e9da5-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e9da5-116">See Also</span></span>  
 <span data-ttu-id="e9da5-117">[Mirroring del database di ALTER DATABASE &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-database-transact-sql-database-mirroring) </span><span class="sxs-lookup"><span data-stu-id="e9da5-117">[ALTER DATABASE Database Mirroring &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-database-transact-sql-database-mirroring) </span></span>  
 [<span data-ttu-id="e9da5-118">Database Mirroring Operating Modes</span><span class="sxs-lookup"><span data-stu-id="e9da5-118">Database Mirroring Operating Modes</span></span>](database-mirroring-operating-modes.md)  
  
  
