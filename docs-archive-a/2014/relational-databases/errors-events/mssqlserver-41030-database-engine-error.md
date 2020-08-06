---
title: MSSQLSERVER_41030 | Microsoft Docs
ms.custom: ''
ms.date: 03/08/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 41030 (Database Engine error)
ms.assetid: c85341ae-0fbf-42ae-9275-4cfe678238f0
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: b137b739d4c1641b88983708df62d2e52fd0eab5
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87721476"
---
# <a name="mssqlserver_41030"></a><span data-ttu-id="009b9-102">MSSQLSERVER_41030</span><span class="sxs-lookup"><span data-stu-id="009b9-102">MSSQLSERVER_41030</span></span>
    
## <a name="details"></a><span data-ttu-id="009b9-103">Dettagli</span><span class="sxs-lookup"><span data-stu-id="009b9-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="009b9-104">Nome prodotto</span><span class="sxs-lookup"><span data-stu-id="009b9-104">Product Name</span></span>|[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]|  
|<span data-ttu-id="009b9-105">ID evento</span><span class="sxs-lookup"><span data-stu-id="009b9-105">Event ID</span></span>|<span data-ttu-id="009b9-106">41030</span><span class="sxs-lookup"><span data-stu-id="009b9-106">41030</span></span>|  
|<span data-ttu-id="009b9-107">Origine evento</span><span class="sxs-lookup"><span data-stu-id="009b9-107">Event Source</span></span>|<span data-ttu-id="009b9-108">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="009b9-108">MSSQLSERVER</span></span>|  
|<span data-ttu-id="009b9-109">Componente</span><span class="sxs-lookup"><span data-stu-id="009b9-109">Component</span></span>|<span data-ttu-id="009b9-110">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="009b9-110">SQLEngine</span></span>|  
|<span data-ttu-id="009b9-111">Nome simbolico</span><span class="sxs-lookup"><span data-stu-id="009b9-111">Symbolic Name</span></span>|<span data-ttu-id="009b9-112">OPEN_CLUSTER_SUB_KEY</span><span class="sxs-lookup"><span data-stu-id="009b9-112">OPEN_CLUSTER_SUB_KEY</span></span>|  
|<span data-ttu-id="009b9-113">Testo del messaggio</span><span class="sxs-lookup"><span data-stu-id="009b9-113">Message Text</span></span>|<span data-ttu-id="009b9-114">Impossibile aprire la sottochiave del Registro di sistema WSFC (Windows Server Failover Clustering) '%.\*ls', codice di errore %d.</span><span class="sxs-lookup"><span data-stu-id="009b9-114">Failed to open the Windows Server Failover Clustering registry subkey '%.\*ls' (Error code %d).</span></span>  <span data-ttu-id="009b9-115">La chiave padre è la chiave radice cluster.</span><span class="sxs-lookup"><span data-stu-id="009b9-115">The parent key is the cluster root key.</span></span>  <span data-ttu-id="009b9-116">È possibile che il servizio WSFC non sia in esecuzione o non sia accessibile nello stato corrente o che gli argomenti specificati non siano validi.</span><span class="sxs-lookup"><span data-stu-id="009b9-116">The WSFC service may not be running or may not be accessible in its current state, or the specified arguments are invalid.</span></span> <span data-ttu-id="009b9-117">Se il gruppo di disponibilità corrispondente è stato eliminato, l'errore è previsto.</span><span class="sxs-lookup"><span data-stu-id="009b9-117">If the corresponding availability group has been dropped, this error is expected.</span></span> <span data-ttu-id="009b9-118">Per informazioni su questo codice di errore, vedere la sezione relativa ai codici di errore di sistema nella documentazione sullo sviluppo per Windows.</span><span class="sxs-lookup"><span data-stu-id="009b9-118">For information about this error code, see "System Error Codes" in the Windows Development documentation.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="009b9-119">Spiegazione</span><span class="sxs-lookup"><span data-stu-id="009b9-119">Explanation</span></span>  
 <span data-ttu-id="009b9-120">Se un cluster WSFC viene eliminato, vengono rimosse tutte le chiavi del Registro di sistema correlate a [!INCLUDE[ssHADR](../../includes/sshadr-md.md)].</span><span class="sxs-lookup"><span data-stu-id="009b9-120">If a WSFC cluster is destroyed, it removes all registry keys related to [!INCLUDE[ssHADR](../../includes/sshadr-md.md)].</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="009b9-121">Azione dell'utente</span><span class="sxs-lookup"><span data-stu-id="009b9-121">User Action</span></span>  
 <span data-ttu-id="009b9-122">Dopo aver creato di nuovo il cluster WSFC, disabilitare e quindi riabilitare AlwaysOn in ogni nodo del cluster in cui un'istanza di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] è abilitata per AlwaysOn.</span><span class="sxs-lookup"><span data-stu-id="009b9-122">After re-creating a WSFC cluster, disable and then re-enable AlwaysOn on every cluster node on which an instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] is enabled for AlwaysOn.</span></span> <span data-ttu-id="009b9-123">Per questa attività è possibile utilizzare Gestione configurazione [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="009b9-123">You can use the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Configuration Manager for this task.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="009b9-124">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="009b9-124">See Also</span></span>  
 <span data-ttu-id="009b9-125">[Abilitare e disabilitare Gruppi di disponibilità AlwaysOn &#40;SQL Server&#41;](../../database-engine/availability-groups/windows/enable-and-disable-always-on-availability-groups-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="009b9-125">[Enable and Disable AlwaysOn Availability Groups &#40;SQL Server&#41;](../../database-engine/availability-groups/windows/enable-and-disable-always-on-availability-groups-sql-server.md) </span></span>  
 [<span data-ttu-id="009b9-126">Windows Server Failover Clustering &#40;WSFC&#41; con SQL Server</span><span class="sxs-lookup"><span data-stu-id="009b9-126">Windows Server Failover Clustering &#40;WSFC&#41; with SQL Server</span></span>](../../sql-server/failover-clusters/windows/windows-server-failover-clustering-wsfc-with-sql-server.md)  
  
  
