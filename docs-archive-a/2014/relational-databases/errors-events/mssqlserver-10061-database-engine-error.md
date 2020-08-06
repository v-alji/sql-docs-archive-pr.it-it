---
title: MSSQLSERVER_10061 | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
f1_keywords:
- "10061"
helpviewer_keywords:
- 10061 (Database Engine error)
ms.assetid: 729602f3-08df-474c-8740-8dea13c1eee3
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 0c866bd8dce01f65036f1d508a94252a97613424
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87719956"
---
# <a name="mssqlserver_10061"></a><span data-ttu-id="46963-102">MSSQLSERVER_10061</span><span class="sxs-lookup"><span data-stu-id="46963-102">MSSQLSERVER_10061</span></span>
    
## <a name="details"></a><span data-ttu-id="46963-103">Dettagli</span><span class="sxs-lookup"><span data-stu-id="46963-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="46963-104">Nome prodotto</span><span class="sxs-lookup"><span data-stu-id="46963-104">Product Name</span></span>|<span data-ttu-id="46963-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="46963-105">SQL Server</span></span>|  
|<span data-ttu-id="46963-106">ID evento</span><span class="sxs-lookup"><span data-stu-id="46963-106">Event ID</span></span>|<span data-ttu-id="46963-107">10061</span><span class="sxs-lookup"><span data-stu-id="46963-107">10061</span></span>|  
|<span data-ttu-id="46963-108">Origine evento</span><span class="sxs-lookup"><span data-stu-id="46963-108">Event Source</span></span>|<span data-ttu-id="46963-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="46963-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="46963-110">Componente</span><span class="sxs-lookup"><span data-stu-id="46963-110">Component</span></span>|<span data-ttu-id="46963-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="46963-111">SQLEngine</span></span>|  
|<span data-ttu-id="46963-112">Nome simbolico</span><span class="sxs-lookup"><span data-stu-id="46963-112">Symbolic Name</span></span>||  
|<span data-ttu-id="46963-113">Testo del messaggio</span><span class="sxs-lookup"><span data-stu-id="46963-113">Message Text</span></span>|<span data-ttu-id="46963-114">Si è verificato un errore durante il tentativo di stabilire una connessione al server.</span><span class="sxs-lookup"><span data-stu-id="46963-114">An error has occurred while establishing a connection to the server.</span></span>  <span data-ttu-id="46963-115">Quando ci si connette a SQL Server, è possibile che l'errore sia determinato dal fatto che le impostazioni predefinite di SQL Server non consentono le connessioni remote.</span><span class="sxs-lookup"><span data-stu-id="46963-115">When connecting to SQL Server, this failure may be caused by the fact that under the default settings SQL Server does not allow remote connections.</span></span> <span data-ttu-id="46963-116">(provider: provider TCP, errore: 0 - Impossibile stabilire la connessione. Rifiuto persistente del computer di destinazione.) (Microsoft SQL Server, Errore: 10061)</span><span class="sxs-lookup"><span data-stu-id="46963-116">(provider: TCP Provider, error: 0 - No connection could be made because the target machine actively refused it.) (Microsoft SQL Server, Error: 10061)</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="46963-117">Spiegazione</span><span class="sxs-lookup"><span data-stu-id="46963-117">Explanation</span></span>  
 <span data-ttu-id="46963-118">Il server non ha risposto alla richiesta del client.</span><span class="sxs-lookup"><span data-stu-id="46963-118">The server did not respond to the client request.</span></span> <span data-ttu-id="46963-119">Questo errore potrebbe verificarsi poiché il server non è stato avviato.</span><span class="sxs-lookup"><span data-stu-id="46963-119">This error could occur because the server is not started.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="46963-120">Azione dell'utente</span><span class="sxs-lookup"><span data-stu-id="46963-120">User Action</span></span>  
 <span data-ttu-id="46963-121">Verificare che il server sia stato avviato.</span><span class="sxs-lookup"><span data-stu-id="46963-121">Make sure that the server is started.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="46963-122">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="46963-122">See Also</span></span>  
 <span data-ttu-id="46963-123">[Gestire il servizio Motore di database](../../database-engine/configure-windows/manage-the-database-engine-services.md) </span><span class="sxs-lookup"><span data-stu-id="46963-123">[Manage the Database Engine Services](../../database-engine/configure-windows/manage-the-database-engine-services.md) </span></span>  
 <span data-ttu-id="46963-124">[Configurare i protocolli client](../../database-engine/configure-windows/configure-client-protocols.md) </span><span class="sxs-lookup"><span data-stu-id="46963-124">[Configure Client Protocols](../../database-engine/configure-windows/configure-client-protocols.md) </span></span>  
 <span data-ttu-id="46963-125">[Protocolli di rete e librerie di rete](../../sql-server/install/network-protocols-and-network-libraries.md) </span><span class="sxs-lookup"><span data-stu-id="46963-125">[Network Protocols and Network Libraries](../../sql-server/install/network-protocols-and-network-libraries.md) </span></span>  
 <span data-ttu-id="46963-126">[Configurazione di rete dei client](../../database-engine/configure-windows/client-network-configuration.md) </span><span class="sxs-lookup"><span data-stu-id="46963-126">[Client Network Configuration](../../database-engine/configure-windows/client-network-configuration.md) </span></span>  
 <span data-ttu-id="46963-127">[Configurare i protocolli client](../../database-engine/configure-windows/configure-client-protocols.md) </span><span class="sxs-lookup"><span data-stu-id="46963-127">[Configure Client Protocols](../../database-engine/configure-windows/configure-client-protocols.md) </span></span>  
 [<span data-ttu-id="46963-128">Abilitare o disabilitare un protocollo di rete del server</span><span class="sxs-lookup"><span data-stu-id="46963-128">Enable or Disable a Server Network Protocol</span></span>](../../database-engine/configure-windows/enable-or-disable-a-server-network-protocol.md)  
  
  
