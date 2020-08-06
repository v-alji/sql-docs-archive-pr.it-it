---
title: Aggiornare un cluster di failover di SQL Server | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: high-availability
ms.topic: conceptual
helpviewer_keywords:
- upgrading failover clusters
- clusters [SQL Server], upgrading
- failover clustering [SQL Server], upgrading
ms.assetid: daac41fe-7d0b-4f14-84c2-62952ad8cbfa
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: ca08e83c362e714f234a60ee358df3bcb03ade93
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87628264"
---
# <a name="upgrade-a-sql-server-failover-cluster"></a><span data-ttu-id="7685d-102">Aggiornare un cluster di failover di SQL Server</span><span class="sxs-lookup"><span data-stu-id="7685d-102">Upgrade a SQL Server Failover Cluster</span></span>
  [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] <span data-ttu-id="7685d-103">supporta l'aggiornamento separato del [!INCLUDE[ssDE](../../../includes/ssde-md.md)] e di [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)] dai cluster di failover di [!INCLUDE[ssVersion2005](../../../includes/ssversion2005-md.md)], [!INCLUDE[ssKatmai](../../../includes/sskatmai-md.md)], [!INCLUDE[ssKilimanjaro](../../../includes/sskilimanjaro-md.md)] e [!INCLUDE[ssSQL11](../../../includes/sssql11-md.md)] in tutti i nodi del cluster di failover.</span><span class="sxs-lookup"><span data-stu-id="7685d-103">supports upgrade of the [!INCLUDE[ssDE](../../../includes/ssde-md.md)] and [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)] from [!INCLUDE[ssVersion2005](../../../includes/ssversion2005-md.md)], [!INCLUDE[ssKatmai](../../../includes/sskatmai-md.md)], [!INCLUDE[ssKilimanjaro](../../../includes/sskilimanjaro-md.md)], and [!INCLUDE[ssSQL11](../../../includes/sssql11-md.md)] failover clusters separately on all failover cluster nodes.</span></span>  
  
 <span data-ttu-id="7685d-104">I dettagli relativi al supporto sono i seguenti:</span><span class="sxs-lookup"><span data-stu-id="7685d-104">Support details are as follows:</span></span>  
  
-   <span data-ttu-id="7685d-105">L'aggiornamento è supportato sia tramite l'interfaccia utente sia dal prompt dei comandi.</span><span class="sxs-lookup"><span data-stu-id="7685d-105">Upgrade is supported both through the user interface and from the command prompt.</span></span> <span data-ttu-id="7685d-106">Per altre informazioni, vedere [Eseguire l'aggiornamento di un'istanza del cluster di failover di SQL Server &#40;installazione&#41;](upgrade-a-sql-server-failover-cluster-instance-setup.md) e [Installare SQL Server 2014 dal prompt dei comandi](../../../database-engine/install-windows/install-sql-server-from-the-command-prompt.md).</span><span class="sxs-lookup"><span data-stu-id="7685d-106">For more information, see [Upgrade a SQL Server Failover Cluster Instance &#40;Setup&#41;](upgrade-a-sql-server-failover-cluster-instance-setup.md) and [Install SQL Server 2014 from the Command Prompt](../../../database-engine/install-windows/install-sql-server-from-the-command-prompt.md).</span></span>  
  
-   <span data-ttu-id="7685d-107">Aggiornamento da [!INCLUDE[ssKilimanjaro](../../../includes/sskilimanjaro-md.md)] : è possibile eseguire l'aggiornamento dal prompt dei comandi in ogni nodo del cluster di failover o tramite l'interfaccia utente del programma di installazione per aggiornare ogni nodo del cluster.</span><span class="sxs-lookup"><span data-stu-id="7685d-107">Upgrading from [!INCLUDE[ssKilimanjaro](../../../includes/sskilimanjaro-md.md)] - You can run upgrade from the command prompt on each failover cluster node, or by using the Setup UI to upgrade each cluster node.</span></span> <span data-ttu-id="7685d-108">Se nell'istanza che si intende aggiornare non sono presenti le caratteristiche di replica e di ricerca full-text, queste verranno installate automaticamente senza che sia possibile ometterle.</span><span class="sxs-lookup"><span data-stu-id="7685d-108">If Full-text search and Replication features do not exist on the instance being upgraded, they will be installed automatically with no option to omit them.</span></span>  
  
-   <span data-ttu-id="7685d-109">Installazione del Service Pack: è necessario applicare separatamente i patch e i service pack di [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] ai cluster di failover di [!INCLUDE[ssSQL11](../../../includes/sssql11-md.md)] in tutti i nodi.</span><span class="sxs-lookup"><span data-stu-id="7685d-109">Service pack installation - you must apply [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] service packs and patches to [!INCLUDE[ssSQL11](../../../includes/sssql11-md.md)] failover clusters separately on all nodes.</span></span>  
  
-   <span data-ttu-id="7685d-110">Non sono supportati gli scenari seguenti:</span><span class="sxs-lookup"><span data-stu-id="7685d-110">The following scenarios are not supported:</span></span>  
  
    -   <span data-ttu-id="7685d-111">Non è possibile eseguire la migrazione da un'istanza autonoma di [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] a un cluster di failover.</span><span class="sxs-lookup"><span data-stu-id="7685d-111">You cannot migrate from a stand-alone instance of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] to a failover cluster.</span></span>  
  
    -   <span data-ttu-id="7685d-112">Aggiungere funzionalità a un cluster di failover.</span><span class="sxs-lookup"><span data-stu-id="7685d-112">Add features to a failover cluster.</span></span> <span data-ttu-id="7685d-113">Non è possibile ad esempio aggiungere il [!INCLUDE[ssDE](../../../includes/ssde-md.md)] a un cluster di failover solo di [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)]esistente.</span><span class="sxs-lookup"><span data-stu-id="7685d-113">For example, you cannot add the [!INCLUDE[ssDE](../../../includes/ssde-md.md)] to an existing [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)]-only failover cluster.</span></span>  
  
    -   <span data-ttu-id="7685d-114">Non è possibile effettuare il downgrade di un nodo del cluster di failover a un'istanza autonoma.</span><span class="sxs-lookup"><span data-stu-id="7685d-114">You cannot downgrade a failover cluster node to a stand-alone instance.</span></span>  
  
