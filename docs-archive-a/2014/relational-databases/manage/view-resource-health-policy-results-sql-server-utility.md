---
title: Visualizzare i risultati dei criteri di integrità delle risorse (Utilità SQL Server) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
ms.assetid: 80cb14fb-f4c6-4be2-ba17-eb4e4cddd35f
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: c4ab30ad0e87782f8187370a53747be4cf5d313d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87716291"
---
# <a name="view-resource-health-policy-results-sql-server-utility"></a><span data-ttu-id="d2942-102">Visualizzazione dei risultati dei criteri di integrità delle risorse (Utilità SQL Server)</span><span class="sxs-lookup"><span data-stu-id="d2942-102">View Resource Health Policy Results (SQL Server Utility)</span></span>
  <span data-ttu-id="d2942-103">Usare il dashboard Utilità in [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)] per visualizzare i parametri delle risorse di Utilità [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] per le istanze gestite di [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] e le applicazioni livello dati.</span><span class="sxs-lookup"><span data-stu-id="d2942-103">Use the Utility dashboard in [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)] to view [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Utility resource parameters for managed instances of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] and data-tier applications.</span></span> <span data-ttu-id="d2942-104">Per altre informazioni, vedere [Attività e funzionalità di Utilità SQL Server](sql-server-utility-features-and-tasks.md).</span><span class="sxs-lookup"><span data-stu-id="d2942-104">For more information, see [SQL Server Utility Features and Tasks](sql-server-utility-features-and-tasks.md).</span></span>  
  
##  <a name="SSMSProcedure"></a>  
  
#### <a name="view-sql-server-utility-resource-health-policy-results"></a><span data-ttu-id="d2942-105">Visualizzare i risultati dei criteri di integrità delle risorse di Utilità SQL Server.</span><span class="sxs-lookup"><span data-stu-id="d2942-105">View SQL Server Utility resource health policy results.</span></span>  
  
1.  <span data-ttu-id="d2942-106">In [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)] (SSMS) fare clic su **Visualizza**, quindi su **Esplora utilità** per visualizzare il riquadro di spostamento di Esplora utilità.</span><span class="sxs-lookup"><span data-stu-id="d2942-106">In [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)] (SSMS), click **View**, then click **Utility Explorer** to view the Utility Explorer navigation pane.</span></span> <span data-ttu-id="d2942-107">Per visualizzare il riquadro del contenuto, fare clic su **Visualizza**, quindi su **Contenuto Esplora utilità**.</span><span class="sxs-lookup"><span data-stu-id="d2942-107">To view the content pane, click **View**, then click **Utility Explorer Content**.</span></span>  
  
2.  <span data-ttu-id="d2942-108">Nel riquadro di spostamento fare clic su ![](../../database-engine/media/connect-to-utility.gif "Connetti a utilità")**Connetti a utilità**.</span><span class="sxs-lookup"><span data-stu-id="d2942-108">In the navigation pane, click ![](../../database-engine/media/connect-to-utility.gif "Connect_to_Utility")**Connect to Utility**.</span></span> <span data-ttu-id="d2942-109">Se non è stato creato un punto di controllo dell'utilità o se non sono state registrate istanze di [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] o applicazioni livello dati in Utilità [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] , vedere [Attività e funzionalità di Utilità SQL Server](sql-server-utility-features-and-tasks.md).</span><span class="sxs-lookup"><span data-stu-id="d2942-109">If you have not created a utility control point (UCP) or if you have not enrolled instances of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] or data-tier applications into the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Utility, see [SQL Server Utility Features and Tasks](sql-server-utility-features-and-tasks.md).</span></span>  
  
3.  <span data-ttu-id="d2942-110">Fare clic sul nodo del punto di controllo dell'utilità per visualizzare dati riepilogativi per le istanze gestite di [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] e le applicazioni livello dati (fare clic con il pulsante destro del mouse per aggiornare i dati).</span><span class="sxs-lookup"><span data-stu-id="d2942-110">Click the UCP node to view summary data for managed instances of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] and data-tier applications (right-click to refresh).</span></span> <span data-ttu-id="d2942-111">I dati del dashboard vengono visualizzati nel riquadro del contenuto.</span><span class="sxs-lookup"><span data-stu-id="d2942-111">Dashboard data is displayed in the content pane.</span></span>  
  
4.  <span data-ttu-id="d2942-112">Fare clic sul nodo **Istanze gestite** per visualizzare i dati della visualizzazione elenco per le istanze gestite di [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] (fare clic con il pulsante destro del mouse per aggiornare i dati).</span><span class="sxs-lookup"><span data-stu-id="d2942-112">Click the **Managed Instances** node to view list view data for managed instances of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] (right-click to refresh).</span></span> <span data-ttu-id="d2942-113">I dati della visualizzazione elenco vengono visualizzati nel riquadro del contenuto.</span><span class="sxs-lookup"><span data-stu-id="d2942-113">List view data is displayed in the content pane.</span></span>  
  
5.  <span data-ttu-id="d2942-114">Fare clic sul nodo **Deployed Data-tier Applications** (Applicazioni livello dati distribuite) per visualizzare i dati della visualizzazione elenco per le applicazioni del livello dati (fare clic con il pulsante destro del mouse per aggiornare i dati).</span><span class="sxs-lookup"><span data-stu-id="d2942-114">Click the **Deployed Data-tier Applications** node to view list view data for data-tier applications (right-click to refresh).</span></span> <span data-ttu-id="d2942-115">I dati della visualizzazione elenco vengono visualizzati nel riquadro del contenuto.</span><span class="sxs-lookup"><span data-stu-id="d2942-115">List view data is displayed in the content pane.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d2942-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d2942-116">See Also</span></span>  
 <span data-ttu-id="d2942-117">[Attività e funzionalità di Utilità SQL Server](sql-server-utility-features-and-tasks.md) </span><span class="sxs-lookup"><span data-stu-id="d2942-117">[SQL Server Utility Features and Tasks](sql-server-utility-features-and-tasks.md) </span></span>  
 <span data-ttu-id="d2942-118">[Ridurre le segnalazioni non significative nei criteri di utilizzo della CPU &#40;Utilità SQL Server&#41;](reduce-noise-in-cpu-utilization-policies-sql-server-utility.md) </span><span class="sxs-lookup"><span data-stu-id="d2942-118">[Reduce Noise in CPU Utilization Policies &#40;SQL Server Utility&#41;](reduce-noise-in-cpu-utilization-policies-sql-server-utility.md) </span></span>  
 <span data-ttu-id="d2942-119">[Dettagli di applicazioni livello dati distribuite &#40;Utilità SQL Server&#41;](../../database-engine/deployed-data-tier-application-details-sql-server-utility.md) </span><span class="sxs-lookup"><span data-stu-id="d2942-119">[Deployed Data-tier Application Details &#40;SQL Server Utility&#41;](../../database-engine/deployed-data-tier-application-details-sql-server-utility.md) </span></span>  
 <span data-ttu-id="d2942-120">[Dettagli di istanze gestite &#40;Utilità SQL Server&#41;](../../database-engine/managed-instance-details-sql-server-utility.md) </span><span class="sxs-lookup"><span data-stu-id="d2942-120">[Managed Instance Details &#40;SQL Server Utility&#41;](../../database-engine/managed-instance-details-sql-server-utility.md) </span></span>  
 [<span data-ttu-id="d2942-121">Amministrazione utilità &#40;Utilità SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="d2942-121">Utility Administration &#40;SQL Server Utility&#41;</span></span>](../../database-engine/utility-administration-sql-server-utility.md)  
  
  
