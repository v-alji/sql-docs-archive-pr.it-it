---
title: Ospitare un database del server di report in un cluster di failover di SQL Server | Microsoft Docs
ms.custom: ''
ms.date: 08/10/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
ms.assetid: 7bd5f019-2857-452f-a023-cc3b9e93aec4
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 921ce03fd08e7820266b828d5848f64db1e257ee
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87716115"
---
# <a name="host-a-report-server-database-in-a-sql-server-failover-cluster"></a><span data-ttu-id="ce15c-102">Ospitare un database del server di report in un cluster di failover di SQL Server</span><span class="sxs-lookup"><span data-stu-id="ce15c-102">Host a Report Server Database in a SQL Server Failover Cluster</span></span>
  [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="ce15c-103">offre supporto per il clustering di failover, per consentire l'utilizzo di più dischi per una o più istanze di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="ce15c-103">provides failover clustering support so that you can use multiple disks for one or more [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instances.</span></span> <span data-ttu-id="ce15c-104">Il clustering di failover è supportato solo per il database del server di report e non è possibile eseguire il servizio Windows ReportServer o il servizio Web come parte di un cluster di failover.</span><span class="sxs-lookup"><span data-stu-id="ce15c-104">Failover clustering is supported only for the report server database; you cannot run the Report Server service as part of a failover cluster.</span></span>  
  
 <span data-ttu-id="ce15c-105">Per ospitare un database del server di report in un cluster di failover di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , è necessario che il cluster sia già installato e configurato.</span><span class="sxs-lookup"><span data-stu-id="ce15c-105">To host a report server database on a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] failover cluster, the cluster must already be installed and configured.</span></span> <span data-ttu-id="ce15c-106">È quindi possibile selezionare il cluster di failover come nome del server quando si crea il database del server di report nella pagina Impostazione database dello strumento Gestione configurazione [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="ce15c-106">You can then select the failover cluster as the server name when you create the report server database in the Database Setup page of the [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] Configuration tool.</span></span>  
  
 <span data-ttu-id="ce15c-107">Sebbene il servizio Windows ReportServer non possa essere eseguito come parte di un cluster di failover, è possibile installare [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] in un computer in cui è installato un cluster di failover di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="ce15c-107">Although the Report Server service cannot participate in a failover cluster, you can install [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] on a computer that has a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] failover cluster installed.</span></span> <span data-ttu-id="ce15c-108">Il server di report viene eseguito indipendentemente dal cluster di failover.</span><span class="sxs-lookup"><span data-stu-id="ce15c-108">The report server runs independently of the failover cluster.</span></span> <span data-ttu-id="ce15c-109">Se si installa un server di report in un computer che fa parte di un'istanza di failover di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , non è necessario utilizzare il cluster di failover per il database del server di report, ma, per ospitare il database, è possibile utilizzare un'istanza di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] diversa.</span><span class="sxs-lookup"><span data-stu-id="ce15c-109">If you install a report server on a computer that is part of a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] failover instance, you are not required to use the failover cluster for the report server database; you can use a different [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instance to host the database.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ce15c-110">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ce15c-110">See Also</span></span>  
 <span data-ttu-id="ce15c-111">[Database del server di report &#40;modalità nativa SSRS&#41;](../report-server/report-server-database-ssrs-native-mode.md) </span><span class="sxs-lookup"><span data-stu-id="ce15c-111">[Report Server Database &#40;SSRS Native Mode&#41;](../report-server/report-server-database-ssrs-native-mode.md) </span></span>  
 [<span data-ttu-id="ce15c-112">Creare un database del server di report &#40;Gestione configurazione SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="ce15c-112">Create a Report Server Database  &#40;SSRS Configuration Manager&#41;</span></span>](../../sql-server/install/create-a-report-server-database-ssrs-configuration-manager.md)  
  
  
