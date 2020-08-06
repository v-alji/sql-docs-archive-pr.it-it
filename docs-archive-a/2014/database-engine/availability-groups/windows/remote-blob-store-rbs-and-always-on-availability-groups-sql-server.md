---
title: Archivio BLOB remoti (RBS) e Gruppi di disponibilità AlwaysOn (SQL Server) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: high-availability
ms.topic: conceptual
ms.assetid: 01a70258-d4fd-40bc-bc44-c490b5d6c420
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: f12a11162d286731b2b510a9051183e6c3025b2a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87626313"
---
# <a name="remote-blob-store-rbs-and-alwayson-availability-groups-sql-server"></a><span data-ttu-id="b0fb5-102">Archivio BLOB remoti (RBS) e gruppi di disponibilità AlwaysOn (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="b0fb5-102">Remote Blob Store (RBS) and AlwaysOn Availability Groups (SQL Server)</span></span>
  [!INCLUDE[ssHADR](../../../includes/sshadr-md.md)]<span data-ttu-id="b0fb5-103">può offrire una soluzione di disponibilità elevata e ripristino di emergenza per [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] gli oggetti BLOB (BLOB) di [archiviazione BLOB remoti](../../../relational-databases/blob/remote-blob-store-rbs-sql-server.md) .</span><span class="sxs-lookup"><span data-stu-id="b0fb5-103">can provide a high-availability and disaster recovery solution for [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)][Remote Blob Store (RBS)](../../../relational-databases/blob/remote-blob-store-rbs-sql-server.md) BLOB objects (blobs).</span></span> [!INCLUDE[ssHADR](../../../includes/sshadr-md.md)] <span data-ttu-id="b0fb5-104">protegge tutti i metadati e gli schemi di RBS archiviati in un database di disponibilità replicandoli nelle repliche secondarie.</span><span class="sxs-lookup"><span data-stu-id="b0fb5-104">protects any RBS metadata and schemas stored in an availability database by replicating them to the secondary replicas.</span></span> <span data-ttu-id="b0fb5-105">Questo è il database del contenuto di SharePoint.</span><span class="sxs-lookup"><span data-stu-id="b0fb5-105">This is the SharePoint Content Database.</span></span> <span data-ttu-id="b0fb5-106">In generale, tramite [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] questi metadati di RBS vengono archiviati in modo indipendente dal BLOB.</span><span class="sxs-lookup"><span data-stu-id="b0fb5-106">Generally speaking, [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] stores this RBS metadata independently from the blob.</span></span>  
  
 <span data-ttu-id="b0fb5-107">La protezione dei dati BLOB di RBS dipende dal percorso dell'archivio BLOB, come riportato di seguito:</span><span class="sxs-lookup"><span data-stu-id="b0fb5-107">The protection for RBD BLOB data depends on the BLOB Store Location, as follows:</span></span>  
  
|<span data-ttu-id="b0fb5-108">Percorso dell'archivio BLOB</span><span class="sxs-lookup"><span data-stu-id="b0fb5-108">BLOB Store Location</span></span>|<span data-ttu-id="b0fb5-109">Possibilità di protezione dei dati BLOB tramite i gruppi di disponibilità</span><span class="sxs-lookup"><span data-stu-id="b0fb5-109">Can Availability Groups Protect This BLOB Data?</span></span>|  
|-------------------------|-----------------------------------------------------|  
|<span data-ttu-id="b0fb5-110">Stesso database in cui sono contenuti i metadati di RBS (archiviato utilizzando un provider FILESTREAM remoto di RBS)</span><span class="sxs-lookup"><span data-stu-id="b0fb5-110">The same database that contains the RBS metadata  (stored using a RBS remote FILESTREAM provider)</span></span>|<span data-ttu-id="b0fb5-111">Sì</span><span class="sxs-lookup"><span data-stu-id="b0fb5-111">Yes</span></span>|  
|<span data-ttu-id="b0fb5-112">Database diverso nella stessa istanza di [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] (archiviato utilizzando un provider FILESTREAM remoto di RBS)</span><span class="sxs-lookup"><span data-stu-id="b0fb5-112">Another database in the same instance of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] (stored using a RBS remote FILESTREAM provider)</span></span>|<span data-ttu-id="b0fb5-113">Sì</span><span class="sxs-lookup"><span data-stu-id="b0fb5-113">Yes</span></span><br /><br /> <span data-ttu-id="b0fb5-114">È consigliabile inserire questo database nello stesso gruppo di disponibilità del database in cui sono contenuti i metadati di RBS.</span><span class="sxs-lookup"><span data-stu-id="b0fb5-114">We recommend that you put this database in the same availability group as the database that contains the RBS metadata.</span></span>|  
|<span data-ttu-id="b0fb5-115">Database diverso in un'istanza differente di [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] (archiviato utilizzando un provider FILESTREAM remoto di RBS)</span><span class="sxs-lookup"><span data-stu-id="b0fb5-115">Another database in a different instance of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] (stored using a RBS remote FILESTREAM provider)</span></span>|<span data-ttu-id="b0fb5-116">Sì</span><span class="sxs-lookup"><span data-stu-id="b0fb5-116">Yes</span></span><br /><br /> <span data-ttu-id="b0fb5-117">Questo database deve trovarsi in un gruppo di disponibilità separato.</span><span class="sxs-lookup"><span data-stu-id="b0fb5-117">This database must be in a separate availability group.</span></span>|  
|<span data-ttu-id="b0fb5-118">Archivio BLOB di terze parti</span><span class="sxs-lookup"><span data-stu-id="b0fb5-118">A third-party BLOB store</span></span>|<span data-ttu-id="b0fb5-119">No</span><span class="sxs-lookup"><span data-stu-id="b0fb5-119">No</span></span><br /><br /> <span data-ttu-id="b0fb5-120">Per proteggere questi dati BLOB, utilizzare i meccanismi di disponibilità elevata del provider dell'archivio BLOB.</span><span class="sxs-lookup"><span data-stu-id="b0fb5-120">To protect this BLOB data, use the high-availability mechanisms of the BLOB store provider.</span></span>|  
  
