---
title: Configurazione di rete cluster | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
f1_keywords:
- cluster network selection, Setup
- cluster network selection
ms.assetid: 579482ef-a023-45b2-9176-b4a4188adf9d
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: 17ab563817a3b9b476dfd566f4a7f2beda98ca26
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87628205"
---
# <a name="cluster-network-configuration"></a><span data-ttu-id="7a868-102">Configurazione di rete cluster</span><span class="sxs-lookup"><span data-stu-id="7a868-102">Cluster Network Configuration</span></span>
  <span data-ttu-id="7a868-103">Utilizzare la pagina **Selezione rete cluster** per specificare le risorse di rete per l'istanza del cluster di failover.</span><span class="sxs-lookup"><span data-stu-id="7a868-103">Use the **Cluster Network Selection** page to specify the network resources for your failover cluster instance.</span></span>  
  
## <a name="options"></a><span data-ttu-id="7a868-104">Opzioni</span><span class="sxs-lookup"><span data-stu-id="7a868-104">Options</span></span>  
 <span data-ttu-id="7a868-105">\*\* [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Nome di rete del cluster di failover\*\* : nome utilizzato per identificare l'istanza del cluster di failover nella rete.</span><span class="sxs-lookup"><span data-stu-id="7a868-105">**[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Failover Cluster Network Name** - This is the name used to identify your failover cluster instance on the network.</span></span>  
  
 <span data-ttu-id="7a868-106">**Impostazioni di rete** : specificare il tipo e l'indirizzo IP per l'istanza del cluster di failover.</span><span class="sxs-lookup"><span data-stu-id="7a868-106">**Network Settings** - Specify the IP type and IP address for your failover cluster instance.</span></span>  
  
 <span data-ttu-id="7a868-107">Durante le operazioni di aggiunta e rimozione dei noti, in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] viene visualizzato un elenco di sola lettura degli indirizzi IP esistenti per il cluster di failover di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="7a868-107">During the Add Node and Remove Node operations, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] displays a read-only list of the existing IP addresses for the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] failover cluster.</span></span>  
  
-   <span data-ttu-id="7a868-108">Installazione integrata:</span><span class="sxs-lookup"><span data-stu-id="7a868-108">Integrated Install:</span></span>  
  
    -   <span data-ttu-id="7a868-109">Se si aggiunge un nodo che supporta un set identico di subnet di rete supportate dai nodi esistenti nel cluster di failover di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , non sarà possibile aggiungere ulteriori indirizzi IP.</span><span class="sxs-lookup"><span data-stu-id="7a868-109">If you are adding a node that supports an identical set of network subnets supported by the existing nodes of the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] failover cluster, no additional IP addresses can be added.</span></span> <span data-ttu-id="7a868-110">L'impostazione della dipendenza rimane invariata.</span><span class="sxs-lookup"><span data-stu-id="7a868-110">The dependency setting remains unchanged.</span></span>  
  
    -   <span data-ttu-id="7a868-111">Se si aggiunge un nodo che supporta un subset di subnet supportate dai nodi esistenti nel cluster di failover di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , non sarà possibile aggiungere ulteriori risorse indirizzo IP.</span><span class="sxs-lookup"><span data-stu-id="7a868-111">If you are adding a node that supports a subset of the subnets supported by the existing nodes on the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] failover cluster, no additional IP address resources can be added.</span></span> <span data-ttu-id="7a868-112">La dipendenza della risorsa indirizzo IP viene impostata su OR per riflettere il fatto che tutti gli indirizzi IP specificati non sono validi su tutti i nodi del cluster.</span><span class="sxs-lookup"><span data-stu-id="7a868-112">The IP address resource dependency is set to OR to reflect that all the specified IP addresses are not valid on all the cluster nodes.</span></span>  
  
    -   <span data-ttu-id="7a868-113">Se si aggiunge un nodo che supporta subnet oltre a quelle già supportate dai nodi esistenti nel cluster di failover di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , si avrà la possibilità di aggiungere nuovi indirizzi IP validi.</span><span class="sxs-lookup"><span data-stu-id="7a868-113">If you are adding a node that supports subnets in addition to the subnets already supported by the existing nodes on the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] failover cluster, you have the option of adding new valid IP addresses.</span></span> <span data-ttu-id="7a868-114">Se vengono specificati nuovi indirizzi IP, la dipendenza della risorsa indirizzo IP viene impostata su OR per riflettere il fatto che tutti gli indirizzi IP specificati non sono validi su tutti i nodi del cluster.</span><span class="sxs-lookup"><span data-stu-id="7a868-114">If new IP addresses are specified, the IP address resource dependency is set to OR to reflect that all the specified IP addresses are not valid on all the cluster nodes.</span></span>  
  
    -   <span data-ttu-id="7a868-115">Se si aggiunge un nodo che supporta subnet di rete aggiuntive, ma nessuna delle subnet supportate dai nodi esistenti nel cluster di failover di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , verrà richiesto di aggiungere ulteriori indirizzi IP.</span><span class="sxs-lookup"><span data-stu-id="7a868-115">If you are adding a node that supports additional network subnets, but supports none of the subnets supported by the existing nodes on the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] failover cluster, you are required to add additional IP addresses.</span></span> <span data-ttu-id="7a868-116">La dipendenza della risorsa indirizzo IP viene impostata su OR per riflettere il fatto che tutti gli indirizzi IP specificati non sono validi su tutti i nodi del cluster.</span><span class="sxs-lookup"><span data-stu-id="7a868-116">The IP address resource dependency is set to OR to reflect that all the specified IP addresses are not valid on all the cluster nodes.</span></span>  
  
