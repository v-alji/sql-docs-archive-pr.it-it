---
title: Configurare i criteri di integrità (Utilità SQL Server) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
ms.assetid: 030aac3b-8901-4c41-91ed-aba96420276c
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: c5ee466dd2d5bac2ea64364bfc78de8f2f5bea10
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87625398"
---
# <a name="configure-health-policies-sql-server-utility"></a><span data-ttu-id="d29c8-102">Configurazione dei criteri di integrità (Utilità SQL Server)</span><span class="sxs-lookup"><span data-stu-id="d29c8-102">Configure Health Policies (SQL Server Utility)</span></span>
  <span data-ttu-id="d29c8-103">Usare il dashboard di Utilità [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] per visualizzare i parametri delle risorse di Utilità [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] per le istanze gestite di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] e le applicazioni livello dati.</span><span class="sxs-lookup"><span data-stu-id="d29c8-103">Use the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Utility dashboard in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] to view [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Utility resource parameters for managed instances of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] and data-tier applications.</span></span> <span data-ttu-id="d29c8-104">Per altre informazioni, vedere [Attività e funzionalità di Utilità SQL Server](sql-server-utility-features-and-tasks.md).</span><span class="sxs-lookup"><span data-stu-id="d29c8-104">For more information, see [SQL Server Utility Features and Tasks](sql-server-utility-features-and-tasks.md).</span></span>  
  
 <span data-ttu-id="d29c8-105">Per visualizzare i risultati dei criteri di integrità di Utilità [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , connettersi a un punto di controllo dell'utilità da [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)].</span><span class="sxs-lookup"><span data-stu-id="d29c8-105">To view [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Utility health policy results, connect to a utility control point from [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)].</span></span> <span data-ttu-id="d29c8-106">Per altre informazioni, vedere [Utilizzo di Esplora utilità per gestire Utilità SQL Server](use-utility-explorer-to-manage-the-sql-server-utility.md).</span><span class="sxs-lookup"><span data-stu-id="d29c8-106">For more information, see [Use Utility Explorer to Manage the SQL Server Utility](use-utility-explorer-to-manage-the-sql-server-utility.md).</span></span>  
  
 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="d29c8-107">È possibile configurare i criteri di integrità di Utilità per applicazioni livello dati e istanze gestite di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="d29c8-107">Utility health policies can be configured for data-tier applications and managed instances of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="d29c8-108">I criteri di integrità possono essere definiti a livello globale per tutte le applicazioni livello dati e per tutte le istanze gestite di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] in Utilità [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] oppure possono essere definiti singolarmente per ogni applicazione livello dati e per ogni istanza gestita di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] in Utilità [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="d29c8-108">Health policies can be defined globally for all data-tier applications and managed instances of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] in the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Utility, or they can be defined individually for each data-tier application and for each managed instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] in the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Utility.</span></span>  
  
## <a name="monitoring-policies-for-data-tier-applications"></a><span data-ttu-id="d29c8-109">Criteri di monitoraggio per le applicazioni del livello dati</span><span class="sxs-lookup"><span data-stu-id="d29c8-109">Monitoring Policies for Data-tier Applications</span></span>  
 <span data-ttu-id="d29c8-110">Di seguito vengono indicati i criteri di sovrautilizzo e sottoutilizzo per le applicazioni livello dati di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] :</span><span class="sxs-lookup"><span data-stu-id="d29c8-110">Overutilization and underutilization policies for [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] data-tier applications are as follows:</span></span>  
  
-   <span data-ttu-id="d29c8-111">Utilizzo del processore da parte dell'applicazione del livello dati.</span><span class="sxs-lookup"><span data-stu-id="d29c8-111">Data-tier application processor utilization.</span></span>  
  
-   <span data-ttu-id="d29c8-112">Spazio occupato dall'applicazione del livello dati per i file di database.</span><span class="sxs-lookup"><span data-stu-id="d29c8-112">Data-tier application file space for database files.</span></span>  
  
-   <span data-ttu-id="d29c8-113">Spazio occupato dall'applicazione del livello dati per i volumi di archiviazione.</span><span class="sxs-lookup"><span data-stu-id="d29c8-113">Data-tier application file space for storage volumes.</span></span>  
  
