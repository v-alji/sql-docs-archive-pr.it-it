---
title: Eseguire il mapping delle porte TCP/IP ai nodi NUMA (SQL Server) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
helpviewer_keywords:
- NUMA
- memory [SQL Server], NUMA
- affinity NUMA
- ports [SQL Server], working with NUMA
- CPU [SQL Server], NUMA support
- NUMA, How to map a port to a NUMA node
- NUMA affinity
- TCP/IP [SQL Server], NUMA support
- non-uniform memory access
ms.assetid: 07727642-0266-4cbc-8c55-3c367e4458ca
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: cf4a1bd7e02719d3884011ad3faa20a1ccc6466a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87712372"
---
# <a name="map-tcp-ip-ports-to-numa-nodes-sql-server"></a><span data-ttu-id="63d3f-102">Eseguire il mapping delle porte TCP/IP ai nodi NUMA (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="63d3f-102">Map TCP IP Ports to NUMA Nodes (SQL Server)</span></span>
  <span data-ttu-id="63d3f-103">In questo argomento si descrive come eseguire il mapping di porte TCP/IP ai nodi NUMA (non-uniform memory access, accesso non uniforme alla memoria) tramite Gestione configurazione [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="63d3f-103">This topic describes how to map TCP/IP ports to non-uniform memory access (NUMA) nodes by using [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Configuration Manager.</span></span> <span data-ttu-id="63d3f-104">All'avvio, tramite il [!INCLUDE[ssDE](../../includes/ssde-md.md)] vengono scritte le informazioni sul nodo nel log degli errori.</span><span class="sxs-lookup"><span data-stu-id="63d3f-104">On startup, the [!INCLUDE[ssDE](../../includes/ssde-md.md)] writes the node information to the error log.</span></span>  
  
 <span data-ttu-id="63d3f-105">Per determinare il numero del nodo da usare, leggere le informazioni sul nodo nel log degli errori o nella vista **sys.dm_os_schedulers** .</span><span class="sxs-lookup"><span data-stu-id="63d3f-105">To determine the node number of the node you want to use, either read the node information from the error log, or from the **sys.dm_os_schedulers** view.</span></span> <span data-ttu-id="63d3f-106">Per impostare un indirizzo e una porta TCP/IP in uno o più nodi, aggiungere una mappa di bit per l'identificazione del nodo, ovvero una maschera di affinità, tra parentesi dopo il numero di porta.</span><span class="sxs-lookup"><span data-stu-id="63d3f-106">To set a TCP/IP address and port to single or multiple nodes, append a node identification bitmap (an affinity mask) in brackets after the port number.</span></span> <span data-ttu-id="63d3f-107">I nodi possono essere specificati in formato decimale o esadecimale.</span><span class="sxs-lookup"><span data-stu-id="63d3f-107">Nodes can be specified in either decimal or hexadecimal format.</span></span> <span data-ttu-id="63d3f-108">Per creare la mappa di bit, numerare in primo luogo i nodi da destra a sinistra partendo da zero, come in 76543210.</span><span class="sxs-lookup"><span data-stu-id="63d3f-108">To create the bitmap, first number the nodes from right to left starting with zero, as in 76543210.</span></span> <span data-ttu-id="63d3f-109">Creare una rappresentazione binaria dell'elenco dei nodi, indicando 1 per i nodi che si desidera utilizzare e 0 per quelli che non si desidera utilizzare.</span><span class="sxs-lookup"><span data-stu-id="63d3f-109">Create a binary representation of the node list, providing 1 for nodes you want to use, and 0 for nodes you do not want to use.</span></span> <span data-ttu-id="63d3f-110">Ad esempio, per utilizzare i nodi NUMA 0, 2 e 5, specificare 00100101.</span><span class="sxs-lookup"><span data-stu-id="63d3f-110">For example, to use NUMA nodes 0, 2, and 5, specify 00100101.</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="63d3f-111">Numero del nodo NUMA</span><span class="sxs-lookup"><span data-stu-id="63d3f-111">NUMA node number</span></span>|<span data-ttu-id="63d3f-112">76543210</span><span class="sxs-lookup"><span data-stu-id="63d3f-112">76543210</span></span>|  
|<span data-ttu-id="63d3f-113">Maschera per 0, 2 e 5 partendo da destra</span><span class="sxs-lookup"><span data-stu-id="63d3f-113">Mask for 0, 2, and 5 counting from right</span></span>|<span data-ttu-id="63d3f-114">00100101</span><span class="sxs-lookup"><span data-stu-id="63d3f-114">00100101</span></span>|  
  
 <span data-ttu-id="63d3f-115">Convertire la rappresentazione binaria (00100101) in un valore decimale `[37]`o esadecimale `[0x25]`.</span><span class="sxs-lookup"><span data-stu-id="63d3f-115">Convert the binary representation (00100101), into decimal `[37]`, or hexadecimal `[0x25]`.</span></span> <span data-ttu-id="63d3f-116">Per restare in attesa su tutti i nodi, non indicare alcun identificatore di nodo.</span><span class="sxs-lookup"><span data-stu-id="63d3f-116">To listen on all nodes, provide no node identifier.</span></span>  
  
 <span data-ttu-id="63d3f-117">Se viene eseguito il mapping di una porta a più nodi NUMA, in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] vengono assegnate le connessioni ai nodi seguendo uno schema round-robin senza tentare di bilanciare il carico sui nodi.</span><span class="sxs-lookup"><span data-stu-id="63d3f-117">If a port is mapped to more than one NUMA node, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] assigns connections to nodes in a round-robin fashion without attempting to balance load across the nodes.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="63d3f-118">Per abilitare [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] all'ascolto su più porte TCP per ogni indirizzo IP, vedere [Configurazione del Motore di database per l'attesa su più porte TCP](configure-the-database-engine-to-listen-on-multiple-tcp-ports.md).</span><span class="sxs-lookup"><span data-stu-id="63d3f-118">To enable [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] to listen on multiple TCP ports for each IP address, see [Configure the Database Engine to Listen on Multiple TCP Ports](configure-the-database-engine-to-listen-on-multiple-tcp-ports.md).</span></span>  
  