-   <span data-ttu-id="7a868-117">Installazione avanzata: durante il passaggio di completamento dell'installazione specificare l'indirizzo IP per tutti i nodi e le subnet dell'istanza del cluster di failover.</span><span class="sxs-lookup"><span data-stu-id="7a868-117">Advanced Install: During the Complete step of the installation, specify the IP address for all the nodes and subnets for your failover cluster instance.</span></span> <span data-ttu-id="7a868-118">È possibile specificare più indirizzi IP per un cluster di failover su più subnet, tuttavia è supportato un solo indirizzo IP per subnet.</span><span class="sxs-lookup"><span data-stu-id="7a868-118">You can specify multiple IP addresses for a multi-subnet failover cluster, but only one IP address per subnet is supported.</span></span> <span data-ttu-id="7a868-119">Ogni nodo preparato deve essere proprietario di almeno un indirizzo IP.</span><span class="sxs-lookup"><span data-stu-id="7a868-119">Every prepared node should be an owner of at least one IP address.</span></span> <span data-ttu-id="7a868-120">Se si dispone di più subnet nel cluster di failover di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , viene richiesto di impostare la dipendenza della risorsa indirizzo IP su OR.Rimozione nodo:</span><span class="sxs-lookup"><span data-stu-id="7a868-120">If you have multiple subnets in your [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] failover cluster, you are prompted to set the IP address resource dependency to OR.Remove Node:</span></span>  
  
    -   <span data-ttu-id="7a868-121">Se gli indirizzi IP restanti sono supportati su tutti i nodi restanti, viene richiesto di impostare la dipendenza della risorsa indirizzo IP su AND.</span><span class="sxs-lookup"><span data-stu-id="7a868-121">If the remaining IP addresses are supported on all the remaining nodes, you are prompted to set the IP address resource dependencyto AND.</span></span>  
  
    -   <span data-ttu-id="7a868-122">Se gli indirizzi IP restanti non sono supportati su tutti i nodi restanti, la dipendenza della risorsa indirizzo IP rimane impostata su OR.</span><span class="sxs-lookup"><span data-stu-id="7a868-122">If the remaining IP addresses are not supported on all the remaining nodes, the IP address resource dependency is left as OR.</span></span>  
  
  
