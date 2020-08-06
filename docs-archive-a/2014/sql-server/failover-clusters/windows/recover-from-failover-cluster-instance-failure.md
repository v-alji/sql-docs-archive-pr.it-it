---
title: Recuperare da un errore dell'istanza del cluster di failover | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: high-availability
ms.topic: conceptual
helpviewer_keywords:
- clusters [SQL Server], recovery from failure
- failover clustering [SQL Server], recovery from failure
- hardware failures [SQL Server]
- recovering failover cluster failures [SQL Server]
ms.assetid: 3d151d0c-e841-4325-8606-c094de37d7d1
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 60db4c2e480b094c18d0a8071e947a38cdc779d8
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87724432"
---
# <a name="recover-from-failover-cluster-instance-failure"></a><span data-ttu-id="5bbec-102">Recuperare da un errore dell'istanza del cluster di failover</span><span class="sxs-lookup"><span data-stu-id="5bbec-102">Recover from Failover Cluster Instance Failure</span></span>
  <span data-ttu-id="5bbec-103">In questo argomento viene descritta la modalità di recupero dagli errori del cluster tramite lo snap-in Gestione cluster di failover quando si verifica il failover in [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)].</span><span class="sxs-lookup"><span data-stu-id="5bbec-103">This topic describes how to recover from cluster failures by using the Failover Cluster Manager snap-in after a failover occurs in [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)].</span></span> <span data-ttu-id="5bbec-104">Lo snap-in Gestione cluster di failover è l'applicazione di gestione cluster per il servizio Windows Server Failover Clustering (WSFC).</span><span class="sxs-lookup"><span data-stu-id="5bbec-104">The Failover Cluster Manager snap-in is the cluster management application for the Windows Serer Failover Clustering (WSFC) service.</span></span>  
  
