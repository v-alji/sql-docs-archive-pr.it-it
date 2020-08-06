---
title: Eseguire SQL Server in rete o non in rete | Microsoft docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
helpviewer_keywords:
- verifying Server service has been started
- net start [SQL Server]
- command prompt [SQL Server], connections
- SQL Server services, networks
- status information [SQL Server], Server service
- running SQL Server
- networking [SQL Server], SQL Server with or without
- services [SQL Server], networks
- starting Server service
- SQL Server, running
ms.assetid: 54eac961-5c7a-4481-982d-f93a64b5c2f4
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: a80e7e4d42f322bc42d0c67c57e3a1f9bddb87a0
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87628973"
---
# <a name="run-sql-server-with-or-without-a-network"></a><span data-ttu-id="062e3-102">Esecuzione di SQL Server in rete o non in rete</span><span class="sxs-lookup"><span data-stu-id="062e3-102">Run SQL Server With or Without a Network</span></span>
  [!INCLUDE[msCoName](../../includes/msconame-md.md)] <span data-ttu-id="062e3-103">[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] può essere eseguito in rete o può funzionare anche senza una rete.</span><span class="sxs-lookup"><span data-stu-id="062e3-103">[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] can run on a network, or it can function without a network.</span></span>  
  
## <a name="running-sql-server-on-a-network"></a><span data-ttu-id="062e3-104">Esecuzione di SQL Server in rete</span><span class="sxs-lookup"><span data-stu-id="062e3-104">Running SQL Server on a Network</span></span>  
 <span data-ttu-id="062e3-105">Affinché [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] possa comunicare in rete, è necessario che il servizio [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] sia in esecuzione.</span><span class="sxs-lookup"><span data-stu-id="062e3-105">For [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] to communicate over a network, the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] service must be running.</span></span> <span data-ttu-id="062e3-106">Per impostazione predefinita, il servizio [!INCLUDE[msCoName](../../includes/msconame-md.md)] viene avviato automaticamente tramite [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Windows.</span><span class="sxs-lookup"><span data-stu-id="062e3-106">By default, [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows automatically starts the built-in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] service.</span></span> <span data-ttu-id="062e3-107">Per verificare che il servizio [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] sia stato avviato, al prompt dei comandi digitare il comando seguente:</span><span class="sxs-lookup"><span data-stu-id="062e3-107">To find out whether the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] service has been started, at the command prompt, type the following:</span></span>  
  
 <span data-ttu-id="062e3-108">**net start**</span><span class="sxs-lookup"><span data-stu-id="062e3-108">**net start**</span></span>  
  
 <span data-ttu-id="062e3-109">Se i servizi associati a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] sono stati avviati, nell'output di **net start** vengono visualizzati i servizi seguenti:</span><span class="sxs-lookup"><span data-stu-id="062e3-109">If the services associated with [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] have been started, the following services will appear in the **net start** output:</span></span>  
  
-   <span data-ttu-id="062e3-110">Analysis Services (MSSQLSERVER)</span><span class="sxs-lookup"><span data-stu-id="062e3-110">Analysis Services (MSSQLSERVER)</span></span>  
  
-   <span data-ttu-id="062e3-111">SQL Server (MSSQLSERVER)</span><span class="sxs-lookup"><span data-stu-id="062e3-111">SQL Server (MSSQLSERVER)</span></span>  
  
-   <span data-ttu-id="062e3-112">SQL Server Agent (MSSQLSERVER)</span><span class="sxs-lookup"><span data-stu-id="062e3-112">SQL Server Agent (MSSQLSERVER)</span></span>  
  
