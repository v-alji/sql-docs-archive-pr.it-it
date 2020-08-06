---
title: 'Mirroring del database: Interoperabilità e coesistenza (SQL Server) | Microsoft Docs'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: high-availability
ms.topic: conceptual
helpviewer_keywords:
- high availability [SQL Server], interoperability and coexistence
- Database Engine [SQL Server], high availability
ms.assetid: 89fef397-e0cf-4e08-b598-25b8d4170523
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 057392842974c3342fc57d0ec113f8b1bb58b9dd
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87627394"
---
# <a name="database-mirroring-interoperability-and-coexistence-sql-server"></a><span data-ttu-id="752a5-102">Mirroring del database: interoperabilità e coesistenza (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="752a5-102">Database Mirroring: Interoperability and Coexistence (SQL Server)</span></span>
  <span data-ttu-id="752a5-103">È possibile utilizzare il mirroring del database con i componenti e le funzionalità seguenti di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]:</span><span class="sxs-lookup"><span data-stu-id="752a5-103">Database mirroring can be used with the following features or components of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]:</span></span>  
  
-   [<span data-ttu-id="752a5-104">Istanze del cluster di failover AlwaysOn (Clustering di failover SQL Server)</span><span class="sxs-lookup"><span data-stu-id="752a5-104">AlwaysOn Failover Cluster Instances (SQL Server Failover Clustering)</span></span>](database-mirroring-and-sql-server-failover-cluster-instances.md)  
  
-   [<span data-ttu-id="752a5-105">Change Data Capture (e rilevamento delle modifiche)</span><span class="sxs-lookup"><span data-stu-id="752a5-105">Change data capture (and change tracking)</span></span>](../../relational-databases/track-changes/change-data-capture-and-other-sql-server-features.md)  
  
-   [<span data-ttu-id="752a5-106">Snapshot di database</span><span class="sxs-lookup"><span data-stu-id="752a5-106">Database snapshots</span></span>](../../relational-databases/databases/database-snapshots-sql-server.md)  
  
-   [<span data-ttu-id="752a5-107">Cataloghi full-text</span><span class="sxs-lookup"><span data-stu-id="752a5-107">Full-text catalogs</span></span>](database-mirroring-and-full-text-catalogs-sql-server.md)  
  
-   [<span data-ttu-id="752a5-108">Log shipping</span><span class="sxs-lookup"><span data-stu-id="752a5-108">Log shipping</span></span>](database-mirroring-and-log-shipping-sql-server.md)  
  
-   [<span data-ttu-id="752a5-109">Replica</span><span class="sxs-lookup"><span data-stu-id="752a5-109">Replication</span></span>](database-mirroring-and-replication-sql-server.md)  
  
 <span data-ttu-id="752a5-110">Il mirroring del database non consente di interoperare con gli elementi seguenti:</span><span class="sxs-lookup"><span data-stu-id="752a5-110">Database mirroring does not interoperate with the following:</span></span>  
  
-   <span data-ttu-id="752a5-111">Transazioni tra database e transazioni distribuite</span><span class="sxs-lookup"><span data-stu-id="752a5-111">Cross-database transactions/distributed transactions</span></span>  
  
     <span data-ttu-id="752a5-112">Per altre informazioni sui motivi per cui queste transazioni non sono supportate, vedere [Transazioni tra database non supportate per il mirroring del database o i gruppi di disponibilità AlwaysOn &#40;SQL Server&#41;](../availability-groups/windows/transactions-always-on-availability-and-database-mirroring.md).</span><span class="sxs-lookup"><span data-stu-id="752a5-112">For information about why such transactions are not supported, see [Cross-Database Transactions Not Supported For Database Mirroring or AlwaysOn Availability Groups &#40;SQL Server&#41;](../availability-groups/windows/transactions-always-on-availability-and-database-mirroring.md).</span></span>  
  
-   [!INCLUDE[ssHADR](../../includes/sshadr-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="752a5-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="752a5-113">See Also</span></span>  
 [<span data-ttu-id="752a5-114">Mirroring del database &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="752a5-114">Database Mirroring &#40;SQL Server&#41;</span></span>](database-mirroring-sql-server.md)  
  
  