##  <a name="limitations"></a><a name="Limitations"></a> <span data-ttu-id="b0fb5-121">Limitazioni</span><span class="sxs-lookup"><span data-stu-id="b0fb5-121">Limitations</span></span>  
  
-   <span data-ttu-id="b0fb5-122">I gestori RBS devono essere indirizzati alla replica primaria.</span><span class="sxs-lookup"><span data-stu-id="b0fb5-122">RBS maintainers need to be targeted on the primary replica.</span></span>  
  
##  <a name="recommendations"></a><a name="Recommendations"></a> <span data-ttu-id="b0fb5-123">Indicazioni</span><span class="sxs-lookup"><span data-stu-id="b0fb5-123">Recommendations</span></span>  
  
-   <span data-ttu-id="b0fb5-124">Utilizzare un listener del gruppo di disponibilità.</span><span class="sxs-lookup"><span data-stu-id="b0fb5-124">Use an availability group listener.</span></span> <span data-ttu-id="b0fb5-125">Per altre informazioni, vedere [Listener del gruppo di disponibilità, connettività client e failover dell'applicazione &#40;SQL Server&#41;](../../listeners-client-connectivity-application-failover.md).</span><span class="sxs-lookup"><span data-stu-id="b0fb5-125">For more information, see [Availability Group Listeners, Client Connectivity, and Application Failover &#40;SQL Server&#41;](../../listeners-client-connectivity-application-failover.md).</span></span>  
  
##  <a name="related-content"></a><a name="RelatedContent"></a> <span data-ttu-id="b0fb5-126">Contenuto correlato</span><span class="sxs-lookup"><span data-stu-id="b0fb5-126">Related Content</span></span>  
  
-   <span data-ttu-id="b0fb5-127">[Maintaining Remote BLOB Store](https://msdn.microsoft.com/library/gg316773\(SQL.105\).aspx) (Gestione dell'archivio BLOB remoti) in [!INCLUDE[ssKilimanjaro](../../../includes/sskilimanjaro-md.md)] Documentazione online</span><span class="sxs-lookup"><span data-stu-id="b0fb5-127">[Maintaining Remote BLOB Store](https://msdn.microsoft.com/library/gg316773\(SQL.105\).aspx) (in [!INCLUDE[ssKilimanjaro](../../../includes/sskilimanjaro-md.md)] Books Online)</span></span>  
  
-   <span data-ttu-id="b0fb5-128">[Running RBS Maintainer](https://blogs.msdn.com/b/sqlrbs/archive/2010/03/19/running-rbs-maintainer.aspx) (Esecuzione di Gestore RBS) (blog)</span><span class="sxs-lookup"><span data-stu-id="b0fb5-128">[Running RBS Maintainer](https://blogs.msdn.com/b/sqlrbs/archive/2010/03/19/running-rbs-maintainer.aspx) (blog)</span></span>  
  
-   <span data-ttu-id="b0fb5-129">[Configure Remote BLOB Storage (RBS) with the FILESTREAM provider (SharePoint 2010)](https://blogs.msdn.com/b/mvpawardprogram/archive/2012/04/02/configure-remote-blob-storage-rbs-with-the-filestream-provider-sharepoint-2010.aspx) (Configurare l'archivio BLOB remoti (RBS) con il provider FILESTREAM (SharePoint 2010)) (blog)</span><span class="sxs-lookup"><span data-stu-id="b0fb5-129">[Configure Remote BLOB Storage (RBS) with the FILESTREAM provider (SharePoint 2010)](https://blogs.msdn.com/b/mvpawardprogram/archive/2012/04/02/configure-remote-blob-storage-rbs-with-the-filestream-provider-sharepoint-2010.aspx) (blog)</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b0fb5-130">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b0fb5-130">See Also</span></span>  
 <span data-ttu-id="b0fb5-131">[Connettività client AlwaysOn &#40;SQL Server&#41;](always-on-client-connectivity-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="b0fb5-131">[AlwaysOn Client Connectivity &#40;SQL Server&#41;](always-on-client-connectivity-sql-server.md) </span></span>  
 [<span data-ttu-id="b0fb5-132">Archivio Blob remoto &#40;RBS&#41; &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="b0fb5-132">Remote Blob Store &#40;RBS&#41; &#40;SQL Server&#41;</span></span>](../../../relational-databases/blob/remote-blob-store-rbs-sql-server.md)  
  
  
