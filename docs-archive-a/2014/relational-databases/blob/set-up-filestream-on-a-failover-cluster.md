---
title: Configurare FILESTREAM in un cluster di failover | Microsoft Docs
ms.custom: ''
ms.date: 06/14/2017
ms.prod: sql-server-2014
ms.technology: filestream
ms.reviewer: ''
ms.topic: conceptual
helpviewer_keywords:
- FILESTREAM [SQL Server], setting up on a failover cluster
ms.assetid: 6721f780-20b7-4109-8ddb-ac327310699e
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 29541bbcfd323a85a3fa751f60904fd1a26e1199
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87712043"
---
# <a name="set-up-filestream-on-a-failover-cluster"></a><span data-ttu-id="d8b23-102">Configurazione di FILESTREAM in un cluster di failover</span><span class="sxs-lookup"><span data-stu-id="d8b23-102">Set Up FILESTREAM on a Failover Cluster</span></span>
  <span data-ttu-id="d8b23-103">In questo argomento viene descritto come abilitare FILESTREAM in un cluster di failover.</span><span class="sxs-lookup"><span data-stu-id="d8b23-103">This topic describes how to enable FILESTREAM on a failover cluster.</span></span> <span data-ttu-id="d8b23-104">Prima di eseguire questa procedura, è consigliabile acquisire familiarità con il [clustering di failover](../../sql-server/failover-clusters/windows/always-on-failover-cluster-instances-sql-server.md) e abilitare FILESTREAM.</span><span class="sxs-lookup"><span data-stu-id="d8b23-104">Before you try this procedure, you should understand [failover clustering](../../sql-server/failover-clusters/windows/always-on-failover-cluster-instances-sql-server.md) and have FILESTREAM enabled.</span></span> <span data-ttu-id="d8b23-105">Per informazioni su come abilitare FILESTREAM, vedere [Abilitare e configurare FILESTREAM](enable-and-configure-filestream.md).</span><span class="sxs-lookup"><span data-stu-id="d8b23-105">For information about how to enable FILESTREAM, see [Enable and Configure FILESTREAM](enable-and-configure-filestream.md).</span></span>  
  
### <a name="to-set-up-filestream-on-a-failover-cluster"></a><span data-ttu-id="d8b23-106">Per configurare FILESTREAM in un cluster di failover</span><span class="sxs-lookup"><span data-stu-id="d8b23-106">To set up FILESTREAM on a failover cluster</span></span>  
  
1.  <span data-ttu-id="d8b23-107">Configurare il nodo primario per il cluster di failover.</span><span class="sxs-lookup"><span data-stu-id="d8b23-107">Set up the primary node for the failover cluster.</span></span>  
  
     <span data-ttu-id="d8b23-108">Al termine della configurazione, abilitare FILESTREAM nel nodo primario usando **Gestione configurazione SQL Server**.</span><span class="sxs-lookup"><span data-stu-id="d8b23-108">After the setup finishes, enable FILESTREAM on the primary node by using **SQL Server Configuration Manager**.</span></span> <span data-ttu-id="d8b23-109">Verranno abilitate le impostazioni per cui è necessario disporre dei privilegi di amministratore di Windows.</span><span class="sxs-lookup"><span data-stu-id="d8b23-109">This enables the settings that require Windows Admin privileges.</span></span> <span data-ttu-id="d8b23-110">Se è necessario usare l'accesso remoto, selezionare **Consenti ai client remoti l'accesso tramite flusso ai dati FILESTREAM**.</span><span class="sxs-lookup"><span data-stu-id="d8b23-110">If remote access is required, select **Allow remote clients to have streaming access to FILESTREAM data**.</span></span> <span data-ttu-id="d8b23-111">Verrà creata una risorsa cluster di condivisione file.</span><span class="sxs-lookup"><span data-stu-id="d8b23-111">This will create a file-share cluster resource.</span></span>  
  
2.  <span data-ttu-id="d8b23-112">Configurare un nodo passivo.</span><span class="sxs-lookup"><span data-stu-id="d8b23-112">Set up a passive node.</span></span>  
  
     <span data-ttu-id="d8b23-113">Al termine della configurazione, abilitare FILESTREAM nel nodo passivo usando **Gestione configurazione SQL Server**.</span><span class="sxs-lookup"><span data-stu-id="d8b23-113">After the setup finishes, enable FILESTREAM on the passive node by using **SQL Server Configuration Manager**.</span></span> <span data-ttu-id="d8b23-114">Il nome specificato per **Nome condivisione di Windows** deve essere lo stesso in tutti i nodi del cluster.</span><span class="sxs-lookup"><span data-stu-id="d8b23-114">The name that you specify for **Windows Share Name** must be the same across all nodes in the cluster.</span></span>  
  
3.  <span data-ttu-id="d8b23-115">Per aggiungere più nodi passivi, ripetere il passaggio 2.</span><span class="sxs-lookup"><span data-stu-id="d8b23-115">To add more passive nodes, repeat step 2.</span></span>  
  
4.  <span data-ttu-id="d8b23-116">Una volta aggiunti tutti i nodi, completare il processo eseguendo la stored procedure sp_configure in ogni istanza di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="d8b23-116">After all the nodes are added, complete the process by executing the sp_configure stored procedure on each instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
5.  <span data-ttu-id="d8b23-117">Per aggiungere e abilitare nodi aggiuntivi nel cluster in qualsiasi momento, ripetere i passaggi 2, 3 e 4.</span><span class="sxs-lookup"><span data-stu-id="d8b23-117">To add and enable additional nodes to the cluster at any time, you can repeat steps 2, 3, and 4.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d8b23-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d8b23-118">See Also</span></span>  
 <span data-ttu-id="d8b23-119">[Opzioni di configurazione del server &#40;SQL Server&#41;](../../database-engine/configure-windows/server-configuration-options-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="d8b23-119">[Server Configuration Options &#40;SQL Server&#41;](../../database-engine/configure-windows/server-configuration-options-sql-server.md) </span></span>  
 <span data-ttu-id="d8b23-120">[Creare un nuovo cluster di failover di SQL Server &#40;programma di installazione&#41;](../../sql-server/failover-clusters/install/create-a-new-sql-server-failover-cluster-setup.md) </span><span class="sxs-lookup"><span data-stu-id="d8b23-120">[Create a New SQL Server Failover Cluster &#40;Setup&#41;](../../sql-server/failover-clusters/install/create-a-new-sql-server-failover-cluster-setup.md) </span></span>  
 <span data-ttu-id="d8b23-121">[Rimuovere un'istanza del cluster di failover di SQL Server &#40;programma di installazione&#41;](../../sql-server/failover-clusters/install/remove-a-sql-server-failover-cluster-instance-setup.md) </span><span class="sxs-lookup"><span data-stu-id="d8b23-121">[Remove a SQL Server Failover Cluster Instance &#40;Setup&#41;](../../sql-server/failover-clusters/install/remove-a-sql-server-failover-cluster-instance-setup.md) </span></span>  
 [<span data-ttu-id="d8b23-122">Aggiungere o rimuovere nodi in un cluster di failover di SQL Server &#40;programma di installazione&#41;</span><span class="sxs-lookup"><span data-stu-id="d8b23-122">Add or Remove Nodes in a SQL Server Failover Cluster &#40;Setup&#41;</span></span>](../../sql-server/failover-clusters/install/add-or-remove-nodes-in-a-sql-server-failover-cluster-setup.md)  
  
  
