---
title: Topologie per la sincronizzazione tramite il Web | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
helpviewer_keywords:
- Web synchronization, topologies
- IIS server configuration [SQL Server replication]
ms.assetid: 59444faf-bcb6-4421-a3df-8715753e453b
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 5e28ca5a222e2286d154c16ef41d3147dc56e25a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87629348"
---
# <a name="topologies-for-web-synchronization"></a><span data-ttu-id="3e6aa-102">Topologie per la sincronizzazione tramite il Web</span><span class="sxs-lookup"><span data-stu-id="3e6aa-102">Topologies for Web Synchronization</span></span>
  <span data-ttu-id="3e6aa-103">È possibile scegliere tra diverse topologie di replica di sincronizzazione [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] tramite il Web.</span><span class="sxs-lookup"><span data-stu-id="3e6aa-103">You can choose from a variety of [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Web synchronization replication topologies.</span></span> <span data-ttu-id="3e6aa-104">Le modalità comuni di configurazione della sincronizzazione tramite il Web includono:</span><span class="sxs-lookup"><span data-stu-id="3e6aa-104">Common ways to configure Web synchronization include:</span></span>  
  
-   <span data-ttu-id="3e6aa-105">Server singolo</span><span class="sxs-lookup"><span data-stu-id="3e6aa-105">Single server</span></span>  
  
-   <span data-ttu-id="3e6aa-106">Due server</span><span class="sxs-lookup"><span data-stu-id="3e6aa-106">Two servers</span></span>  
  
-   <span data-ttu-id="3e6aa-107">Più sistemi [!INCLUDE[msCoName](../../includes/msconame-md.md)] Internet Information Services (IIS) e ripubblicazione [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3e6aa-107">Multiple [!INCLUDE[msCoName](../../includes/msconame-md.md)] Internet Information Services (IIS) systems and [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] republishing</span></span>  
  
 <span data-ttu-id="3e6aa-108">Per informazioni sulla configurazione della sincronizzazione Web, vedere [Configurare la sincronizzazione Web](configure-web-synchronization.md).</span><span class="sxs-lookup"><span data-stu-id="3e6aa-108">For information about configuring Web synchronization, see [Configure Web Synchronization](configure-web-synchronization.md).</span></span>  
  
## <a name="single-server"></a><span data-ttu-id="3e6aa-109">Server unico</span><span class="sxs-lookup"><span data-stu-id="3e6aa-109">Single Server</span></span>  
 <span data-ttu-id="3e6aa-110">Nella topologia più semplice, quella di tipo IIS, il server di pubblicazione [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] e il server di distribuzione [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] sono contenuti in un unico server.</span><span class="sxs-lookup"><span data-stu-id="3e6aa-110">In the simplest topology, IIS, the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Publisher, and the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Distributor all reside on a single server.</span></span> <span data-ttu-id="3e6aa-111">I Sottoscrittori si sincronizzano connettendosi ad IIS sul server di pubblicazione.</span><span class="sxs-lookup"><span data-stu-id="3e6aa-111">Subscribers synchronize by connecting to IIS on the Publisher.</span></span> <span data-ttu-id="3e6aa-112">Il server di pubblicazione può essere protetto da un firewall.</span><span class="sxs-lookup"><span data-stu-id="3e6aa-112">The Publisher can be located behind a firewall.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="3e6aa-113">L'uso di questa funzionalità è consigliabile solo per gli scenari intranet.</span><span class="sxs-lookup"><span data-stu-id="3e6aa-113">This configuration is recommended only for intranet scenarios.</span></span> <span data-ttu-id="3e6aa-114">Per gli altri scenari, è consigliabile che il server IIS e i server di pubblicazione e di distribuzione [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] si trovino su computer diversi.</span><span class="sxs-lookup"><span data-stu-id="3e6aa-114">For other scenarios, it is recommended that the IIS server and [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Publisher/Distributor be on separate computers.</span></span>  
  
 <span data-ttu-id="3e6aa-115">![Sincronizzazione Web con un singolo server](media/web-sync02.gif "Sincronizzazione Web con un singolo server")</span><span class="sxs-lookup"><span data-stu-id="3e6aa-115">![Web synchronization with a single server](media/web-sync02.gif "Web synchronization with a single server")</span></span>  
  
## <a name="two-servers"></a><span data-ttu-id="3e6aa-116">Due server</span><span class="sxs-lookup"><span data-stu-id="3e6aa-116">Two Servers</span></span>  
 <span data-ttu-id="3e6aa-117">È possibile posizionare IIS su un server e configurare il server di pubblicazione e quello di distribuzione [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] su un altro server.</span><span class="sxs-lookup"><span data-stu-id="3e6aa-117">You can place IIS on one server and configure the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Publisher and Distributor on another server.</span></span> <span data-ttu-id="3e6aa-118">Il server che esegue IIS può essere isolato da Internet da un firewall.</span><span class="sxs-lookup"><span data-stu-id="3e6aa-118">The server running IIS can be isolated from the Internet by a firewall.</span></span> <span data-ttu-id="3e6aa-119">I Sottoscrittori si sincronizzano connettendosi ad IIS.</span><span class="sxs-lookup"><span data-stu-id="3e6aa-119">Subscribers synchronize by connecting to IIS.</span></span>  
  
 <span data-ttu-id="3e6aa-120">![Sincronizzazione Web con due server](media/web-sync03.gif "Sincronizzazione Web con due server")</span><span class="sxs-lookup"><span data-stu-id="3e6aa-120">![Web synchronization with two servers](media/web-sync03.gif "Web synchronization with two servers")</span></span>  
  
## <a name="multiple-iis-systems-and-sql-server-republishing"></a><span data-ttu-id="3e6aa-121">Più sistemi IIS e ripubblicazione SQL Server</span><span class="sxs-lookup"><span data-stu-id="3e6aa-121">Multiple IIS Systems and SQL Server Republishing</span></span>  
 <span data-ttu-id="3e6aa-122">Se è necessario supportare numeri molto elevati di Sottoscrittori che si sincronizzano contemporaneamente, è possibile suddividere il lavoro tra più computer che eseguono IIS.</span><span class="sxs-lookup"><span data-stu-id="3e6aa-122">If you need to support very large numbers of Subscribers that synchronize at the same time, you can partition the work across multiple computers running IIS.</span></span>  
  
 <span data-ttu-id="3e6aa-123">![Sincronizzazione Web con più server IIS](media/web-sync04.gif "Sincronizzazione Web con più server IIS")</span><span class="sxs-lookup"><span data-stu-id="3e6aa-123">![Web synchronization with multiple IIS servers](media/web-sync04.gif "Web synchronization with multiple IIS servers")</span></span>  
  
 <span data-ttu-id="3e6aa-124">Se sul computer che esegue [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]è richiesto un ulteriore bilanciamento del carico, è possibile creare una gerarchia di ripubblicazione su più computer.</span><span class="sxs-lookup"><span data-stu-id="3e6aa-124">If further load balancing is required on the computer running [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], you can create a republishing hierarchy on multiple computers.</span></span> <span data-ttu-id="3e6aa-125">Il server di pubblicazione di livello massimo pubblica i dati nei Sottoscrittori che a loro volta ripubblicano i dati, richieste di bilanciamento del carico dei Sottoscrittori.</span><span class="sxs-lookup"><span data-stu-id="3e6aa-125">The top-level Publisher publishes data to Subscribers, which in turn republish the data, load balancing requests from the Subscribers.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="3e6aa-126">I Sottoscrittori possono eseguire la sincronizzazione solo con un server di pubblicazione specifico.</span><span class="sxs-lookup"><span data-stu-id="3e6aa-126">Subscribers can only synchronize with a specific Publisher.</span></span> <span data-ttu-id="3e6aa-127">Un Sottoscrittore del server di ripubblicazione A, ad esempio, non potrà eseguire la sincronizzazione con il server di ripubblicazione B, se A non è disponibile.</span><span class="sxs-lookup"><span data-stu-id="3e6aa-127">For example, a Subscriber to republisher A cannot synchronize with republisher B when A is not available.</span></span>  
  
 <span data-ttu-id="3e6aa-128">![Sincronizzazione Web con ripubblicazione](media/web-sync05.gif "Sincronizzazione Web con ripubblicazione")</span><span class="sxs-lookup"><span data-stu-id="3e6aa-128">![Web synchronization with republishing](media/web-sync05.gif "Web synchronization with republishing")</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3e6aa-129">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="3e6aa-129">See Also</span></span>  
 <span data-ttu-id="3e6aa-130">[Configure Web Synchronization](configure-web-synchronization.md) </span><span class="sxs-lookup"><span data-stu-id="3e6aa-130">[Configure Web Synchronization](configure-web-synchronization.md) </span></span>  
 [<span data-ttu-id="3e6aa-131">Sincronizzazione Web per la replica di tipo merge</span><span class="sxs-lookup"><span data-stu-id="3e6aa-131">Web Synchronization for Merge Replication</span></span>](web-synchronization-for-merge-replication.md)  
  
  
