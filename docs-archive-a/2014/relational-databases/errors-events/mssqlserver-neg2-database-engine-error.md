---
title: MSSQLSERVER_-2 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
f1_keywords:
- "2"
helpviewer_keywords:
- -2 (Database Engine error)
ms.assetid: f37a7b7d-26e1-4b9e-bcb4-57f7805393d2
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 5d39b4a11387a60056bba3f87adffcb2653b60f2
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87716368"
---
# <a name="mssqlserver_-2"></a><span data-ttu-id="ad671-102">MSSQLSERVER_-2</span><span class="sxs-lookup"><span data-stu-id="ad671-102">MSSQLSERVER_-2</span></span>
    
## <a name="details"></a><span data-ttu-id="ad671-103">Dettagli</span><span class="sxs-lookup"><span data-stu-id="ad671-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="ad671-104">Nome prodotto</span><span class="sxs-lookup"><span data-stu-id="ad671-104">Product Name</span></span>|<span data-ttu-id="ad671-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="ad671-105">SQL Server</span></span>|  
|<span data-ttu-id="ad671-106">ID evento</span><span class="sxs-lookup"><span data-stu-id="ad671-106">Event ID</span></span>|<span data-ttu-id="ad671-107">-2</span><span class="sxs-lookup"><span data-stu-id="ad671-107">-2</span></span>|  
|<span data-ttu-id="ad671-108">Origine evento</span><span class="sxs-lookup"><span data-stu-id="ad671-108">Event Source</span></span>|<span data-ttu-id="ad671-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="ad671-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="ad671-110">Componente</span><span class="sxs-lookup"><span data-stu-id="ad671-110">Component</span></span>|<span data-ttu-id="ad671-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="ad671-111">SQLEngine</span></span>|  
|<span data-ttu-id="ad671-112">Nome simbolico</span><span class="sxs-lookup"><span data-stu-id="ad671-112">Symbolic Name</span></span>||  
|<span data-ttu-id="ad671-113">Testo del messaggio</span><span class="sxs-lookup"><span data-stu-id="ad671-113">Message Text</span></span>|<span data-ttu-id="ad671-114">Timeout.</span><span class="sxs-lookup"><span data-stu-id="ad671-114">Timeout expired.</span></span>  <span data-ttu-id="ad671-115">Il tempo disponibile è scaduto prima del completamento dell'operazione o il server non risponde.</span><span class="sxs-lookup"><span data-stu-id="ad671-115">The timeout period elapsed prior to completion of the operation or the server is not responding.</span></span> <span data-ttu-id="ad671-116">(Microsoft SQL Server, Errore: -2)</span><span class="sxs-lookup"><span data-stu-id="ad671-116">(Microsoft SQL Server, Error: -2)</span></span>|   
  
## <a name="explanation"></a><span data-ttu-id="ad671-117">Spiegazione</span><span class="sxs-lookup"><span data-stu-id="ad671-117">Explanation</span></span>  
 <span data-ttu-id="ad671-118">Non è possibile stabilire la connessione tra il client [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] e il server.</span><span class="sxs-lookup"><span data-stu-id="ad671-118">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] client cannot connect to the server.</span></span> <span data-ttu-id="ad671-119">Questo errore potrebbe verificarsi poiché la connessione è stata rifiutata dal firewall del server.</span><span class="sxs-lookup"><span data-stu-id="ad671-119">This error could occur because the firewall on the server has refused the connection.</span></span> 
  
## <a name="user-action"></a><span data-ttu-id="ad671-120">Azione dell'utente</span><span class="sxs-lookup"><span data-stu-id="ad671-120">User Action</span></span>  
 <span data-ttu-id="ad671-121">Verificare che il firewall dell'istanza del server di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] sia configurato per l'accettazione delle connessioni.</span><span class="sxs-lookup"><span data-stu-id="ad671-121">Make sure that you have configured the firewall on the server instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] to accept connections.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ad671-122">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ad671-122">See Also</span></span>  
 <span data-ttu-id="ad671-123">[Configurare la Windows Firewall per consentire l'accesso SQL Server](../../sql-server/install/configure-the-windows-firewall-to-allow-sql-server-access.md) </span><span class="sxs-lookup"><span data-stu-id="ad671-123">[Configure the Windows Firewall to Allow SQL Server Access](../../sql-server/install/configure-the-windows-firewall-to-allow-sql-server-access.md) </span></span>  
 <span data-ttu-id="ad671-124">[Configurare un Windows Firewall per l'accesso motore di database](../../database-engine/configure-windows/configure-a-windows-firewall-for-database-engine-access.md) </span><span class="sxs-lookup"><span data-stu-id="ad671-124">[Configure a Windows Firewall for Database Engine Access](../../database-engine/configure-windows/configure-a-windows-firewall-for-database-engine-access.md) </span></span>  
 <span data-ttu-id="ad671-125">[Configurare i protocolli client](../../database-engine/configure-windows/configure-client-protocols.md) </span><span class="sxs-lookup"><span data-stu-id="ad671-125">[Configure Client Protocols](../../database-engine/configure-windows/configure-client-protocols.md) </span></span>  
 <span data-ttu-id="ad671-126">[Protocolli di rete e librerie di rete](../../sql-server/install/network-protocols-and-network-libraries.md) </span><span class="sxs-lookup"><span data-stu-id="ad671-126">[Network Protocols and Network Libraries](../../sql-server/install/network-protocols-and-network-libraries.md) </span></span>  
 <span data-ttu-id="ad671-127">[Configurazione di rete dei client](../../database-engine/configure-windows/client-network-configuration.md) </span><span class="sxs-lookup"><span data-stu-id="ad671-127">[Client Network Configuration](../../database-engine/configure-windows/client-network-configuration.md) </span></span>  
 <span data-ttu-id="ad671-128">[Configurare i protocolli client](../../database-engine/configure-windows/configure-client-protocols.md) </span><span class="sxs-lookup"><span data-stu-id="ad671-128">[Configure Client Protocols](../../database-engine/configure-windows/configure-client-protocols.md) </span></span>  
 [<span data-ttu-id="ad671-129">Abilitare o disabilitare un protocollo di rete del server</span><span class="sxs-lookup"><span data-stu-id="ad671-129">Enable or Disable a Server Network Protocol</span></span>](../../database-engine/configure-windows/enable-or-disable-a-server-network-protocol.md)  
  