-   <span data-ttu-id="7685d-115">Per altre informazioni, vedere [Istanze del cluster di failover Always On (SQL Server)](always-on-failover-cluster-instances-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="7685d-115">For more information, see [AlwaysOn Failover Cluster Instances (SQL Server)](always-on-failover-cluster-instances-sql-server.md).</span></span>  
  
## <a name="upgrading-a-ssnoversion-multi-subnet-failover-cluster"></a><span data-ttu-id="7685d-116">Aggiornamento di un cluster di failover su più subnet di [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7685d-116">Upgrading a [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Multi-Subnet Failover Cluster</span></span>  
 <span data-ttu-id="7685d-117">Non è possibile aggiornare direttamente un [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] cluster di failover non su più subnet di a un cluster di failover su più [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] subnet di.</span><span class="sxs-lookup"><span data-stu-id="7685d-117">You cannot directly upgrade a non-multi-subnet [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] failover cluster to a [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] multi-subnet failover cluster.</span></span> <span data-ttu-id="7685d-118">Per altre informazioni, vedere [Eseguire l'aggiornamento di un'istanza del cluster di failover di SQL Server &#40;installazione&#41;](upgrade-a-sql-server-failover-cluster-instance-setup.md).</span><span class="sxs-lookup"><span data-stu-id="7685d-118">For more information, see [Upgrade a SQL Server Failover Cluster Instance &#40;Setup&#41;](upgrade-a-sql-server-failover-cluster-instance-setup.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7685d-119">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="7685d-119">See Also</span></span>  
 <span data-ttu-id="7685d-120">[Aggiornamenti di versione ed edizione supportati](../../../database-engine/install-windows/supported-version-and-edition-upgrades.md) </span><span class="sxs-lookup"><span data-stu-id="7685d-120">[Supported Version and Edition Upgrades](../../../database-engine/install-windows/supported-version-and-edition-upgrades.md) </span></span>  
 <span data-ttu-id="7685d-121">[Aggiornare un'istanza del cluster di failover di SQL Server &#40;l'installazione&#41;](upgrade-a-sql-server-failover-cluster-instance-setup.md) </span><span class="sxs-lookup"><span data-stu-id="7685d-121">[Upgrade a SQL Server Failover Cluster Instance &#40;Setup&#41;](upgrade-a-sql-server-failover-cluster-instance-setup.md) </span></span>  
 [<span data-ttu-id="7685d-122">Installazione di SQL Server 2014 dal prompt dei comandi</span><span class="sxs-lookup"><span data-stu-id="7685d-122">Install SQL Server 2014 from the Command Prompt</span></span>](../../../database-engine/install-windows/install-sql-server-from-the-command-prompt.md)  
  
  