## <a name="running-sql-server-without-a-network"></a><span data-ttu-id="062e3-113">Esecuzione di SQL Server non in rete</span><span class="sxs-lookup"><span data-stu-id="062e3-113">Running SQL Server Without a Network</span></span>  
 <span data-ttu-id="062e3-114">Quando si esegue un'istanza di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] non in rete, non è necessario avviare il servizio predefinito [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="062e3-114">When running an instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] without a network, you do not need to start the built-in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] service.</span></span> <span data-ttu-id="062e3-115">Poiché [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], Gestione configurazione SQL Server e i comandi **net start** e **net stop** funzionano anche senza una rete, le procedure per l'avvio e l'arresto di un'istanza di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] sono identiche per operazioni in rete e in modalità autonoma.</span><span class="sxs-lookup"><span data-stu-id="062e3-115">Because [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], SQL Server Configuration Manager, and the **net start** and **net stop** commands are functional even without a network, the procedures for starting and stopping an instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] are identical for a network or stand-alone operation.</span></span>  
  
 <span data-ttu-id="062e3-116">Quando ci si connette a un'istanza autonoma di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] da un client locale quale **sqlcmd**, la connessione alla rete viene ignorata e si accede direttamente all'istanza di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] tramite una pipe locale.</span><span class="sxs-lookup"><span data-stu-id="062e3-116">When connecting to an instance of a stand-alone [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] from a local client such as **sqlcmd**, you bypass the network and connect directly to the instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] by using a local pipe.</span></span> <span data-ttu-id="062e3-117">La pipe locale e la pipe di rete vengono utilizzate rispettivamente quando non si utilizza e si utilizza la rete.</span><span class="sxs-lookup"><span data-stu-id="062e3-117">The difference between a local pipe and a network pipe is whether you are using a network.</span></span> <span data-ttu-id="062e3-118">Salvo diversa indicazione, le pipe locali e quelle di rete stabiliscono una connessione a un'istanza di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] tramite la pipe standard (\\\\.\pipe\sql\query).</span><span class="sxs-lookup"><span data-stu-id="062e3-118">Both local and network pipes establish a connection with an instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] by using the standard pipe (\\\\.\pipe\sql\query), unless otherwise directed.</span></span>  
  
 <span data-ttu-id="062e3-119">Quando si esegue la connessione a un'istanza locale di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] senza specificare il nome di un server, si utilizza una pipe locale.</span><span class="sxs-lookup"><span data-stu-id="062e3-119">When you connect to an instance of a local [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] without specifying a server name, you are using a local pipe.</span></span> <span data-ttu-id="062e3-120">Quando si esegue la connessione a un'istanza locale di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] e si specifica un nome di server, si utilizza una pipe di rete o un altro meccanismo IPC (InterProcess Communication) di rete, ad esempio IPX/SPX (Internetwork Packet Exchange/Sequenced Packet Exchange), a condizione che [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] sia stato configurato per l'utilizzo di più reti.</span><span class="sxs-lookup"><span data-stu-id="062e3-120">When you connect to an instance of a local [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] and specify a server name explicitly, you are using either a network pipe or another network interprocess communication (IPC) mechanism, such as Internetwork Packet Exchange/Sequenced Packet Exchange (IPX/SPX) (assuming you have configured [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] to use multiple networks).</span></span> <span data-ttu-id="062e3-121">Poiché un'istanza autonoma di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] non supporta le pipe di rete, è necessario omettere l'argomento non necessario **/** _<nome_server>_ quando ci si connette all'istanza di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] da un client.</span><span class="sxs-lookup"><span data-stu-id="062e3-121">Because a stand-alone [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] does not support network pipes, you must omit the unnecessary **/**_<Server_name>_ argument when connecting to the instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] from a client.</span></span> <span data-ttu-id="062e3-122">Ad esempio, per connettersi a un'istanza autonoma di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] da **osql**, digitare:</span><span class="sxs-lookup"><span data-stu-id="062e3-122">For example, to connect to a stand-alone instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] from **osql**, type:</span></span>  
  
 <span data-ttu-id="062e3-123">**osql /Usa /P** _\<saPassword>_</span><span class="sxs-lookup"><span data-stu-id="062e3-123">**osql /Usa /P** _\<saPassword>_</span></span>  
  
  