##  <a name="using-sql-server-configuration-manager"></a><a name="SSMSProcedure"></a> <span data-ttu-id="63d3f-119">Utilizzo di Gestione configurazione SQL Server</span><span class="sxs-lookup"><span data-stu-id="63d3f-119">Using SQL Server Configuration Manager</span></span>  
  
#### <a name="to-map-a-tcpip-port-to-a-numa-node"></a><span data-ttu-id="63d3f-120">Per eseguire il mapping di una porta TCP/IP a un nodo NUMA</span><span class="sxs-lookup"><span data-stu-id="63d3f-120">To map a TCP/IP port to a NUMA node</span></span>  
  
1.  <span data-ttu-id="63d3f-121">In Gestione configurazione [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] espandere **Configurazione di rete SQL Server** e quindi fare clic su **Protocolli per** *\<instance name>* .</span><span class="sxs-lookup"><span data-stu-id="63d3f-121">In [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Configuration Manager, expand **SQL Server Network Configuration**, and then click **Protocols for** *\<instance name>*.</span></span>  
  
2.  <span data-ttu-id="63d3f-122">Nel riquadro dei dettagli fare doppio clic su **TCP/IP**.</span><span class="sxs-lookup"><span data-stu-id="63d3f-122">In the details pane, double-click **TCP/IP**.</span></span>  
  
3.  <span data-ttu-id="63d3f-123">Nella sezione corrispondente all'indirizzo IP da configurare della scheda **Indirizzi IP** aggiungere l'identificatore di nodo NUMA tra parentesi dopo il numero di porta nella casella **Porta TCP** .</span><span class="sxs-lookup"><span data-stu-id="63d3f-123">On the **IP Addresses** tab, in the section corresponding to the IP address to configure, in the **TCP Port** box, add the NUMA node identifier in brackets after the port number.</span></span> <span data-ttu-id="63d3f-124">Ad esempio, per la porta TCP 1500 e i nodi 0, 2 e 5, usare `1500[37]` o `1500[0x25]`.</span><span class="sxs-lookup"><span data-stu-id="63d3f-124">For example, for TCP port 1500 and nodes 0, 2, and 5, use `1500[37]`, or `1500[0x25]`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="63d3f-125">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="63d3f-125">See Also</span></span>  
 [<span data-ttu-id="63d3f-126">Configurare SQL Server per l'uso di &#40;soft-NUMA SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="63d3f-126">Configure SQL Server to Use Soft-NUMA &#40;SQL Server&#41;</span></span>](soft-numa-sql-server.md)  
  
  
