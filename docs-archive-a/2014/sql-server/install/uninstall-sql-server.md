---
title: Disinstalla SQL Server 2014 | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: install
ms.topic: conceptual
ms.assetid: e6255f8e-a25e-4b3d-9310-c5da2f9c9333
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: e72f153c28a1ccd827150eb3dddc0b52321518a5
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87628136"
---
# <a name="uninstall-sql-server-2014"></a><span data-ttu-id="93a90-102">Disinstallare SQL Server 2014</span><span class="sxs-lookup"><span data-stu-id="93a90-102">Uninstall SQL Server 2014</span></span>
  <span data-ttu-id="93a90-103">Seguire gli argomenti indicati a continuazione per disinstallare completamente un'istanza esistente di [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] e preparare il sistema in modo che sia possibile reinstallare [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="93a90-103">Follow the topics below to uninstall an existing instance of [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] completely, and prepare the system so that you can reinstall [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="93a90-104">Contenuto della sezione</span><span class="sxs-lookup"><span data-stu-id="93a90-104">In This Section</span></span>  
 [<span data-ttu-id="93a90-105">Disinstallare un'istanza esistente di SQL Server &#40;Setup&#41;</span><span class="sxs-lookup"><span data-stu-id="93a90-105">Uninstall an Existing Instance of SQL Server &#40;Setup&#41;</span></span>](uninstall-an-existing-instance-of-sql-server-setup.md)  
 <span data-ttu-id="93a90-106">In questo argomento viene descritto come disinstallare manualmente un'istanza autonoma di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="93a90-106">This topic describes how to manually uninstall a stand-alone instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
 [<span data-ttu-id="93a90-107">Disinstallare PowerPivot per SharePoint</span><span class="sxs-lookup"><span data-stu-id="93a90-107">Uninstall PowerPivot for SharePoint</span></span>](uninstall-power-pivot-for-sharepoint.md)  
 <span data-ttu-id="93a90-108">In questo argomento si descrive come disinstallare manualmente PowerPivot per SharePoint.</span><span class="sxs-lookup"><span data-stu-id="93a90-108">This topic describes how to manually uninstall PowerPivot for SharePoint.</span></span>  
  
 [<span data-ttu-id="93a90-109">Disinstallare Reporting Services</span><span class="sxs-lookup"><span data-stu-id="93a90-109">Uninstall Reporting Services</span></span>](uninstall-reporting-services.md)  
 <span data-ttu-id="93a90-110">In questo argomento si descrive come disinstallare i server [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] sia per server in modalità SharePoint sia per quelli in modalità nativa.</span><span class="sxs-lookup"><span data-stu-id="93a90-110">This topic describes how to uninstall [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] servers for both SharePoint mode and Native mode servers.</span></span>  
  
 [<span data-ttu-id="93a90-111">Disinstallare e rimuovere Master Data Services</span><span class="sxs-lookup"><span data-stu-id="93a90-111">Uninstall and Remove Master Data Services</span></span>](uninstall-and-remove-master-data-services.md)  
 <span data-ttu-id="93a90-112">In questo argomento si descrive il processo di disinstallazione e rimozione di [!INCLUDE[ssMDSshort](../../includes/ssmdsshort-md.md)] dal computer locale.</span><span class="sxs-lookup"><span data-stu-id="93a90-112">This topic describes the process of uninstalling and removing [!INCLUDE[ssMDSshort](../../includes/ssmdsshort-md.md)] from the local computer.</span></span>  
  
 [<span data-ttu-id="93a90-113">Rimuovere oggetti server Data Quality Services</span><span class="sxs-lookup"><span data-stu-id="93a90-113">Remove Data Quality Server Objects</span></span>](remove-data-quality-server-objects.md)  
 <span data-ttu-id="93a90-114">In questo argomento si descrive come rimuovere manualmente gli oggetti [!INCLUDE[ssDQSServer](../../includes/ssdqsserver-md.md)] dopo aver disinstallato [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] o solo il componente [!INCLUDE[ssDQSServer](../../includes/ssdqsserver-md.md)] in [!INCLUDE[ssDQSnoversion](../../includes/ssdqsnoversion-md.md)] (DQS).</span><span class="sxs-lookup"><span data-stu-id="93a90-114">This topic describes how to manually remove the [!INCLUDE[ssDQSServer](../../includes/ssdqsserver-md.md)] objects after uninstalling either [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] or just the [!INCLUDE[ssDQSServer](../../includes/ssdqsserver-md.md)] component in [!INCLUDE[ssDQSnoversion](../../includes/ssdqsnoversion-md.md)] (DQS).</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="93a90-115">Sezioni correlate</span><span class="sxs-lookup"><span data-stu-id="93a90-115">Related Sections</span></span>  
  
-   [<span data-ttu-id="93a90-116">Rimuovere un'istanza del cluster di failover di SQL Server &#40;programma di installazione&#41;</span><span class="sxs-lookup"><span data-stu-id="93a90-116">Remove a SQL Server Failover Cluster Instance &#40;Setup&#41;</span></span>](../failover-clusters/install/remove-a-sql-server-failover-cluster-instance-setup.md)  
  
-   [<span data-ttu-id="93a90-117">Aggiungere o rimuovere nodi in un cluster di failover di SQL Server &#40;programma di installazione&#41;</span><span class="sxs-lookup"><span data-stu-id="93a90-117">Add or Remove Nodes in a SQL Server Failover Cluster &#40;Setup&#41;</span></span>](../failover-clusters/install/add-or-remove-nodes-in-a-sql-server-failover-cluster-setup.md)  
  
-   [<span data-ttu-id="93a90-118">Rimuovere un'installazione di SQL Server 2014</span><span class="sxs-lookup"><span data-stu-id="93a90-118">Drop a SQL Server 2014 Installation</span></span>](../../database-engine/install-windows/repair-a-failed-sql-server-installation.md)  
  
## <a name="see-also"></a><span data-ttu-id="93a90-119">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="93a90-119">See Also</span></span>  
 <span data-ttu-id="93a90-120">[Pianificazione di un'installazione di SQL Server](planning-a-sql-server-installation.md) </span><span class="sxs-lookup"><span data-stu-id="93a90-120">[Planning a SQL Server Installation](planning-a-sql-server-installation.md) </span></span>  
 <span data-ttu-id="93a90-121">[Installare SQL Server 2014](../../database-engine/install-windows/install-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="93a90-121">[Install SQL Server 2014](../../database-engine/install-windows/install-sql-server.md) </span></span>  
 [<span data-ttu-id="93a90-122">Aggiornamento a SQL Server 2014</span><span class="sxs-lookup"><span data-stu-id="93a90-122">Upgrade to SQL Server 2014</span></span>](../../database-engine/install-windows/upgrade-sql-server.md)  
  
  