-   <span data-ttu-id="d29c8-114">Utilizzo del processore del computer.</span><span class="sxs-lookup"><span data-stu-id="d29c8-114">Computer processor utilization.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="d29c8-115">Utilizzo del volume di archiviazione e del processore sono criteri di sola lettura per le applicazioni livello dati.</span><span class="sxs-lookup"><span data-stu-id="d29c8-115">Storage volume and processor utilization are read-only policies for data-tier applications.</span></span>  
  
 <span data-ttu-id="d29c8-116">Per altre informazioni sulla visualizzazione o sulla modifica di criteri di monitoraggio globali per le applicazioni livello dati, vedere [Amministrazione utilità &#40;Utilità SQL Server&#41;](../../database-engine/utility-administration-sql-server-utility.md).</span><span class="sxs-lookup"><span data-stu-id="d29c8-116">For more information about viewing or changing global monitoring policies for data-tier applications, see [Utility Administration &#40;SQL Server Utility&#41;](../../database-engine/utility-administration-sql-server-utility.md).</span></span>  
  
 <span data-ttu-id="d29c8-117">Per altre informazioni sulla visualizzazione o sulla modifica di criteri di monitoraggio per singole applicazioni livello dati, vedere [Dettagli di Applicazioni di livello dati distribuite &#40;Utilità SQL Server&#41;](../../database-engine/deployed-data-tier-application-details-sql-server-utility.md).</span><span class="sxs-lookup"><span data-stu-id="d29c8-117">For more information about viewing or changing monitoring policies for individual data-tier applications, see [Deployed Data-tier Application Details &#40;SQL Server Utility&#41;](../../database-engine/deployed-data-tier-application-details-sql-server-utility.md).</span></span>  
  
## <a name="monitoring-policies-for-managed-instances-of-sql-server"></a><span data-ttu-id="d29c8-118">Criteri di monitoraggio per le istanze gestite di SQL Server</span><span class="sxs-lookup"><span data-stu-id="d29c8-118">Monitoring Policies for Managed Instances of SQL Server</span></span>  
 <span data-ttu-id="d29c8-119">I criteri di sovrautilizzo e sottoutilizzo per le istanze gestite di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] sono i seguenti:</span><span class="sxs-lookup"><span data-stu-id="d29c8-119">Overutilization and underutilization policies for managed instances of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] are as follows:</span></span>  
  
-   [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="d29c8-120">.</span><span class="sxs-lookup"><span data-stu-id="d29c8-120">instance processor utilization.</span></span>  
  
-   [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="d29c8-121">per i file di database.</span><span class="sxs-lookup"><span data-stu-id="d29c8-121">instance file space for database files.</span></span>  
  
-   [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="d29c8-122">per i volumi di archiviazione.</span><span class="sxs-lookup"><span data-stu-id="d29c8-122">instance file space for storage volumes.</span></span>  
  
-   <span data-ttu-id="d29c8-123">Utilizzo del processore del computer.</span><span class="sxs-lookup"><span data-stu-id="d29c8-123">Computer processor utilization.</span></span>  
  
 <span data-ttu-id="d29c8-124">Per altre informazioni sulla visualizzazione o sulla modifica di criteri di monitoraggio globali per le istanze globali di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], vedere [Amministrazione utilità &#40;Utilità SQL Server&#41;](../../database-engine/utility-administration-sql-server-utility.md).</span><span class="sxs-lookup"><span data-stu-id="d29c8-124">For more information about viewing or changing global monitoring policies for managed instances of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], see [Utility Administration &#40;SQL Server Utility&#41;](../../database-engine/utility-administration-sql-server-utility.md).</span></span>  
  
 <span data-ttu-id="d29c8-125">Per altre informazioni sulla visualizzazione o sulla modifica di criteri di monitoraggio per singole istanze globali di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], vedere [Dettagli di istanze gestite &#40;Utilità SQL Server&#41;](../../database-engine/managed-instance-details-sql-server-utility.md).</span><span class="sxs-lookup"><span data-stu-id="d29c8-125">For more information about viewing or changing monitoring policies for individual managed instances of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], see [Managed Instance Details &#40;SQL Server Utility&#41;](../../database-engine/managed-instance-details-sql-server-utility.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d29c8-126">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d29c8-126">See Also</span></span>  
 <span data-ttu-id="d29c8-127">[Attività e funzionalità di Utilità SQL Server](sql-server-utility-features-and-tasks.md) </span><span class="sxs-lookup"><span data-stu-id="d29c8-127">[SQL Server Utility Features and Tasks](sql-server-utility-features-and-tasks.md) </span></span>  
 [<span data-ttu-id="d29c8-128">Riduzione delle segnalazioni non significative nei criteri di utilizzo della CPU &#40;Utilità SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="d29c8-128">Reduce Noise in CPU Utilization Policies &#40;SQL Server Utility&#41;</span></span>](reduce-noise-in-cpu-utilization-policies-sql-server-utility.md)  
  
  