-   [<span data-ttu-id="5bbec-105">Ripristino da un errore irreversibile</span><span class="sxs-lookup"><span data-stu-id="5bbec-105">Recover from an irreparable failure</span></span>](#Scenario1)  
  
-   [<span data-ttu-id="5bbec-106">Recuperare da un errore software</span><span class="sxs-lookup"><span data-stu-id="5bbec-106">Recover from a software failure</span></span>](#Scenario2)  
  
##  <a name="recover-from-an-irreparable-failure"></a><a name="Scenario1"></a> <span data-ttu-id="5bbec-107">Recuperare da un errore irreversibile</span><span class="sxs-lookup"><span data-stu-id="5bbec-107">Recover from an irreparable failure</span></span>  
 <span data-ttu-id="5bbec-108">Eseguire i passi di seguito riportati per recuperare da un errore irreversibile.</span><span class="sxs-lookup"><span data-stu-id="5bbec-108">Use the following steps to recover from an irreparable failure.</span></span> <span data-ttu-id="5bbec-109">Questo errore può essere provocato, ad esempio, dall'errore di un controller del disco o del sistema operativo.</span><span class="sxs-lookup"><span data-stu-id="5bbec-109">The failure could be caused, for example, by the failure of a disk controller or the operating system.</span></span> <span data-ttu-id="5bbec-110">In questo caso il problema dipende da un errore hardware nel nodo 1 di un cluster a due nodi.</span><span class="sxs-lookup"><span data-stu-id="5bbec-110">In this case, failure is caused by hardware failure in Node 1 of a two-node cluster.</span></span>  
  
1.  <span data-ttu-id="5bbec-111">Dopo l'errore del Nodo 1, l'istanza FCI di [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] genera un errore sul Nodo 2.</span><span class="sxs-lookup"><span data-stu-id="5bbec-111">After Node 1 fails, the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] FCI fails over to Node 2.</span></span>  
  
2.  <span data-ttu-id="5bbec-112">Rimuovere il Nodo 1 dall'istanza FCI.</span><span class="sxs-lookup"><span data-stu-id="5bbec-112">Evict Node 1 from the FCI.</span></span> <span data-ttu-id="5bbec-113">A tale scopo, aprire lo snap-in Gestione cluster di failover dal Nodo 2, fare clic con il pulsante destro del mouse sul Nodo 1, quindi fare clic su **Sposta azioni**, quindi scegliere **Rimuovi nodo**.</span><span class="sxs-lookup"><span data-stu-id="5bbec-113">To do this, from Node 2, open the Failover Cluster Manager snap-in, right-click Node1, click **Move Actions**, and then click **Evict Node**.</span></span>  
  
3.  <span data-ttu-id="5bbec-114">Verificare che il Nodo 1 sia stato rimosso dalla definizione del cluster.</span><span class="sxs-lookup"><span data-stu-id="5bbec-114">Verify that Node 1 has been evicted from the cluster definition.</span></span>  
  
4.  <span data-ttu-id="5bbec-115">Installare il nuovo componente hardware per sostituire quello danneggiato nel Nodo 1.</span><span class="sxs-lookup"><span data-stu-id="5bbec-115">Install new hardware to replace the failed hardware in Node 1.</span></span>  
  
5.  <span data-ttu-id="5bbec-116">Tramite lo snap-in Gestione cluster di failover, aggiungere il Nodo 1 al cluster esistente.</span><span class="sxs-lookup"><span data-stu-id="5bbec-116">Using the Failover Cluster Manager snap-in, add Node 1 to the existing cluster.</span></span> <span data-ttu-id="5bbec-117">Per altre informazioni, vedere [Operazioni preliminari all'installazione del clustering di failover](../install/before-installing-failover-clustering.md).</span><span class="sxs-lookup"><span data-stu-id="5bbec-117">For more information, see [Before Installing Failover Clustering](../install/before-installing-failover-clustering.md).</span></span>  
  
6.  <span data-ttu-id="5bbec-118">Assicurarsi che gli account amministratore siano gli stessi in tutti i nodi del cluster.</span><span class="sxs-lookup"><span data-stu-id="5bbec-118">Ensure that the administrator accounts are the same on all cluster nodes.</span></span>  
  
7.  <span data-ttu-id="5bbec-119">Eseguire il programma di installazione di [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] per aggiungere il Nodo 1 all'istanza FCI.</span><span class="sxs-lookup"><span data-stu-id="5bbec-119">Run [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Setup to add Node 1 to the FCI.</span></span> <span data-ttu-id="5bbec-120">Per altre informazioni, vedere [Aggiungere o rimuovere nodi in un cluster di failover di SQL Server &#40;programma di installazione&#41;](../install/add-or-remove-nodes-in-a-sql-server-failover-cluster-setup.md).</span><span class="sxs-lookup"><span data-stu-id="5bbec-120">For more information, see [Add or Remove Nodes in a SQL Server Failover Cluster &#40;Setup&#41;](../install/add-or-remove-nodes-in-a-sql-server-failover-cluster-setup.md).</span></span>  
  
##  <a name="recover-from-a-reparable-failure"></a><a name="Scenario2"></a> <span data-ttu-id="5bbec-121">Recuperare da un errore reversibile</span><span class="sxs-lookup"><span data-stu-id="5bbec-121">Recover from a reparable failure</span></span>  
 <span data-ttu-id="5bbec-122">Eseguire i passi di seguito riportati per recuperare da un errore reversibile.</span><span class="sxs-lookup"><span data-stu-id="5bbec-122">Us the following steps to recover from a reparable failure.</span></span> <span data-ttu-id="5bbec-123">In questo caso, l'errore dipende dalla mancata disponibilità o dall'interruzione del collegamento del Nodo 1, che tuttavia non è danneggiato.</span><span class="sxs-lookup"><span data-stu-id="5bbec-123">In this case, failure is caused by Node 1 being down or offline but not irretrievably broken.</span></span> <span data-ttu-id="5bbec-124">L'errore può essere causato da un errore del sistema operativo, da un errore hardware o da un errore dell'istanza di [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="5bbec-124">This could be caused by an operating system failure, hardware failure, or failure in the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] instance itself.</span></span>  
  
1.  <span data-ttu-id="5bbec-125">Dopo l'errore del Nodo 1, l'istanza FCI genera un errore sul Nodo 2.</span><span class="sxs-lookup"><span data-stu-id="5bbec-125">After Node 1 fails, the FCI fails over to Node 2.</span></span>  
  
2.  <span data-ttu-id="5bbec-126">Risolvere il problema del Nodo 1.</span><span class="sxs-lookup"><span data-stu-id="5bbec-126">Resolve the problem with Node 1.</span></span>  
  
3.  <span data-ttu-id="5bbec-127">Accertarsi che tutti i nodi siano online e il servizio WSFC sia funzionante.</span><span class="sxs-lookup"><span data-stu-id="5bbec-127">Ensure that all nodes are online and the WSFC service is working.</span></span>  
  
4.  <span data-ttu-id="5bbec-128">Eseguire il failover di [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] nel nodo recuperato.</span><span class="sxs-lookup"><span data-stu-id="5bbec-128">Fail over [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] to the recovered node.</span></span>  
  
  
