---
title: Il servizio cluster WSFC è offline | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: high-availability
ms.topic: conceptual
f1_keywords:
- sql12.swb.agdashboard.agp1WSFCquorum.issues.f1
helpviewer_keywords:
- Availability Groups [SQL Server], policies
ms.assetid: d502548d-ece6-4a42-9ded-2157d33e3d21
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: e6e7b48f96eb09638291b1d0655d385d606b1666
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87716824"
---
# <a name="wsfc-cluster-service-is-offline"></a><span data-ttu-id="76c6f-102">Il servizio cluster WSFC è offline</span><span class="sxs-lookup"><span data-stu-id="76c6f-102">WSFC cluster service is offline</span></span>
    
## <a name="introduction"></a><span data-ttu-id="76c6f-103">Introduzione</span><span class="sxs-lookup"><span data-stu-id="76c6f-103">Introduction</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="76c6f-104">**Nome criteri**</span><span class="sxs-lookup"><span data-stu-id="76c6f-104">**Policy Name**</span></span>|<span data-ttu-id="76c6f-105">Stato del cluster WSFC</span><span class="sxs-lookup"><span data-stu-id="76c6f-105">WSFC Cluster State</span></span>|  
|<span data-ttu-id="76c6f-106">**Problema**</span><span class="sxs-lookup"><span data-stu-id="76c6f-106">**Issue**</span></span>|<span data-ttu-id="76c6f-107">Il servizio cluster WSFC è offline.</span><span class="sxs-lookup"><span data-stu-id="76c6f-107">WSFC cluster service is offline.</span></span>|  
|<span data-ttu-id="76c6f-108">**Categoria**</span><span class="sxs-lookup"><span data-stu-id="76c6f-108">**Category**</span></span>|<span data-ttu-id="76c6f-109">**Critico**</span><span class="sxs-lookup"><span data-stu-id="76c6f-109">**Critical**</span></span>|  
|<span data-ttu-id="76c6f-110">**Facet**</span><span class="sxs-lookup"><span data-stu-id="76c6f-110">**Facet**</span></span>|<span data-ttu-id="76c6f-111">Istanza di SQL Server</span><span class="sxs-lookup"><span data-stu-id="76c6f-111">Instance of SQL Server</span></span>|  
  
## <a name="description"></a><span data-ttu-id="76c6f-112">Descrizione</span><span class="sxs-lookup"><span data-stu-id="76c6f-112">Description</span></span>  
 <span data-ttu-id="76c6f-113">Questi criteri consentono di controllare lo stato di WSCF (Windows Server Failover Clustering).</span><span class="sxs-lookup"><span data-stu-id="76c6f-113">This policy checks the state of the Windows Server Failover Cluster (WSFC).</span></span> <span data-ttu-id="76c6f-114">I criteri sono in uno stato non integro e viene generato un avviso quando il cluster WSFC è offline o nello stato di quorum forzato.</span><span class="sxs-lookup"><span data-stu-id="76c6f-114">The policy is in an unhealthy state and an alert is raised when the WSFC cluster is offline or in the forced quorum state.</span></span> <span data-ttu-id="76c6f-115">Tutti i gruppi di disponibilità ospitati all'interno di questo cluster sono offline oppure è necessaria un'azione di ripristino di emergenza.</span><span class="sxs-lookup"><span data-stu-id="76c6f-115">All availability groups hosted within this cluster are offline or a disaster recovery action is required.</span></span>  
  
 <span data-ttu-id="76c6f-116">Lo stato dei criteri è integro quando quello del cluster è nel quorum normale.</span><span class="sxs-lookup"><span data-stu-id="76c6f-116">The policy state is healthy when the cluster state is in the normal quorum.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="76c6f-117">Per questa versione di [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)], le informazioni sulle possibili cause e le soluzioni sono disponibili nella pagina relativa alla situazione in cui il [servizio cluster WSFC è offline](https://go.microsoft.com/fwlink/p/?LinkId=220849) su Wiki di TechNet.</span><span class="sxs-lookup"><span data-stu-id="76c6f-117">For this release of [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)], information about possible causes and solutions is located at [WSFC cluster service is offline](https://go.microsoft.com/fwlink/p/?LinkId=220849) on the TechNet Wiki.</span></span>  
  
## <a name="possible-causes"></a><span data-ttu-id="76c6f-118">Possibili cause</span><span class="sxs-lookup"><span data-stu-id="76c6f-118">Possible Causes</span></span>  
 <span data-ttu-id="76c6f-119">Questo problema può essere causato da un problema del servizio cluster o dalla perdita del quorum nel cluster.</span><span class="sxs-lookup"><span data-stu-id="76c6f-119">This issue can be caused by a cluster service issue or by the loss of the quorum in the cluster.</span></span>  
  
## <a name="possible-solution"></a><span data-ttu-id="76c6f-120">Possibile soluzione</span><span class="sxs-lookup"><span data-stu-id="76c6f-120">Possible Solution</span></span>  
 <span data-ttu-id="76c6f-121">Utilizzare lo strumento Amministratore cluster per eseguire il quorum forzato o il flusso di lavoro del ripristino di emergenza.</span><span class="sxs-lookup"><span data-stu-id="76c6f-121">Use the Cluster Administrator tool to perform the forced quorum or disaster recovery workflow.</span></span> <span data-ttu-id="76c6f-122">Se non è possibile risolvere il problema eseguendo il quorum forzato o il ripristino di emergenza, contattare l'amministratore del cluster.</span><span class="sxs-lookup"><span data-stu-id="76c6f-122">If you cannot resolve the issue by performing the forced quorum or disaster recovery, contact your cluster administrator to help resolve this issue.</span></span> <span data-ttu-id="76c6f-123">Per altre informazioni, vedere [Forzare l'avvio di un cluster WSFC senza un quorum](../../../sql-server/failover-clusters/windows/force-a-wsfc-cluster-to-start-without-a-quorum.md) nella documentazione online di [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="76c6f-123">For more information, see [Force a WSFC Cluster to Start Without a Quorum](../../../sql-server/failover-clusters/windows/force-a-wsfc-cluster-to-start-without-a-quorum.md) in [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Books Online.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="76c6f-124">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="76c6f-124">See Also</span></span>  
 <span data-ttu-id="76c6f-125">[Panoramica di Gruppi di disponibilità AlwaysOn &#40;SQL Server&#41;](overview-of-always-on-availability-groups-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="76c6f-125">[Overview of AlwaysOn Availability Groups &#40;SQL Server&#41;](overview-of-always-on-availability-groups-sql-server.md) </span></span>  
 [<span data-ttu-id="76c6f-126">Usare il Dashboard Always On &#40;SQL Server Management Studio&#41;</span><span class="sxs-lookup"><span data-stu-id="76c6f-126">Use the AlwaysOn Dashboard &#40;SQL Server Management Studio&#41;</span></span>](use-the-always-on-dashboard-sql-server-management-studio.md)  
  
  
