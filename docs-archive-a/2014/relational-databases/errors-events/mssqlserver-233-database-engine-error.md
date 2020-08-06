---
title: MSSQLSERVER_233 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
f1_keywords:
- "233"
helpviewer_keywords:
- 233 (Database Engine error)
ms.assetid: 201665dc-7ac8-4c19-90d3-33354c5caa72
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 8c51fac7c0af16c520d7cf5538e512912e62cf87
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87714391"
---
# <a name="mssqlserver_233"></a><span data-ttu-id="4b79d-102">MSSQLSERVER_233</span><span class="sxs-lookup"><span data-stu-id="4b79d-102">MSSQLSERVER_233</span></span>
    
## <a name="details"></a><span data-ttu-id="4b79d-103">Dettagli</span><span class="sxs-lookup"><span data-stu-id="4b79d-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="4b79d-104">Nome prodotto</span><span class="sxs-lookup"><span data-stu-id="4b79d-104">Product Name</span></span>|<span data-ttu-id="4b79d-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="4b79d-105">SQL Server</span></span>|  
|<span data-ttu-id="4b79d-106">ID evento</span><span class="sxs-lookup"><span data-stu-id="4b79d-106">Event ID</span></span>|<span data-ttu-id="4b79d-107">233</span><span class="sxs-lookup"><span data-stu-id="4b79d-107">233</span></span>|  
|<span data-ttu-id="4b79d-108">Origine evento</span><span class="sxs-lookup"><span data-stu-id="4b79d-108">Event Source</span></span>|<span data-ttu-id="4b79d-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="4b79d-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="4b79d-110">Componente</span><span class="sxs-lookup"><span data-stu-id="4b79d-110">Component</span></span>|<span data-ttu-id="4b79d-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="4b79d-111">SQLEngine</span></span>|  
|<span data-ttu-id="4b79d-112">Nome simbolico</span><span class="sxs-lookup"><span data-stu-id="4b79d-112">Symbolic Name</span></span>||  
|<span data-ttu-id="4b79d-113">Testo del messaggio</span><span class="sxs-lookup"><span data-stu-id="4b79d-113">Message Text</span></span>|<span data-ttu-id="4b79d-114">La connessione al server è stata stabilita con esito positivo, ma si è verificato un errore durante il processo di accesso.</span><span class="sxs-lookup"><span data-stu-id="4b79d-114">A connection was successfully established with the server, but then an error occurred during the login process.</span></span> <span data-ttu-id="4b79d-115">(provider: Provider memoria condivisa, errore: 0 - Nessun altro processo all'altra estremità della pipe.) (Microsoft SQL Server, Errore: 233)</span><span class="sxs-lookup"><span data-stu-id="4b79d-115">(provider: Shared Memory Provider, error: 0 - No process is on the other end of the pipe.) (Microsoft SQL Server, Error: 233)</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="4b79d-116">Spiegazione</span><span class="sxs-lookup"><span data-stu-id="4b79d-116">Explanation</span></span>  
 <span data-ttu-id="4b79d-117">Non è possibile stabilire la connessione tra il client [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] e il server.</span><span class="sxs-lookup"><span data-stu-id="4b79d-117">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] client cannot connect to the server.</span></span> <span data-ttu-id="4b79d-118">Questo errore potrebbe verificarsi poiché il server non è configurato per l'accettazione di connessioni remote.</span><span class="sxs-lookup"><span data-stu-id="4b79d-118">This error could occur because the server is not configured to accept remote connections.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="4b79d-119">Azione dell'utente</span><span class="sxs-lookup"><span data-stu-id="4b79d-119">User Action</span></span>  
 <span data-ttu-id="4b79d-120">Utilizzare lo strumento Gestione configurazione [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] per consentire l'accettazione di connessioni remote in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="4b79d-120">Use the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Configuration Manager tool to allow [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] to accept remote connections.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4b79d-121">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="4b79d-121">See Also</span></span>  
 <span data-ttu-id="4b79d-122">[Protocolli di rete e librerie di rete](../../sql-server/install/network-protocols-and-network-libraries.md) </span><span class="sxs-lookup"><span data-stu-id="4b79d-122">[Network Protocols and Network Libraries](../../sql-server/install/network-protocols-and-network-libraries.md) </span></span>  
 <span data-ttu-id="4b79d-123">[Configurazione di rete dei client](../../database-engine/configure-windows/client-network-configuration.md) </span><span class="sxs-lookup"><span data-stu-id="4b79d-123">[Client Network Configuration](../../database-engine/configure-windows/client-network-configuration.md) </span></span>  
 <span data-ttu-id="4b79d-124">[Configurare i protocolli client](../../database-engine/configure-windows/configure-client-protocols.md) </span><span class="sxs-lookup"><span data-stu-id="4b79d-124">[Configure Client Protocols](../../database-engine/configure-windows/configure-client-protocols.md) </span></span>  
 [<span data-ttu-id="4b79d-125">Abilitare o disabilitare un protocollo di rete del server</span><span class="sxs-lookup"><span data-stu-id="4b79d-125">Enable or Disable a Server Network Protocol</span></span>](../../database-engine/configure-windows/enable-or-disable-a-server-network-protocol.md)  
  
  
