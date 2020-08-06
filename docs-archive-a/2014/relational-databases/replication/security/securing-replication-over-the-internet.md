---
title: Sicurezza della replica su Internet | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
helpviewer_keywords:
- security [SQL Server replication], Internet
- Internet [SQL Server replication], security
ms.assetid: 25b7af05-2721-4b24-9083-fb671e8bf4e0
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 47408b2b9559d33da4563c6fc9560d20338ee01d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87724487"
---
# <a name="securing-replication-over-the-internet"></a><span data-ttu-id="c0d8a-102">Sicurezza della replica su Internet</span><span class="sxs-lookup"><span data-stu-id="c0d8a-102">Securing Replication Over the Internet</span></span>
  <span data-ttu-id="c0d8a-103">La replica su Internet garantisce una notevole flessibilità, in particolare ai Sottoscrittori mobili, tuttavia richiede una configurazione appropriata per assicurare un livello di sicurezza adeguato.</span><span class="sxs-lookup"><span data-stu-id="c0d8a-103">Replication over the Internet can provide flexibility, particularly for mobile Subscribers, but you must configure Internet replication appropriately to ensure adequate security.</span></span> [!INCLUDE[msCoName](../../../includes/msconame-md.md)] <span data-ttu-id="c0d8a-104">consiglia di utilizzare una delle due tecniche seguenti per la condivisione protetta delle informazioni su Internet:</span><span class="sxs-lookup"><span data-stu-id="c0d8a-104">recommends using one of two techniques for securely sharing information over the Internet:</span></span>  
  
-   <span data-ttu-id="c0d8a-105">Rete privata virtuale (VPN, Virtual Private Network)</span><span class="sxs-lookup"><span data-stu-id="c0d8a-105">Virtual private network (VPN)</span></span>  
  
-   <span data-ttu-id="c0d8a-106">Opzione di sincronizzazione tramite il Web per la replica di tipo merge</span><span class="sxs-lookup"><span data-stu-id="c0d8a-106">The Web synchronization option for merge replication</span></span>  
  
## <a name="virtual-private-network"></a><span data-ttu-id="c0d8a-107">Rete privata virtuale</span><span class="sxs-lookup"><span data-stu-id="c0d8a-107">Virtual Private Network</span></span>  
 <span data-ttu-id="c0d8a-108">Le reti private virtuali costituiscono un approccio semplice e affidabile, strutturato su più livelli, alla replica dei dati [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] su Internet.</span><span class="sxs-lookup"><span data-stu-id="c0d8a-108">Virtual private networks provide a simple and secure layered approach to replicating [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] data over the Internet.</span></span> <span data-ttu-id="c0d8a-109">Dal punto di vista logico, la connessione VPN su Internet opera analogamente a un collegamento su rete WAN tra siti.</span><span class="sxs-lookup"><span data-stu-id="c0d8a-109">The VPN connection over the Internet logically operates as a Wide Area Network (WAN) link between the sites.</span></span>  
  
 <span data-ttu-id="c0d8a-110">A tale scopo è necessario consentire agli utenti l'esecuzione del tunneling su Internet o su un'altra rete pubblica utilizzando un protocollo disponibile in [!INCLUDE[msCoName](../../../includes/msconame-md.md)] Windows NT 4.0 o in [!INCLUDE[msCoName](../../../includes/msconame-md.md)] Windows 2000, ad esempio [!INCLUDE[msCoName](../../../includes/msconame-md.md)] PPTP (Point-to-Point Tunneling Protocol) oppure il protocollo L2TP (Layer Two Tunneling Protocol) disponibile nel sistema operativo Windows 2000.</span><span class="sxs-lookup"><span data-stu-id="c0d8a-110">This is achieved by allowing the user to tunnel through the Internet or another public network using a protocol such as [!INCLUDE[msCoName](../../../includes/msconame-md.md)] Point-to-Point Tunneling Protocol (PPTP) available with the [!INCLUDE[msCoName](../../../includes/msconame-md.md)] Windows NT version 4.0 or [!INCLUDE[msCoName](../../../includes/msconame-md.md)] Windows 2000 operating system, or Layer Two Tunneling Protocol (L2TP) available with the Windows 2000 operating system.</span></span> <span data-ttu-id="c0d8a-111">Questo processo consente di ottenere un livello di sicurezza e di caratteristiche simile a quello disponibile in una rete privata.</span><span class="sxs-lookup"><span data-stu-id="c0d8a-111">This process provides security and features similar to those available in a private network.</span></span>  
  
 <span data-ttu-id="c0d8a-112">Per ulteriori informazioni sulla configurazione di una rete VPN, vedere la documentazione di [!INCLUDE[msCoName](../../../includes/msconame-md.md)] Windows.</span><span class="sxs-lookup"><span data-stu-id="c0d8a-112">For more information about setting up a VPN, see the [!INCLUDE[msCoName](../../../includes/msconame-md.md)] Windows documentation.</span></span>  
  
## <a name="web-synchronization-through-iis"></a><span data-ttu-id="c0d8a-113">Sincronizzazione tramite il Web con IIS</span><span class="sxs-lookup"><span data-stu-id="c0d8a-113">Web Synchronization Through IIS</span></span>  
 <span data-ttu-id="c0d8a-114">L'opzione di sincronizzazione tramite il Web per la replica di tipo merge consente di replicare i dati utilizzando il protocollo HTTPS e costituisce, pertanto, un approccio conveniente alla replica dei dati attraverso un firewall.</span><span class="sxs-lookup"><span data-stu-id="c0d8a-114">The web synchronization option for merge replication provides the ability to replicate data using the HTTPS protocol, which can be a convenient approach to replicating data through a firewall.</span></span> <span data-ttu-id="c0d8a-115">Per altre informazioni, vedere [Configurare la sincronizzazione Web](../configure-web-synchronization.md) and [Architettura di sicurezza per la sincronizzazione tramite il Web](security-architecture-for-web-synchronization.md).</span><span class="sxs-lookup"><span data-stu-id="c0d8a-115">For more information, see [Configure Web Synchronization](../configure-web-synchronization.md) and [Security Architecture for Web Synchronization](security-architecture-for-web-synchronization.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c0d8a-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c0d8a-116">See Also</span></span>  
 <span data-ttu-id="c0d8a-117">[Replication Security Best Practices](replication-security-best-practices.md) </span><span class="sxs-lookup"><span data-stu-id="c0d8a-117">[Replication Security Best Practices](replication-security-best-practices.md) </span></span>  
 [<span data-ttu-id="c0d8a-118">Sicurezza replica di SQL Server</span><span class="sxs-lookup"><span data-stu-id="c0d8a-118">SQL Server Replication Security</span></span>](view-and-modify-replication-security-settings.md)  
  
  
